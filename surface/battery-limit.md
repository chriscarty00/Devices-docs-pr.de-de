---
title: Einstellung der Batterie Grenze (Oberfläche)
description: Die Batterie Grenze ist eine UEFI-Einstellung, die das Aufladen des Surface-Geräte Akkus ändert und seine Langlebigkeit verlängern kann.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833508"
---
# <span data-ttu-id="f5987-103">Einstellungen für Akkulimit</span><span class="sxs-lookup"><span data-stu-id="f5987-103">Battery Limit setting</span></span>

<span data-ttu-id="f5987-104">Die Option "Akku Grenze" ist eine UEFI-Einstellung, die das Aufladen des Surface-Geräte Akkus ändert und seine Langlebigkeit verlängern kann.</span><span class="sxs-lookup"><span data-stu-id="f5987-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="f5987-105">Diese Einstellung wird in den Fällen empfohlen, in denen das Gerät kontinuierlich an die Stromversorgung angeschlossen ist, beispielsweise wenn Geräte in Kiosk Lösungen integriert sind.</span><span class="sxs-lookup"><span data-stu-id="f5987-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="f5987-106">Funktionsweise des Batterie Limits</span><span class="sxs-lookup"><span data-stu-id="f5987-106">How Battery Limit works</span></span>

<span data-ttu-id="f5987-107">Wenn Sie das Gerät auf Batterie Grenzwert setzen, ändert sich das Protokoll zum Aufladen des Geräte Akkus.</span><span class="sxs-lookup"><span data-stu-id="f5987-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="f5987-108">Wenn die Batterie Grenze aktiviert ist, wird die Akkuladung auf 50% der maximalen Kapazität begrenzt.</span><span class="sxs-lookup"><span data-stu-id="f5987-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="f5987-109">Die in Windows gemeldete Belastungsstufe spiegelt diesen Grenzwert wider.</span><span class="sxs-lookup"><span data-stu-id="f5987-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="f5987-110">Daher wird angezeigt, dass der Akku bis zu 50% aufgeladen wird und nicht über diesen Grenzwert hinaus belastet wird.</span><span class="sxs-lookup"><span data-stu-id="f5987-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="f5987-111">Wenn Sie die Batterie Grenze aktivieren, während das Gerät über 50% aufgeladen ist, zeigt das Batteriesymbol an, dass das Gerät angeschlossen ist, aber entladen wird, bis das Gerät 50% seiner maximalen Ladekapazität erreicht.</span><span class="sxs-lookup"><span data-stu-id="f5987-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="f5987-112">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="f5987-112">Supported devices</span></span>
<span data-ttu-id="f5987-113">Die UEFI-Einstellung für das Batterie Limit ist in die neuesten Surface-Geräte einschließlich Surface pro 7 und Surface Laptop 3 integriert.</span><span class="sxs-lookup"><span data-stu-id="f5987-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="f5987-114">Für ältere Geräte ist eine [Oberflächen UEFI-Firmware-Aktualisierung](manage-surface-driver-and-firmware-updates.md)erforderlich, die über Windows Update oder über die MSI-Treiber-und Firmware-Pakete auf der [Surface Support-Website](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f5987-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="f5987-115">Aktivieren Sie das Kontrollkästchen ["Batterie Grenzwert" für Surface-Geräte, die für längere Zeit](https://support.microsoft.com/help/4464941) für die spezifische Oberflächen UEFI-Version, die für jedes unterstützte Gerät erforderlich ist, angeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f5987-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="f5987-116">Aktivieren des Batterie Grenzwerts in der Oberfläche UEFI (Surface pro 4 und höher)</span><span class="sxs-lookup"><span data-stu-id="f5987-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="f5987-117">Die Einstellung für die Oberfläche des UEFI-Batterie Limits kann durch Starten in die Oberfläche UEFI (**Power + Vol up** beim Einschalten des Geräts) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f5987-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="f5987-118">Wählen Sie **Startkonfiguration**aus, und aktivieren Sie dann unter **Erweiterte Optionen**den **Modus Batterie-limitmodus** **auf ein**.</span><span class="sxs-lookup"><span data-stu-id="f5987-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Screenshot der erweiterten Optionen](images/enable-bl.png) 

