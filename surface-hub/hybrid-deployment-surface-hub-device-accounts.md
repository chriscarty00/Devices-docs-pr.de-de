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
# <span data-ttu-id="71aa5-104">Hybridbereitstellung (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="71aa5-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="71aa5-105">Eine Hybridbereitstellung erfordert eine spezielle Verarbeitung, um ein Gerätekonto für Ihren Microsoft Surface Hub einzurichten.</span><span class="sxs-lookup"><span data-stu-id="71aa5-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="71aa5-106">Bei Verwendung einer Hybridbereitstellung, in der Ihre Organisation über verschiedene Dienste verfügt, von denen einige lokal und einige online gehostet werden, hängt die Konfiguration davon ab, wo jeder Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="71aa5-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="71aa5-107">In diesem Thema werden Hybridbereitstellungen für [Exchange lokal gehostet](#exchange-on-premises), [Exchange online gehostet](#exchange-online), Skype for Business in einer lokalen Umgebung, [Skype for Business Online und Skype for Business in einer hybriden Umgebung behandelt.</span><span class="sxs-lookup"><span data-stu-id="71aa5-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="71aa5-108">Da es so viele unterschiedliche Varianten bei dieser Art von Bereitstellung gibt, ist es nicht möglich, ausführliche Anweisungen für alle davon bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="71aa5-109">Der folgende Prozess funktioniert für viele Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-109">The following process will work for many configurations.</span></span> <span data-ttu-id="71aa5-110">Wenn der Prozess für Ihre Konfiguration nicht geeignet ist, wird empfohlen, PowerShell zu verwenden (siehe [Anhang: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)), um dasselbe Endergebnis wie hier dokumentiert zu erzielen. Diese Vorgehensweise kann auch für andere Bereitstellungsoptionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="71aa5-111">Sie sollten dann das bereitgestellte PowerShell-Skript verwenden, um Ihr Surface Hub-Setup zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="71aa5-112">(Informationen finden Sie unter [Kontovalidierungsskript](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span><span class="sxs-lookup"><span data-stu-id="71aa5-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="71aa5-113">Führen Sie in einer Exchange-Hybridumgebung die Schritte für [Exchange lokal](#exchange-on-premises)aus.</span><span class="sxs-lookup"><span data-stu-id="71aa5-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="71aa5-114">Verwenden Sie das Cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) , um Exchange-Objekte nach Office 365 zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="71aa5-115">Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="71aa5-115">Exchange on-premises</span></span>

<span data-ttu-id="71aa5-116">Nutzen Sie dieses Verfahren, wenn Sie Exchange lokal verwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="71aa5-117">Bei diesem Verfahren werden AD-Verwaltungstools verwendet, um für Ihr lokales Domänenkonto eine E-Mail-Adresse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="71aa5-118">Dieses Konto wird mit Office 365 synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="71aa5-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="71aa5-119">Klicken Sie im AD-Tool **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in der Ihre Surface Hub-Konten erstellt werden, klicken Sie auf **Neu**, und **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="71aa5-120">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet im Feld **Vollständiger Name** und den Alias im Feld **Benutzeranmeldename** ein.</span><span class="sxs-lookup"><span data-stu-id="71aa5-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="71aa5-121">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-121">Click **Next**.</span></span><p>

![Feld „Neues Objekt“ zum Erstellen eines neuen Benutzers in Active Directory](images/hybriddeployment-01a.png)

- <span data-ttu-id="71aa5-123">Geben Sie das Kennwort für dieses Konto ein.</span><span class="sxs-lookup"><span data-stu-id="71aa5-123">Type the password for this account.</span></span> <span data-ttu-id="71aa5-124">Es muss zur Bestätigung erneut eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="71aa5-125">Stellen Sie sicher, dass das Kontrollkästchen **Kennwort läuft niemals ab** die einzige aktivierte Option ist.</span><span class="sxs-lookup"><span data-stu-id="71aa5-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="71aa5-126">**Wichtig:** Die Auswahl von **Kennwort läuft niemals ab** ist eine Voraussetzung für Skype for Business auf Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="71aa5-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="71aa5-127">Ihre Domänenregeln können Kennwörter untersagen, die nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="71aa5-128">In diesem Fall müssen Sie eine Ausnahme für jedes Surface Hub-Gerätekonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Bild mit Dialogfeld „Kennwort“](images/hybriddeployment-02a.png)

