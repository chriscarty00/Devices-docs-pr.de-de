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
ms.date: 11/03/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: b86776b56e892c34ea8b5abbc55d5c48723a5f9e
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154127"
---
# <span data-ttu-id="03777-104">Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="03777-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="03777-105">Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um apps und Einstellungen auf dem Surface Hub 2 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="03777-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="03777-106">Diese Schritte werden empfohlen, um die optimale Benutzerfreundlichkeit bei der Verwendung dieses personalisierten Touchscreen-und Stift Computers zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="03777-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="03777-107">Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="03777-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="03777-108">Konfigurieren von Systemeinstellungen</span><span class="sxs-lookup"><span data-stu-id="03777-108">Configure system settings</span></span>

1. <span data-ttu-id="03777-109">Anmelden mit einem Konto, das über lokale Administratorrechte auf dem Gerät verfügt.</span><span class="sxs-lookup"><span data-stu-id="03777-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="03777-110">Auf Azure AD-verbundenen Geräten wird der Benutzer, der die Azure AD-Verknüpfung ausführt, automatisch der lokalen Administratorgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="03777-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="03777-111">Azure AD Global Administrators und Azure AD Devices-Administratoren sind <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> auch lokale Administratoren </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="03777-112">Sie können **net localgroup-Administratoren** an einer Eingabeaufforderung eingeben, um die Konten aufzulisten, die über lokale Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="03777-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="03777-113">Benennen Sie das Gerät mit einem Anzeigenamen um, beispielsweise: **username-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="03777-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="03777-114">Wählen Sie **Start**  >  **Einstellungen**  >  -**Konten**  >  **Synchronisieren Sie Ihre Einstellungen** aus, und deaktivieren Sie die **Synchronisierungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="03777-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="03777-115">Die hier verwendeten Einstellungen dienen dazu, die optimale Touchscreen-Bildschirmoberfläche zu aktivieren, und daher möchten Sie möglicherweise keine anderen Geräte synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="03777-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="03777-116">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="03777-116">Restart the device.</span></span>

## <span data-ttu-id="03777-117">Aktivieren der Bildschirmtastatur und des Touchpads</span><span class="sxs-lookup"><span data-stu-id="03777-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="03777-118">Tippen und halten oder klicken Sie mit der rechten Maustaste auf die Taskleiste, und wählen Sie dann die Schaltfläche **Bildschirmtastatur anzeigen** und die **Schaltfläche Touchpad anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="03777-119">Die Bildschirmtastatur ist für die direkte Benutzereingabe hilfreich, und das virtuelle Touchpad hilft bei der präzisen Auswahl, dem Hovern des Bildschirms oder als Alternative zum Tippen und halten für das Klicken mit der rechten Maustaste.</span><span class="sxs-lookup"><span data-stu-id="03777-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="03777-120">Nachfolgend sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="03777-120">See the following example.</span></span>

      ![Touch-Einstellungen](images/touch.png)

2. <span data-ttu-id="03777-122">Konfigurieren Sie die Bildschirmtastatur auf QWERTY und unverankert.</span><span class="sxs-lookup"><span data-stu-id="03777-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="03777-123">Wählen Sie das **Tastatur** Symbol in der Taskleiste aus, um die Bildschirmtastatur anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03777-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="03777-124">Wählen Sie auf der Bildschirmtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="03777-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="03777-125">Wählen Sie in der obersten Zeile den neben letzten Tastaturtyp aus, um die QWERTY-Funktion zu aktivieren, und die letzte Option in der zweiten Zeile, um das Floating zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="03777-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="03777-126">Weitere Informationen finden Sie in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="03777-126">See the following examples.</span></span>

       ![Tastatureinstellungen](images/kbd.png)
 
