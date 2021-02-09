---
title: Erstellen eines Gerätekontos mithilfe der Benutzeroberfläche (Surface Hub v1)
description: Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Gerätekonto für Microsoft Surface Hub entweder mit der Office 365-UI oder mit dem Exchange Admin Center erstellen.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: Erstellen eines Gerätekontos, Office 365 UI, Exchange Admin Center, Microsoft 365 Admin Center, Skype for Business, Postfachrichtlinie für mobile Geräte
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: dd19e2fd2417acd29e71c7555e94ee849fbc1bec
ms.sourcegitcommit: 32b6c25698479fa289f642c5b5761ff3be15b686
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "11318009"
---
# <span data-ttu-id="fb628-104">Erstellen eines Gerätekontos mithilfe der Benutzeroberfläche (Surface Hub v1)</span><span class="sxs-lookup"><span data-stu-id="fb628-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="fb628-105">Diese Seite enthält Informationen zum ursprünglichen Surface Hub (v1).</span><span class="sxs-lookup"><span data-stu-id="fb628-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="fb628-106">Informationen zu Surface Hub 2S finden Sie unter [Erstellen des Surface Hub 2S-Gerätekontos.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="fb628-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="fb628-107">Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Gerätekonto für Microsoft Surface Hub entweder mit der [Office 365-UI](#create-device-acct-o365) oder mit dem [Exchange Admin Center](#create-device-acct-eac) erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb628-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="fb628-108">Erstellen eines Gerätekontos mithilfe von Office 365</span><span class="sxs-lookup"><span data-stu-id="fb628-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="fb628-109">[Erstellen Sie das Konto im Microsoft 365 Admin Center.](#create-device-acct-o365-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="fb628-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="fb628-110">[Erstellen einer Postfachrichtlinie für mobile Geräte (ActiveSync) über das Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy)</span><span class="sxs-lookup"><span data-stu-id="fb628-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="fb628-111">[Abschließen der Gerätekontoerstellung mit PowerShell](#create-device-acct-o365-complete-acct)</span><span class="sxs-lookup"><span data-stu-id="fb628-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="fb628-112">[Konfigurieren der Exchange-Eigenschaften des Kontos mit PowerShell](#create-device-acct-o365-configure-exch-prop)</span><span class="sxs-lookup"><span data-stu-id="fb628-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="fb628-113">[Aktivieren des Kontos mit Skype for Business](#create-device-acct-o365-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="fb628-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="fb628-114">Erstellen des Kontos im Admin Center</span><span class="sxs-lookup"><span data-stu-id="fb628-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="fb628-115">Melden Sie sich bei Office 365 über einen Besuch [https://portal.office.com](https://portal.office.com) an.</span><span class="sxs-lookup"><span data-stu-id="fb628-115">Sign in to Office 365 by visiting [https://portal.office.com](https://portal.office.com).</span></span>

2.  <span data-ttu-id="fb628-116">Geben Sie die Administratoranmeldeinformationen für den Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="fb628-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="fb628-117">Dadurch gehen Sie zu Ihrem Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="fb628-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 Admin Center.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="fb628-119">Navigieren Sie im Admin \*\*\*\* Center im linken Bereich zu "Ressourcen", und klicken Sie dann auf "Räume" **& Gerät**.</span><span class="sxs-lookup"><span data-stu-id="fb628-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Räume & Geräteoption im Admin Center](images/room-equipment.png)

4. <span data-ttu-id="fb628-121">Klicken Sie auf **Hinzufügen**, um ein neues Raumkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb628-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="fb628-122">Geben Sie einen Anzeigenamen und eine E-Mail-Adresse für das Konto ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fb628-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Erstellen eines neuen Raumkontofensters](images/room-add.png)