-   <span data-ttu-id="71aa5-130">Klicken Sie auf **Fertig stellen** , um das Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-130">Click **Finish** to create the account.</span></span>

![Bild mit Kontoname, Anmeldename und Kennwortoptionen für einen neuen Benutzer](images/hybriddeployment-03a.png)

2. <span data-ttu-id="71aa5-132">Aktivieren Sie das Remote-Postfach.</span><span class="sxs-lookup"><span data-stu-id="71aa5-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="71aa5-133">Öffnen Sie die lokale Exchange-Verwaltungsshell mit Administratorberechtigungen, und führen Sie dieses Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="71aa5-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="71aa5-134">Besitzen Sie keine lokale Exchange-Umgebung, um dieses Cmdlet auszuführen, können Sie die gleichen direkt auf das Active Directory-Objekt für das Konto ändern.</span><span class="sxs-lookup"><span data-stu-id="71aa5-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="71aa5-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="71aa5-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="71aa5-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="71aa5-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="71aa5-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="71aa5-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="71aa5-138">Führen Sie eine Verzeichnissynchronisierung aus, nachdem Sie das Konto erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="71aa5-139">Wenn Sie fertig sind, wechseln Sie zur Seite "Benutzer" im Microsoft 365 Admin Center, und überprüfen Sie, ob das in den vorherigen Schritten erstellte Konto mit Online verbunden wurde.</span><span class="sxs-lookup"><span data-stu-id="71aa5-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="71aa5-140">Stellen Sie eine Verbindung mit Microsoft Exchange Online her, und legen Sie einige Eigenschaften für das Konto in Office 365 fest.</span><span class="sxs-lookup"><span data-stu-id="71aa5-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="71aa5-141">Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Microsoft Exchange her.</span><span class="sxs-lookup"><span data-stu-id="71aa5-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="71aa5-142">Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="71aa5-143">Die nächsten Schritten werden auf dem Office 365-Mandanten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="71aa5-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="71aa5-144">Erstellen Sie eine neue Exchange ActiveSync-Richtlinie, oder verwenden Sie eine kompatible vorhandene Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="71aa5-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="71aa5-145">Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="71aa5-146">Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled**-Eigenschaft auf „False“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="71aa5-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="71aa5-147">Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="71aa5-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="71aa5-148">Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“.</span><span class="sxs-lookup"><span data-stu-id="71aa5-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="71aa5-149">Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="71aa5-150">Nachdem Sie eine kompatible Richtlinie haben, müssen Sie die Richtlinie auf das Geräte Konto anwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="71aa5-151">Legen Sie Exchange-Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="71aa5-151">Set Exchange properties.</span></span>

<span data-ttu-id="71aa5-152">Exchange-Eigenschaften werden für das Gerätekonto festgelegt, um das Besprechungsergebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="71aa5-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="71aa5-153">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="71aa5-154">Stellen Sie eine Verbindung mit Azure AD her.</span><span class="sxs-lookup"><span data-stu-id="71aa5-154">Connect to Azure AD.</span></span>

