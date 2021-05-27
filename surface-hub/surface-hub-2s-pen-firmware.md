---
title: Aktualisieren der Stift-Firmware auf Surface Hub 2S
description: Auf dieser Seite wird beschrieben, wie Die Firmware für den Surface Hub 2-Stift aktualisiert wird.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: c94cb701fb1b7fcdc0168a795f57a4e497317902
ms.sourcegitcommit: 77b2c51f8467ac3ac37399551b0cc20d9ce57d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "11585966"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>Aktualisieren der Stift-Firmware auf Surface Hub 2S

Sie können die Firmware auf Surface Hub 2 Stift von Windows Update for Business aktualisieren oder das Firmwareupdate auf einen separaten PC herunterladen. Aktualisierte Firmware ist ab dem Windows 26. Februar 2020 verfügbar. 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>Aktualisieren der Stiftfirmware Windows Update for Business

In diesem Abschnitt wird beschrieben, wie Sie die Stiftfirmware über die automatisierten Wartungszyklen für Windows Update aktualisieren, die standardmäßig für 3 Uhr nachts konfiguriert sind. Sie müssen zwei Wartungszyklen planen, bevor Sie das Update auf den Surface Hub anwenden. Alternativ können Sie wie jedes andere Update auch Windows Update for Business (WUfB) verwenden, um die Stiftfirmware anzuwenden. Weitere Informationen finden Sie unter [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Stellen Sie sicher, Surface Hub 2 Stift mit Surface Hub 2S gekoppelt ist: Drücken und halten Sie die obere Taste, bis das led-Licht der weißen Anzeige blinkt. ****

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 Stift](images/sh2-pen-1.png)

2. Melden Surface Hub Sie sich als Administrator an, öffnen Sie **Einstellungen**, und suchen Sie dann nach neuen Bluetooth Geräten.

3. Wählen Sie den Stift aus, um den Kopplungsprozess zu abschließen.

4. Drücken Sie **die obere** Schaltfläche auf dem Stift, um das Update anzuwenden. Es kann bis zu zwei Stunden dauern.

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>Aktualisieren der Stiftfirmware durch Herunterladen auf separaten PC

Sie können die Firmware auf einem Surface Hub 2-Stift von einem separaten PC aktualisieren, auf dem Windows 10. Mit dieser Methode können Sie auch überprüfen, ob die Stiftfirmware erfolgreich auf die neueste Version aktualisiert wurde.

1. Koppeln Sie Surface Hub 2-Stift mit Ihrem Bluetooth PC: **** Halten Sie die obere Taste gedrückt, bis die led-Leuchte der weißen Anzeige blinkt.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 Stift](images/sh2-pen-1.png)

2. Suchen Sie auf dem PC nach neuen Bluetooth Geräten.

3. Wählen Sie den Stift aus, um den Kopplungsprozess zu abschließen.

4. Trennen Sie alle Surface Hub 2s-Stifte, bevor Sie ein neues Update starten.

5. Laden Sie [Surface Hub 2 Pen Firmware Update Tool auf](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) Ihren PC herunter.

6. Führen Sie **PenCfu.exe.** Der Installationsfortschritt wird im Tool angezeigt. Es kann einige Minuten dauern, bis die Aktualisierung abgeschlossen ist. 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>Überprüfen der Firmwareversion Surface Hub 2 Stifts

1. Führen **get_version.bat** aus, und drücken Sie **die obere** Schaltfläche auf dem Stift.

2. Das Tool berichtet die Firmwareversion des Stifts. 

   Beispiel:
    - Alte Firmware ist 468.2727.368
    - Neue Firmware ist 468.3347.368

## <a name="command-line-options"></a>Befehlszeilenoptionen

Sie können Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) über die Befehlszeile ausführen.

1. Koppeln Sie den Stift mit Ihrem PC, und klicken Sie auf **die obere** Schaltfläche des Stifts.

2. Doppelklicken ** SiePenCfu.exe, ** um das Firmwareupdate zu initiieren. Beachten Sie, dass die Konfigurationsdatei und die Firmwareimagedateien im gleichen Ordner wie das Tool gespeichert werden müssen.

3. Führen Sie für weitere Optionen **PenCfu.exe -h** aus, um die verfügbaren Parameter anzuzeigen, wie in der folgenden Tabelle aufgeführt.  

   Beispiel: `PenCfu.exe -h`

4. Geben **Sie STRG+C ein,** um das Tool sicher herunterfahren zu können.


| Befehl | Beschreibung |
| -------------- |---------------------------- |
| -h-Hilfe        | Hilfe und Beenden der Befehlszeilenschnittstelle des Anzeigetools. |
| -v-Version     | Anzeigen der Toolversion und des Exits. |
| -l log-filter  | Legen Sie eine Filterebene für die Protokolldatei ein. Protokollmeldungen haben 4 mögliche Ebenen: DEBUG (niedrigste), INFO, WARNUNG und FEHLER (am höchsten). Durch Festlegen einer Protokollfilterebene werden Protokollmeldungen so gefiltert, dass nur Nachrichten mit derselben Ebene oder höher angezeigt werden. Wenn die Filterstufe beispielsweise auf WARNUNG festgelegt ist, werden nur WARNUNGs- und FEHLERmeldungen protokolliert. Standardmäßig ist diese Option auf AUS festgelegt, wodurch die Protokollierung deaktiviert wird. |
| -g get-version | Wenn angegeben, wird dem Tool nur die FW-Version des verbundenen Stifts angezeigt, die der Konfigurationsdatei entspricht, die im gleichen Ordner wie das Tool gespeichert ist.  |

