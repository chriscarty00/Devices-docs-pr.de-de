---
title: Konfigurieren von Surface Hub 2S-lokalen Konten mit PowerShell
description: Informationen zum Konfigurieren von Surface Hub 2S-lokalen Konten mit PowerShell
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834000"
---
# Konfigurieren von Surface Hub 2S-lokalen Konten mit PowerShell

## Herstellen einer Verbindung mit Exchange Server PowerShell

> [!IMPORTANT]
> Für einige dieser Cmdlets benötigen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Client Zugriffsdienst des lokalen Exchange-Servers.

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## Erstellen des Geräte Kontos

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## Automatische Kalenderverarbeitung einrichten

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## Aktivieren des Skype for Business-Objekts

> [!NOTE]
> Es ist wichtig, dass Sie den FQDN des Skype for Business-registrierungspools kennen.

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## Postfachrichtlinie für mobile Geräte

Möglicherweise müssen Sie eine Postfachrichtlinie für mobile Geräte (auch bekannt als ActiveSync-Richtlinie) erstellen, damit der Surface-Hub eine Verbindung mit Ihrer Online-oder lokalen Umgebung herstellen kann.

## Erstellen einer Postfachrichtlinie für Mobile Surface Hub-Geräte

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## Zusätzliche Einstellungen

Es wird empfohlen, eine QuickInfo zu Surface Hub rooms hinzuzufügen, damit die Benutzer daran denken, dass die Besprechung eine Skype for Business-oder Teams-Besprechung ist:

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
