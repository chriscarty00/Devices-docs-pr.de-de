---
title: Wake-on-LAN für Surface Devices (Surface)
description: Schauen Sie sich an, wie Sie Wake-on-LAN verwenden können, um Geräte zur Durchführung von Verwaltungs-oder Wartungsaufgaben Remote zu reaktivieren oder Verwaltungslösungen automatisch zu aktivieren – selbst wenn die Geräte heruntergefahren sind.
keywords: Update, bereitstellen, Treiber, wol, Wake-on-LAN
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
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833151"
---
# <span data-ttu-id="19106-104">Wake-On-LAN für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="19106-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="19106-105">Surface-Geräte, auf denen Windows 10, Version 1607 (auch bekannt als Windows 10 Anniversary Update) oder höher ausgeführt wird und einen Surface-Ethernet-Adapter zum Herstellen einer Verbindung mit einem kabelgebundenen Netzwerk verwenden, können aus dem verbundenen Standbymodus auf Wake-on-LAN (WOL) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="19106-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="19106-106">Mit WOL können Sie Geräte Remote reaktivieren, um Verwaltungs-oder Wartungsaufgaben auszuführen oder Verwaltungslösungen (wie Microsoft Endpoint Configuration Manager) automatisch zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="19106-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="19106-107">So können Sie beispielsweise Anwendungen auf Surface-Geräten bereitstellen, die mit einer Dockingstation für Surface Dock oder Surface pro 3 angedockt sind, indem Sie den Microsoft Endpoint Configuration Manager in einem Fenster mitten in der Nacht verwenden, wenn das Office leer ist.</span><span class="sxs-lookup"><span data-stu-id="19106-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="19106-108">Surface-Geräte müssen mit dem Stromnetz verbunden sein und im Standby-Modus (Sleep) zur Unterstützung von WOL angeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="19106-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="19106-109">WOL ist von Geräten, die sich im Ruhezustand befinden oder ausgeschaltet sind, nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="19106-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="19106-110">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="19106-110">Supported devices</span></span>

<span data-ttu-id="19106-111">Die folgenden Geräte werden für WOL unterstützt:</span><span class="sxs-lookup"><span data-stu-id="19106-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="19106-112">Surface-Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="19106-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="19106-113">Surface USB-C zu Ethernet und USB-Adapter</span><span class="sxs-lookup"><span data-stu-id="19106-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="19106-114">Surface Dock</span><span class="sxs-lookup"><span data-stu-id="19106-114">Surface Dock</span></span>
* <span data-ttu-id="19106-115">Surface-Docking-Station für Surface pro 3</span><span class="sxs-lookup"><span data-stu-id="19106-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="19106-116">Surface3</span><span class="sxs-lookup"><span data-stu-id="19106-116">Surface 3</span></span>
* <span data-ttu-id="19106-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="19106-117">Surface Pro 3</span></span>
* <span data-ttu-id="19106-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="19106-118">Surface Pro 4</span></span>
* <span data-ttu-id="19106-119">Surface pro (fünfte Generation)</span><span class="sxs-lookup"><span data-stu-id="19106-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="19106-120">Surface pro (5th Gen) mit LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="19106-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="19106-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="19106-121">Surface Book</span></span>
* <span data-ttu-id="19106-122">Surface-Laptop (1st Generation)</span><span class="sxs-lookup"><span data-stu-id="19106-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="19106-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="19106-123">Surface Pro 6</span></span>
* <span data-ttu-id="19106-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="19106-124">Surface Book 2</span></span>
* <span data-ttu-id="19106-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="19106-125">Surface Laptop 2</span></span>
* <span data-ttu-id="19106-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="19106-126">Surface Go</span></span>
* <span data-ttu-id="19106-127">Surface Go mit LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="19106-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="19106-128">Surface Studio 2 (siehe Surface Studio 2-Anleitung unten)</span><span class="sxs-lookup"><span data-stu-id="19106-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="19106-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="19106-129">Surface Pro 7</span></span>
* <span data-ttu-id="19106-130">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="19106-130">Surface Laptop 3</span></span>

## <span data-ttu-id="19106-131">WOL-Treiber</span><span class="sxs-lookup"><span data-stu-id="19106-131">WOL driver</span></span>

