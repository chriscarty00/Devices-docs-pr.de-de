---
title: Aktualisieren der Stift-Firmware auf Surface Hub 2S
description: Auf dieser Seite wird beschrieben, wie Sie die Firmware für den Surface Hub 2-Stift aktualisieren.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833055"
---
# Aktualisieren der Stift-Firmware auf Surface Hub 2S

Sie können die Firmware auf dem Surface Hub 2-Stift über Windows Update für Unternehmen oder durch Herunterladen des Firmware-Updates auf einen separaten PC aktualisieren. Die aktualisierte Firmware steht ab dem 26. Februar 2020 über Windows Update zur Verfügung. 

## Aktualisieren der Stift-Firmware mithilfe von Windows Update für Unternehmen

In diesem Abschnitt wird beschrieben, wie Sie die Stift-Firmware über die automatisierten Wartungszyklen für Windows Update aktualisieren, die standardmäßig so konfiguriert sind, dass Sie nächtlich um 3 Uhr morgens ausgeführt werden. Sie müssen zwei Wartungszyklen planen, bevor Sie die Aktualisierung auf den Surface Hub 2-Stift anwenden können. Alternativ können Sie wie jedes andere Update auch Windows Server Update Services (WSUS) verwenden, um die Stift-Firmware anzuwenden. Weitere Informationen finden Sie unter [Verwalten von Windows-Updates auf Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Stellen Sie sicher, dass der Surface Hub 2-Stift mit dem Surface Hub 2S verbunden ist: halten Sie die **obere** Taste gedrückt, bis die weiße Anzeige-LED blinkt. <br>
![Surface Hub 2-Stift](images/sh2-pen-1.png) <br>
2. Melden Sie sich auf Surface Hub als Administrator an, öffnen Sie **Einstellungen**, und suchen Sie dann nach neuen Bluetooth-Geräten.
3. Wählen Sie den Stift aus, um den Kopplungsvorgang abzuschließen.
4. Drücken Sie die **obere** Taste des Stifts, um die Aktualisierung anzuwenden. Es kann bis zu zwei Stunden dauern, bis der Vorgang abgeschlossen ist.

## Aktualisieren der Stift-Firmware durch herunterladen auf den separaten PC

Sie können die Firmware auf dem Surface Hub 2-Stift von einem separaten PC mit Windows 10 aktualisieren. Mit dieser Methode können Sie auch sicherstellen, dass die Stift-Firmware erfolgreich auf die neueste Version aktualisiert wurde.

1. Verbinden Sie den Surface Hub 2-Stift mit Ihrem Bluetooth-fähigen PC: Drücken Sie die **obere** Taste, und halten Sie sie gedrückt, bis die weiße LED-Anzeige blinkt. <br>
![Surface Hub 2-Stift](images/sh2-pen-1.png) <br>
2. Suchen Sie auf dem PC nach neuen Bluetooth-Geräten.
3. Wählen Sie den Stift aus, um den Kopplungsvorgang abzuschließen.
4. Trennen Sie alle anderen Surface Hub 2S-Stifte, bevor Sie ein neues Update beginnen.
3. Laden Sie das [Surface Hub 2-Tool zur Aktualisierung der Stift-Firmware](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) auf Ihren PC herunter.
4. Führen Sie **PenCfu.exe aus.** Der Installationsfortschritt wird im Tool angezeigt. Es kann einige Minuten dauern, bis die Aktualisierung abgeschlossen ist. 


## Überprüfen der Firmware-Version des Surface Hub 2-Stifts

1. Führen Sie **get_version.bat** aus, und drücken Sie die **obere** Taste des Stifts.
2. Das Tool meldet die Firmware-Version des Stifts. Beispiel:
    - Alte Firmware ist 468.2727.368
    - Neue Firmware ist 468.2863.369

## Befehlszeilenoptionen

Sie können Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) über die Befehlszeile ausführen.

1. Koppeln Sie den Stift an Ihren PC, und klicken Sie auf die **obere** Schaltfläche des Stifts.
2. Doppelklicken Sie auf **PenCfu.exe** , um das Firmware-Update zu initiieren. Beachten Sie, dass die Konfigurationsdatei und die Firmware-Bilddateien im gleichen Ordner wie das Tool gespeichert werden müssen.
3. Wenn Sie weitere Optionen anzeigen möchten, führen Sie **PenCfu.exe-h** aus, um die verfügbaren Parameter anzuzeigen, wie in der folgenden Tabelle aufgelistet.  
    - Beispiel: PenCfu.exe-h
4. Drücken Sie **STRG + C** , um das Tool sicher herunterzufahren.

 

| **Befehl**    | **Beschreibung**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h-Hilfe        | Anzeigetool Befehlszeilenschnittstelle Hilfe und beenden.                                                                                                                                                                                                                                                                                                                                             |
| -v-Version     | Tool Version anzeigen und beenden                                                                                                                                                                                                                                                                                                                                                                 |
| -l Log-Filter  | Legen Sie eine Filterstufe für die Protokolldatei auf. Protokollnachrichten weisen 4 mögliche Ebenen auf: Debug (niedrigste), Informationen, Warnung und Fehler (höchste). Durch das Festlegen einer Protokollfilter Ebene werden die Nachrichten nur auf eine Nachricht mit der gleichen oder höheren Ebene gefiltert. Wenn beispielsweise die Filterstufe auf Warning gesetzt ist, werden nur Warn-und Fehlermeldungen protokolliert. Standardmäßig ist diese Option auf OFF gesetzt, wodurch die Protokollierung deaktiviert wird. |
| -g Get-Version | Wenn angegeben, erhält das Tool nur die FW-Version des verbundenen Stifts, die mit der Konfigurationsdatei übereinstimmt, die im gleichen Ordner wie das Tool gespeichert ist.                                                                                                                                                                                                                                    