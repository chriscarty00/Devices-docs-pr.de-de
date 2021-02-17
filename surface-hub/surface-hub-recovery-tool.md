---
title: Verwenden des Wiederherstellungstools für Surface Hub
description: So verwenden Sie das Surface Hub-Wiederherstellungstool zum erneuten Abbilden des SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub verwalten
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 0cc444eab51e9c3cc0bf2f9c2f0c36ac491906b1
ms.sourcegitcommit: 7b09b4bc757c5385c4f5560713cb03448afde9ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339366"
---
# <span data-ttu-id="a1e82-104">Verwenden des Wiederherstellungstools für Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a1e82-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="a1e82-105">Das [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) hilft Ihnen, ein neues Image ihres Surface Hub Solid State Drive (SSD) mithilfe eines Windows 10-Desktopgeräts zu erstellen, ohne die Unterstützung aufforderen oder ssd ersetzen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="a1e82-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="a1e82-106">Mit diesem Tool können Sie ein Reimage einer SSD mit einem unbekannten Administratorkennwort, Startfehlern, nicht abgeschlossenen Cloudwiederherstellungen oder einem Gerät mit einer älteren Version des Betriebssystems durchführen.</span><span class="sxs-lookup"><span data-stu-id="a1e82-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="a1e82-107">Das Tool korrigiert nicht physisch beschädigte SSDs.</span><span class="sxs-lookup"><span data-stu-id="a1e82-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="a1e82-108">Zum erneuten Abbilden der Surface Hub-SSD mithilfe des Wiederherstellungstools müssen Sie das SSD vom Surface Hub entfernen, das Laufwerk mit dem USB-zu-SATA-Kabel verbinden und dann das Kabel mit dem Desktop-PC verbinden, auf dem das Wiederherstellungstool installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a1e82-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="a1e82-109">Weitere Informationen zum Entfernen des vorhandenen Laufwerks vom Surface Hub finden Sie unter [Surface Hub-SSD-Ersatz.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="a1e82-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1e82-110">Lassen Sie das Gerät nicht in den Ruhezustand wechseln oder unterbrechen Sie den Download der Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="a1e82-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="a1e82-111">Wenn das Tool beim Reimaging ihres Laufwerks nicht erfolgreich ist, wenden Sie sich an [den Surface Hub-Support.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="a1e82-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="a1e82-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a1e82-112">Prerequisites</span></span>

### <span data-ttu-id="a1e82-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="a1e82-113">Mandatory</span></span>

- <span data-ttu-id="a1e82-114">Host-PC mit 64-Bit-Version von Windows 10, Version 1607 oder höher.</span><span class="sxs-lookup"><span data-stu-id="a1e82-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="a1e82-115">Internetzugriff</span><span class="sxs-lookup"><span data-stu-id="a1e82-115">Internet access</span></span>
- <span data-ttu-id="a1e82-116">Öffnen von USB 2.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="a1e82-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="a1e82-117">USB-zu-SATA-Kabel</span><span class="sxs-lookup"><span data-stu-id="a1e82-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="a1e82-118">10 GB freier Speicherplatz auf dem Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="a1e82-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="a1e82-119">SSDs, die mit Surface Hub oder einer SSD ausgeliefert wurden, die vom Support als Ersatz bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a1e82-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="a1e82-120">Von Microsoft nicht bereitgestellte SSDs werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1e82-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="a1e82-121">Empfohlen</span><span class="sxs-lookup"><span data-stu-id="a1e82-121">Recommended</span></span>

- <span data-ttu-id="a1e82-122">High-Speed-Internetverbindung</span><span class="sxs-lookup"><span data-stu-id="a1e82-122">High-speed Internet connection</span></span>
- <span data-ttu-id="a1e82-123">Öffnen des USB 3.0-Ports</span><span class="sxs-lookup"><span data-stu-id="a1e82-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="a1e82-124">USB 3.0 oder höher USB-zu-SATA-Kabel</span><span class="sxs-lookup"><span data-stu-id="a1e82-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="a1e82-125">Das Imageerstellungstool wurde mit der folgenden Kabelerstellung und dem folgenden Modell getestet:</span><span class="sxs-lookup"><span data-stu-id="a1e82-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="a1e82-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="a1e82-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="a1e82-127">Rosawill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="a1e82-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="a1e82-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="a1e82-128">Ugreen 20231</span></span>

## <span data-ttu-id="a1e82-129">Surface Hub Recovery Tool herunterladen</span><span class="sxs-lookup"><span data-stu-id="a1e82-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="a1e82-130">Das Surface Hub-Wiederherstellungstool steht unter dem Dateinamen "Surface Hub-Wiederherstellungstool" unter dem Namen "Surface Hub Tools for [IT"](https://www.microsoft.com/download/details.aspx?id=52210) zum \*\*SurfaceHub_Recovery_v2.7.139.0.msi. \*\*</span><span class="sxs-lookup"><span data-stu-id="a1e82-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.7.139.0.msi**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1e82-131">Diese version, released February 11, 2021, replaces the earlier build, which is no longer functional.</span><span class="sxs-lookup"><span data-stu-id="a1e82-131">This version, released Feb 11, 2021, replaces the earlier build, which is no longer functional.</span></span> <span data-ttu-id="a1e82-132">Wenn Sie dieses Tool zuvor heruntergeladen haben, deinstallieren Sie es, und installieren Sie die aktuelle Version.</span><span class="sxs-lookup"><span data-stu-id="a1e82-132">If you downloaded this tool previously, please uninstall it and install the current version.</span></span>