3. <span data-ttu-id="03777-128">Konfigurieren Sie die Einstellungen für die Soft-Tastatur.</span><span class="sxs-lookup"><span data-stu-id="03777-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="03777-129">Wählen Sie auf der Bildschirmtastatur das Symbol **Einstellungen** aus, oder suchen Sie nach den **Eingabeeinstellungen**, und öffnen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="03777-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![Soft Keyboard-Einstellungen](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="03777-131">Aktivieren Sie alle Optionen unter Rechtschreibung, Eingabe und Bildschirmtastatur.</span><span class="sxs-lookup"><span data-stu-id="03777-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="03777-132">Das folgende Beispiel zeigt das Trackpad, das nützlich ist, um zu navigieren und Optionen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="03777-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="03777-133">Die Bildschirmtastatur wird verwendet, um den Microsoft Store zu durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="03777-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Verwenden des Trackpads](images/store.png)

## <span data-ttu-id="03777-135">Konfigurieren der Bluetooth-Tastatur und-Maus (optional)</span><span class="sxs-lookup"><span data-stu-id="03777-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="03777-136">Schließen Sie eine Tastatur und Maus an, wenn Sie das Gerät als Ihr primäres Windows-Gerät verwenden, oder verwenden Sie es häufig für die Eingabe oder die Genauigkeit der Arbeit.</span><span class="sxs-lookup"><span data-stu-id="03777-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="03777-137">Wenn sich Ihr Surface-Hub-Gerät in der Nähe eines PCs befindet, können Sie <a href="https://aka.ms/mm" target="_blank"> die Maus ohne Rahmen verwenden, </a> um nahtlos zwischen dem Surface-Hub und dem PC zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="03777-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="03777-138">Weitere Informationen finden Sie unter <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft-Download aus der Garage: Maus ohne Rahmen.</span><span class="sxs-lookup"><span data-stu-id="03777-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="03777-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="03777-139">OneDrive for Business</span></span>

<span data-ttu-id="03777-140">Verwenden Sie <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business, </a> um Tools, Protokolle und andere Dateien auf einfache Weise zwischen allen ihren Arbeitsgeräten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="03777-140">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="03777-141">Mit OneDrive können Sie Ihre Arbeitsdateien zwischen ihren Laptops, dem Surface Hub-Desktop und ihren von InTune verwalteten mobilen Geräten freigeben.</span><span class="sxs-lookup"><span data-stu-id="03777-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="03777-142">Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="03777-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="03777-143">Wenn Sie die Größe der Surface-Hub-SSD (128 GB) berücksichtigen und OneDrive auf Ihrem Surface Hub-Desktop Gerät konfigurieren, stellen Sie sicher, dass die Standardkonfiguration darin besteht, die Dateien online zu speichern und während der Verwendung Dateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="03777-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="03777-144">Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung **files on-Demand** fest, um **Speicherplatz zu sparen und während der Verwendung Dateien herunterzuladen**.</span><span class="sxs-lookup"><span data-stu-id="03777-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="03777-145">Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Abfragen und Einrichten von Dateien auf Anforderungsstatus in Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-145">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive-Einstellungen](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="03777-147">Sie können diese Schritte auch wiederholen, um eine persönliche OneDrive zu konfigurieren, aber achten Sie darauf, den Speicherplatz zu sparen und nur Dateien herunterzuladen, wenn Sie Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="03777-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="03777-148">SharePoint und Teams</span><span class="sxs-lookup"><span data-stu-id="03777-148">SharePoint and Teams</span></span>

<span data-ttu-id="03777-149">SharePoint-und Teams-Kanaldateien können mithilfe des OneDrive-Synchronisierungsmoduls auch lokal mit ihren Desktopgeräten wie Laptops und Surface Hubs synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="03777-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="03777-150">So synchronisieren Sie interne Unternehmensdateien mit der OneDrive-Synchronisierungs-App auf Ihr lokales Laufwerk:</span><span class="sxs-lookup"><span data-stu-id="03777-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="03777-151">Wechseln Sie zu einer SharePoint-Website, und navigieren Sie zum Dokumentverzeichnis auf oberster Ebene für Dateien, die Sie auf Ihrem lokalen Gerät anzeigen oder bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="03777-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="03777-152">Wählen Sie auf der Schaltfläche " **Synchronisieren** " oben im SharePoint-Menüband aus.</span><span class="sxs-lookup"><span data-stu-id="03777-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="03777-153">Wählen Sie auf **Öffnen** im Popupfenster aus, auf dem **diese Website versucht, Microsoft OneDrive zu öffnen**.</span><span class="sxs-lookup"><span data-stu-id="03777-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="03777-154">Überprüfen Sie, ob die SharePoint-Dateien mit Ihrem lokalen Laufwerk synchronisiert werden, indem Sie auf das OneDrive-Symbol unten rechts in der Taskleiste klicken.</span><span class="sxs-lookup"><span data-stu-id="03777-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="03777-155">Überprüfen Sie, ob die Konfiguration so eingestellt ist, dass die Dateien online bleiben, und laden Sie die Dateien nur während der Verwendung herunter.</span><span class="sxs-lookup"><span data-stu-id="03777-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="03777-156">Öffnen Sie den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="03777-156">Open file explorer.</span></span>
    
    2. <span data-ttu-id="03777-157">Navigieren Sie zu und klicken Sie mit der rechten Maustaste auf Ihren SharePoint-Namen Beispiel: \*\*contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="03777-157">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="03777-158">Wählen Sie **Speicherplatz freigeben**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-158">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="03777-159">In der Spalte Status wird der Status von Dateien und Ordnern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03777-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="03777-160">Weitere Informationen finden Sie unter <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Synchronisieren von SharePoint-Dateien mit dem OneDrive-synchronisierungsclient </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-160">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="03777-161">Teams-Kanaldateien werden auf SharePoint-Websites mit allen gleichen SharePoint-Dokumentfunktionen wie Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="03777-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="03777-162">So synchronisieren Sie Teams-Kanaldateien:</span><span class="sxs-lookup"><span data-stu-id="03777-162">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="03777-163">Navigieren Sie zu dem Interessenbereich "Teams", und wählen Sie oben die Registerkarte " **Dateien** " aus.</span><span class="sxs-lookup"><span data-stu-id="03777-163">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="03777-164">Wählen Sie dann **Synchronisieren**aus. Die Dateien werden synchronisiert und werden im Datei-Explorer auf dem \*\*Desktop \ Contoso \<name of the Teams Channel\> \*\*angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03777-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="03777-165">Verwenden Sie dasselbe Verfahren, das Sie zum Synchronisieren von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern, und laden Sie Sie nur herunter, wenn Sie Sie verwenden, indem Sie im Datei-Explorer auf den Namen des Teams-Kanals tippen und halten oder mit der rechten Maustaste darauf klicken und dann **Platz freigeben**auswählen.</span><span class="sxs-lookup"><span data-stu-id="03777-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="03777-166">Surface Hub-Stifteinstellungen</span><span class="sxs-lookup"><span data-stu-id="03777-166">Surface Hub pen settings</span></span>

**<span data-ttu-id="03777-167">Koppeln des Bluetooth Surface Hub-Stifts</span><span class="sxs-lookup"><span data-stu-id="03777-167">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="03777-168">Koppeln Sie den Stift, um die Stift-Firmware auf dem neuesten Stand zu halten, und erhalten Sie Informationen zu den Akkuladestatus auf der Seite Bluetooth-Geräteeinstellungen oder in der Surface-App:</span><span class="sxs-lookup"><span data-stu-id="03777-168">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="03777-169">Wählen Sie **Start**  >  **Settings**  >  **Devices**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-169">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="03777-170">Wählen Sie **Bluetooth oder anderes Gerät hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-170">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="03777-171">Wählen Sie **Bluetooth**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-171">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="03777-172">Entfernen Sie die Stift-Endstück-Taste und schütteln, um die Batterie Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="03777-172">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="03777-173">Setzen Sie die Kappe wieder ein, und halten Sie die Kappe gedrückt, bis die Kopplungs-LED blinkt.</span><span class="sxs-lookup"><span data-stu-id="03777-173">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="03777-174">Wählen Sie auf den Surface Hub Bluetooth-Einstellungen die Option **Surface Hub 2 Pen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-174">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="03777-175">Führen Sie den Kopplungsvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="03777-175">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="03777-176">Wenn die Kopplung nicht erfolgreich ist, können Sie versuchen, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="03777-176">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="03777-177">Wenn dies nicht funktioniert, können Sie testen, ob der Akku aufgeladen wird, indem Sie überprüfen, ob der Stift in der Whiteboard-Anwendung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="03777-177">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="03777-178">Wenn dies nicht der Fall ist, ersetzen Sie die Batterie, und versuchen Sie dann, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="03777-178">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="03777-179">Falls erforderlich, starten Sie das Gerät neu, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="03777-179">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="03777-180">**Einrichten von Stifttasten Kombinationen** Der Surface-Hub-Stift hat eine Verknüpfungsschaltfläche, die manchmal auch als "Schwanz Klick" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="03777-180">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="03777-181">Für das Konfigurieren von Tastenkombinationen müssen Sie den Stift zunächst wie zuvor beschrieben koppeln.</span><span class="sxs-lookup"><span data-stu-id="03777-181">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="03777-182">Suchen Sie nach Stift, und wählen Sie **Stift & Windows Ink-Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-182">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="03777-183">Wählen Sie am unteren Rand der Seite Stifttasten Kombinationen aus, die das Dialogfeld öffnen, das hier angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="03777-183">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Stifttasten Kombinationen](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="03777-185">Kamerakonfiguration</span><span class="sxs-lookup"><span data-stu-id="03777-185">Camera configuration</span></span>

<span data-ttu-id="03777-186">Sie können die Kamera oben oder an jeder Seite des Geräts montieren.</span><span class="sxs-lookup"><span data-stu-id="03777-186">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="03777-187">Montieren Sie die Kamera in einer Position, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktop-Standfuß statt mit einem Wagen verwenden oder sich in der Nähe des Hubs befinden.</span><span class="sxs-lookup"><span data-stu-id="03777-187">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="03777-188">Da die Kamera nicht automatisch gedreht wird, benötigen Sie eine 2mm-Sechskant-Taste, um die Kamera manuell zu drehen.</span><span class="sxs-lookup"><span data-stu-id="03777-188">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="03777-189">Weitere Informationen dazu, wie Sie die Kamera seitlich montieren und die Kamera manuell drehen können, finden Sie unter <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S-Kameralinsen Ausrichtung </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-189">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="03777-190">Windows Hello-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="03777-190">Windows Hello configuration</span></span>

<span data-ttu-id="03777-191">Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen.</span><span class="sxs-lookup"><span data-stu-id="03777-191">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="03777-192">Der Surface Hub 2-Fingerabdruckleser-Zubehör kann an einen beliebigen USB-C-Anschluss des Geräts angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="03777-192">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="03777-193">Wenn Sie einen Surface Hub 2-Fingerabdruckleser bestellen oder technische Daten anzeigen möchten, lesen Sie (Surface-Hub-2-Essential-Add-ons.MD "target =" _blank ">Essential Add-ons für Windows 10 pro und Enterprise auf Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-193">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="03777-194">Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie **Start**  >  **Einstellungen**  >  **Accounts**  >  für die**Anmeldeoptionen**  >  **Windows Hello Fingerabdruck** aus, um Ihren Fingerabdruck einzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="03777-194">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="03777-195">Verwenden Sie ein Windows Hello Certified-Gerät für die Flächen Erkennung.</span><span class="sxs-lookup"><span data-stu-id="03777-195">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="03777-196">Die Surface Hub 2S-Kamera unterstützt keine Windows Hello Face-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="03777-196">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="03777-197">Aktivieren eines Symbol Symbols für den Sperrbildschirm auf der Taskleiste</span><span class="sxs-lookup"><span data-stu-id="03777-197">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="03777-198">So fügen Sie der Taskleiste ein Symbol hinzu, das eine Touchscreen-Sperre ähnlich der Windows-L-Tastenkombination ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="03777-198">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="03777-199">Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen Sie **neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**  >  **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-199">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="03777-200">Geben Sie einen Namen für die Verknüpfung ein, beispielsweise " **mein PC sperren**", und wählen Sie dann **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-200">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="03777-201">Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-201">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="03777-202">Geben Sie auf der Registerkarte **Verknüpfung** im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll, Lock Workstation**</span><span class="sxs-lookup"><span data-stu-id="03777-202">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="03777-203">Wählen Sie die Schaltfläche **Symbol ändern** aus, und navigieren Sie zu **C:\Windows\System32\imageres.dll** , und wählen Sie ein Symbol aus, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="03777-203">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="03777-204">Siehe hierzu das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="03777-204">See the following example:</span></span>

    ![Wählen Sie ein Symbol aus.](images/lock.png)
    
1.  <span data-ttu-id="03777-206">Wählen Sie **OK** aus, um die Verknüpfung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="03777-206">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="03777-207">Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die Verknüpfung, und wählen Sie **an Taskleiste anheften**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-207">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="03777-208">Nachdem Sie die Tastenkombination "Sperren" an die Taskleiste angeheftet haben, können Sie Sie vom Desktop löschen.</span><span class="sxs-lookup"><span data-stu-id="03777-208">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="03777-209">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="03777-209">Applications</span></span>

### <span data-ttu-id="03777-210">Aktualisieren von installierten apps</span><span class="sxs-lookup"><span data-stu-id="03777-210">Update installed apps</span></span>

<span data-ttu-id="03777-211">So aktualisieren Sie alle installierten Store-Apps:</span><span class="sxs-lookup"><span data-stu-id="03777-211">To update all installed Store apps:</span></span>

1. <span data-ttu-id="03777-212">Öffnen Sie die Microsoft Store-App, und wählen Sie in der oberen rechten Ecke die Option Weitere Auslassungszeichen **anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="03777-212">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>

2. <span data-ttu-id="03777-213">Klicken Sie auf **Downloads und Updates**.</span><span class="sxs-lookup"><span data-stu-id="03777-213">Select **Downloads and updates**.</span></span>

2. <span data-ttu-id="03777-214">Klicken Sie auf **Updates abrufen**.</span><span class="sxs-lookup"><span data-stu-id="03777-214">Select **Get updates**.</span></span>

### <span data-ttu-id="03777-215">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="03777-215">Microsoft Whiteboard</span></span>

<span data-ttu-id="03777-216">So installieren Sie das Microsoft Whiteboard:</span><span class="sxs-lookup"><span data-stu-id="03777-216">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="03777-217">Wählen Sie unten rechts in der Taskleiste das Symbol für den **Windows-Freihand-Arbeitsbereich** aus, und laden Sie **Whiteboard**herunter.</span><span class="sxs-lookup"><span data-stu-id="03777-217">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Freihand-Arbeitsbereich](images/ink.png) 

<span data-ttu-id="03777-219">Sie können Whiteboard auch über den Microsoft Store installieren:</span><span class="sxs-lookup"><span data-stu-id="03777-219">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="03777-220">Öffnen Sie die Microsoft Store-App, und suchen Sie nach **Whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="03777-220">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="03777-221">Wählen Sie " **Nein** ", wenn Sie sich anmelden und geräteübergreifend verwenden.</span><span class="sxs-lookup"><span data-stu-id="03777-221">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="03777-222">Anheften des Whiteboards an die Taskleiste</span><span class="sxs-lookup"><span data-stu-id="03777-222">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="03777-223">Surface-App</span><span class="sxs-lookup"><span data-stu-id="03777-223">Surface app</span></span>

1. <span data-ttu-id="03777-224">Suchen Sie im Microsoft Store nach **Surface**.</span><span class="sxs-lookup"><span data-stu-id="03777-224">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="03777-225">Setzen Sie den **verfügbaren** Filter auf **alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="03777-225">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="03777-226">Installieren Sie die **Surface** -app.</span><span class="sxs-lookup"><span data-stu-id="03777-226">Install the **Surface** app.</span></span> <span data-ttu-id="03777-227">Dies sollte die erste aufgelistete APP sein.</span><span class="sxs-lookup"><span data-stu-id="03777-227">This should be the first app listed.</span></span> <span data-ttu-id="03777-228">Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die APP installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="03777-228">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="03777-229">Anheften Sie die **Surface** -APP an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="03777-229">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="03777-230">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="03777-230">Snip & Sketch</span></span>

1. <span data-ttu-id="03777-231">Öffnen Sie die APP **Snip & Sketch** , und fixieren Sie Sie an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="03777-231">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="03777-232">Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-232">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="03777-233">Aktivieren Sie in **Einstellungen** **die Option automatisch in Zwischenablage kopieren**, **snips speichern**und **mehrere Fenster** (optional).</span><span class="sxs-lookup"><span data-stu-id="03777-233">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="03777-234">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="03777-234">Microsoft Office</span></span>

1. <span data-ttu-id="03777-235">Öffnen <a href="https://portal.office.com/account#installs" target="_blank"> Sie das Office </a> -Portal, und installieren Sie die gewünschten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="03777-235">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="03777-236">Anheften Sie die gewünschten Office-Anwendungen an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="03777-236">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="03777-237">Wenn Outlook installiert ist, müssen Sie Outlook Ost so einstellen, dass nur der letzte zwei Wochen-Cache gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="03777-237">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="03777-238">Dadurch werden die Datenträgernutzung und die Einrichtungszeit erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="03777-238">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="03777-239">Wählen Sie **Datei**  >  **Kontoeinstellungen** aus, und wählen Sie Ihr Konto aus.</span><span class="sxs-lookup"><span data-stu-id="03777-239">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="03777-240">Wählen Sie **ändern** aus, und legen Sie den Schieberegler für die **Verwendung des Exchange-Cache-Modus** auf 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="03777-240">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="03777-241">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03777-241">Microsoft Teams</span></span>

1. <span data-ttu-id="03777-242">Laden Sie Microsoft Teams herunter, und installieren Sie Sie <a href="https://teams.microsoft.com/downloads" target="_blank"> </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-242">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="03777-243">Konfigurieren Sie die Einstellungen für die automatische Startanwendung (optional).</span><span class="sxs-lookup"><span data-stu-id="03777-243">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="03777-244">Anheften von Teams an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="03777-244">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="03777-245">Sie können die Benachrichtigungen für Teams auf dem Gerät reduzieren, um Ablenkungen zu vermeiden (optional).</span><span class="sxs-lookup"><span data-stu-id="03777-245">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams-Benachrichtigungen](images/teams.png)

### <span data-ttu-id="03777-247">Connect-App</span><span class="sxs-lookup"><span data-stu-id="03777-247">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03777-248">In Windows 10, Version 2004 und höher, ist die Connect-App für drahtlose Projektion unter Verwendung von Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="03777-248">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="03777-249">Wenn Sie Windows-Version 2004 oder höher installiert (oder aktualisiert) haben, wird möglicherweise auf dem Bildschirm Projektion auf diesen PC unter Einstellungen Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="03777-249">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Projekt auf diesem PC](images/sh2-project.png) 


1. <span data-ttu-id="03777-251">Wenn Sie die APP auf der Seite "auf diesen PC projizieren" installieren möchten, wählen Sie **optionale Features**  >  **Add a Feature** und dann die **drahtlose Anzeige** -App aus.</span><span class="sxs-lookup"><span data-stu-id="03777-251">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="03777-252">Unter **einigen Windows-und Android-Geräten können Sie auf diesen PC projizieren, wenn Sie sagen, dass es in Ordnung ist**, wählen Sie:</span><span class="sxs-lookup"><span data-stu-id="03777-252">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="03777-253">**Überall verfügbar** , wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="03777-253">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="03777-254">Wählen Sie andernfalls **überall in sicheren Netzwerken verfügbar**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-254">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="03777-255">Wählen Sie unter **Projekt auf diesem PC anfordern**die Option **nur erstes Mal**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-255">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="03777-256">Wählen Sie unter **PIN für Kopplung anfordern**die Option **nie**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-256">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="03777-257">Wenn Sie die app starten und an die Taskleiste anheften möchten, suchen Sie nach **Connect**.</span><span class="sxs-lookup"><span data-stu-id="03777-257">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="03777-258">Öffnen Sie die app.</span><span class="sxs-lookup"><span data-stu-id="03777-258">Open the app.</span></span> <span data-ttu-id="03777-259">Klicken Sie, während die APP geöffnet ist, mit der rechten Maustaste auf das Symbol "App verbinden" auf der Taskleiste, und wählen Sie **an Taskleiste anheften**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-259">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="03777-260">Schließen Sie dann die Connect-app.</span><span class="sxs-lookup"><span data-stu-id="03777-260">Then close the Connect app.</span></span> <span data-ttu-id="03777-261">**Project auf diesem PC** funktioniert möglicherweise nur, wenn die APP mindestens einmal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="03777-261">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="03777-262">Empfohlene Konfiguration, wenn Sie sich nicht im Unternehmensnetzwerk befinden:</span><span class="sxs-lookup"><span data-stu-id="03777-262">Recommended configuration when not on the corporate network:</span></span>

![Einstellungen zu Hause](images/project1.png)

<span data-ttu-id="03777-264">Empfohlene Konfiguration im Unternehmensnetzwerk:</span><span class="sxs-lookup"><span data-stu-id="03777-264">Recommended configuration on the corporate network:</span></span>

![Einstellungen bei der Arbeit](images/project2.png)

### <span data-ttu-id="03777-266">Ihr Smartphone</span><span class="sxs-lookup"><span data-stu-id="03777-266">Your Phone</span></span>

<span data-ttu-id="03777-267">Die APP **Ihres Telefons** wird unter Windows 10 standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="03777-267">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="03777-268">Wenn Sie nicht vorhanden ist, können Sie Sie auch aus dem Windows Store installieren.</span><span class="sxs-lookup"><span data-stu-id="03777-268">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="03777-269">Informationen zum Einrichten der App finden Sie unter so wird es <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> gemacht: Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten zwischen Ihrem PC und Smartphone </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-269">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="03777-270">Weitere Informationen finden Sie unter <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Beheben häufig auftretender Probleme mit ihrer Telefon-APP unter Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-270">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

### <span data-ttu-id="03777-271">Super Fancy Zones</span><span class="sxs-lookup"><span data-stu-id="03777-271">Super Fancy Zones</span></span>

<span data-ttu-id="03777-272">**Super fancy Zones** hilft Benutzern beim Anordnen von Windows zum Maximieren von Bildschirm Immobilien.</span><span class="sxs-lookup"><span data-stu-id="03777-272">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="03777-273">Sie ist jetzt in <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> auf GitHub enthalten.</span><span class="sxs-lookup"><span data-stu-id="03777-273">It is now included in <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub.</span></span>

### <span data-ttu-id="03777-274">Edge Chrom-Browser</span><span class="sxs-lookup"><span data-stu-id="03777-274">Edge Chromium browser</span></span>

<span data-ttu-id="03777-275">Laden Sie den neuen Edge Chrom-Browser herunter, und installieren Sie ihn <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> </a> .</span><span class="sxs-lookup"><span data-stu-id="03777-275">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="03777-276">Surface Hub-Hardware Diagnosetool</span><span class="sxs-lookup"><span data-stu-id="03777-276">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="03777-277">Das <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub-Hardware Diagnosetool ist </a> kostenlos im Microsoft Store erhältlich.</span><span class="sxs-lookup"><span data-stu-id="03777-277">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="03777-278">Das Tool ist so konzipiert, dass Sie sicherstellen können, dass Ihr Surface Hub optimal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03777-278">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="03777-279">Sie enthält Tests, um festzustellen, ob Ihre Firmware auf dem neuesten Stand ist und richtig konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="03777-279">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="03777-280">Interaktive Tests ermöglichen Ihnen, zu bestätigen, dass die wesentlichen Funktionen wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="03777-280">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="03777-281">Wenn Probleme auftreten, können Ergebnisse gespeichert und für das Surface Hub-Support-Team freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="03777-281">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="03777-282">Klicken Sie auf den Link, um ihn aus dem Microsoft Store zu installieren, und anheften Sie die Anwendung dann an Ihre Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="03777-282">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="03777-283">Zusätzliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="03777-283">Additional settings</span></span>

### <span data-ttu-id="03777-284">Stift Schwanz auswählen, um Whiteboard zu starten</span><span class="sxs-lookup"><span data-stu-id="03777-284">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="03777-285">Suchen Sie nach **Stift** , und wählen Sie **Stift & Windows Ink-Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-285">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="03777-286">**Klicken Sie** am unteren Rand der Seite unter **Stifttasten Kombinationen** auf **Microsoft Whiteboard**auswählen.</span><span class="sxs-lookup"><span data-stu-id="03777-286">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="03777-287">Energieverwaltung</span><span class="sxs-lookup"><span data-stu-id="03777-287">Power management</span></span>

<span data-ttu-id="03777-288">Es stehen mehrere Energieeinstellungen zur Verfügung, mit denen Sie Windows 10 pro oder Enterprise auf Surface Hub 2 optimal nutzen können.</span><span class="sxs-lookup"><span data-stu-id="03777-288">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="03777-289">Dazu gehören Bildschirm-und PC-Timeouts sowie deren Interaktion mit der integrierten Anwesenheitserkennung (Human Presence Detection, Doppler), dem Bildschirmschoner und dem Kennwortschutz und dann, wenn angemessen, wie die Energieeinstellungen für Gruppenrichtlinien, die für Laptops/Desktopbenutzer vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="03777-289">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="03777-290">Mit Windows 10 pro oder Enterprise auf Surface Hub 2 können Sie den Bildschirm nicht über die Fingereingabe, Maus-und Tastaturaktionen sowie über die integrierte Erkennung für die menschliche Benutzungs Erkennung (Human Auslastung Detection, Doppler) in den Standbymodus versetzen.</span><span class="sxs-lookup"><span data-stu-id="03777-290">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="03777-291">Die Erkennung für die menschliche Auslastung ist standardmäßig aktiviert, kann aber bei Bedarf in UEFI deaktiviert werden, indem die Option Device im Surface UEFI Configurator-Tool entweder als Teil der anfänglichen Migration oder durch Erstellen und Anwenden eines späteren UEFI-Konfigurationspakets deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="03777-291">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="03777-292">Energieverwaltung: Bildschirm-und PC-Ruhemodus-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="03777-292">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="03777-293">Wählen Sie **Start**  >  **Einstellungen**  >  **System**  >  **Power & Sleep**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-293">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="03777-294">Stellen Sie den Power Mode-Schieberegler auf **optimale Leistung**ein.</span><span class="sxs-lookup"><span data-stu-id="03777-294">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="03777-295">Konfigurieren Sie die Einstellungen für den Bildschirm und den Ruhezustand nach Ihren wünschen, während Sie auch die Doppler-Anwesenheitserkennung erfassen, die das Gerät aktiviert, wenn Bewegungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="03777-295">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="03777-296">Daher empfiehlt es sich, den Bildschirm so zu konfigurieren, dass er **nach 2 Stunden ausgeschaltet** wird und der PC **nach 4 Stunden ausgeschaltet wird.**</span><span class="sxs-lookup"><span data-stu-id="03777-296">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="03777-297">Energieverwaltung: Bildschirmschoner</span><span class="sxs-lookup"><span data-stu-id="03777-297">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="03777-298">Suchen Sie nach **dem Sperrbildschirm** , und öffnen Sie die Einstellungen für den **Sperrbildschirm**.</span><span class="sxs-lookup"><span data-stu-id="03777-298">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="03777-299">Konfigurieren Sie die Einstellungen für das **Bildschirm Timeout** und die **Bildschirmschonereinstellungen** nach Ihren Wünschen.</span><span class="sxs-lookup"><span data-stu-id="03777-299">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="03777-300">Empfohlene Standardwerte:</span><span class="sxs-lookup"><span data-stu-id="03777-300">Recommended default values are:</span></span>

   - <span data-ttu-id="03777-301">Bildschirmschoner (ohne) oder Bildschirmschoner Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="03777-301">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="03777-302">Wartezeit auf 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="03777-302">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="03777-303">Zeigen Sie auf Resume den Anmeldebildschirm an.</span><span class="sxs-lookup"><span data-stu-id="03777-303">On resume, display logon screen.</span></span>


**<span data-ttu-id="03777-304">Energieverwaltung: Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="03777-304">Power Management: Group Policy</span></span>**

<span data-ttu-id="03777-305">Bevor Sie das folgende Verfahren ausführen, erkundigen Sie sich bei Ihrer IT-Abteilung, ob ein Surface Hub 2S-Gerät aus der globalen Energieverwaltungsrichtlinie ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="03777-305">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="03777-306">Einige Energieverwaltungseinstellungen können die Anwesenheits Erkennungsfunktion deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="03777-306">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="03777-307">Suchen Sie nach **Software Center** , und öffnen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="03777-307">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="03777-308">Wählen Sie **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-308">Select **Options**.</span></span>

3. <span data-ttu-id="03777-309">Erweitern Sie die **Energieverwaltung**  , und wählen Sie **auf diesem Computer keine Energieeinstellungen von meiner IT-Abteilung anwenden aus**.</span><span class="sxs-lookup"><span data-stu-id="03777-309">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Software Einstellungen](images/soft-cntr.png)

