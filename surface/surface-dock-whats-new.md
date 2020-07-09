---
title: Neuerungen in Surface Dock 2
description: In diesem Artikel werden die neuen Features und Funktionen für das Surface Dock der nächsten Generation hervorgehoben.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/25/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 1f6f4a7efb8dc345487e5e5054374f81a91a20d5
ms.sourcegitcommit: 36bac9da2f7b0815fbceb008f869b497380c55db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "10860635"
---
# Neuerungen in Surface Dock 2

Surface Dock 2, das Surface Dock der nächsten Generation, ermöglicht Benutzern das Verbinden externer Monitore und mehrerer Peripheriegeräte, um eine vollständig modernisierte Desktopoberfläche von einem Surface-Gerät zu erhalten. Für die Maximierung der Effizienz im Büro, in einem flexiblen Arbeitsbereich oder zu Hause bietet Surface Dock 2 sieben Anschlüsse, darunter zwei frontseitige USB-C-Anschlüsse mit 15 Watt Schnelllade Leistung für Telefone und Zubehör. 

### Unterstützung für vollständige Geräteverwaltung

Surface Dock 2 wurde entwickelt, um die IT-Verwaltung zu vereinfachen, sodass Administratoren Firmware-Updates mithilfe von Windows Update automatisieren oder Updates mit internen Softwareverteilungstools zentralisieren können.

- Der Surface Enterprise Management-Modus (Semm) ermöglicht IT-Administratoren, Ports auf Surface Dock 2 zu sichern. Weitere Informationen finden Sie unter [Secure Surface Dock 2-Anschlüsse mit Surface Enterprise-Verwaltungsmodus](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999).
-  Die Windows-Verwaltungsinstrumentation (WMI)-Unterstützung ermöglicht IT-Administratoren die Remoteüberwachung und Verwaltung der neuesten Firmware, des Richtlinien Zustands und der zugehörigen Daten auf Surface Dock 2-Geräten. Weitere Informationen finden Sie unter [Verwalten von Surface Dock 2 mit WMI](surface-dock2-wmi.md).

## Allgemeine Systemanforderungen

- Windows 10, Version 1809. Es gibt keine Unterstützung für Windows 7-, Windows 8-oder nicht-Surface-Hostgeräte. Surface Dock 2 funktioniert mit den folgenden Surface-Geräten:

  - Surface pro (fünfte Generation)
  - Surface-Laptop (1st Generation)
  - Surface Pro 6
  - Surface Book 2
  - Surface Laptop 2
  - Surface Go
  - Surface Pro 7
  - Surface Pro X 
  - Surface Laptop 3
  - DGM-Buch 3
  - Surface Go 2

## Surface Dock 2-Komponenten

![Surface Dock 2-Komponenten](./images/surface-dock2.png)
 
### USB

- Zwei frontseitige USB-C-Anschlüsse.
- Zwei Anschlüsse für USB-C (Gen 2) an der Rückseite.
- Zwei nach hinten weisende USB-Anschlüsse. 

### Video
    
- Dual-4K@60Hz. Unterstützt bis zu zwei Displays auf den folgenden Geräten:

  - DGM-Buch 3
  - Surface Go 2
  - Surface Pro 7
  - Surface Pro X
  - Surface Laptop 3

- Dual 4K@ 4K@30Hz. Unterstützt bis zu zwei Displays auf den folgenden Geräten:

  - Surface Pro 6
  - Surface pro (fünfte Generation)
  - Surface Laptop 2
  - Surface-Laptop (1st Generation)
  - Surface Go
  - DGM-Buch 2.

### Ethernet

- 1-Gigabit-Ethernet-Anschluss. 

### Externe Stromversorgung

- 199 Watt unterstützt 100V-240V.


## Vergleich von Surface Dock 2 

### Tabelle1. Surface Dock 2-Technische Datenvergleich

