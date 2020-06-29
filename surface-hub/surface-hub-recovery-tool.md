---
title: Verwenden des Wiederherstellungstools für Surface Hub
description: Verwenden des Surface Hub-Wiederherstellungstools zum erneuten abbilden der SSD
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub verwalten
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834168"
---
# <span data-ttu-id="2ab89-104">Verwenden des Wiederherstellungstools für Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2ab89-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="2ab89-105">Das [Microsoft Surface Hub-Wiederherstellungs Tool](https://www.microsoft.com/download/details.aspx?id=52210) unterstützt Sie beim erneuten abbilden Ihres Surface Hub-Solid-State-Laufwerks (SSD) mithilfe eines Windows 10-Desktop Geräts, ohne den Support zu anrufen oder die SSD zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2ab89-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="2ab89-106">Mit diesem Tool können Sie eine SSD umbilden, die über ein unbekanntes Administrator Kennwort, Startfehler, keine Cloud-Wiederherstellung oder ein Gerät mit einer älteren Version des Betriebssystems verfügt.</span><span class="sxs-lookup"><span data-stu-id="2ab89-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="2ab89-107">Das Tool repariert keine physisch beschädigten SSDs.</span><span class="sxs-lookup"><span data-stu-id="2ab89-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="2ab89-108">Wenn Sie das Surface-Hub-SSD mithilfe des Wiederherstellungstools erneut abbilden möchten, müssen Sie die SSD vom Surface-Hub entfernen, das Laufwerk mit dem USB-zu-SATA-Kabel verbinden und dann das Kabel an den Desktop-PC anschließen, auf dem das Wiederherstellungstool installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2ab89-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="2ab89-109">Weitere Informationen zum Entfernen des vorhandenen Laufwerks aus dem Surface Hub finden Sie unter [Ersetzen des Surface Hub-SSD](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="2ab89-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ab89-110">Lassen Sie das Gerät nicht in den Standbymodus wechseln oder den Download der Bilddatei unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="2ab89-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="2ab89-111">Wenn das Tool beim erneuten abbilden Ihres Laufwerks nicht erfolgreich ist, wenden Sie sich bitte an den [Surface Hub-Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="2ab89-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="2ab89-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2ab89-112">Prerequisites</span></span>

### <span data-ttu-id="2ab89-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="2ab89-113">Mandatory</span></span>

- <span data-ttu-id="2ab89-114">Host-PC mit 64-Bit-Version von Windows 10, Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="2ab89-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="2ab89-115">Internetzugriff</span><span class="sxs-lookup"><span data-stu-id="2ab89-115">Internet access</span></span>
- <span data-ttu-id="2ab89-116">Öffnen Sie den USB-Port 2,0 oder höher</span><span class="sxs-lookup"><span data-stu-id="2ab89-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="2ab89-117">USB-zu-SATA-Kabel</span><span class="sxs-lookup"><span data-stu-id="2ab89-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="2ab89-118">10 GB freier Speicherplatz auf dem Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="2ab89-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="2ab89-119">SSDs, geliefert mit Surface Hub oder einer SSD, die vom Support als Ersatz bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2ab89-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="2ab89-120">SSDs, die nicht von Microsoft bereitgestellt werden, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ab89-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="2ab89-121">Empfohlen</span><span class="sxs-lookup"><span data-stu-id="2ab89-121">Recommended</span></span>

- <span data-ttu-id="2ab89-122">Hochgeschwindigkeits-Internet Verbindung</span><span class="sxs-lookup"><span data-stu-id="2ab89-122">High-speed Internet connection</span></span>
- <span data-ttu-id="2ab89-123">USB 3,0-Port öffnen</span><span class="sxs-lookup"><span data-stu-id="2ab89-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="2ab89-124">USB-3,0 oder höheres USB-zu-SATA-Kabel</span><span class="sxs-lookup"><span data-stu-id="2ab89-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="2ab89-125">Das Imaging-Tool wurde mit dem folgenden Hersteller und Modell von Kabeln getestet:</span><span class="sxs-lookup"><span data-stu-id="2ab89-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="2ab89-126">StarTech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="2ab89-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="2ab89-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="2ab89-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="2ab89-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="2ab89-128">Ugreen 20231</span></span>

