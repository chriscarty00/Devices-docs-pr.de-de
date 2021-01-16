---
title: Einstellung für den Akkugrenzwert (Surface)
description: Der Akkugrenzwert ist eine UEFI-Einstellung, die ändert, wie der Akku des Surface-Geräts aufgeladen wird und die Lebensdauer verlängern kann.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271142"
---
# <span data-ttu-id="00da1-103">Einstellungen für Akkulimit</span><span class="sxs-lookup"><span data-stu-id="00da1-103">Battery Limit setting</span></span>

<span data-ttu-id="00da1-104">Die Option "Akkulimit" ist eine UEFI-Einstellung, die ändert, wie der Akku des Surface-Geräts aufgeladen wird und die Lebensdauer verlängern kann.</span><span class="sxs-lookup"><span data-stu-id="00da1-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="00da1-105">Diese Einstellung wird in Fällen empfohlen, in denen das Gerät ständig an die Stromversorgung angeschlossen ist, z. B. wenn Geräte in Kiosklösungen integriert sind.</span><span class="sxs-lookup"><span data-stu-id="00da1-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="00da1-106">Funktionsweise des Akkugrenzwerts</span><span class="sxs-lookup"><span data-stu-id="00da1-106">How Battery Limit works</span></span>

<span data-ttu-id="00da1-107">Wenn Sie das Gerät auf "Akkulimit" festlegen, wird das Protokoll zum Aufladen des Geräteakku geändert.</span><span class="sxs-lookup"><span data-stu-id="00da1-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="00da1-108">Wenn der Akkugrenzwert aktiviert ist, ist der Akkustand auf 50 % der maximalen Kapazität beschränkt.</span><span class="sxs-lookup"><span data-stu-id="00da1-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="00da1-109">Die in Windows gemeldete Gebührenstufe spiegelt diesen Grenzwert wider.</span><span class="sxs-lookup"><span data-stu-id="00da1-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="00da1-110">Daher wird gezeigt, dass der Akku bis zu 50 % aufgeladen wird und nicht über diesen Grenzwert hinaus aufgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="00da1-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="00da1-111">Wenn Sie den Akkugrenzwert aktivieren, während das Gerät über 50 % aufgeladen ist, zeigt das Symbol "Akku" an, dass das Gerät eingesteckt ist, aber entladen wird, bis das Gerät 50 % seiner maximalen Ladekapazität erreicht.</span><span class="sxs-lookup"><span data-stu-id="00da1-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="00da1-112">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="00da1-112">Supported devices</span></span>

