---
title: Erstellen eines Gerätekontos mithilfe der UI (Surface Hub)
description: Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Gerätekonto für Microsoft Surface Hub entweder mit der Office 365-UI oder mit dem Exchange Admin Center erstellen.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: Erstellen eines Geräte Kontos, Office 365 UI, Exchange Admin Center, Microsoft 365 Admin Center, Skype for Business, Postfachrichtlinie für mobile Geräte
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834075"
---
# <span data-ttu-id="24085-104">Erstellen eines Gerätekontos mithilfe der UI (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="24085-104">Create a device account using UI (Surface Hub)</span></span>


<span data-ttu-id="24085-105">Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Gerätekonto für Microsoft Surface Hub entweder mit der [Office 365-UI](#create-device-acct-o365) oder mit dem [Exchange Admin Center](#create-device-acct-eac) erstellen.</span><span class="sxs-lookup"><span data-stu-id="24085-105">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="24085-106">Erstellen eines Gerätekontos mithilfe von Office 365</span><span class="sxs-lookup"><span data-stu-id="24085-106">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="24085-107">[Erstellen Sie das Konto im Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="24085-107">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="24085-108">[Erstellen einer Postfachrichtlinie für mobile Geräte (ActiveSync) über das Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy)</span><span class="sxs-lookup"><span data-stu-id="24085-108">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="24085-109">[Abschließen der Gerätekontoerstellung mit PowerShell](#create-device-acct-o365-complete-acct)</span><span class="sxs-lookup"><span data-stu-id="24085-109">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="24085-110">[Konfigurieren der Exchange-Eigenschaften des Kontos mit PowerShell](#create-device-acct-o365-configure-exch-prop)</span><span class="sxs-lookup"><span data-stu-id="24085-110">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="24085-111">[Aktivieren des Kontos mit Skype for Business](#create-device-acct-o365-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="24085-111">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="24085-112">Erstellen des Kontos im Admin Center</span><span class="sxs-lookup"><span data-stu-id="24085-112">Create the account in the admin center</span></span>

1.  <span data-ttu-id="24085-113">Wenn Sie sich bei Office 365 anmelden, besuchen Siehttps://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="24085-113">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="24085-114">Geben Sie die Administratoranmeldeinformationen für den Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="24085-114">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="24085-115">Damit gelangen Sie zu Ihrem Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="24085-115">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Microsoft 365 Admin Center](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="24085-117">Navigieren Sie im Admin Center zu **Ressourcen** im linken Bereich, und klicken Sie dann auf **Räume & Geräte**.</span><span class="sxs-lookup"><span data-stu-id="24085-117">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Option "Räume & Ausstattung" im Admin Center](images/room-equipment.png)

4. <span data-ttu-id="24085-119">Klicken Sie auf **Hinzufügen**, um ein neues Raumkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24085-119">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="24085-120">Geben Sie einen Anzeigenamen und eine E-Mail-Adresse für das Konto ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="24085-120">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Erstellen eines neuen Raumkontofensters](images/room-add.png)

5. <span data-ttu-id="24085-122">Wählen Sie das Raumkonto, das Sie gerade erstellt haben, aus der Liste Aktive Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="24085-122">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="24085-123">Im rechten Bereich werden die Kontoeigenschaften und mehrere optionale Aktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24085-123">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="24085-124">Klicken Sie auf **Kennwort zurücksetzen**, um das Kennwort zu ändern, und heben Sie die Auswahl von **Diesen Benutzer bei der ersten Anmeldung sein Kennwort ändern lassen** auf, da es nicht möglich ist, beim Surface Hub-Anmeldeprozesses das Kennwort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="24085-124">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="24085-125">Klicken Sie für den Abschnitt **Zugewiesene Lizenz** auf **Bearbeiten**, und klicken Sie dann auf den Dropdownpfeil neben der Lizenz, um die Details zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="24085-125">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="24085-126">Wählen Sie einen Speicherort für den Benutzer aus, und aktivieren Sie in der Liste der Lizenzen auf **Skype for Business Online (Plan 2)**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24085-126">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="24085-127">Die Lizenz kann abhängig von Ihrer Organisation variieren. (Beispielsweise kann Plan2 oder Plan3 angezeigt werden.)</span><span class="sxs-lookup"><span data-stu-id="24085-127">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="24085-128">Erstellen einer Postfachrichtlinie für mobile Geräte (ActiveSync) über das Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="24085-128">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="24085-129">Klicken Sie im linken Bereich des Admin Centers auf **Administrator**und dann auf **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="24085-129">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![Admin Center mit Exchange-aktiven Benutzern](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="24085-131">Dadurch wird eine weitere Registerkarte in Ihrem Browser geöffnet, über die Sie zum Exchange Admin Center gelangen, wo Sie die Postfacheinstellung für Surface Hub erstellen und festlegen können.</span><span class="sxs-lookup"><span data-stu-id="24085-131">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Exchange Admin Center](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="24085-133">Zum Erstellen einer Postfachrichtlinie für mobile Geräte klicken Sie im linken Bereich auf **Mobil** und dann auf **Postfachrichtlinien für mobile Geräte**.</span><span class="sxs-lookup"><span data-stu-id="24085-133">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="24085-134">Surface Hubs erfordern ein Konto mit einer Postfachrichtlinie für mobile Geräte, die kein Kennwort erfordert. Wenn Sie bereits über eine vorhandene Richtlinie verfügen, die dieser Anforderung entspricht, können Sie diese Richtlinie auf das Konto anwenden.</span><span class="sxs-lookup"><span data-stu-id="24085-134">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="24085-135">Führen Sie andernfalls die folgenden Schritte aus, um eine neue Richtlinie zu erstellen, die nur für Surface Hub-Gerätekonten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="24085-135">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Exchange Admin Center – Erstellen einer Postfachrichtlinie für mobile Geräte](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="24085-137">Zum Erstellen einer neuen Postfachrichtlinie für mobile Geräte für Surface Hub klicken Sie in den Steuerelementen oberhalb der Liste der Richtlinien auf die Schaltfläche **+** , um eine neue Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="24085-137">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="24085-138">Geben Sie als Namen einen Namen an, mit dem Sie diese Richtlinie von anderen Gerätekonten unterscheiden können (z. B. *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="24085-138">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="24085-139">Stellen Sie sicher, dass die Richtlinie kein Kennwort für die zugewiesenen Geräte erfordert. Überprüfen Sie daher, dass **Kennwort anfordern** deaktiviert bleibt, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24085-139">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Abbildung der neuen Richtlinie für mobile Geräte](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="24085-141">Nachdem Sie die neue Postfachrichtlinie für mobile Geräte erstellt haben, wechseln Sie zurück zum **Exchange Admin Center**. Dort wird die neue Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24085-141">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Bild mit der neuen Postfachrichtlinie für mobile Geräte im Exchange Admin Center](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="24085-143">Abschließen der Gerätekontoerstellung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="24085-143">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="24085-144">Ab hier müssen Sie den Vorgang zur Kontoerstellung mithilfe von PowerShell abschließen, um Konfigurationen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="24085-144">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="24085-145">Um von diesen PowerShell-Skripts verwendete Cmdlets auszuführen, muss Folgendes für die PowerShell-Verwaltungskonsole installiert werden:</span><span class="sxs-lookup"><span data-stu-id="24085-145">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="24085-146">Microsoft Online Services-Anmelde Assistent für IT-Experten RTW</span><span class="sxs-lookup"><span data-stu-id="24085-146">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="24085-147">Windows Azure Active Directory-Modul für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24085-147">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="24085-148">Skype for Business Online, Windows PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="24085-148">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="24085-149">Installieren des folgenden Moduls in PowerShell</span><span class="sxs-lookup"><span data-stu-id="24085-149">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="24085-150">Herstellen einer Verbindung mit Onlinediensten</span><span class="sxs-lookup"><span data-stu-id="24085-150">Connecting to online services</span></span>

1.  <span data-ttu-id="24085-151">Führen Sie Windows PowerShell als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="24085-151">Run Windows PowerShell as Administrator.</span></span>

    ![Abbildung zur Verdeutlichung, wie Sie Windows PowerShell starten und als Administrator ausführen](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="24085-153">Erstellen Sie ein Anmeldeinformationsobjekt, erstellen Sie dann eine neue Sitzung, die eine Verbindung mit Skype for Business Online herstellt, geben Sie das globale Mandantenadministratorkonto an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="24085-153">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Bild für Anforderung für Windows PowerShell-Anmeldeinformationen](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="24085-155">Führen Sie zur Herstellung einer Verbindung mit Microsoft Online Services Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="24085-155">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="24085-157">Führen Sie nun zur Herstellung einer Verbindung mit Skype for Business Online-Diensten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="24085-157">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="24085-159">Führen Sie zum Schluss zur Herstellung einer Verbindung mit Exchange Online-Diensten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="24085-159">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="24085-161">Sie müssen nun die gerade erstellte Skype for Business Online-Sitzung und Exchange Online-Sitzung importieren, wodurch die Exchange- und Skype-Befehle importiert werden, sodass Sie diese lokal verwenden können.</span><span class="sxs-lookup"><span data-stu-id="24085-161">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="24085-162">Beachten Sie, dass dies einige Zeit dauern kann.</span><span class="sxs-lookup"><span data-stu-id="24085-162">Note that this could take a while to complete.</span></span>

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="24085-164">Wenn Sie mit den Onlinediensten verbunden sind, müssen Sie weitere Cmdlets ausführen, um dieses Kontos als Surface Hub-Gerätekonto zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24085-164">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="24085-165">Konfigurieren der Exchange-Eigenschaften des Kontos mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="24085-165">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="24085-166">Nachdem Sie mit den Onlinediensten verbunden sind, können Sie die Einrichtung des Gerätekontos abschließen.</span><span class="sxs-lookup"><span data-stu-id="24085-166">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="24085-167">Sie verwenden die E-Mail-Adresse des Gerätekontos für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="24085-167">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="24085-168">Ändern des Postfachtyps von „regulär“ in „Raum“</span><span class="sxs-lookup"><span data-stu-id="24085-168">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="24085-169">Festlegen des Kennworts und Aktivieren des Raumpostfachkontos</span><span class="sxs-lookup"><span data-stu-id="24085-169">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="24085-170">Ändern verschiedener Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="24085-170">Change various Exchange properties</span></span>
-   <span data-ttu-id="24085-171">Festlegen des Kennworts des Benutzerkontos auf „Läuft nie ab“.</span><span class="sxs-lookup"><span data-stu-id="24085-171">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="24085-172">Sie müssen die E-Mail-Adresse des Kontos eingeben und eine Variable mit diesem Wert erstellen:</span><span class="sxs-lookup"><span data-stu-id="24085-172">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="24085-173">Rufen Sie den Wert zum Speichern aus dem Postfach ab:</span><span class="sxs-lookup"><span data-stu-id="24085-173">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="24085-174">Drucken Sie den Wert:</span><span class="sxs-lookup"><span data-stu-id="24085-174">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="24085-175">Die richtige E-Mail-Adresse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24085-175">You will see the correct email address.</span></span>

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="24085-177">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24085-177">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="24085-178">Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="24085-178">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="24085-179">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="24085-179">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="24085-181">Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="24085-181">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="24085-182">Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="24085-182">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="24085-183">Aktivieren des Kontos mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="24085-183">Enable the account with Skype for Business</span></span>

<span data-ttu-id="24085-184">Aktivieren Sie das Gerätekonto mit Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="24085-184">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="24085-185">Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="24085-185">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="24085-186">Sie müssen Skype for Business Online Standalone Plan 2 oder höher in Ihrem Office 365-Plan haben.</span><span class="sxs-lookup"><span data-stu-id="24085-186">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="24085-187">Der Plan muss Konferenzfunktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="24085-187">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="24085-188">Wenn Sie Enterprise-VoIP (PSTN-Telefonie) mithilfe von Telefoniedienstanbieter für den Surface Hub benötigen, benötigen Sie den Standalone-Plan 3 von Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="24085-188">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="24085-189">Die Mandantenbenutzer müssen über Exchange-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="24085-189">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="24085-190">Ihr Surface Hub-Konto erfordert einen eigenständigen Skype for Business Online-Plan 2 oder eine Skype for Business Online Standalone Plan 3-Lizenz, es ist jedoch keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24085-190">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="24085-191">Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="24085-191">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="24085-192">Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24085-192">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="24085-193">Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:</span><span class="sxs-lookup"><span data-stu-id="24085-193">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="24085-194">Erstellen eines Gerätekontos mithilfe von Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="24085-194">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="24085-195">Diese Methode funktioniert nur, wenn Sie die Synchronisierung von einem lokalen Active Directory aus durchführt.</span><span class="sxs-lookup"><span data-stu-id="24085-195">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="24085-196">Sie können das Exchange Admin Center zum Erstellen eines Gerätekontos verwenden:</span><span class="sxs-lookup"><span data-stu-id="24085-196">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="24085-197">[Erstellen eines Kontos und eines Postfachs mit dem Exchange Admin Center](#create-device-acct-exch-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="24085-197">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="24085-198">[Erstellen einer Postfachrichtlinie für mobile Geräte über das Exchange Admin Center](#create-device-acct-exch-mbx-policy)</span><span class="sxs-lookup"><span data-stu-id="24085-198">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="24085-199">[Konfigurieren des Kontos mit PowerShell](#create-device-acct-exch-powershell-conf)</span><span class="sxs-lookup"><span data-stu-id="24085-199">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="24085-200">[Aktivieren des Kontos mit Skype for Business](#create-device-acct-exch-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="24085-200">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="24085-201">Erstellen eines Konto und eines Postfachs mit dem Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="24085-201">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="24085-202">Melden Sie sich beim Exchange Admin Center mit Exchange-Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="24085-202">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="24085-203">Navigieren Sie im Exchange Admin Center (EAC) im linken Bereich zu **Empfänger** .</span><span class="sxs-lookup"><span data-stu-id="24085-203">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Abbildung von Postfächern im Exchange Admin Center](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="24085-205">Klicken Sie in den Steuerelementen oberhalb der Liste der Postfächer auf **+**, um ein neues Postfach zu erstellen, und geben Sie Folgendes an: **Anzeigename**, **Name** und **Benutzeranmeldename**. Klicken Sie anschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24085-205">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Abbildung der Erstellung ein neuen Postfachs](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="24085-207">Erstellen einer Postfachrichtlinie für mobile Geräte aus dem Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="24085-207">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="24085-208">Wenn Sie dem erstellten Konto eine Richtlinie erstellen und zuweisen möchten und Exchange 2010 verwenden, lesen Sie die entsprechenden Informationen zur Richtlinienerstellung und Richtlinienzuweisung, wenn Sie die Exchange-Verwaltungskonsole verwenden.</span><span class="sxs-lookup"><span data-stu-id="24085-208">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="24085-209">Wechseln Sie zum Exchange Admin Center.</span><span class="sxs-lookup"><span data-stu-id="24085-209">Go to the Exchange Admin Center.</span></span>

    ![Abbildung des Exchange Admin Center](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="24085-211">Zum Erstellen einer Postfachrichtlinie für mobile Geräte klicken Sie im linken Bereich auf **Mobil** und dann auf **Postfachrichtlinien für mobile Geräte**.</span><span class="sxs-lookup"><span data-stu-id="24085-211">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="24085-212">Surface Hubs erfordern ein Konto mit einer Postfachrichtlinie für mobile Geräte, die kein Kennwort erfordert. Wenn Sie bereits über eine vorhandene Richtlinie verfügen, die dieser Anforderung entspricht, können Sie diese Richtlinie auf das Konto anwenden.</span><span class="sxs-lookup"><span data-stu-id="24085-212">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="24085-213">Führen Sie andernfalls die folgenden Schritte aus, um eine neue Richtlinie zu erstellen, die nur für Surface Hub-Gerätekonten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="24085-213">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Abbildung der Verwendung von Exchange Admin Center zum Erstellen einer Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="24085-215">Zum Erstellen einer neuen Postfachrichtlinie für mobile Geräte klicken Sie in den Steuerelementen oberhalb der Liste der Richtlinien auf die Schaltfläche **+** , um eine neue Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="24085-215">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="24085-216">Geben Sie als Namen einen Namen an, mit dem Sie diese Richtlinie von anderen Gerätekonten unterscheiden können (z. B. *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="24085-216">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="24085-217">Die Richtlinie darf nicht kennwortgeschützt sein. Stellen Sie daher sicher, dass **Kennwort anfordern** deaktiviert bleibt, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24085-217">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Abbildung der neuen Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="24085-219">Nachdem Sie die neue Postfachrichtlinie für mobile Geräte erstellt haben, wechseln Sie zurück zum Exchange Admin Center. Dort wird die neue Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24085-219">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Bild der neuen Postfachrichtlinie für mobile Geräte im Exchange Admin Center](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="24085-221">Zum Anwenden der ActiveSync-Richtlinie ohne Verwendung von PowerShell können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="24085-221">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="24085-222">Klicken Sie im Exchange Admin Center auf **Empfänger** &gt; **Postfächer**, und wählen Sie ein Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="24085-222">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Abbildung des Exchange Admin Center](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="24085-224">Scrollen Sie im Bereich **Details** zu **Telefon- und Sprachfunktionen**, und klicken Sie auf **Details anzeigen**, um den Bildschirm **Details des mobilen Geräts** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="24085-224">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Abbildung von Postfachdetails](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="24085-226">Die derzeit zugewiesene Postfachrichtlinie für mobile Geräte wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24085-226">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="24085-227">Zum Ändern der Postfachrichtlinie für mobile Geräte klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="24085-227">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Abbildung der derzeit zugewiesenen Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="24085-229">Wählen Sie die entsprechende Postfachrichtlinie für mobile Geräte in der Liste aus, klicken Sie auf **OK** und dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24085-229">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Abbildung der Liste von Postfachrichtlinien für mobile Geräte](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="24085-231">Konfigurieren des Kontos mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="24085-231">Use PowerShell to configure the account</span></span>

<span data-ttu-id="24085-232">Nachdem Sie mit den Onlinediensten verbunden sind, können Sie die Einrichtung des Gerätekontos abschließen.</span><span class="sxs-lookup"><span data-stu-id="24085-232">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="24085-233">Sie verwenden die E-Mail-Adresse des Gerätekontos für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="24085-233">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="24085-234">Ändern des Postfachtyps von „regulär“ in „Raum“</span><span class="sxs-lookup"><span data-stu-id="24085-234">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="24085-235">Ändern verschiedener Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="24085-235">Change various Exchange properties</span></span>
-   <span data-ttu-id="24085-236">Festlegen des Kennworts des Benutzerkontos auf „Läuft nie ab“.</span><span class="sxs-lookup"><span data-stu-id="24085-236">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="24085-237">Sie müssen die E-Mail-Adresse des Kontos eingeben und eine Variable mit diesem Wert erstellen:</span><span class="sxs-lookup"><span data-stu-id="24085-237">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="24085-238">Rufen Sie den Wert zum Speichern aus dem Postfach ab:</span><span class="sxs-lookup"><span data-stu-id="24085-238">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="24085-239">Drucken Sie den Wert, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="24085-239">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="24085-240">Die richtige E-Mail-Adresse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24085-240">You will see the correct email address.</span></span>

2.  <span data-ttu-id="24085-241">Sie müssen das Konto in ein Raumpostfach konvertieren, damit Sie Folgendes ausführen können:</span><span class="sxs-lookup"><span data-stu-id="24085-241">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="24085-242">Zum Authentifizieren des Gerätekontos auf einem Surface Hub müssen Sie das Raumpostfachkonto aktivieren und ein Kennwort festlegen, damit das Gerät das Konto zum Abrufen von Besprechungsinformationen mithilfe von ActiveSync und zum Anmelden bei Skype for Business verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="24085-242">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="24085-243">Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="24085-243">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="24085-244">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="24085-244">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="24085-245">Jetzt müssen wir einige Eigenschaften in AD festlegen.</span><span class="sxs-lookup"><span data-stu-id="24085-245">Now we have to set some properties in AD.</span></span> <span data-ttu-id="24085-246">Dazu benötigen Sie das Alias des Kontos (dies ist der Teil des Benutzerprinzipalnamens vor „@“).</span><span class="sxs-lookup"><span data-stu-id="24085-246">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="24085-247">Der Benutzer muss in AD aktiviert werden, bevor er mit einem Surface Hub authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="24085-247">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="24085-248">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="24085-248">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="24085-249">Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="24085-249">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="24085-250">Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="24085-250">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="24085-251">Aktivieren des Kontos mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="24085-251">Enable the account with Skype for Business</span></span>

<span data-ttu-id="24085-252">Aktivieren Sie das Gerätekonto mit Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="24085-252">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="24085-253">Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="24085-253">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="24085-254">Sie müssen Skype for Business Online Standalone Plan 2 oder höher in Ihrem Office 365-Plan haben.</span><span class="sxs-lookup"><span data-stu-id="24085-254">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="24085-255">Der Plan muss Konferenzfunktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="24085-255">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="24085-256">Wenn Sie Enterprise-VoIP (PSTN-Telefonie) mithilfe von Telefoniedienstanbieter für den Surface Hub benötigen, benötigen Sie den Standalone-Plan 3 von Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="24085-256">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="24085-257">Die Mandantenbenutzer müssen über Exchange-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="24085-257">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="24085-258">Ihr Surface Hub-Konto erfordert einen eigenständigen Skype for Business Online-Plan 2 oder eine Skype for Business Online Standalone Plan 3-Lizenz, es ist jedoch keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24085-258">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="24085-259">Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="24085-259">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="24085-260">Abrufen des Surface Hub-Konto registrierungspools</span><span class="sxs-lookup"><span data-stu-id="24085-260">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="24085-261">Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:</span><span class="sxs-lookup"><span data-stu-id="24085-261">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. <span data-ttu-id="24085-262">Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24085-262">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