### <span data-ttu-id="03777-311">Speicheroptimierung</span><span class="sxs-lookup"><span data-stu-id="03777-311">Storage Sense</span></span>

<span data-ttu-id="03777-312">Der Surface Hub 2 verfügt über eine 128 GB-SSD für den lokalen Speicher, daher ist es notwendig, die Verwendung von Speicher Sparmaßnahmen während der normalen Nutzung zu überdenken.</span><span class="sxs-lookup"><span data-stu-id="03777-312">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="03777-313">So konfigurieren Sie den Speicher Sinn:</span><span class="sxs-lookup"><span data-stu-id="03777-313">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="03777-314">Suchen Sie nach den **Speichereinstellungen**, die unter **System Einstellungen**gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="03777-314">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="03777-315">Wählen Sie unter **Einstellungen**die Option **Speicher Sinn aktivieren** aus, um die Seite **Speicher** Einstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="03777-315">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="03777-316">Stellen Sie den Speicher Sinn auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="03777-316">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="03777-317">Wählen Sie **Speicher Sinn konfigurieren aus, oder führen Sie es jetzt** aus, und konfigurieren Sie die Einstellungen so, dass Dateien so weit wie möglich online bleiben (aufgrund des geringen Festplattenspeichers).</span><span class="sxs-lookup"><span data-stu-id="03777-317">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="03777-318">Empfohlene Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="03777-318">Recommended settings:</span></span>

