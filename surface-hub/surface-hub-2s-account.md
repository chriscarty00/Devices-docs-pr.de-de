---
title: Erstellen des Gerätekontos für Surface Hub 2S
description: Auf dieser Seite wird das Verfahren zum Erstellen des Surface Hub 2S-Geräte Kontos beschrieben.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833802"
---
# Erstellen des Gerätekontos für Surface Hub 2S

Beim Erstellen eines Surface Hub Device-Kontos (auch als Room-Postfach bezeichnet) kann Surface Hub 2S Besprechungsanfragen empfangen, genehmigen oder ablehnen sowie an Besprechungen mit Microsoft Teams oder Skype for Business teilnehmen. Konfigurieren Sie das Geräte Konto während der Installation von Out-of-Box Experience (OOBE). Falls erforderlich, können Sie Sie später ändern (ohne das OOBE-Setup durchlaufen zu müssen).

Im Gegensatz zu Standard-Chatroom-Postfächern, die standardmäßig deaktiviert bleiben, müssen Sie das Surface Hub 2S-Geräte Konto aktivieren, um sich bei Microsoft Teams und Skype for Business anmelden zu können. Surface Hub 2S basiert auf Exchange ActiveSync, das eine ActiveSync-Postfachrichtlinie für das Geräte Konto erfordert. Wenden Sie die standardmäßige ActiveSync-Postfachrichtlinie an, die in Exchange Online enthalten ist.

Erstellen Sie das Konto mithilfe des Microsoft 365 admin Centers oder mithilfe von PowerShell. Sie können Exchange Online PowerShell verwenden, um bestimmte Features zu konfigurieren, einschließlich:

- Kalenderverarbeitung für jedes Surface Hub-Geräte Konto
- Benutzerdefinierte automatische Antworten auf Planungsanforderungen
- Wenn die standardmäßige ActiveSync-Postfachrichtlinie bereits von einer anderen Person oder einem anderen Prozess geändert wurde, müssen Sie wahrscheinlich eine neue ActiveSync-Postfachrichtlinie erstellen und zuweisen.

> [!NOTE]  
> Das Surface Hub-Geräte Konto unterstützt keine Drittanbieter-Verbund Identitätsanbieter (FIPS) und muss ein Active Directory-Standardkonto oder ein Azure Active Directory-Konto sein.

## Erstellen eines Kontos mit Microsoft 365 Admin Center

1. Wechseln Sie im Microsoft 365 Admin Center zu **Ressourcen** , wählen Sie **Räume & Geräte** und dann **+ Raum**aus.

2. Geben Sie einen Namen und eine e-Mail-Adresse für das Geräte Konto an. Lassen Sie die verbleibenden Einstellungen im Standardzustand unverändert.

   ![Angeben eines Namens und einer e-Mail-Adresse](images/sh2-account2.png)

   ![Beibehalten der verbleibenden Einstellungen im Standardzustand](images/sh2-account3.png)

3. Legen Sie das Kennwort für das Geräte Konto ein. Zum Festlegen des Kennworts Wählen Sie **Benutzer** aus, und wählen Sie dann **aktive Benutzer**aus. Suchen Sie nun nach dem neu erstellten Benutzer, um das Kennwort einzurichten. Stellen Sie sicher, dass Sie die Option **diesen Benutzer zum Ändern des Kennworts bei der ersten Anmeldung** festlegen **nicht** auswählen.

   ![Festlegen des Kennworts für das Geräte Konto](images/sh2-account4.png)

4. Weisen Sie dem Raum eine Office 365-Lizenz zu. Es wird empfohlen, die Office 365- **Besprechungsraum** Lizenz zuzuweisen, eine neue Option, die das Konto für Skype for Business Online und Microsoft Teams automatisch aktiviert.

   ![Zuweisen der Office 365-Lizenz](images/sh2-account5.png)

### Abschließen des Setups über PowerShell

- **Skype for Business:** Nur für Skype for Business (lokal oder Online) können Sie das Skype for Business-Objekt aktivieren, indem Sie **enable-CsMeetingRoom** ausführen, um Features wie Besprechungsraum Eingabeaufforderung für Audio und Lobby-Haltebereich zu aktivieren.

- **Microsoft Teams und Skype for Business-Kalender:** Legen Sie die [**automatische Verarbeitung des Kalenders**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) für dieses Konto an.

## Erstellen eines Kontos mithilfe von PowerShell

Anstatt das Microsoft Admin Center-Portal zu verwenden, können Sie das Konto mithilfe von PowerShell erstellen.

### Herstellen einer Verbindung mit Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### Erstellen eines neuen Raumpostfachs

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### Einrichten der automatischen Verarbeitung von Kalendern

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### Zuweisen einer Lizenz

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell

### Installieren von Voraussetzungen

- [Visual C++ 2017 Redistributable](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [PowerShell-Modul für Skype for Business Online](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
