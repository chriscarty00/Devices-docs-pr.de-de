---
title: Bewährte Methoden für die Energieeinstellungen für Surface-Geräte
description: In diesem Thema finden Sie Empfehlungen für bewährte Methoden zum Verwalten optimaler Energieeinstellungen und erläutern, wie die Oberfläche die Energieverwaltungsfunktionalität optimiert. Dieser Artikel bezieht sich auf alle derzeit unterstützten Surface-Geräte wie Surface pro 7, Surface pro X und Surface Laptop 3.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832512"
---
# Bewährte Methoden für die Energieeinstellungen für Surface-Geräte

Surface-Geräte sind so konzipiert, dass Sie die neuesten Fortschritte beim Energieverbrauch von mobilen Geräten nutzen, um eine optimierte, Arbeits übergreifende Arbeitsauslastung zu gewährleisten. Je nachdem, was Sie gerade tun, wird in Surface dynamisch optimiert, wie die Leistung auf einzelne Hardwarekomponenten übertragen wird, indem Sie im Moment Systemkomponenten zur Behandlung von Hintergrundaufgaben-wie etwa einer eingehenden e-Mail oder einem Netzwerkdatenverkehr--durchlaufen, bevor Sie zu einem schwachen Leerlaufzustand (S0ix) zurückkehren.

## Zusammenfassung der Empfehlungen für IT-Administratoren

Um sicherzustellen, dass Surface-Geräte in ihrer gesamten Organisation von den Funktionen zur Oberflächenenergie Optimierung voll profitieren:

-  Installieren Sie die neuesten Treiber und Firmware von Windows Update oder den Surface Driver und die MSI-Firmware. Dadurch wird standardmäßig der symmetrische Energiesparplan (aka Power Profile) erstellt und die optimalen Energieeinstellungen konfiguriert.  Weitere Informationen finden Sie unter [Verwalten und Bereitstellen von Oberflächen Treiber-und Firmware-Updates](manage-surface-driver-and-firmware-updates.md).
- Vermeiden Sie das Erstellen benutzerdefinierter Energieprofile oder das Anpassen erweiterter Energieeinstellungen, die nicht in der Standardbenutzeroberfläche angezeigt werden (**System**  >  **Power & Sleep**).
- Wenn Sie das Power Profile von Geräten im gesamten Netzwerk verwalten müssen (beispielsweise in stark verwalteten Organisationen), verwenden Sie das powercfg-Befehls Tool, um den Energiesparplan aus dem Factory-Abbild des Surface-Geräts zu exportieren und dann in das Bereitstellungspaket für Ihre Surface-Geräte zu importieren. 

    >[!NOTE]
    >Sie können einen Energiesparplan nur über die gleiche Art von Oberflächengerät exportieren.  So können Sie beispielsweise einen Energiesparplan nicht von Surface Laptop exportieren und auf Surface pro importieren.  Weitere Informationen finden Sie unter [Konfigurieren von Energieeinstellungen](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).

- Schließen Sie Oberflächen Geräte aus allen vorhandenen Energieverwaltungsrichtlinien Einstellungen aus. 

## Hintergrund

Die Art und Weise, wie die Oberfläche die Energieverwaltung implementiert, unterscheidet sich erheblich vom früheren Betriebssystemstandard, der die Leistung durch eine Reihe von Sleep-Zuständen allmählich verringert und deaktiviert. Beispiel: Radfahren durch S1, S2, S3 usw.

Stattdessen wird Surface mit einem benutzerdefinierten Power profile-Feature abbildet, das die Legacy-Ruhezustands-und Energieverbrauchs Funktionen durch moderne standbyfunktionen und dynamische Feinabstimmung ersetzt. Dieses benutzerdefinierte Energieprofil wird über den Surface Serial-Hub-Treiber und das System-Aggregator-Modul (Sam) implementiert. Der Sam-Chip fungiert als Energierichtlinienbesitzer des Surface-Geräts und verwendet Algorithmen zur Berechnung des optimalen Energiebedarfs. Es funktioniert in Verbindung mit Windows Power Manager, um nur die für Hardwarekomponenten benötigte Energiemenge zuzuweisen oder zu drosseln. Dieser Artikel bezieht sich auf alle derzeit unterstützten Surface-Geräte wie Surface pro 7, Surface pro X und Surface Laptop 3.

## Verwenden des benutzerdefinierten Energieprofils in Surface

Wenn Sie die Power-Optionen auf einem Surface-Gerät aufrufen, sehen Sie, dass ein einzelner Energiesparplan verfügbar ist. Dies ist das benutzerdefinierte Energieprofil. Und wenn Sie zu den erweiterten Energieeinstellungen wechseln, sehen Sie eine weitaus kleinere Teilmenge der Energieoptionen im Vergleich zu einem generischen PC mit Windows 10. Im Gegensatz zu generischen Geräten verfügt Surface über Firmware und benutzerdefinierte Komponenten, um diese Energieoptionen zu verwalten.


