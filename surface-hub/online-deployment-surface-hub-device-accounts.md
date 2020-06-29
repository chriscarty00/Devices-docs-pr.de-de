---
title: Onlinebereitstellung mit Office 365 (Surface Hub)
description: Dieses Thema enthält Anweisungen zum Hinzufügen eines Gerätekontos für Microsoft Surface Hub bei einer reinen Onlinebereitstellung.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: Gerätekonto für Surface Hub, Onlinebereitstellung
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833616"
---
# Onlinebereitstellung mit Office 365 (Surface Hub)


Dieses Thema enthält Anweisungen zum Hinzufügen eines Gerätekontos für Microsoft Surface Hub bei einer reinen Onlinebereitstellung.

Bei einer reinen Onlinebereitstellung (O365) können Sie [die bereitgestellten PowerShell-Skripts verwenden](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts), um Gerätekonten zu erstellen. 

1. Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange her.

   Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann das Konto in Surface Hub authentifiziert werden.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Wenn Sie ein neues Ressourcenpostfach erstellen:

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.

   Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist. Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.

   Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“. Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   Wenn Sie über eine kompatible Richtlinie verfügen, müssen Sie die Richtlinie auf das Gerätekonto anwenden.

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. Für das Gerätekonto müssen verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern. Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Stellen Sie eine Verbindung mit Azure AD her.
    
   Sie müssen zuerst das Azure AD-Modul für die PowerShell Version 2 installieren. Führen Sie an einer PowerShell-Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl aus:
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   Sie müssen eine Verbindung mit Azure AD herstellen, um einige Kontoeinstellungen anzuwenden. Sie können zum Herstellen der Verbindung dieses Cmdlet ausführen.

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub erfordert eine Lizenz für Skype for Business-Funktionen. Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende [Voraussetzungen für Skype for Business Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online) erfüllen.
   
   Als Nächstes können Sie mit `Get-AzureADSubscribedSku` eine Liste der verfügbaren SKUs für Ihren O365-Mandanten abrufen.

   Nachdem Sie die SKUs aufgelistet haben, müssen Sie die die für die `$License.SkuId`-Variable gewünschte SKU-ID zuweisen.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. Aktivieren Sie das Gerätekonto mit Skype for Business.
   Wenn das Skype for Business-PowerShell-Modul nicht installiert ist, [laden Sie hier das Skype for Business Online Windows PowerShell-Modul herunter](https://www.microsoft.com/download/details.aspx?id=39366). 

   - Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - Wenn Sie sich dann nicht sicher sind, welcher Wert für den `RegistrarPool`-Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen (z.B. <em>alice@contoso.com</em>):

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       ODER durch Festlegen einer Variablen
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - Aktivieren Sie das Surface Hub-Konto mit dem folgenden Cmdlet:
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       ODER verwenden Sie die Variable $strRegistarPool von oben
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

Zur Überprüfung sollten Sie jeden Skype for Business-Client (PC, Android usw.) verwenden können, um sich bei diesem Konto anzumelden.