<span data-ttu-id="71aa5-155">Sie müssen zuerst das Azure AD-Modul für die PowerShell Version 2 installieren.</span><span class="sxs-lookup"><span data-stu-id="71aa5-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="71aa5-156">Führen Sie in einer Eingabeaufforderung mit erhöhten PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="71aa5-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="71aa5-157">Sie müssen eine Verbindung mit Azure AD herstellen, um einige Kontoeinstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="71aa5-158">Sie können zum Herstellen der Verbindung dieses Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="71aa5-159">Weisen Sie eine Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="71aa5-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="71aa5-160">Das Gerätekonto benötigt eine gültige Office 365 (O365)-Lizenz, andernfalls funktionieren Exchange und Skype for Business nicht.</span><span class="sxs-lookup"><span data-stu-id="71aa5-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="71aa5-161">Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen – dieser bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="71aa5-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="71aa5-162">Sie können mit `Get-AzureADSubscribedSku` eine Liste der verfügbaren SKUs für Ihren O365-Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="71aa5-163">Nachdem Sie die SKUs aufgelistet haben, müssen Sie die die für die `$License.SkuId`-Variable gewünschte SKU-ID zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="71aa5-164">Als Nächstes aktivieren Sie das Gerätekonto mit [[Skype for Business Online](#skype-for-business-online), [Skype for Business in einer lokalen Umgebung](#skype-for-business-on-premises) oder [Skype for Business in einer hybriden Umgebung](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="71aa5-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="71aa5-165">Skype für Unternehmen Online</span><span class="sxs-lookup"><span data-stu-id="71aa5-165">Skype for Business Online</span></span>