## Moderner Standbymodus

Das algorithmisch eingebettete benutzerdefinierte Power Profile ermöglicht moderne Standby-Konnektivität für Surface, indem ein Energiesparmodus für Instant-On/Instant-off-Funktionen, die für Smartphones typisch sind, beibehalten wird. S0ix, auch als tiefste Runtime Idle-Platt Form Status (Drips) bezeichnet, ist der standardmäßige Power Mode für Surface-Geräte. Moderner Standbymodus hat zwei Modi:

- **Verbundener Standbymodus.** Der Standardmodus für die aktuelle Zustellung von e-Mails, Nachrichten und Cloud-synchronisierten Daten, verbundener Standby-Modus sorgt für WLAN und verwaltet die Netzwerkverbindung.

- **Nicht verbundener Standbymodus.** Ein optionaler Modus für längere Akkulaufzeit, nicht verbundener Standby-Modus sorgt für die gleiche spontane Nutzung und spart Strom, indem WLAN, Bluetooth und verwandte Netzwerkverbindungen ausgeschaltet werden.

Weitere Informationen zum modernen Standby-Modus finden Sie im [Microsoft Hardware dev Center](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).

## Optimierte Oberfläche für die Energieverwaltung 

Surface integriert die folgenden Features, die Benutzern dabei helfen sollen, die Energieverwaltungsfunktionalität zu optimieren:

