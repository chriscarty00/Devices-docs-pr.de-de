---
title: Lokale Bereitstellung-Gesamtstruktur (Surface Hub)
description: In diesem Thema wird erläutert, wie Sie ein Gerätekonto für Microsoft Surface Hub bei einer lokalen Bereitstellung mit einzelner Gesamtstruktur hinzufügen.
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: Bereitstellung mit einzelner Gesamtstruktur, lokale Bereitstellung, Gerätekonto, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833643"
---
# <span data-ttu-id="608fc-104">Lokale Bereitstellung für Surface Hub in einer Umgebung mit einzelner Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="608fc-104">On-premises deployment for Surface Hub in a single-forest environment</span></span>


<span data-ttu-id="608fc-105">In diesem Thema wird erläutert, wie Sie ein Gerätekonto für Microsoft Surface Hub bei einer lokalen Bereitstellung mit einzelner Gesamtstruktur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="608fc-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a single-forest, on-premises deployment.</span></span>

<span data-ttu-id="608fc-106">Bei einer lokalen Bereitstellung mit einzelner Gesamtstruktur mit Microsoft Exchange 2013 oder höher und Skype for Business 2013 oder höher können Sie [die bereitgestellten PowerShell-Skripts verwenden](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts), um Gerätekonten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="608fc-106">If you have a single-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="608fc-107">Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, siehe [lokale Bereitstellung für Surface Hub in einer Umgebung mit mehreren Gesamtstrukturen](on-premises-deployment-surface-hub-multi-forest.md).</span><span class="sxs-lookup"><span data-stu-id="608fc-107">If you’re using a multi-forest deployment, see [On-premises deployment for Surface Hub in a multi-forest environment](on-premises-deployment-surface-hub-multi-forest.md).</span></span>

1. <span data-ttu-id="608fc-108">Starten Sie eine Remote-PowerShell-Sitzung von einem PC aus, und stellen Sie eine Verbindung mit Exchange her.</span><span class="sxs-lookup"><span data-stu-id="608fc-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

   <span data-ttu-id="608fc-109">Achten Sie darauf, dass Sie die richtigen Berechtigungen festgelegt haben, um die zugeordneten Cmdlets auszuführen.</span><span class="sxs-lookup"><span data-stu-id="608fc-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   <span data-ttu-id="608fc-110">Beachten Sie hier, dass `$strExchangeServer` der vollqualifizierte Domänenname (FQDN) des Exchange-Servers und `$strLyncFQDN` der vollqualifizierte Domänenname des Skype for Business-Servers ist.</span><span class="sxs-lookup"><span data-stu-id="608fc-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. <span data-ttu-id="608fc-111">Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="608fc-111">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="608fc-112">Dadurch kann das Konto in Surface Hub authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="608fc-112">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="608fc-113">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="608fc-113">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="608fc-114">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="608fc-114">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> <span data-ttu-id="608fc-115">Das virtuelle ActiveSync-Verzeichnis Standardauthentifizierung muss aktiviert sein, da sich der Surface-Hub nicht mit anderen Authentifizierungsmethoden authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="608fc-115">ActiveSync Virtual Directory Basic Authentication is required to be enabled as the Surface Hub is unable to authenticate using other authentication methods.</span></span>

