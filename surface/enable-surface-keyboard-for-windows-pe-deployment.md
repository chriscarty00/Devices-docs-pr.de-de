---
title: So aktivieren Sie die Surface -Laptop-Tastatur während der MDT-Bereitstellung
description: Wenn Sie MDT zum Bereitstellen von Windows 10 auf Surface Laptops verwenden, müssen Sie Tastaturtreiber für die Verwendung in der Windows PE-Umgebung importieren.
keywords: Windows 10-Oberfläche, automatisieren, anpassen, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312061"
---
# <span data-ttu-id="03a1a-104">So aktivieren Sie die Surface -Laptop-Tastatur während der MDT-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="03a1a-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="03a1a-105">In diesem Artikel wird ein Bereitstellungsansatz behandelt, bei dem Das Microsoft Deployment Toolkit (MDT) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03a1a-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="03a1a-106">Sie können diese Informationen auch auf andere Bereitstellungsmethoden anwenden.</span><span class="sxs-lookup"><span data-stu-id="03a1a-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="03a1a-107">Auf den meisten Arten von Surface-Geräten sollte die Tastatur während der Lite Touch Installation (LTI) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="03a1a-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="03a1a-108">Surface Laptop erfordert jedoch einige zusätzliche Treiber, um die Tastatur zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="03a1a-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="03a1a-109">Für Surface Laptop (1. Generation) und Surface Laptop 2-Geräte müssen Sie die Ordnerstruktur und Auswahlprofile vorbereiten, mit denen Sie Tastaturtreiber für die Verwendung während der Windows Preinstallation Environment (Windows PE)-Phase von LTI angeben können.</span><span class="sxs-lookup"><span data-stu-id="03a1a-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="03a1a-110">Weitere Informationen zu dieser Ordnerstruktur finden Sie unter Bereitstellen eines [Windows 10-Images mithilfe von MDT: Schritt 5: Vorbereiten des Treiberrepositorys.](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)</span><span class="sxs-lookup"><span data-stu-id="03a1a-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="03a1a-111">Wenn Sie Tastaturtreiber für Surface Laptop 2 und Surface Laptop 3 in derselben Windows PE-Startinstanz verwenden, müssen Sie die Firmware möglicherweise manuell zurücksetzen, wenn die Tastatur oder das Touchpad in Windows PE nicht funktionieren:</span><span class="sxs-lookup"><span data-stu-id="03a1a-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="03a1a-112">Halten Sie den Netzschalter 30 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="03a1a-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="03a1a-113">Wenn Sie mit einem Netzteil verbunden sind, drücken und halten Sie den Netzschalter gedrückt, bis das Licht am Ende des Netzkabels kurz ausgeschaltet wird, bevor Sie wieder einschalten.</span><span class="sxs-lookup"><span data-stu-id="03a1a-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03a1a-114">Wenn Sie ein Windows 10-Image auf einem Surface Laptop bereitstellen, auf dem Windows 10 im S-Modus vorinstalliert ist, finden Sie informationen unter KB [4032347, Probleme](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)bei der Bereitstellung von Windows auf Surface-Geräten mit vorinstalliertem Windows 10 im S-Modus.</span><span class="sxs-lookup"><span data-stu-id="03a1a-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="03a1a-115">Führen Sie die folgenden Schritte aus, um dem Auswahlprofil die Tastaturtreiber hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="03a1a-116">Laden Sie die neueste Surface Laptop -MSI-Datei von den entsprechenden Speicherorten herunter:</span><span class="sxs-lookup"><span data-stu-id="03a1a-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="03a1a-117">Surface Laptop (1. Generation) Treiber und Firmware</span><span class="sxs-lookup"><span data-stu-id="03a1a-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="03a1a-118">Surface Laptop 2 Treiber und Firmware</span><span class="sxs-lookup"><span data-stu-id="03a1a-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="03a1a-119">Surface Laptop 3 mit Intel -Prozessortreibern und Firmware</span><span class="sxs-lookup"><span data-stu-id="03a1a-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="03a1a-120">Extrahieren Sie den Inhalt der Surface Laptop-MSI-Datei in einen Ordner, den Sie leicht finden können (z. B. c:\surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="03a1a-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="03a1a-121">Öffnen Sie zum Extrahieren des Inhalts ein Eingabeaufforderungsfenster mit erhöhten Rechten, und führen Sie den Befehl aus dem folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="03a1a-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="03a1a-122">Öffnen Sie die Deployment Workbench, erweitern Sie den Knoten **"Deployment Shares"** und Ihre Bereitstellungsfreigabe, und navigieren Sie dann zum **Ordner "WindowsPEX64".**</span><span class="sxs-lookup"><span data-stu-id="03a1a-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Abbildung des Speicherorts des Ordners WindowsPEX64 in der Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="03a1a-124">Klicken Sie mit der rechten Maustaste auf den **Ordner WindowsPEX64,** und wählen Sie **"Treiber importieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="03a1a-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="03a1a-125">Folgen Sie den Anweisungen im Assistenten zum Importieren von Treibern, um die Treiberordner in den Ordner WindowsPEX64 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="03a1a-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="03a1a-126">Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="03a1a-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="03a1a-127">Die Verzeichnisstruktur beginnt entweder mit SurfacePlatformInstaller (ältere MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien), je nachdem, wann die MSI veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="03a1a-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="03a1a-128">Um Surface Laptop (1. Generation) zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="03a1a-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="03a1a-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="03a1a-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="03a1a-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="03a1a-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="03a1a-133">Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="03a1a-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="03a1a-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="03a1a-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="03a1a-138">Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="03a1a-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="03a1a-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="03a1a-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="03a1a-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="03a1a-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="03a1a-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="03a1a-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="03a1a-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="03a1a-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="03a1a-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="03a1a-146">Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="03a1a-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="03a1a-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="03a1a-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="03a1a-150">SurfaceUpdate\SerialSERIEART</span><span class="sxs-lookup"><span data-stu-id="03a1a-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="03a1a-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="03a1a-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="03a1a-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="03a1a-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="03a1a-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="03a1a-154">Um Surface Laptop 3 mit Intel Processor zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="03a1a-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="03a1a-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="03a1a-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="03a1a-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="03a1a-158">SurfaceUpdate\SerialSERIEART</span><span class="sxs-lookup"><span data-stu-id="03a1a-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="03a1a-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="03a1a-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="03a1a-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="03a1a-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="03a1a-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="03a1a-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="03a1a-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="03a1a-163">Beim Importieren der folgenden Ordner werden vollständige Tastatur-, Trackpad- und Touchfunktionen in PE für Surface Laptop 3 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="03a1a-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="03a1a-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="03a1a-165">SerialIOI2C</span></span>
    - <span data-ttu-id="03a1a-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-166">SerialIOSPI</span></span>
    - <span data-ttu-id="03a1a-167">SerialSERIEART</span><span class="sxs-lookup"><span data-stu-id="03a1a-167">SerialIOUART</span></span>
    - <span data-ttu-id="03a1a-168">itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-168">itouch</span></span>
    - <span data-ttu-id="03a1a-169">Chipsatz</span><span class="sxs-lookup"><span data-stu-id="03a1a-169">Chipset</span></span>
    - <span data-ttu-id="03a1a-170">ChipsatzLPSS</span><span class="sxs-lookup"><span data-stu-id="03a1a-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="03a1a-171">ChipetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="03a1a-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="03a1a-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="03a1a-172">ManagementEngine</span></span>
    - <span data-ttu-id="03a1a-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="03a1a-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="03a1a-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="03a1a-174">SurfaceBattery</span></span>
    - <span data-ttu-id="03a1a-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="03a1a-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="03a1a-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="03a1a-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="03a1a-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="03a1a-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="03a1a-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="03a1a-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="03a1a-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="03a1a-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="03a1a-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="03a1a-180">SurfaceService</span></span>
    - <span data-ttu-id="03a1a-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="03a1a-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="03a1a-182">Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="03a1a-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="03a1a-183">Die Verzeichnisstruktur beginnt entweder mit SurfacePlatformInstaller (ältere MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien), je nachdem, wann die MSI veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="03a1a-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="03a1a-184">Um Surface Laptop (1. Generation) zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="03a1a-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="03a1a-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="03a1a-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="03a1a-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="03a1a-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="03a1a-189">Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="03a1a-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="03a1a-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="03a1a-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="03a1a-194">Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="03a1a-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="03a1a-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="03a1a-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="03a1a-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="03a1a-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="03a1a-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="03a1a-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="03a1a-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="03a1a-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="03a1a-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="03a1a-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="03a1a-202">Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="03a1a-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="03a1a-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="03a1a-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="03a1a-206">SurfaceUpdate\SerialSERIEART</span><span class="sxs-lookup"><span data-stu-id="03a1a-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="03a1a-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="03a1a-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="03a1a-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="03a1a-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="03a1a-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="03a1a-210">Um Surface Laptop 3 mit Intel Processor zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="03a1a-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="03a1a-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="03a1a-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="03a1a-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="03a1a-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="03a1a-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="03a1a-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="03a1a-214">SurfaceUpdate\SerialSERIEART</span><span class="sxs-lookup"><span data-stu-id="03a1a-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="03a1a-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="03a1a-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="03a1a-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="03a1a-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="03a1a-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="03a1a-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="03a1a-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="03a1a-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="03a1a-219">Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="03a1a-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="03a1a-220">Die verbleibenden Surface -Laptop-Treiber befinden sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3".</span><span class="sxs-lookup"><span data-stu-id="03a1a-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="03a1a-221">Stellen Sie sicher, dass der Ordner WindowsPEX64 jetzt die importierten Treiber enthält.</span><span class="sxs-lookup"><span data-stu-id="03a1a-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="03a1a-222">Der Ordner sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-222">The folder should resemble the following:</span></span>  

   ![Abbildung der neu importierten Treiber im Ordner "WindowsPEX64" der Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="03a1a-224">Konfigurieren Sie ein Auswahlprofil, das den Ordner "WindowsPEX64" verwendet.</span><span class="sxs-lookup"><span data-stu-id="03a1a-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="03a1a-225">Das Auswahlprofil sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="03a1a-225">The selection profile should resemble the following:</span></span>  

   ![Abbildung des im Rahmen eines Auswahlprofils ausgewählten WindowsPEX64-Ordners](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="03a1a-227">Konfigurieren Sie die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe wie folgt für die Verwendung des neuen Auswahlprofils:</span><span class="sxs-lookup"><span data-stu-id="03a1a-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="03a1a-228">Wählen **Sie für die**Plattform **x64 aus.**</span><span class="sxs-lookup"><span data-stu-id="03a1a-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="03a1a-229">Wählen **Sie für das**Auswahlprofil das neue Profil aus.</span><span class="sxs-lookup"><span data-stu-id="03a1a-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="03a1a-230">Wählen **Sie "Alle Treiber aus dem Auswahlprofil hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="03a1a-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Abbildung der Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="03a1a-232">Stellen Sie sicher, dass Sie die verbleibenden Surface -Laptop-Treiber mithilfe eines Auswahlprofils oder einer **DriverGroup001-Variablen konfiguriert** haben.</span><span class="sxs-lookup"><span data-stu-id="03a1a-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="03a1a-233">Für Surface Laptop (1. Generation) ist das Modell **Surface Laptop.**</span><span class="sxs-lookup"><span data-stu-id="03a1a-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="03a1a-234">Die verbleibenden Surface -Laptop-Treiber sollten sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop" befinden, wie in der Abbildung unten in dieser Liste dargestellt.</span><span class="sxs-lookup"><span data-stu-id="03a1a-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="03a1a-235">Für Surface Laptop 2 ist surface **Laptop 2 das Modell.**</span><span class="sxs-lookup"><span data-stu-id="03a1a-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="03a1a-236">Die verbleibenden Surface -Laptop-Treiber sollten sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2" befinden.</span><span class="sxs-lookup"><span data-stu-id="03a1a-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="03a1a-237">Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="03a1a-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="03a1a-238">Die verbleibenden Surface -Laptop-Treiber befinden sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3".</span><span class="sxs-lookup"><span data-stu-id="03a1a-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Abbildung der regulären Surface Laptop (1. Generation)-Treiber im Surface Laptop-Ordner der Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="03a1a-240">Nachdem Sie die MDT-Bereitstellungsfreigabe für die Verwendung des neuen Auswahlprofils und der zugehörigen Einstellungen konfiguriert haben, setzen Sie den Bereitstellungsprozess wie in "Bereitstellen eines [Windows 10-Images mit MDT: Schritt 6:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)Erstellen der Bereitstellungs-Tasksequenz" beschrieben fort.</span><span class="sxs-lookup"><span data-stu-id="03a1a-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
