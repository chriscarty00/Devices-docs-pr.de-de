---
title: Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2
description: Dieser Artikel enthält Empfehlungen, um die beste Erfahrung bei der Verwendung eines personalisierten Touch- und Stiftcomputers mit großem Bildschirm sicherzustellen.
keywords: Surface Hub, Windows 10, Desktop, Installation, Konfiguration
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393588"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="3980c-104">Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="3980c-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="3980c-105">Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 Pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um Apps und Einstellungen auf Ihrem Surface Hub 2 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="3980c-106">Diese Schritte werden empfohlen, um die beste Erfahrung bei der Verwendung dieses personalisierten Touch- und Stiftcomputers mit großem Bildschirm zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="3980c-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="3980c-107">Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3980c-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="3980c-108">Konfigurieren von Systemeinstellungen</span><span class="sxs-lookup"><span data-stu-id="3980c-108">Configure system settings</span></span>

1. <span data-ttu-id="3980c-109">Melden Sie sich mit einem Konto an, das über lokale Administratorrechte auf dem Gerät verfügt.</span><span class="sxs-lookup"><span data-stu-id="3980c-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="3980c-110">Auf geräten, die azure AD beigetreten sind, wird der Benutzer, der den Azure AD-Beitritt ausführt, automatisch der lokalen Administratorgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3980c-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="3980c-111">Globale Azure AD-Administratoren und Azure AD-Geräteadministratoren <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> sind auch lokale </a> Administratoren.</span><span class="sxs-lookup"><span data-stu-id="3980c-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="3980c-112">Sie können an einer **Eingabeaufforderung** Netzwerkadministratoren für lokale Gruppen eingeben, um die Konten mit lokalen Administratorrechten auflisten zu können.</span><span class="sxs-lookup"><span data-stu-id="3980c-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="3980c-113">Benennen Sie das Gerät mithilfe eines Anzeigenamens um, z. B. **benutzername-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="3980c-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="3980c-114">Wählen **Sie Einstellungen**  >  **starten**  >  **Konten**  >  **synchronisieren Ihre Einstellungen aus,** und deaktivieren Sie die **Synchronisierungseinstellungen.**</span><span class="sxs-lookup"><span data-stu-id="3980c-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="3980c-115">Die hier verwendeten Einstellungen sollen die beste Toucherfahrung für große Bildschirme ermöglichen, daher möchten Sie möglicherweise keine anderen Geräte synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="3980c-116">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="3980c-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="3980c-117">Aktivieren der Touchtastatur und des Touchpads</span><span class="sxs-lookup"><span data-stu-id="3980c-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="3980c-118">Wählen **Sie**  >  **Starteinstellungen**  >  **Geräte**  >  **eingeben aus,** und aktivieren Sie Touchtastatur anzeigen, wenn sie sich nicht im **Tablet-Modus** befindet und keine Tastatur angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="3980c-119">Tippen und halten Oder klicken Sie mit der rechten Maustaste auf die Taskleiste, und wählen Sie dann Touchtastaturschaltfläche **anzeigen** und **Touchpad anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="3980c-120">Die Touchtastatur ist hilfreich für direkte Benutzereingaben, und das virtuelle Touchpad hilft bei präzisen Auswahlen, zeigenden Bildschirmtipps oder als Alternative zum Tippen und Halten für rechtsklicken.</span><span class="sxs-lookup"><span data-stu-id="3980c-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="3980c-121">Nachfolgend sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3980c-121">See the following example.</span></span>

      ![Toucheinstellungen](images/touch.png)

3. <span data-ttu-id="3980c-123">Konfigurieren Sie die Touchtastatur auf QWERTY und unverankert.</span><span class="sxs-lookup"><span data-stu-id="3980c-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="3980c-124">Wählen Sie **das Tastatursymbol** auf der Taskleiste aus, um die Touchtastatur zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="3980c-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="3980c-125">Wählen Sie auf der Touchtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3980c-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="3980c-126">Wählen Sie den nächsten bis letzten Tastaturtyp in der oberen Zeile aus, um QWERTY zu aktivieren, und die letzte Option in der zweiten Zeile, um das Unverankerte zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="3980c-127">Weitere Informationen finden Sie in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="3980c-127">See the following examples.</span></span>

       ![Tastatureinstellungen](images/kbd.png)
 
4. <span data-ttu-id="3980c-129">Konfigurieren Sie die Softtastatureinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3980c-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="3980c-130">Wählen Sie **das Symbol** Einstellungen auf der Touchtastatur aus, oder suchen Sie nach **Eingabeeinstellungen,** und öffnen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="3980c-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![Softtastatureinstellungen](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="3980c-132">Aktivieren Sie alle Optionen unter Rechtschreib-, Eingabe- und Touchtastatur.</span><span class="sxs-lookup"><span data-stu-id="3980c-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="3980c-133">Das folgende Beispiel zeigt das Trackpad, das zum Navigieren und Auswählen von Optionen hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="3980c-134">Die Bildschirmtastatur wird zum Durchsuchen des Microsoft Store verwendet:</span><span class="sxs-lookup"><span data-stu-id="3980c-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Verwenden des Trackpads](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="3980c-136">Konfigurieren Bluetooth Tastatur und Maus (optional)</span><span class="sxs-lookup"><span data-stu-id="3980c-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="3980c-137">Verbinden Sie Tastatur und Maus, wenn Sie das Gerät als primäres Windows-Gerät verwenden oder es häufig zur Eingabe oder Genauigkeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="3980c-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="3980c-138">Wenn sich Ihr Surface Hub-Gerät in der Nähe eines PCs befindet, können Sie Mouse ohne Rahmen verwenden, um nahtlos zwischen Surface Hub und <a href="https://aka.ms/mm" target="_blank"> </a> PC zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3980c-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="3980c-139">Weitere Informationen finden Sie unter <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span><span class="sxs-lookup"><span data-stu-id="3980c-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="3980c-140">Beispiel für das Taskleistenlayout</span><span class="sxs-lookup"><span data-stu-id="3980c-140">Example of Taskbar layout</span></span>

