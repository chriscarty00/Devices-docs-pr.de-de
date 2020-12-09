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
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203556"
---
# <span data-ttu-id="68c0b-104">Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="68c0b-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="68c0b-105">Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um apps und Einstellungen auf dem Surface Hub 2 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="68c0b-106">Diese Schritte werden empfohlen, um die optimale Benutzerfreundlichkeit bei der Verwendung dieses personalisierten Touchscreen-und Stift Computers zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="68c0b-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="68c0b-107">Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="68c0b-108">Konfigurieren von Systemeinstellungen</span><span class="sxs-lookup"><span data-stu-id="68c0b-108">Configure system settings</span></span>

1. <span data-ttu-id="68c0b-109">Anmelden mit einem Konto, das über lokale Administratorrechte auf dem Gerät verfügt.</span><span class="sxs-lookup"><span data-stu-id="68c0b-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="68c0b-110">Auf Azure AD-verbundenen Geräten wird der Benutzer, der die Azure AD-Verknüpfung ausführt, automatisch der lokalen Administratorgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68c0b-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="68c0b-111">Azure AD Global Administrators und Azure AD Devices-Administratoren sind <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> auch lokale Administratoren </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="68c0b-112">Sie können **net localgroup-Administratoren** an einer Eingabeaufforderung eingeben, um die Konten aufzulisten, die über lokale Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="68c0b-113">Benennen Sie das Gerät mit einem Anzeigenamen um, beispielsweise: **username-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="68c0b-114">Wählen Sie **Start**  >  **Einstellungen**  >  -**Konten**  >  **Synchronisieren Sie Ihre Einstellungen** aus, und deaktivieren Sie die **Synchronisierungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="68c0b-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="68c0b-115">Die hier verwendeten Einstellungen dienen dazu, die optimale Touchscreen-Bildschirmoberfläche zu aktivieren, und daher möchten Sie möglicherweise keine anderen Geräte synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="68c0b-116">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="68c0b-116">Restart the device.</span></span>

## <span data-ttu-id="68c0b-117">Aktivieren der Bildschirmtastatur und des Touchpads</span><span class="sxs-lookup"><span data-stu-id="68c0b-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="68c0b-118">Tippen und halten oder klicken Sie mit der rechten Maustaste auf die Taskleiste, und wählen Sie dann die Schaltfläche **Bildschirmtastatur anzeigen** und die **Schaltfläche Touchpad anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="68c0b-119">Die Bildschirmtastatur ist für die direkte Benutzereingabe hilfreich, und das virtuelle Touchpad hilft bei der präzisen Auswahl, dem Hovern des Bildschirms oder als Alternative zum Tippen und halten für das Klicken mit der rechten Maustaste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="68c0b-120">Nachfolgend sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68c0b-120">See the following example.</span></span>

      ![Touch-Einstellungen](images/touch.png)

2. <span data-ttu-id="68c0b-122">Konfigurieren Sie die Bildschirmtastatur auf QWERTY und unverankert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="68c0b-123">Wählen Sie das **Tastatur** Symbol in der Taskleiste aus, um die Bildschirmtastatur anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="68c0b-124">Wählen Sie auf der Bildschirmtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="68c0b-125">Wählen Sie in der obersten Zeile den neben letzten Tastaturtyp aus, um die QWERTY-Funktion zu aktivieren, und die letzte Option in der zweiten Zeile, um das Floating zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="68c0b-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="68c0b-126">Weitere Informationen finden Sie in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-126">See the following examples.</span></span>

       ![Tastatureinstellungen](images/kbd.png)
 
3. <span data-ttu-id="68c0b-128">Konfigurieren Sie die Einstellungen für die Soft-Tastatur.</span><span class="sxs-lookup"><span data-stu-id="68c0b-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="68c0b-129">Wählen Sie auf der Bildschirmtastatur das Symbol **Einstellungen** aus, oder suchen Sie nach den **Eingabeeinstellungen**, und öffnen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="68c0b-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![Soft Keyboard-Einstellungen](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="68c0b-131">Aktivieren Sie alle Optionen unter Rechtschreibung, Eingabe und Bildschirmtastatur.</span><span class="sxs-lookup"><span data-stu-id="68c0b-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="68c0b-132">Das folgende Beispiel zeigt das Trackpad, das nützlich ist, um zu navigieren und Optionen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="68c0b-133">Die Bildschirmtastatur wird verwendet, um den Microsoft Store zu durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="68c0b-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Verwenden des Trackpads](images/store.png)

## <span data-ttu-id="68c0b-135">Konfigurieren der Bluetooth-Tastatur und-Maus (optional)</span><span class="sxs-lookup"><span data-stu-id="68c0b-135">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="68c0b-136">Schließen Sie eine Tastatur und Maus an, wenn Sie das Gerät als Ihr primäres Windows-Gerät verwenden, oder verwenden Sie es häufig für die Eingabe oder die Genauigkeit der Arbeit.</span><span class="sxs-lookup"><span data-stu-id="68c0b-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="68c0b-137">Wenn sich Ihr Surface-Hub-Gerät in der Nähe eines PCs befindet, können Sie <a href="https://aka.ms/mm" target="_blank"> die Maus ohne Rahmen verwenden, </a> um nahtlos zwischen dem Surface-Hub und dem PC zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="68c0b-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="68c0b-138">Weitere Informationen finden Sie unter <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft-Download aus der Garage: Maus ohne Rahmen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="68c0b-139">Beispiel für ein Taskleisten Layout</span><span class="sxs-lookup"><span data-stu-id="68c0b-139">Example of Taskbar layout</span></span>

