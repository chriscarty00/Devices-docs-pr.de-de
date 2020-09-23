---
title: Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2
description: Dieser Artikel enthält Empfehlungen, mit denen Sie bei Verwendung eines personalisierten Touchscreen-und Stift Computers mit großem Touchscreen optimale Ergebnisse erzielen können.
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
ms.date: 09/22/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: dd580a3b67ffa7c46ce823765d589fec47fadb44
ms.sourcegitcommit: d7fe059a823b7e5f1daec447d92dac60bdd2a26e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "11072842"
---
# <span data-ttu-id="5d07f-104">Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="5d07f-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="5d07f-105">Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um apps und Einstellungen auf dem Surface Hub 2 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5d07f-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="5d07f-106">Diese Schritte werden empfohlen, um die optimale Benutzerfreundlichkeit bei der Verwendung dieses personalisierten Touchscreen-und Stift Computers zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="5d07f-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="5d07f-107">Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="5d07f-108">Konfigurieren von Systemeinstellungen</span><span class="sxs-lookup"><span data-stu-id="5d07f-108">Configure system settings</span></span>

1. <span data-ttu-id="5d07f-109">Anmelden mit einem Konto, das über lokale Administratorrechte auf dem Gerät verfügt.</span><span class="sxs-lookup"><span data-stu-id="5d07f-109">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="5d07f-110">Auf Azure AD-verbundenen Geräten wird der Benutzer, der die Azure AD-Verknüpfung ausführt, automatisch der lokalen Administratorgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5d07f-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="5d07f-111">Azure AD Global Administrators und Azure AD Devices-Administratoren sind [auch lokale Administratoren](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="5d07f-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="5d07f-112">Sie können **net localgroup-Administratoren** an einer Eingabeaufforderung eingeben, um die Konten aufzulisten, die über lokale Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="5d07f-113">Benennen Sie das Gerät mit einem Anzeigenamen um, beispielsweise: **username-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="5d07f-114">Wählen Sie **Start**  >  **Einstellungen**  >  -**Konten**  >  **Synchronisieren Sie Ihre Einstellungen** aus, und deaktivieren Sie die **Synchronisierungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="5d07f-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="5d07f-115">Die hier verwendeten Einstellungen dienen dazu, die optimale Touchscreen-Bildschirmoberfläche zu aktivieren, und daher möchten Sie möglicherweise keine anderen Geräte synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="5d07f-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="5d07f-116">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="5d07f-116">Reboot the device.</span></span>

## <span data-ttu-id="5d07f-117">Aktivieren der Bildschirmtastatur und des Touchpads</span><span class="sxs-lookup"><span data-stu-id="5d07f-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="5d07f-118">Tippen und halten oder klicken Sie mit der rechten Maustaste auf die Taskleiste, und wählen Sie dann die Schaltfläche **Bildschirmtastatur anzeigen** und die **Schaltfläche Touchpad anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="5d07f-119">Die Bildschirmtastatur ist für die direkte Benutzereingabe hilfreich, und das virtuelle Touchpad hilft bei der präzisen Auswahl, dem Hovern des Bildschirms oder als Alternative zum Tippen und halten für das Klicken mit der rechten Maustaste.</span><span class="sxs-lookup"><span data-stu-id="5d07f-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="5d07f-120">Nachfolgend sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5d07f-120">See the following example.</span></span>

     ![Touch-Einstellungen](images/touch.png)

2. <span data-ttu-id="5d07f-122">Konfigurieren Sie die Bildschirmtastatur auf QWERTY und unverankert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-122">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="5d07f-123">Wählen Sie das Tastatursymbol in der Taskleiste aus, um die Bildschirmtastatur anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-123">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="5d07f-124">Wählen Sie auf der Bildschirmtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="5d07f-125">Wählen Sie in der obersten Zeile den neben letzten Tastaturtyp aus, um die QWERTY-Funktion zu aktivieren, und die letzte Option in der zweiten Zeile, um das Floating zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="5d07f-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="5d07f-126">Weitere Informationen finden Sie in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-126">See the following examples.</span></span>

     ![Tastatureinstellungen](images/kbd.png)

3. <span data-ttu-id="5d07f-128">Konfigurieren Sie die Einstellungen für die Soft-Tastatur.</span><span class="sxs-lookup"><span data-stu-id="5d07f-128">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="5d07f-129">Suchen nach und Öffnen von **Eingabeeinstellungen**</span><span class="sxs-lookup"><span data-stu-id="5d07f-129">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="5d07f-130">Aktivieren Sie alle Optionen unter Rechtschreibung, Eingabe und Bildschirmtastatur.</span><span class="sxs-lookup"><span data-stu-id="5d07f-130">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="5d07f-131">Das folgende Beispiel zeigt das Trackpad, das nützlich ist, um zu navigieren und Optionen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-131">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="5d07f-132">Die Bildschirmtastatur wird verwendet, um den Microsoft Store zu durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="5d07f-132">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Verwenden des Trackpads](images/store.png)

## <span data-ttu-id="5d07f-134">Konfigurieren der Bluetooth-Tastatur und-Maus (optional)</span><span class="sxs-lookup"><span data-stu-id="5d07f-134">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="5d07f-135">Schließen Sie eine Tastatur und Maus an, wenn Sie das Gerät als Ihr primäres Windows-Gerät verwenden, oder verwenden Sie es häufig für die Eingabe oder die Genauigkeit der Arbeit.</span><span class="sxs-lookup"><span data-stu-id="5d07f-135">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="5d07f-136">Wenn sich Ihr Surface-Hub-Gerät in der Nähe eines PCs befindet, können Sie die [Maus ohne Rahmen](https://aka.ms/mm) verwenden, um nahtlos zwischen dem Surface-Hub und dem PC zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="5d07f-136">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="5d07f-137">Weitere Informationen finden Sie unter [Microsoft-Download aus der Garage: Maus ohne Rahmen](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="5d07f-137">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="5d07f-138">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="5d07f-138">OneDrive for Business</span></span>

<span data-ttu-id="5d07f-139">Verwenden Sie [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) , um Tools, Protokolle und andere Dateien auf einfache Weise zwischen allen ihren Arbeitsgeräten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="5d07f-139">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="5d07f-140">Mit OneDrive können Sie Ihre Arbeitsdateien zwischen ihren Laptops, dem Surface Hub-Desktop und ihren von InTune verwalteten mobilen Geräten freigeben.</span><span class="sxs-lookup"><span data-stu-id="5d07f-140">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="5d07f-141">Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-141">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="5d07f-142">Wenn Sie die Größe der Surface-Hub-SSD (128 GB) berücksichtigen und OneDrive auf Ihrem Surface Hub-Desktop Gerät konfigurieren, stellen Sie sicher, dass die Standardkonfiguration darin besteht, die Dateien online zu speichern und während der Verwendung Dateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-142">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="5d07f-143">Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung **files on-Demand** fest, um **Speicherplatz zu sparen und während der Verwendung Dateien herunterzuladen**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-143">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="5d07f-144">Weitere Informationen finden Sie unter [Abfragen und Einrichten von Dateien auf Anforderungsstatus in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="5d07f-144">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![OneDrive-Einstellungen](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="5d07f-146">Sie können diese Schritte auch wiederholen, um eine persönliche OneDrive zu konfigurieren, aber achten Sie darauf, den Speicherplatz zu sparen und nur Dateien herunterzuladen, wenn Sie Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-146">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="5d07f-147">SharePoint und Teams</span><span class="sxs-lookup"><span data-stu-id="5d07f-147">SharePoint and Teams</span></span>

<span data-ttu-id="5d07f-148">SharePoint-und Teams-Kanaldateien können mithilfe des OneDrive-Synchronisierungsmoduls auch lokal mit ihren Desktopgeräten wie Laptops und Surface Hubs synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-148">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="5d07f-149">So synchronisieren Sie interne Unternehmensdateien mit der OneDrive-Synchronisierungs-App auf Ihr lokales Laufwerk:</span><span class="sxs-lookup"><span data-stu-id="5d07f-149">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="5d07f-150">Wechseln Sie zu einer SharePoint-Website, und navigieren Sie zum Dokumentverzeichnis auf oberster Ebene für Dateien, die Sie auf Ihrem lokalen Gerät anzeigen oder bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="5d07f-150">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="5d07f-151">Wählen Sie auf der Schaltfläche " **Synchronisieren** " oben im SharePoint-Menüband aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-151">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="5d07f-152">Wählen Sie auf **Öffnen** im Popupfenster aus, auf dem **diese Website versucht, Microsoft OneDrive zu öffnen**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-152">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="5d07f-153">Überprüfen Sie, ob die SharePoint-Dateien mit Ihrem lokalen Laufwerk synchronisiert werden, indem Sie auf das OneDrive-Symbol unten rechts in der Taskleiste klicken.</span><span class="sxs-lookup"><span data-stu-id="5d07f-153">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="5d07f-154">Überprüfen Sie, ob die Konfiguration so eingestellt ist, dass die Dateien online bleiben, und laden Sie die Dateien nur während der Verwendung herunter.</span><span class="sxs-lookup"><span data-stu-id="5d07f-154">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="5d07f-155">Öffnen Sie den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="5d07f-155">Open file explorer.</span></span>
    2. <span data-ttu-id="5d07f-156">Navigieren Sie zu und wählen Sie mit der rechten Maustaste auf dem \*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-156">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="5d07f-157">Wählen Sie **Speicherplatz freigeben**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-157">Select **Free up space**.</span></span>
    4. <span data-ttu-id="5d07f-158">In der Spalte Status wird der Status von Dateien und Ordnern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d07f-158">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="5d07f-159">Weitere Informationen finden Sie unter [Synchronisieren von SharePoint-Dateien mit dem OneDrive-synchronisierungsclient](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="5d07f-159">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="5d07f-160">Teams-Kanaldateien werden auf SharePoint-Websites mit allen gleichen SharePoint-Dokumentfunktionen wie Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-160">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="5d07f-161">So synchronisieren Sie Teams-Kanaldateien:</span><span class="sxs-lookup"><span data-stu-id="5d07f-161">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="5d07f-162">Navigieren Sie zu dem Interessenbereich "Teams", und wählen Sie oben auf der Registerkarte " **Dateien** " aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-162">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="5d07f-163">Wählen Sie dann **Synchronisieren**aus. Die Dateien werden synchronisiert und werden im Datei-Explorer unter \*\*Desktop \ Microsoft \ \<name of the Teams Channel\> \*\*angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d07f-163">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="5d07f-164">Verwenden Sie dasselbe Verfahren, das Sie zum Synchronisieren von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern, und laden Sie Sie nur herunter, wenn Sie Sie verwenden, indem Sie im Datei-Explorer auf den Namen des Teams-Kanals tippen und halten oder mit der rechten Maustaste darauf klicken und dann **Platz freigeben**auswählen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-164">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="5d07f-165">Koppeln des Surface Hub-Stifts</span><span class="sxs-lookup"><span data-stu-id="5d07f-165">Pair the Surface Hub pen</span></span>

<span data-ttu-id="5d07f-166">So koppeln Sie das Stift Gerät:</span><span class="sxs-lookup"><span data-stu-id="5d07f-166">To pair the pen device:</span></span>

1. <span data-ttu-id="5d07f-167">Wählen Sie **Start**  >  **Settings**  >  **Devices**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-167">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="5d07f-168">Wählen Sie **Bluetooth oder anderes Gerät hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-168">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="5d07f-169">Wählen Sie **Bluetooth**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-169">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="5d07f-170">Entfernen Sie die Stift-Endstück-Taste und schütteln, um die Batterie Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-170">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="5d07f-171">Setzen Sie die Kappe wieder ein, und halten Sie die Kappe gedrückt, bis die Kopplungs-LED blinkt.</span><span class="sxs-lookup"><span data-stu-id="5d07f-171">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="5d07f-172">Wählen Sie auf den Surface Hub Bluetooth-Einstellungen die Option **Surface Hub 2 Pen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-172">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="5d07f-173">Führen Sie den Kopplungsvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-173">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="5d07f-174">Wenn die Kopplung nicht erfolgreich ist, versuchen Sie, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="5d07f-174">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="5d07f-175">Falls erforderlich, starten Sie das Gerät neu, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="5d07f-175">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="5d07f-176">Kamerakonfiguration</span><span class="sxs-lookup"><span data-stu-id="5d07f-176">Camera configuration</span></span>

<span data-ttu-id="5d07f-177">Sie können die Kamera oben oder an jeder Seite des Geräts montieren.</span><span class="sxs-lookup"><span data-stu-id="5d07f-177">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="5d07f-178">Montieren Sie die Kamera in einer Position, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktop-Standfuß statt mit einem Wagen verwenden oder sich in der Nähe des Hubs befinden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-178">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="5d07f-179">Da die Kamera nicht automatisch gedreht wird, benötigen Sie eine 2mm-Sechskant-Taste, um die Kamera manuell zu drehen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-179">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="5d07f-180">Weitere Informationen dazu, wie Sie die Kamera seitlich montieren und die Kamera manuell drehen können, finden Sie unter [Surface Hub 2S-Kameralinsen Ausrichtung](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span><span class="sxs-lookup"><span data-stu-id="5d07f-180">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="5d07f-181">Windows Hello-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5d07f-181">Windows Hello configuration</span></span>

<span data-ttu-id="5d07f-182">Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-182">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="5d07f-183">Der Surface Hub 2-Fingerabdruckleser-Zubehör kann an einen beliebigen USB-C-Anschluss des Geräts angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-183">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

> <i><span data-ttu-id="5d07f-184">Der Surface Hub 2-Fingerabdruckleser steht demnächst zum Kauf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5d07f-184">The Surface Hub 2 Fingerprint Reader will be available for purchase soon.</span></span> <span data-ttu-id="5d07f-185">Bitte besuchen Sie diese Seite, um weitere Informationen zu erhalten, einschließlich des Kaufs.</span><span class="sxs-lookup"><span data-stu-id="5d07f-185">Please check back on this page for more information including how to purchase.</span></span></i>

<span data-ttu-id="5d07f-186">Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie **Start**  >  **Einstellungen**  >  **Accounts**  >  für die**Anmeldeoptionen**  >  **Windows Hello Fingerabdruck** aus, um Ihren Fingerabdruck einzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="5d07f-186">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="5d07f-187">Verwenden Sie ein Windows Hello Certified-Gerät für die Flächen Erkennung.</span><span class="sxs-lookup"><span data-stu-id="5d07f-187">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="5d07f-188">Die Surface Hub 2S-Kamera unterstützt keine Windows Hello Face-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="5d07f-188">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="5d07f-189">Aktivieren eines Symbol Symbols für den Sperrbildschirm auf der Taskleiste</span><span class="sxs-lookup"><span data-stu-id="5d07f-189">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="5d07f-190">So fügen Sie der Taskleiste ein Symbol hinzu, das eine Touchscreen-Sperre ähnlich der Windows-L-Tastenkombination ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="5d07f-190">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="5d07f-191">Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen Sie **neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**  >  **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-191">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="5d07f-192">Geben Sie einen Namen für die Verknüpfung ein, beispielsweise " **mein PC sperren**", und wählen Sie dann **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-192">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="5d07f-193">Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-193">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="5d07f-194">Geben Sie auf der Registerkarte **Verknüpfung** im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll, Lock Workstation**</span><span class="sxs-lookup"><span data-stu-id="5d07f-194">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="5d07f-195">Wählen Sie die Schaltfläche **Symbol ändern** aus, und navigieren Sie zu **C:\Windows\System32\imageres.dll** , und wählen Sie ein Symbol aus, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5d07f-195">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="5d07f-196">Siehe hierzu das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d07f-196">See the following example:</span></span>

    ![Wählen Sie ein Symbol aus.](images/lock.png)
    
1.  <span data-ttu-id="5d07f-198">Wählen Sie **OK** aus, um die Verknüpfung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5d07f-198">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="5d07f-199">Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die Verknüpfung, und wählen Sie **an Taskleiste anheften**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-199">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

## <span data-ttu-id="5d07f-200">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5d07f-200">Applications</span></span>

### <span data-ttu-id="5d07f-201">Aktualisieren von installierten apps</span><span class="sxs-lookup"><span data-stu-id="5d07f-201">Update installed apps</span></span>

<span data-ttu-id="5d07f-202">So aktualisieren Sie alle installierten Store-Apps:</span><span class="sxs-lookup"><span data-stu-id="5d07f-202">To update all installed Store apps:</span></span>

1. <span data-ttu-id="5d07f-203">Öffnen Sie die Microsoft Store-App, und wählen Sie in der oberen rechten Ecke die Option Weitere Auslassungszeichen **anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-203">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="5d07f-204">Klicken Sie auf **Downloads und Updates**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-204">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="5d07f-205">Klicken Sie auf **Updates abrufen**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-205">Select **Get updates**.</span></span>

### <span data-ttu-id="5d07f-206">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="5d07f-206">Microsoft Whiteboard</span></span>

<span data-ttu-id="5d07f-207">So installieren Sie das Microsoft Whiteboard:</span><span class="sxs-lookup"><span data-stu-id="5d07f-207">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="5d07f-208">Wählen Sie unten rechts in der Taskleiste das Symbol für den **Windows-Freihand-Arbeitsbereich** aus, und laden Sie **Whiteboard**herunter.</span><span class="sxs-lookup"><span data-stu-id="5d07f-208">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Freihand-Arbeitsbereich](images/ink.png) 

<span data-ttu-id="5d07f-210">Sie können Whiteboard auch über den Microsoft Store installieren:</span><span class="sxs-lookup"><span data-stu-id="5d07f-210">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="5d07f-211">Öffnen Sie die Microsoft Store-App, und suchen Sie nach **Whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-211">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="5d07f-212">Wählen Sie " **Nein** ", wenn Sie sich anmelden und geräteübergreifend verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-212">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="5d07f-213">Anheften des Whiteboards an die Taskleiste</span><span class="sxs-lookup"><span data-stu-id="5d07f-213">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="5d07f-214">Surface-App</span><span class="sxs-lookup"><span data-stu-id="5d07f-214">Surface app</span></span>

1. <span data-ttu-id="5d07f-215">Suchen Sie im Microsoft Store nach **Surface**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-215">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="5d07f-216">Setzen Sie den **verfügbaren** Filter auf **alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-216">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="5d07f-217">Installieren Sie die **Surface** -app.</span><span class="sxs-lookup"><span data-stu-id="5d07f-217">Install the **Surface** app.</span></span> <span data-ttu-id="5d07f-218">Dies sollte die erste aufgelistete APP sein.</span><span class="sxs-lookup"><span data-stu-id="5d07f-218">This should be the first app listed.</span></span> <span data-ttu-id="5d07f-219">Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die APP installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="5d07f-219">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="5d07f-220">Anheften Sie die **Surface** -APP an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="5d07f-220">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="5d07f-221">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="5d07f-221">Snip & Sketch</span></span>

1. <span data-ttu-id="5d07f-222">Öffnen Sie die APP **Snip & Sketch** , und fixieren Sie Sie an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="5d07f-222">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="5d07f-223">Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-223">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="5d07f-224">Aktivieren Sie in **Einstellungen** **die Option automatisch in Zwischenablage kopieren**, **snips speichern**und **mehrere Fenster** (optional).</span><span class="sxs-lookup"><span data-stu-id="5d07f-224">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="5d07f-225">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="5d07f-225">Microsoft Office</span></span>

1. <span data-ttu-id="5d07f-226">Öffnen Sie das [Office-Portal](https://portal.office.com/account#installs) , und installieren Sie die gewünschten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-226">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="5d07f-227">Anheften Sie die gewünschten Office-Anwendungen an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="5d07f-227">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="5d07f-228">Wenn Outlook installiert ist, müssen Sie Outlook Ost so einstellen, dass nur der letzte zwei Wochen-Cache gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="5d07f-228">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="5d07f-229">Dadurch werden die Datenträgernutzung und die Einrichtungszeit erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-229">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="5d07f-230">Wählen Sie **Datei**  >  **Kontoeinstellungen** aus, und wählen Sie Ihr Konto aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-230">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="5d07f-231">Wählen Sie **ändern** aus, und legen Sie den Schieberegler für die **Verwendung des Exchange-Cache-Modus** auf 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="5d07f-231">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="5d07f-232">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d07f-232">Microsoft Teams</span></span>

1. <span data-ttu-id="5d07f-233">Laden Sie [Microsoft Teams](https://teams.microsoft.com/downloads)herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="5d07f-233">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="5d07f-234">Konfigurieren Sie die Einstellungen für die automatische Startanwendung (optional).</span><span class="sxs-lookup"><span data-stu-id="5d07f-234">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="5d07f-235">Anheften von Teams an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="5d07f-235">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="5d07f-236">Sie können die Benachrichtigungen für Teams auf dem Gerät reduzieren, um Ablenkungen zu vermeiden (optional).</span><span class="sxs-lookup"><span data-stu-id="5d07f-236">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![Teams-Benachrichtigungen](images/teams.png)

### <span data-ttu-id="5d07f-238">Connect-App</span><span class="sxs-lookup"><span data-stu-id="5d07f-238">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d07f-239">In Windows 10, Version 2004 und höher, ist die Connect-App für drahtlose Projektion unter Verwendung von Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5d07f-239">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="5d07f-240">Wenn Sie die APP installieren möchten, wählen Sie unter **Einstellungen**  >  **apps**  >  **optionale Features**  >  **ein Feature hinzufügen** aus, und installieren Sie dann die **drahtlose Anzeige** -app.</span><span class="sxs-lookup"><span data-stu-id="5d07f-240">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="5d07f-241">Suchen Sie nach **Connect**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-241">Search for **Connect**.</span></span>
2. <span data-ttu-id="5d07f-242">Öffnen Sie die APP, und schließen Sie Sie dann (**Project auf diesem PC** funktioniert möglicherweise nicht, wenn die APP mindestens einmal ausgeführt wurde).</span><span class="sxs-lookup"><span data-stu-id="5d07f-242">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="5d07f-243">Tippen und halten oder klicken Sie mit der rechten Maustaste, um die Taskleiste zu anheften.</span><span class="sxs-lookup"><span data-stu-id="5d07f-243">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="5d07f-244">Suchen Sie nach **Projektions Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-244">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="5d07f-245">**Wenn Sie unter Windows-und Android-Geräten auf diesen PC projizieren können, wenn Sie sagen, dass es in Ordnung ist**, wählen Sie **überall verfügbar** aus, wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="5d07f-245">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="5d07f-246">Andernfalls können Sie **überall in sicheren Netzwerken verfügbar**wählen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-246">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="5d07f-247">Wählen Sie unter **Projekt auf diesem PC anfordern**die Option **nur erstes Mal**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-247">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="5d07f-248">Wählen Sie unter **PIN für Kopplung anfordern**die Option **nie**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-248">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="5d07f-249">Empfohlene Konfiguration, wenn Sie sich nicht im Unternehmensnetzwerk befinden:</span><span class="sxs-lookup"><span data-stu-id="5d07f-249">Recommended configuration when not on the corporate network:</span></span>

  ![Einstellungen zu Hause](images/project1.png)

<span data-ttu-id="5d07f-251">Empfohlene Konfiguration im Unternehmensnetzwerk:</span><span class="sxs-lookup"><span data-stu-id="5d07f-251">Recommended configuration on the corporate network:</span></span>

  ![Einstellungen bei der Arbeit](images/project2.png)

### <span data-ttu-id="5d07f-253">Ihr Smartphone</span><span class="sxs-lookup"><span data-stu-id="5d07f-253">Your Phone</span></span>

<span data-ttu-id="5d07f-254">Die APP **Ihres Telefons** wird unter Windows 10 standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-254">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="5d07f-255">Wenn Sie nicht vorhanden ist, können Sie Sie auch aus dem Windows Store installieren.</span><span class="sxs-lookup"><span data-stu-id="5d07f-255">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="5d07f-256">Informationen zum Einrichten der App finden Sie unter so wird es [gemacht: Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten zwischen Ihrem PC und Smartphone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="5d07f-256">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="5d07f-257">Weitere Informationen finden Sie unter [Beheben häufig auftretender Probleme mit ihrer Telefon-APP unter Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="5d07f-257">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="5d07f-258">Super Fancy Zones</span><span class="sxs-lookup"><span data-stu-id="5d07f-258">Super Fancy Zones</span></span>

<span data-ttu-id="5d07f-259">**Super fancy Zones** hilft Benutzern beim Anordnen von Windows zum Maximieren von Bildschirm Immobilien.</span><span class="sxs-lookup"><span data-stu-id="5d07f-259">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="5d07f-260">Sie ist jetzt in [PowerToys](https://github.com/microsoft/PowerToys/releases) auf GitHub enthalten.</span><span class="sxs-lookup"><span data-stu-id="5d07f-260">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="5d07f-261">Edge Chrom-Browser</span><span class="sxs-lookup"><span data-stu-id="5d07f-261">Edge Chromium browser</span></span>

<span data-ttu-id="5d07f-262">Laden Sie den neuen [Edge Chrom-Browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL)herunter, und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="5d07f-262">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="5d07f-263">Zusätzliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5d07f-263">Additional settings</span></span>

### <span data-ttu-id="5d07f-264">Stift Schwanz auswählen, um Whiteboard zu starten</span><span class="sxs-lookup"><span data-stu-id="5d07f-264">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="5d07f-265">Suchen Sie nach **Stift** , und wählen Sie **Stift & Windows Ink-Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-265">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="5d07f-266">**Klicken Sie** am unteren Rand der Seite unter **Stifttasten Kombinationen** auf **Microsoft Whiteboard**auswählen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-266">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="5d07f-267">Energie-und Ruhezustandseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5d07f-267">Power and sleep settings</span></span>

1. <span data-ttu-id="5d07f-268">Wählen Sie **Start**  >  **Einstellungen**  >  **System**  >  **Power & Sleep**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-268">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="5d07f-269">Stellen Sie den Power Mode-Schieberegler auf **optimale Leistung**ein.</span><span class="sxs-lookup"><span data-stu-id="5d07f-269">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="5d07f-270">Konfigurieren Sie die Einstellungen für den Bildschirm und den Ruhezustand nach Ihren wünschen, während Sie auch die Doppler-Anwesenheitserkennung erfassen, die das Gerät aktiviert, wenn Bewegungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-270">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="5d07f-271">Daher empfiehlt es sich, den Bildschirm so zu konfigurieren, dass er **nach 2 Stunden ausgeschaltet** wird und der PC **nach 4 Stunden ausgeschaltet wird.**</span><span class="sxs-lookup"><span data-stu-id="5d07f-271">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>
### <span data-ttu-id="5d07f-272">Bildschirmschoner.</span><span class="sxs-lookup"><span data-stu-id="5d07f-272">Screen saver.</span></span>

1. <span data-ttu-id="5d07f-273">Suchen Sie nach **dem Sperrbildschirm** , und öffnen Sie die Einstellungen für den **Sperrbildschirm**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-273">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="5d07f-274">Konfigurieren Sie die Einstellungen für das **Bildschirm Timeout** und die **Bildschirmschonereinstellungen** nach Ihren Wünschen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-274">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="5d07f-275">Speicheroptimierung</span><span class="sxs-lookup"><span data-stu-id="5d07f-275">Storage Sense</span></span>

<span data-ttu-id="5d07f-276">Der Surface Hub 2 verfügt über eine 128 GB-SSD für den lokalen Speicher, daher ist es notwendig, die Verwendung von Speicher Sparmaßnahmen während der normalen Nutzung zu überdenken.</span><span class="sxs-lookup"><span data-stu-id="5d07f-276">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="5d07f-277">So konfigurieren Sie den Speicher Sinn:</span><span class="sxs-lookup"><span data-stu-id="5d07f-277">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="5d07f-278">Suchen Sie nach den **Speichereinstellungen**, die unter **System Einstellungen**gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-278">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="5d07f-279">Wählen Sie unter **Einstellungen**die Option **Speicher Sinn aktivieren** aus, um die Seite **Speicher** Einstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-279">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="5d07f-280">Stellen Sie den Speicher Sinn auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-280">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="5d07f-281">Wählen Sie **Speicher Sinn konfigurieren aus, oder führen Sie es jetzt** aus, und konfigurieren Sie die Einstellungen so, dass Dateien so weit wie möglich online bleiben (aufgrund des geringen Festplattenspeichers).</span><span class="sxs-lookup"><span data-stu-id="5d07f-281">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="5d07f-282">Empfohlene Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="5d07f-282">Recommended settings:</span></span>
- <span data-ttu-id="5d07f-283">Führen Sie den Speicher Sinn = jeden Tag aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-283">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="5d07f-284">Löschen Sie temporäre Dateien, die meine apps nicht verwenden = alle 14 Tage (mindestens).</span><span class="sxs-lookup"><span data-stu-id="5d07f-284">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="5d07f-285">Löschen Sie Dateien im Ordner "Downloads", wenn Sie über mehr als = 30 Tage vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5d07f-285">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="5d07f-286">OneDrive: Inhalt wird online – nur, wenn er nicht mehr als = 30 Tage geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="5d07f-286">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="5d07f-287">Tabletmodus</span><span class="sxs-lookup"><span data-stu-id="5d07f-287">Tablet mode</span></span>

<span data-ttu-id="5d07f-288">Aktivieren Sie den Tablet-Modus, wenn dies für Barrierefreiheitsanforderungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5d07f-288">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="5d07f-289">Energieverwaltung</span><span class="sxs-lookup"><span data-stu-id="5d07f-289">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="5d07f-290">Bevor Sie das folgende Verfahren ausführen, erkundigen Sie sich bei Ihrer IT-Abteilung, ob ein Surface Hub 2S-Gerät aus der globalen Energieverwaltungsrichtlinie ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d07f-290">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="5d07f-291">Einige Energieverwaltungseinstellungen können die Anwesenheits Erkennungsfunktion deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5d07f-291">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="5d07f-292">Suchen Sie nach **Software Center** , und öffnen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="5d07f-292">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="5d07f-293">Wählen Sie im Navigationsbereich **Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-293">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="5d07f-294">Erweitern Sie den Abschnitt **Energieverwaltung** , und wählen Sie **auf diesem Computer keine Energieeinstellungen von meiner IT-Abteilung anwenden aus**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-294">Expand the **Power management** section and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Software Einstellungen](images/soft-cntr.png)

### <span data-ttu-id="5d07f-296">Sound Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5d07f-296">Sound settings</span></span>

1. <span data-ttu-id="5d07f-297">Suchen Sie nach **Sounds-Einstellungen** , und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="5d07f-297">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="5d07f-298">Wählen Sie auf der rechten Seite **Sound Control Panel** aus, und klicken Sie auf die Registerkarte **Sounds** .</span><span class="sxs-lookup"><span data-stu-id="5d07f-298">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="5d07f-299">Klicken Sie unter **Programmereignisse** auf **Gerät verbinden** und **Gerät trennen** mit **keiner**.</span><span class="sxs-lookup"><span data-stu-id="5d07f-299">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="5d07f-300">Benachrichtigungen zum Schweigen</span><span class="sxs-lookup"><span data-stu-id="5d07f-300">Silence notifications</span></span>

1. <span data-ttu-id="5d07f-301">Suchen Sie nach **Fokus Unterstützung** , und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="5d07f-301">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="5d07f-302">Wählen Sie **nur Erinnerungen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-302">Select **Alarms Only**.</span></span> <span data-ttu-id="5d07f-303">Dadurch werden keine Konstanten Benachrichtigungs Flyouts vermieden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-303">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="5d07f-304">Datenträgerbereinigung</span><span class="sxs-lookup"><span data-stu-id="5d07f-304">Disk Cleanup</span></span>

1. <span data-ttu-id="5d07f-305">Suchen Sie nach **Datenträgerbereinigung** , und öffnen Sie diese APP.</span><span class="sxs-lookup"><span data-stu-id="5d07f-305">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="5d07f-306">Wählen Sie unter **zu löschende Dateien**die Dateien aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d07f-306">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="5d07f-307">Wählen Sie auch **Systemdateien bereinigen**aus.</span><span class="sxs-lookup"><span data-stu-id="5d07f-307">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="5d07f-308">Fertig stellen und überprüfen</span><span class="sxs-lookup"><span data-stu-id="5d07f-308">Complete and verify</span></span>

1. <span data-ttu-id="5d07f-309">Suchen Sie nach allen Windows-Updates, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="5d07f-309">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="5d07f-310">Aktualisieren von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5d07f-310">Update Group Policy</span></span>
    1. <span data-ttu-id="5d07f-311">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate force/Boot/Wait: 0**ein.</span><span class="sxs-lookup"><span data-stu-id="5d07f-311">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="5d07f-312">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="5d07f-312">Reboot the device.</span></span>
4. <span data-ttu-id="5d07f-313">Überprüfen der Taskleisten-apps</span><span class="sxs-lookup"><span data-stu-id="5d07f-313">Verify taskbar apps.</span></span>
    - <span data-ttu-id="5d07f-314">Connect-App</span><span class="sxs-lookup"><span data-stu-id="5d07f-314">Connect App</span></span>
    - <span data-ttu-id="5d07f-315">Symbol "Sperren"</span><span class="sxs-lookup"><span data-stu-id="5d07f-315">Lock Icon</span></span>
    - <span data-ttu-id="5d07f-316">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="5d07f-316">Snip & Sketch</span></span>
    - <span data-ttu-id="5d07f-317">Teams (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="5d07f-317">Teams (if applicable)</span></span>
    - <span data-ttu-id="5d07f-318">Office-Apps (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="5d07f-318">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="5d07f-319">Surface-App</span><span class="sxs-lookup"><span data-stu-id="5d07f-319">Surface App</span></span>
    - <span data-ttu-id="5d07f-320">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="5d07f-320">Whiteboard</span></span>
5. <span data-ttu-id="5d07f-321">Überprüfen Sie die Anwesenheitserkennung.</span><span class="sxs-lookup"><span data-stu-id="5d07f-321">Verify presence detection.</span></span>
    - <span data-ttu-id="5d07f-322">Die Anwesenheitserkennung ist ein grünes Symbol in der Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="5d07f-322">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="5d07f-323">Überprüfen Sie, ob das projizieren auf diesen PC mit der Connect-App aktiviert ist (die Anwendung muss vor dem Herstellen der Verbindung nicht ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="5d07f-323">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="5d07f-324">Überprüfen Sie die Energie-und Ruhezustandseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5d07f-324">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="5d07f-325">Bildschirmschoner: 15 Minuten, auf (keine), Mystify oder leer; Kontrollkästchen zum Anfordern eines Kennworts ist aktiviert</span><span class="sxs-lookup"><span data-stu-id="5d07f-325">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="5d07f-326">Bildschirm: Ausschalten **nach 2 Stunden.**</span><span class="sxs-lookup"><span data-stu-id="5d07f-326">Screen: **Turn off after 2 hours.**</span></span>
    - <span data-ttu-id="5d07f-327">PC: Ausschalten  **nach 4 Stunden.**</span><span class="sxs-lookup"><span data-stu-id="5d07f-327">PC:  **Turn off after 4 hours.**</span></span>
8. <span data-ttu-id="5d07f-328">Überprüfen Sie, ob Windows Hello funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-328">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="5d07f-329">Überprüfen der Synchronisierung Ihre Einstellungen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5d07f-329">Verify sync your settings is disabled.</span></span>
10. <span data-ttu-id="5d07f-330">Überprüfen von Start-apps.</span><span class="sxs-lookup"><span data-stu-id="5d07f-330">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="5d07f-331">Nach der Installation und Konfiguration von Windows 10 kann der Surface Hub 2S genauso wie jedes andere Windows 10-Gerät verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5d07f-331">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="5d07f-332">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5d07f-332">Related topics</span></span>

[<span data-ttu-id="5d07f-333">Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="5d07f-333">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
