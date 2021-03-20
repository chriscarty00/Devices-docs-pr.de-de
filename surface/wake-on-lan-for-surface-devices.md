---
title: Wake-On-LAN für Surface-Geräte
description: Erfahren Sie, wie Sie Wake On LAN verwenden können, um Geräte remote zu aktivieren, um Verwaltungsaufgaben automatisch auszuführen.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442161"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="7e56a-104">Wake-On-LAN für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="7e56a-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="7e56a-105">Surface-Geräte, die einen Surface -Ethernet-Adapter zum Herstellen einer Verbindung mit einem verkabelten Netzwerk verwenden, können wake On LAN (WOL) aus dem verbundenen Standbymodus nutzen.</span><span class="sxs-lookup"><span data-stu-id="7e56a-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="7e56a-106">Mit WOL können Sie Geräte remote aktivieren und automatisch Verwaltungsaufgaben mithilfe von Verwaltungslösungen wie Microsoft Endpoint Manager/Microsoft Intune ausführen.</span><span class="sxs-lookup"><span data-stu-id="7e56a-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="7e56a-107">VON WOL unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="7e56a-107">WOL-supported devices</span></span>

- <span data-ttu-id="7e56a-108">Surface -Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="7e56a-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="7e56a-109">Surface USB-C zu Ethernet und USB Adapter</span><span class="sxs-lookup"><span data-stu-id="7e56a-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="7e56a-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="7e56a-110">Surface Dock 2</span></span>
- <span data-ttu-id="7e56a-111">Surface Pro 6 und höher</span><span class="sxs-lookup"><span data-stu-id="7e56a-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="7e56a-112">Surface Book (alle Generationen)</span><span class="sxs-lookup"><span data-stu-id="7e56a-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="7e56a-113">Surface Laptop (alle Generationen)</span><span class="sxs-lookup"><span data-stu-id="7e56a-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="7e56a-114">Surface Go (alle Generationen)</span><span class="sxs-lookup"><span data-stu-id="7e56a-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="7e56a-115">Surface Studio 2 (siehe Anhang)</span><span class="sxs-lookup"><span data-stu-id="7e56a-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="7e56a-116">Verwenden von Surface WOL</span><span class="sxs-lookup"><span data-stu-id="7e56a-116">Using Surface WOL</span></span>

<span data-ttu-id="7e56a-117">IT-Administratoren können Geräte mithilfe einer Wake-on-LAN-Anforderung (Magisches Paket) auslösen, die die MAC-Adresse des Zielcomputers enthält.</span><span class="sxs-lookup"><span data-stu-id="7e56a-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="7e56a-118">Um ein Magisches Paket zu senden und ein Gerät mithilfe von WOL zu wecken, müssen Sie die MAC-Adresse des Zielgeräts und den Ethernetadapter kennen.</span><span class="sxs-lookup"><span data-stu-id="7e56a-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="7e56a-119">Da das Magische Paket nicht das IP-Netzwerkprotokoll verwendet, ist es nicht möglich, die IP-Adresse oder den DNS-Namen des Geräts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e56a-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="7e56a-120">Viele Verwaltungslösungen, z. B. Microsoft Endpoint Configuration Manager und Microsoft Store-Apps von Drittanbietern, bieten integrierte Unterstützung für WOL.</span><span class="sxs-lookup"><span data-stu-id="7e56a-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="7e56a-121">Beachten Sie, dass sich Geräte im Modus "Verbundener Standbymodus" (Standbymodus) befinden und mit Netzstrom verbunden sein müssen.</span><span class="sxs-lookup"><span data-stu-id="7e56a-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="7e56a-122">Weitere Informationen zum Aufwachen von Geräten mit Endpoint Configuration Manager finden Sie unter [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span><span class="sxs-lookup"><span data-stu-id="7e56a-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


## <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="7e56a-123">So überprüfen Sie, ob WOL auf Ihrem Gerät aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="7e56a-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="7e56a-124">Wählen Sie auf Ihrem ethernetgebundenen Gerät den Netzwerkadapter aus, und wählen Sie dann **Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="7e56a-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Surface Ethernet Adapter](images/surface-ethernet.png)

2. <span data-ttu-id="7e56a-126">Wählen **Sie Erweitert**konfigurieren  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="7e56a-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="7e56a-127">Scrollen Sie zu **Modern Standby WoL Magic Packet,** und stellen Sie **sicher, dass Enabled** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7e56a-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![Überprüfen, ob "WOL" auf Ihrem Gerät aktiviert ist](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="7e56a-129">Anhang: Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="7e56a-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="7e56a-130">Verwenden Sie das folgende Verfahren, um WOL auf Surface Studio 2 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e56a-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="7e56a-131">Erstellen Sie die folgenden Registrierungsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="7e56a-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="7e56a-132">Führen Sie den folgenden Befehl aus</span><span class="sxs-lookup"><span data-stu-id="7e56a-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="7e56a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e56a-133">Learn more</span></span>

- [<span data-ttu-id="7e56a-134">Microsoft Surface USB-C-zu-Ethernet- und #A0</span><span class="sxs-lookup"><span data-stu-id="7e56a-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="7e56a-135">Surface USB 3.0 Gigabit Ethernet Adapter</span><span class="sxs-lookup"><span data-stu-id="7e56a-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