<span data-ttu-id="71aa5-166">Mandantenbenutzer müssen über Exchange-Postfächer verfügen (pro Mandant ist mindestens ein Exchange-Postfach erforderlich), wenn Skype für Unternehmen Online aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="71aa5-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="71aa5-167">In der folgende Tabelle wird erläutert, welche Pläne oder zusätzlichen Dienste Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="71aa5-168">Skype Raumsystem – Szenario</span><span class="sxs-lookup"><span data-stu-id="71aa5-168">Skype room system scenario</span></span> | <span data-ttu-id="71aa5-169">Wenn Sie über Office 365 Premium, Microsoft 365-Apps für Unternehmen oder Skype for Business Standalone-Plan 2 verfügen, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="71aa5-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="71aa5-170">Wenn Sie über einen auf Enterprise basierten Plan verfügen, ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="71aa5-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="71aa5-171">Wenn Sie über Skype for Business Server 2015 (lokal oder Hybrid) verfügen, benötigen Sie:</span><span class="sxs-lookup"><span data-stu-id="71aa5-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="71aa5-172">Einer geplanten Besprechung beitreten</span><span class="sxs-lookup"><span data-stu-id="71aa5-172">Join a scheduled meeting</span></span> | <span data-ttu-id="71aa5-173">Skype für Unternehmen (eigenständig) Plan 1</span><span class="sxs-lookup"><span data-stu-id="71aa5-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="71aa5-174">E1, 3, 4 oder 5</span><span class="sxs-lookup"><span data-stu-id="71aa5-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="71aa5-175">Skype für Unternehmen Server Standard CAL</span><span class="sxs-lookup"><span data-stu-id="71aa5-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="71aa5-176">Initiieren einer Ad-hoc-Besprechung</span><span class="sxs-lookup"><span data-stu-id="71aa5-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="71aa5-177">Skype für Unternehmen (eigenständig) Plan 2</span><span class="sxs-lookup"><span data-stu-id="71aa5-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="71aa5-178">E 1, 3, 4 oder 5</span><span class="sxs-lookup"><span data-stu-id="71aa5-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="71aa5-179">Skype für Unternehmen Server Standard CAL oder Enterprise CAL</span><span class="sxs-lookup"><span data-stu-id="71aa5-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="71aa5-180">Initiieren einer Ad-hoc-Besprechung und von einer Besprechung aus Telefonnummern auswählen</span><span class="sxs-lookup"><span data-stu-id="71aa5-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="71aa5-181">Skype for Business Standalone-Plan 2 mit Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="71aa5-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="71aa5-182">**Hinweis:** Die Abrechnung für PSTN Consumption ist optional</span><span class="sxs-lookup"><span data-stu-id="71aa5-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="71aa5-183">E1 oder E3 mit Audio-Conferencing oder E5</span><span class="sxs-lookup"><span data-stu-id="71aa5-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="71aa5-184">Skype für Unternehmen Server Standard CAL oder Enterprise CAL</span><span class="sxs-lookup"><span data-stu-id="71aa5-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="71aa5-185">Teilen Sie dem Raum eine Telefonnummer zu und empfangen Sie Anrufe aus dem Raum oder treten Sie mithilfe einer Telefonnummer einer Konferenz bei</span><span class="sxs-lookup"><span data-stu-id="71aa5-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="71aa5-186">Skype for Business Standalone-Plan 2 mit Telefon System und einem PSTN-Sprachanruf Plan</span><span class="sxs-lookup"><span data-stu-id="71aa5-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="71aa5-187">E1 oder E3 mit Telefon System und einem PSTN-Sprachanruf Plan oder E5</span><span class="sxs-lookup"><span data-stu-id="71aa5-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="71aa5-188">Skype für Unternehmen Server Standard CAL oder Plus CAL</span><span class="sxs-lookup"><span data-stu-id="71aa5-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="71aa5-189">Die folgende Tabelle enthält die Office365-Pläne und Optionen für Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="71aa5-190">O365-Plan</span><span class="sxs-lookup"><span data-stu-id="71aa5-190">O365 Plan</span></span> | <span data-ttu-id="71aa5-191">Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="71aa5-191">Skype for Business</span></span> | <span data-ttu-id="71aa5-192">Telefon System</span><span class="sxs-lookup"><span data-stu-id="71aa5-192">Phone System</span></span> | <span data-ttu-id="71aa5-193">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="71aa5-193">Audio Conferencing</span></span> | <span data-ttu-id="71aa5-194">Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="71aa5-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="71aa5-195">O365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="71aa5-195">O365 Business Essentials</span></span> | <span data-ttu-id="71aa5-196">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-196">Included</span></span> |  |  |  |
| <span data-ttu-id="71aa5-197">O365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="71aa5-197">O365 Business Premium</span></span> | <span data-ttu-id="71aa5-198">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-198">Included</span></span> |  |  |  |
| <span data-ttu-id="71aa5-199">E1</span><span class="sxs-lookup"><span data-stu-id="71aa5-199">E1</span></span> | <span data-ttu-id="71aa5-200">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-200">Included</span></span> | <span data-ttu-id="71aa5-201">Add-On</span><span class="sxs-lookup"><span data-stu-id="71aa5-201">Add-on</span></span> | <span data-ttu-id="71aa5-202">Add-On</span><span class="sxs-lookup"><span data-stu-id="71aa5-202">Add-on</span></span> | <span data-ttu-id="71aa5-203">Add-on (erfordert das Telefon System-Add-on)</span><span class="sxs-lookup"><span data-stu-id="71aa5-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="71aa5-204">E3</span><span class="sxs-lookup"><span data-stu-id="71aa5-204">E3</span></span> | <span data-ttu-id="71aa5-205">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-205">Included</span></span> | <span data-ttu-id="71aa5-206">Add-On</span><span class="sxs-lookup"><span data-stu-id="71aa5-206">Add-on</span></span> | <span data-ttu-id="71aa5-207">Add-On</span><span class="sxs-lookup"><span data-stu-id="71aa5-207">Add-on</span></span> | <span data-ttu-id="71aa5-208">Add-on (erfordert das Telefon System-Add-on)</span><span class="sxs-lookup"><span data-stu-id="71aa5-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="71aa5-209">E5</span><span class="sxs-lookup"><span data-stu-id="71aa5-209">E5</span></span> | <span data-ttu-id="71aa5-210">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-210">Included</span></span> | <span data-ttu-id="71aa5-211">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-211">Included</span></span> | <span data-ttu-id="71aa5-212">Eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="71aa5-212">Included</span></span> | <span data-ttu-id="71aa5-213">Add-On</span><span class="sxs-lookup"><span data-stu-id="71aa5-213">Add-on</span></span>  |

