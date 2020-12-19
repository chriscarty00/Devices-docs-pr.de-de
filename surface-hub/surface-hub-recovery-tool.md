---
title: Verwenden des Wiederherstellungstools für Surface Hub
description: Verwenden des Surface Hub-Wiederherstellungstools zum erneuten abbilden der SSD
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub verwalten
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/18/2018
ms.localizationpriority: medium
ms.openlocfilehash: a9ebab6848efa706609a39b0eb99fa42df2156bf
ms.sourcegitcommit: ce7ad475b776a78ba215e77111ea5371afeb4f28
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2020
ms.locfileid: "11237327"
---
# Verwenden des Wiederherstellungstools für Surface Hub

Das [Microsoft Surface Hub-Wiederherstellungs Tool](https://www.microsoft.com/download/details.aspx?id=52210) unterstützt Sie beim erneuten abbilden Ihres Surface Hub-Solid-State-Laufwerks (SSD) mithilfe eines Windows 10-Desktop Geräts, ohne den Support zu anrufen oder die SSD zu ersetzen. Mit diesem Tool können Sie eine SSD umbilden, die über ein unbekanntes Administrator Kennwort, Startfehler, keine Cloud-Wiederherstellung oder ein Gerät mit einer älteren Version des Betriebssystems verfügt. Das Tool repariert keine physisch beschädigten SSDs.

Wenn Sie das Surface-Hub-SSD mithilfe des Wiederherstellungstools erneut abbilden möchten, müssen Sie die SSD vom Surface-Hub entfernen, das Laufwerk mit dem USB-zu-SATA-Kabel verbinden und dann das Kabel an den Desktop-PC anschließen, auf dem das Wiederherstellungstool installiert ist. Weitere Informationen zum Entfernen des vorhandenen Laufwerks aus dem Surface Hub finden Sie unter [Ersetzen des Surface Hub-SSD](surface-hub-ssd-replacement.md).

> [!IMPORTANT]
> Lassen Sie das Gerät nicht in den Standbymodus wechseln oder den Download der Bilddatei unterbrechen.

Wenn das Tool beim erneuten abbilden Ihres Laufwerks nicht erfolgreich ist, wenden Sie sich bitte an den [Surface Hub-Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## Voraussetzungen

### Mandatory

- Host-PC mit 64-Bit-Version von Windows 10, Version 1607 oder höher
- Internetzugriff
- Öffnen Sie den USB-Port 2,0 oder höher
- USB-zu-SATA-Kabel
- 10 GB freier Speicherplatz auf dem Hostcomputer
- SSDs, geliefert mit Surface Hub oder einer SSD, die vom Support als Ersatz bereitgestellt wird. SSDs, die nicht von Microsoft bereitgestellt werden, werden nicht unterstützt.

### Empfohlen

- Hochgeschwindigkeits-Internet Verbindung
- USB 3,0-Port öffnen
- USB-3,0 oder höheres USB-zu-SATA-Kabel
- Das Imaging-Tool wurde mit dem folgenden Hersteller und Modell von Kabeln getestet:
    - StarTech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## Herunterladen des Surface Hub-Wiederherstellungstools

Surface Hub-Wiederherstellungs Tool steht unter dem Dateinamen **SurfaceHub_Recovery_v2.0.139.0.msi**für den Download von [Surface Hub-Tools](https://www.microsoft.com/download/details.aspx?id=52210) zur Verfügung.

Klicken Sie zum Starten des Downloads auf **herunterladen**, wählen Sie in der Liste **SurfaceHub_Recovery_v2.0.139.0.msi** aus, und klicken Sie auf **weiter**. Wählen Sie im Popup-Fenster eine der folgenden Optionen aus:

- Klicken Sie auf **Ausführen** , um die Installation sofort zu starten.
- Klicken Sie auf **Speichern** , um den Download zur späteren Installation auf Ihren Computer zu kopieren.

Installieren des Surface Hub-Wiederherstellungstools auf dem Host-PC.

## Ausführen des Surface Hub-Wiederherstellungstools

1. Wählen Sie auf dem Host-PC die Schaltfläche **Start** aus, Scrollen Sie durch die alphabetische Liste auf der linken Seite, und wählen Sie die Verknüpfung für das Wiederherstellungstool aus.

    ![Microsoft Surface Hub-Wiederherstellungs Tool-Verknüpfung](images/shrt-shortcut.png)

2. Klicken Sie auf **Start**.

    ![Start Schaltfläche für das Wiederherstellungs Tool](images/shrt-start.png)


3. Klicken Sie im Fenster " **Anleitung** " auf **weiter**.

    ![Lassen Sie Ihren Computer nicht in die Schlaf Anleitung gehen](images/shrt-guidance.png)

4. Klicken Sie im Fenster Bild auswählen entweder auf **RS2** oder auf dessen Nachfolger **20H2**, wählen Sie **weiter** aus, und wählen Sie dann **Bild herunterladen aus.**

     ![Wiederherstellungstool auswählen des Bild ](images/shrt-select-image.png) ![ Wiederherstellungstools herunterladen](images/shrt-download-image.png)

5. Die Zeit zum Herunterladen des Wiederherstellungs Bilds hängt von den Geschwindigkeiten der Internetverbindung ab. Bei einer durchschnittlichen Unternehmensverbindung kann es bis zu einer Stunde dauern, bis die 8 GB-Imagedatei heruntergeladen wurde.

    ![Bild wird heruntergeladen](images/shrt-download.png)



5. Wenn der Download abgeschlossen ist, weist das Tool Sie an, ein SSD-Laufwerk zu verbinden. Wenn das Tool das angefügte Laufwerk nicht finden kann, besteht eine gute Wahrscheinlichkeit, dass das verwendete Kabel nicht den Namen der SSD an Windows meldet.  Das Imaging-Tool muss den Namen des Laufwerks als "LiteOn L CH-128V2S USB-Gerät" finden, bevor es fortfahren kann.  Weitere Informationen zum Entfernen des vorhandenen Laufwerks aus dem Surface Hub finden Sie unter [Ersetzen des Surface Hub-SSD](surface-hub-ssd-replacement.md).

    ![SSD verbinden](images/shrt-drive.png)

6. Wenn das Laufwerk erkannt wird, klicken Sie auf **Start** , um mit der Wiederherstellung zu beginnen. Klicken Sie auf der Warnung, dass alle Daten auf dem Laufwerk gelöscht werden, auf **OK**.



    Vor dem Anwenden des Systemabbilds auf das Laufwerk wird die SSD neu partitioniert und formatiert. Das Kopieren der Systembinärdateien dauert ungefähr 30 Minuten, kann aber je nach der Geschwindigkeit Ihres USB-Busses, des verwendeten Kabels oder der auf Ihrem System installierten Antivirensoftware länger dauern.



## Problembehandlung und häufige Probleme

Problem | Anmerkungen
--- | ---
Das Tool kann die SSD nicht abbilden | Stellen Sie sicher, dass Sie eine von der Factory bereitgestellte SSD und eines der getesteten Kabel verwenden.
Der Prozess der Bildbearbeitung wird angehalten/fixiert angezeigt | Es ist sicher, das Surface Hub-Wiederherstellungs Tool ohne negative Auswirkungen auf die SSD zu schließen und neu zu starten.
Das Laufwerk wird vom Tool nicht erkannt | Überprüfen Sie, ob der Surface Hub SSD als Lite-On Laufwerk "LiteOn L CH-128V2S USB Device" aufgelistet ist.  Wenn das Laufwerk als ein anderes benanntes Gerät erkannt wird, ist das aktuelle Kabel nicht kompatibel. Versuchen Sie es mit einem anderen Kabel oder einem der oben aufgeführten getesteten Kabel.
Fehler:-2147024809 | Öffnen Sie den Datenträger-Manager, und entfernen Sie die Partitionen auf dem Surface-Hub-Laufwerk.  Trennen Sie das Laufwerk, und schließen Sie es erneut an den Hostcomputer an. Starten Sie das Imaging-Tool erneut.

Wenn das Tool beim erneuten abbilden Ihres Laufwerks nicht erfolgreich ist, wenden Sie sich bitte an den [Surface Hub-Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## Versionsverlauf

### Version v 2.0.139.0

*Veröffentlichungsdatum: 18. Dezember 2020*<br>
Diese Version des Surface Hub-Wiederherstellungstools bietet Unterstützung für die folgenden Elemente:
- Update zur Unterstützung von Windows 10 Team 2020 Update (20H2)
- Verbesserungen bei der Benutzeroberfläche
- Architektonische Änderungen
- Telemetrie-Ergänzungen