<span data-ttu-id="3980c-141">Nachdem Sie die folgenden Schritte zum Einrichten/Konfigurieren Ihres Surface Hub 2 für Windows 10 Professional oder Enterprise abgeschlossen haben, wird empfohlen, die am häufigsten verwendeten Anwendungen an die Taskleiste anheften zu können, um die einzelnen Anwendungen schnell und einfach zu starten.</span><span class="sxs-lookup"><span data-stu-id="3980c-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="3980c-142">Im Folgenden finden Sie ein Beispiel dafür, wie Ihre Taskleiste aussehen könnte:</span><span class="sxs-lookup"><span data-stu-id="3980c-142">Below is an example of what your taskbar could look like:</span></span>

 ![Taskleistenlayout](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="3980c-144">Aktualisieren installierter Apps</span><span class="sxs-lookup"><span data-stu-id="3980c-144">Update installed apps</span></span>

<span data-ttu-id="3980c-145">So aktualisieren Sie alle installierten Store-Apps:</span><span class="sxs-lookup"><span data-stu-id="3980c-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="3980c-146">Öffnen Sie die Microsoft Store-App, und wählen Sie die **Option Weitere** Auslassungspunkte in der oberen rechten Ecke aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="3980c-147">Wählen Sie **Downloads und Updates aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="3980c-148">Wählen Sie **Updates erhalten aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="3980c-149">Überprüfen und Installieren aller Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="3980c-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="3980c-150">Nach der Migration zu Windows 10 Professional oder Windows 10 Enterprise stehen Möglicherweise Wartungs- und Funktionsupdates zur Installation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3980c-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="3980c-151">Wechseln Sie **zu Einstellungen**Update & Security >, und wählen Sie dann  >  \*\*\*\* Nach Updates **suchen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="3980c-152">Wenn Updates verfügbar sind, installieren Sie sie, starten Sie den Vorgang neu, und wiederholen Sie den Vorgang, bis die folgende Benachrichtigung angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="3980c-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Benachrichtigung "Sie sind auf dem neuesten Stand" für Windows Update](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="3980c-154">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3980c-154">OneDrive for Business</span></span>

<span data-ttu-id="3980c-155">Verwenden Sie OneDrive for Business zum einfachen Freigeben von Tools, Protokollen und anderen Dateien <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> zwischen allen Arbeitsgeräten.</span><span class="sxs-lookup"><span data-stu-id="3980c-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="3980c-156">Mit OneDrive können Sie Ihre Arbeitsdateien zwischen Ihren Laptops, Surface Hub Desktop und Ihren von Intune verwalteten mobilen Geräten freigeben.</span><span class="sxs-lookup"><span data-stu-id="3980c-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="3980c-157">Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3980c-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="3980c-158">Wenn Sie die Größe der Surface Hub-SSD (128 GB) bedenken, müssen Sie beim Konfigurieren von OneDrive auf Ihrem Surface Hub Desktop-Gerät sicherstellen, dass die Standardkonfiguration die Onlinespeicherung der Dateien und das Herunterladen von Dateien während der Verwendung ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="3980c-159">Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung Dateien **bei** Bedarf auf Speicherplatz sparen und Dateien während der Verwendung **herunter.**</span><span class="sxs-lookup"><span data-stu-id="3980c-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="3980c-160">Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="3980c-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![#A0](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="3980c-162">Sie können diese Schritte auch wiederholen, um ein persönliches OneDrive zu konfigurieren, aber achten Sie darauf, speicherplatzsparend zu sein und dateien nur nach Bedarf herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3980c-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="3980c-163">SharePoint und Teams</span><span class="sxs-lookup"><span data-stu-id="3980c-163">SharePoint and Teams</span></span>

<span data-ttu-id="3980c-164">SharePoint- und #A0 können mithilfe des #A1 auch lokal mit Ihren Desktopgeräten synchronisiert werden, z. B. Laptops und Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="3980c-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="3980c-165">So synchronisieren Sie interne Unternehmensdateien mit Ihrem lokalen Laufwerk mit der OneDrive-Synchronisierungs-App:</span><span class="sxs-lookup"><span data-stu-id="3980c-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="3980c-166">Wechseln Sie zu einer SharePoint-Website, und navigieren Sie zum Dokumentverzeichnis auf oberster Ebene für Dateien, die Sie auf Ihrem lokalen Gerät anzeigen oder bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3980c-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="3980c-167">Wählen Sie auf der **Schaltfläche Synchronisieren** oben im SharePoint-Menüband aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="3980c-168">Wählen Sie **im Popup** Öffnen aus Diese **Website versucht, Microsoft OneDrive zu öffnen.**</span><span class="sxs-lookup"><span data-stu-id="3980c-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="3980c-169">Vergewissern Sie sich, dass die #A0 mit Ihrem lokalen Laufwerk synchronisiert werden, indem Sie das #A1 unten rechts auf der Taskleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="3980c-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="3980c-170">Überprüfen Sie, ob die Konfiguration so festgelegt ist, dass die Dateien online bleiben, und laden Sie die Dateien nur so herunter, wie Sie sie verwenden:</span><span class="sxs-lookup"><span data-stu-id="3980c-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="3980c-171">Öffnen Sie den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="3980c-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="3980c-172">Navigieren Sie zu Und klicken Sie mit der rechten Maustaste auf Ihren #A0 z. B. \*\*Contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="3980c-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="3980c-173">Wählen **Sie Speicherplatz frei.**</span><span class="sxs-lookup"><span data-stu-id="3980c-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="3980c-174">In der Spalte Status wird der Status von Dateien und Ordnern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3980c-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="3980c-175">Weitere Informationen finden Sie unter <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client </a> .</span><span class="sxs-lookup"><span data-stu-id="3980c-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="3980c-176">Teams Channel-Dateien werden auf SharePoint-Websites mit derselben SharePoint-Dokumentfunktionalität gespeichert, einschließlich Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten.</span><span class="sxs-lookup"><span data-stu-id="3980c-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="3980c-177">So synchronisieren Sie Teams Channel-Dateien:</span><span class="sxs-lookup"><span data-stu-id="3980c-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="3980c-178">Navigieren Sie zum Teams-Kanal von Interesse, und wählen **Sie** oben die Registerkarte Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="3980c-179">Wählen Sie dann **Synchronisieren aus.** Die Dateien beginnen mit der Synchronisierung und werden im Datei-Explorer unter \*\*Desktop \ Contoso \ angezeigt. \<name of the Teams Channel\> \*\*</span><span class="sxs-lookup"><span data-stu-id="3980c-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="3980c-180">Verwenden Sie das gleiche Verfahren, das Sie für die Synchronisierung von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern und sie nur herunterzuladen, wenn Sie sie verwenden, indem Sie im Namen des Teams-Kanals auf Datei-Explorer tippen und diese halten oder mit der rechten Maustaste klicken und dann **Speicherplatz**freigeben auswählen.</span><span class="sxs-lookup"><span data-stu-id="3980c-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="3980c-181">Surface Hub-Stifteinstellungen</span><span class="sxs-lookup"><span data-stu-id="3980c-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="3980c-182">Koppeln Bluetooth Surface Hub Pen</span><span class="sxs-lookup"><span data-stu-id="3980c-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="3980c-183">Koppeln Sie den Stift, um die Stiftfirmware auf dem neuesten Stand zu halten, legen Sie die Stiftverknüpfungen ein und erhalten Sie Akkuladeinformationen auf der Seite Bluetooth Geräteeinstellungen oder in der Surface-App:</span><span class="sxs-lookup"><span data-stu-id="3980c-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="3980c-184">Wählen **Sie**  >  **Starteinstellungen**  >  **Geräte aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="3980c-185">Wählen **Sie Bluetooth oder ein anderes Gerät hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="3980c-186">Wählen **Sie Bluetooth**aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="3980c-187">Entfernen Sie die Stift-Tail-Taste, und wackeln Sie, um die Akkuverbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="3980c-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="3980c-188">Setzen Sie die Kappe wieder ein, und drücken Und halten Sie die Kappe, bis die Kopplungs-LED blinkt.</span><span class="sxs-lookup"><span data-stu-id="3980c-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="3980c-189">Wählen Sie unter Surface Hub Bluetooth Surface **Hub 2 Pen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="3980c-190">Schließen Sie den Kopplungsvorgang ab.</span><span class="sxs-lookup"><span data-stu-id="3980c-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="3980c-191">Wenn die Kopplung nicht erfolgreich ist, können Sie versuchen, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="3980c-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="3980c-192">Wenn dies nicht funktioniert, können Sie testen, ob der Akku geladen ist, indem Sie überprüfen, ob der Stift in der Whiteboard-Anwendung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3980c-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="3980c-193">Wenn nicht, ersetzen Sie den Akku, und versuchen Sie dann, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="3980c-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="3980c-194">Starten Sie das Gerät bei Bedarf neu, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="3980c-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="3980c-195">**Festlegen von Stiftverknüpfungen** Der Surface Hub-Stift verfügt über eine Verknüpfungsschaltfläche, die manchmal als "Tail Click" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="3980c-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="3980c-196">Zum Konfigurieren von Verknüpfungen müssen Sie den Stift zuerst koppeln, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3980c-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="3980c-197">Suchen Sie nach Stift, und wählen **& Windows Ink-Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="3980c-198">Wählen Sie am unteren Rand der Seite die Option Stiftverknüpfungen aus, die das Dialogfeld öffnen, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3980c-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Stiftverknüpfungen](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="3980c-200">Kamerakonfiguration</span><span class="sxs-lookup"><span data-stu-id="3980c-200">Camera configuration</span></span>

<span data-ttu-id="3980c-201">Sie können die Kamera oben oder auf beiden Seiten des Geräts einhängen.</span><span class="sxs-lookup"><span data-stu-id="3980c-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="3980c-202">Stellen Sie die Kamera an einer Position ein, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktopständer anstelle eines Einkaufswagens verwenden oder sich in der Nähe des Hubs befinden.</span><span class="sxs-lookup"><span data-stu-id="3980c-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="3980c-203">Die Kamera wird nicht automatisch gedreht, daher benötigen Sie eine 2mm-Hextaste, um die Kamera manuell zu drehen.</span><span class="sxs-lookup"><span data-stu-id="3980c-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="3980c-204">Weitere Informationen zum seitlichen Einhängen der Kamera und zum manuellen Drehen der Kamera finden Sie unter Ausrichtung der <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S-Kameralinse. </a></span><span class="sxs-lookup"><span data-stu-id="3980c-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="3980c-205">Windows Hello-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3980c-205">Windows Hello configuration</span></span>

<span data-ttu-id="3980c-206">Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen.</span><span class="sxs-lookup"><span data-stu-id="3980c-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="3980c-207">Das Surface Hub 2 Fingerprint Reader-Zubehör kann an einen beliebigen USB-C-Port auf dem Gerät angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3980c-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="3980c-208">Informationen zum Bestellen eines Surface Hub 2-Fingerabdrucklesers oder zum Anzeigen technischer Spezifikationen finden Sie unter (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="3980c-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="3980c-209">Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie \*\*\*\*  >  **Starteinstellungen**  >  **Konten**  >  **Anmeldeoptionen**Windows Hello Fingerprint aus,  >  \*\*\*\* um Ihren Fingerabdruck zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="3980c-210">Verwenden Sie ein Windows Hello-zertifiziertes Gerät für die Gesichtserkennung.</span><span class="sxs-lookup"><span data-stu-id="3980c-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="3980c-211">Die Surface Hub 2S-Kamera unterstützt keine Windows Hello-Gesichtserkennung.</span><span class="sxs-lookup"><span data-stu-id="3980c-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="3980c-212">Aktivieren eines Verknüpfungssymbols für den Sperrbildschirm auf der Taskleiste</span><span class="sxs-lookup"><span data-stu-id="3980c-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="3980c-213">So fügen Sie der Taskleiste ein Symbol hinzu, das die Sperre mit einem Touchscreen aktiviert, ähnlich der Windows-L-Tastenkombination:</span><span class="sxs-lookup"><span data-stu-id="3980c-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="3980c-214">Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen **Sie Neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**Weiter  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="3980c-215">Geben Sie einen Namen für die Verknüpfung an, z. **B. Pc sperren,** und wählen Sie dann **Fertig stellen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="3980c-216">Klicken oder tippen Sie mit der rechten Maustaste auf die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="3980c-217">Geben Sie **auf** der Registerkarte Verknüpfung im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll,LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="3980c-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="3980c-218">Wählen Sie **die Schaltfläche Symbol** ändern aus, navigieren Sie zu **C:\Windows\System32\imageres.dll** und wählen Sie ein zu verwendende Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="3980c-219">Siehe hierzu das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3980c-219">See the following example:</span></span>

    ![Auswählen eines Symbols](images/lock.png)
    
1.  <span data-ttu-id="3980c-221">Wählen **Sie OK** aus, um die Verknüpfung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3980c-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="3980c-222">Klicken oder tippen Sie mit der rechten Maustaste auf die Verknüpfung, und wählen **Sie An Taskleiste anheften aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="3980c-223">Nachdem Sie die Sperrverknüpfung an die Taskleiste angeheftet haben, können Sie sie auf dem Desktop löschen.</span><span class="sxs-lookup"><span data-stu-id="3980c-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="3980c-224">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3980c-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="3980c-225">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="3980c-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="3980c-226">So installieren Sie das Microsoft Whiteboard:</span><span class="sxs-lookup"><span data-stu-id="3980c-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="3980c-227">Wählen Sie das **Symbol Windows Ink Workspace** unten rechts auf der Taskleiste aus, und laden Sie **Whiteboard herunter.**</span><span class="sxs-lookup"><span data-stu-id="3980c-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Freihandarbeitsbereich](images/ink.png) 

<span data-ttu-id="3980c-229">Alternativ können Sie Whiteboard aus dem Microsoft Store installieren:</span><span class="sxs-lookup"><span data-stu-id="3980c-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="3980c-230">Öffnen Sie die Microsoft Store-App, und suchen Sie **nach Whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="3980c-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="3980c-231">Wählen **Sie Nein,** dank der Anmeldung und Verwendung auf allen Geräten.</span><span class="sxs-lookup"><span data-stu-id="3980c-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="3980c-232">Pin Whiteboard an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="3980c-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="3980c-233">Surface-App</span><span class="sxs-lookup"><span data-stu-id="3980c-233">Surface app</span></span>

1. <span data-ttu-id="3980c-234">Suchen Sie im Microsoft Store nach **Surface**.</span><span class="sxs-lookup"><span data-stu-id="3980c-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="3980c-235">Legen Sie **den Filter Verfügbar** auf Alle Geräte **.**</span><span class="sxs-lookup"><span data-stu-id="3980c-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="3980c-236">Installieren Sie die **Surface-App.**</span><span class="sxs-lookup"><span data-stu-id="3980c-236">Install the **Surface** app.</span></span> <span data-ttu-id="3980c-237">Dies sollte die erste aufgeführte App sein.</span><span class="sxs-lookup"><span data-stu-id="3980c-237">This should be the first app listed.</span></span> <span data-ttu-id="3980c-238">Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die App zu installieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="3980c-239">Heften Sie **die Surface-App** an die Taskleiste an.</span><span class="sxs-lookup"><span data-stu-id="3980c-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="3980c-240">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="3980c-240">Snip & Sketch</span></span>

1. <span data-ttu-id="3980c-241">Öffnen Sie **die Snip-&** Sketch-App, undheften Sie sie an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="3980c-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="3980c-242">Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="3980c-243">Aktivieren **Sie unter**Einstellungen die Option Automatische Kopie in die **Zwischenablage,** **Snips**speichern und **Mehrere Fenster** (optional).</span><span class="sxs-lookup"><span data-stu-id="3980c-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="3980c-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="3980c-244">Microsoft Office</span></span>

1. <span data-ttu-id="3980c-245">Öffnen Sie das <a href="https://portal.office.com/account#installs" target="_blank"> Office-Portal, </a> und installieren Sie die gewünschten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3980c-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="3980c-246">Heften Sie die gewünschten Office-Anwendungen an die Taskleiste an.</span><span class="sxs-lookup"><span data-stu-id="3980c-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="3980c-247">Wenn Outlook installiert ist, stellen Sie sicher, dass Outlook OST nur den Cache der letzten zwei Wochen speichert.</span><span class="sxs-lookup"><span data-stu-id="3980c-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="3980c-248">Dadurch werden die Datenträgernutzung und die Einrichtungszeit deutlich reduziert.</span><span class="sxs-lookup"><span data-stu-id="3980c-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="3980c-249">Wählen **Sie**  >  **Dateikontoeinstellungen aus,** und wählen Sie Ihr Konto aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="3980c-250">Wählen **Sie Ändern** aus, und legen Sie den Schieberegler für den **Exchange-Cache-Modus auf** 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="3980c-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="3980c-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3980c-251">Microsoft Teams</span></span>

1. <span data-ttu-id="3980c-252">Herunterladen und Installieren <a href="https://teams.microsoft.com/downloads" target="_blank"> von Microsoft Teams </a> .</span><span class="sxs-lookup"><span data-stu-id="3980c-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="3980c-253">Konfigurieren Sie Einstellungen für die Anwendung automatischen Start (optional).</span><span class="sxs-lookup"><span data-stu-id="3980c-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="3980c-254">Heften Sie Teams an die Taskleiste an.</span><span class="sxs-lookup"><span data-stu-id="3980c-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="3980c-255">Erwägen Sie die Reduzierung von Teams-Benachrichtigungen auf dem Gerät, um Ablenkungen zu vermeiden (optional).</span><span class="sxs-lookup"><span data-stu-id="3980c-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams-Benachrichtigungen](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="3980c-257">Verbinden der App</span><span class="sxs-lookup"><span data-stu-id="3980c-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3980c-258">In Windows 10, Version 2004 und höher, ist die Connect-App für die drahtlose Projektion mit Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3980c-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="3980c-259">Wenn Sie Windows Version 2004 oder höher installiert (oder auf diese aktualisiert haben), wird möglicherweise Folgendes auf dem Bildschirm Projecting to this PC in den Einstellungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3980c-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Project to this PC](images/sh2-project.png) 


