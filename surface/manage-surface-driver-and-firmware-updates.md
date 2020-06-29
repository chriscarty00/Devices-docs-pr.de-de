---
title: Verwalten und Bereitstellen von Treiber- und Firmwareupdates für Surface
description: In diesem Artikel werden die verfügbaren Optionen zum Verwalten und Bereitstellen von Firmware-und Treiberupdates für Surface-Geräte beschrieben.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, Firmware, Update, Gerät, verwalten, bereitstellen, Treiber, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 91cde5fdf4a7745d491bd2eb928baca75955b90d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832830"
---
# Verwalten und Bereitstellen von Treiber- und Firmwareupdates für Surface

Wie Sie Oberflächen Treiber-und Firmware-Updates verwalten, hängt von Ihrer Umgebung und den organisatorischen Anforderungen ab. Auf Surface-Geräten wird die Firmware dem Betriebssystem als Treiber zur Verfügung gestellt und im Geräte-Manager angezeigt, sodass die Geräte-Firmware und Treiber mithilfe von Windows Update oder Windows Update für Unternehmen automatisch aktualisiert werden können. Obwohl dieser vereinfachte Ansatz für Startups und kleine oder mittelständische Unternehmen möglicherweise geeignet ist, benötigen größere Organisationen in der Regel IT-Administratoren, um Updates intern zu verteilen. Dies kann eine umfassende Planung, Anwendungskompatibilitätstests, das Testen und Überprüfen von Updates sowie die endgültige Genehmigung und Verteilung im gesamten Netzwerk beinhalten.

