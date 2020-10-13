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
ms.openlocfilehash: a56f6e01a4d7bf1cc40d73f34c3abf8e04443989
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114613"
---
# Wake-On-LAN für Surface-Geräte

Surface-Geräte, auf denen Windows 10, Version 1607 (auch bekannt als Windows 10 Anniversary Update) oder höher ausgeführt wird und einen Surface-Ethernet-Adapter zum Herstellen einer Verbindung mit einem kabelgebundenen Netzwerk verwenden, können aus dem verbundenen Standbymodus auf Wake-on-LAN (WOL) zugreifen. Mit WOL können Sie Geräte Remote reaktivieren, um Verwaltungs-oder Wartungsaufgaben auszuführen oder Verwaltungslösungen (wie Microsoft Endpoint Configuration Manager) automatisch zu aktivieren. So können Sie beispielsweise Anwendungen auf Surface-Geräten bereitstellen, die mit einer Dockingstation für Surface Dock oder Surface pro 3 angedockt sind, indem Sie den Microsoft Endpoint Configuration Manager in einem Fenster mitten in der Nacht verwenden, wenn das Office leer ist.

>[!NOTE]
>Surface-Geräte müssen mit dem Stromnetz verbunden sein und im Standby-Modus (Sleep) zur Unterstützung von WOL angeschlossen sein. WOL ist von Geräten, die sich im Ruhezustand befinden oder ausgeschaltet sind, nicht möglich.

## Unterstützte Geräte

Die folgenden Geräte werden für WOL unterstützt:

* Surface-Ethernet-Adapter
* Surface USB-C zu Ethernet und USB-Adapter
* Surface Dock
* Surface-Docking-Station für Surface pro 3
* Surface3
* Surface Pro 3
* Surface Pro 4
* Surface pro (fünfte Generation)
* Surface pro (5th Gen) mit LTE Advanced
* Surface Book
* Surface-Laptop (1st Generation)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go mit LTE Advanced
* Surface Studio 2 (siehe Surface Studio 2-Anleitung unten)
* Surface Pro 7
* Surface Laptop 3
* Surface Laptop go

## WOL-Treiber

Um die WOL-Unterstützung auf Surface-Geräten zu aktivieren, ist ein bestimmter Treiber für den Surface-Ethernet-Adapter erforderlich. Dieser Treiber ist nicht im Standardtreiber-und Firmware-Paket für Surface-Geräte enthalten – Sie müssen ihn separat herunterladen und installieren. Sie können den Surface WOL-Treiber (SurfaceWOL.msi) über die Seite [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.

Sie können diese Microsoft Windows Installer-Datei (MSI) auf einem Surface-Gerät ausführen, um den Surface WOL-Treiber zu installieren, oder Sie können Sie mit einer Anwendungs Bereitstellungslösung wie dem Microsoft Endpoint Configuration Manager auf Surface-Geräte verteilen. Wenn Sie den Surface WOL-Treiber während der Bereitstellung einbeziehen möchten, können Sie die MSI-Datei während des Bereitstellungsprozesses als Anwendung installieren. Sie können auch die Surface WOL-Treiberdateien extrahieren, um Sie in den Bereitstellungsprozess einzubeziehen. Sie können Sie beispielsweise in Ihre Bereitstellungsfreigabe für Microsoft Deployment Toolkit (MDT) aufnehmen. Weitere Informationen zur Oberflächen Bereitstellung mit MDT finden Sie unter [Bereitstellen von Windows 10 auf Surface Devices mit Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).

> [!NOTE]
> Während der Installation von SurfaceWOL.msi wird der folgende Registrierungsschlüssel auf den Wert 1 festgesetzt, was eine einfache Identifizierung von Systemen ermöglicht, auf denen der WOL-Treiber installiert wurde. Wenn Sie sich entschieden haben, diese Treiber während der Bereitstellung separat zu extrahieren und zu installieren, wird dieser Registrierungsschlüssel nicht konfiguriert und muss manuell oder mit einem Skript konfiguriert werden.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Um den Inhalt von SurfaceWOL.msi zu extrahieren, verwenden Sie die Option für die administrative Installation von msiexec (**/a**), wie im folgenden Beispiel gezeigt, um den Inhalt in den C:\WOL\-Ordner zu extrahieren:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Surface Studio 2-Anweisungen

Um WOL auf Surface Studio 2 zu aktivieren, müssen Sie das folgende Verfahren verwenden:

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

2. Führen Sie den folgenden Befehl aus.

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Verwenden von Surface WOL

Der Surface WOL-Treiber entspricht dem WOL-Standard, wobei das Gerät durch eine spezielle Netzwerkkommunikation geweckt wird, die als magisches Paket bezeichnet wird. Das Magic-Paket besteht aus 6 Bytes von 255 (oder FF im Hexadezimalformat) gefolgt von 16 Wiederholungen der Mac-Adresse des Zielcomputers. Weitere Informationen zum Magic-Paket und dem WOL-Standard finden Sie unter [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).

>[!NOTE]
>Wenn Sie ein magisches Paket senden und ein Gerät mithilfe von WOL aufwachen möchten, müssen Sie die Mac-Adresse des Zielgeräts und des Ethernet-Adapters kennen. Da das Magic-Paket das IP-Netzwerkprotokoll nicht verwendet, ist es nicht möglich, die IP-Adresse oder den DNS-Namen des Geräts zu verwenden.

Viele Verwaltungslösungen wie Configuration Manager bieten integrierte Unterstützung für WOL. Es gibt auch viele Lösungen, einschließlich Microsoft Store-Apps, PowerShell-Modulen, Anwendungen von Drittanbietern und Verwaltungslösungen von Drittanbietern, mit denen Sie ein magisches Paket senden können, um ein Gerät zu reaktivieren. So können Sie beispielsweise das [PowerShell-Modul Wake-on-LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) aus dem TechNet-Skript Center verwenden. 

>[!NOTE]
>Nachdem ein Gerät mit einem Magic-Paket geweckt wurde, wird das Gerät wieder in den Standbymodus versetzt, wenn eine Anwendung den Ruhezustand des Systems nicht aktiv verhindert oder wenn der AllowSystemRequiredPowerRequests-Registrierungsschlüssel nicht auf 1 konfiguriert ist, wodurch Anwendungen den Ruhezustand verhindern können. Weitere Informationen zu diesem Registrierungsschlüssel finden Sie im Abschnitt [WOL-Treiber](#wol-driver) in diesem Artikel.