1. <span data-ttu-id="3980c-261">Wenn Sie die App auf der Einstellungsseite "Auf diesen PC projiziert" installieren möchten, wählen Sie Optionale **Features**Hinzufügen eines Features aus, und installieren Sie dann  >  \*\*\*\* die **App "Drahtlosanzeige".**</span><span class="sxs-lookup"><span data-stu-id="3980c-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="3980c-262">Wählen Sie unter Einige Windows- und Android-Geräte auf diesen PC projiziert werden, wenn Sie sagen, es **ist OK,** wählen Sie:</span><span class="sxs-lookup"><span data-stu-id="3980c-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="3980c-263">**Überall verfügbar,** wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="3980c-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="3980c-264">Wählen Sie andernfalls **Überall verfügbar in sicheren Netzwerken aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="3980c-265">Wählen **Sie unter Projekt auf diesen PC fragen**die Option Nur **erstes Mal aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="3980c-266">Wählen **Sie unter PIN für die Kopplung benötigen**die Option Nie **aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="3980c-267">Suchen Sie nach Connect, um die App zu starten und an die Taskleiste **anheften.**</span><span class="sxs-lookup"><span data-stu-id="3980c-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="3980c-268">Öffnen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="3980c-268">Open the app.</span></span> <span data-ttu-id="3980c-269">Während die App geöffnet ist, klicken Sie mit der rechten Maustaste auf das Symbol App verbinden auf der Taskleiste, und wählen Sie **Pin an Taskleiste aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="3980c-270">Schließen Sie dann die Connect-App.</span><span class="sxs-lookup"><span data-stu-id="3980c-270">Then close the Connect app.</span></span> <span data-ttu-id="3980c-271">**Project to this PC** might not work unless the app has been run at least once.</span><span class="sxs-lookup"><span data-stu-id="3980c-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="3980c-272">Empfohlene Konfiguration, wenn nicht im Unternehmensnetzwerk:</span><span class="sxs-lookup"><span data-stu-id="3980c-272">Recommended configuration when not on the corporate network:</span></span>