1. <span data-ttu-id="71aa5-214">Zunächst erstellen Sie eine PowerShell-Remotesitzung mit der Onlineumgebung von Skype für Unternehmen von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="71aa5-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="71aa5-215">Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="71aa5-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="71aa5-216">Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:</span><span class="sxs-lookup"><span data-stu-id="71aa5-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="71aa5-217">Weisen Sie Ihrem Surface Hub-Konto eine Skype for Business-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="71aa5-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="71aa5-218">Nachdem Sie die vorhergehenden Schritte zum Aktivieren Ihres Surface Hub-Kontos in Skype for Business Online abgeschlossen haben, müssen Sie Surface Hub eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="71aa5-219">Weisen Sie dem Gerät mithilfe des Office 365-Verwaltungsportals entweder eine Skype for Business Online (Plan 2) oder eine Skype for Business Online-Lizenz (Plan 3) zu.</span><span class="sxs-lookup"><span data-stu-id="71aa5-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="71aa5-220">Melden Sie sich als Administrator an, öffnen Sie das O365-Verwaltungsportal, und klicken Sie auf die Verwaltungs-App.</span><span class="sxs-lookup"><span data-stu-id="71aa5-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="71aa5-221">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="71aa5-222">Klicken Sie auf das Surface Hub-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="71aa5-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="71aa5-223">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-223">Click **Licenses**.</span></span>

- <span data-ttu-id="71aa5-224">Wählen Sie unter **Lizenzen zuweisen**die Option Skype for Business (Plan 1) oder Skype for Business (Plan 2) aus, je nach Ihren Lizenzierungs-und Enterprise-VoIP-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="71aa5-225">Sie müssen eine Lizenz für Plan 2 verwenden, wenn Sie Enterprise-VoIP auf dem Surface Hub verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="71aa5-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="71aa5-226">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="71aa5-227">Sie können auch das Microsoft Azure Active Directory-Modul für Windows PowerShell zum Ausführen der Cmdlets verwenden, die zum Zuweisen einer dieser Lizenzen erforderlich sind. Dies wird hier jedoch nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="71aa5-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="71aa5-228">Zur Überprüfung sollten Sie jeden Skype for Business-Client (PC, Android usw.) verwenden können, um sich bei diesem Konto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="71aa5-229">Skype for Business in einer lokalen Umgebung</span><span class="sxs-lookup"><span data-stu-id="71aa5-229">Skype for Business on-premises</span></span>

<span data-ttu-id="71aa5-230">Um dieses Cmdlet auszuführen, müssen Sie eine Verbindung mit einem der Skype-Front-Ends herstellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="71aa5-231">Öffnen Sie die Skype-PowerShell-Sitzung, und führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="71aa5-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="71aa5-232">Skype for Business in einer hybriden Umgebung</span><span class="sxs-lookup"><span data-stu-id="71aa5-232">Skype for Business hybrid</span></span>

<span data-ttu-id="71aa5-233">Wenn Ihre Organisation [Hybridverbindungen zwischen Skype for Business Server und Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx) eingerichtet hat, sind die Schritte zum Erstellen von Konten anders als bei einer standardmäßigen Surface Hub-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="71aa5-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="71aa5-234">Der Surface Hub erfordert ein Skype-Konto vom Typ `meetingroom`, während ein normaler Benutzer ein Konto vom Typ „user“ in Skype verwenden würde.</span><span class="sxs-lookup"><span data-stu-id="71aa5-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="71aa5-235">Wenn Ihr Skype-Server für eine hybride Umgebung eingerichtet wurde, in der Benutzer auf dem lokalen Skype-Server und in Office365 gehostet werden können, treten beim Erstellen eines Surface Hub-Kontos u. U. Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="71aa5-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="71aa5-236">In der Skype for Business Server 2015-Hybridumgebung müssen alle Benutzer, die Sie in Skype for Business Online verwenden möchten, zunächst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in den Active Directory-Domänendiensten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="71aa5-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="71aa5-237">Sie können den Benutzer dann in Skype for Business Online verschieben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="71aa5-238">Das Verschieben eines Benutzerkontos von lokal zu Online erfolgt über das Cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="71aa5-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="71aa5-239">Verwenden Sie das Cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) , um ein Csmeetingroom-Objekt zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="71aa5-240">Wenn Sie das Cmdlet Move-CsMeetingRoom verwenden möchten, müssen Sie [das kumulative Update vom Mai 2017 für Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) oder [das kumulative Update vom Juli 2017 5.0.8308.992 für lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)installiert haben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="71aa5-241">Exchange online gehostet</span><span class="sxs-lookup"><span data-stu-id="71aa5-241">Exchange online</span></span>