<span data-ttu-id="a1e82-133">Klicken Sie zum Starten des Downloads auf **"Herunterladen",** **wählenSurfaceHub_Recovery_v2.7.139.0.msi** aus der Liste aus, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="a1e82-133">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.7.139.0.msi**  from the list, and click **Next**.</span></span> <span data-ttu-id="a1e82-134">Wählen Sie im Popup eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a1e82-134">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="a1e82-135">Klicken **Sie auf "Ausführen",** um die Installation sofort zu starten.</span><span class="sxs-lookup"><span data-stu-id="a1e82-135">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="a1e82-136">Klicken **Sie auf "Speichern",** um den Download zur späteren Installation auf Ihren Computer zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="a1e82-136">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="a1e82-137">Installieren Sie das Surface Hub-Wiederherstellungstool auf dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="a1e82-137">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="a1e82-138">Ausführen des Surface Hub-Wiederherstellungstools</span><span class="sxs-lookup"><span data-stu-id="a1e82-138">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="a1e82-139">Wählen Sie auf dem Host-PC die **Startschaltfläche** aus, scrollen Sie durch die alphabetische Liste auf der linken Seite, und wählen Sie die Verknüpfung des Wiederherstellungstools aus.</span><span class="sxs-lookup"><span data-stu-id="a1e82-139">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub Recovery Tool](images/shrt-shortcut.png)

2. <span data-ttu-id="a1e82-141">Klicken Sie auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="a1e82-141">Click **Start**.</span></span>

    ![Schaltfläche "Wiederherstellungstool starten"](images/shrt-start.png)


3. <span data-ttu-id="a1e82-143">Klicken Sie **im Fenster "Anleitung"** auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="a1e82-143">In the **Guidance** window, click **Next**.</span></span>

    ![Lassen Sie Ihren Computer nicht in den Ruhezustand wechseln.](images/shrt-guidance.png)