- <span data-ttu-id="03777-319">Führen Sie den Speicher Sinn = jeden Tag aus.</span><span class="sxs-lookup"><span data-stu-id="03777-319">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="03777-320">Löschen Sie temporäre Dateien, die meine apps nicht verwenden = alle 14 Tage (mindestens).</span><span class="sxs-lookup"><span data-stu-id="03777-320">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="03777-321">Löschen Sie Dateien im Ordner "Downloads", wenn Sie über mehr als = 30 Tage vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="03777-321">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="03777-322">OneDrive: Inhalt wird online – nur, wenn er nicht mehr als = 30 Tage geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="03777-322">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="03777-323">Tabletmodus</span><span class="sxs-lookup"><span data-stu-id="03777-323">Tablet mode</span></span>

<span data-ttu-id="03777-324">Aktivieren Sie den Tablet-Modus, wenn dies für Barrierefreiheitsanforderungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="03777-324">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="03777-325">Sound Einstellungen</span><span class="sxs-lookup"><span data-stu-id="03777-325">Sound settings</span></span>

1. <span data-ttu-id="03777-326">Suchen Sie nach **Sounds-Einstellungen** , und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="03777-326">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="03777-327">Wählen Sie auf der rechten Seite **Sound Control Panel** aus, und klicken Sie auf die Registerkarte **Sounds** .</span><span class="sxs-lookup"><span data-stu-id="03777-327">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="03777-328">Klicken Sie unter **Programmereignisse** auf **Gerät verbinden** und **Gerät trennen** mit **keiner**.</span><span class="sxs-lookup"><span data-stu-id="03777-328">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="03777-329">Benachrichtigungen zum Schweigen</span><span class="sxs-lookup"><span data-stu-id="03777-329">Silence notifications</span></span>

