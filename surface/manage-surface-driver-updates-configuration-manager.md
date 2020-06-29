---
title: Verwalten von Oberflächen Treiberupdates in Configuration Manager
description: In diesem Artikel werden die verfügbaren Optionen zum Verwalten und Bereitstellen von Firmware-und Treiberupdates für Surface-Geräte beschrieben.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, Firmware, Update, Gerät, verwalten, bereitstellen, Treiber, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: 1a9c8c64bd524de58696c73a28795b69cc70a7b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833418"
---
# <span data-ttu-id="f6b09-104">Verwalten von Oberflächen Treiberupdates in Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6b09-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="f6b09-105">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f6b09-105">Summary</span></span>

<span data-ttu-id="f6b09-106">Ab [Microsoft System Center Configuration Manager, Version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), können Sie die Microsoft Surface-Firmware und Treiberupdates direkt über den Configuration Manager-Client synchronisieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f6b09-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="f6b09-107">Der Prozess ähnelt dem Bereitstellen regulärer Updates.</span><span class="sxs-lookup"><span data-stu-id="f6b09-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="f6b09-108">Einige zusätzliche Konfigurationen sind jedoch erforderlich, um die Oberflächen Treiberaktualisierungen in Ihrem Katalog zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f6b09-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="f6b09-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f6b09-109">Prerequisites</span></span>