|Komponente|Surface Dock|Surface Dock 2|
|---|---|---|
|Surflink|Ja|Ja|
|USB-A|2 frontseitig USB 3,1 Gen 1<br>2 Heckverkleidung USB 3,1 Gen 1|2 Heckverkleidung USB 3,2 Gen 2 (7.5 w Leistung)|
|Mini-Display-Port|2 Heckverkleidung (DP 1.2)|Keine|
|USB-C|Keine|2 frontseitig USB 3,2 Gen 2<br>(20W Power)<br>2 Heckverkleidung USB 3,2 Gen 2 (DP 1.4 a)<br>(7.5 w Leistung)|
|3,5 mm Audio-Eingang/-Ausgang|Ja|Ja|
|Ethernet|Ja, 1 Gigabit|Ja 1 Gigabit|
|DC-Stromversorgung|Ja|Ja|
|Kensington-Sperre|Ja|Ja|
|Surflink-Kabellänge|65cm|80cm|
|Surflink-Hostleistung|60W|120W|
|USB-Ladeleistung|30W|60W|
|USB-Bitrate|5 Gbit/s|10 Gbit/s|
|Monitor-Unterstützung|2 x 4K-@30fps oder<br>1 x 4K @ 60fps|2 x 4K @ 60fps|
|Wake-on-LAN aus verbundenem Standby <sup> 1</sup>|Ja|Ja|
|Wake-on-LAN von S4/S5 Sleep-Modi|Nein|Ja|
|PXE-Netzwerkstart|Ja|Ja|
|SEMM-Host Zugriffssteuerung|Nein|Ja
|SEMM-Port Zugriffssteuerung <sup> 2</sup>|Nein|Ja|
|Support für Wartung|MSI|Windows Update oder MSI|
||||

1. *Geräte müssen für Wake-on-LAN über Surface Enterprise Management Mode (Semm) oder Device Firmware Control Interface (DFCI) konfiguriert werden, um aus dem Ruhezustand oder aus dem Standbymodus zu reaktivieren. Wake from Hibernate oder Power-Off wird unter Surface pro 7, Surface Laptop 3, Surface pro X, Surface Book 3 und Surface Go 2 unterstützt.  Für einige Funktionen ist eine Software Lizenz erforderlich. Separat erhältlich.*

2. *Für einige Funktionen ist eine Software Lizenz erforderlich. Separat erhältlich.*

## Optimierte Geräteverwaltung

Surface hat mithilfe von Windows Update optimierte Verwaltungsfunktionen freigegeben und ermöglicht IT-Administratoren die Nutzung der folgenden unternehmensweiten Funktionen:

- **Reibungslose Updates**. Aktualisieren Sie Ihre Docks automatisch und automatisch mit Windows Update oder Microsoft Endpoint Configuration Manager (vormals System Center Configuration Manager-SCCM) oder anderen MSI-Bereitstellungstools. 
- **Wake aus dem Netzwerk**. Verwalten und Zugreifen auf unternehmensgeräte, ohne dass die Benutzer ihre Geräte auf dem laufenden halten. Auch wenn sich ein angedocktes Gerät im Standbymodus, Ruhezustand oder Energiesparmodus befindet, kann Ihr Team mithilfe des Endpunkt Konfigurations-Managers oder anderer Enterprise-Verwaltungstools aus dem Netzwerk für Dienst und Verwaltung aufwachen.
- **Zentralisierte IT-Steuerung**. Steuern Sie, wer eine Verbindung mit Surface Dock 2 herstellen kann, indem Sie die Ports ein-und ausschalten. Einschränken, welche Hostgeräte mit Surface Dock 2 verwendet werden können Beschränken Sie den Zugriff auf einen einzelnen Benutzer oder konfigurieren Sie Docks, damit nur bestimmte Benutzer in Ihrem Team oder im gesamten Unternehmen darauf zugreifen können.

## Nächste Schritte

- [Sichere Surface Dock 2-Anschlüsse mit Surface Enterprise-Verwaltungsmodus](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)
- [Surface Enterprise Management-Modus](surface-enterprise-management-mode.md)
- [Bewährte Energieeinstellungen für Surface-Geräte](maintain-optimal-power-settings-on-Surface-devices.md)
