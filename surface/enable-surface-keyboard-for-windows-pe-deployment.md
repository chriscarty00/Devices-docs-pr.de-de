---
title: Aktivieren der Surface-Laptop Tastatur während der MDT-Bereitstellung
description: Wenn Sie das MDT für die Bereitstellung von Windows 10 auf Surface-Laptops verwenden, müssen Sie die Tastaturtreiber importieren, um Sie in der Windows PE-Umgebung verwenden zu können.
keywords: Windows 10 Surface, automatisieren, anpassen, MDT
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
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247307"
---
# <span data-ttu-id="f2892-104">Aktivieren der Surface-Laptop Tastatur während der MDT-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f2892-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="f2892-105">In diesem Artikel wird ein Bereitstellungsansatz behandelt, in dem Microsoft Deployment Toolkit (MDT) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f2892-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="f2892-106">Sie können diese Informationen auch auf andere Bereitstellungsmethoden anwenden.</span><span class="sxs-lookup"><span data-stu-id="f2892-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="f2892-107">Bei den meisten Arten von Surface-Geräten sollte die Tastatur während der Lite Touch-Installation (LTI) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f2892-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="f2892-108">Surface Laptop erfordert jedoch einige zusätzliche Treiber, um die Tastatur zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f2892-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="f2892-109">Für Surface Laptop (1st Generation) und Surface Laptop 2-Geräte müssen Sie die Ordnerstruktur und die Auswahlprofile vorbereiten, mit deren Hilfe Sie während der Windows PE-Phase (Windows Preinstallation Environment) von LTI Tastaturtreiber angeben können.</span><span class="sxs-lookup"><span data-stu-id="f2892-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="f2892-110">Weitere Informationen zu dieser Ordnerstruktur finden Sie unter [Bereitstellen eines Windows 10-Images mithilfe von MDT: Schritt 5: Vorbereiten des Treiber-Repositorys](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="f2892-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f2892-111">Wenn Sie ein Windows 10-Abbild auf einem Surface-Laptop bereitstellen, auf dem Windows 10 im s-Modus vorinstalliert ist, lesen Sie KB [4032347, Probleme beim Bereitstellen von Windows auf Surface-Geräten mit vorinstalliertem Windows 10 im s-Modus](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="f2892-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="f2892-112">Führen Sie die folgenden Schritte aus, um die Tastaturtreiber zum Auswahlprofil hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f2892-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="f2892-113">Laden Sie die neueste msi-Datei für Surface Laptop von den entsprechenden Speicherorten herunter:</span><span class="sxs-lookup"><span data-stu-id="f2892-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="f2892-114">Surface Laptop (1st Gen)-Treiber und-Firmware</span><span class="sxs-lookup"><span data-stu-id="f2892-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="f2892-115">Surface Laptop 2-Treiber und-Firmware</span><span class="sxs-lookup"><span data-stu-id="f2892-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="f2892-116">Surface Laptop 3 mit Intel-Prozessor Treibern und-Firmware</span><span class="sxs-lookup"><span data-stu-id="f2892-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="f2892-117">Extrahieren Sie den Inhalt der MSI-Datei des Surface-Laptops in einen Ordner, den Sie problemlos finden können (beispielsweise "c-surface_laptop_drivers").</span><span class="sxs-lookup"><span data-stu-id="f2892-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="f2892-118">Um den Inhalt zu extrahieren, öffnen Sie ein Eingabeaufforderungsfenster mit erhöhten Rechten, und führen Sie den Befehl aus dem folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="f2892-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="f2892-119">Öffnen Sie die Deployment Workbench, und erweitern Sie den Knoten **Bereitstellung Freigaben** und ihre Bereitstellungsfreigabe, und navigieren Sie dann zum Ordner **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="f2892-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Bild, das den Speicherort des Ordners "WindowsPEX64" in der Deployment Workbench zeigt](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="f2892-121">Klicken Sie mit der rechten Maustaste auf den Ordner **WindowsPEX64** , und wählen Sie **Treiber importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="f2892-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="f2892-122">Folgen Sie den Anweisungen im Assistenten zum Importieren des Treibers, um die Treiberordner in den Ordner WindowsPEX64 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f2892-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f2892-123">Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f2892-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="f2892-124">Die Verzeichnisstruktur wird entweder mit SurfacePlatformInstaller (älteren MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien) gestartet, je nachdem, wann die MSI-Datei veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="f2892-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="f2892-125">Um Surface Laptop (1st Generation) zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="f2892-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="f2892-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="f2892-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="f2892-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="f2892-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f2892-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="f2892-130">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="f2892-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="f2892-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="f2892-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="f2892-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="f2892-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f2892-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="f2892-135">Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="f2892-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="f2892-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="f2892-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="f2892-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="f2892-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="f2892-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="f2892-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="f2892-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="f2892-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="f2892-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="f2892-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f2892-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="f2892-143">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="f2892-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="f2892-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="f2892-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f2892-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="f2892-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f2892-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="f2892-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f2892-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="f2892-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f2892-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="f2892-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f2892-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="f2892-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f2892-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="f2892-151">Wenn Sie Surface Laptop 3 mit Intel-Prozessor unterstützen möchten, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="f2892-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="f2892-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="f2892-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f2892-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="f2892-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f2892-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="f2892-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f2892-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="f2892-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f2892-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="f2892-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f2892-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="f2892-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="f2892-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="f2892-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f2892-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="f2892-160">Beim Importieren der folgenden Ordner werden die vollständige Tastatur-, Trackpad-und Touchfunktionen in PE für Surface Laptop 3 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2892-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="f2892-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="f2892-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f2892-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="f2892-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f2892-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="f2892-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f2892-164">IclSerialIOUART</span></span>
- <span data-ttu-id="f2892-165">iTouch</span><span class="sxs-lookup"><span data-stu-id="f2892-165">itouch</span></span>
- <span data-ttu-id="f2892-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="f2892-166">IclChipset</span></span>
- <span data-ttu-id="f2892-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="f2892-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="f2892-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="f2892-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="f2892-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="f2892-169">ManagementEngine</span></span>
- <span data-ttu-id="f2892-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="f2892-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="f2892-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="f2892-171">SurfaceBattery</span></span>
- <span data-ttu-id="f2892-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="f2892-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="f2892-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f2892-173">SurfaceHidMini</span></span>
- <span data-ttu-id="f2892-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="f2892-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="f2892-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="f2892-175">SurfaceIntegration</span></span>
- <span data-ttu-id="f2892-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f2892-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="f2892-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="f2892-177">SurfaceService</span></span>
- <span data-ttu-id="f2892-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="f2892-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="f2892-179">Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f2892-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="f2892-180">Die Verzeichnisstruktur wird entweder mit SurfacePlatformInstaller (älteren MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien) gestartet, je nachdem, wann die MSI-Datei veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="f2892-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="f2892-181">Um Surface Laptop (1st Generation) zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="f2892-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="f2892-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="f2892-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="f2892-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="f2892-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f2892-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="f2892-186">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="f2892-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="f2892-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="f2892-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="f2892-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="f2892-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f2892-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="f2892-191">Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="f2892-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="f2892-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="f2892-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="f2892-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f2892-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="f2892-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="f2892-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="f2892-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="f2892-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="f2892-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="f2892-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="f2892-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f2892-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="f2892-199">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="f2892-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="f2892-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="f2892-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f2892-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="f2892-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f2892-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="f2892-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f2892-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="f2892-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f2892-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="f2892-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f2892-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="f2892-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f2892-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="f2892-207">Wenn Sie Surface Laptop 3 mit Intel-Prozessor unterstützen möchten, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="f2892-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="f2892-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f2892-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="f2892-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f2892-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="f2892-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f2892-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="f2892-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f2892-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="f2892-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f2892-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="f2892-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f2892-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="f2892-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="f2892-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="f2892-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f2892-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2892-216">Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="f2892-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="f2892-217">Die restlichen Surface-Laptop Treiber befinden sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3-Ordner.</span><span class="sxs-lookup"><span data-stu-id="f2892-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="f2892-218">Überprüfen Sie, ob der WindowsPEX64-Ordner nun die importierten Treiber enthält.</span><span class="sxs-lookup"><span data-stu-id="f2892-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="f2892-219">Der Ordner sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f2892-219">The folder should resemble the following:</span></span>  

   ![Bild, in dem die neu importierten Treiber im Ordner "WindowsPEX64" der Deployment Workbench angezeigt werden](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="f2892-221">Konfigurieren Sie ein Auswahlprofil, das den Ordner "WindowsPEX64" verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2892-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="f2892-222">Das Auswahlprofil sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f2892-222">The selection profile should resemble the following:</span></span>  

   ![Bild, in dem der WindowsPEX64-Ordner angezeigt wird, der als Teil eines Auswahl Profils ausgewählt ist](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="f2892-224">Konfigurieren Sie die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe, um das neue Auswahlprofil wie folgt zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="f2892-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="f2892-225">Wählen Sie unter **Plattform**die Option **x64**aus.</span><span class="sxs-lookup"><span data-stu-id="f2892-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="f2892-226">Wählen Sie im **Auswahlprofil**das neue Profil aus.</span><span class="sxs-lookup"><span data-stu-id="f2892-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="f2892-227">Wählen Sie **alle Treiber aus dem Auswahlprofil einbeziehen aus**.</span><span class="sxs-lookup"><span data-stu-id="f2892-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Bild, in dem die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe angezeigt werden](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="f2892-229">Überprüfen Sie, ob Sie die restlichen Surface-Laptop Treiber mithilfe eines Auswahl Profils oder einer **DriverGroup001** -Variablen konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f2892-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="f2892-230">Für Surface Laptop (1st Generation) ist das Modell **Surface Laptop**.</span><span class="sxs-lookup"><span data-stu-id="f2892-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="f2892-231">Die restlichen Surface-Laptop Treiber sollten sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop-Ordner befinden, wie in der Abbildung dargestellt, die dieser Liste folgt.</span><span class="sxs-lookup"><span data-stu-id="f2892-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="f2892-232">Für Surface Laptop 2 ist das Modell **Surface Laptop 2**.</span><span class="sxs-lookup"><span data-stu-id="f2892-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="f2892-233">Die restlichen Surface-Laptop Treiber sollten sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2-Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="f2892-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="f2892-234">Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="f2892-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="f2892-235">Die restlichen Surface-Laptop Treiber befinden sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3-Ordner.</span><span class="sxs-lookup"><span data-stu-id="f2892-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Abbildung der normalen Surface Laptop-Treiber (1st Gen) im Surface Laptop-Ordner der Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="f2892-237">Nachdem Sie die MDT-Bereitstellungsfreigabe für die Verwendung des neuen Auswahl Profils und der zugehörigen Einstellungen konfiguriert haben, fahren Sie mit dem Bereitstellungsprozess fort, wie unter [Bereitstellen eines Windows 10-Abbilds mit MDT: Schritt 6: Erstellen der Bereitstellungstasksequenz](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2892-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
