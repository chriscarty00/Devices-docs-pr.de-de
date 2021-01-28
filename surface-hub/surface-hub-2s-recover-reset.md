---
title: Zurücksetzen und Wiederherstellung für Surface Hub 2S
description: Erfahren Sie, wie Sie Surface Hub 2S wiederherstellen und zurücksetzen.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304808"
---
# Zurücksetzen und Wiederherstellung für Surface Hub 2S

Wenn Probleme mit Surface Hub 2S auftreten, können Sie das Gerät auf die Werkseinstellungen zurücksetzen oder mithilfe eines USB-Laufwerks wiederherstellen.

Melden Sie sich zunächst bei Surface Hub 2S mit Administratoranmeldeinformationen an, öffnen Sie die **App** "Einstellungen", wählen Sie **"&** Aktualisieren" und dann "Wiederherstellung" **aus.**

## Setzen Sie das Gerät zurück

   > [!IMPORTANT]
   > Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, da Sie später dazu aufgefordert werden. Weitere Informationen finden Sie unter ["Speichern des BitLocker-Schlüssels".](save-bitlocker-key-surface-hub.md)

1. Um das Gerät zurückzusetzen, wählen Sie **"Erste Schritte" aus.**

2. Wenn das **Fenster "Bereit zum Zurücksetzen" dieses Gerätefensters** angezeigt wird, wählen Sie **"Zurücksetzen" aus.** 
  
   > [!IMPORTANT]
   > Wenn der Hub mit der Wiederherstellungspartition neu startet, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert. Wenn Sie diese Eingabeaufforderung überspringen, kann die Zurücksetzung fehlschlagen. Sobald Sie den Schlüssel "BitLocker" eingeben, installiert der Hub das Betriebssystem von der Wiederherstellungspartition neu. Dies kann bis zu einer Stunde dauern.
  
3. Führen Sie zum Neukonfigurieren des Geräts das erste Setupprogramm aus.

4. Wenn Sie das Gerät mithilfe von Microsoft Intune oder einer anderen Lösung für die Verwaltung mobiler Geräte verwalten, ziehen Sie den vorherigen Eintrag zurück, löschen Sie ihn, und registrieren Sie das neue Gerät erneut. Weitere Informationen finden Sie unter [Entfernen von Geräten mithilfe von Zurückziehen,](https://docs.microsoft.com/intune/devices-wipe)Zurückziehen oder manuellen Entfernen der Registrierung des Geräts.

   > [!div class="mx-imgBorder"]
   > ![*Zurücksetzen und Wiederherstellung für Surface Hub 2S*](images/sh2-reset.png)
   <br/>*Abbildung1. Zurücksetzen und Wiederherstellung für Surface Hub 2S* 

## Wiederherstellen von Surface Hub 2S mithilfe eines USB-Wiederherstellungslaufwerks

Neu in Surface Hub 2S: Sie können das Gerät jetzt mithilfe eines Wiederherstellungsabbilds neu installieren.

### Wiederherstellung von einem USB-Laufwerk

Mit Surface Hub 2S können Sie das Gerät mithilfe eines Wiederherstellungsabbilds neu installieren. Dadurch können Sie das Gerät in den Werkseinstellungen neu installieren, wenn Sie den BitLocker-Schlüssel verloren haben oder wenn Sie nicht mehr über Administratoranmeldeinformationen für die Einstellungs-App verfügen.

>[!NOTE]
>Verwenden Sie ein USB 3.0-Laufwerk mit 8 GB oder 16 GB Speicher, formatiert als FAT32.

1. Laden Sie von einem separaten PC das Wiederherstellungsimage der ZIP-Datei von der [Surface -Wiederherstellungswebsite](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) herunter, und kehren Sie dann zu diesen Anweisungen zurück. 

1. Entpacken Sie die heruntergeladene Datei im Stammverzeichnis des USB-Laufwerks.  

1. Schließen Sie das #A0 an einen beliebigen USB-C- oder #A1 auf Surface Hub 2S an.

1. Deaktivieren Sie das Gerät:

   1. Drücken Sie beim Drücken der Taste "Lautstärke nach unten" die Ein-/Aus-Taste.
   1. Drücken Sie weiterhin beide Tasten, bis das Windows-Logo angezeigt wird.
   1. Lassen Sie die Ein/Aus-Taste los, halten Sie jedoch die Schaltfläche "Volume down" gedrückt, bis die Installation der Benutzeroberfläche beginnt.

      ![*Verwenden der Tasten "Volume down" und "Power", um die Wiederherstellung zu initiieren*](images/sh2-keypad.png)
      <br>*Abbildung2. Lautstärke- und Netztasten*

1. Wählen Sie auf dem Sprachauswahlbildschirm die Anzeigesprache für Surface Hub 2S aus.

1. Wählen **Sie "Von einem Laufwerk wiederherstellen"** aus, und **bereinigen**Sie das Laufwerk vollständig, und wählen Sie dann **"Wiederherstellen" aus.** Wenn Sie zur Eingabe eines BitLocker-Schlüssels aufgefordert werden, wählen Sie **"Dieses Laufwerk überspringen" aus.** Surface Hub 2S wird mehrmals neu gestartet und benötigt ca. 30 Minuten, um den Wiederherstellungsvorgang abschließen zu können.

Entfernen Sie beim ersten Einrichten des Bildschirms das USB-Laufwerk.

## Hilfe und Support zu Windows

Wenn Sie Fragen haben oder Hilfe benötigen, können [Sie eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)