<span data-ttu-id="19106-132">Um die WOL-Unterstützung auf Surface-Geräten zu aktivieren, ist ein bestimmter Treiber für den Surface-Ethernet-Adapter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="19106-132">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="19106-133">Dieser Treiber ist nicht im Standardtreiber-und Firmware-Paket für Surface-Geräte enthalten – Sie müssen ihn separat herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="19106-133">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="19106-134">Sie können den Surface WOL-Treiber (SurfaceWOL.msi) über die Seite [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="19106-134">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="19106-135">Sie können diese Microsoft Windows Installer-Datei (MSI) auf einem Surface-Gerät ausführen, um den Surface WOL-Treiber zu installieren, oder Sie können Sie mit einer Anwendungs Bereitstellungslösung wie dem Microsoft Endpoint Configuration Manager auf Surface-Geräte verteilen.</span><span class="sxs-lookup"><span data-stu-id="19106-135">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="19106-136">Wenn Sie den Surface WOL-Treiber während der Bereitstellung einbeziehen möchten, können Sie die MSI-Datei während des Bereitstellungsprozesses als Anwendung installieren.</span><span class="sxs-lookup"><span data-stu-id="19106-136">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="19106-137">Sie können auch die Surface WOL-Treiberdateien extrahieren, um Sie in den Bereitstellungsprozess einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="19106-137">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="19106-138">Sie können Sie beispielsweise in Ihre Bereitstellungsfreigabe für Microsoft Deployment Toolkit (MDT) aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="19106-138">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="19106-139">Weitere Informationen zur Oberflächen Bereitstellung mit MDT finden Sie unter [Bereitstellen von Windows 10 auf Surface Devices mit Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span><span class="sxs-lookup"><span data-stu-id="19106-139">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="19106-140">Während der Installation von SurfaceWOL.msi wird der folgende Registrierungsschlüssel auf den Wert 1 festgesetzt, was eine einfache Identifizierung von Systemen ermöglicht, auf denen der WOL-Treiber installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="19106-140">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="19106-141">Wenn Sie sich entschieden haben, diese Treiber während der Bereitstellung separat zu extrahieren und zu installieren, wird dieser Registrierungsschlüssel nicht konfiguriert und muss manuell oder mit einem Skript konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="19106-141">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="19106-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="19106-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="19106-143">Um den Inhalt von SurfaceWOL.msi zu extrahieren, verwenden Sie die Option für die administrative Installation von msiexec (**/a**), wie im folgenden Beispiel gezeigt, um den Inhalt in den C:\WOL\-Ordner zu extrahieren:</span><span class="sxs-lookup"><span data-stu-id="19106-143">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="19106-144">Surface Studio 2-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="19106-144">Surface Studio 2 instructions</span></span>

<span data-ttu-id="19106-145">Um WOL auf Surface Studio 2 zu aktivieren, müssen Sie das folgende Verfahren verwenden:</span><span class="sxs-lookup"><span data-stu-id="19106-145">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="19106-146">Erstellen Sie die folgenden Registrierungsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="19106-146">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="19106-147">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="19106-147">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="19106-148">Verwenden von Surface WOL</span><span class="sxs-lookup"><span data-stu-id="19106-148">Using Surface WOL</span></span>

<span data-ttu-id="19106-149">Der Surface WOL-Treiber entspricht dem WOL-Standard, wobei das Gerät durch eine spezielle Netzwerkkommunikation geweckt wird, die als magisches Paket bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="19106-149">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="19106-150">Das Magic-Paket besteht aus 6 Bytes von 255 (oder FF im Hexadezimalformat) gefolgt von 16 Wiederholungen der Mac-Adresse des Zielcomputers.</span><span class="sxs-lookup"><span data-stu-id="19106-150">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="19106-151">Weitere Informationen zum Magic-Paket und dem WOL-Standard finden Sie unter [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span><span class="sxs-lookup"><span data-stu-id="19106-151">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="19106-152">Wenn Sie ein magisches Paket senden und ein Gerät mithilfe von WOL aufwachen möchten, müssen Sie die Mac-Adresse des Zielgeräts und des Ethernet-Adapters kennen.</span><span class="sxs-lookup"><span data-stu-id="19106-152">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="19106-153">Da das Magic-Paket das IP-Netzwerkprotokoll nicht verwendet, ist es nicht möglich, die IP-Adresse oder den DNS-Namen des Geräts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="19106-153">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="19106-154">Viele Verwaltungslösungen wie Configuration Manager bieten integrierte Unterstützung für WOL.</span><span class="sxs-lookup"><span data-stu-id="19106-154">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="19106-155">Es gibt auch viele Lösungen, einschließlich Microsoft Store-Apps, PowerShell-Modulen, Anwendungen von Drittanbietern und Verwaltungslösungen von Drittanbietern, mit denen Sie ein magisches Paket senden können, um ein Gerät zu reaktivieren.</span><span class="sxs-lookup"><span data-stu-id="19106-155">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="19106-156">So können Sie beispielsweise das [PowerShell-Modul Wake-on-LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) aus dem TechNet-Skript Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="19106-156">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="19106-157">Nachdem ein Gerät mit einem Magic-Paket geweckt wurde, wird das Gerät wieder in den Standbymodus versetzt, wenn eine Anwendung den Ruhezustand des Systems nicht aktiv verhindert oder wenn der AllowSystemRequiredPowerRequests-Registrierungsschlüssel nicht auf 1 konfiguriert ist, wodurch Anwendungen den Ruhezustand verhindern können.</span><span class="sxs-lookup"><span data-stu-id="19106-157">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="19106-158">Weitere Informationen zu diesem Registrierungsschlüssel finden Sie im Abschnitt [WOL-Treiber](#wol-driver) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="19106-158">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