<span data-ttu-id="68c0b-140">Nachdem Sie die folgenden Schritte zum Einrichten/Konfigurieren Ihres Surface Hub 2 für Windows 10 Professional oder Enterprise ausgeführt haben, empfiehlt es sich, die am häufigsten verwendeten Anwendungen auf der Taskleiste zu verwenden, um die einzelnen Anwendungen schnell zu starten.</span><span class="sxs-lookup"><span data-stu-id="68c0b-140">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="68c0b-141">Nachfolgend finden Sie ein Beispiel dafür, wie Ihre Taskleiste aussehen könnte:</span><span class="sxs-lookup"><span data-stu-id="68c0b-141">Below is an example of what your taskbar could look like:</span></span>

 ![Taskleisten Layout](images/taskblyt.png)
### <span data-ttu-id="68c0b-143">Aktualisieren von installierten apps</span><span class="sxs-lookup"><span data-stu-id="68c0b-143">Update installed apps</span></span>

<span data-ttu-id="68c0b-144">So aktualisieren Sie alle installierten Store-Apps:</span><span class="sxs-lookup"><span data-stu-id="68c0b-144">To update all installed Store apps:</span></span>

1. <span data-ttu-id="68c0b-145">Öffnen Sie die Microsoft Store-App, und wählen Sie in der oberen rechten Ecke die Option Weitere Auslassungszeichen **anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-145">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="68c0b-146">Wählen Sie **Downloads und Updates aus.**</span><span class="sxs-lookup"><span data-stu-id="68c0b-146">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="68c0b-147">Wählen Sie **Updates abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-147">Select **Get updates**</span></span>

### <span data-ttu-id="68c0b-148">Überprüfen und Installieren aller Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="68c0b-148">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="68c0b-149">Nach der Migration zu Windows 10 Professional oder Windows 10 Enterprise sind möglicherweise Wartungs-und Funktionsupdates verfügbar, die Sie installieren können.</span><span class="sxs-lookup"><span data-stu-id="68c0b-149">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="68c0b-150">Wechseln Sie zu **Einstellungen**  >  **Aktualisieren & Sicherheits** >, und wählen Sie dann **auf Updates überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-150">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="68c0b-151">Wenn Updates vorhanden sind, installieren Sie Sie, starten Sie den Computer neu, und wiederholen Sie den Vorgang, bis die folgende Meldung angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="68c0b-151">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Windows Update-Benachrichtigung "Sie sind aktuell"](images/wustatus.png)


## <span data-ttu-id="68c0b-153">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="68c0b-153">OneDrive for Business</span></span>

<span data-ttu-id="68c0b-154">Verwenden Sie <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business, </a> um Tools, Protokolle und andere Dateien auf einfache Weise zwischen allen ihren Arbeitsgeräten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="68c0b-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="68c0b-155">Mit OneDrive können Sie Ihre Arbeitsdateien zwischen ihren Laptops, dem Surface Hub-Desktop und ihren von InTune verwalteten mobilen Geräten freigeben.</span><span class="sxs-lookup"><span data-stu-id="68c0b-155">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="68c0b-156">Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-156">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="68c0b-157">Wenn Sie die Größe der Surface-Hub-SSD (128 GB) berücksichtigen und OneDrive auf Ihrem Surface Hub-Desktop Gerät konfigurieren, stellen Sie sicher, dass die Standardkonfiguration darin besteht, die Dateien online zu speichern und während der Verwendung Dateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-157">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="68c0b-158">Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung **files on-Demand** fest, um **Speicherplatz zu sparen und während der Verwendung Dateien herunterzuladen**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-158">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="68c0b-159">Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Abfragen und Einrichten von Dateien auf Anforderungsstatus in Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-159">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive-Einstellungen](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="68c0b-161">Sie können diese Schritte auch wiederholen, um eine persönliche OneDrive zu konfigurieren, aber achten Sie darauf, den Speicherplatz zu sparen und nur Dateien herunterzuladen, wenn Sie Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-161">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="68c0b-162">SharePoint und Teams</span><span class="sxs-lookup"><span data-stu-id="68c0b-162">SharePoint and Teams</span></span>

