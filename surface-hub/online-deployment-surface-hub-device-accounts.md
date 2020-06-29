---
title: Onlinebereitstellung mit Office 365 (Surface Hub)
description: Dieses Thema enthält Anweisungen zum Hinzufügen eines Gerätekontos für Microsoft Surface Hub bei einer reinen Onlinebereitstellung.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: Gerätekonto für Surface Hub, Onlinebereitstellung
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833616"
---
# <span data-ttu-id="0f8ca-104">Onlinebereitstellung mit Office 365 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="0f8ca-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="0f8ca-105">Dieses Thema enthält Anweisungen zum Hinzufügen eines Gerätekontos für Microsoft Surface Hub bei einer reinen Onlinebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="0f8ca-106">Bei einer reinen Onlinebereitstellung (O365) können Sie [die bereitgestellten PowerShell-Skripts verwenden](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts), um Gerätekonten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="0f8ca-107">Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange her.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="0f8ca-108">Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="0f8ca-109">Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="0f8ca-110">Dadurch kann das Konto in Surface Hub authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="0f8ca-111">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="0f8ca-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="0f8ca-112">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="0f8ca-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="0f8ca-113">Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="0f8ca-114">Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="0f8ca-115">Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="0f8ca-116">Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="0f8ca-117">Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="0f8ca-118">Wenn Sie über eine kompatible Richtlinie verfügen, müssen Sie die Richtlinie auf das Gerätekonto anwenden.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="0f8ca-119">Für das Gerätekonto müssen verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="0f8ca-120">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="0f8ca-121">Stellen Sie eine Verbindung mit Azure AD her.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="0f8ca-122">Sie müssen zuerst das Azure AD-Modul für die PowerShell Version 2 installieren.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="0f8ca-123">Führen Sie an einer PowerShell-Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0f8ca-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="0f8ca-124">Sie müssen eine Verbindung mit Azure AD herstellen, um einige Kontoeinstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="0f8ca-125">Sie können zum Herstellen der Verbindung dieses Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="0f8ca-126">Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="0f8ca-127">Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="0f8ca-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="0f8ca-128">Surface Hub erfordert eine Lizenz für Skype for Business-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="0f8ca-129">Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende [Voraussetzungen für Skype for Business Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online) erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="0f8ca-130">Als Nächstes können Sie mit `Get-AzureADSubscribedSku` eine Liste der verfügbaren SKUs für Ihren O365-Mandanten abrufen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="0f8ca-131">Nachdem Sie die SKUs aufgelistet haben, müssen Sie die die für die `$License.SkuId`-Variable gewünschte SKU-ID zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

8. <span data-ttu-id="0f8ca-132">Aktivieren Sie das Gerätekonto mit Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="0f8ca-133">Wenn das Skype for Business-PowerShell-Modul nicht installiert ist, [laden Sie hier das Skype for Business Online Windows PowerShell-Modul herunter](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="0f8ca-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="0f8ca-134">Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="0f8ca-135">Wenn Sie sich dann nicht sicher sind, welcher Wert für den `RegistrarPool`-Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen (z.B. <em>alice@contoso.com</em>):</span><span class="sxs-lookup"><span data-stu-id="0f8ca-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="0f8ca-136">ODER durch Festlegen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="0f8ca-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="0f8ca-137">Aktivieren Sie das Surface Hub-Konto mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0f8ca-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="0f8ca-138">ODER verwenden Sie die Variable $strRegistarPool von oben</span><span class="sxs-lookup"><span data-stu-id="0f8ca-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="0f8ca-139">Zur Überprüfung sollten Sie jeden Skype for Business-Client (PC, Android usw.) verwenden können, um sich bei diesem Konto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="0f8ca-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>





