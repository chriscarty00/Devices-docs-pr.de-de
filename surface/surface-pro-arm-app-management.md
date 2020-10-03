---
title: Bereitstellen, Verwalten und Warten von Surface Pro X
description: Dieser Artikel enthält eine Übersicht über wichtige Überlegungen zur Bereitstellung, Verwaltung und Wartung des Surface Pro X.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/01/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 758cde12ea79e42630dad55b06eb50d0ab9dda12
ms.sourcegitcommit: f996a95af741e54536b1f3eb94d0f13f681f5d5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093128"
---
# Bereitstellen, Verwalten und Warten von Surface Pro X

## Einführung

Surface Pro X ist für hohe kommerzielle Leistungsanforderungen konzipiert und beschreitet neue Wege durch den integrierten leistungsstärksten Prozessor, der je auf einem ARM-Gerät ausgeliefert wurde, dem ARM-basierten SQ1-Chipsatz von Microsoft.

Mit einer CPU mit 3GHz und einer GPU mit 2,1 Teraflops bietet Surface Pro X eine vollständige Windows-Umgebung. Dank der Akkulaufzeit von 13 Stunden und des integrierten 4G LTE ist er ideal geeignet für mobile Mitarbeiter und Profis in den Bereichen Finanzen, Recht und Medizin oder in allen Bereichen, in denen eine längere Akkulaufzeit und kontinuierliche Konnektivität erforderlich sind.

Surface Pro X ist fast ausschließlich für eine moderne, cloudbasierte Umgebung rund um Microsoft 365, Intune und Windows Autopilot konzipiert. Dieser Artikel beschreibt, wie das im Einzelnen aussieht, und führt die wichtigsten Überlegungen zur Bereitstellung, Verwaltung und Wartung des Surface Pro X aus.

## Bereitstellen von Surface Pro X

Um eine optimale Leistung zu erzielen, stellen Sie Surface Pro X mithilfe von Windows Autopilot und entweder mit Unterstützung eines Microsoft Cloud Solution Providers oder eigenständig bereit, indem Sie Autopilot-Bereitstellungsprofile und verwandte Funktionen verwenden. Weitere Informationen finden Sie unter:

- [Windows Autopilot und Surface-Geräte](windows-autopilot-and-surface-devices.md)
- [Übersicht über Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

Die Autopilot-Bereitstellung bietet mehrere Vorteile: Sie ermöglicht Ihnen die Verwendung des werkseitig bereitgestellten Betriebssystems, das für die Zero Touch-Bereitstellung optimiert ist, um die Vorinstallation von Office Pro Plus einzuschließen.

Organisationen, die bereits moderne Management-, Sicherheits- und Produktivitätslösungen einsetzen, sind gut positioniert, um von den einzigartigen Leistungsmerkmalen von Surface Pro X zu profitieren. Auch Kunden, die branchenspezifische Apps, Microsoft Store-Apps (UWP) oder Remotedesktop-Lösungen einsetzen, profitieren davon.

## Überlegungen zur imagebasierten Bereitstellung

Microsoft Deployment Toolkit (MDT)) und Microsoft Endpoint Configuration Manager (ehemals System Center Configuration Manager) unterstützen Surface Pro X derzeit nicht für die Bereitstellung von Betriebssystemen. Kunden, die auf eine imagebasierte Bereitstellung vertrauen, sollten Surface Pro 7 in Betracht ziehen, während sie den richtigen Zeitpunkt für den Wechsel zur Cloud abschätzen.

## Verwalten von Surface Pro X-Geräten

### Intune