![Einstellungen zu Hause](images/project1.png)

<span data-ttu-id="3980c-274">Empfohlene Konfiguration im Unternehmensnetzwerk:</span><span class="sxs-lookup"><span data-stu-id="3980c-274">Recommended configuration on the corporate network:</span></span>

![Einstellungen bei der Arbeit](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="3980c-276">Ihr Smartphone</span><span class="sxs-lookup"><span data-stu-id="3980c-276">Your Phone</span></span>

<span data-ttu-id="3980c-277">Die **App "Ihr Telefon"** wird standardmäßig unter Windows 10 installiert.</span><span class="sxs-lookup"><span data-stu-id="3980c-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="3980c-278">Wenn sie nicht vorhanden ist, können Sie sie auch aus dem Windows Store installieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="3980c-279">Weitere Informationen zum Einrichten der App finden Sie unter Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> zwischen Ihrem PC und Ihrem </a> Smartphone.</span><span class="sxs-lookup"><span data-stu-id="3980c-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="3980c-280">Weitere Informationen finden Sie unter Beheben häufiger Probleme mit Der App Für Ihr <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Telefon unter Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="3980c-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="3980c-281">Ausgefallene Zonen</span><span class="sxs-lookup"><span data-stu-id="3980c-281">Fancy Zones</span></span>


<span data-ttu-id="3980c-282">**Fancy Zones** ist Teil einer Sammlung von Tools namens <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="3980c-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="3980c-283">Es ist eine hervorragende Möglichkeit, die Bildschirmfläche auf einem Surface Hub 2 zu nutzen, indem Sie feste Layouts auf Ihrem Display definieren können ("Zonen"), und wählen Sie dann aus, welche App dann in jeder Zone ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3980c-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="3980c-284">Das [PowerToys-Wiki](https://github.com/microsoft/PowerToys/wiki) enthält Anweisungen zum Verwenden und Anpassen der einzelnen Tools, einschließlich [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="3980c-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="3980c-285">Auf einer hohen Ebene – nach der Installation von PowerToys können Sie ein benutzerdefiniertes Layout auswählen oder erstellen und dann die Umschalttaste gedrückt halten und Tastaturtasten ziehen oder verwenden, um eine laufende App in bestimmte Zonen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="3980c-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="3980c-286">Die Verwendung Bluetooth oder USB-Tastatur und -Maus hilft dabei, oder Sie können die Bildschirmtastatur und das Touchpad verwenden.</span><span class="sxs-lookup"><span data-stu-id="3980c-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="3980c-287">Tipps für Power toys</span><span class="sxs-lookup"><span data-stu-id="3980c-287">Power toys tips</span></span>**
- <span data-ttu-id="3980c-288">Um E-Mail-Benachrichtigungen über PowerToys-Releaseupdates auf GitHub zu erhalten, klicken Sie oben auf der Seite auf die Schaltfläche ["Registrieren".](https://github.com/microsoft/PowerToys/releases)</span><span class="sxs-lookup"><span data-stu-id="3980c-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="3980c-289">Sobald PowerToys installiert ist, können Sie Windows-Benachrichtigungen empfangen und/oder die neuesten Updates herunterladen und installieren, indem Sie die PowerToys-Einstellungen **konfigurieren,** um Updates automatisch auf herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3980c-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="3980c-290">Um zu den PowerToys-Einstellungen zu wechseln, wählen Sie auf der Taskleiste das Nach oben karat **Ausführen** von Apps aus, und klicken oder drücken Sie mit der rechten Maustaste das PowerToys-Symbol, bis das Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3980c-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="3980c-291">Wählen Sie "Einstellungen" aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-291">Select “Settings”.</span></span>
- <span data-ttu-id="3980c-292">Aktivieren Sie am unteren Rand der Seite PowerToys-Einstellungen updates **automatisch** herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3980c-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="3980c-293">Wenn ein Update veröffentlicht wurde, wird eine Windows-Benachrichtigung angezeigt, mit der Sie die Möglichkeit erhalten, wann das Update installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3980c-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="3980c-294">Edge Chromium-Browser</span><span class="sxs-lookup"><span data-stu-id="3980c-294">Edge Chromium browser</span></span>

<span data-ttu-id="3980c-295">Laden Sie den neuen <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium-Browser herunter, und installieren Sie </a> sie.</span><span class="sxs-lookup"><span data-stu-id="3980c-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="3980c-296">Surface Hub Hardware Diagnostic Tool</span><span class="sxs-lookup"><span data-stu-id="3980c-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="3980c-297">Das <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic </a> Tool, das kostenlos im Microsoft Store verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="3980c-298">Das Tool soll Ihnen dabei helfen, sicherzustellen, dass Ihr Surface Hub optimal ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="3980c-299">Es enthält Tests, um festzustellen, ob Ihre Firmware auf dem neuesten Stand ist und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="3980c-300">Mit interaktiven Tests können Sie bestätigen, dass wesentliche Funktionen wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="3980c-301">Wenn Probleme auftreten, können Ergebnisse gespeichert und für das Surface Hub-Support-Team freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3980c-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="3980c-302">Klicken Sie auf den Link, um ihn aus dem Microsoft Store zu installieren, undheften Sie die Anwendung dann an Die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="3980c-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="3980c-303">Zusätzliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="3980c-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="3980c-304">Stiftschweif auswählen, um Whiteboard zu starten</span><span class="sxs-lookup"><span data-stu-id="3980c-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="3980c-305">Suchen Sie **nach Stift,** und wählen **& Windows Ink-Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="3980c-306">Klicken Sie am unteren Rand der Seite unter **Stiftverknüpfungen** **auf** **Microsoft Whiteboard auswählen.**</span><span class="sxs-lookup"><span data-stu-id="3980c-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="3980c-307">Energieverwaltung</span><span class="sxs-lookup"><span data-stu-id="3980c-307">Power management</span></span>

<span data-ttu-id="3980c-308">Es stehen mehrere Energieeinstellungen zur Verfügung, um die bestmögliche Erfahrung mit Windows 10 Pro oder Enterprise auf Surface Hub 2 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3980c-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="3980c-309">Dies umfasst Bildschirm- und PC-Timeouts und die Interaktion mit der integrierten Erkennung von Anwesenheitseinstellungen (Doppler), dem Bildschirmschoner und Kennwortschutz und anschließend gegebenenfalls, wie Gruppenrichtlinieneinstellungen für Laptop-/Desktopbenutzer umgepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3980c-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="3980c-310">Windows 10 Pro oder Enterprise auf Surface Hub 2 verhindert, dass der Bildschirm mit Touch-, Maus- und Tastaturaktionen sowie der integrierten Erkennung von Personenbelegung (Doppler) in den Ruhezustand geht.</span><span class="sxs-lookup"><span data-stu-id="3980c-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="3980c-311">Die Erkennung von Personenbelegung ist standardmäßig aktiviert, kann jedoch bei Bedarf in UEFI deaktiviert werden, indem die Geräteoption im Surface UEFI Configurator-Tool entweder als Teil der anfänglichen Migration oder durch Erstellen und Anwenden eines späteren UEFI-Konfigurationspakets umgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="3980c-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="3980c-312">Energieverwaltung: Einstellungen für bildschirm- und PC-Ruhezustand</span><span class="sxs-lookup"><span data-stu-id="3980c-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="3980c-313">Wählen **Sie**  >  **Starteinstellungen**  >  **System**  >  **power & sleep aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="3980c-314">Legen Sie den Schieberegler für den Energiemodus auf **Beste Leistung .**</span><span class="sxs-lookup"><span data-stu-id="3980c-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="3980c-315">Konfigurieren Sie Bildschirm- und Ruhezustandswerte nach Ihren Vorstellungen, während gleichzeitig die Erkennung von Doppler-Anwesenheitserkennungen verwendet wird, die das Gerät aufweckt, wenn Bewegungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="3980c-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="3980c-316">Daher wird empfohlen, bildschirm nach **2** Stunden und den PC nach 4 Stunden auf Deaktivieren **zu setzen.**</span><span class="sxs-lookup"><span data-stu-id="3980c-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="3980c-317">Energieverwaltung: Bildschirmschoner</span><span class="sxs-lookup"><span data-stu-id="3980c-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="3980c-318">Suchen Sie **nach Sperrbildschirm,** und öffnen Sie **Sperrbildschirmeinstellungen.**</span><span class="sxs-lookup"><span data-stu-id="3980c-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="3980c-319">Konfigurieren **Sie Bildschirmtimeouteinstellungen** und **Bildschirmschonereinstellungen** nach Ihren Wünschen.</span><span class="sxs-lookup"><span data-stu-id="3980c-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="3980c-320">Empfohlene Standardwerte sind:</span><span class="sxs-lookup"><span data-stu-id="3980c-320">Recommended default values are:</span></span>

   - <span data-ttu-id="3980c-321">Bildschirmschoner für (Keine) oder einen Bildschirmschoner Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="3980c-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="3980c-322">Wartezeit bis zu 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="3980c-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="3980c-323">Zeigen Sie beim Fortsetzen den Anmeldebildschirm an.</span><span class="sxs-lookup"><span data-stu-id="3980c-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="3980c-324">Energieverwaltung: Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3980c-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="3980c-325">Bevor Sie das folgende Verfahren ausführen, sollten Sie bei Ihrer IT-Abteilung nach Genehmigung suchen, um ein Surface Hub 2S-Gerät von der globalen Energieverwaltungsrichtlinie auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="3980c-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="3980c-326">Einige Energieverwaltungseinstellungen können die Anwesenheitserkennungsfunktion deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3980c-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="3980c-327">Suchen Sie **nach Software Center,** und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="3980c-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="3980c-328">Wählen Sie **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-328">Select **Options**.</span></span>

3. <span data-ttu-id="3980c-329">Erweitern Sie **die Energieverwaltung,** und wählen Sie Energieeinstellungen aus meiner IT-Abteilung nicht auf **diesen Computer anwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Softwareeinstellungen](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="3980c-331">Speicheroptimierung</span><span class="sxs-lookup"><span data-stu-id="3980c-331">Storage Sense</span></span>

<span data-ttu-id="3980c-332">Der Surface Hub 2 verfügt über eine 128-GB-SSD für lokalen Speicher. Daher ist es erforderlich, die Verwendung von Speichereinsparungen während der normalen Nutzung zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3980c-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="3980c-333">So konfigurieren Sie Speichersinn:</span><span class="sxs-lookup"><span data-stu-id="3980c-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="3980c-334">Suchen Sie **nach Speichereinstellungen**, die unter **Systemeinstellungen gefunden werden.**</span><span class="sxs-lookup"><span data-stu-id="3980c-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="3980c-335">Wählen **Sie unter Einstellungen**die Option **Speichersinn aktivieren aus,** um die Seite **Speichereinstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3980c-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="3980c-336">Aktivieren Sie Speichersinn auf **Ein.**</span><span class="sxs-lookup"><span data-stu-id="3980c-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="3980c-337">Wählen **Sie Speichersinn konfigurieren aus, oder führen** Sie ihn jetzt aus, und konfigurieren Sie die Einstellungen so, dass Dateien so weit wie möglich online bleiben (aufgrund des begrenzten Speicherplatzes auf dem Laufwerk).</span><span class="sxs-lookup"><span data-stu-id="3980c-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="3980c-338">Empfohlene Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3980c-338">Recommended settings:</span></span>

- <span data-ttu-id="3980c-339">Führen Sie Speichersinn = jeden Tag aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="3980c-340">Löschen temporärer Dateien, die meine Apps nicht verwenden = Alle 14 Tage (mindestens).</span><span class="sxs-lookup"><span data-stu-id="3980c-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="3980c-341">Löschen Sie Dateien in meinem Downloadordner, wenn sie seit mehr als 30 Tagen dort sind.</span><span class="sxs-lookup"><span data-stu-id="3980c-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="3980c-342">OneDrive: Inhalte werden nur online verfügbar, wenn sie nicht länger als = 30 Tage geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="3980c-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="3980c-343">Tabletmodus</span><span class="sxs-lookup"><span data-stu-id="3980c-343">Tablet mode</span></span>

<span data-ttu-id="3980c-344">Aktivieren Sie den Tablet-Modus, wenn dies für Barrierefreiheitsanforderungen gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="3980c-345">Soundeinstellungen</span><span class="sxs-lookup"><span data-stu-id="3980c-345">Sound settings</span></span>

1. <span data-ttu-id="3980c-346">Suchen Sie nach **Sounds-Einstellungen,** und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="3980c-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="3980c-347">Wählen **Sie rechts die Soundsteuerung** aus, und wählen Sie die Registerkarte **Sounds** aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="3980c-348">Legen **Sie unter Programmereignisse** **Geräte verbinden und** **Gerätetrennung auf** Keine **festlegen.**</span><span class="sxs-lookup"><span data-stu-id="3980c-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="3980c-349">Stille Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="3980c-349">Silence notifications</span></span>

1. <span data-ttu-id="3980c-350">Suchen Sie nach **Fokushilfe,** und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="3980c-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="3980c-351">Wählen Sie **nur Alarme aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-351">Select **Alarms Only**.</span></span> <span data-ttu-id="3980c-352">Dadurch werden flyouts für konstante Benachrichtigungen vermieden.</span><span class="sxs-lookup"><span data-stu-id="3980c-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="3980c-353">Datenträgerbereinigung</span><span class="sxs-lookup"><span data-stu-id="3980c-353">Disk Cleanup</span></span>

1. <span data-ttu-id="3980c-354">Suchen Sie **nach Datenträgerbereinigung,** und öffnen Sie diese App.</span><span class="sxs-lookup"><span data-stu-id="3980c-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="3980c-355">Wählen **Sie unter Zu löschende**Dateien die Dateien aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3980c-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="3980c-356">Wählen Sie **außerdem Systemdateien bereinigen aus.**</span><span class="sxs-lookup"><span data-stu-id="3980c-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="3980c-357">Abschließen und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="3980c-357">Complete and verify</span></span>

1. <span data-ttu-id="3980c-358">Suchen Sie nach allen Windows-Updates, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="3980c-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="3980c-359">Aktualisieren der Gruppenrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="3980c-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="3980c-360">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate /force /boot /wait:0 ein.**</span><span class="sxs-lookup"><span data-stu-id="3980c-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="3980c-361">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="3980c-361">Restart the device.</span></span>

4. <span data-ttu-id="3980c-362">Überprüfen Sie Taskleisten-Apps.</span><span class="sxs-lookup"><span data-stu-id="3980c-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="3980c-363">Connect App</span><span class="sxs-lookup"><span data-stu-id="3980c-363">Connect App</span></span>
   - <span data-ttu-id="3980c-364">Sperrsymbol</span><span class="sxs-lookup"><span data-stu-id="3980c-364">Lock Icon</span></span>
   - <span data-ttu-id="3980c-365">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="3980c-365">Snip & Sketch</span></span>
   - <span data-ttu-id="3980c-366">Teams (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="3980c-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="3980c-367">Office Apps (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="3980c-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="3980c-368">Surface App</span><span class="sxs-lookup"><span data-stu-id="3980c-368">Surface App</span></span>
   - <span data-ttu-id="3980c-369">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="3980c-369">Whiteboard</span></span>
    
5. <span data-ttu-id="3980c-370">Überprüfen Sie die Anwesenheitserkennung.</span><span class="sxs-lookup"><span data-stu-id="3980c-370">Verify presence detection.</span></span>

   - <span data-ttu-id="3980c-371">Die Anwesenheitserkennung ist ein grünes Symbol in der Systemleiste.</span><span class="sxs-lookup"><span data-stu-id="3980c-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="3980c-372">Überprüfen Sie, ob die Projektierung auf diesen PC mit der Connect App aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="3980c-373">Führen Sie nach dem  **Konfigurieren von Project für diese PC-Einstellungen** die Connect-App mindestens einmal aus.</span><span class="sxs-lookup"><span data-stu-id="3980c-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="3980c-374">(Anschließend muss die Connect-App nicht ausgeführt werden, um auf Surface Hub zu projiziert werden.)</span><span class="sxs-lookup"><span data-stu-id="3980c-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="3980c-375">Überprüfen Sie die Energie- und Ruhezustandseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3980c-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="3980c-376">Bildschirmschoner: 15 Minuten, festgelegt auf (keine), Mystify oder Blank; stellen Sie sicher, dass das Kontrollkästchen zum Erfordern eines Kennworts aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="3980c-377">Bildschirm: **Nach 2 Stunden deaktivieren.**</span><span class="sxs-lookup"><span data-stu-id="3980c-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="3980c-378">PC: **Nach 4 Stunden deaktivieren.**</span><span class="sxs-lookup"><span data-stu-id="3980c-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="3980c-379">Überprüfen Sie, ob Windows Hello funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3980c-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="3980c-380">Überprüfen Sie, ob die Synchronisierung Ihrer Einstellungen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3980c-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="3980c-381">Überprüfen Sie Start-Apps.</span><span class="sxs-lookup"><span data-stu-id="3980c-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="3980c-382">Nach der Installation und Konfiguration von Windows 10 kann Surface Hub 2S wie jedes andere Windows 10-Gerät verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3980c-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3980c-383">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3980c-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="3980c-384">Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="3980c-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
