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
ms.openlocfilehash: 9c3302616de97cf60b7d750948fed653456a7cba
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442889"
---
# <a name="wake-on-lan-for-surface-devices"></a>Wake-On-LAN für Surface-Geräte

Surface-Geräte, die einen Surface -Ethernet-Adapter zum Herstellen einer Verbindung mit einem verkabelten Netzwerk verwenden, können wake On LAN (WOL) aus dem verbundenen Standbymodus nutzen. Mit WOL können Sie Geräte remote aktivieren und automatisch Verwaltungsaufgaben mithilfe von Verwaltungslösungen wie Microsoft Endpoint Manager/Microsoft Intune ausführen.

## <a name="wol-supported-devices"></a>VON WOL unterstützte Geräte

- Surface -Ethernet-Adapter
- Surface USB-C zu Ethernet und USB Adapter
- Surface Dock 2
- Surface Pro 6 und höher
- Surface Book (alle Generationen)
- Surface Laptop (alle Generationen)
- Surface Go (alle Generationen)
- Surface Studio 2 (siehe Anhang)


## <a name="using-surface-wol"></a>Verwenden von Surface WOL

IT-Administratoren können Geräte mithilfe einer Wake-on-LAN-Anforderung (Magisches Paket) auslösen, die die MAC-Adresse des Zielcomputers enthält. Um ein Magisches Paket zu senden und ein Gerät mithilfe von WOL zu wecken, müssen Sie die MAC-Adresse des Zielgeräts und den Ethernetadapter kennen. Da das Magische Paket nicht das IP-Netzwerkprotokoll verwendet, ist es nicht möglich, die IP-Adresse oder den DNS-Namen des Geräts zu verwenden.

Viele Verwaltungslösungen, z. B. Microsoft Endpoint Configuration Manager und Microsoft Store-Apps von Drittanbietern, bieten integrierte Unterstützung für WOL. Beachten Sie, dass sich Geräte im Modus "Verbundener Standbymodus" (Standbymodus) befinden und mit Netzstrom verbunden sein müssen. Weitere Informationen zum Aufwachen von Geräten mit Endpoint Configuration Manager finden Sie unter [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).


### <a name="to-check-wol-is-enabled-on-your-device"></a>So überprüfen Sie, ob WOL auf Ihrem Gerät aktiviert ist

1. Wählen Sie auf Ihrem ethernetgebundenen Gerät den Netzwerkadapter aus, und wählen Sie dann **Eigenschaften aus.**

   > [!div class="mx-imgBorder"]
   > ![Surface Ethernet Adapter](images/surface-ethernet.png)

2. Wählen **Sie Erweitert**konfigurieren  >  **aus.**
3. Scrollen Sie zu **Modern Standby WoL Magic Packet,** und stellen Sie **sicher, dass Enabled** ausgewählt ist.

     ![Überprüfen, ob "WOL" auf Ihrem Gerät aktiviert ist](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a>Anhang: Surface Studio 2

Verwenden Sie das folgende Verfahren, um WOL auf Surface Studio 2 zu aktivieren.

1. Erstellen Sie die folgenden Registrierungsschlüssel:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Führen Sie den folgenden Befehl aus

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Surface USB-C-zu-Ethernet- und #A0](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Surface USB 3.0 Gigabit Ethernet Adapter](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
