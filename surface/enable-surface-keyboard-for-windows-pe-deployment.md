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
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832554"
---
# <span data-ttu-id="5b0f3-104">Aktivieren der Surface-Laptop Tastatur während der MDT-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5b0f3-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="5b0f3-105">In diesem Artikel wird ein Bereitstellungsansatz behandelt, in dem Microsoft Deployment Toolkit (MDT) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="5b0f3-106">Sie können diese Informationen auch auf andere Bereitstellungsmethoden anwenden.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="5b0f3-107">Bei den meisten Arten von Surface-Geräten sollte die Tastatur während der Lite Touch-Installation (LTI) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="5b0f3-108">Surface Laptop erfordert jedoch einige zusätzliche Treiber, um die Tastatur zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="5b0f3-109">Für Surface Laptop (1st Generation) und Surface Laptop 2-Geräte müssen Sie die Ordnerstruktur und die Auswahlprofile vorbereiten, mit deren Hilfe Sie während der Windows PE-Phase (Windows Preinstallation Environment) von LTI Tastaturtreiber angeben können.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="5b0f3-110">Weitere Informationen zu dieser Ordnerstruktur finden Sie unter [Bereitstellen eines Windows 10-Images mithilfe von MDT: Schritt 5: Vorbereiten des Treiber-Repositorys](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="5b0f3-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="5b0f3-111">Das Hinzufügen von Surface Laptop 2-und Surface Laptop 3-Tastaturtreibern in derselben Windows PE-Start Instanz aufgrund eines Treiber Konflikts wird derzeit nicht unterstützt. Verwenden Sie stattdessen separate Instanzen.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b0f3-112">Wenn Sie ein Windows 10-Abbild auf einem Surface-Laptop bereitstellen, auf dem Windows 10 im s-Modus vorinstalliert ist, lesen Sie KB [4032347, Probleme beim Bereitstellen von Windows auf Surface-Geräten mit vorinstalliertem Windows 10 im s-Modus](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="5b0f3-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="5b0f3-113">Führen Sie die folgenden Schritte aus, um die Tastaturtreiber zum Auswahlprofil hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="5b0f3-114">Laden Sie die neueste msi-Datei für Surface Laptop von den entsprechenden Speicherorten herunter:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="5b0f3-115">Surface Laptop (1st Gen)-Treiber und-Firmware</span><span class="sxs-lookup"><span data-stu-id="5b0f3-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="5b0f3-116">Surface Laptop 2-Treiber und-Firmware</span><span class="sxs-lookup"><span data-stu-id="5b0f3-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="5b0f3-117">Surface Laptop 3 mit Intel-Prozessor Treibern und-Firmware</span><span class="sxs-lookup"><span data-stu-id="5b0f3-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="5b0f3-118">Extrahieren Sie den Inhalt der MSI-Datei des Surface-Laptops in einen Ordner, den Sie problemlos finden können (beispielsweise "c-surface_laptop_drivers").</span><span class="sxs-lookup"><span data-stu-id="5b0f3-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="5b0f3-119">Um den Inhalt zu extrahieren, öffnen Sie ein Eingabeaufforderungsfenster mit erhöhten Rechten, und führen Sie den Befehl aus dem folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="5b0f3-120">Öffnen Sie die Deployment Workbench, und erweitern Sie den Knoten **Bereitstellung Freigaben** und ihre Bereitstellungsfreigabe, und navigieren Sie dann zum Ordner **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="5b0f3-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Bild, das den Speicherort des Ordners "WindowsPEX64" in der Deployment Workbench zeigt](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="5b0f3-122">Klicken Sie mit der rechten Maustaste auf den Ordner **WindowsPEX64** , und wählen Sie **Treiber importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="5b0f3-123">Folgen Sie den Anweisungen im Assistenten zum Importieren des Treibers, um die Treiberordner in den Ordner WindowsPEX64 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5b0f3-124">Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="5b0f3-125">Die Verzeichnisstruktur wird entweder mit SurfacePlatformInstaller (älteren MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien) gestartet, je nachdem, wann die MSI-Datei veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="5b0f3-126">Um Surface Laptop (1st Generation) zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="5b0f3-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="5b0f3-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="5b0f3-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="5b0f3-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="5b0f3-131">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="5b0f3-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="5b0f3-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="5b0f3-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="5b0f3-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="5b0f3-136">Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="5b0f3-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="5b0f3-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="5b0f3-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="5b0f3-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="5b0f3-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="5b0f3-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="5b0f3-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="5b0f3-144">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="5b0f3-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="5b0f3-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="5b0f3-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="5b0f3-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="5b0f3-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5b0f3-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="5b0f3-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5b0f3-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="5b0f3-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="5b0f3-152">Wenn Sie Surface Laptop 3 mit Intel-Prozessor unterstützen möchten, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="5b0f3-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="5b0f3-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="5b0f3-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="5b0f3-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="5b0f3-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5b0f3-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="5b0f3-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5b0f3-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="5b0f3-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="5b0f3-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="5b0f3-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="5b0f3-161">Beim Importieren der folgenden Ordner werden die vollständige Tastatur-, Trackpad-und Touchfunktionen in PE für Surface Laptop 3 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="5b0f3-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="5b0f3-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="5b0f3-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="5b0f3-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-165">IclSerialIOUART</span></span>
- <span data-ttu-id="5b0f3-166">iTouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-166">itouch</span></span>
- <span data-ttu-id="5b0f3-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="5b0f3-167">IclChipset</span></span>
- <span data-ttu-id="5b0f3-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="5b0f3-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="5b0f3-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="5b0f3-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="5b0f3-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="5b0f3-170">ManagementEngine</span></span>
- <span data-ttu-id="5b0f3-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="5b0f3-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="5b0f3-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="5b0f3-172">SurfaceBattery</span></span>
- <span data-ttu-id="5b0f3-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="5b0f3-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="5b0f3-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5b0f3-174">SurfaceHidMini</span></span>
- <span data-ttu-id="5b0f3-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="5b0f3-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="5b0f3-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="5b0f3-176">SurfaceIntegration</span></span>
- <span data-ttu-id="5b0f3-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5b0f3-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="5b0f3-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="5b0f3-178">SurfaceService</span></span>
- <span data-ttu-id="5b0f3-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="5b0f3-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="5b0f3-180">Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="5b0f3-181">Die Verzeichnisstruktur wird entweder mit SurfacePlatformInstaller (älteren MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien) gestartet, je nachdem, wann die MSI-Datei veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="5b0f3-182">Um Surface Laptop (1st Generation) zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="5b0f3-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="5b0f3-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="5b0f3-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="5b0f3-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="5b0f3-187">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="5b0f3-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5b0f3-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="5b0f3-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="5b0f3-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="5b0f3-192">Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="5b0f3-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="5b0f3-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="5b0f3-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5b0f3-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="5b0f3-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="5b0f3-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="5b0f3-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="5b0f3-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="5b0f3-200">Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="5b0f3-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5b0f3-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="5b0f3-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="5b0f3-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="5b0f3-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5b0f3-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="5b0f3-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5b0f3-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="5b0f3-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="5b0f3-208">Wenn Sie Surface Laptop 3 mit Intel-Prozessor unterstützen möchten, importieren Sie die folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="5b0f3-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5b0f3-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="5b0f3-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5b0f3-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="5b0f3-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5b0f3-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="5b0f3-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5b0f3-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="5b0f3-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5b0f3-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="5b0f3-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5b0f3-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="5b0f3-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="5b0f3-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="5b0f3-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5b0f3-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b0f3-217">Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="5b0f3-218">Die restlichen Surface-Laptop Treiber befinden sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3-Ordner.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="5b0f3-219">Überprüfen Sie, ob der WindowsPEX64-Ordner nun die importierten Treiber enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="5b0f3-220">Der Ordner sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-220">The folder should resemble the following:</span></span>  

   ![Bild, in dem die neu importierten Treiber im Ordner "WindowsPEX64" der Deployment Workbench angezeigt werden](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="5b0f3-222">Konfigurieren Sie ein Auswahlprofil, das den Ordner "WindowsPEX64" verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="5b0f3-223">Das Auswahlprofil sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-223">The selection profile should resemble the following:</span></span>  

   ![Bild, in dem der WindowsPEX64-Ordner angezeigt wird, der als Teil eines Auswahl Profils ausgewählt ist](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="5b0f3-225">Konfigurieren Sie die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe, um das neue Auswahlprofil wie folgt zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="5b0f3-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="5b0f3-226">Wählen Sie unter **Plattform**die Option **x64**aus.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="5b0f3-227">Wählen Sie im **Auswahlprofil**das neue Profil aus.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="5b0f3-228">Wählen Sie **alle Treiber aus dem Auswahlprofil einbeziehen aus**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Bild, in dem die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe angezeigt werden](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="5b0f3-230">Überprüfen Sie, ob Sie die restlichen Surface-Laptop Treiber mithilfe eines Auswahl Profils oder einer **DriverGroup001** -Variablen konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="5b0f3-231">Für Surface Laptop (1st Generation) ist das Modell **Surface Laptop**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="5b0f3-232">Die restlichen Surface-Laptop Treiber sollten sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop-Ordner befinden, wie in der Abbildung dargestellt, die dieser Liste folgt.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="5b0f3-233">Für Surface Laptop 2 ist das Modell **Surface Laptop 2**.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="5b0f3-234">Die restlichen Surface-Laptop Treiber sollten sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2-Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="5b0f3-235">Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="5b0f3-236">Die restlichen Surface-Laptop Treiber befinden sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3-Ordner.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Abbildung der normalen Surface Laptop-Treiber (1st Gen) im Surface Laptop-Ordner der Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="5b0f3-238">Nachdem Sie die MDT-Bereitstellungsfreigabe für die Verwendung des neuen Auswahl Profils und der zugehörigen Einstellungen konfiguriert haben, fahren Sie mit dem Bereitstellungsprozess fort, wie unter [Bereitstellen eines Windows 10-Abbilds mit MDT: Schritt 6: Erstellen der Bereitstellungstasksequenz](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b0f3-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
