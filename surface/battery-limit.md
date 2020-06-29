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
# Einstellungen für Akkulimit

Die Option "Akku Grenze" ist eine UEFI-Einstellung, die das Aufladen des Surface-Geräte Akkus ändert und seine Langlebigkeit verlängern kann. Diese Einstellung wird in den Fällen empfohlen, in denen das Gerät kontinuierlich an die Stromversorgung angeschlossen ist, beispielsweise wenn Geräte in Kiosk Lösungen integriert sind.  

## Funktionsweise des Batterie Limits

Wenn Sie das Gerät auf Batterie Grenzwert setzen, ändert sich das Protokoll zum Aufladen des Geräte Akkus. Wenn die Batterie Grenze aktiviert ist, wird die Akkuladung auf 50% der maximalen Kapazität begrenzt. Die in Windows gemeldete Belastungsstufe spiegelt diesen Grenzwert wider. Daher wird angezeigt, dass der Akku bis zu 50% aufgeladen wird und nicht über diesen Grenzwert hinaus belastet wird. Wenn Sie die Batterie Grenze aktivieren, während das Gerät über 50% aufgeladen ist, zeigt das Batteriesymbol an, dass das Gerät angeschlossen ist, aber entladen wird, bis das Gerät 50% seiner maximalen Ladekapazität erreicht.  

## Unterstützte Geräte
Die UEFI-Einstellung für das Batterie Limit ist in die neuesten Surface-Geräte einschließlich Surface pro 7 und Surface Laptop 3 integriert. Für ältere Geräte ist eine [Oberflächen UEFI-Firmware-Aktualisierung](manage-surface-driver-and-firmware-updates.md)erforderlich, die über Windows Update oder über die MSI-Treiber-und Firmware-Pakete auf der [Surface Support-Website](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)zur Verfügung steht. Aktivieren Sie das Kontrollkästchen ["Batterie Grenzwert" für Surface-Geräte, die für längere Zeit](https://support.microsoft.com/help/4464941) für die spezifische Oberflächen UEFI-Version, die für jedes unterstützte Gerät erforderlich ist, angeschlossen werden müssen. 

## Aktivieren des Batterie Grenzwerts in der Oberfläche UEFI (Surface pro 4 und höher)

Die Einstellung für die Oberfläche des UEFI-Batterie Limits kann durch Starten in die Oberfläche UEFI (**Power + Vol up** beim Einschalten des Geräts) konfiguriert werden. Wählen Sie **Startkonfiguration**aus, und aktivieren Sie dann unter **Erweiterte Optionen**den **Modus Batterie-limitmodus** **auf ein**.  

![Screenshot der erweiterten Optionen](images/enable-bl.png) 

## Aktivieren des Batterie Limits für Surface Go und Surface Go 2
Die Einstellung für die Oberflächen-Batterie Grenze kann durch Starten in die Oberfläche UEFI (**Power + Vol up** beim Einschalten des Geräts) konfiguriert werden. Wählen Sie **Startkonfiguration**aus, und verschieben Sie dann unter **Kiosk Modus**den Schieberegler nach rechts, um den Batterie Grenzwert auf **aktiviert**festzulegen.  

![Screenshot der Batterie Grenze des Kiosk Modus in Surface go](images/go-batterylimit.png) 

## Aktivieren des Batterie Grenzwerts in der Oberfläche UEFI (Surface pro 3)

Die Einstellung für die Oberfläche des UEFI-Batterie Limits kann durch Starten in die Oberfläche UEFI (**Power + Vol up** beim Einschalten des Geräts) konfiguriert werden. Wählen Sie **Kiosk Modus**, dann **Batterie Grenzwert**und dann **aktiviert**aus.

![Screenshot der erweiterten Optionen](images/enable-bl-sp3.png) 

![Screenshot der erweiterten Optionen](images/enable-bl-sp3-2.png) 

## Aktivieren des Batterie Limits mit dem Surface Enterprise Management Mode (Semm) oder Surface pro 3-Firmware PowerShell-Skripts

Die Oberfläche des UEFI-Batterie Limits ist auch für die Konfiguration über die folgenden Methoden verfügbar:

- Surface pro 4 und höher 
    - [Microsoft Surface UEFI-Konfigurator](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Oberflächen-UEFI-Manager-PowerShell-Skripts (SEMM_Powershell.zip) in den [Surface Tools für IT-Downloads](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Verwenden des Microsoft Surface UEFI-Konfigurators

Zum Konfigurieren des Batterie Limit-Modus legen Sie die Einstellung **Kiosk Außerkraftsetzungen** auf der Seite **Erweiterte Einstellungen** für Konfiguration in Semm (Surface pro 4 und höher) fest.

![Screenshot der erweiterten Einstellungen](images/semm-bl.png)

### Verwenden von PowerShell-Skripten für Surface UEFI Manager

Die Funktion für das Batterie Limit wird über die folgende Einstellung gesteuert:  

`407 = Battery Profile`

**Beschreibung**: aktives Verwaltungsschema für Batterie Nutzungsmuster

**Standard**:  `0` 

Wählen Sie diese `1` Option aus, um die Batterie zu begrenzen.

### Verwenden von Surface pro 3-Firmware-Tools

Die Funktion für das Batterie Limit wird über die folgende Einstellung gesteuert:  

**Name**: BatteryLimitEnable

**Beschreibung**: BatteryLimit

**Aktueller Wert**:  `0` 

**Standardwert**: `0`

**Vorgeschlagener Wert**: `0` 

Wählen Sie diese `1` Option aus, um die Batterie zu begrenzen.

>[!NOTE]
>Um diese Einstellung zu konfigurieren, müssen Sie [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)verwenden. 