## <span data-ttu-id="2ab89-129">Herunterladen des Surface Hub-Wiederherstellungstools</span><span class="sxs-lookup"><span data-stu-id="2ab89-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="2ab89-130">Surface Hub-Wiederherstellungs Tool steht unter dem Dateinamen **SurfaceHub_Recovery_v1.14.137.0.msi**für den Download von [Surface Hub-Tools](https://www.microsoft.com/download/details.aspx?id=52210) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2ab89-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="2ab89-131">Klicken Sie zum Starten des Downloads auf **herunterladen**, wählen Sie in der Liste **SurfaceHub_Recovery_v1.14.137.0.msi** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ab89-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="2ab89-132">Wählen Sie im Popup-Fenster eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="2ab89-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="2ab89-133">Klicken Sie auf **Ausführen** , um die Installation sofort zu starten.</span><span class="sxs-lookup"><span data-stu-id="2ab89-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="2ab89-134">Klicken Sie auf **Speichern** , um den Download zur späteren Installation auf Ihren Computer zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="2ab89-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="2ab89-135">Installieren des Surface Hub-Wiederherstellungstools auf dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="2ab89-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="2ab89-136">Ausführen des Surface Hub-Wiederherstellungstools</span><span class="sxs-lookup"><span data-stu-id="2ab89-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="2ab89-137">Wählen Sie auf dem Host-PC die Schaltfläche **Start** aus, Scrollen Sie durch die alphabetische Liste auf der linken Seite, und wählen Sie die Verknüpfung für das Wiederherstellungstool aus.</span><span class="sxs-lookup"><span data-stu-id="2ab89-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub-Wiederherstellungs Tool-Verknüpfung](images/shrt-shortcut.png)

2. <span data-ttu-id="2ab89-139">Klicken Sie auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="2ab89-139">Click **Start**.</span></span>

    ![Start Schaltfläche für das Wiederherstellungs Tool](images/shrt-start.png)

3. <span data-ttu-id="2ab89-141">Klicken Sie im Fenster " **Anleitung** " auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ab89-141">In the **Guidance** window, click **Next**.</span></span>

    ![Lassen Sie Ihren Computer nicht in die Schlaf Anleitung gehen](images/shrt-guidance.png)

4. <span data-ttu-id="2ab89-143">Klicken Sie auf **Ja** , um das Bild herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2ab89-143">click **Yes** to download the image.</span></span> <span data-ttu-id="2ab89-144">Die Zeit zum Herunterladen des Wiederherstellungs Bilds hängt von den Geschwindigkeiten der Internetverbindung ab.</span><span class="sxs-lookup"><span data-stu-id="2ab89-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="2ab89-145">Bei einer durchschnittlichen Unternehmensverbindung kann es bis zu einer Stunde dauern, bis die 8 GB-Imagedatei heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2ab89-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Das Bild herunterladen?](images/shrt-download.png)

5. <span data-ttu-id="2ab89-147">Wenn der Download abgeschlossen ist, weist das Tool Sie an, ein SSD-Laufwerk zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="2ab89-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="2ab89-148">Wenn das Tool das angefügte Laufwerk nicht finden kann, besteht eine gute Wahrscheinlichkeit, dass das verwendete Kabel nicht den Namen der SSD an Windows meldet.</span><span class="sxs-lookup"><span data-stu-id="2ab89-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="2ab89-149">Das Imaging-Tool muss den Namen des Laufwerks als "LiteOn L CH-128V2S USB-Gerät" finden, bevor es fortfahren kann.</span><span class="sxs-lookup"><span data-stu-id="2ab89-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="2ab89-150">Weitere Informationen zum Entfernen des vorhandenen Laufwerks aus dem Surface Hub finden Sie unter [Ersetzen des Surface Hub-SSD](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="2ab89-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![SSD verbinden](images/shrt-drive.png)