<span data-ttu-id="68c0b-163">SharePoint-und Teams-Kanaldateien können mithilfe des OneDrive-Synchronisierungsmoduls auch lokal mit ihren Desktopgeräten wie Laptops und Surface Hubs synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-163">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="68c0b-164">So synchronisieren Sie interne Unternehmensdateien mit der OneDrive-Synchronisierungs-App auf Ihr lokales Laufwerk:</span><span class="sxs-lookup"><span data-stu-id="68c0b-164">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="68c0b-165">Wechseln Sie zu einer SharePoint-Website, und navigieren Sie zum Dokumentverzeichnis auf oberster Ebene für Dateien, die Sie auf Ihrem lokalen Gerät anzeigen oder bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="68c0b-165">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="68c0b-166">Wählen Sie auf der Schaltfläche " **Synchronisieren** " oben im SharePoint-Menüband aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-166">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="68c0b-167">Wählen Sie auf **Öffnen** im Popupfenster aus, auf dem **diese Website versucht, Microsoft OneDrive zu öffnen**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-167">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="68c0b-168">Überprüfen Sie, ob die SharePoint-Dateien mit Ihrem lokalen Laufwerk synchronisiert werden, indem Sie auf das OneDrive-Symbol unten rechts in der Taskleiste klicken.</span><span class="sxs-lookup"><span data-stu-id="68c0b-168">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="68c0b-169">Überprüfen Sie, ob die Konfiguration so eingestellt ist, dass die Dateien online bleiben, und laden Sie die Dateien nur während der Verwendung herunter.</span><span class="sxs-lookup"><span data-stu-id="68c0b-169">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="68c0b-170">Öffnen Sie den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="68c0b-170">Open file explorer.</span></span>
    
    2. <span data-ttu-id="68c0b-171">Navigieren Sie zu und klicken Sie mit der rechten Maustaste auf Ihren SharePoint-Namen Beispiel: \*\*contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="68c0b-171">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="68c0b-172">Wählen Sie **Speicherplatz freigeben**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-172">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="68c0b-173">In der Spalte Status wird der Status von Dateien und Ordnern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68c0b-173">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="68c0b-174">Weitere Informationen finden Sie unter <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Synchronisieren von SharePoint-Dateien mit dem OneDrive-synchronisierungsclient </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-174">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="68c0b-175">Teams-Kanaldateien werden auf SharePoint-Websites mit allen gleichen SharePoint-Dokumentfunktionen wie Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-175">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="68c0b-176">So synchronisieren Sie Teams-Kanaldateien:</span><span class="sxs-lookup"><span data-stu-id="68c0b-176">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="68c0b-177">Navigieren Sie zu dem Interessenbereich "Teams", und wählen Sie oben die Registerkarte " **Dateien** " aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-177">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="68c0b-178">Wählen Sie dann **Synchronisieren**aus. Die Dateien werden synchronisiert und werden im Datei-Explorer auf dem \*\*Desktop \ Contoso \<name of the Teams Channel\> \*\*angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68c0b-178">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="68c0b-179">Verwenden Sie dasselbe Verfahren, das Sie zum Synchronisieren von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern, und laden Sie Sie nur herunter, wenn Sie Sie verwenden, indem Sie im Datei-Explorer auf den Namen des Teams-Kanals tippen und halten oder mit der rechten Maustaste darauf klicken und dann **Platz freigeben**auswählen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-179">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="68c0b-180">Surface Hub-Stifteinstellungen</span><span class="sxs-lookup"><span data-stu-id="68c0b-180">Surface Hub pen settings</span></span>