<span data-ttu-id="71aa5-242">Nutzen Sie dieses Verfahren, wenn Sie Exchange online verwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="71aa5-243">Erstellen Sie ein E-Mail-Konto in Office 365.</span><span class="sxs-lookup"><span data-stu-id="71aa5-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="71aa5-244">Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange her.</span><span class="sxs-lookup"><span data-stu-id="71aa5-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="71aa5-245">Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="71aa5-246">Einrichten eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="71aa5-246">Set up a mailbox.</span></span>

<span data-ttu-id="71aa5-247">Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="71aa5-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="71aa5-248">Dadurch kann das Konto in Surface Hub authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="71aa5-249">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="71aa5-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="71aa5-250">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="71aa5-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="71aa5-251">Erstellen Sie eine Exchange ActiveSync-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="71aa5-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="71aa5-252">Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="71aa5-253">Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="71aa5-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="71aa5-254">Wenn dies nicht richtig eingestellt ist, werden die Exchange-Dienste im Surface-Hub (e-Mail, Kalender und Besprechungs Besprechungen) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="71aa5-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="71aa5-255">Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“.</span><span class="sxs-lookup"><span data-stu-id="71aa5-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="71aa5-256">Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="71aa5-257">Nachdem Sie eine kompatible Richtlinie haben, müssen Sie die Richtlinie auf das Geräte Konto anwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="71aa5-258">Richtlinien können jedoch nur auf Benutzerkonten und nicht auf Ressourcenpostfächer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="71aa5-259">Sie benötigen das Postfach in einen Benutzertyp umwandeln, die Richtlinie anwenden und dann wieder zurück in ein Postfach umwandeln – Sie müssen es möglicherweise erneut aktivieren und auch das Kennwort noch einmal festlegen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="71aa5-260">Legen Sie Exchange-Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="71aa5-260">Set Exchange properties.</span></span>

<span data-ttu-id="71aa5-261">Für das Gerätekonto müssen verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="71aa5-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="71aa5-262">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="71aa5-263">Fügen Sie eine e-Mail-Adresse für Ihr lokales Domänenkonto hinzu.</span><span class="sxs-lookup"><span data-stu-id="71aa5-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="71aa5-264">Bei diesem Verfahren werden AD-Verwaltungstools verwendet, um für Ihr lokales Domänenkonto eine E-Mail-Adresse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="71aa5-265">Klicken Sie im AD-Tool **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in der Ihre Surface Hub-Konten erstellt werden, klicken Sie auf **Neu**, und **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="71aa5-266">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet im Feld **Vollständiger Name** und den Alias im Feld **Benutzeranmeldename** ein.</span><span class="sxs-lookup"><span data-stu-id="71aa5-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="71aa5-267">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-267">Click **Next**.</span></span>

![Feld „Neues Objekt“ zum Erstellen eines neuen Benutzers in Active Directory](images/hybriddeployment-01a.png)

