---
title: Zurücksetzen oder Wiederherstellen eines Surface-Hubs
description: Beschreibt die Zurücksetzungs-und Wiederherstellungsprozesse für den Surface Hub und enthält Anweisungen.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Oberflächen Nabe zurücksetzen, wiederherstellen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: c5cf643d0f4a68344bb098916a909dd66e1dac9b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833730"
---
# Zurücksetzen oder Wiederherstellen eines Surface-Hubs

In diesem Artikel wird beschrieben, wie Sie einen Microsoft Surface-Hub zurücksetzen oder wiederherstellen.  

[Beim Zurücksetzen des Surface-Hubs](#reset-a-surface-hub) wird sein Betriebssystem auf das letzte kumulative Windows-Update zurückgesetzt, und alle lokalen Benutzer Dateien und Konfigurationsinformationen werden entfernt. Die Informationen, die entfernt werden, umfassen Folgendes:

- das Gerätekonto
- Kontoinformationen für die lokalen Administratoren des Geräts
- Domain-Join-oder Azure AD-Join-Informationen
- Informationen zur Mobile Device Management (MDM)-Registrierung
- Konfigurationsinformationen, die mithilfe von MDM oder der Einstellungs-APP festgesetzt wurden

Wenn Sie [einen Surface-Hub aus der Cloud wiederherstellen](#recover-a-surface-hub-from-the-cloud) , werden diese Informationen ebenfalls entfernt. Darüber hinaus downloadet der Surface Hub ein neues Betriebssystemabbild und installiert es. Sie können angeben, ob beim Wiederherstellungsvorgang andere Informationen beibehalten werden sollen, die auf dem Surface Hub gespeichert sind.

## Zurücksetzen eines Surface-Hubs

Möglicherweise müssen Sie den Surface-Hub aus folgenden Gründen zurücksetzen:

- Sie purposing das Gerät erneut für einen neuen Besprechungsraum und möchten es neu konfigurieren.
- Sie möchten die lokale Verwaltung des Geräts ändern.
- Der Benutzername oder das Kennwort für das Geräte Konto oder das Administrator Konto ging verloren.
- Nachdem Sie ein Update installiert haben, sinkt die Leistung des Geräts.

Wenn während des Reset-Vorgangs ein leerer Bildschirm für längere Zeit angezeigt wird, warten Sie bitte, und nehmen Sie keine Aktion vor.

> [!WARNING]
> Der Geräte Zurücksetzungsvorgang kann bis zu sechs Stunden dauern. Schalten Sie den Surface Hub erst ab, wenn Sie den Vorgang beenden. Wenn Sie den Vorgang unterbrechen, wird das Gerät nicht mehr funktionsfähig. Das Gerät erfordert Gewährleistungs Service, um wieder funktionsfähig zu werden.

1. Öffnen Sie **Einstellungen** auf dem Surface Hub.

   ![Abbildung mit der Einstellungs-APP für Surface Hub](images/sh-settings.png)

1. Wählen Sie **Update & Security**aus.

   ![Abbildung, die das Update & Sicherheitsgruppe in der Einstellungs-APP für Surface Hub zeigt.](images/sh-settings-update-security.png)

1. Wählen Sie **Wiederherstellen**aus, und wählen Sie dann unter **Gerät zurücksetzen**die Option **Erste Schritte**aus.

   ![Abbildung, die die Option "Gerät zurücksetzen" in der Einstellungs-APP für Surface Hub zeigt.](images/sh-settings-reset-device.png)

   Nachdem der Zurücksetzungsvorgang abgeschlossen ist, startet der Surface-Hub das [erste Ausführungsprogramm](first-run-program-surface-hub.md) erneut. Wenn der Reset-Prozess auf ein Problem stößt, wird der Surface-Hub wieder auf das zuvor vorhandene Betriebssystembild gerollt und dann der Begrüßungsbildschirm angezeigt.

<span id="cloud-recovery" />

## Wiederherstellen von Surface Hub-Gerät aus der Cloud

Wenn der Surface-Hub aus irgendeinem Grund unbrauchbar wird, können Sie ihn weiterhin ohne Unterstützung durch den Microsoft-Support aus der Cloud wiederherstellen. Mit dem Surface Hub können Sie ein neues Betriebssystemabbild aus der Cloud herunterladen und dieses Bild verwenden, um das Betriebssystem neu zu installieren.

Möglicherweise müssen Sie diese Art des Wiederherstellungsprozesses unter den folgenden Umständen verwenden:

- [Der Surface-Hub oder die zugehörigen Konten haben einen instabilen Zustand eingegeben.](#recover-a-surface-hub-in-a-bad-state)
- [Der Surface-Hub ist gesperrt](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>Der Prozess " **Wiederherstellen aus der Cloud** " erfordert eine offene Internetverbindung (kein Proxy oder andere Authentifizierungen). Eine Ethernet-Verbindung wird empfohlen.

### Wiederherstellen von Surface Hub in einem fehlerhaften Zustand

Wenn das Geräte Konto in einen instabilen Zustand gelangt oder wenn beim Administratorkonto Probleme auftreten, können Sie die app "Einstellungen" verwenden, um den Cloud-Wiederherstellungsprozess zu starten. Sie sollten den Cloud-Wiederherstellungsprozess nur verwenden, wenn das Problem durch das [Zurücksetzen des Geräts](#reset-a-surface-hub) nicht behoben wird.

1. Wählen Sie auf dem Surface Hub die Option **Einstellungen** &gt; **Aktualisieren & Security** &gt; **Recovery**aus.

1. Wählen Sie unter **aus der Cloud wiederherstellen die**Option **jetzt neu starten**aus.

   ![Aus der Cloud wiederherstellen](images/recover-from-the-cloud.png)

### Wiederherstellen eines gesperrten Surface Hub-Geräts

In seltenen Fällen kann für einen Surface Hub ein Fehler auftreten, während am Ende einer Sitzung Benutzer- und App-Daten bereinigt werden. In diesem Fall wird das Gerät automatisch neu gestartet und versucht, den Vorgang erneut auszuführen. Wenn dieser Vorgang jedoch wiederholt fehlschlägt, sperrt das Gerät automatisch, um Benutzerdaten zu schützen. Wenn Sie die Sperre aufheben möchten, müssen Sie [das Gerät zurücksetzen](#reset-a-surface-hub) oder, falls das nicht funktioniert, es aus der Cloud wiederherstellen.

1. Suchen Sie den Netzschalter an der Unterkante des Surface Hub. Der Netzschalter befindet sich neben dem Netzkabel. Weitere Informationen zum Netzschalter finden Sie im [Readiness-Leitfaden zur Surface Hub-Website (PDF)](surface-hub-site-readiness-guide.md).

1. Wenn der Surface-Hub den Begrüßungsbildschirm anzeigt, verwenden Sie den Netzschalter, um den Surface Hub zu deaktivieren.

1. Verwenden Sie den Netzschalter, um den Surface Hub wieder einzuschalten. Das Gerät wird gestartet, und der Bildschirm des Surface Hub-Logos wird angezeigt. Wenn sich drehende Punkte unterhalb des Surface Hub-Logos befinden, verwenden Sie den Netzschalter, um den Surface Hub wieder zu deaktivieren.  

1. Wiederholen Sie den Schritt 3 3 Mal, oder bis der Surface-Hub die Meldung "Automatische Reparatur wird vorbereitet" anzeigt. Nachdem diese Meldung angezeigt wird, zeigt der Surface-Hub den Windows RE-Bildschirm an.

1. Wählen Sie **Erweiterte Optionen**aus.

1. Wählen Sie **in der Cloud wiederherstellen aus**. (Optional können Sie " **Zurücksetzen**" auswählen. Die **Wiederherstellung aus der Cloud** ist jedoch die empfohlene Vorgehensweise.)

   ![Wiederherstellen aus der Cloud](images/recover-from-cloud.png)
1. Wenn Sie aufgefordert werden, den BitLocker-Schlüssel einzugeben, führen Sie eine der folgenden Aktionen aus:

   - Wenn Sie die Informationen beibehalten möchten, die BitLocker auf dem Surface-Hub schützt, geben Sie den BitLocker-Schlüssel ein.
   - Wenn Sie die geschützten Informationen verwerfen möchten, wählen Sie **dieses Laufwerk überspringen** aus.  

1. Wenn Sie dazu aufgefordert werden, wählen Sie **erneut installieren**aus.

    ![Neuinstallation](images/reinstall.png)

1. Wenn Sie den Datenträger neu partitionieren möchten, wählen Sie **Ja**aus.

   ![Neu partitionieren](images/repartition.png)

   Zunächst downloadet der Wiederherstellungsvorgang das Betriebssystemabbild aus der Cloud.  

   ![Wird heruntergeladen: 97&](images/recover-progress.png)

   Wenn der Download abgeschlossen ist, stellt der Wiederherstellungsprozess den Surface-Hub entsprechend den von Ihnen ausgewählten Optionen wieder her.
   

## Support kontaktieren

Wenn Sie Fragen haben oder Hilfe benötigen, können Sie [eine Supportanfrage erstellen](https://support.microsoft.com/supportforbusiness/productselection).


## Verwandte Themen

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub-Administratorhandbuch](surface-hub-administrators-guide.md)