**<span data-ttu-id="68c0b-181">Koppeln des Bluetooth Surface Hub-Stifts</span><span class="sxs-lookup"><span data-stu-id="68c0b-181">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="68c0b-182">Koppeln Sie den Stift, um die Stift-Firmware auf dem neuesten Stand zu halten, legen Sie die Tastenkombinationen für den Stift und die Akku Lade Informationen auf der Seite Bluetooth-Geräteeinstellungen oder in der Surface-App ab:</span><span class="sxs-lookup"><span data-stu-id="68c0b-182">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="68c0b-183">Wählen Sie **Start**  >  **Settings**  >  **Devices**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-183">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="68c0b-184">Wählen Sie **Bluetooth oder anderes Gerät hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-184">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="68c0b-185">Wählen Sie **Bluetooth**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-185">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="68c0b-186">Entfernen Sie die Stift-Endstück-Taste und schütteln, um die Batterie Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-186">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="68c0b-187">Setzen Sie die Kappe wieder ein, und halten Sie die Kappe gedrückt, bis die Kopplungs-LED blinkt.</span><span class="sxs-lookup"><span data-stu-id="68c0b-187">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="68c0b-188">Wählen Sie auf den Surface Hub Bluetooth-Einstellungen die Option **Surface Hub 2 Pen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-188">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="68c0b-189">Führen Sie den Kopplungsvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-189">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="68c0b-190">Wenn die Kopplung nicht erfolgreich ist, können Sie versuchen, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="68c0b-190">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="68c0b-191">Wenn dies nicht funktioniert, können Sie testen, ob der Akku aufgeladen wird, indem Sie überprüfen, ob der Stift in der Whiteboard-Anwendung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-191">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="68c0b-192">Wenn dies nicht der Fall ist, ersetzen Sie die Batterie, und versuchen Sie dann, den Stift erneut zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="68c0b-192">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="68c0b-193">Falls erforderlich, starten Sie das Gerät neu, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="68c0b-193">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="68c0b-194">**Einrichten von Stifttasten Kombinationen** Der Surface-Hub-Stift hat eine Verknüpfungsschaltfläche, die manchmal auch als "Schwanz Klick" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="68c0b-194">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="68c0b-195">Für das Konfigurieren von Tastenkombinationen müssen Sie den Stift zunächst wie zuvor beschrieben koppeln.</span><span class="sxs-lookup"><span data-stu-id="68c0b-195">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="68c0b-196">Suchen Sie nach Stift, und wählen Sie **Stift & Windows Ink-Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-196">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="68c0b-197">Wählen Sie am unteren Rand der Seite Stifttasten Kombinationen aus, die das Dialogfeld öffnen, das hier angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="68c0b-197">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Stifttasten Kombinationen](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="68c0b-199">Kamerakonfiguration</span><span class="sxs-lookup"><span data-stu-id="68c0b-199">Camera configuration</span></span>

<span data-ttu-id="68c0b-200">Sie können die Kamera oben oder an jeder Seite des Geräts montieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-200">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="68c0b-201">Montieren Sie die Kamera in einer Position, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktop-Standfuß statt mit einem Wagen verwenden oder sich in der Nähe des Hubs befinden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-201">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="68c0b-202">Da die Kamera nicht automatisch gedreht wird, benötigen Sie eine 2mm-Sechskant-Taste, um die Kamera manuell zu drehen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-202">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="68c0b-203">Weitere Informationen dazu, wie Sie die Kamera seitlich montieren und die Kamera manuell drehen können, finden Sie unter <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S-Kameralinsen Ausrichtung </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-203">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="68c0b-204">Windows Hello-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="68c0b-204">Windows Hello configuration</span></span>

<span data-ttu-id="68c0b-205">Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-205">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="68c0b-206">Der Surface Hub 2-Fingerabdruckleser-Zubehör kann an einen beliebigen USB-C-Anschluss des Geräts angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-206">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="68c0b-207">Wenn Sie einen Surface Hub 2-Fingerabdruckleser bestellen oder technische Daten anzeigen möchten, lesen Sie (Surface-Hub-2-Essential-Add-ons.MD "target =" _blank ">Essential Add-ons für Windows 10 pro und Enterprise auf Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-207">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="68c0b-208">Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie **Start**  >  **Einstellungen**  >  **Accounts**  >  für die**Anmeldeoptionen**  >  **Windows Hello Fingerabdruck** aus, um Ihren Fingerabdruck einzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="68c0b-208">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="68c0b-209">Verwenden Sie ein Windows Hello Certified-Gerät für die Flächen Erkennung.</span><span class="sxs-lookup"><span data-stu-id="68c0b-209">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="68c0b-210">Die Surface Hub 2S-Kamera unterstützt keine Windows Hello Face-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="68c0b-210">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="68c0b-211">Aktivieren eines Symbol Symbols für den Sperrbildschirm auf der Taskleiste</span><span class="sxs-lookup"><span data-stu-id="68c0b-211">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="68c0b-212">So fügen Sie der Taskleiste ein Symbol hinzu, das eine Touchscreen-Sperre ähnlich der Windows-L-Tastenkombination ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="68c0b-212">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="68c0b-213">Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen Sie **neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**  >  **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-213">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="68c0b-214">Geben Sie einen Namen für die Verknüpfung ein, beispielsweise " **mein PC sperren**", und wählen Sie dann **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-214">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="68c0b-215">Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-215">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="68c0b-216">Geben Sie auf der Registerkarte **Verknüpfung** im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll, Lock Workstation**</span><span class="sxs-lookup"><span data-stu-id="68c0b-216">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="68c0b-217">Wählen Sie die Schaltfläche **Symbol ändern** aus, und navigieren Sie zu **C:\Windows\System32\imageres.dll** , und wählen Sie ein Symbol aus, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="68c0b-217">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="68c0b-218">Siehe hierzu das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="68c0b-218">See the following example:</span></span>

    ![Wählen Sie ein Symbol aus.](images/lock.png)
    
1.  <span data-ttu-id="68c0b-220">Wählen Sie **OK** aus, um die Verknüpfung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="68c0b-220">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="68c0b-221">Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die Verknüpfung, und wählen Sie **an Taskleiste anheften**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-221">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="68c0b-222">Nachdem Sie die Tastenkombination "Sperren" an die Taskleiste angeheftet haben, können Sie Sie vom Desktop löschen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-222">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="68c0b-223">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="68c0b-223">Applications</span></span>


### <span data-ttu-id="68c0b-224">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="68c0b-224">Microsoft Whiteboard</span></span>

<span data-ttu-id="68c0b-225">So installieren Sie das Microsoft Whiteboard:</span><span class="sxs-lookup"><span data-stu-id="68c0b-225">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="68c0b-226">Wählen Sie unten rechts in der Taskleiste das Symbol für den **Windows-Freihand-Arbeitsbereich** aus, und laden Sie **Whiteboard**herunter.</span><span class="sxs-lookup"><span data-stu-id="68c0b-226">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Freihand-Arbeitsbereich](images/ink.png) 

<span data-ttu-id="68c0b-228">Sie können Whiteboard auch über den Microsoft Store installieren:</span><span class="sxs-lookup"><span data-stu-id="68c0b-228">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="68c0b-229">Öffnen Sie die Microsoft Store-App, und suchen Sie nach **Whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-229">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="68c0b-230">Wählen Sie " **Nein** ", wenn Sie sich anmelden und geräteübergreifend verwenden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-230">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="68c0b-231">Anheften des Whiteboards an die Taskleiste</span><span class="sxs-lookup"><span data-stu-id="68c0b-231">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="68c0b-232">Surface-App</span><span class="sxs-lookup"><span data-stu-id="68c0b-232">Surface app</span></span>

1. <span data-ttu-id="68c0b-233">Suchen Sie im Microsoft Store nach **Surface**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-233">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="68c0b-234">Setzen Sie den **verfügbaren** Filter auf **alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-234">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="68c0b-235">Installieren Sie die **Surface** -app.</span><span class="sxs-lookup"><span data-stu-id="68c0b-235">Install the **Surface** app.</span></span> <span data-ttu-id="68c0b-236">Dies sollte die erste aufgelistete APP sein.</span><span class="sxs-lookup"><span data-stu-id="68c0b-236">This should be the first app listed.</span></span> <span data-ttu-id="68c0b-237">Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die APP installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="68c0b-237">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="68c0b-238">Anheften Sie die **Surface** -APP an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-238">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="68c0b-239">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="68c0b-239">Snip & Sketch</span></span>

1. <span data-ttu-id="68c0b-240">Öffnen Sie die APP **Snip & Sketch** , und fixieren Sie Sie an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-240">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="68c0b-241">Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-241">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="68c0b-242">Aktivieren Sie in **Einstellungen** **die Option automatisch in Zwischenablage kopieren**, **snips speichern**und **mehrere Fenster** (optional).</span><span class="sxs-lookup"><span data-stu-id="68c0b-242">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="68c0b-243">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="68c0b-243">Microsoft Office</span></span>

1. <span data-ttu-id="68c0b-244">Öffnen <a href="https://portal.office.com/account#installs" target="_blank"> Sie das Office </a> -Portal, und installieren Sie die gewünschten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-244">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="68c0b-245">Anheften Sie die gewünschten Office-Anwendungen an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-245">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="68c0b-246">Wenn Outlook installiert ist, müssen Sie Outlook Ost so einstellen, dass nur der letzte zwei Wochen-Cache gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="68c0b-246">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="68c0b-247">Dadurch werden die Datenträgernutzung und die Einrichtungszeit erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-247">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="68c0b-248">Wählen Sie **Datei**  >  **Kontoeinstellungen** aus, und wählen Sie Ihr Konto aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-248">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="68c0b-249">Wählen Sie **ändern** aus, und legen Sie den Schieberegler für die **Verwendung des Exchange-Cache-Modus** auf 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="68c0b-249">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="68c0b-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68c0b-250">Microsoft Teams</span></span>

1. <span data-ttu-id="68c0b-251">Laden Sie Microsoft Teams herunter, und installieren Sie Sie <a href="https://teams.microsoft.com/downloads" target="_blank"> </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-251">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="68c0b-252">Konfigurieren Sie die Einstellungen für die automatische Startanwendung (optional).</span><span class="sxs-lookup"><span data-stu-id="68c0b-252">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="68c0b-253">Anheften von Teams an die Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-253">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="68c0b-254">Sie können die Benachrichtigungen für Teams auf dem Gerät reduzieren, um Ablenkungen zu vermeiden (optional).</span><span class="sxs-lookup"><span data-stu-id="68c0b-254">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams-Benachrichtigungen](images/teams.png)

