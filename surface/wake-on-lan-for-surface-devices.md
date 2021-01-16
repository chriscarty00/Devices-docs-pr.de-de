---
title: Wake On LAN für Surface-Geräte (Surface)
description: Erfahren Sie, wie Sie Wake On LAN verwenden können, um Geräte remote zu aktivieren, um Verwaltungs- oder Wartungsaufgaben auszuführen oder Verwaltungslösungen automatisch zu aktivieren – auch wenn die Geräte ausgeschaltet sind.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271122"
---
# <span data-ttu-id="8f266-104">Wake-On-LAN für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="8f266-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="8f266-105">Surface-Geräte, die Windows 10, Version 1607 (auch bekannt als Windows 10 Anniversary Update) oder höher ausführen und einen Surface-Ethernet-Adapter verwenden, um eine Verbindung mit einem kabelgebundenen Netzwerk herzustellen, können Wake On LAN (WOL) aus dem verbundenen Standbymodus verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f266-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="8f266-106">Mit WOL können Sie Geräte remote aktivieren, um Verwaltungs- oder Wartungsaufgaben auszuführen oder Verwaltungslösungen (z. B. Microsoft Endpoint Configuration Manager) automatisch zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f266-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="8f266-107">Sie können z. B. Anwendungen auf Surface-Geräten bereitstellen, die mit einem Surface Dock oder einer Surface Pro 3-Dockingstation angedockt sind, indem Sie Microsoft Endpoint Configuration Manager in einem Fenster mitten in der Nacht verwenden, wenn das Büro leer ist.</span><span class="sxs-lookup"><span data-stu-id="8f266-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="8f266-108">Surface-Geräte müssen mit dem Netzbetrieb verbunden sein und sich im verbundenen Standbymodus (Standbymodus) befindet, um WOL zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8f266-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="8f266-109">WOL ist von Geräten, die sich im Ruhezustand befinden oder ausgeschaltet sind, nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="8f266-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="8f266-110">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="8f266-110">Supported devices</span></span>

