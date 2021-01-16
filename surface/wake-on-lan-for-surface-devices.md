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
# Wake-On-LAN für Surface-Geräte

Surface-Geräte, die Windows 10, Version 1607 (auch bekannt als Windows 10 Anniversary Update) oder höher ausführen und einen Surface-Ethernet-Adapter verwenden, um eine Verbindung mit einem kabelgebundenen Netzwerk herzustellen, können Wake On LAN (WOL) aus dem verbundenen Standbymodus verwenden. Mit WOL können Sie Geräte remote aktivieren, um Verwaltungs- oder Wartungsaufgaben auszuführen oder Verwaltungslösungen (z. B. Microsoft Endpoint Configuration Manager) automatisch zu aktivieren. Sie können z. B. Anwendungen auf Surface-Geräten bereitstellen, die mit einem Surface Dock oder einer Surface Pro 3-Dockingstation angedockt sind, indem Sie Microsoft Endpoint Configuration Manager in einem Fenster mitten in der Nacht verwenden, wenn das Büro leer ist.

>[!NOTE]
>Surface-Geräte müssen mit dem Netzbetrieb verbunden sein und sich im verbundenen Standbymodus (Standbymodus) befindet, um WOL zu unterstützen. WOL ist von Geräten, die sich im Ruhezustand befinden oder ausgeschaltet sind, nicht möglich.

## Unterstützte Geräte

Die folgenden Geräte werden für WOL unterstützt:

* Surface-Ethernet-Adapter
* Surface USB-C zu Ethernet und #A0
* Surface Dock
* Surface DockingStation für Surface Pro 3
* Surface3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (5. Generation)
* Surface Pro (5. Generation) mit LTE Advanced
* Surface Book
* Surface Laptop (1. Generation)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go mit LTE Advanced
* Surface Studio 2 (siehe Surface Studio 2-Anweisungen unten)
* Surface Pro 7
* Surface Laptop 3
* Surface Laptop Go
* Surface Pro 7+

## DRIVER

Zum Aktivieren der UNTERSTÜTZUNG von WOL auf Surface-Geräten ist ein bestimmter Treiber für den Surface-Ethernet-Adapter erforderlich. Dieser Treiber ist nicht im Standardtreiber- und Firmwarepaket für Surface-Geräte enthalten– Sie müssen ihn separat herunterladen und installieren. Sie können den Surface -WOL-Treiber (SurfaceWOL.msi) von der [Seite "Surface Tools for IT"](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.

Sie können diese Microsoft Windows Installer (.msi)-Datei auf einem Surface-Gerät ausführen, um den Surface -WOL-Treiber zu installieren, oder Sie können ihn mit einer Anwendungsbereitstellungslösung, z. B. Microsoft Endpoint Configuration Manager, auf Surface-Geräten verteilen. Wenn Sie den Surface -WOL-Treiber während der Bereitstellung verwenden möchten, können Sie die .msi-Datei während des Bereitstellungsprozesses als Anwendung installieren. Sie können auch die Surface -WOL-Treiberdateien extrahieren, um sie in den Bereitstellungsprozess zu verwenden. Sie können sie beispielsweise in Ihre Microsoft Deployment Toolkit (MDT)-Bereitstellungsfreigabe verwenden. Weitere Informationen zur Bereitstellung von Surface mit MDT finden Sie unter "Bereitstellen von [Windows 10 auf Surface-Geräten mit Dem Microsoft Deployment Toolkit".](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)

> [!NOTE]
> Während der Installation von SurfaceWOL.msi wird der folgende Registrierungsschlüssel auf den Wert 1 festgelegt, was eine einfache Identifizierung von Systemen ermöglicht, auf denen der TREIBER "WOL" installiert wurde. Wenn Sie diese Treiber während der Bereitstellung separat extrahieren und installieren möchten, wird dieser Registrierungsschlüssel nicht konfiguriert und muss manuell oder mit einem Skript konfiguriert werden.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Um den Inhalt von SurfaceWOL.msi zu extrahieren, verwenden Sie die Verwaltungsinstallationsoption MSIExec (**/a),** wie im folgenden Beispiel gezeigt, um den Inhalt in den Ordner "C:\WOL\" zu extrahieren:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Surface Studio 2-Anweisungen

Zum Aktivieren von WOL auf Surface Studio 2 müssen Sie das folgende Verfahren verwenden:

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

2. Führen Sie den folgenden Befehl aus:

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Verwenden von Surface WOL

Der Surface -WOL-Treiber entspricht dem WOL-Standard, wobei das Gerät durch eine spezielle Netzwerkkommunikation, die als "Magisches Paket" bezeichnet wird, aufgewunken wird. Das magische Paket besteht aus 6 Byte von 255 (oder FF in Hexadezimal), gefolgt von 16 Wiederholungen der MAC-Adresse des Zielcomputers. Weitere Informationen zum magischen Paket und zum STANDARD "WOL" finden Sie auf [Wikipedia.](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)

>[!NOTE]
>Um ein magisches Paket zu senden und ein Gerät mithilfe von WOL zu reaktivierungen, müssen Sie die MAC-Adresse des Zielgeräts und des Ethernetadapters kennen. Da das Magerpaket nicht das IP-Netzwerkprotokoll verwendet, ist es nicht möglich, die IP-Adresse oder den DNS-Namen des Geräts zu verwenden.

Viele Verwaltungslösungen, z. B. Configuration Manager, bieten integrierte Unterstützung für WOL. Es gibt auch viele Lösungen, einschließlich Microsoft Store-Apps, PowerShell-Modulen, Drittanbieteranwendungen und Verwaltungslösungen von Drittanbietern, mit denen Sie ein magisches Paket senden können, um ein Gerät zu reaktivierungen. Beispielsweise können Sie das [Wake On LAN -PowerShell-Modul](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) aus dem TechNet Script Center verwenden. 

>[!NOTE]
>Nachdem ein Gerät mit einem magischen Paket aufgewunken wurde, wird das Gerät wieder in den Ruhezustand zurückver setzt, wenn eine Anwendung den Ruhezustand auf dem System nicht aktiv verhindert oder wenn der Registrierungsschlüssel "AllowSystemRequiredPowerRequests" nicht auf 1 konfiguriert ist, wodurch Anwendungen den Ruhezustand verhindern können. Weitere Informationen [zu diesem Registrierungsschlüssel](#wol-driver) finden Sie im Abschnitt zu den DRIVER-Treibern in diesem Artikel.