### <span data-ttu-id="68c0b-256">Connect-App</span><span class="sxs-lookup"><span data-stu-id="68c0b-256">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68c0b-257">In Windows 10, Version 2004 und höher, ist die Connect-App für drahtlose Projektion unter Verwendung von Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="68c0b-257">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="68c0b-258">Wenn Sie Windows-Version 2004 oder höher installiert (oder aktualisiert) haben, wird möglicherweise auf dem Bildschirm Projektion auf diesen PC unter Einstellungen Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="68c0b-258">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Projekt auf diesem PC](images/sh2-project.png) 


1. <span data-ttu-id="68c0b-260">Wenn Sie die APP auf der Seite "auf diesen PC projizieren" installieren möchten, wählen Sie **optionale Features**  >  **Add a Feature** und dann die **drahtlose Anzeige** -App aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-260">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="68c0b-261">Unter **einigen Windows-und Android-Geräten können Sie auf diesen PC projizieren, wenn Sie sagen, dass es in Ordnung ist**, wählen Sie:</span><span class="sxs-lookup"><span data-stu-id="68c0b-261">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="68c0b-262">**Überall verfügbar** , wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="68c0b-262">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="68c0b-263">Wählen Sie andernfalls **überall in sicheren Netzwerken verfügbar**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-263">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="68c0b-264">Wählen Sie unter **Projekt auf diesem PC anfordern**die Option **nur erstes Mal**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-264">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="68c0b-265">Wählen Sie unter **PIN für Kopplung anfordern**die Option **nie**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-265">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="68c0b-266">Wenn Sie die app starten und an die Taskleiste anheften möchten, suchen Sie nach **Connect**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-266">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="68c0b-267">Öffnen Sie die app.</span><span class="sxs-lookup"><span data-stu-id="68c0b-267">Open the app.</span></span> <span data-ttu-id="68c0b-268">Klicken Sie, während die APP geöffnet ist, mit der rechten Maustaste auf das Symbol "App verbinden" auf der Taskleiste, und wählen Sie **an Taskleiste anheften**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-268">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="68c0b-269">Schließen Sie dann die Connect-app.</span><span class="sxs-lookup"><span data-stu-id="68c0b-269">Then close the Connect app.</span></span> <span data-ttu-id="68c0b-270">**Project auf diesem PC** funktioniert möglicherweise nur, wenn die APP mindestens einmal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="68c0b-270">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="68c0b-271">Empfohlene Konfiguration, wenn Sie sich nicht im Unternehmensnetzwerk befinden:</span><span class="sxs-lookup"><span data-stu-id="68c0b-271">Recommended configuration when not on the corporate network:</span></span>

![Einstellungen zu Hause](images/project1.png)

<span data-ttu-id="68c0b-273">Empfohlene Konfiguration im Unternehmensnetzwerk:</span><span class="sxs-lookup"><span data-stu-id="68c0b-273">Recommended configuration on the corporate network:</span></span>

![Einstellungen bei der Arbeit](images/project2.png)

### <span data-ttu-id="68c0b-275">Ihr Smartphone</span><span class="sxs-lookup"><span data-stu-id="68c0b-275">Your Phone</span></span>

<span data-ttu-id="68c0b-276">Die APP **Ihres Telefons** wird unter Windows 10 standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-276">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="68c0b-277">Wenn Sie nicht vorhanden ist, können Sie Sie auch aus dem Windows Store installieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-277">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="68c0b-278">Informationen zum Einrichten der App finden Sie unter so wird es <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> gemacht: Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten zwischen Ihrem PC und Smartphone </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-278">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="68c0b-279">Weitere Informationen finden Sie unter <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Beheben häufig auftretender Probleme mit ihrer Telefon-APP unter Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-279">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <span data-ttu-id="68c0b-280">Fancy Zones</span><span class="sxs-lookup"><span data-stu-id="68c0b-280">Fancy Zones</span></span>


