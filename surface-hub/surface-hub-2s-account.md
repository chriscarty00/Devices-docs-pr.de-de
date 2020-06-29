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
# <span data-ttu-id="aa173-104">Erstellen des Gerätekontos für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="aa173-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="aa173-105">Beim Erstellen eines Surface Hub Device-Kontos (auch als Room-Postfach bezeichnet) kann Surface Hub 2S Besprechungsanfragen empfangen, genehmigen oder ablehnen sowie an Besprechungen mit Microsoft Teams oder Skype for Business teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="aa173-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="aa173-106">Konfigurieren Sie das Geräte Konto während der Installation von Out-of-Box Experience (OOBE).</span><span class="sxs-lookup"><span data-stu-id="aa173-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="aa173-107">Falls erforderlich, können Sie Sie später ändern (ohne das OOBE-Setup durchlaufen zu müssen).</span><span class="sxs-lookup"><span data-stu-id="aa173-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="aa173-108">Im Gegensatz zu Standard-Chatroom-Postfächern, die standardmäßig deaktiviert bleiben, müssen Sie das Surface Hub 2S-Geräte Konto aktivieren, um sich bei Microsoft Teams und Skype for Business anmelden zu können.</span><span class="sxs-lookup"><span data-stu-id="aa173-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="aa173-109">Surface Hub 2S basiert auf Exchange ActiveSync, das eine ActiveSync-Postfachrichtlinie für das Geräte Konto erfordert.</span><span class="sxs-lookup"><span data-stu-id="aa173-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="aa173-110">Wenden Sie die standardmäßige ActiveSync-Postfachrichtlinie an, die in Exchange Online enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="aa173-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="aa173-111">Erstellen Sie das Konto mithilfe des Microsoft 365 admin Centers oder mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa173-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="aa173-112">Sie können Exchange Online PowerShell verwenden, um bestimmte Features zu konfigurieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="aa173-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="aa173-113">Kalenderverarbeitung für jedes Surface Hub-Geräte Konto</span><span class="sxs-lookup"><span data-stu-id="aa173-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="aa173-114">Benutzerdefinierte automatische Antworten auf Planungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="aa173-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="aa173-115">Wenn die standardmäßige ActiveSync-Postfachrichtlinie bereits von einer anderen Person oder einem anderen Prozess geändert wurde, müssen Sie wahrscheinlich eine neue ActiveSync-Postfachrichtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="aa173-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="aa173-116">Das Surface Hub-Geräte Konto unterstützt keine Drittanbieter-Verbund Identitätsanbieter (FIPS) und muss ein Active Directory-Standardkonto oder ein Azure Active Directory-Konto sein.</span><span class="sxs-lookup"><span data-stu-id="aa173-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="aa173-117">Erstellen eines Kontos mit Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="aa173-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="aa173-118">Wechseln Sie im Microsoft 365 Admin Center zu **Ressourcen** , wählen Sie **Räume & Geräte** und dann **+ Raum**aus.</span><span class="sxs-lookup"><span data-stu-id="aa173-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="aa173-119">Geben Sie einen Namen und eine e-Mail-Adresse für das Geräte Konto an.</span><span class="sxs-lookup"><span data-stu-id="aa173-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="aa173-120">Lassen Sie die verbleibenden Einstellungen im Standardzustand unverändert.</span><span class="sxs-lookup"><span data-stu-id="aa173-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Angeben eines Namens und einer e-Mail-Adresse](images/sh2-account2.png)

   ![Beibehalten der verbleibenden Einstellungen im Standardzustand](images/sh2-account3.png)

3. <span data-ttu-id="aa173-123">Legen Sie das Kennwort für das Geräte Konto ein.</span><span class="sxs-lookup"><span data-stu-id="aa173-123">Set the password for the device account.</span></span> <span data-ttu-id="aa173-124">Zum Festlegen des Kennworts Wählen Sie **Benutzer** aus, und wählen Sie dann **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="aa173-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="aa173-125">Suchen Sie nun nach dem neu erstellten Benutzer, um das Kennwort einzurichten.</span><span class="sxs-lookup"><span data-stu-id="aa173-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="aa173-126">Stellen Sie sicher, dass Sie die Option **diesen Benutzer zum Ändern des Kennworts bei der ersten Anmeldung** festlegen **nicht** auswählen.</span><span class="sxs-lookup"><span data-stu-id="aa173-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Festlegen des Kennworts für das Geräte Konto](images/sh2-account4.png)

4. <span data-ttu-id="aa173-128">Weisen Sie dem Raum eine Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="aa173-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="aa173-129">Es wird empfohlen, die Office 365- **Besprechungsraum** Lizenz zuzuweisen, eine neue Option, die das Konto für Skype for Business Online und Microsoft Teams automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa173-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Zuweisen der Office 365-Lizenz](images/sh2-account5.png)

### <span data-ttu-id="aa173-131">Abschließen des Setups über PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa173-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="aa173-132">**Skype for Business:** Nur für Skype for Business (lokal oder Online) können Sie das Skype for Business-Objekt aktivieren, indem Sie **enable-CsMeetingRoom** ausführen, um Features wie Besprechungsraum Eingabeaufforderung für Audio und Lobby-Haltebereich zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="aa173-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="aa173-133">**Microsoft Teams und Skype for Business-Kalender:** Legen Sie die [**automatische Verarbeitung des Kalenders**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) für dieses Konto an.</span><span class="sxs-lookup"><span data-stu-id="aa173-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="aa173-134">Erstellen eines Kontos mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa173-134">Create account using PowerShell</span></span>

<span data-ttu-id="aa173-135">Anstatt das Microsoft Admin Center-Portal zu verwenden, können Sie das Konto mithilfe von PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa173-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="aa173-136">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa173-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="aa173-137">Erstellen eines neuen Raumpostfachs</span><span class="sxs-lookup"><span data-stu-id="aa173-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="aa173-138">Einrichten der automatischen Verarbeitung von Kalendern</span><span class="sxs-lookup"><span data-stu-id="aa173-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="aa173-139">Zuweisen einer Lizenz</span><span class="sxs-lookup"><span data-stu-id="aa173-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="aa173-140">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa173-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="aa173-141">Installieren von Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="aa173-141">Install pre-requisites</span></span>

- [<span data-ttu-id="aa173-142">Visual C++ 2017 Redistributable</span><span class="sxs-lookup"><span data-stu-id="aa173-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="aa173-143">PowerShell-Modul für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aa173-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