- <span data-ttu-id="71aa5-269">Geben Sie das Kennwort für dieses Konto ein.</span><span class="sxs-lookup"><span data-stu-id="71aa5-269">Type the password for this account.</span></span> <span data-ttu-id="71aa5-270">Es muss zur Bestätigung erneut eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="71aa5-271">Stellen Sie sicher, dass das Kontrollkästchen **Kennwort läuft niemals ab** die einzige aktivierte Option ist.</span><span class="sxs-lookup"><span data-stu-id="71aa5-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71aa5-272">Die Auswahl von " **Kennwort läuft nie ab** " ist eine Voraussetzung für Skype for Business auf dem Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="71aa5-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="71aa5-273">Ihre Domänenregeln können Kennwörter untersagen, die nicht ablaufen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="71aa5-274">In diesem Fall müssen Sie eine Ausnahme für jedes Surface Hub-Gerätekonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Bild mit Dialogfeld „Kennwort“](images/hybriddeployment-02a.png)

- <span data-ttu-id="71aa5-276">Klicken Sie auf **Fertig stellen** , um das Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-276">Click **Finish** to create the account.</span></span>

![Bild mit Kontoname, Anmeldename und Kennwortoptionen für einen neuen Benutzer](images/hybriddeployment-03a.png)

6. <span data-ttu-id="71aa5-278">Führen Sie eine Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="71aa5-278">Run directory synchronization.</span></span>

<span data-ttu-id="71aa5-279">Führen Sie eine Verzeichnissynchronisierung aus, nachdem Sie das Konto erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="71aa5-280">Wenn diese abgeschlossen ist, wechseln Sie zur Seite „Benutzer“, und überprüfen Sie, ob die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="71aa5-281">Stellen Sie eine Verbindung mit Azure AD her.</span><span class="sxs-lookup"><span data-stu-id="71aa5-281">Connect to Azure AD.</span></span>