6. <span data-ttu-id="2ab89-152">Wenn das Laufwerk erkannt wird, klicken Sie auf **Start** , um mit der Wiederherstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="2ab89-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="2ab89-153">Klicken Sie auf der Warnung, dass alle Daten auf dem Laufwerk gelöscht werden, auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ab89-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![Erneutes Imaging der SSD starten](images/shrt-drive-start.png)

    <span data-ttu-id="2ab89-155">Vor dem Anwenden des Systemabbilds auf das Laufwerk wird die SSD neu partitioniert und formatiert.</span><span class="sxs-lookup"><span data-stu-id="2ab89-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="2ab89-156">Das Kopieren der Systembinärdateien dauert ungefähr 30 Minuten, kann aber je nach der Geschwindigkeit Ihres USB-Busses, des verwendeten Kabels oder der auf Ihrem System installierten Antivirensoftware länger dauern.</span><span class="sxs-lookup"><span data-stu-id="2ab89-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![Kopieren erfolgt](images/shrt-done.png)

    ![Reimaging abgeschlossen](images/shrt-complete.png)

## <span data-ttu-id="2ab89-159">Problembehandlung und häufige Probleme</span><span class="sxs-lookup"><span data-stu-id="2ab89-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="2ab89-160">Problem</span><span class="sxs-lookup"><span data-stu-id="2ab89-160">Issue</span></span> | <span data-ttu-id="2ab89-161">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="2ab89-161">Notes</span></span>
--- | ---
<span data-ttu-id="2ab89-162">Das Tool kann die SSD nicht abbilden</span><span class="sxs-lookup"><span data-stu-id="2ab89-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="2ab89-163">Stellen Sie sicher, dass Sie eine von der Factory bereitgestellte SSD und eines der getesteten Kabel verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ab89-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="2ab89-164">Der Prozess der Bildbearbeitung wird angehalten/fixiert angezeigt</span><span class="sxs-lookup"><span data-stu-id="2ab89-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="2ab89-165">Es ist sicher, das Surface Hub-Wiederherstellungs Tool ohne negative Auswirkungen auf die SSD zu schließen und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="2ab89-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="2ab89-166">Das Laufwerk wird vom Tool nicht erkannt</span><span class="sxs-lookup"><span data-stu-id="2ab89-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="2ab89-167">Überprüfen Sie, ob der Surface Hub SSD als Lite-On-Laufwerk "LiteOn L CH-128V2S USB Device" aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="2ab89-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="2ab89-168">Wenn das Laufwerk als ein anderes benanntes Gerät erkannt wird, ist das aktuelle Kabel nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="2ab89-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="2ab89-169">Versuchen Sie es mit einem anderen Kabel oder einem der oben aufgeführten getesteten Kabel.</span><span class="sxs-lookup"><span data-stu-id="2ab89-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="2ab89-170">Fehler:-2147024809</span><span class="sxs-lookup"><span data-stu-id="2ab89-170">Error: -2147024809</span></span> | <span data-ttu-id="2ab89-171">Öffnen Sie den Datenträger-Manager, und entfernen Sie die Partitionen auf dem Surface-Hub-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="2ab89-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="2ab89-172">Trennen Sie das Laufwerk, und schließen Sie es erneut an den Hostcomputer an.</span><span class="sxs-lookup"><span data-stu-id="2ab89-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="2ab89-173">Starten Sie das Imaging-Tool erneut.</span><span class="sxs-lookup"><span data-stu-id="2ab89-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="2ab89-174">Wenn das Tool beim erneuten abbilden Ihres Laufwerks nicht erfolgreich ist, wenden Sie sich bitte an den [Surface Hub-Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="2ab89-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>