Intune ist eine Komponente von Microsoft Enterprise Mobility + Security, die für die Identitäts- und Zugriffssteuerung in Azure Active Directory integriert ist und eine präzise Verwaltung von registrierten Surface Pro X-Geräten ermöglicht. Intune-Richtlinien für die Mobile Geräteverwaltung (Mobile Device Management, MDM) bieten gegenüber älteren lokalen Tools wie der Windows-Gruppenrichtlinie eine Reihe von Vorteilen. Dazu gehören schnellere Geräteanmeldezeiten und ein optimierter Richtlinienkatalog, der eine vollständige Geräteverwaltung über die Cloud ermöglicht. Sie können beispielsweise LTE mithilfe von eSIM-Profilen verwalten, um Datentarife zu konfigurieren und Aktivierungscodes auf mehreren Geräten bereitzustellen.<br> 

Weitere Informationen zur Verwendung von Intune erhalten Sie in der [Intune-Dokumentation](https://docs.microsoft.com/intune/).

### Gemeinsame Verwaltung

Nach der Bereitstellung in Autopilot können Sie Surface Pro X-Geräte mit Azure AD oder Active Directory (Azure AD Hybrid Join) verknüpfen, wo Sie die Geräte mit Intune oder gemeinsam mit Endpoint Configuration Manager verwalten können, wodurch der ConfigMgr-Client (32-Bit x86) installiert wird.

### MDM-Lösungen von Drittanbietern

Sie können Surface Pro X-Geräte möglicherweise mit MDM-Tools von Drittanbietern verwalten. Weitere Informationen erhalten Sie von Ihrem MDM-Anbieter.

### Antivirensoftware

Windows Defender trägt während der unterstützten Lebensdauer Ihres Windows 10-Geräts zum Schutz von Windows 10 auf ARM-basierten PCs bei. 

Die Antivirensoftware eines Drittanbieters kann nicht auf einem Windows10-PC installiert werden, auf dem ein ARM-basierter Prozessor ausgeführt wird. Die Zusammenarbeit mit Drittanbietern von Antivirensoftware wird fortgesetzt, um die AV-App-Vorbereitung auf ARM-basierten PCs zu gewährleisten. Wenden Sie sich den Anbieter der Antivirensoftware, um weitere Informationen zur Verfügbarkeit ihrer Apps zu erhalten.

## Warten von Surface Pro X

Surface Pro X unterstützt Windows10 ab Version 1903. Als ARM-basiertes Gerät stellt es bestimmte Anforderungen an die Aktualität der Treiber und Firmware. 

Surface Pro X ist auf Windows Update ausgelegt, um das Aktualisieren von Treibern und Firmware für Privatbenutzer und Benutzer in Kleinunternehmen zu vereinfachen. Verwenden Sie die Standardeinstellungen, um automatische Updates zu erhalten.  Führen Sie zur Überprüfung die folgenden Schritte aus:

1. Navigieren Sie zu **Start** > **Einstellungen > Update und Sicherheit > Windows Update** > **Erweiterte Optionen**.
2. Wählen Sie unter **Auswählen der Installationsmethode für Updates** die Option **Automatisch (empfohlen)** aus.

### Empfehlungen für Geschäftskunden

- Verwenden Sie Windows Update oder Windows Update for Business zum Aktualisieren auf die neueste(n) Treiber und Firmware. Weitere Informationen finden Sie unter [Bereitstellen von Updates mit Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).
- Wenn für die Verfahren eine Windows Installer-Datei (.msi) erforderlich ist, wenden Sie sich an den [Support für Surface für Unternehmen](https://support.microsoft.com/help/4037645). 
- Weitere Informationen zum Bereitstellen und Verwalten von Updates auf Surface-Geräten finden Sie unter [Verwalten und Bereitstellen der neuesten Firmware und Treiber für Surface](manage-surface-driver-and-firmware-updates.md).
- Beachten Sie, dass Windows Server Update Services (WSUS) die Bereitstellung von Treibern und Firmware für Surface Pro X nicht unterstützt.

## Ausführen von Apps auf Surface Pro X

Bis auf einige Ausnahmen, werden die meisten Apps auf ARM-basierten Windows10-PCs ausgeführt.

### Unterstützte Apps

- Die meisten x86 Win32-Apps werden auf Surface Pro X ausgeführt.
- Native ARM64- und UWP-Apps für den Microsoft Store bieten eine hervorragende Benutzerfreundlichkeit durch die Nutzung der vollständig nativen Geschwindigkeit des ARM-basierten Prozessors, und dies bei gleichzeitiger Optimierung der Akkulaufzeit.
- Apps, die Treiber verwenden, die für einen Windows10-PC mit einem ARM-basierten Prozessor ausgelegt sind.

> [!NOTE]
> Mit der 64-Bit-Emulation, die demnächst in der Vorschau über das Windows-Insider-Programm eingeführt wird, können Sie 64-Bit (x64) Apps auf Surface Pro X ausführen.

Weitere Informationen zum Ausführen von Apps auf Surface Pro X finden Sie unter:

- [Häufig gestellte Fragen zu Windows10 ARM-basierten PCs](https://support.microsoft.com/help/4521606)
- [Dokumentation zu Windows10 auf ARM](https://docs.microsoft.com/windows/arm)

## Virtuelle Desktops (VDI)

Windows Virtual Desktop ermöglicht den Zugriff auf Windows-Desktopcomputer, -Anwendungen und -Daten auf allen Computergeräten oder -plattformen von jedem Standort aus. Weitere Informationen finden Sie auf der [Windows Virtual Desktop-Website](https://aka.ms/wvd). 

## Surfen mit Surface Pro X

Gängige auf Surface Pro X ausgeführte Browser:

- Integrierte Browser wie Edge, Firefox, Chrome und Internet Explorer werden auf Surface Pro X ausgeführt.
- Die integrierten Browser Edge und Firefox sind direkt ausführbar und bieten somit eine höhere Leistung auf einem Windows10-PC mit ARM-basiertem Prozessor.

## Installieren und Verwenden von Microsoft Office

- Verwenden Sie Office365 auf einem Windows10-PC mit ARM-basiertem Prozessor, um optimale Ergebnisse zu erzielen.
- Office 365 "Klick-und-Los" installiert Outlook, Word, Excel und PowerPoint, optimiert für die Ausführung auf einem Windows 10-PC auf einem ARM-basierten Prozessor.
- Microsoft Teams wird problemlos auf Surface Pro X ausgeführt.
- Installieren Sie für "unbefristete Versionen" von Office wie Office 2019 die 32-Bit-Version.

## VPN

Um zu ermitteln, ob ein bestimmtes VPN eines Drittanbieters einen Windows10 PC auf einem ARM-basierten Prozessor unterstützt, wenden Sie sich an den VPN-Anbieter.

## Vergleich der wichtigsten Features

Die folgenden Tabellen zeigen die Verfügbarkeit ausgewählter wichtiger Features auf Surface Pro X mit Windows10 auf ARM im Vergleich zum Intel-basierten Surface Pro 7.

| Bereitstellung                              | Surface Pro 7 | Surface Pro X | Anmerkungen                                                                                                                           |
| --------------------------------------- | ------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                       | Ja           | Ja           |                                                                                                                                 |
| Unterstützung für Netzwerkstart (PXE)          | Ja           | Nein           |                                                                                                                                 |
| Windows Configuration Designer          | Ja           | Nein            | Wird nicht für Surface Pro X empfohlen                                                                                              |
| WinPE                                   | Ja           | Ja           | Wird nicht für Surface Pro X empfohlen. Microsoft stellt nicht die erforderliche(n) ISO-Datei und Treiber zur Unterstützung von WinPE mit Surface Pro X bereit. |
| Endpoint Configuration Manager: Betriebssystembereitstellung | Ja           | Nein            | Wird auf Surface Pro X nicht unterstützt                                                                                              |
| MDT                                     | Ja           | Nein            | Wird auf Surface Pro X nicht unterstützt                                                                                              |


| Verwaltung                                    | Surface Pro 7       | Surface Pro X | Anmerkungen                                                                                 |
| --------------------------------------------- | ------------------- | ------------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Ja                 | Ja           | Verwaltung von LTE mit eSIM-Profilen                                                        |
| Windows Autopilot                             | Ja                 | Ja           |                                                                                       |
| Azure AD (gemeinsame Verwaltung)                      | Ja                 | Ja           | Ermöglicht die Verknüpfung von Surface Pro X mit Azure AD oder Active Directory (Azure AD Hybrid Join) |
| Endpoint Configuration Manager                                          | Ja               | Ja           |                                                                                       |
| Einschalten bei Wiederherstellung im Netzbetrieb                      | Ja                 | Ja           |                                                                                   |
| Surface-Diagnosetoolkit für Unternehmen | Ja                 | Ja           |                                                                                   |
| Surface Dock Firmware-Update                  | Ja                 | Nein           |                                                                                   |
| Asset Tag-Hilfsprogramm                             | Ja                 | Ja           |                                                                                   |
| Surface Enterprise Management Mode (SEMM)     | Ja | Teilweise       | Hardware auf Surface Pro X kann auf Firmwareebene nicht deaktiviert werden                 |
| Surface UEFI-Konfigurator                     | Ja |   Nein            | Hardware auf Surface Pro X kann auf Firmwareebene nicht deaktiviert werden                |
| Surface UEFI-Manager                          | Ja | Teilweise       | Hardware auf Surface Pro X kann auf Firmwareebene nicht deaktiviert werden                 |


| Sicherheit                          | Surface Pro 7 | Surface Pro X | Anmerkungen                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------- | ------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BitLocker                         | Ja           | Ja           |                                                                                                                                                                                                                                                                                                                                                      |
| WindowsDefender                  | Ja           | Ja           |                                                                                                                                                                                                                                                                                                                                                      |
| Unterstützung für Antivirensoftware von Drittanbietern | Ja           | Siehe Hinweis      |Die Antivirensoftware eines Drittanbieters kann nicht auf einem Windows10-PC installiert werden, auf dem ein ARM-basierter Prozessor ausgeführt wird. Die Zusammenarbeit mit Drittanbietern von Antivirensoftware wird fortgesetzt, um die AV-App-Vorbereitung auf ARM-basierten PCs zu gewährleisten. Wenden Sie sich den Anbieter der Antivirensoftware, um weitere Informationen zur Verfügbarkeit ihrer Apps zu erhalten. |
| Bedingter Zugriff                | Ja           | Ja           |                                                                                                                                                                                                                                                                                                                                                      |
| Sicherer Start                       | Ja           | Ja           |                                                                                                                                                                                                                                                                                                                                                      |
| Windows Information Protection    | Ja           | Ja           |                                                                                                                                                                                                                                                                                                                                                      |
| Surface Data Eraser (SDE)         | Ja           | Ja           |                                                                                                                                                                                                                                                                                                                                                     
## Häufig gestellte Fragen

### Kann ich Surface Pro X mit MDT oder Endpoint Configuration Manager bereitstellen?

Das Microsoft Deployment Toolkit (MDT) und Microsoft Endpoint Configuration Manager unterstützen Surface Pro X derzeit nicht für die Bereitstellung von Betriebssystemen. Kunden, die auf eine imagebasierte Bereitstellung vertrauen, sollten Surface Pro 7 in Betracht ziehen, während sie den richtigen Zeitpunkt für den Wechsel zur Cloud abschätzen.

### Wie kann ich Surface Pro X bereitstellen?

Stellen Sie Surface Pro X mithilfe von Windows Autopilot bereit.

### Ist eine BMR verfügbar?

Ja.

### Ist Intune erforderlich, um Surface Pro X zu verwalten?

Intune wird empfohlen, ist aber nicht erforderlich. Nach der Bereitstellung in Autopilot können Sie Surface Pro X-Geräte mit Azure AD oder Active Directory (Azure AD Hybrid Join) verknüpfen, wo Sie die Geräte mit Intune oder gemeinsam mit Endpoint Configuration Manager verwalten können, wodurch der ConfigMgr-Client (32-Bit x86) installiert wird.