<span data-ttu-id="71aa5-282">Sie müssen zuerst das Azure AD-Modul für die PowerShell Version 2 installieren.</span><span class="sxs-lookup"><span data-stu-id="71aa5-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="71aa5-283">Führen Sie in einer Eingabeaufforderung mit erhöhten PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="71aa5-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="71aa5-284">Sie müssen eine Verbindung mit Azure AD herstellen, um einige Kontoeinstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="71aa5-285">Sie können dieses Cmdlet ausführen, um eine Verbindung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="71aa5-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="71aa5-286">Weisen Sie eine Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="71aa5-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="71aa5-287">Das Gerätekonto benötigt eine gültige Office 365 (O365)-Lizenz, andernfalls funktionieren Exchange und Skype for Business nicht.</span><span class="sxs-lookup"><span data-stu-id="71aa5-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="71aa5-288">Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen – dieser bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="71aa5-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="71aa5-289">Als Nächstes können Sie mit `Get-AzureADSubscribedSku` eine Liste der verfügbaren SKUs für Ihren O365-Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="71aa5-290">Nachdem Sie die SKUs aufgelistet haben, müssen Sie die die für die `$License.SkuId`-Variable gewünschte SKU-ID zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="71aa5-291">Als Nächstes aktivieren Sie das Gerätekonto mit [[Skype for Business Online](#skype-for-business-online), [Skype for Business in einer lokalen Umgebung](#skype-for-business-on-premises) oder [Skype for Business in einer hybriden Umgebung](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="71aa5-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="71aa5-292">Skype für Unternehmen Online</span><span class="sxs-lookup"><span data-stu-id="71aa5-292">Skype for Business Online</span></span>

<span data-ttu-id="71aa5-293">Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende [Voraussetzungen für Skype for Business Online](#skype-for-business-online) erfüllen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="71aa5-294">Zunächst erstellen Sie eine PowerShell-Remotesitzung mit der Onlineumgebung von Skype for Business von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="71aa5-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="71aa5-295">Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="71aa5-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="71aa5-296">Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:</span><span class="sxs-lookup"><span data-stu-id="71aa5-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="71aa5-297">Zuweisen einer Skype for Business-Lizenz zu Ihrem Surface Hub-Konto</span><span class="sxs-lookup"><span data-stu-id="71aa5-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="71aa5-298">Nachdem Sie die vorhergehenden Schritte zum Aktivieren Ihres Surface Hub-Kontos in Skype for Business Online abgeschlossen haben, müssen Sie Surface Hub eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="71aa5-299">Weisen Sie dem Gerät mithilfe des Office 365-Verwaltungsportals entweder eine Skype for Business Online (Plan 2) oder eine Skype for Business Online-Lizenz (Plan 3) zu.</span><span class="sxs-lookup"><span data-stu-id="71aa5-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="71aa5-300">Melden Sie sich als Mandantenadministrator an, öffnen Sie das O365-Verwaltungsportal, und klicken Sie auf die Verwaltungs-App.</span><span class="sxs-lookup"><span data-stu-id="71aa5-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="71aa5-301">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="71aa5-302">Klicken Sie auf das Surface Hub-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="71aa5-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="71aa5-303">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-303">Click **Licenses**.</span></span>

- <span data-ttu-id="71aa5-304">Wählen Sie unter **Lizenzen zuweisen**Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus, abhängig von Ihren Lizenzierungsanforderungen und Enterprise-VoIP-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="71aa5-305">Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP auf Surface Hub verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="71aa5-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="71aa5-306">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="71aa5-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="71aa5-307">Sie können auch das Windows Azure Active Directory-Modul für Windows PowerShell zum Ausführen der Cmdlets verwenden, die zum Zuweisen einer dieser Lizenzen erforderlich sind. Dies wird hier jedoch nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="71aa5-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="71aa5-308">Zur Überprüfung sollten Sie jeden Skype for Business-Client (PC, Android usw.) verwenden können, um sich bei diesem Konto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="71aa5-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="71aa5-309">Skype for Business in einer lokalen Umgebung</span><span class="sxs-lookup"><span data-stu-id="71aa5-309">Skype for Business on-premises</span></span>

<span data-ttu-id="71aa5-310">Um dieses Cmdlet auszuführen, müssen Sie eine Verbindung mit einem der Skype-Front-Ends herstellen.</span><span class="sxs-lookup"><span data-stu-id="71aa5-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="71aa5-311">Öffnen Sie die Skype-PowerShell-Sitzung, und führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="71aa5-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="71aa5-312">Skype for Business in einer hybriden Umgebung</span><span class="sxs-lookup"><span data-stu-id="71aa5-312">Skype for Business hybrid</span></span>

<span data-ttu-id="71aa5-313">Wenn Ihre Organisation [Hybridverbindungen zwischen Skype for Business Server und Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx) eingerichtet hat, sind die Schritte zum Erstellen von Konten anders als bei einer standardmäßigen Surface Hub-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="71aa5-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="71aa5-314">Der Surface Hub erfordert ein Skype-Konto vom Typ *meetingroom*, während ein normaler Benutzer ein Konto vom Typ *user* in Skype verwenden würde.</span><span class="sxs-lookup"><span data-stu-id="71aa5-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="71aa5-315">Wenn Ihr Skype-Server für eine hybride Umgebung eingerichtet wurde, in der Benutzer auf dem lokalen Skype-Server und in Office365 gehostet werden können, treten beim Erstellen eines Surface Hub-Kontos u. U. Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="71aa5-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="71aa5-316">In der Skype for Business Server 2015-Hybridumgebung müssen alle Benutzer, die Sie in Skype for Business Online verwenden möchten, zunächst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in den Active Directory-Domänendiensten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="71aa5-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="71aa5-317">Sie können den Benutzer dann in Skype for Business Online verschieben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="71aa5-318">Das Verschieben eines Benutzerkontos von lokal zu Online erfolgt über das Cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="71aa5-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="71aa5-319">Verwenden Sie das Cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) , um ein Csmeetingroom-Objekt zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="71aa5-320">Wenn Sie das Cmdlet Move-CsMeetingRoom verwenden möchten, müssen Sie [das kumulative Update vom Mai 2017 für Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) oder [das kumulative Update vom Juli 2017 5.0.8308.992 für lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)installiert haben.</span><span class="sxs-lookup"><span data-stu-id="71aa5-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>