3. <span data-ttu-id="608fc-116">Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="608fc-116">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="608fc-117">Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="608fc-117">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="608fc-118">Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="608fc-118">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="608fc-119">Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet – dieses erstellt eine Richtlinie namens „Surface Hubs“.</span><span class="sxs-lookup"><span data-stu-id="608fc-119">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="608fc-120">Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.</span><span class="sxs-lookup"><span data-stu-id="608fc-120">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   <span data-ttu-id="608fc-121">Wenn Sie über eine kompatible Richtlinie verfügen, müssen Sie die Richtlinie auf das Gerätekonto anwenden.</span><span class="sxs-lookup"><span data-stu-id="608fc-121">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="608fc-122">Richtlinien können jedoch nur auf Benutzerkonten und nicht auf Ressourcenpostfächer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="608fc-122">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="608fc-123">Sie benötigen das Postfach in einen Benutzertyp umwandeln, die Richtlinie anwenden und dann wieder zurück in ein Postfach umwandeln – Sie müssen es möglicherweise erneut aktivieren und auch das Kennwort noch einmal festlegen.</span><span class="sxs-lookup"><span data-stu-id="608fc-123">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. <span data-ttu-id="608fc-124">Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis für Benutzer zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="608fc-124">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="608fc-125">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="608fc-125">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="608fc-126">Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="608fc-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="608fc-127">Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="608fc-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. <span data-ttu-id="608fc-128">Aktivieren Sie das Konto in Active Directory, damit es bei Surface Hub authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="608fc-128">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. <span data-ttu-id="608fc-129">Aktivieren Sie das Gerätekonto mit Skype for Business, indem Sie das Surface Hub-AD-Konto für einen Skype for Business Server-Pool aktivieren:</span><span class="sxs-lookup"><span data-stu-id="608fc-129">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   <span data-ttu-id="608fc-130">Sie müssen die Session Initiation-Protokoll (SIP)-Adresse und den Domänencontroller für Surface Hub zusammen mit Ihrer eigenen Skype for Business Server-Pool-ID und Benutzeridentität verwenden.</span><span class="sxs-lookup"><span data-stu-id="608fc-130">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>

8. <span data-ttu-id="608fc-131">OPTIONAL: Sie können durch Aktivieren von Enterprise-VoIP für Ihr Konto auch zulassen, dass Surface Hub PSTN-Telefonanrufe durchführt und empfängt.</span><span class="sxs-lookup"><span data-stu-id="608fc-131">OPTIONAL: You can also allow your Surface Hub to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="608fc-132">Enterprise-VoIP ist keine Voraussetzung für Surface Hub, aber wenn Sie PSTN-Wahlfunktionen für den Surface Hub-Client ermöglichen möchten, können Sie diese wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="608fc-132">Enterprise Voice isn't a requirement for Surface Hub, but if you want PSTN dialing functionality for the Surface Hub client, here's how to enable it:</span></span>

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   <span data-ttu-id="608fc-133">Wieder müssen Sie die bereitgestellten Domänencontroller-und Telefonnummern Beispiele durch ihre eigenen Informationen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="608fc-133">Again, you need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="608fc-134">Der Parameterwert `$true` bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="608fc-134">The parameter value `$true` stays the same.</span></span>
    

 ## <span data-ttu-id="608fc-135">Deaktivieren anonymer e-Mails und Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="608fc-135">Disable anonymous email and IM</span></span>




<span data-ttu-id="608fc-136">Surface Hub verwendet ein Geräte Konto, um e-Mail-und Zusammenarbeitsdienste (Chat, Video, Sprache) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="608fc-136">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="608fc-137">Dieses Geräte Konto wird als Ursprungsidentität ("von"-Partei) beim Senden von e-Mails, Chats und Anrufen verwendet.</span><span class="sxs-lookup"><span data-stu-id="608fc-137">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="608fc-138">Da dieses Konto nicht von einem einzelnen, identifizierbaren Nutzer stammt, wird es als "Anonym" eingestuft, da es vom Device-Konto des Surface Hub stammt.</span><span class="sxs-lookup"><span data-stu-id="608fc-138">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="608fc-139">Angenommen, Sie verfügen über eine benutzerspezifische Clientrichtlinie, die jedem Besprechungsraum Gerät mit einer Identität von **SurfaceHubPolicy**zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="608fc-139">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="608fc-140">Zum Deaktivieren anonymer e-Mails und Nachrichten fügen Sie dieser Clientrichtlinie mithilfe der folgenden Befehle eine clientPolicyEntry hinzu.</span><span class="sxs-lookup"><span data-stu-id="608fc-140">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="608fc-141">So überprüfen Sie, ob die Richtlinie festgesetzt wurde:</span><span class="sxs-lookup"><span data-stu-id="608fc-141">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="608fc-142">Die Ausgabe sollte wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="608fc-142">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="608fc-143">So ändern Sie den Richtlinieneintrag:</span><span class="sxs-lookup"><span data-stu-id="608fc-143">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="608fc-144">So entfernen Sie den Richtlinieneintrag:</span><span class="sxs-lookup"><span data-stu-id="608fc-144">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