<span data-ttu-id="f6b09-110">Zum Verwalten von Oberflächen Treiberupdates müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="f6b09-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f6b09-111">Sie müssen Configuration Manager, Version 1710 oder eine neuere Version, verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6b09-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="f6b09-112">Für alle Software Update Punkte (SUPs) muss Windows Server 2016 oder eine neuere Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6b09-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="f6b09-113">Andernfalls ignoriert Configuration Manager diese Einstellung, und die Oberflächen Treiber werden nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f6b09-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="f6b09-114">Wenn Ihre Umgebung die Voraussetzungen nicht erfüllt, finden Sie im Abschnitt [häufig gestellte Fragen](#frequently-asked-questions-faq) die [alternativen Methoden](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) zum Bereitstellen von Oberflächen Treiber-und Firmware-Updates.</span><span class="sxs-lookup"><span data-stu-id="f6b09-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="f6b09-115">Nützliche Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="f6b09-115">Useful log files</span></span>

<span data-ttu-id="f6b09-116">Die folgenden Protokolle sind besonders nützlich, wenn Sie Oberflächen Treiberupdates verwalten.</span><span class="sxs-lookup"><span data-stu-id="f6b09-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="f6b09-117">Protokollname</span><span class="sxs-lookup"><span data-stu-id="f6b09-117">Log name</span></span>|<span data-ttu-id="f6b09-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6b09-118">Description</span></span>|
|---|---|
|<span data-ttu-id="f6b09-119">WCM. log</span><span class="sxs-lookup"><span data-stu-id="f6b09-119">WCM.log</span></span>|<span data-ttu-id="f6b09-120">Zeichnet Details zur Softwareupdatepunkt-Konfiguration und Verbindungen mit dem WSUS-Server für abonnierte Updatekategorien,-Klassifikationen und-Sprachen auf.</span><span class="sxs-lookup"><span data-stu-id="f6b09-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="f6b09-121">WsyncMgr. log</span><span class="sxs-lookup"><span data-stu-id="f6b09-121">WsyncMgr.log</span></span>|<span data-ttu-id="f6b09-122">Zeichnet Details zum Synchronisierungsprozess für Softwareupdates auf.</span><span class="sxs-lookup"><span data-stu-id="f6b09-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="f6b09-123">Diese Protokolle befinden sich auf dem Website Server, der den SUP verwaltet, oder auf dem SUP selbst, wenn er direkt auf einem Website Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f6b09-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="f6b09-124">Eine vollständige Liste der Configuration Manager-Protokolle finden Sie unter [Protokolldateien in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="f6b09-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="f6b09-125">Aktivieren der Verwaltung von Oberflächen Treiberupdates</span><span class="sxs-lookup"><span data-stu-id="f6b09-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="f6b09-126">Führen Sie die folgenden Schritte aus, um die Verwaltung von Oberflächen Treiberupdates in Configuration Manager zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6b09-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="f6b09-127">Wechseln Sie in der Configuration Manager-Konsole **Administration**zu  >  **Overview**  >  **Website Konfigurations**  >  **Websites**für die Verwaltungsübersicht.</span><span class="sxs-lookup"><span data-stu-id="f6b09-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="f6b09-128">Wählen Sie die Website aus, die den SUP-Server der obersten Ebene für Ihre Umgebung enthält.</span><span class="sxs-lookup"><span data-stu-id="f6b09-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="f6b09-129">Wählen Sie im Menüband **Websitekomponenten konfigurieren**aus, und wählen Sie dann **Software Update Punkt**aus.</span><span class="sxs-lookup"><span data-stu-id="f6b09-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="f6b09-130">Oder klicken Sie mit der rechten Maustaste auf die Website, **Configure Site Components**und wählen Sie dann  >  **Software Update Punkt**für Websitekomponenten konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="f6b09-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="f6b09-131">Aktivieren Sie auf der Registerkarte **Klassifikationen** das Kontrollkästchen **Microsoft-Oberflächen Treiber und Firmware-Updates einbeziehen** .</span><span class="sxs-lookup"><span data-stu-id="f6b09-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![Eigenschaften von Software Update Punkt-Komponenten](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="f6b09-133">Wenn Sie von der folgenden Warnmeldung aufgefordert werden, wählen Sie **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="f6b09-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Konfigurations-Manager](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="f6b09-135">Wählen Sie auf der Registerkarte Produkte die Produkte aus, die Sie aktualisieren möchten, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="f6b09-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="f6b09-136">Die meisten Treiber gehören zu den folgenden Produktgruppen:</span><span class="sxs-lookup"><span data-stu-id="f6b09-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="f6b09-137">Treiber für Windows 10 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="f6b09-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="f6b09-138">Aktualisieren von Windows 10-und höher-&-Wartungs Treibern</span><span class="sxs-lookup"><span data-stu-id="f6b09-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-139">Windows 10 Anniversary Update und spätere Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-140">Windows 10 Anniversary Update und höheres Upgrade & Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-141">Windows 10 Creators-Update und spätere Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-142">Windows 10 Creators-Update und späteres Upgrade & Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-143">Windows 10 Fall Creators Update und spätere Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-144">Windows 10 Fall Creators Update-und höheres Upgrade & Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-145">Windows 10 S und spätere Wartungs Treiber</span><span class="sxs-lookup"><span data-stu-id="f6b09-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="f6b09-146">Windows 10 S, Version 1709 und höher, Wartungs Treiber für Tests</span><span class="sxs-lookup"><span data-stu-id="f6b09-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="f6b09-147">Windows 10 S, Version 1709 und höher, Upgrade & Wartungs Treiber für Tests</span><span class="sxs-lookup"><span data-stu-id="f6b09-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="f6b09-148">Die meisten Oberflächen Treiber gehören mehreren Windows 10-Produktgruppen an.</span><span class="sxs-lookup"><span data-stu-id="f6b09-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="f6b09-149">Sie müssen möglicherweise nicht alle Produkte auswählen, die hier aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="f6b09-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="f6b09-150">Um die Anzahl der Produkte zu verringern, die ihren Update Katalog füllen, empfehlen wir, dass Sie nur die Produkte auswählen, die für Ihre Umgebung für die Synchronisierung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f6b09-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="f6b09-151">Überprüfen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f6b09-151">Verifying the configuration</span></span>

<span data-ttu-id="f6b09-152">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob der SUP richtig konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="f6b09-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="f6b09-153">Öffnen Sie WsyncMgr. log, und suchen Sie dann nach dem folgenden Eintrag:</span><span class="sxs-lookup"><span data-stu-id="f6b09-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="f6b09-154">Wenn einer der folgenden Einträge in WsyncMgr. log protokolliert wird, aktivieren Sie Schritt 4 im vorherigen Abschnitt erneut:</span><span class="sxs-lookup"><span data-stu-id="f6b09-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="f6b09-155">Öffnen Sie WCM. log, und suchen Sie dann nach einem Eintrag, der wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="f6b09-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![WCM. Log-Einstellungen](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="f6b09-157">Bei diesem Eintrag handelt es sich um ein XML-Element, in dem alle Produktgruppen und Klassifikationen aufgelistet sind, die aktuell vom SUP-Server synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="f6b09-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="f6b09-158">Sie können beispielsweise einen Eintrag sehen, der wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="f6b09-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="f6b09-159">Wenn Sie die Produkte, die Sie in Schritt 6 im vorherigen Abschnitt ausgewählt haben, nicht finden können, überprüfen Sie, ob die SUP-Einstellungen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="f6b09-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="f6b09-160">Sie können auch warten, bis die nächste Synchronisierung abgeschlossen ist, und dann überprüfen, ob die Oberflächen Treiber-und Firmware-Updates in der Configuration Manager-Konsole unter Software Updates aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="f6b09-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="f6b09-161">Die Konsole zeigt beispielsweise die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="f6b09-161">For example, the console might display the following information:</span></span>

   ![Alle Suchergebnisse für Software Updates](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="f6b09-163">Manuelle Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="f6b09-163">Manual synchronization</span></span>

<span data-ttu-id="f6b09-164">Wenn Sie nicht bis zur nächsten Synchronisierung warten möchten, führen Sie die folgenden Schritte aus, um eine Synchronisierung zu starten:</span><span class="sxs-lookup"><span data-stu-id="f6b09-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="f6b09-165">Wechseln Sie in der Configuration Manager-Konsole zu **Software Library**  >  **Overview**  >  **Softwareupdates**  >  **alle Softwareupdates**.</span><span class="sxs-lookup"><span data-stu-id="f6b09-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="f6b09-166">Wählen Sie im Menüband **Software Updates synchronisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="f6b09-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="f6b09-167">Oder klicken Sie mit der rechten Maustaste auf **alle Softwareupdates**, und wählen Sie dann **Software Update synchronisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="f6b09-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="f6b09-168">Überwachen Sie den Synchronisierungsfortschritt, indem Sie in WsyncMgr. log nach den folgenden Einträgen suchen:</span><span class="sxs-lookup"><span data-stu-id="f6b09-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <span data-ttu-id="f6b09-169">Bereitstellen von Surface-Firmware und Treiberupdates</span><span class="sxs-lookup"><span data-stu-id="f6b09-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="f6b09-170">Sie können DGM-Firmware und Treiberupdates auf die gleiche Weise wie andere Updates bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f6b09-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="f6b09-171">Weitere Informationen zur Bereitstellung finden Sie unter [System Center 2012 Configuration Manager – Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span><span class="sxs-lookup"><span data-stu-id="f6b09-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="f6b09-172">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="f6b09-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="f6b09-173">Nachdem ich die in diesem Artikel beschriebenen Schritte ausgeführt habe, sind meine Oberflächen Treiber weiterhin nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f6b09-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="f6b09-174">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="f6b09-174">Why?</span></span>**

<span data-ttu-id="f6b09-175">Wenn Sie die Synchronisierung von einem Upstream-Server für Windows Server Update Services (WSUS) anstelle von Microsoft Update durchführen, stellen Sie sicher, dass der WSUS-Upstream-Server für die Unterstützung und Synchronisierung von Oberflächen Treiberupdates konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f6b09-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="f6b09-176">Alle Downstreamserver sind auf Updates limitiert, die in der WSUS-Upstream-Server Datenbank vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f6b09-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="f6b09-177">Es gibt mehr als 68.000-Updates, die in WSUS als Treiber klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="f6b09-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="f6b09-178">Um zu verhindern, dass nicht mit der Oberfläche Verwandte Treiber mit dem Configuration Manager synchronisiert werden, wird die Treiber Synchronisierung mit einer Zulassungsliste von Microsoft gefiltert.</span><span class="sxs-lookup"><span data-stu-id="f6b09-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="f6b09-179">Nachdem die neue Zulassungsliste veröffentlicht und in Configuration Manager integriert wurde, werden die neuen Treiber der Konsole nach der nächsten Synchronisierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6b09-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="f6b09-180">Microsoft hat sich zum Ziel gesetzt, die Surface-Treiber jeden Monat in Einklang mit Patch Tuesday zur Liste "zulassen" hinzuzufügen, damit Sie für die Synchronisierung mit Configuration Manager zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f6b09-180">Microsoft aims to get the Surface drivers added to the allow list each month in line with Patch Tuesday to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="f6b09-181">Wenn Ihre Configuration Manager-Umgebung offline ist, wird jedes Mal, wenn Sie [Wartungsupdates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) in Configuration Manager importieren, eine neue Zulassungsliste importiert.</span><span class="sxs-lookup"><span data-stu-id="f6b09-181">If your Configuration Manager environment is offline, a new allow list is imported every time you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="f6b09-182">Darüber hinaus müssen Sie einen [neuen WSUS-Katalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) importieren, der die Treiber enthält, bevor die Updates in der Configuration Manager-Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f6b09-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="f6b09-183">Da eine eigenständige WSUS-Umgebung mehr Treiber als ein Configuration Manager-SUP enthält, empfiehlt es sich, eine Configuration Manager-Umgebung mit Online Funktionen zu erstellen und diese für die Synchronisierung von Oberflächen Treibern zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f6b09-183">Because a stand-alone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="f6b09-184">Dadurch wird ein kleinerer WSUS-Export bereitgestellt, der der Offlineumgebung ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="f6b09-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="f6b09-185">Wenn Ihre Configuration Manager-Umgebung online ist und neue Updates erkennen kann, erhalten Sie automatisch Updates für die Liste.</span><span class="sxs-lookup"><span data-stu-id="f6b09-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="f6b09-186">Wenn die erwarteten Treiber nicht angezeigt werden, überprüfen Sie die Funktionen "WCM. log" und "WsyncMgr. log" auf Synchronisierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="f6b09-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log for any synchronization failures.</span></span>

**<span data-ttu-id="f6b09-187">Meine Configuration Manager-Umgebung offline ist, kann ich Oberflächen Treiber manuell in WSUS importieren?</span><span class="sxs-lookup"><span data-stu-id="f6b09-187">My Configuration Manager environment is offline, can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="f6b09-188">Nein.</span><span class="sxs-lookup"><span data-stu-id="f6b09-188">No.</span></span> <span data-ttu-id="f6b09-189">Auch wenn das Update in WSUS importiert wurde, wird das Update nicht in die Configuration Manager-Konsole für die Bereitstellung importiert, wenn es nicht in der Zulassungsliste aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="f6b09-189">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="f6b09-190">Sie müssen das [Dienst Verbindungs Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) verwenden, um Wartungsupdates in Configuration Manager zu importieren, um die Zulassungsliste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f6b09-190">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="f6b09-191">Welche alternativen Methoden sind für die Bereitstellung von Oberflächen Treiber-und Firmware-Updates verfügbar?</span><span class="sxs-lookup"><span data-stu-id="f6b09-191">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="f6b09-192">Informationen zum Bereitstellen von Oberflächen Treiber-und Firmware-Updates über alternative Kanäle finden Sie unter [Verwalten von Oberflächen Treiber-und Firmware-Updates](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="f6b09-192">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates).</span></span> <span data-ttu-id="f6b09-193">Wenn Sie die MSI-oder exe-Datei herunterladen und dann über herkömmliche Software Bereitstellungskanäle bereitstellen möchten, lesen Sie [Aktualisieren der Surface-Firmware mit Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="f6b09-193">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="f6b09-194">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6b09-194">Additional Information</span></span>

<span data-ttu-id="f6b09-195">Weitere Informationen zu Oberflächen Treiber-und Firmware-Updates finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="f6b09-195">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="f6b09-196">Herunterladen der neuesten Firmware und Treiber für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="f6b09-196">Download the latest firmware and drivers for Surface devices</span></span>](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)
- [<span data-ttu-id="f6b09-197">Verwalten von Treiber- und Firmwareupdates für Surface</span><span class="sxs-lookup"><span data-stu-id="f6b09-197">Manage Surface driver and firmware updates</span></span>](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)
- [<span data-ttu-id="f6b09-198">Überlegungen für Surface und System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6b09-198">Considerations for Surface and System Center Configuration Manager</span></span>](https://docs.microsoft.com/surface/considerations-for-surface-and-system-center-configuration-manager)
