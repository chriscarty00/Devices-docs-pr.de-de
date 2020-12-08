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
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196728"
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

- **Microsoft Teams und Skype for Business-Kalender:** Legen Sie die [**automatische Verarbeitung des Kalenders**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) für dieses Konto an.

## Erstellen eines Kontos mithilfe von PowerShell

Anstatt das Microsoft Admin Center-Portal zu verwenden, können Sie das Konto mithilfe von PowerShell erstellen.

### Herstellen einer Verbindung mit Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### Postfach erstellen

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### Einrichten der automatischen Verarbeitung von Kalendern

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### Aktivieren von ActiveSync, wenn die Verwendung der e-Mail-App erforderlich ist

 Die standardmäßige ActiveSync-Richtlinie funktioniert, wenn unchnaged. Erstellen Sie andernfalls eine neue Richtlinie, und weisen Sie diese zu.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### Verbindung mit Azure AD herstellen

```powershell
Connect-AzureAD
```

### Zuweisen einer Lizenz

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### Überprüfen auf verfügbare Lizenzen

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```