---
title: Lokale Bereitstellung mit mehreren Gesamtstrukturen (Surface Hub)
description: In diesem Thema wird erläutert, wie Sie ein Gerätekonto für Microsoft Surface Hub bei einer lokalen Bereitstellung mit mehreren Gesamtstrukturen hinzufügen.
keywords: Bereitstellung mit mehreren Gesamtstrukturen, lokale Bereitstellung, Gerätekonto, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833619"
---
# Lokale Bereitstellung für Surface Hub in einer Umgebung mit mehreren Gesamtstrukturen


In diesem Thema wird erläutert, wie Sie ein Gerätekonto für Microsoft Surface Hub bei einer lokalen Bereitstellung mit mehreren Gesamtstrukturen hinzufügen.

Bei einer lokalen Bereitstellung mit mehreren Gesamtstrukturen mit Microsoft Exchange 2013 oder höher und Skype for Business 2013 oder höher können Sie [die bereitgestellten PowerShell-Skripts verwenden](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts), um Gerätekonten zu erstellen. Wenn Sie eine Bereitstellung mit einer Gesamtstruktur verwenden, siehe [lokale Bereitstellung für Surface Hub in einer Umgebung mit einer Gesamtstruktur](on-premises-deployment-surface-hub-device-accounts.md).

1.  Starten Sie eine Remote-PowerShell-Sitzung von einem PC aus, und stellen Sie eine Verbindung mit Exchange her.

    Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.

    Beachten Sie hier, dass `$strExchangeServer` der vollqualifizierte Domänenname (FQDN) des Exchange-Servers und `$strLyncFQDN` der vollqualifizierte Domänenname des Skype for Business-Servers ist.

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  Nach dem Einrichten einer Sitzung ein neues Postfach in der Ressourcengesamtstruktur erstellen. Dadurch kann das Konto in Surface Hub authentifiziert werden.

    Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.

    Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled**-Eigenschaft auf **False** festgelegt ist. Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.

    Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet –– dieses erstellt eine Richtlinie namens „Surface Hubs“. Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    Wenn Sie über eine kompatible Richtlinie verfügen, müssen Sie die Richtlinie auf das Gerätekonto anwenden. 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis für Benutzer zu verbessern. Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md). Dies sollte in der Benutzergesamtstruktur festgelegt werden.

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  Aktivieren Sie das Konto in Active Directory, damit es bei Surface Hub authentifiziert wird. Dies sollte in der Benutzergesamtstruktur festgelegt werden.

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. Jetzt müssen Sie das Postfach auf ein verknüpftes Postfach ändern:

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  Aktivieren Sie das Gerätekonto mit Skype for Business, indem Sie das Surface Hub-AD-Konto für einen Skype for Business Server-Pool aktivieren:

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    Sie müssen die Session Initiation-Protokoll (SIP)-Adresse und den Domänencontroller für Surface Hub zusammen mit Ihrer eigenen Skype for Business Server-Pool-ID und Benutzeridentität verwenden.


## Deaktivieren anonymer e-Mails und Chatnachrichten



Surface Hub verwendet ein Geräte Konto, um e-Mail-und Zusammenarbeitsdienste (Chat, Video, Sprache) bereitzustellen. Dieses Geräte Konto wird als Ursprungsidentität ("von"-Partei) beim Senden von e-Mails, Chats und Anrufen verwendet. Da dieses Konto nicht von einem einzelnen, identifizierbaren Nutzer stammt, wird es als "Anonym" eingestuft, da es vom Device-Konto des Surface Hub stammt.  

Angenommen, Sie verfügen über eine benutzerspezifische Clientrichtlinie, die jedem Besprechungsraum Gerät mit einer Identität von **SurfaceHubPolicy**zugeordnet ist. Zum Deaktivieren anonymer e-Mails und Nachrichten fügen Sie dieser Clientrichtlinie mithilfe der folgenden Befehle eine clientPolicyEntry hinzu.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

So überprüfen Sie, ob die Richtlinie festgesetzt wurde:

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

Die Ausgabe sollte wie folgt lauten:

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
So ändern Sie den Richtlinieneintrag:

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
So entfernen Sie den Richtlinieneintrag:

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