- [Einzelner Energiesparplan](#singular-power-plan)

- [Vereinfachte Benutzeroberfläche für Energieeinstellungen](#simplified-power-settings-user-interface)

- [Windows-Leistungsstärke Regler](#windows-performance-power-slider)

### Einzelner Energiesparplan

Surface wurde für eine optimierte Energie Verwaltungsumgebung entwickelt, die das Erstellen benutzerdefinierter Energiesparpläne oder das manuelle Konfigurieren von Energieeinstellungen entfällt. Microsoft optimiert die Benutzeroberfläche durch die Bereitstellungeines einzelnen Energiesparplans (Balanced), der die verschiedenen Energiesparpläne von standardmäßigen Windows-Builds ersetzt.

### Vereinfachte Benutzeroberfläche für Energieeinstellungen

Surface bietet eine vereinfachte Benutzeroberfläche in Übereinstimmung mit den Empfehlungen zur Energieeinstellung für bewährte Methoden. Im Allgemeinen empfiehlt es sich, nur die in der Standardbenutzeroberfläche sichtbaren Einstellungen anzupassen und die Konfiguration erweiterter Energieeinstellungen oder Gruppenrichtlinieneinstellungen zu vermeiden. Die Verwendung des standardmäßigen Bildschirms und der Sleep-Timeouts, wobei maximale Helligkeitswerte vermieden werden, sind die effektivste Möglichkeit für Benutzer, eine längere Akkulaufzeit beizubehalten.

![Abbildung1. Vereinfachte Energie & Ruhezustandseinstellungen](images/powerintrofig1.png)

Abbildung1. Vereinfachte Energie-und Ruhezustandseinstellungen

### Windows-Leistungsstärke Regler

Surface-Geräte mit Windows 10 Build 1709 und höher verfügen über einen Power-Schieberegler, der es Ihnen ermöglicht, die Akkulaufzeit bei Bedarf zu priorisieren oder die Leistung bei Bedarf zu bevorzugen. Sie können über die Taskleiste auf den Power Slider zugreifen, indem Sie auf das Batteriesymbol klicken. Ziehen Sie nach links, um die Akkulaufzeit zu verlängern (Batteriesparmodus) oder nach rechts, um die Leistung zu beschleunigen.

![Abbildung2. Power-Schieberegler](images/powerintrofig2a.png)

Abbildung2. Power-Schieberegler

Der Power-Schieberegler aktiviert vier Zustände, wie in der folgenden Tabelle beschrieben:

| Slider-Modus| Beschreibung |
|---|---|
| Stromsparmodus| Hilft, Strom zu sparen und die Akkulaufzeit zu verlängern, wenn das System von einer Stromquelle getrennt wird. Wenn der Stromsparmodus aktiviert ist, sind einige Windows-Features deaktiviert, gedrosselt oder Verhalten sich anders. Die Bildschirmhelligkeit wird ebenfalls reduziert. Der Stromsparmodus steht nur zur Verfügung, wenn der Akku (DC) verwendet wird. Weitere Informationen finden Sie unter [Stromsparmodus](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).|
| Empfohlen | Bietet eine längere Akkulaufzeit als die Standardeinstellungen in früheren Versionen von Windows. |
| Bessere Leistung | Etwas begünstigt die Leistung über die Akkulaufzeit und funktioniert als standardmäßiger Schieberegler. |
| Beste Leistung | Begünstigt die Leistung gegenüber Power für Arbeitslasten, die maximale Leistung und Reaktionsfähigkeit erfordern, unabhängig von der Stromaufnahme des Akkus.|

Der Power Slider-Modus steuert direkt bestimmte Hardwarekomponenten, die in der folgenden Tabelle aufgeführt sind.

| Komponente | Slider-Funktionalität |
|---|---|
| Intel-Drehzahl Schicht (CPU-Energie Register) und Präferenz Hinweis für Energieleistung. | Wählt die beste Betriebsfrequenz und-Spannung für optimale Leistung und Leistung aus. Die Energy Performance-Einstellung (PERFEPP) ist ein globaler Energieeffizienz Hinweis für die CPU. |
| Lüftergeschwindigkeit (RPM)| Passt sich gegebenenfalls den geänderten Bedingungen an, wie etwa das stumm halten des Lüfters im Batteriesparmodus.|
| Leistungsgrenzwerte für Prozessor Pakete (PL1/pl2).| Erfordert, dass die CPU ihre Häufigkeits Auswahl verwaltet, um einen durchschnittlichen Leistungsgrenzwert für PL1-und Turbo (pl2)-Arbeitslasten zu erfüllen.|
| Prozessor-turbofrequenz Grenzwerte (IA Turbo-Einschränkungen). | Stellt die Prozessor-und Grafikleistung so ein, dass Prozessorkerne schneller oder langsamer als die Nennbetriebs Häufigkeit ausgeführt werden können.                                                |

>[!NOTE]
>Der Power-Schieberegler ist völlig unabhängig von den Energieeinstellungen des Betriebssystems, unabhängig davon, ob Sie über die Systemsteuerung/Energieoptionen, Gruppenrichtlinien oder verwandte Methoden konfiguriert sind.

Weitere Informationen finden Sie unter:

-   [Anpassen des Windows-Leistungsstärke Reglers](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Stromsparmodus.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Bewährte Methoden für eine längere Akkulaufzeit


| Bewährte Methode | Wechseln Sie zu | Nächste Schritte |
|---|---|---|                                                                                                                                    
| Sicherstellen, dass Ihr Surface-Gerät auf dem neuesten Stand ist| Windows Update | Geben Sie **Windows Update** in das Suchfeld der Taskleiste ein, und wählen Sie **auf Updates überprüfen**aus. |
| Wählen Sie die optimale Energieeinstellung für das, was Sie gerade tun. | Power-Schieberegler | Wählen Sie in der Taskleiste das Akkusymbol aus, und wählen Sie dann **beste Leistung**, **optimale Akkulaufzeit**oder zwischendurch aus.|
| Akku schonen, wenn er nicht zu klein ist | Stromsparmodus | Wählen Sie in der Taskleiste das Akkusymbol aus, und klicken Sie auf **Batterie Einstellungen**. Wählen Sie " **Stromsparmodus automatisch aktivieren" aus, wenn meine Batterie unter fällt** , und verschieben Sie dann den Schieberegler nach rechts, um die Akkulaufzeit zu verlängern. |
| Konfigurieren der optimalen Bildschirmhelligkeit | Stromsparmodus | Wählen Sie in der Taskleiste das Akkusymbol aus, und klicken Sie auf **Batterie Einstellungen**, und wählen Sie **im Batteriesparmodus niedrigere Bildschirmhelligkeit**aus. |
| Energie sparen, wenn Sie nicht angeschlossen sind | Stromsparmodus| Wählen Sie **den Status des Stromsparmodus bis zum nächsten Aufladen aktivieren**aus.|
| Untersuchen Sie Probleme mit ihren Energieeinstellungen. | Power-Problembehandlung | Wählen Sie in der Taskleiste Suche nach Problembehandlung die Option **Problembehandlung**aus, und wählen Sie dann **Power** aus, und folgen Sie den Anweisungen.|
| Überprüfen der APP-Verwendung | Ihre apps | Schließen Sie apps.|
| Überprüfen Sie das Netzkabel auf eventuelle Schäden.| Ihr Netzkabel | Ersetzen Sie das Netzkabel, wenn es verschlissen oder beschädigt ist.|

## Mehr erfahren 

- [Moderner Standbymodus](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Anpassen des Windows-Leistungsstärke Reglers](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Stromsparmodus](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Verwalten und Bereitstellen von Treiber- und Firmwareupdates für Surface](manage-surface-driver-and-firmware-updates.md)
