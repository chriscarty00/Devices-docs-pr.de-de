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
# <span data-ttu-id="f0705-104">Erstellen des Gerätekontos für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="f0705-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="f0705-105">Beim Erstellen eines Surface Hub Device-Kontos (auch als Room-Postfach bezeichnet) kann Surface Hub 2S Besprechungsanfragen empfangen, genehmigen oder ablehnen sowie an Besprechungen mit Microsoft Teams oder Skype for Business teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f0705-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="f0705-106">Konfigurieren Sie das Geräte Konto während der Installation von Out-of-Box Experience (OOBE).</span><span class="sxs-lookup"><span data-stu-id="f0705-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="f0705-107">Falls erforderlich, können Sie Sie später ändern (ohne das OOBE-Setup durchlaufen zu müssen).</span><span class="sxs-lookup"><span data-stu-id="f0705-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="f0705-108">Im Gegensatz zu Standard-Chatroom-Postfächern, die standardmäßig deaktiviert bleiben, müssen Sie das Surface Hub 2S-Geräte Konto aktivieren, um sich bei Microsoft Teams und Skype for Business anmelden zu können.</span><span class="sxs-lookup"><span data-stu-id="f0705-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="f0705-109">Surface Hub 2S basiert auf Exchange ActiveSync, das eine ActiveSync-Postfachrichtlinie für das Geräte Konto erfordert.</span><span class="sxs-lookup"><span data-stu-id="f0705-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="f0705-110">Wenden Sie die standardmäßige ActiveSync-Postfachrichtlinie an, die in Exchange Online enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f0705-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="f0705-111">Erstellen Sie das Konto mithilfe des Microsoft 365 admin Centers oder mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0705-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="f0705-112">Sie können Exchange Online PowerShell verwenden, um bestimmte Features zu konfigurieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="f0705-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="f0705-113">Kalenderverarbeitung für jedes Surface Hub-Geräte Konto</span><span class="sxs-lookup"><span data-stu-id="f0705-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="f0705-114">Benutzerdefinierte automatische Antworten auf Planungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="f0705-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="f0705-115">Wenn die standardmäßige ActiveSync-Postfachrichtlinie bereits von einer anderen Person oder einem anderen Prozess geändert wurde, müssen Sie wahrscheinlich eine neue ActiveSync-Postfachrichtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0705-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="f0705-116">Das Surface Hub-Geräte Konto unterstützt keine Drittanbieter-Verbund Identitätsanbieter (FIPS) und muss ein Active Directory-Standardkonto oder ein Azure Active Directory-Konto sein.</span><span class="sxs-lookup"><span data-stu-id="f0705-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="f0705-117">Erstellen eines Kontos mit Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="f0705-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f0705-118">Wechseln Sie im Microsoft 365 Admin Center zu **Ressourcen** , wählen Sie **Räume & Geräte** und dann **+ Raum**aus.</span><span class="sxs-lookup"><span data-stu-id="f0705-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="f0705-119">Geben Sie einen Namen und eine e-Mail-Adresse für das Geräte Konto an.</span><span class="sxs-lookup"><span data-stu-id="f0705-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="f0705-120">Lassen Sie die verbleibenden Einstellungen im Standardzustand unverändert.</span><span class="sxs-lookup"><span data-stu-id="f0705-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Angeben eines Namens und einer e-Mail-Adresse](images/sh2-account2.png)

   ![Beibehalten der verbleibenden Einstellungen im Standardzustand](images/sh2-account3.png)

3. <span data-ttu-id="f0705-123">Legen Sie das Kennwort für das Geräte Konto ein.</span><span class="sxs-lookup"><span data-stu-id="f0705-123">Set the password for the device account.</span></span> <span data-ttu-id="f0705-124">Zum Festlegen des Kennworts Wählen Sie **Benutzer** aus, und wählen Sie dann **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="f0705-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="f0705-125">Suchen Sie nun nach dem neu erstellten Benutzer, um das Kennwort einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f0705-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="f0705-126">Stellen Sie sicher, dass Sie die Option **diesen Benutzer zum Ändern des Kennworts bei der ersten Anmeldung** festlegen **nicht** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f0705-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Festlegen des Kennworts für das Geräte Konto](images/sh2-account4.png)

4. <span data-ttu-id="f0705-128">Weisen Sie dem Raum eine Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="f0705-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="f0705-129">Es wird empfohlen, die Office 365- **Besprechungsraum** Lizenz zuzuweisen, eine neue Option, die das Konto für Skype for Business Online und Microsoft Teams automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0705-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Zuweisen der Office 365-Lizenz](images/sh2-account5.png)

### <span data-ttu-id="f0705-131">Abschließen des Setups über PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0705-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="f0705-132">**Microsoft Teams und Skype for Business-Kalender:** Legen Sie die [**automatische Verarbeitung des Kalenders**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) für dieses Konto an.</span><span class="sxs-lookup"><span data-stu-id="f0705-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="f0705-133">Erstellen eines Kontos mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0705-133">Create account using PowerShell</span></span>

<span data-ttu-id="f0705-134">Anstatt das Microsoft Admin Center-Portal zu verwenden, können Sie das Konto mithilfe von PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0705-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="f0705-135">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0705-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="f0705-136">Postfach erstellen</span><span class="sxs-lookup"><span data-stu-id="f0705-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="f0705-137">Einrichten der automatischen Verarbeitung von Kalendern</span><span class="sxs-lookup"><span data-stu-id="f0705-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="f0705-138">Aktivieren von ActiveSync, wenn die Verwendung der e-Mail-App erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="f0705-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="f0705-139">Die standardmäßige ActiveSync-Richtlinie funktioniert, wenn unchnaged.</span><span class="sxs-lookup"><span data-stu-id="f0705-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="f0705-140">Erstellen Sie andernfalls eine neue Richtlinie, und weisen Sie diese zu.</span><span class="sxs-lookup"><span data-stu-id="f0705-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="f0705-141">Verbindung mit Azure AD herstellen</span><span class="sxs-lookup"><span data-stu-id="f0705-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="f0705-142">Zuweisen einer Lizenz</span><span class="sxs-lookup"><span data-stu-id="f0705-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="f0705-143">Überprüfen auf verfügbare Lizenzen</span><span class="sxs-lookup"><span data-stu-id="f0705-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```