<span data-ttu-id="8f266-111">Die folgenden Geräte werden für WOL unterstützt:</span><span class="sxs-lookup"><span data-stu-id="8f266-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="8f266-112">Surface-Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="8f266-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="8f266-113">Surface USB-C zu Ethernet und #A0</span><span class="sxs-lookup"><span data-stu-id="8f266-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="8f266-114">Surface Dock</span><span class="sxs-lookup"><span data-stu-id="8f266-114">Surface Dock</span></span>
* <span data-ttu-id="8f266-115">Surface DockingStation für Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="8f266-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="8f266-116">Surface3</span><span class="sxs-lookup"><span data-stu-id="8f266-116">Surface 3</span></span>
* <span data-ttu-id="8f266-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="8f266-117">Surface Pro 3</span></span>
* <span data-ttu-id="8f266-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8f266-118">Surface Pro 4</span></span>
* <span data-ttu-id="8f266-119">Surface Pro (5. Generation)</span><span class="sxs-lookup"><span data-stu-id="8f266-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="8f266-120">Surface Pro (5. Generation) mit LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="8f266-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="8f266-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="8f266-121">Surface Book</span></span>
* <span data-ttu-id="8f266-122">Surface Laptop (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="8f266-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="8f266-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="8f266-123">Surface Pro 6</span></span>
* <span data-ttu-id="8f266-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="8f266-124">Surface Book 2</span></span>
* <span data-ttu-id="8f266-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="8f266-125">Surface Laptop 2</span></span>
* <span data-ttu-id="8f266-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="8f266-126">Surface Go</span></span>
* <span data-ttu-id="8f266-127">Surface Go mit LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="8f266-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="8f266-128">Surface Studio 2 (siehe Surface Studio 2-Anweisungen unten)</span><span class="sxs-lookup"><span data-stu-id="8f266-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="8f266-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8f266-129">Surface Pro 7</span></span>
* <span data-ttu-id="8f266-130">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="8f266-130">Surface Laptop 3</span></span>
* <span data-ttu-id="8f266-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="8f266-131">Surface Laptop Go</span></span>
* <span data-ttu-id="8f266-132">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="8f266-132">Surface Pro 7+</span></span>

## <span data-ttu-id="8f266-133">DRIVER</span><span class="sxs-lookup"><span data-stu-id="8f266-133">WOL driver</span></span>

<span data-ttu-id="8f266-134">Zum Aktivieren der UNTERSTÜTZUNG von WOL auf Surface-Geräten ist ein bestimmter Treiber für den Surface-Ethernet-Adapter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f266-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="8f266-135">Dieser Treiber ist nicht im Standardtreiber- und Firmwarepaket für Surface-Geräte enthalten– Sie müssen ihn separat herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="8f266-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="8f266-136">Sie können den Surface -WOL-Treiber (SurfaceWOL.msi) von der [Seite "Surface Tools for IT"](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8f266-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="8f266-137">Sie können diese Microsoft Windows Installer (.msi)-Datei auf einem Surface-Gerät ausführen, um den Surface -WOL-Treiber zu installieren, oder Sie können ihn mit einer Anwendungsbereitstellungslösung, z. B. Microsoft Endpoint Configuration Manager, auf Surface-Geräten verteilen.</span><span class="sxs-lookup"><span data-stu-id="8f266-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="8f266-138">Wenn Sie den Surface -WOL-Treiber während der Bereitstellung verwenden möchten, können Sie die .msi-Datei während des Bereitstellungsprozesses als Anwendung installieren.</span><span class="sxs-lookup"><span data-stu-id="8f266-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="8f266-139">Sie können auch die Surface -WOL-Treiberdateien extrahieren, um sie in den Bereitstellungsprozess zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f266-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="8f266-140">Sie können sie beispielsweise in Ihre Microsoft Deployment Toolkit (MDT)-Bereitstellungsfreigabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f266-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="8f266-141">Weitere Informationen zur Bereitstellung von Surface mit MDT finden Sie unter "Bereitstellen von [Windows 10 auf Surface-Geräten mit Dem Microsoft Deployment Toolkit".](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)</span><span class="sxs-lookup"><span data-stu-id="8f266-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="8f266-142">Während der Installation von SurfaceWOL.msi wird der folgende Registrierungsschlüssel auf den Wert 1 festgelegt, was eine einfache Identifizierung von Systemen ermöglicht, auf denen der TREIBER "WOL" installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8f266-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="8f266-143">Wenn Sie diese Treiber während der Bereitstellung separat extrahieren und installieren möchten, wird dieser Registrierungsschlüssel nicht konfiguriert und muss manuell oder mit einem Skript konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8f266-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="8f266-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="8f266-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="8f266-145">Um den Inhalt von SurfaceWOL.msi zu extrahieren, verwenden Sie die Verwaltungsinstallationsoption MSIExec (**/a),** wie im folgenden Beispiel gezeigt, um den Inhalt in den Ordner "C:\WOL\" zu extrahieren:</span><span class="sxs-lookup"><span data-stu-id="8f266-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="8f266-146">Surface Studio 2-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8f266-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="8f266-147">Zum Aktivieren von WOL auf Surface Studio 2 müssen Sie das folgende Verfahren verwenden:</span><span class="sxs-lookup"><span data-stu-id="8f266-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="8f266-148">Erstellen Sie die folgenden Registrierungsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="8f266-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="8f266-149">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8f266-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="8f266-150">Verwenden von Surface WOL</span><span class="sxs-lookup"><span data-stu-id="8f266-150">Using Surface WOL</span></span>

<span data-ttu-id="8f266-151">Der Surface -WOL-Treiber entspricht dem WOL-Standard, wobei das Gerät durch eine spezielle Netzwerkkommunikation, die als "Magisches Paket" bezeichnet wird, aufgewunken wird.</span><span class="sxs-lookup"><span data-stu-id="8f266-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="8f266-152">Das magische Paket besteht aus 6 Byte von 255 (oder FF in Hexadezimal), gefolgt von 16 Wiederholungen der MAC-Adresse des Zielcomputers.</span><span class="sxs-lookup"><span data-stu-id="8f266-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="8f266-153">Weitere Informationen zum magischen Paket und zum STANDARD "WOL" finden Sie auf [Wikipedia.](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)</span><span class="sxs-lookup"><span data-stu-id="8f266-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="8f266-154">Um ein magisches Paket zu senden und ein Gerät mithilfe von WOL zu reaktivierungen, müssen Sie die MAC-Adresse des Zielgeräts und des Ethernetadapters kennen.</span><span class="sxs-lookup"><span data-stu-id="8f266-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="8f266-155">Da das Magerpaket nicht das IP-Netzwerkprotokoll verwendet, ist es nicht möglich, die IP-Adresse oder den DNS-Namen des Geräts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f266-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="8f266-156">Viele Verwaltungslösungen, z. B. Configuration Manager, bieten integrierte Unterstützung für WOL.</span><span class="sxs-lookup"><span data-stu-id="8f266-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="8f266-157">Es gibt auch viele Lösungen, einschließlich Microsoft Store-Apps, PowerShell-Modulen, Drittanbieteranwendungen und Verwaltungslösungen von Drittanbietern, mit denen Sie ein magisches Paket senden können, um ein Gerät zu reaktivierungen.</span><span class="sxs-lookup"><span data-stu-id="8f266-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="8f266-158">Beispielsweise können Sie das [Wake On LAN -PowerShell-Modul](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) aus dem TechNet Script Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f266-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="8f266-159">Nachdem ein Gerät mit einem magischen Paket aufgewunken wurde, wird das Gerät wieder in den Ruhezustand zurückver setzt, wenn eine Anwendung den Ruhezustand auf dem System nicht aktiv verhindert oder wenn der Registrierungsschlüssel "AllowSystemRequiredPowerRequests" nicht auf 1 konfiguriert ist, wodurch Anwendungen den Ruhezustand verhindern können.</span><span class="sxs-lookup"><span data-stu-id="8f266-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="8f266-160">Weitere Informationen [zu diesem Registrierungsschlüssel](#wol-driver) finden Sie im Abschnitt zu den DRIVER-Treibern in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="8f266-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