<span data-ttu-id="00da1-113">Die Einstellung "Battery Limit UEFI" ist in die neuesten Surface-Geräte, einschließlich Surface Pro 7+, Surface Pro 7 und Surface Laptop 3, integrierte.</span><span class="sxs-lookup"><span data-stu-id="00da1-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="00da1-114">Frühere Geräte erfordern ein [Surface UEFI-Firmwareupdate,](manage-surface-driver-and-firmware-updates.md)das über Windows Update oder die MSI-Treiber- und Firmwarepakete auf der [Surface Support-Website verfügbar ist.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)</span><span class="sxs-lookup"><span data-stu-id="00da1-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="00da1-115">Aktivieren [Sie "Akkulimit" für Surface-Geräte,](https://support.microsoft.com/help/4464941) die für die spezifische Surface -UEFI-Version, die für jedes unterstützte Gerät erforderlich ist, über einen längeren Zeitraum angeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="00da1-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="00da1-116">Aktivieren des Akkugrenzwerts auf Surface UEFI (Surface Pro 4 und höher)</span><span class="sxs-lookup"><span data-stu-id="00da1-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="00da1-117">Die Einstellung für den Surface -UEFI-Akkugrenzwert kann durch Starten auf Surface UEFI konfiguriert werden (**Ein- und** Aufladen beim Einschalten des Geräts).</span><span class="sxs-lookup"><span data-stu-id="00da1-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="00da1-118">Wählen **Sie die Startkonfiguration**aus, und schalten Sie dann unter **"Erweiterte**Optionen" den Akkugrenzmodus aktivieren **auf** **"Ein" um.**</span><span class="sxs-lookup"><span data-stu-id="00da1-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Erweiterte Optionen für den Akkugrenzwert](images/enable-bl.png) 

## <span data-ttu-id="00da1-120">Aktivieren des Akkulimits auf Surface Go und Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="00da1-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="00da1-121">Die Einstellung "Surface Battery Limit" kann durch Starten von Surface UEFI **(Power + Vol Up** beim Einschalten des Geräts) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="00da1-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="00da1-122">Wählen **Sie die Startkonfiguration**aus, und verschieben Sie dann unter **Kioskmodus**den Schieberegler nach rechts, um den Akkugrenzwert auf **"Aktiviert" festzulegen.**</span><span class="sxs-lookup"><span data-stu-id="00da1-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Akkugrenzwert des Kioskmodus auf Surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="00da1-124">Aktivieren des Akkugrenzwerts auf Surface UEFI (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="00da1-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="00da1-125">Die Einstellung für den Surface -UEFI-Akkugrenzwert kann durch Starten auf Surface UEFI konfiguriert werden (**Ein- und** Aufladen beim Einschalten des Geräts).</span><span class="sxs-lookup"><span data-stu-id="00da1-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="00da1-126">Wählen **Sie "Kioskmodus",** **"Akkulimit"** und dann "Aktiviert" **aus.**</span><span class="sxs-lookup"><span data-stu-id="00da1-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Screenshot der erweiterten Optionen](images/enable-bl-sp3.png) 

![Erweiterte Optionen](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="00da1-129">Aktivieren des Akkulimits mithilfe von Surface Enterprise Management Mode (SEMM) oder Surface Pro 3 Firmware-PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="00da1-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="00da1-130">Der Surface -UEFI-Akkugrenzwert ist auch für die Konfiguration über die folgenden Methoden verfügbar:</span><span class="sxs-lookup"><span data-stu-id="00da1-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="00da1-131">Surface Pro 4 und höher</span><span class="sxs-lookup"><span data-stu-id="00da1-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="00da1-132">Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="00da1-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="00da1-133">Surface UEFI Manager –Powershell-Skripts (SEMM_Powershell.zip) in den [Surface Tools für IT-Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="00da1-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="00da1-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="00da1-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="00da1-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="00da1-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="00da1-136">Verwenden Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="00da1-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="00da1-137">Um den Akkugrenzmodus zu konfigurieren, legen Sie die Einstellung "Außerkraftsetzungen für **Kiosk"** auf der Konfigurationsseite "Erweiterte **Einstellungen"** in SEMM (Surface Pro 4 und höher) ein.</span><span class="sxs-lookup"><span data-stu-id="00da1-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Screenshot der erweiterten Einstellungen](images/semm-bl.png)

### <span data-ttu-id="00da1-139">Verwenden von Surface UEFI Manager -PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="00da1-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="00da1-140">Die Funktion für den Akkugrenzwert wird über die folgende Einstellung gesteuert:</span><span class="sxs-lookup"><span data-stu-id="00da1-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="00da1-141">**Beschreibung:** Aktives Verwaltungsschema für das Akkunutzungsmuster</span><span class="sxs-lookup"><span data-stu-id="00da1-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="00da1-142">**Standard:**</span><span class="sxs-lookup"><span data-stu-id="00da1-142">**Default**:</span></span>  `0` 

<span data-ttu-id="00da1-143">Legen Sie diese Option `1` so ein, dass der Akkugrenzwert aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="00da1-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="00da1-144">Verwenden Surface Pro 3 Firmwaretools</span><span class="sxs-lookup"><span data-stu-id="00da1-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="00da1-145">Die Funktion für den Akkugrenzwert wird über die folgende Einstellung gesteuert:</span><span class="sxs-lookup"><span data-stu-id="00da1-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="00da1-146">**Name**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="00da1-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="00da1-147">**Beschreibung**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="00da1-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="00da1-148">**Aktueller Wert:**</span><span class="sxs-lookup"><span data-stu-id="00da1-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="00da1-149">**Standardwert:**</span><span class="sxs-lookup"><span data-stu-id="00da1-149">**Default Value**:</span></span> `0`

<span data-ttu-id="00da1-150">**Vorgeschlagener Wert:**</span><span class="sxs-lookup"><span data-stu-id="00da1-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="00da1-151">Legen Sie diese Option `1` so ein, dass der Akkugrenzwert aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="00da1-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="00da1-152">Um diese Einstellung zu konfigurieren, müssen Sie [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="00da1-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