1. <span data-ttu-id="03777-330">Suchen Sie nach **Fokus Unterstützung** , und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="03777-330">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="03777-331">Wählen Sie **nur Erinnerungen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-331">Select **Alarms Only**.</span></span> <span data-ttu-id="03777-332">Dadurch werden keine Konstanten Benachrichtigungs Flyouts vermieden.</span><span class="sxs-lookup"><span data-stu-id="03777-332">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="03777-333">Datenträgerbereinigung</span><span class="sxs-lookup"><span data-stu-id="03777-333">Disk Cleanup</span></span>

1. <span data-ttu-id="03777-334">Suchen Sie nach **Datenträgerbereinigung** , und öffnen Sie diese APP.</span><span class="sxs-lookup"><span data-stu-id="03777-334">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="03777-335">Wählen Sie unter **zu löschende Dateien**die Dateien aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="03777-335">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="03777-336">Wählen Sie auch **Systemdateien bereinigen**aus.</span><span class="sxs-lookup"><span data-stu-id="03777-336">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="03777-337">Fertig stellen und überprüfen</span><span class="sxs-lookup"><span data-stu-id="03777-337">Complete and verify</span></span>

1. <span data-ttu-id="03777-338">Suchen Sie nach allen Windows-Updates, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="03777-338">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="03777-339">Aktualisieren von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="03777-339">Update Group Policy</span></span>

   1. <span data-ttu-id="03777-340">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate force/Boot/Wait: 0**ein.</span><span class="sxs-lookup"><span data-stu-id="03777-340">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="03777-341">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="03777-341">Restart the device.</span></span>