## <span data-ttu-id="f5987-120">Aktivieren des Batterie Limits für Surface Go und Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="f5987-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="f5987-121">Die Einstellung für die Oberflächen-Batterie Grenze kann durch Starten in die Oberfläche UEFI (**Power + Vol up** beim Einschalten des Geräts) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f5987-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="f5987-122">Wählen Sie **Startkonfiguration**aus, und verschieben Sie dann unter **Kiosk Modus**den Schieberegler nach rechts, um den Batterie Grenzwert auf **aktiviert**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f5987-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Screenshot der Batterie Grenze des Kiosk Modus in Surface go](images/go-batterylimit.png) 

## <span data-ttu-id="f5987-124">Aktivieren des Batterie Grenzwerts in der Oberfläche UEFI (Surface pro 3)</span><span class="sxs-lookup"><span data-stu-id="f5987-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="f5987-125">Die Einstellung für die Oberfläche des UEFI-Batterie Limits kann durch Starten in die Oberfläche UEFI (**Power + Vol up** beim Einschalten des Geräts) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f5987-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="f5987-126">Wählen Sie **Kiosk Modus**, dann **Batterie Grenzwert**und dann **aktiviert**aus.</span><span class="sxs-lookup"><span data-stu-id="f5987-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Screenshot der erweiterten Optionen](images/enable-bl-sp3.png) 

![Screenshot der erweiterten Optionen](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="f5987-129">Aktivieren des Batterie Limits mit dem Surface Enterprise Management Mode (Semm) oder Surface pro 3-Firmware PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="f5987-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="f5987-130">Die Oberfläche des UEFI-Batterie Limits ist auch für die Konfiguration über die folgenden Methoden verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f5987-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="f5987-131">Surface pro 4 und höher</span><span class="sxs-lookup"><span data-stu-id="f5987-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="f5987-132">Microsoft Surface UEFI-Konfigurator</span><span class="sxs-lookup"><span data-stu-id="f5987-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="f5987-133">Oberflächen-UEFI-Manager-PowerShell-Skripts (SEMM_Powershell.zip) in den [Surface Tools für IT-Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="f5987-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="f5987-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="f5987-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="f5987-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="f5987-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="f5987-136">Verwenden des Microsoft Surface UEFI-Konfigurators</span><span class="sxs-lookup"><span data-stu-id="f5987-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="f5987-137">Zum Konfigurieren des Batterie Limit-Modus legen Sie die Einstellung **Kiosk Außerkraftsetzungen** auf der Seite **Erweiterte Einstellungen** für Konfiguration in Semm (Surface pro 4 und höher) fest.</span><span class="sxs-lookup"><span data-stu-id="f5987-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Screenshot der erweiterten Einstellungen](images/semm-bl.png)

### <span data-ttu-id="f5987-139">Verwenden von PowerShell-Skripten für Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="f5987-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="f5987-140">Die Funktion für das Batterie Limit wird über die folgende Einstellung gesteuert:</span><span class="sxs-lookup"><span data-stu-id="f5987-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="f5987-141">**Beschreibung**: aktives Verwaltungsschema für Batterie Nutzungsmuster</span><span class="sxs-lookup"><span data-stu-id="f5987-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="f5987-142">**Standard**:</span><span class="sxs-lookup"><span data-stu-id="f5987-142">**Default**:</span></span>  `0` 

<span data-ttu-id="f5987-143">Wählen Sie diese `1` Option aus, um die Batterie zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="f5987-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="f5987-144">Verwenden von Surface pro 3-Firmware-Tools</span><span class="sxs-lookup"><span data-stu-id="f5987-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="f5987-145">Die Funktion für das Batterie Limit wird über die folgende Einstellung gesteuert:</span><span class="sxs-lookup"><span data-stu-id="f5987-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="f5987-146">**Name**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="f5987-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="f5987-147">**Beschreibung**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="f5987-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="f5987-148">**Aktueller Wert**:</span><span class="sxs-lookup"><span data-stu-id="f5987-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="f5987-149">**Standardwert**:</span><span class="sxs-lookup"><span data-stu-id="f5987-149">**Default Value**:</span></span> `0`

<span data-ttu-id="f5987-150">**Vorgeschlagener Wert**:</span><span class="sxs-lookup"><span data-stu-id="f5987-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="f5987-151">Wählen Sie diese `1` Option aus, um die Batterie zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="f5987-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="f5987-152">Um diese Einstellung zu konfigurieren, müssen Sie [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5987-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