4. <span data-ttu-id="a1e82-145">Klicken Sie im Fenster "Bild auswählen" entweder **auf RS2** oder dessen Nachfolger **20H2,** wählen Sie **"Weiter"** und dann **"Bild herunterladen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a1e82-145">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="a1e82-146">![Bild "Wiederherstellungstool Auswählen des ](images/shrt-select-image.png) ![ Bildwiederherstellungstools herunterladen"](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="a1e82-146">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="a1e82-147">Die Zeit zum Herunterladen des Wiederherstellungsabbilds hängt von der Geschwindigkeit der Internetverbindung ab.</span><span class="sxs-lookup"><span data-stu-id="a1e82-147">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="a1e82-148">Bei einer durchschnittlichen Unternehmensverbindung kann es bis zu einer Stunde dauern, bis die 8 GB-Bilddatei heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a1e82-148">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Bild herunterladen](images/shrt-download.png)



5. <span data-ttu-id="a1e82-150">Wenn der Download abgeschlossen ist, werden Sie vom Tool angewiesen, ein Laufwerk mit SSD zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="a1e82-150">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="a1e82-151">Wenn das Tool das angeschlossene Laufwerk nicht finden kann, besteht die Wahrscheinlichkeit, dass das verwendete Kabel den Namen der SSD nicht an Windows meldet.</span><span class="sxs-lookup"><span data-stu-id="a1e82-151">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="a1e82-152">Das Imageerstellungstool muss den Namen des Laufwerks als "LITEON L CH-128V2S USB-Gerät" finden, bevor es fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1e82-152">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="a1e82-153">Weitere Informationen zum Entfernen des vorhandenen Laufwerks vom Surface Hub finden Sie unter [Surface Hub-SSD-Ersatz.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="a1e82-153">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Verbinden von SSD](images/shrt-drive.png)

6. <span data-ttu-id="a1e82-155">Wenn das Laufwerk erkannt wird, klicken **Sie auf "Start",** um mit dem erneuten Imageerstellungsprozess zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a1e82-155">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="a1e82-156">Klicken Sie in der Warnung, dass alle Daten auf dem Laufwerk gelöscht werden, auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1e82-156">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="a1e82-157">Vor dem Anwenden des Systemimages auf das Laufwerk wird das SSD neupartitioniert und formatiert.</span><span class="sxs-lookup"><span data-stu-id="a1e82-157">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="a1e82-158">Das Kopieren der Systemdateien dauert ca. 30 Minuten, kann jedoch je nach Geschwindigkeit des USB-Bus, des verwendeten Kabels oder der auf dem System installierten Antivirensoftware länger dauern.</span><span class="sxs-lookup"><span data-stu-id="a1e82-158">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="a1e82-159">Problembehandlung und häufige Probleme</span><span class="sxs-lookup"><span data-stu-id="a1e82-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="a1e82-160">Problem</span><span class="sxs-lookup"><span data-stu-id="a1e82-160">Issue</span></span> | <span data-ttu-id="a1e82-161">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a1e82-161">Notes</span></span>
--- | ---
<span data-ttu-id="a1e82-162">Das Tool kann das Image der SSD nicht abbilden.</span><span class="sxs-lookup"><span data-stu-id="a1e82-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="a1e82-163">Stellen Sie sicher, dass Sie ein vom Hersteller bereitgestelltes SSD und eines der getesteten Kabel verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1e82-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="a1e82-164">Der Reimagingprozess wird angehalten/eingefroren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1e82-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="a1e82-165">Es ist sicher, das Surface Hub Recovery Tool ohne schlechte Auswirkungen auf das SSD zu schließen und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="a1e82-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="a1e82-166">Das Laufwerk wird vom Tool nicht erkannt</span><span class="sxs-lookup"><span data-stu-id="a1e82-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="a1e82-167">Stellen Sie sicher, dass die Surface Hub-SSD als Lite-On "LITEON L CH-128V2S-USB-Gerät" aufgezählt wird.</span><span class="sxs-lookup"><span data-stu-id="a1e82-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="a1e82-168">Wenn das Laufwerk als ein anderes benanntes Gerät erkannt wird, ist das aktuelle Kabel nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a1e82-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="a1e82-169">Versuchen Sie es mit einem anderen Kabel oder einem der oben aufgeführten getesteten Kabel.</span><span class="sxs-lookup"><span data-stu-id="a1e82-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="a1e82-170">Fehler: -2147024809</span><span class="sxs-lookup"><span data-stu-id="a1e82-170">Error: -2147024809</span></span> | <span data-ttu-id="a1e82-171">Öffnen Sie den Datenträger-Manager, und entfernen Sie die Partitionen auf dem Surface Hub-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="a1e82-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="a1e82-172">Trennen Sie das Laufwerk, und stellen Sie es wieder mit dem Hostcomputer wieder her.</span><span class="sxs-lookup"><span data-stu-id="a1e82-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="a1e82-173">Starten Sie das Imageerstellungstool erneut.</span><span class="sxs-lookup"><span data-stu-id="a1e82-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="a1e82-174">Wenn das Tool beim Reimaging ihres Laufwerks nicht erfolgreich ist, wenden Sie sich an [den Surface Hub-Support.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="a1e82-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="a1e82-175">Versionsverlauf</span><span class="sxs-lookup"><span data-stu-id="a1e82-175">Version history</span></span>


### <span data-ttu-id="a1e82-176">Version v2.7.139.0</span><span class="sxs-lookup"><span data-stu-id="a1e82-176">Version v2.7.139.0</span></span>

*<span data-ttu-id="a1e82-177">Veröffentlichungsdatum: 11. Februar 2021</span><span class="sxs-lookup"><span data-stu-id="a1e82-177">Release date: February 11, 2021</span></span>*<br>
<span data-ttu-id="a1e82-178">Diese Version des Surface Hub-Wiederherstellungstools bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a1e82-178">This version of Surface Hub Recovery Tool adds support for the following:</span></span>

- <span data-ttu-id="a1e82-179">Sicherheitsupdate</span><span class="sxs-lookup"><span data-stu-id="a1e82-179">Security update</span></span>


### <span data-ttu-id="a1e82-180">Version v2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="a1e82-180">Version v2.0.139.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1e82-181">Diese Version ist nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="a1e82-181">This version is no longer functional.</span></span> <span data-ttu-id="a1e82-182">Laden Sie die oben aufgeführte aktuelle Version herunter.</span><span class="sxs-lookup"><span data-stu-id="a1e82-182">Please download the current version, listed above.</span></span> 

*<span data-ttu-id="a1e82-183">Veröffentlichungsdatum: 18. Dezember 2020</span><span class="sxs-lookup"><span data-stu-id="a1e82-183">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="a1e82-184">Diese Version des Surface Hub-Wiederherstellungstools bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a1e82-184">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="a1e82-185">Update zur Unterstützung von Windows 10 Team 2020 Update (20H2)</span><span class="sxs-lookup"><span data-stu-id="a1e82-185">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="a1e82-186">Verbesserungen der Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="a1e82-186">User experience improvements</span></span>
- <span data-ttu-id="a1e82-187">Architekturänderungen</span><span class="sxs-lookup"><span data-stu-id="a1e82-187">Architectural changes</span></span>
- <span data-ttu-id="a1e82-188">Telemetrieergungen</span><span class="sxs-lookup"><span data-stu-id="a1e82-188">Telemetry additions</span></span>