4. <span data-ttu-id="03777-342">Überprüfen der Taskleisten-apps</span><span class="sxs-lookup"><span data-stu-id="03777-342">Verify taskbar apps.</span></span>

   - <span data-ttu-id="03777-343">Connect-App</span><span class="sxs-lookup"><span data-stu-id="03777-343">Connect App</span></span>
   - <span data-ttu-id="03777-344">Symbol "Sperren"</span><span class="sxs-lookup"><span data-stu-id="03777-344">Lock Icon</span></span>
   - <span data-ttu-id="03777-345">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="03777-345">Snip & Sketch</span></span>
   - <span data-ttu-id="03777-346">Teams (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="03777-346">Teams (if applicable)</span></span>
   - <span data-ttu-id="03777-347">Office-Apps (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="03777-347">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="03777-348">Surface-App</span><span class="sxs-lookup"><span data-stu-id="03777-348">Surface App</span></span>
   - <span data-ttu-id="03777-349">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="03777-349">Whiteboard</span></span>
    
5. <span data-ttu-id="03777-350">Überprüfen Sie die Anwesenheitserkennung.</span><span class="sxs-lookup"><span data-stu-id="03777-350">Verify presence detection.</span></span>

   - <span data-ttu-id="03777-351">Die Anwesenheitserkennung ist ein grünes Symbol in der Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="03777-351">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="03777-352">Überprüfen Sie, ob das projizieren auf diesen PC mit der Connect-App aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="03777-352">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="03777-353">Nachdem  **Sie Project auf diese PC** -Einstellungen konfiguriert haben, führen Sie die Connect-App mindestens einmal aus.</span><span class="sxs-lookup"><span data-stu-id="03777-353">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="03777-354">(Anschließend muss die Connect-APP nicht ausgeführt werden, damit Project to Surface Hub projiziert werden kann.)</span><span class="sxs-lookup"><span data-stu-id="03777-354">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="03777-355">Überprüfen Sie die Energie-und Ruhezustandseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="03777-355">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="03777-356">Bildschirmschoner: 15 Minuten, auf (keine), Mystify oder leer; Stellen Sie sicher, dass das Kontrollkästchen für das Anfordern eines Kennworts aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="03777-356">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="03777-357">Bildschirm: Ausschalten **nach 2 Stunden**.</span><span class="sxs-lookup"><span data-stu-id="03777-357">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="03777-358">PC: Ausschalten  **nach 4 Stunden**.</span><span class="sxs-lookup"><span data-stu-id="03777-358">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="03777-359">Überprüfen Sie, ob Windows Hello funktioniert.</span><span class="sxs-lookup"><span data-stu-id="03777-359">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="03777-360">Überprüfen der Synchronisierung Ihre Einstellungen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="03777-360">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="03777-361">Überprüfen von Start-apps.</span><span class="sxs-lookup"><span data-stu-id="03777-361">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="03777-362">Nach der Installation und Konfiguration von Windows 10 kann der Surface Hub 2S genauso wie jedes andere Windows 10-Gerät verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="03777-362">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="03777-363">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="03777-363">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="03777-364">Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="03777-364">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
