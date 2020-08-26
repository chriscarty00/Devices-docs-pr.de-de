---
title: Zurücksetzen und Wiederherstellen für Surface Hub 2S
description: Hier erfahren Sie, wie Sie Surface Hub 2S wiederherstellen und zurücksetzen.
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
ms.openlocfilehash: e3b1e380f9776fc56e99b8d4e35f708aa952759c
ms.sourcegitcommit: e075b46f14b730464d66246b0280ef2cfa16b3fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963584"
---
# Zurücksetzen und Wiederherstellen für Surface Hub 2S

Wenn Probleme mit Surface Hub 2S auftreten, können Sie das Gerät auf die Werkseinstellungen zurücksetzen oder mithilfe eines USB-Laufwerks wiederherstellen.

Melden Sie sich zunächst bei Surface Hub 2S mit Administratoranmeldeinformationen an, öffnen Sie die **Einstellungs** -APP, wählen Sie **Update & Security**aus, und wählen Sie dann **Wiederherstellen**aus.

## Setzen Sie das Gerät zurück

1. Wenn Sie das Gerät zurücksetzen möchten, wählen Sie **Erste Schritte**aus.

2. Wenn das Fenster **bereit zum Zurücksetzen dieses Geräts** angezeigt wird, wählen Sie **Zurücksetzen**aus. 
  
   > [!NOTE]
   > Surface Hub 2S installiert das Betriebssystem von der Wiederherstellungspartition erneut. Dieser Vorgang kann bis zu einer Stunde dauern.
  
3. Um das Gerät neu zu konfigurieren, führen Sie das erstmalige Setup-Programm aus.

4. Wenn Sie das Gerät mithilfe von Microsoft InTune oder einer anderen Lösung für die Verwaltung mobiler Geräte verwalten, ziehen Sie den vorherigen Eintrag zurück, löschen Sie ihn, und registrieren Sie das neue Gerät dann erneut. Weitere Informationen finden Sie unter [Entfernen von Geräten mithilfe von wischen, zurückziehen oder manuelles Aufheben der Registrierung des Geräts](https://docs.microsoft.com/intune/devices-wipe).

> [!div class="mx-imgBorder"]
> ![* Reset und Recovery für Surface Hub 2S *](images/sh2-reset.png)
<br/>*Abbildung1. Zurücksetzen und Wiederherstellen für Surface Hub 2S* 

## Wiederherstellen des Surface Hub 2S mithilfe eines USB-Wiederherstellungs Laufwerks

Neu in Surface Hub 2S können Sie das Gerät jetzt mithilfe eines Wiederherstellungs Bilds erneut installieren.

### Wiederherstellung von einem USB-Laufwerk

Mithilfe von Surface Hub 2S können Sie das Gerät mithilfe eines Wiederherstellungs Bilds erneut installieren. Auf diese Weise können Sie das Gerät erneut auf die Werkseinstellungen installieren, wenn Sie den BitLocker-Schlüssel verloren haben oder wenn Sie nicht mehr über Administratoranmeldeinformationen für die Einstellungs-APP verfügen.

>[!NOTE]
>Verwenden Sie ein USB-3,0-Laufwerk mit 8 GB oder 16 GB Speicher, das als FAT32 formatiert ist.

1. Laden Sie das ZIP-Datei Wiederherstellungsabbild von einem separaten PC von der [Surface Recovery-Website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) herunter, und kehren Sie dann zu diesen Anweisungen zurück. 

1. Entzippen Sie die heruntergeladene Datei auf das Stammverzeichnis des USB-Laufwerks.  

1. Schließen Sie das USB-Laufwerk an einen beliebigen USB-C-oder USB-Anschluss an Surface Hub 2S an.

1. Gerät ausschalten:

   1. Drücken Sie bei gedrückter Lautstärketaste die Power-Taste.
   1. Drücken Sie beide Tasten so lange, bis Sie das Windows-Logo sehen.
   1. Lassen Sie den Netzschalter Los, halten Sie die Lautstärketaste aber weiterhin gedrückt, bis die Benutzeroberfläche für die Installation beginnt.

   ![* Verwenden Sie die Lautstärke-und Netztasten, um die Wiederherstellung zu initiieren *](images/sh2-keypad.png) <br>
   **Abbildung2. Lautstärke-und Power-Tasten**

1. Wählen Sie auf dem Bildschirm Sprachauswahl die Anzeigesprache für den Surface Hub 2S aus.

1. Wählen Sie **auf einem Laufwerk wiederherstellen aus** , und **reinigen Sie das Laufwerk vollständig**, und wählen Sie dann **Wiederherstellen**aus. Wenn Sie zur Eingabe eines BitLocker-Schlüssels aufgefordert werden, wählen Sie **dieses Laufwerk überspringen**aus. Surface Hub 2S wird mehrmals neu gestartet, und es dauert ungefähr 30 Minuten, bis der Wiederherstellungsvorgang abgeschlossen ist.

Wenn der Bildschirm für die erstmalige Einrichtung angezeigt wird, entfernen Sie das USB-Laufwerk.

## Hilfe und Support zu Windows

Wenn Sie Fragen haben oder Hilfe benötigen, können Sie [eine Supportanfrage erstellen](https://support.microsoft.com/supportforbusiness/productselection).
