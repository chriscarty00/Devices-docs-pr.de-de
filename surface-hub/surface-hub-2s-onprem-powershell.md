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
# <span data-ttu-id="58e1a-104">Konfigurieren von Surface Hub 2S-lokalen Konten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="58e1a-104">Configure Surface Hub 2S on-premises accounts with PowerShell</span></span>

## <span data-ttu-id="58e1a-105">Herstellen einer Verbindung mit Exchange Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="58e1a-105">Connect to Exchange Server PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58e1a-106">Für einige dieser Cmdlets benötigen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Client Zugriffsdienst des lokalen Exchange-Servers.</span><span class="sxs-lookup"><span data-stu-id="58e1a-106">You'll need the Fully Qualified Domain Name (FQDN) for the Client Access service of the on-premises Exchange server for some of these cmdlets.</span></span>

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## <span data-ttu-id="58e1a-107">Erstellen des Geräte Kontos</span><span class="sxs-lookup"><span data-stu-id="58e1a-107">Create the device account</span></span>

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## <span data-ttu-id="58e1a-108">Automatische Kalenderverarbeitung einrichten</span><span class="sxs-lookup"><span data-stu-id="58e1a-108">Set automatic calendar processing</span></span>

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## <span data-ttu-id="58e1a-109">Aktivieren des Skype for Business-Objekts</span><span class="sxs-lookup"><span data-stu-id="58e1a-109">Enable the Skype for Business object</span></span>

> [!NOTE]
> <span data-ttu-id="58e1a-110">Es ist wichtig, dass Sie den FQDN des Skype for Business-registrierungspools kennen.</span><span class="sxs-lookup"><span data-stu-id="58e1a-110">It is important that you know the FQDN of the Skype for Business Registrar Pool.</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## <span data-ttu-id="58e1a-111">Postfachrichtlinie für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="58e1a-111">Mobile Device Mailbox Policy</span></span>

<span data-ttu-id="58e1a-112">Möglicherweise müssen Sie eine Postfachrichtlinie für mobile Geräte (auch bekannt als ActiveSync-Richtlinie) erstellen, damit der Surface-Hub eine Verbindung mit Ihrer Online-oder lokalen Umgebung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="58e1a-112">You may need to create a Mobile Device Mailbox Policy (also known as ActiveSync Policy) to allow your Surface Hub to connect to your online or on-premises environment.</span></span>

## <span data-ttu-id="58e1a-113">Erstellen einer Postfachrichtlinie für Mobile Surface Hub-Geräte</span><span class="sxs-lookup"><span data-stu-id="58e1a-113">Create a Surface Hub mobile device mailbox policy</span></span>

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## <span data-ttu-id="58e1a-114">Zusätzliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="58e1a-114">Additional settings</span></span>

<span data-ttu-id="58e1a-115">Es wird empfohlen, eine QuickInfo zu Surface Hub rooms hinzuzufügen, damit die Benutzer daran denken, dass die Besprechung eine Skype for Business-oder Teams-Besprechung ist:</span><span class="sxs-lookup"><span data-stu-id="58e1a-115">It is recommended to add a MailTip to Surface Hub rooms so users remember to make the meeting a Skype for Business or Teams meeting:</span></span>

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
