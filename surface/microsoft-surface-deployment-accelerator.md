---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator bietet einen schnellen und einfachen Bereitstellungsmechanismus für Organisationen, die ein Reimaging von Surface-Geräten durchführen möchten.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: bereitstellen, installieren, Tool
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016556"
---
# <span data-ttu-id="88829-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="88829-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="88829-105">Microsoft Surface Deployment Accelerator (SDA) automatisiert die Erstellung und Konfiguration einer von Microsoft empfohlenen Bereitstellungsumgebung mithilfe von kostenlosen Microsoft-Bereitstellungstools.</span><span class="sxs-lookup"><span data-stu-id="88829-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="88829-106">Im April 2020 neu gestaltet, um die Bereitstellung von Surface-Images in einer Unternehmensumgebung zu vereinfachen und zu automatisieren, können Sie mit dem SDA-Tool ein Windows-Abbild erstellen, das Sie an Ihre organisatorischen Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="88829-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="88829-107">Das Open Source-skriptgesteuerte SDA-Tool nutzt das Windows Assessment and Deployment Kit (ADK) für Windows 10, wodurch die Erstellung von Windows-Images (WIM) in Test-oder Produktionsumgebungen vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="88829-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="88829-108">Wenn das neueste ADK noch nicht installiert ist, wird es heruntergeladen und installiert, wenn das SDA-Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="88829-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="88829-109">Das resultierende Bild entspricht in engem Zusammenhang mit der Konfiguration von grundlegendem (Bare Metal Recovery)-Bildern ohne vorinstallierte Anwendungen wie Microsoft Office oder die Surface UWP-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="88829-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="88829-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88829-110">Requirements</span></span>

1. <span data-ttu-id="88829-111">Ein USB-Stick mit einer Größe von mindestens 16 GB.</span><span class="sxs-lookup"><span data-stu-id="88829-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="88829-112">Das USB-Laufwerk wird formatiert.</span><span class="sxs-lookup"><span data-stu-id="88829-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="88829-113">Eine ISO-Datei mit Windows 10 pro oder Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="88829-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="88829-114">Das Medien Erstellungstool kann zum Herunterladen von Windows 10 und zum Erstellen einer ISO-Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88829-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="88829-115">Weitere Informationen finden Sie unter [Herunterladen von Windows 10](https://www.microsoft.com/software-download/windows10).</span><span class="sxs-lookup"><span data-stu-id="88829-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="88829-116">Ein Gerät, auf dem Windows 10, Version 2004 oder höher, mit Internet Zugriff ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="88829-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="88829-117">Eine detaillierte Liste der Anforderungen finden Sie im Abschnitt [Voraussetzungen](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) des Readme-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="88829-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="88829-118">Ausführen des SDA</span><span class="sxs-lookup"><span data-stu-id="88829-118">How to run the SDA</span></span>

**<span data-ttu-id="88829-119">So führen Sie SDA aus:</span><span class="sxs-lookup"><span data-stu-id="88829-119">To run SDA:</span></span>**

1. <span data-ttu-id="88829-120">Wechseln Sie zu [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="88829-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="88829-121">Lesen Sie die [Readme](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) -Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="88829-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="88829-122">Klicken Sie auf der [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) -Seite auf die Schaltfläche **Code** , und wählen Sie dann **ZIP herunterladen** aus, um die Dateien lokal auf Ihrem Computer zu speichern.</span><span class="sxs-lookup"><span data-stu-id="88829-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="88829-123">Klicken Sie mit der rechten Maustaste auf die ZIP-Datei, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="88829-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="88829-124">Aktivieren Sie auf der Registerkarte **Allgemein** das Kontrollkästchen **Blockierung aufheben** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="88829-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="88829-125">Extrahieren Sie die ZIP-Datei an einen Speicherort auf Ihrer Festplatte (z. b.: C:\SDA).</span><span class="sxs-lookup"><span data-stu-id="88829-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="88829-126">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung mit erhöhten Rechten, und legen Sie ExecutionPolicy für die aktuelle Sitzung auf Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="88829-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="88829-127">Führen Sie das SDA-Skript aus, das Parameter für Ihre Umgebung angibt.</span><span class="sxs-lookup"><span data-stu-id="88829-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="88829-128">Mithilfe des Skripts können Bilder erstellt werden, um Windows 10 auf einer Vielzahl von Surface-Geräten zu installieren.</span><span class="sxs-lookup"><span data-stu-id="88829-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="88829-129">Eine vollständige Liste der unterstützten Geräte finden Sie im Readme-Artikel zu SDA unter [Geräteparameter](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) .</span><span class="sxs-lookup"><span data-stu-id="88829-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="88829-130">Mit dem folgenden Befehl wird beispielsweise ein bootfähiges USB-Laufwerk erstellt, das zum [Installieren von Windows 10 auf Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="88829-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="88829-131">Beispiel für eine Skriptausgabe:</span><span class="sxs-lookup"><span data-stu-id="88829-131">Sample script output is below.</span></span>

   ![Tool zum Ausführen des Surface-Bereitstellungs Beschleunigers](images/sda1.png)

    <span data-ttu-id="88829-133">Das Skript erfordert etwa 45 Minuten für die Ausführung, kann aber je nach verfügbarer CPU-und Datenträgerressourcen länger dauern.</span><span class="sxs-lookup"><span data-stu-id="88829-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="88829-134">Nach dem Erstellen eines Windows-Abbilds werden Sie vom Skript aufgefordert, den Laufwerkbuchstaben Ihres USB-Laufwerks einzufügen und zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="88829-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="88829-135">Das USB-Laufwerk wird dann formatiert, als bootfähig konfiguriert und Dateien kopiert, um die Installation des benutzerdefinierten Windows 10-Bilds für Surface-Geräte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="88829-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="88829-136">Legen Sie das USB-Laufwerk in das Gerät ein, auf dem Sie Windows 10 installieren möchten, und starten Sie die Installation von Windows 10.</span><span class="sxs-lookup"><span data-stu-id="88829-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="88829-137">USB-Start muss im BIOS aktiviert sein, was eine vorübergehende Deaktivierung des sicheren Starts erfordern kann.</span><span class="sxs-lookup"><span data-stu-id="88829-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88829-138">Das Booten vom USB-Laufwerk beginnt sofort mit der Installation von Windows 10.</span><span class="sxs-lookup"><span data-stu-id="88829-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="88829-139">Stellen Sie sicher, dass Ihr Gerät bereit ist, bevor Sie den USB-Anschluss einfügen und neu starten.</span><span class="sxs-lookup"><span data-stu-id="88829-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="88829-140">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="88829-140">Related links</span></span>

 - [<span data-ttu-id="88829-141">Open-Source-Image-Bereitstellungstool auf GitHub veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="88829-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="88829-142">Herunterladen und Installieren des Windows ADK</span><span class="sxs-lookup"><span data-stu-id="88829-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
