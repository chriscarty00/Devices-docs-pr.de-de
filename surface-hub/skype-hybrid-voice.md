---
title: Online- oder Hybridbereitstellung mithilfe von Skype-Hybrid-Voice-Umgebung (Surface Hub)
description: In diesem Thema wird erläutert, wie Skype for Business Cloud PBX mit lokaler PSTN-Konnektivität über den Cloud Connector Edition- oder Skype for Business 2015-Pool aktiviert wird.
keywords: Hybridbereitstellung, Skype-Hybrid-Voice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833841"
---
# Online- oder Hybridbereitstellung mithilfe von Skype-Hybrid-Voice-Umgebung (Surface Hub)

In diesem Thema wird erläutert, wie Skype for Business Cloud PBX mit lokaler PSTN (Public Switched Telephone Network)-Konnektivität über den Cloud Connector Edition- oder Skype for Business 2015-Pool aktiviert wird. In dieser Option. Ihre Skype for Business-Home-Pools und Exchange-Server sind in der Cloud und per PSTN über einen lokalen Pool verbunden, auf dem Skype for Business 2015 oder Cloud Connector Edition ausgeführt wird. [Weitere Informationen über die verschiedenen Cloud PBX-Optionen](https://technet.microsoft.com/library/mt612869.aspx).  

Wenn Sie Skype for Business Cloud PBX mit einer der Hybrid-Voice-Optionen bereitgestellt haben, führen Sie die folgenden Schrittezum Aktivieren des Raumkontos für Surface Hub aus. Es ist wichtig, zunächst ein normales Benutzerkonto zu erstellen, alle Hybrid-Sprachoptionen und Telefonnummern zuzuweisen und das Konto in ein Raumkonto zu konvertieren. Wenn Sie diese Reihenfolge nicht befolgen, können Sie keine hybride Telefonnummer zuweisen.  

>[!WARNING]
>Wenn Sie ein Konto vor der Konfiguration von Hybrid-Voice erstellen (Sie führen den Befehl Enable-CSMeetingRoom aus), können Sie die erforderlichen Hybrid-Voice-Parameter nicht konfigurieren. Zum Konfigurieren von Hybrid-Voice-Parametern für ein zuvor konfiguriertes Konto oder zum Neukonfigurieren einer Telefonnummer löschen Sie die E5 oder E3 + Cloud PBX-Add-On-Lizenz, und befolgen Sie die unten stehenden Schritte, beginnend mit Schritt3.

1. Erstellen Sie ein neues Benutzerkonto für Surface Hub. In diesem Beispiel wird <strong> surfacehub2@adatum.com verwendet </strong> . Das Konto kann in lokales Active Directory erstellt und mit der Cloud synchronisiert oder direkt in der Cloud erstellt werden. 

    ![Neuer Objekt-Benutzer](images/new-user-hybrid-voice.png)

2. Wählen Sie **Kennwort läuft nie ab** aus. Dies ist wichtig für ein Surface Hub-Gerät.

   ![Kennwort läuft nie ab](images/new-user-password-hybrid-voice.png)

3. Fügen Sie in Office365 die **E5**-Lizenz oder das **E3 und Cloud PBX**-Add-On dem Benutzerkonto hinzu, das für den Raum erstellt wurde. Dies ist erforderlich, damit Hybrid-Voice funktioniert.

   ![Produkt-Lizenz hinzufügen](images/product-license-hybrid-voice.png)

4. Warten Sie etwa 15Minuten, bis das Benutzerkonto für den Raum in Skype for Business Online angezeigt wird.

5. Nachdem das Benutzerkonto für Raum in Skype for Business Online erstellt wurde, aktivieren sie es für Hybrid-Voice in Skype for Business-Remote-PowerShell durch Ausführen des folgenden Cmdlet:

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. Überprüfen Sie den Hybrid-Voice-Abfrageablauf, indem Sie Testabfragen über den Surface Hub tätigen.

7. Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange her, indem Sie die folgenden Cmdlets ausführen.

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. Nach dem Einrichten einer Sitzung ändern Sie das Benutzerkonto für den Raum, um es als **RoomMailboxAccount** zu aktivieren, indem Sie die folgenden Cmdlets ausführen. Dadurch kann das Konto mit Surface Hub authentifiziert werden.

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.

   Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled**-Eigenschaft auf **False** festgelegt ist. Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.
    
   Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet (dieses erstellt eine Richtlinie namens „Surface Hubs“). Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   Wenn Sie über eine kompatible Richtlinie verfügen, müssen Sie die Richtlinie auf das Gerätekonto anwenden. Richtlinien können jedoch nur auf Benutzerkonten und nicht auf Ressourcenpostfächer angewendet werden. Führen Sie die folgenden Cmdlets aus, um das Postfach in einen Benutzertyp umzuwandeln, die Richtlinie anzuwenden und dann wieder zurück in ein Postfach umzuwandeln (Sie müssen das Konto möglicherweise erneut aktivieren und das Kennwort noch einmal festlegen).
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. Für das Gerätekonto müssen verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern. Sie können sehen, welche Eigenschaften in [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) festgelegt werden können. Die folgenden Cmdlets bieten ein Beispiel zum Festlegen von Exchange-Eigenschaften.

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. Aktivieren Sie das Postfach als ein Besprechungsgerät in Skype for Business Online. Führen Sie das folgende Cmdlet aus, das das Konto als Besprechungs Gerät aktiviert. 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    Durch Ausführen dieses Cmdlet werden Benutzer gefragt, ob sie einen Besprechungsraum sind, wie in der folgenden Abbildung dargestellt. Mit **Ja** werden Mikrofon und Lautsprecher stummgeschaltet.

    ![](images/adjust-room-audio.png)


    
Derzeit ist das Raumkonto vollständig konfiguriert, einschließlich Hybrid-Voice. Wenn Sie Skype lokal verwenden, können Sie zusätzliche Attribute, z.B. Beschreibung, Position usw., lokal konfigurieren. Wenn Sie einen Raum in Skype Online erstellen, können diese Parameter online festgelegt werden. 

In der folgenden Abbildungsehen Sie, wie das Gerät für die Benutzer angezeigt wird.


![](images/select-room-hybrid-voice.png)