> [!NOTE]
> Dieser Artikel richtet sich an technische Support-Mitarbeiter und IT-Experten und gilt nur für Surface-Geräte. Wenn Sie Hilfe bei der Installation von Surface-Updates oder Firmware auf einem Home-Gerät benötigen, lesen Sie [Aktualisieren der Surface-Firmware und Windows 10](https://support.microsoft.com/help/4023505).

Während Software verteilungslösungen auf Unternehmensniveau weiterentwickelt werden, bleibt die Geschäftslogik für die zentrale Verwaltung von Updates gleich: die Sicherheit von Surface-Geräten wird beibehalten und mit den neuesten Verbesserungen des Betriebssystems und der Features aktualisiert. Dies ist für die Aufrechterhaltung einer stabilen Produktionsumgebung und die Sicherstellung, dass Benutzer nicht produktiv sind, unerlässlich. Dieser Artikel enthält eine Übersicht über empfohlene Tools und Prozesse für größere Organisationen, um diese Ziele zu erreichen.

## Zentrales Update Management in kommerziellen Umgebungen

Microsoft verfügt über optimierte Tools für die Verwaltung von Geräten – einschließlich Treiber-und Firmware-Updates – in einer einzigen vereinheitlichten Benutzeroberfläche mit dem Namen [Microsoft Endpoint Manager Admin Center](https://devicemanagement.microsoft.com/) , auf das von Devicemanagement.Microsoft.com aus zugegriffen wird.

### Verwalten von Updates mit Configuration Manager und InTune

Microsoft Endpoint Configuration Manager ermöglicht das Synchronisieren und Bereitstellen von Surface-Firmware und Treiberupdates mit dem Configuration Manager-Client. Durch die Integration in Microsoft InTune können Sie alle Ihre verwalteten, gemeinsam verwalteten und mit Partnern verwalteten Geräte an einem zentralen Ort anzeigen. Dies ist die empfohlene Lösung für große Organisationen zum Verwalten von Oberflächen Updates.

Detaillierte Anweisungen finden Sie in den folgenden Ressourcen:

- [Verwalten von Oberflächen Treiberupdates in Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Bereitstellen von Anwendungen mit Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Endpunkt-Konfigurations-Manager-Dokumentation](https://docs.microsoft.com/configmgr/)

### Verwalten von Updates mit dem Microsoft Deployment Toolkit

Das Microsoft Deployment Toolkit (MDT) enthält in Endpoint Configuration Manager optionale Bereitstellungstools, die Sie je nach Umgebung verwenden möchten. Dazu gehören das Windows-Bewertungs-und Bereitstellungs-Kit (Windows ADK), Windows-System Abbild-Manager (Windows SIM), Bereitstellungs-Image-Service und-Verwaltung (DISM) und das Benutzerstatus-Migrations Tool (USMT). Sie können die neueste Version von MDT über die [Download Seite des Microsoft Deployment Toolkit](https://www.microsoft.com/download/details.aspx?id=54259)herunterladen.

Detaillierte Anweisungen finden Sie in den folgenden Ressourcen:

- [Microsoft Deployment Toolkit-Dokumentation](https://docs.microsoft.com/configmgr/mdt/)
- [Bereitstellen von Windows10 mit dem Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Bereitstellen von Windows 10 auf Surface-Geräten mit Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Oberflächen Treiber-und Firmware-Updates werden als Windows Installer-Dateien (*. msi) verpackt. Zum Bereitstellen dieser Windows Installer-Pakete können Sie Endpoint Configuration Manager oder MDT verwenden. Informationen zum Auswählen der richtigen MSI-Datei für ein Gerät und Betriebssystem finden Sie in den folgenden Anleitungen zum Herunterladen von MSI-Dateien.

Anweisungen zum Bereitstellen von Updates mithilfe des Endpunkt Konfigurations-Managers finden Sie unter [Bereitstellen von Anwendungen mit Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Anweisungen zum Bereitstellen von Updates mithilfe von MDT finden Sie unter [Bereitstellen eines Windows 10-Bilds mithilfe von MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**WindowsPE und Surface-Firmware und-Treiber**

Endpunkt Konfigurations-Manager und MDT verwenden sowohl die Windows-Vorinstallationsumgebung (windowsPE) während des Bereitstellungsprozesses. WindowsPE unterstützt nur eine begrenzte Anzahl grundlegender Treiber, beispielsweise für Netzwerkadapter und Speichercontroller. Treiber für Windows-Komponenten, die nicht Teil von windowsPE sind, können Fehler verursachen. Als bewährte Methode können Sie solche Fehler verhindern, indem Sie den Bereitstellungsprozess so konfigurieren, dass nur die erforderlichen Treiber während der windowsPE-Phase verwendet werden.

### Endpoint Configuration Manager

Ab Endpunkt-Konfigurations-Manager können Sie Microsoft Surface-Firmware und-Treiberupdates mit dem Configuration Manager-Client synchronisieren und bereitstellen. Weitere Informationen finden Sie unter KB 4098906, [so wird es gemacht: Verwalten von Oberflächen Treiberupdates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## Unterstützte Geräte

Herunterladbare MSI-Dateien stehen für Surface-Geräte von Surface pro 2 und höher zur Verfügung. Informationen zu MSI-Dateien für die neuesten Surface-Geräte wie Surface pro 7, Surface pro X und Surface Laptop 3 sind nach der Veröffentlichung auf dieser Seite verfügbar.

## Verwalten von Firmware mit DFCI

Mit DFCI-Profilen (Device Firmware Configuration Interface), die in InTune integriert sind (jetzt in [Public Preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)verfügbar), erweitert die Oberfläche-UEFI-Verwaltung den modernen Verwaltungs Stapel auf die UEFI-Hardwareebene. DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Kontrolle über Sicherheitseinstellungen, einschließlich Startoptionen und integrierte Peripheriegeräte, und legt die Grundlagen für fortschrittliche Sicherheitsszenarien in der Zukunft fest. Weitere Informationen finden Sie unter:

- [Intune-Verwaltung von Surface UEFI-Einstellungen](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Ankündigung der Remoteverwaltung von Oberflächen UEFI-Einstellungen aus InTune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## Bewährte Methoden für Update Bereitstellungsprozesse

Um eine stabile Umgebung beizubehalten, wird dringend empfohlen, die Parität mit der neuesten Version von Windows 10 beizubehalten.  Empfehlungen für bewährte Methoden finden Sie unter [Erstellen von Bereitstellungs Ringen für Updates für Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).

## Herunterladbare Oberflächen Aktualisierungspakete

Bestimmte Versionen von Windows 10 verfügen über separate MSI-Dateien, die jeweils alle erforderlichen kumulativen Treiber-und Firmware-Updates für Surface-Geräte enthalten. Update Pakete können einige oder alle der folgenden Komponenten umfassen:

- Wi-Fi und LTE
- Video
- Solid-State-Laufwerk
- System-Aggregator-Modul (Sam)
- Akku
- Tastaturcontroller
- Embedded-Controller (EC)
- Verwaltungsmodul (Me)
- Unified Extensible Firmware Interface (UEFI)

### Herunterladen von MSI-Dateien

1. Navigieren Sie zum [Herunterladen von Treibern und Firmware für Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) im Microsoft Download Center.
2. Wählen Sie den MSI-Dateinamen aus, der dem Surface-Modell und der Windows-Version entspricht. Der Name der MSI-Datei enthält die minimale unterstützte Windows-Buildnummer, die erforderlich ist, um die Treiber und die Firmware zu installieren. So können Sie beispielsweise, wie in der folgenden Abbildung gezeigt, zum Aktualisieren eines DGM-Buches 2 mit Build 18362 von Windows 10 **SurfaceBook2_Win10_18362_19.101.13994.msi auswählen.** Wählen Sie für ein DGM-Buch 2 mit Build 16299 von Windows 10 **SurfaceBook2_Win10_16299_1803509_3.msi**aus.

    ![Abbildung1. Herunterladen von DGM-Updates](images/fig1-downloads-msi.png)

    *Abbildung1. Herunterladen von DGM-Updates*

### Surface. msi-Benennungskonvention

Seit August 2019 verwenden MSI-Dateien die folgende Benennungskonvention:

- *Product*_*Windows Release*_*Windows Build number*_*Versionsnummer*_*Revision der Versionsnummer (in der Regel 0)*.

**Beispiel**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Dieser Dateiname enthält die folgenden Informationen:

- **Produkt:** SurfacePro6
- **Windows-Version:** Win10
- **Build:** 18362
- **Version:** 19.073.44195 – zeigt das Datum und die Uhrzeit der Erstellung der Datei wie folgt an:
  - **Jahr:** 19 (2019)
  - **Monat und Woche:** 073 (dritte Juli-Woche)
  - **Minute des Monats:** 44195
- **Revision der Version:** 0 (erste Version dieser Version)

### Legacy Surface. msi-Benennungskonvention

Legacy-MSI-Dateien (Dateien, die vor August 2019 erstellt wurden) folgten der gleichen allgemeinen Benennungs Formel, verwendeten jedoch eine andere Methode, um die Versionsnummer abzuleiten.

**Beispiel**

- SurfacePro6_Win10_16299_1900307_0.msi

Dieser Dateiname enthält die folgenden Informationen:

- **Produkt:** SurfacePro6
- **Windows-Version:** Win10
- **Build:** 16299
- **Version:** 1900307 – Dies zeigt das Datum, an dem die Datei erstellt wurde, und ihre Position in der Veröffentlichungs Sequenz wie folgt:
  - **Jahr:** 19 (2019)
  - **Anzahl der Veröffentlichung:** 003 (dritte Version des Jahres)
  - **Produktversionsnummer:** 07 (Surface pro 6 ist offiziell die siebte Version von Surface pro)
- **Revision der Version:** 0 (erste Version dieser Version)

## Mehr erfahren

- [Herunterladen von Treibern und Firmware für Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Verwalten von Oberflächen Treiberupdates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Bereitstellen von Anwendungen mit Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Endpunkt-Konfigurations-Manager-Dokumentation](https://docs.microsoft.com/configmgr/)
- [Microsoft Deployment Toolkit-Dokumentation](https://docs.microsoft.com/configmgr/mdt/)
- [Bereitstellen von Windows10 mit dem Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Bereitstellen von Windows 10 auf Surface-Geräten mit Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Intune-Verwaltung von Surface UEFI-Einstellungen](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Ankündigung der Remoteverwaltung von Oberflächen UEFI-Einstellungen aus InTune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Erstellen von Bereitstellungsringen für Windows10-Updates](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
