---
title: Online- oder Hybridbereitstellung mithilfe von Skype-Hybrid-Voice-Umgebung (Surface Hub)
description: In diesem Thema wird erläutert, wie Skype for Business Cloud PBX mit lokaler PSTN-Konnektivität über den Cloud Connector Edition- oder Skype for Business 2015-Pool aktiviert wird.
keywords: Hybridbereitstellung, Skype-Hybrid-Voice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833841"
---
# <span data-ttu-id="9b71e-104">Online- oder Hybridbereitstellung mithilfe von Skype-Hybrid-Voice-Umgebung (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="9b71e-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="9b71e-105">In diesem Thema wird erläutert, wie Skype for Business Cloud PBX mit lokaler PSTN (Public Switched Telephone Network)-Konnektivität über den Cloud Connector Edition- oder Skype for Business 2015-Pool aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9b71e-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="9b71e-106">In dieser Option.</span><span class="sxs-lookup"><span data-stu-id="9b71e-106">In this option.</span></span> <span data-ttu-id="9b71e-107">Ihre Skype for Business-Home-Pools und Exchange-Server sind in der Cloud und per PSTN über einen lokalen Pool verbunden, auf dem Skype for Business 2015 oder Cloud Connector Edition ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b71e-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="9b71e-108">[Weitere Informationen über die verschiedenen Cloud PBX-Optionen](https://technet.microsoft.com/library/mt612869.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b71e-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="9b71e-109">Wenn Sie Skype for Business Cloud PBX mit einer der Hybrid-Voice-Optionen bereitgestellt haben, führen Sie die folgenden Schrittezum Aktivieren des Raumkontos für Surface Hub aus.</span><span class="sxs-lookup"><span data-stu-id="9b71e-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="9b71e-110">Es ist wichtig, zunächst ein normales Benutzerkonto zu erstellen, alle Hybrid-Sprachoptionen und Telefonnummern zuzuweisen und das Konto in ein Raumkonto zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9b71e-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="9b71e-111">Wenn Sie diese Reihenfolge nicht befolgen, können Sie keine hybride Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9b71e-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="9b71e-112">Wenn Sie ein Konto vor der Konfiguration von Hybrid-Voice erstellen (Sie führen den Befehl Enable-CSMeetingRoom aus), können Sie die erforderlichen Hybrid-Voice-Parameter nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9b71e-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="9b71e-113">Zum Konfigurieren von Hybrid-Voice-Parametern für ein zuvor konfiguriertes Konto oder zum Neukonfigurieren einer Telefonnummer löschen Sie die E5 oder E3 + Cloud PBX-Add-On-Lizenz, und befolgen Sie die unten stehenden Schritte, beginnend mit Schritt3.</span><span class="sxs-lookup"><span data-stu-id="9b71e-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="9b71e-114">Erstellen Sie ein neues Benutzerkonto für Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="9b71e-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="9b71e-115">In diesem Beispiel wird <strong> surfacehub2@adatum.com verwendet </strong> .</span><span class="sxs-lookup"><span data-stu-id="9b71e-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="9b71e-116">Das Konto kann in lokales Active Directory erstellt und mit der Cloud synchronisiert oder direkt in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![Neuer Objekt-Benutzer](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="9b71e-118">Wählen Sie **Kennwort läuft nie ab** aus.</span><span class="sxs-lookup"><span data-stu-id="9b71e-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="9b71e-119">Dies ist wichtig für ein Surface Hub-Gerät.</span><span class="sxs-lookup"><span data-stu-id="9b71e-119">This is important for a Surface Hub device.</span></span>

   ![Kennwort läuft nie ab](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="9b71e-121">Fügen Sie in Office365 die **E5**-Lizenz oder das **E3 und Cloud PBX**-Add-On dem Benutzerkonto hinzu, das für den Raum erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9b71e-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="9b71e-122">Dies ist erforderlich, damit Hybrid-Voice funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9b71e-122">This is required for Hybrid Voice to work.</span></span>

   ![Produkt-Lizenz hinzufügen](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="9b71e-124">Warten Sie etwa 15Minuten, bis das Benutzerkonto für den Raum in Skype for Business Online angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9b71e-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="9b71e-125">Nachdem das Benutzerkonto für Raum in Skype for Business Online erstellt wurde, aktivieren sie es für Hybrid-Voice in Skype for Business-Remote-PowerShell durch Ausführen des folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9b71e-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="9b71e-126">Überprüfen Sie den Hybrid-Voice-Abfrageablauf, indem Sie Testabfragen über den Surface Hub tätigen.</span><span class="sxs-lookup"><span data-stu-id="9b71e-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="9b71e-127">Starten Sie eine Remote-PowerShell-Sitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange her, indem Sie die folgenden Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b71e-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="9b71e-128">Nach dem Einrichten einer Sitzung ändern Sie das Benutzerkonto für den Raum, um es als **RoomMailboxAccount** zu aktivieren, indem Sie die folgenden Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b71e-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="9b71e-129">Dadurch kann das Konto mit Surface Hub authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="9b71e-130">Nach dem Einrichten des Postfachs müssen Sie entweder eine neue Exchange ActiveSync-Richtlinie erstellen oder eine kompatible vorhandene Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="9b71e-131">Surface Hubs sind nur mit Gerätekonten mit einer ActiveSync-Richtlinie kompatibel, in der die **PasswordEnabled**-Eigenschaft auf **False** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9b71e-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="9b71e-132">Wenn dies nicht richtig festgelegt ist, werden Exchange-Dienste auf Surface Hub (E-Mail, Kalender und Besprechungsteilnahme) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9b71e-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="9b71e-133">Wenn Sie noch keine kompatible Richtlinie erstellt haben, verwenden Sie das folgende Cmdlet (dieses erstellt eine Richtlinie namens „Surface Hubs“).</span><span class="sxs-lookup"><span data-stu-id="9b71e-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="9b71e-134">Nachdem sie erstellt wurde, können Sie dieselbe Richtlinie auf weitere Gerätekonten anwenden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="9b71e-135">Wenn Sie über eine kompatible Richtlinie verfügen, müssen Sie die Richtlinie auf das Gerätekonto anwenden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="9b71e-136">Richtlinien können jedoch nur auf Benutzerkonten und nicht auf Ressourcenpostfächer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="9b71e-137">Führen Sie die folgenden Cmdlets aus, um das Postfach in einen Benutzertyp umzuwandeln, die Richtlinie anzuwenden und dann wieder zurück in ein Postfach umzuwandeln (Sie müssen das Konto möglicherweise erneut aktivieren und das Kennwort noch einmal festlegen).</span><span class="sxs-lookup"><span data-stu-id="9b71e-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="9b71e-138">Für das Gerätekonto müssen verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9b71e-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="9b71e-139">Sie können sehen, welche Eigenschaften in [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="9b71e-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="9b71e-140">Die folgenden Cmdlets bieten ein Beispiel zum Festlegen von Exchange-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9b71e-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="9b71e-141">Aktivieren Sie das Postfach als ein Besprechungsgerät in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9b71e-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="9b71e-142">Führen Sie das folgende Cmdlet aus, das das Konto als Besprechungs Gerät aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9b71e-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="9b71e-143">Durch Ausführen dieses Cmdlet werden Benutzer gefragt, ob sie einen Besprechungsraum sind, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9b71e-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="9b71e-144">Mit **Ja** werden Mikrofon und Lautsprecher stummgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="9b71e-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="9b71e-145">Derzeit ist das Raumkonto vollständig konfiguriert, einschließlich Hybrid-Voice.</span><span class="sxs-lookup"><span data-stu-id="9b71e-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="9b71e-146">Wenn Sie Skype lokal verwenden, können Sie zusätzliche Attribute, z.B. Beschreibung, Position usw., lokal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9b71e-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="9b71e-147">Wenn Sie einen Raum in Skype Online erstellen, können diese Parameter online festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9b71e-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="9b71e-148">In der folgenden Abbildungsehen Sie, wie das Gerät für die Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9b71e-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)