5. <span data-ttu-id="fb628-124">Wählen Sie das Raumkonto, das Sie gerade erstellt haben, aus der Liste Aktive Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="fb628-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="fb628-125">Im rechten Bereich werden die Kontoeigenschaften und mehrere optionale Aktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb628-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="fb628-126">Klicken Sie auf **Kennwort zurücksetzen**, um das Kennwort zu ändern, und heben Sie die Auswahl von **Diesen Benutzer bei der ersten Anmeldung sein Kennwort ändern lassen** auf, da es nicht möglich ist, beim Surface Hub-Anmeldeprozesses das Kennwort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fb628-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="fb628-127">Klicken Sie für den Abschnitt **Zugewiesene Lizenz** auf **Bearbeiten**, und klicken Sie dann auf den Dropdownpfeil neben der Lizenz, um die Details zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="fb628-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="fb628-128">Wählen Sie einen Speicherort für den Benutzer aus, und aktivieren Sie in der Liste der Lizenzen auf **Skype for Business Online (Plan 2)**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb628-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="fb628-129">Die Lizenz kann abhängig von Ihrer Organisation variieren. (Beispielsweise kann Plan2 oder Plan3 angezeigt werden.)</span><span class="sxs-lookup"><span data-stu-id="fb628-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="fb628-130">Erstellen einer Postfachrichtlinie für mobile Geräte (ActiveSync) über das Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="fb628-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="fb628-131">Klicken Sie im linken Bereich des Admin Centers auf **ADMIN**, und klicken Sie dann auf **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fb628-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Admin Center mit aktiven Exchange-Benutzern.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="fb628-133">Dadurch wird eine weitere Registerkarte in Ihrem Browser geöffnet, über die Sie zum Exchange Admin Center gelangen, wo Sie die Postfacheinstellung für Surface Hub erstellen und festlegen können.</span><span class="sxs-lookup"><span data-stu-id="fb628-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exchange Admin Center](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="fb628-135">Zum Erstellen einer Postfachrichtlinie für mobile Geräte klicken Sie im linken Bereich auf **Mobil** und dann auf **Postfachrichtlinien für mobile Geräte**.</span><span class="sxs-lookup"><span data-stu-id="fb628-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="fb628-136">Surface Hubs erfordern ein Konto mit einer Postfachrichtlinie für mobile Geräte, die kein Kennwort erfordert. Wenn Sie bereits über eine vorhandene Richtlinie verfügen, die dieser Anforderung entspricht, können Sie diese Richtlinie auf das Konto anwenden.</span><span class="sxs-lookup"><span data-stu-id="fb628-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="fb628-137">Führen Sie andernfalls die folgenden Schritte aus, um eine neue Richtlinie zu erstellen, die nur für Surface Hub-Gerätekonten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb628-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exchange Admin Center – Erstellen einer Postfachrichtlinie für mobile Geräte](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="fb628-139">Zum Erstellen einer neuen Postfachrichtlinie für mobile Geräte für Surface Hub klicken Sie in den Steuerelementen oberhalb der Liste der Richtlinien auf die Schaltfläche **+** , um eine neue Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb628-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="fb628-140">Geben Sie als Namen einen Namen an, mit dem Sie diese Richtlinie von anderen Gerätekonten unterscheiden können (z. B. *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="fb628-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="fb628-141">Stellen Sie sicher, dass die Richtlinie kein Kennwort für die zugewiesenen Geräte erfordert. Überprüfen Sie daher, dass **Kennwort anfordern** deaktiviert bleibt, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb628-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Abbildung der neuen Richtlinie für mobile Geräte](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="fb628-143">Nachdem Sie die neue Postfachrichtlinie für mobile Geräte erstellt haben, wechseln Sie zurück zum **Exchange Admin Center**. Dort wird die neue Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb628-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Bild mit der neuen Postfachrichtlinie für mobile Geräte im Exchange Admin Center](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="fb628-145">Abschließen der Gerätekontoerstellung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb628-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="fb628-146">Ab hier müssen Sie den Vorgang zur Kontoerstellung mithilfe von PowerShell abschließen, um Konfigurationen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fb628-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="fb628-147">Um von diesen PowerShell-Skripts verwendete Cmdlets auszuführen, muss Folgendes für die PowerShell-Verwaltungskonsole installiert werden:</span><span class="sxs-lookup"><span data-stu-id="fb628-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="fb628-148">Microsoft Online Services Sign-In Assistent für IT-Experten RTW</span><span class="sxs-lookup"><span data-stu-id="fb628-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="fb628-149">Windows Azure Active Directory-Modul für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb628-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="fb628-150">Skype for Business Online, Windows PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="fb628-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="fb628-151">Installieren Sie das folgende Modul in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb628-151">Install the following module in PowerShell.</span></span>

```powershell
install-module AzureAD
Install-module MsOnline
```

### <span data-ttu-id="fb628-152">Herstellen einer Verbindung mit Onlinediensten</span><span class="sxs-lookup"><span data-stu-id="fb628-152">Connecting to online services</span></span>

1.  <span data-ttu-id="fb628-153">Führen Sie Windows PowerShell als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="fb628-153">Run Windows PowerShell as Administrator.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Abbildung zur Verdeutlichung, wie Sie Windows PowerShell starten und als Administrator ausführen](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="fb628-155">Erstellen Sie ein Anmeldeinformationsobjekt, erstellen Sie dann eine neue Sitzung, die eine Verbindung mit Skype for Business Online herstellt, geben Sie das globale Mandantenadministratorkonto an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb628-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Bild für Anforderung für Windows PowerShell-Anmeldeinformationen](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="fb628-157">Führen Sie zur Herstellung einer Verbindung mit Microsoft Online Services Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-157">To connect to Microsoft Online Services, run:</span></span>

    ```powershell
    Connect-MsolService -Credential $Cred
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="fb628-159">Führen Sie nun zur Herstellung einer Verbindung mit Skype for Business Online-Diensten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ```powershell
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="fb628-161">Führen Sie zum Schluss zur Herstellung einer Verbindung mit Exchange Online-Diensten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ```powershell
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="fb628-163">Sie müssen nun die gerade erstellte Skype for Business Online-Sitzung und Exchange Online-Sitzung importieren, wodurch die Exchange- und Skype-Befehle importiert werden, sodass Sie diese lokal verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fb628-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ```powershell
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="fb628-164">Beachten Sie, dass dies einige Zeit dauern kann.</span><span class="sxs-lookup"><span data-stu-id="fb628-164">Note that this could take a while to complete.</span></span>

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="fb628-166">Wenn Sie mit den Onlinediensten verbunden sind, müssen Sie weitere Cmdlets ausführen, um dieses Kontos als Surface Hub-Gerätekonto zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb628-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="fb628-167">Konfigurieren der Exchange-Eigenschaften des Kontos mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb628-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="fb628-168">Nachdem Sie mit den Onlinediensten verbunden sind, können Sie die Einrichtung des Gerätekontos abschließen.</span><span class="sxs-lookup"><span data-stu-id="fb628-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="fb628-169">Sie verwenden die E-Mail-Adresse des Gerätekontos für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="fb628-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="fb628-170">Ändern des Postfachtyps von „regulär“ in „Raum“</span><span class="sxs-lookup"><span data-stu-id="fb628-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="fb628-171">Festlegen des Kennworts und Aktivieren des Raumpostfachkontos</span><span class="sxs-lookup"><span data-stu-id="fb628-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="fb628-172">Ändern verschiedener Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fb628-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="fb628-173">Festlegen des Kennworts des Benutzerkontos auf „Läuft nie ab“.</span><span class="sxs-lookup"><span data-stu-id="fb628-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="fb628-174">Sie müssen die E-Mail-Adresse des Kontos eingeben und eine Variable mit diesem Wert erstellen:</span><span class="sxs-lookup"><span data-stu-id="fb628-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="fb628-175">Rufen Sie den Wert zum Speichern aus dem Postfach ab:</span><span class="sxs-lookup"><span data-stu-id="fb628-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="fb628-176">Drucken Sie den Wert:</span><span class="sxs-lookup"><span data-stu-id="fb628-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="fb628-177">Die richtige E-Mail-Adresse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb628-177">You will see the correct email address.</span></span>

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="fb628-179">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="fb628-180">Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="fb628-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="fb628-181">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb628-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="fb628-183">Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb628-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="fb628-184">Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="fb628-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ```powershell
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="fb628-185">Aktivieren des Kontos mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fb628-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="fb628-186">Aktivieren Sie das Gerätekonto mit Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb628-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="fb628-187">Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="fb628-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="fb628-188">Sie benötigen Skype for Business Online Eigenständig Plan 2 oder höher in Ihrem O365-Plan.</span><span class="sxs-lookup"><span data-stu-id="fb628-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="fb628-189">Der Plan muss Konferenzfunktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb628-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="fb628-190">Wenn Sie eine Enterprise-VoIP (PSTN-Telefonie) mit Telefoniedienstanbietern für den Surface Hub benötigen, benötigen Sie Skype for Business Online Eigenständig, Plan 3.</span><span class="sxs-lookup"><span data-stu-id="fb628-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="fb628-191">Die Mandantenbenutzer müssen über Exchange-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="fb628-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="fb628-192">Für Ihr Surface Hub-Konto ist eine Skype for Business Online Standalone Plan 2- oder Skype for Business Online Standalone Plan 3-Lizenz erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb628-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="fb628-193">Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="fb628-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="fb628-194">Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```powershell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

     <span data-ttu-id="fb628-195">Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:</span><span class="sxs-lookup"><span data-stu-id="fb628-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```powershell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="fb628-196">Erstellen eines Gerätekontos mithilfe von Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="fb628-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="fb628-197">Diese Methode funktioniert nur, wenn Sie eine Synchronisierung von einem lokalen Active Directory aus erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb628-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="fb628-198">Sie können das Exchange Admin Center zum Erstellen eines Gerätekontos verwenden:</span><span class="sxs-lookup"><span data-stu-id="fb628-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="fb628-199">[Erstellen eines Kontos und eines Postfachs mit dem Exchange Admin Center](#create-device-acct-exch-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="fb628-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="fb628-200">[Erstellen einer Postfachrichtlinie für mobile Geräte über das Exchange Admin Center](#create-device-acct-exch-mbx-policy)</span><span class="sxs-lookup"><span data-stu-id="fb628-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="fb628-201">[Konfigurieren des Kontos mit PowerShell](#create-device-acct-exch-powershell-conf)</span><span class="sxs-lookup"><span data-stu-id="fb628-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="fb628-202">[Aktivieren des Kontos mit Skype for Business](#create-device-acct-exch-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="fb628-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="fb628-203">Erstellen eines Konto und eines Postfachs mit dem Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="fb628-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="fb628-204">Melden Sie sich beim Exchange Admin Center mit Exchange-Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="fb628-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="fb628-205">Navigieren Sie im Exchange Admin Center (EAC) im linken Bereich zu **Empfänger** .</span><span class="sxs-lookup"><span data-stu-id="fb628-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Abbildung von Postfächern im Exchange Admin Center](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="fb628-207">Klicken Sie in den Steuerelementen oberhalb der Liste der Postfächer auf **+**, um ein neues Postfach zu erstellen, und geben Sie Folgendes an: **Anzeigename**, **Name** und **Benutzeranmeldename**. Klicken Sie anschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb628-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Abbildung der Erstellung ein neuen Postfachs](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="fb628-209">Erstellen einer Postfachrichtlinie für mobile Geräte aus dem Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="fb628-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="fb628-210">Wenn Sie dem erstellten Konto eine Richtlinie erstellen und zuweisen möchten und Exchange 2010 verwenden, suchen Sie bei Verwendung der EMC (Exchange Management Console) die entsprechenden Informationen zur Richtlinienerstellung und -zuweisung.</span><span class="sxs-lookup"><span data-stu-id="fb628-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="fb628-211">Wechseln Sie zum Exchange Admin Center.</span><span class="sxs-lookup"><span data-stu-id="fb628-211">Go to the Exchange Admin Center.</span></span>

    ![Abbildung des Exchange Admin Center](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="fb628-213">Zum Erstellen einer Postfachrichtlinie für mobile Geräte klicken Sie im linken Bereich auf **Mobil** und dann auf **Postfachrichtlinien für mobile Geräte**.</span><span class="sxs-lookup"><span data-stu-id="fb628-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="fb628-214">Surface Hubs erfordern ein Konto mit einer Postfachrichtlinie für mobile Geräte, die kein Kennwort erfordert. Wenn Sie bereits über eine vorhandene Richtlinie verfügen, die dieser Anforderung entspricht, können Sie diese Richtlinie auf das Konto anwenden.</span><span class="sxs-lookup"><span data-stu-id="fb628-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="fb628-215">Führen Sie andernfalls die folgenden Schritte aus, um eine neue Richtlinie zu erstellen, die nur für Surface Hub-Gerätekonten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb628-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Abbildung der Verwendung von Exchange Admin Center zum Erstellen einer Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="fb628-217">Zum Erstellen einer neuen Postfachrichtlinie für mobile Geräte klicken Sie in den Steuerelementen oberhalb der Liste der Richtlinien auf die Schaltfläche **+** , um eine neue Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb628-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="fb628-218">Geben Sie als Namen einen Namen an, mit dem Sie diese Richtlinie von anderen Gerätekonten unterscheiden können (z. B. *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="fb628-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="fb628-219">Die Richtlinie darf nicht kennwortgeschützt sein. Stellen Sie daher sicher, dass **Kennwort anfordern** deaktiviert bleibt, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb628-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Abbildung der neuen Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="fb628-221">Nachdem Sie die neue Postfachrichtlinie für mobile Geräte erstellt haben, wechseln Sie zurück zum Exchange Admin Center. Dort wird die neue Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb628-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Bild der neuen Postfachrichtlinie für mobile Geräte im Exchange Admin Center](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="fb628-223">Zum Anwenden der ActiveSync-Richtlinie ohne Verwendung von PowerShell können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="fb628-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="fb628-224">Klicken Sie im Exchange Admin Center auf **Empfänger** &gt; **Postfächer**, und wählen Sie ein Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="fb628-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Abbildung des Exchange Admin Center](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="fb628-226">Scrollen Sie im Bereich **Details** zu **Telefon- und Sprachfunktionen**, und klicken Sie auf **Details anzeigen**, um den Bildschirm **Details des mobilen Geräts** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb628-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Abbildung von Postfachdetails](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="fb628-228">Die derzeit zugewiesene Postfachrichtlinie für mobile Geräte wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb628-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="fb628-229">Zum Ändern der Postfachrichtlinie für mobile Geräte klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="fb628-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Abbildung der derzeit zugewiesenen Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="fb628-231">Wählen Sie die entsprechende Postfachrichtlinie für mobile Geräte in der Liste aus, klicken Sie auf **OK** und dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb628-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Abbildung der Liste von Postfachrichtlinien für mobile Geräte](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="fb628-233">Konfigurieren des Kontos mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb628-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="fb628-234">Nachdem Sie mit den Onlinediensten verbunden sind, können Sie die Einrichtung des Gerätekontos abschließen.</span><span class="sxs-lookup"><span data-stu-id="fb628-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="fb628-235">Sie verwenden die E-Mail-Adresse des Gerätekontos für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="fb628-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="fb628-236">Ändern des Postfachtyps von „regulär“ in „Raum“</span><span class="sxs-lookup"><span data-stu-id="fb628-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="fb628-237">Ändern verschiedener Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fb628-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="fb628-238">Festlegen des Kennworts des Benutzerkontos auf „Läuft nie ab“.</span><span class="sxs-lookup"><span data-stu-id="fb628-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="fb628-239">Sie müssen die E-Mail-Adresse des Kontos eingeben und eine Variable mit diesem Wert erstellen:</span><span class="sxs-lookup"><span data-stu-id="fb628-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="fb628-240">Rufen Sie den Wert zum Speichern aus dem Postfach ab:</span><span class="sxs-lookup"><span data-stu-id="fb628-240">To store the value got it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="fb628-241">Drucken Sie den Wert, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="fb628-241">Print the value by running:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="fb628-242">Die richtige E-Mail-Adresse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb628-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="fb628-243">Sie müssen das Konto in ein Raumpostfach konvertieren. Führen Sie daher dies aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-243">You need to convert the account into a room mailbox, so run:</span></span>

    ```powershell
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="fb628-244">Zum Authentifizieren des Gerätekontos auf einem Surface Hub müssen Sie das Raumpostfachkonto aktivieren und ein Kennwort festlegen, damit das Gerät das Konto zum Abrufen von Besprechungsinformationen mithilfe von ActiveSync und zum Anmelden bei Skype for Business verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="fb628-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ```powershell
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="fb628-245">Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="fb628-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="fb628-246">Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb628-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="fb628-247">Jetzt müssen wir einige Eigenschaften in AD festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb628-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="fb628-248">Dazu benötigen Sie das Alias des Kontos (dies ist der Teil des Benutzerprinzipalnamens vor „@“).</span><span class="sxs-lookup"><span data-stu-id="fb628-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ```powershell
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="fb628-249">Der Benutzer muss in AD aktiviert werden, bevor er mit einem Surface Hub authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb628-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="fb628-250">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-250">Run:</span></span>

    ```powershell
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="fb628-251">Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb628-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="fb628-252">Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="fb628-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ```powershell
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="fb628-253">Aktivieren des Kontos mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fb628-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="fb628-254">Aktivieren Sie das Gerätekonto mit Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb628-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="fb628-255">Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="fb628-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="fb628-256">Sie benötigen Skype for Business Online Eigenständig Plan 2 oder höher in Ihrem O365-Plan.</span><span class="sxs-lookup"><span data-stu-id="fb628-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="fb628-257">Der Plan muss Konferenzfunktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb628-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="fb628-258">Wenn Sie eine Enterprise-VoIP (PSTN-Telefonie) mit Telefoniedienstanbietern für den Surface Hub benötigen, benötigen Sie Skype for Business Online Eigenständig, Plan 3.</span><span class="sxs-lookup"><span data-stu-id="fb628-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="fb628-259">Die Mandantenbenutzer müssen über Exchange-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="fb628-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="fb628-260">Für Ihr Surface Hub-Konto ist eine Skype for Business Online Standalone Plan 2- oder Skype for Business Online Standalone Plan 3-Lizenz erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb628-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="fb628-261">Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.</span><span class="sxs-lookup"><span data-stu-id="fb628-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="fb628-262">Rufen Sie den Surface Hub-Kontoregistrierungspool ab.</span><span class="sxs-lookup"><span data-stu-id="fb628-262">Retrieve your Surface Hub account Registrar Pool.</span></span>

   <span data-ttu-id="fb628-263">Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:</span><span class="sxs-lookup"><span data-stu-id="fb628-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

   ```PowerShell
   Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
   ```

3. <span data-ttu-id="fb628-264">Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="fb628-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```