<span data-ttu-id="68c0b-281">**Fancy Zones** ist Teil einer Sammlung von Tools namens <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="68c0b-281">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="68c0b-282">Es ist eine großartige Möglichkeit, um den Bildschirm "Real Estate" auf einem Surface Hub 2 zu verwenden, indem Sie die Möglichkeit haben, feste Layouts auf dem Display ("Zonen") zu definieren, und dann auszuwählen, welche app dann in den einzelnen Zonen ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="68c0b-282">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="68c0b-283">Das [PowerToys-wiki](https://github.com/microsoft/PowerToys/wiki) enthält Anleitungen zum verwenden und Anpassen der einzelnen Tools, einschließlich [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="68c0b-283">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="68c0b-284">Auf einem hohen Niveau – nach der Installation von PowerToys können Sie ein benutzerdefiniertes Layout auswählen oder erstellen und dann die UMSCHALTTASTE gedrückt halten und die Tastenkombination ziehen oder verwenden, um eine ausgeführte app in bestimmte Zonen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="68c0b-284">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="68c0b-285">Die Verwendung einer Bluetooth-oder USB-Tastatur und-Maus hilft Ihnen dabei, oder Sie können die Bildschirmtastatur und das Touchpad verwenden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-285">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="68c0b-286">Power Toys-Tipps</span><span class="sxs-lookup"><span data-stu-id="68c0b-286">Power toys tips</span></span>**
- <span data-ttu-id="68c0b-287">Um e-Mail-Benachrichtigungen über PowerToys-Versionsupdates auf GitHub zu erhalten, klicken Sie oben auf der [Seite](https://github.com/microsoft/PowerToys/releases)auf die Schaltfläche "Anmelden".</span><span class="sxs-lookup"><span data-stu-id="68c0b-287">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="68c0b-288">Sobald PowerToys installiert ist, können Sie Windows-Benachrichtigungen empfangen und/oder die neuesten Updates herunterladen und installieren, indem Sie die Einstellungen für den PowerToys- **Download automatisch** auf ein konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-288">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="68c0b-289">Um zu den PowerToys-Einstellungen zu gelangen, wählen Sie in der Taskleiste die auf Carat **ausgeführten apps** aus, und klicken Sie dann mit der rechten Maustaste, oder halten Sie das PowerToys-Symbol gedrückt, bis das Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="68c0b-289">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="68c0b-290">Wählen Sie "Einstellungen" aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-290">Select “Settings”.</span></span>
- <span data-ttu-id="68c0b-291">Aktivieren Sie unten auf der Seite PowerToys-Einstellungen die Option **Updates automatisch herunterladen** auf ein.</span><span class="sxs-lookup"><span data-stu-id="68c0b-291">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="68c0b-292">Wenn ein Update veröffentlicht wurde, wird eine Windows-Benachrichtigung angezeigt, die Ihnen die Möglichkeit bietet, das Update zu installieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-292">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <span data-ttu-id="68c0b-293">Edge Chrom-Browser</span><span class="sxs-lookup"><span data-stu-id="68c0b-293">Edge Chromium browser</span></span>

<span data-ttu-id="68c0b-294">Laden Sie den neuen Edge Chrom-Browser herunter, und installieren Sie ihn <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> </a> .</span><span class="sxs-lookup"><span data-stu-id="68c0b-294">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="68c0b-295">Surface Hub-Hardware Diagnosetool</span><span class="sxs-lookup"><span data-stu-id="68c0b-295">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="68c0b-296">Das <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub-Hardware Diagnosetool ist </a> kostenlos im Microsoft Store erhältlich.</span><span class="sxs-lookup"><span data-stu-id="68c0b-296">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="68c0b-297">Das Tool ist so konzipiert, dass Sie sicherstellen können, dass Ihr Surface Hub optimal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68c0b-297">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="68c0b-298">Sie enthält Tests, um festzustellen, ob Ihre Firmware auf dem neuesten Stand ist und richtig konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="68c0b-298">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="68c0b-299">Interaktive Tests ermöglichen Ihnen, zu bestätigen, dass die wesentlichen Funktionen wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-299">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="68c0b-300">Wenn Probleme auftreten, können Ergebnisse gespeichert und für das Surface Hub-Support-Team freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-300">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="68c0b-301">Klicken Sie auf den Link, um ihn aus dem Microsoft Store zu installieren, und anheften Sie die Anwendung dann an Ihre Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-301">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="68c0b-302">Zusätzliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="68c0b-302">Additional settings</span></span>

### <span data-ttu-id="68c0b-303">Stift Schwanz auswählen, um Whiteboard zu starten</span><span class="sxs-lookup"><span data-stu-id="68c0b-303">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="68c0b-304">Suchen Sie nach **Stift** , und wählen Sie **Stift & Windows Ink-Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-304">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="68c0b-305">**Klicken Sie** am unteren Rand der Seite unter **Stifttasten Kombinationen** auf **Microsoft Whiteboard**auswählen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-305">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="68c0b-306">Energieverwaltung</span><span class="sxs-lookup"><span data-stu-id="68c0b-306">Power management</span></span>

<span data-ttu-id="68c0b-307">Es stehen mehrere Energieeinstellungen zur Verfügung, mit denen Sie Windows 10 pro oder Enterprise auf Surface Hub 2 optimal nutzen können.</span><span class="sxs-lookup"><span data-stu-id="68c0b-307">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="68c0b-308">Dazu gehören Bildschirm-und PC-Timeouts sowie deren Interaktion mit der integrierten Anwesenheitserkennung (Human Presence Detection, Doppler), dem Bildschirmschoner und dem Kennwortschutz und dann, wenn angemessen, wie die Energieeinstellungen für Gruppenrichtlinien, die für Laptops/Desktopbenutzer vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="68c0b-308">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="68c0b-309">Mit Windows 10 pro oder Enterprise auf Surface Hub 2 können Sie den Bildschirm nicht über die Fingereingabe, Maus-und Tastaturaktionen sowie über die integrierte Erkennung für die menschliche Benutzungs Erkennung (Human Auslastung Detection, Doppler) in den Standbymodus versetzen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-309">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="68c0b-310">Die Erkennung für die menschliche Auslastung ist standardmäßig aktiviert, kann aber bei Bedarf in UEFI deaktiviert werden, indem die Option Device im Surface UEFI Configurator-Tool entweder als Teil der anfänglichen Migration oder durch Erstellen und Anwenden eines späteren UEFI-Konfigurationspakets deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="68c0b-310">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="68c0b-311">Energieverwaltung: Bildschirm-und PC-Ruhemodus-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="68c0b-311">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="68c0b-312">Wählen Sie **Start**  >  **Einstellungen**  >  **System**  >  **Power & Sleep**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-312">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="68c0b-313">Stellen Sie den Power Mode-Schieberegler auf **optimale Leistung**ein.</span><span class="sxs-lookup"><span data-stu-id="68c0b-313">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="68c0b-314">Konfigurieren Sie die Einstellungen für den Bildschirm und den Ruhezustand nach Ihren wünschen, während Sie auch die Doppler-Anwesenheitserkennung erfassen, die das Gerät aktiviert, wenn Bewegungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-314">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="68c0b-315">Daher empfiehlt es sich, den Bildschirm so zu konfigurieren, dass er **nach 2 Stunden ausgeschaltet** wird und der PC **nach 4 Stunden ausgeschaltet wird.**</span><span class="sxs-lookup"><span data-stu-id="68c0b-315">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="68c0b-316">Energieverwaltung: Bildschirmschoner</span><span class="sxs-lookup"><span data-stu-id="68c0b-316">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="68c0b-317">Suchen Sie nach **dem Sperrbildschirm** , und öffnen Sie die Einstellungen für den **Sperrbildschirm**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-317">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="68c0b-318">Konfigurieren Sie die Einstellungen für das **Bildschirm Timeout** und die **Bildschirmschonereinstellungen** nach Ihren Wünschen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-318">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="68c0b-319">Empfohlene Standardwerte:</span><span class="sxs-lookup"><span data-stu-id="68c0b-319">Recommended default values are:</span></span>

   - <span data-ttu-id="68c0b-320">Bildschirmschoner (ohne) oder Bildschirmschoner Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="68c0b-320">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="68c0b-321">Wartezeit auf 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="68c0b-321">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="68c0b-322">Zeigen Sie auf Resume den Anmeldebildschirm an.</span><span class="sxs-lookup"><span data-stu-id="68c0b-322">On resume, display logon screen.</span></span>


**<span data-ttu-id="68c0b-323">Energieverwaltung: Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="68c0b-323">Power Management: Group Policy</span></span>**

<span data-ttu-id="68c0b-324">Bevor Sie das folgende Verfahren ausführen, erkundigen Sie sich bei Ihrer IT-Abteilung, ob ein Surface Hub 2S-Gerät aus der globalen Energieverwaltungsrichtlinie ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="68c0b-324">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="68c0b-325">Einige Energieverwaltungseinstellungen können die Anwesenheits Erkennungsfunktion deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="68c0b-325">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="68c0b-326">Suchen Sie nach **Software Center** , und öffnen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="68c0b-326">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="68c0b-327">Wählen Sie **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-327">Select **Options**.</span></span>

3. <span data-ttu-id="68c0b-328">Erweitern Sie die **Energieverwaltung**  , und wählen Sie **auf diesem Computer keine Energieeinstellungen von meiner IT-Abteilung anwenden aus**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-328">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Software Einstellungen](images/soft-cntr.png)

### <span data-ttu-id="68c0b-330">Speicheroptimierung</span><span class="sxs-lookup"><span data-stu-id="68c0b-330">Storage Sense</span></span>

<span data-ttu-id="68c0b-331">Der Surface Hub 2 verfügt über eine 128 GB-SSD für den lokalen Speicher, daher ist es notwendig, die Verwendung von Speicher Sparmaßnahmen während der normalen Nutzung zu überdenken.</span><span class="sxs-lookup"><span data-stu-id="68c0b-331">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="68c0b-332">So konfigurieren Sie den Speicher Sinn:</span><span class="sxs-lookup"><span data-stu-id="68c0b-332">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="68c0b-333">Suchen Sie nach den **Speichereinstellungen**, die unter **System Einstellungen**gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-333">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="68c0b-334">Wählen Sie unter **Einstellungen**die Option **Speicher Sinn aktivieren** aus, um die Seite **Speicher** Einstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-334">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="68c0b-335">Stellen Sie den Speicher Sinn auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-335">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="68c0b-336">Wählen Sie **Speicher Sinn konfigurieren aus, oder führen Sie es jetzt** aus, und konfigurieren Sie die Einstellungen so, dass Dateien so weit wie möglich online bleiben (aufgrund des geringen Festplattenspeichers).</span><span class="sxs-lookup"><span data-stu-id="68c0b-336">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="68c0b-337">Empfohlene Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="68c0b-337">Recommended settings:</span></span>

- <span data-ttu-id="68c0b-338">Führen Sie den Speicher Sinn = jeden Tag aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-338">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="68c0b-339">Löschen Sie temporäre Dateien, die meine apps nicht verwenden = alle 14 Tage (mindestens).</span><span class="sxs-lookup"><span data-stu-id="68c0b-339">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="68c0b-340">Löschen Sie Dateien im Ordner "Downloads", wenn Sie über mehr als = 30 Tage vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="68c0b-340">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="68c0b-341">OneDrive: Inhalt wird online – nur, wenn er nicht mehr als = 30 Tage geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="68c0b-341">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="68c0b-342">Tabletmodus</span><span class="sxs-lookup"><span data-stu-id="68c0b-342">Tablet mode</span></span>

<span data-ttu-id="68c0b-343">Aktivieren Sie den Tablet-Modus, wenn dies für Barrierefreiheitsanforderungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="68c0b-343">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="68c0b-344">Sound Einstellungen</span><span class="sxs-lookup"><span data-stu-id="68c0b-344">Sound settings</span></span>

1. <span data-ttu-id="68c0b-345">Suchen Sie nach **Sounds-Einstellungen** , und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="68c0b-345">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="68c0b-346">Wählen Sie auf der rechten Seite **Sound Control Panel** aus, und klicken Sie auf die Registerkarte **Sounds** .</span><span class="sxs-lookup"><span data-stu-id="68c0b-346">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="68c0b-347">Klicken Sie unter **Programmereignisse** auf **Gerät verbinden** und **Gerät trennen** mit **keiner**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-347">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="68c0b-348">Benachrichtigungen zum Schweigen</span><span class="sxs-lookup"><span data-stu-id="68c0b-348">Silence notifications</span></span>

1. <span data-ttu-id="68c0b-349">Suchen Sie nach **Fokus Unterstützung** , und öffnen Sie diese Seite.</span><span class="sxs-lookup"><span data-stu-id="68c0b-349">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="68c0b-350">Wählen Sie **nur Erinnerungen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-350">Select **Alarms Only**.</span></span> <span data-ttu-id="68c0b-351">Dadurch werden keine Konstanten Benachrichtigungs Flyouts vermieden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-351">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="68c0b-352">Datenträgerbereinigung</span><span class="sxs-lookup"><span data-stu-id="68c0b-352">Disk Cleanup</span></span>

1. <span data-ttu-id="68c0b-353">Suchen Sie nach **Datenträgerbereinigung** , und öffnen Sie diese APP.</span><span class="sxs-lookup"><span data-stu-id="68c0b-353">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="68c0b-354">Wählen Sie unter **zu löschende Dateien**die Dateien aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="68c0b-354">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="68c0b-355">Wählen Sie auch **Systemdateien bereinigen**aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-355">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="68c0b-356">Fertig stellen und überprüfen</span><span class="sxs-lookup"><span data-stu-id="68c0b-356">Complete and verify</span></span>

1. <span data-ttu-id="68c0b-357">Suchen Sie nach allen Windows-Updates, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="68c0b-357">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="68c0b-358">Aktualisieren Sie die Gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="68c0b-358">Update Group Policy.</span></span>

   1. <span data-ttu-id="68c0b-359">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate force/Boot/Wait: 0**ein.</span><span class="sxs-lookup"><span data-stu-id="68c0b-359">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="68c0b-360">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="68c0b-360">Restart the device.</span></span>

4. <span data-ttu-id="68c0b-361">Überprüfen der Taskleisten-apps</span><span class="sxs-lookup"><span data-stu-id="68c0b-361">Verify taskbar apps.</span></span>

   - <span data-ttu-id="68c0b-362">Connect-App</span><span class="sxs-lookup"><span data-stu-id="68c0b-362">Connect App</span></span>
   - <span data-ttu-id="68c0b-363">Symbol "Sperren"</span><span class="sxs-lookup"><span data-stu-id="68c0b-363">Lock Icon</span></span>
   - <span data-ttu-id="68c0b-364">Ausschneiden und skizzieren</span><span class="sxs-lookup"><span data-stu-id="68c0b-364">Snip & Sketch</span></span>
   - <span data-ttu-id="68c0b-365">Teams (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="68c0b-365">Teams (if applicable)</span></span>
   - <span data-ttu-id="68c0b-366">Office-Apps (falls zutreffend)</span><span class="sxs-lookup"><span data-stu-id="68c0b-366">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="68c0b-367">Surface-App</span><span class="sxs-lookup"><span data-stu-id="68c0b-367">Surface App</span></span>
   - <span data-ttu-id="68c0b-368">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="68c0b-368">Whiteboard</span></span>
    
5. <span data-ttu-id="68c0b-369">Überprüfen Sie die Anwesenheitserkennung.</span><span class="sxs-lookup"><span data-stu-id="68c0b-369">Verify presence detection.</span></span>

   - <span data-ttu-id="68c0b-370">Die Anwesenheitserkennung ist ein grünes Symbol in der Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="68c0b-370">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="68c0b-371">Überprüfen Sie, ob das projizieren auf diesen PC mit der Connect-App aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="68c0b-371">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="68c0b-372">Nachdem  **Sie Project auf diese PC** -Einstellungen konfiguriert haben, führen Sie die Connect-App mindestens einmal aus.</span><span class="sxs-lookup"><span data-stu-id="68c0b-372">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="68c0b-373">(Anschließend muss die Connect-APP nicht ausgeführt werden, damit Project to Surface Hub projiziert werden kann.)</span><span class="sxs-lookup"><span data-stu-id="68c0b-373">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="68c0b-374">Überprüfen Sie die Energie-und Ruhezustandseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="68c0b-374">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="68c0b-375">Bildschirmschoner: 15 Minuten, auf (keine), Mystify oder leer; Stellen Sie sicher, dass das Kontrollkästchen für das Anfordern eines Kennworts aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="68c0b-375">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="68c0b-376">Bildschirm: Ausschalten **nach 2 Stunden**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-376">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="68c0b-377">PC: Ausschalten  **nach 4 Stunden**.</span><span class="sxs-lookup"><span data-stu-id="68c0b-377">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="68c0b-378">Überprüfen Sie, ob Windows Hello funktioniert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-378">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="68c0b-379">Überprüfen der Synchronisierung Ihre Einstellungen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="68c0b-379">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="68c0b-380">Überprüfen von Start-apps.</span><span class="sxs-lookup"><span data-stu-id="68c0b-380">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="68c0b-381">Nach der Installation und Konfiguration von Windows 10 kann der Surface Hub 2S genauso wie jedes andere Windows 10-Gerät verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="68c0b-381">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="68c0b-382">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="68c0b-382">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="68c0b-383">Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="68c0b-383">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
