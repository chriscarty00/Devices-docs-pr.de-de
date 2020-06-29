---
title: Hybridbereitstellung (Surface Hub)
description: Eine Hybridbereitstellung erfordert eine spezielle Verarbeitung, um ein Gerätekonto für Ihren Microsoft Surface Hub einzurichten.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: Hybridbereitstellung, Gerätekonto für Surface Hub, Exchange lokal gehostet, Exchange online gehostet
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833670"
---
# Hybridbereitstellung (Surface Hub)

Eine Hybridbereitstellung erfordert eine spezielle Verarbeitung, um ein Gerätekonto für Ihren Microsoft Surface Hub einzurichten. Bei Verwendung einer Hybridbereitstellung, in der Ihre Organisation über verschiedene Dienste verfügt, von denen einige lokal und einige online gehostet werden, hängt die Konfiguration davon ab, wo jeder Dienst gehostet wird. In diesem Thema werden Hybridbereitstellungen für [Exchange lokal gehostet](#exchange-on-premises), [Exchange online gehostet](#exchange-online), Skype for Business in einer lokalen Umgebung, [Skype for Business Online und Skype for Business in einer hybriden Umgebung behandelt. Da es so viele unterschiedliche Varianten bei dieser Art von Bereitstellung gibt, ist es nicht möglich, ausführliche Anweisungen für alle davon bereitzustellen. Der folgende Prozess funktioniert für viele Konfigurationen. Wenn der Prozess für Ihre Konfiguration nicht geeignet ist, wird empfohlen, PowerShell zu verwenden (siehe [Anhang: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)), um dasselbe Endergebnis wie hier dokumentiert zu erzielen. Diese Vorgehensweise kann auch für andere Bereitstellungsoptionen verwendet werden. Sie sollten dann das bereitgestellte PowerShell-Skript verwenden, um Ihr Surface Hub-Setup zu überprüfen. (Informationen finden Sie unter [Kontovalidierungsskript](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)

> [!NOTE]
> Führen Sie in einer Exchange-Hybridumgebung die Schritte für [Exchange lokal](#exchange-on-premises)aus. Verwenden Sie das Cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) , um Exchange-Objekte nach Office 365 zu verschieben.

## Exchange lokal

Nutzen Sie dieses Verfahren, wenn Sie Exchange lokal verwenden.

1. Bei diesem Verfahren werden AD-Verwaltungstools verwendet, um für Ihr lokales Domänenkonto eine E-Mail-Adresse hinzuzufügen. Dieses Konto wird mit Office 365 synchronisiert.

- Klicken Sie im AD-Tool **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in der Ihre Surface Hub-Konten erstellt werden, klicken Sie auf **Neu**, und **Benutzer**.
- Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet im Feld **Vollständiger Name** und den Alias im Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.<p>

![Feld „Neues Objekt“ zum Erstellen eines neuen Benutzers in Active Directory](images/hybriddeployment-01a.png)

- Geben Sie das Kennwort für dieses Konto ein. Es muss zur Bestätigung erneut eingegeben werden. Stellen Sie sicher, dass das Kontrollkästchen **Kennwort läuft niemals ab** die einzige aktivierte Option ist.

> **Wichtig:** Die Auswahl von **Kennwort läuft niemals ab** ist eine Voraussetzung für Skype for Business auf Surface Hub. Ihre Domänenregeln können Kennwörter untersagen, die nicht ablaufen. In diesem Fall müssen Sie eine Ausnahme für jedes Surface Hub-Gerätekonto erstellen.

![Bild mit Dialogfeld „Kennwort“](images/hybriddeployment-02a.png)

-   Klicken Sie auf **Fertig stellen** , um das Konto zu erstellen.

![Bild mit Kontoname, Anmeldename und Kennwortoptionen für einen neuen Benutzer](images/hybriddeployment-03a.png)

2. Aktivieren Sie das Remote-Postfach.

Öffnen Sie die lokale Exchange-Verwaltungsshell mit Administratorberechtigungen, und führen Sie dieses Cmdlet aus.

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> Besitzen Sie keine lokale Exchange-Umgebung, um dieses Cmdlet auszuführen, können Sie die gleichen direkt auf das Active Directory-Objekt für das Konto ändern.
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. Führen Sie eine Verzeichnissynchronisierung aus, nachdem Sie das Konto erstellt haben. Wenn Sie fertig sind, wechseln Sie zur Seite "Benutzer" im Microsoft 365 Admin Center, und überprüfen Sie, ob das in den vorherigen Schritten erstellte Konto mit Online verbunden wurde.

4. Stellen Sie eine Verbindung mit Microsoft Exchange Online her, und legen Sie einige Eigenschaften für das Konto in Office 365 fest.

Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Microsoft Exchange her. Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.

Die nächsten Schritten werden auf dem Office 365-Mandanten ausgeführt.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. Erstellen Sie eine neue Exchange ActiveSync-Richtlinie, oder verwenden Sie eine kompatible vorhandene Richtlinie.

Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.

Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled**-Eigenschaft auf „False“ festgelegt ist. Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.

Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“. Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Nachdem Sie eine kompatible Richtlinie haben, müssen Sie die Richtlinie auf das Geräte Konto anwenden. 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. Legen Sie Exchange-Eigenschaften fest.

Exchange-Eigenschaften werden für das Gerätekonto festgelegt, um das Besprechungsergebnis zu verbessern. Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. Stellen Sie eine Verbindung mit Azure AD her.

Sie müssen zuerst das Azure AD-Modul für die PowerShell Version 2 installieren. Führen Sie in einer Eingabeaufforderung mit erhöhten PowerShell den folgenden Befehl aus:

```PowerShell
Install-Module -Name AzureAD
```

Sie müssen eine Verbindung mit Azure AD herstellen, um einige Kontoeinstellungen anzuwenden. Sie können zum Herstellen der Verbindung dieses Cmdlet ausführen.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Weisen Sie eine Office 365-Lizenz zu.

Das Gerätekonto benötigt eine gültige Office 365 (O365)-Lizenz, andernfalls funktionieren Exchange und Skype for Business nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen – dieser bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind.

Sie können mit `Get-AzureADSubscribedSku` eine Liste der verfügbaren SKUs für Ihren O365-Mandanten abrufen.

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

Als Nächstes aktivieren Sie das Gerätekonto mit [[Skype for Business Online](#skype-for-business-online), [Skype for Business in einer lokalen Umgebung](#skype-for-business-on-premises) oder [Skype for Business in einer hybriden Umgebung](#skype-for-business-hybrid).

### Skype für Unternehmen Online

Mandantenbenutzer müssen über Exchange-Postfächer verfügen (pro Mandant ist mindestens ein Exchange-Postfach erforderlich), wenn Skype für Unternehmen Online aktiviert werden soll. In der folgende Tabelle wird erläutert, welche Pläne oder zusätzlichen Dienste Sie benötigen.

| Skype Raumsystem – Szenario | Wenn Sie über Office 365 Premium, Microsoft 365-Apps für Unternehmen oder Skype for Business Standalone-Plan 2 verfügen, benötigen Sie Folgendes: | Wenn Sie über einen auf Enterprise basierten Plan verfügen, ist Folgendes erforderlich: | Wenn Sie über Skype for Business Server 2015 (lokal oder Hybrid) verfügen, benötigen Sie: |
| --- | --- | --- | --- |
| Einer geplanten Besprechung beitreten | Skype für Unternehmen (eigenständig) Plan 1 | E1, 3, 4 oder 5 | Skype für Unternehmen Server Standard CAL |
| Initiieren einer Ad-hoc-Besprechung | Skype für Unternehmen (eigenständig) Plan 2 | E 1, 3, 4 oder 5 | Skype für Unternehmen Server Standard CAL oder Enterprise CAL |
| Initiieren einer Ad-hoc-Besprechung und von einer Besprechung aus Telefonnummern auswählen | Skype for Business Standalone-Plan 2 mit Audiokonferenz</br></br>**Hinweis:** Die Abrechnung für PSTN Consumption ist optional | E1 oder E3 mit Audio-Conferencing oder E5| Skype für Unternehmen Server Standard CAL oder Enterprise CAL |
| Teilen Sie dem Raum eine Telefonnummer zu und empfangen Sie Anrufe aus dem Raum oder treten Sie mithilfe einer Telefonnummer einer Konferenz bei | Skype for Business Standalone-Plan 2 mit Telefon System und einem PSTN-Sprachanruf Plan | E1 oder E3 mit Telefon System und einem PSTN-Sprachanruf Plan oder E5 | Skype für Unternehmen Server Standard CAL oder Plus CAL |

Die folgende Tabelle enthält die Office365-Pläne und Optionen für Skype für Unternehmen.

| O365-Plan | Skype für Unternehmen | Telefon System | Audiokonferenzen | Anrufpläne |
| --- | --- | --- | --- | --- |
| O365 Business Essentials | Eingeschlossen |  |  |  |
| O365 Business Premium | Eingeschlossen |  |  |  |
| E1 | Eingeschlossen | Add-On | Add-On | Add-on (erfordert das Telefon System-Add-on) |
| E3 | Eingeschlossen | Add-On | Add-On | Add-on (erfordert das Telefon System-Add-on) |
| E5 | Eingeschlossen | Eingeschlossen | Eingeschlossen | Add-On  |

1. Zunächst erstellen Sie eine PowerShell-Remotesitzung mit der Onlineumgebung von Skype für Unternehmen von einem PC aus.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. Weisen Sie Ihrem Surface Hub-Konto eine Skype for Business-Lizenz zu.

 Nachdem Sie die vorhergehenden Schritte zum Aktivieren Ihres Surface Hub-Kontos in Skype for Business Online abgeschlossen haben, müssen Sie Surface Hub eine Lizenz zuweisen. Weisen Sie dem Gerät mithilfe des Office 365-Verwaltungsportals entweder eine Skype for Business Online (Plan 2) oder eine Skype for Business Online-Lizenz (Plan 3) zu.

- Melden Sie sich als Administrator an, öffnen Sie das O365-Verwaltungsportal, und klicken Sie auf die Verwaltungs-App.

- Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.

- Klicken Sie auf das Surface Hub-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.

- Klicken Sie auf **Lizenzen**.

- Wählen Sie unter **Lizenzen zuweisen**die Option Skype for Business (Plan 1) oder Skype for Business (Plan 2) aus, je nach Ihren Lizenzierungs-und Enterprise-VoIP-Anforderungen. Sie müssen eine Lizenz für Plan 2 verwenden, wenn Sie Enterprise-VoIP auf dem Surface Hub verwenden möchten.

- Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können auch das Microsoft Azure Active Directory-Modul für Windows PowerShell zum Ausführen der Cmdlets verwenden, die zum Zuweisen einer dieser Lizenzen erforderlich sind. Dies wird hier jedoch nicht behandelt.

Zur Überprüfung sollten Sie jeden Skype for Business-Client (PC, Android usw.) verwenden können, um sich bei diesem Konto anzumelden.

### Skype for Business in einer lokalen Umgebung

Um dieses Cmdlet auszuführen, müssen Sie eine Verbindung mit einem der Skype-Front-Ends herstellen. Öffnen Sie die Skype-PowerShell-Sitzung, und führen Sie Folgendes aus:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype for Business in einer hybriden Umgebung

Wenn Ihre Organisation [Hybridverbindungen zwischen Skype for Business Server und Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx) eingerichtet hat, sind die Schritte zum Erstellen von Konten anders als bei einer standardmäßigen Surface Hub-Bereitstellung.

Der Surface Hub erfordert ein Skype-Konto vom Typ `meetingroom`, während ein normaler Benutzer ein Konto vom Typ „user“ in Skype verwenden würde. Wenn Ihr Skype-Server für eine hybride Umgebung eingerichtet wurde, in der Benutzer auf dem lokalen Skype-Server und in Office365 gehostet werden können, treten beim Erstellen eines Surface Hub-Kontos u. U. Probleme auf.

In der Skype for Business Server 2015-Hybridumgebung müssen alle Benutzer, die Sie in Skype for Business Online verwenden möchten, zunächst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in den Active Directory-Domänendiensten erstellt wird. Sie können den Benutzer dann in Skype for Business Online verschieben. Das Verschieben eines Benutzerkontos von lokal zu Online erfolgt über das Cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Verwenden Sie das Cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) , um ein Csmeetingroom-Objekt zu verschieben.

> [!NOTE]
> Wenn Sie das Cmdlet Move-CsMeetingRoom verwenden möchten, müssen Sie [das kumulative Update vom Mai 2017 für Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) oder [das kumulative Update vom Juli 2017 5.0.8308.992 für lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)installiert haben.


## Exchange online gehostet

Nutzen Sie dieses Verfahren, wenn Sie Exchange online verwenden.

1. Erstellen Sie ein E-Mail-Konto in Office 365.

Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange her. Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. Einrichten eines Postfachs

Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann das Konto in Surface Hub authentifiziert werden.

Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Wenn Sie ein neues Ressourcenpostfach erstellen:

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. Erstellen Sie eine Exchange ActiveSync-Richtlinie.

Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.

Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist. Wenn dies nicht richtig eingestellt ist, werden die Exchange-Dienste im Surface-Hub (e-Mail, Kalender und Besprechungs Besprechungen) nicht aktiviert.

Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“. Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Nachdem Sie eine kompatible Richtlinie haben, müssen Sie die Richtlinie auf das Geräte Konto anwenden. Richtlinien können jedoch nur auf Benutzerkonten und nicht auf Ressourcenpostfächer angewendet werden. Sie benötigen das Postfach in einen Benutzertyp umwandeln, die Richtlinie anwenden und dann wieder zurück in ein Postfach umwandeln – Sie müssen es möglicherweise erneut aktivieren und auch das Kennwort noch einmal festlegen.

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. Legen Sie Exchange-Eigenschaften fest.

Für das Gerätekonto müssen verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern. Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. Fügen Sie eine e-Mail-Adresse für Ihr lokales Domänenkonto hinzu.

Bei diesem Verfahren werden AD-Verwaltungstools verwendet, um für Ihr lokales Domänenkonto eine E-Mail-Adresse hinzuzufügen.

- Klicken Sie im AD-Tool **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in der Ihre Surface Hub-Konten erstellt werden, klicken Sie auf **Neu**, und **Benutzer**.
- Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet im Feld **Vollständiger Name** und den Alias im Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.

![Feld „Neues Objekt“ zum Erstellen eines neuen Benutzers in Active Directory](images/hybriddeployment-01a.png)

- Geben Sie das Kennwort für dieses Konto ein. Es muss zur Bestätigung erneut eingegeben werden. Stellen Sie sicher, dass das Kontrollkästchen **Kennwort läuft niemals ab** die einzige aktivierte Option ist.

> [!IMPORTANT]
> Die Auswahl von " **Kennwort läuft nie ab** " ist eine Voraussetzung für Skype for Business auf dem Surface Hub. Ihre Domänenregeln können Kennwörter untersagen, die nicht ablaufen. In diesem Fall müssen Sie eine Ausnahme für jedes Surface Hub-Gerätekonto erstellen.

![Bild mit Dialogfeld „Kennwort“](images/hybriddeployment-02a.png)

- Klicken Sie auf **Fertig stellen** , um das Konto zu erstellen.

![Bild mit Kontoname, Anmeldename und Kennwortoptionen für einen neuen Benutzer](images/hybriddeployment-03a.png)

6. Führen Sie eine Verzeichnissynchronisierung aus.

Führen Sie eine Verzeichnissynchronisierung aus, nachdem Sie das Konto erstellt haben. Wenn diese abgeschlossen ist, wechseln Sie zur Seite „Benutzer“, und überprüfen Sie, ob die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

7. Stellen Sie eine Verbindung mit Azure AD her.

Sie müssen zuerst das Azure AD-Modul für die PowerShell Version 2 installieren. Führen Sie in einer Eingabeaufforderung mit erhöhten PowerShell den folgenden Befehl aus:

```PowerShell
Install-Module -Name AzureAD
```

Sie müssen eine Verbindung mit Azure AD herstellen, um einige Kontoeinstellungen anzuwenden. Sie können dieses Cmdlet ausführen, um eine Verbindung herzustellen:

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Weisen Sie eine Office 365-Lizenz zu.

Das Gerätekonto benötigt eine gültige Office 365 (O365)-Lizenz, andernfalls funktionieren Exchange und Skype for Business nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen – dieser bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind.

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

Als Nächstes aktivieren Sie das Gerätekonto mit [[Skype for Business Online](#skype-for-business-online), [Skype for Business in einer lokalen Umgebung](#skype-for-business-on-premises) oder [Skype for Business in einer hybriden Umgebung](#skype-for-business-hybrid).

### Skype für Unternehmen Online

Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende [Voraussetzungen für Skype for Business Online](#skype-for-business-online) erfüllen.

1. Zunächst erstellen Sie eine PowerShell-Remotesitzung mit der Onlineumgebung von Skype for Business von einem PC aus.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. Zuweisen einer Skype for Business-Lizenz zu Ihrem Surface Hub-Konto

Nachdem Sie die vorhergehenden Schritte zum Aktivieren Ihres Surface Hub-Kontos in Skype for Business Online abgeschlossen haben, müssen Sie Surface Hub eine Lizenz zuweisen. Weisen Sie dem Gerät mithilfe des Office 365-Verwaltungsportals entweder eine Skype for Business Online (Plan 2) oder eine Skype for Business Online-Lizenz (Plan 3) zu.

- Melden Sie sich als Mandantenadministrator an, öffnen Sie das O365-Verwaltungsportal, und klicken Sie auf die Verwaltungs-App.

- Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.

- Klicken Sie auf das Surface Hub-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.

- Klicken Sie auf **Lizenzen**.

- Wählen Sie unter **Lizenzen zuweisen**Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus, abhängig von Ihren Lizenzierungsanforderungen und Enterprise-VoIP-Anforderungen. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP auf Surface Hub verwenden möchten.

- Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können auch das Windows Azure Active Directory-Modul für Windows PowerShell zum Ausführen der Cmdlets verwenden, die zum Zuweisen einer dieser Lizenzen erforderlich sind. Dies wird hier jedoch nicht behandelt.

Zur Überprüfung sollten Sie jeden Skype for Business-Client (PC, Android usw.) verwenden können, um sich bei diesem Konto anzumelden.

### Skype for Business in einer lokalen Umgebung

Um dieses Cmdlet auszuführen, müssen Sie eine Verbindung mit einem der Skype-Front-Ends herstellen. Öffnen Sie die Skype-PowerShell-Sitzung, und führen Sie Folgendes aus:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype for Business in einer hybriden Umgebung

Wenn Ihre Organisation [Hybridverbindungen zwischen Skype for Business Server und Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx) eingerichtet hat, sind die Schritte zum Erstellen von Konten anders als bei einer standardmäßigen Surface Hub-Bereitstellung.

Der Surface Hub erfordert ein Skype-Konto vom Typ *meetingroom*, während ein normaler Benutzer ein Konto vom Typ *user* in Skype verwenden würde. Wenn Ihr Skype-Server für eine hybride Umgebung eingerichtet wurde, in der Benutzer auf dem lokalen Skype-Server und in Office365 gehostet werden können, treten beim Erstellen eines Surface Hub-Kontos u. U. Probleme auf.

In der Skype for Business Server 2015-Hybridumgebung müssen alle Benutzer, die Sie in Skype for Business Online verwenden möchten, zunächst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in den Active Directory-Domänendiensten erstellt wird. Sie können den Benutzer dann in Skype for Business Online verschieben. Das Verschieben eines Benutzerkontos von lokal zu Online erfolgt über das Cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Verwenden Sie das Cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) , um ein Csmeetingroom-Objekt zu verschieben.

> [!NOTE]
> Wenn Sie das Cmdlet Move-CsMeetingRoom verwenden möchten, müssen Sie [das kumulative Update vom Mai 2017 für Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) oder [das kumulative Update vom Juli 2017 5.0.8308.992 für lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)installiert haben.
