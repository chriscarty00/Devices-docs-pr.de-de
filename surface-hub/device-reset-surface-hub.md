---
title: Zurücksetzen oder Wiederherstellen eines Surface Hub
description: Beschreibt die Zurücksetzungs- und Wiederherstellungsprozesse für den Surface Hub und enthält Anweisungen.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Zurücksetzen von Surface Hub, Wiederherstellen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304818"
---
# Zurücksetzen oder Wiederherstellen eines Surface Hub

In diesem Artikel wird das Zurücksetzen oder Wiederherstellen eines Microsoft Surface beschrieben.  

[Beim Zurücksetzen des Surface Hub](#reset-a-surface-hub) wird das Betriebssystem auf das letzte kumulative Windows Update zurückgegeben, und alle lokalen Benutzerdateien und Konfigurationsinformationen werden entfernt. Die entfernten Informationen umfassen Folgendes:

- das Gerätekonto
- Kontoinformationen für die lokalen Administratoren des Geräts
- Domänen- oder Azure AD-Join-Informationen
- Registrierungsinformationen zur mobilen Geräteverwaltung (Mobile Device Management, MDM)
- Konfigurationsinformationen, die mithilfe von MDM oder der App "Einstellungen" festgelegt wurden

[Durch das Wiederherstellen eines Surface Hub aus der Cloud](#recover-a-surface-hub-from-the-cloud) werden diese Informationen ebenfalls entfernt. Darüber hinaus lädt der Surface Hub ein neues Betriebssystemimage herunter und installiert es. Sie können angeben, ob beim Wiederherstellungsprozess andere Informationen beibehalten werden, die auf dem Surface Hub gespeichert sind. Dasselbe Betriebssystemimage wird vom [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) verwendet, wenn Sie einen Surface Hub wiederherstellen müssen, für den keine dieser Optionen verwendet werden kann.

## Zurücksetzen eines Surface Hub

Möglicherweise müssen Sie den Surface Hub aus folgenden Gründen zurücksetzen:

- Sie löschen das Gerät für einen neuen Besprechungsraum neu und möchten es neu konfigurieren.
- Sie möchten die lokale Verwaltung des Geräts ändern.
- Der Benutzername oder das Kennwort für das Gerätekonto oder das Administratorkonto ist verloren gegangen.
- Nach der Installation eines Updates nimmt die Leistung des Geräts ab.

Wenn während des Zurücksetzens für längere Zeit ein leerer Bildschirm angezeigt wird, warten Sie, und ergreifen Sie keine Aktion.

> [!WARNING]
> Der Zurücksetzen des Geräts kann bis zu sechs Stunden dauern. Deaktivieren oder trennen Sie den Surface Hub erst, wenn der Prozess abgeschlossen ist. Wenn Sie den Vorgang unterbrechen, ist das Gerät nicht mehr funktionsfähig. Das Gerät erfordert einen Garantiedienst, um wieder funktionsfähig zu werden.

1. Öffnen Sie **Einstellungen** auf dem Surface Hub.

   ![Abbildung der Einstellungs-App für Surface Hub.](images/sh-settings.png)

2. Wählen **Sie "Update & Security" aus.**

   ![Abbildung der Gruppe "Update & Security" in der App "Einstellungen" für Surface Hub.](images/sh-settings-update-security.png)

3. Wählen **Sie "Wiederherstellung"** aus, und wählen Sie dann unter **"Gerät zurücksetzen"** die Option **"Erste Schritte" aus.**

   > [!IMPORTANT]
   > Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, da Sie später dazu aufgefordert werden. Weitere Informationen finden Sie unter ["Speichern des BitLocker-Schlüssels".](save-bitlocker-key-surface-hub.md) Wenn der Hub mit der Wiederherstellungspartition neu startet, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert. Wenn Sie diese Eingabeaufforderung überspringen, kann die Zurücksetzung fehlschlagen.
   
   ![Abbildung der Option "Gerät zurücksetzen" in der App "Einstellungen" für Surface Hub.](images/sh-settings-reset-device.png)

   Nach Abschluss des Zurücksetzungsprozesses startet Surface Hub das Programm für die [erste Ausführung](first-run-program-surface-hub.md) erneut. Wenn beim Zurücksetzen ein Problem besteht, wird der Surface Hub wieder auf das zuvor vorhandene Betriebssystemimage zurückgesetzt, und dann wird die Willkommensbildschirm angezeigt.

<span id="cloud-recovery" />

## Wiederherstellen von Surface Hub-Gerät aus der Cloud

Wenn der Surface Hub aus einem bestimmten Grund nicht mehr verwendet werden kann, können Sie ihn ohne Unterstützung des Microsoft Support weiterhin aus der Cloud wiederherstellen. Surface Hub kann ein neues Betriebssystemimage aus der Cloud herunterladen und dieses Image verwenden, um das Betriebssystem neu zu installieren.

Unter den folgenden Umständen müssen Sie diese Art von Wiederherstellungsprozess möglicherweise verwenden:

- [Der Surface Hub oder die zugehörigen Konten sind in einen instabilen Zustand bzw.](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub ist gesperrt](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>Für **die Wiederherstellung aus dem Cloudprozess** ist eine kabelgebundene Verbindung erforderlich, die eine offene Internetverbindung (kein Proxy oder andere Authentifizierungsaufforderungen) bietet.

### Wiederherstellen von Surface Hub in einem fehlerhaften Zustand

Wenn das Gerätekonto instabil wird oder beim Administratorkonto Probleme auftreten, können Sie den Cloudwiederherstellungsprozess mithilfe der App "Einstellungen" starten. Sie sollten den Cloudwiederherstellungsprozess nur verwenden, [wenn](#reset-a-surface-hub) das Problem beim Zurücksetzen des Geräts nicht behoben wird.

1. Wählen Sie auf dem Surface Hub **"Einstellungen** &gt; **aktualisieren" & Sicherheitswiederherstellung** &gt; **aus.**

2. Wählen **Sie unter "Aus Der Cloud wiederherstellen"** die Option **"Jetzt neu starten" aus.**

   ![Aus der Cloud wiederherstellen](images/recover-from-the-cloud.png)

### Wiederherstellen eines gesperrten Surface Hub-Geräts

In seltenen Fällen kann für einen Surface Hub ein Fehler auftreten, während am Ende einer Sitzung Benutzer- und App-Daten bereinigt werden. In diesem Fall wird das Gerät automatisch neu gestartet und versucht, den Vorgang erneut zu starten. Wenn dieser Vorgang jedoch wiederholt fehlschlägt, wird das Gerät automatisch gesperrt, um Benutzerdaten zu schützen. Um es zu entsperren, müssen Sie das [Gerät](#reset-a-surface-hub) zurücksetzen oder, falls dies nicht funktioniert, es aus der Cloud wiederherstellen.

1. Suchen Sie den Netzschalter unten im Surface Hub. Der Netzschalter befindet sich neben der Netzkabelverbindung. Weitere Informationen zum Netzschalter finden Sie im [Surface Hub Site Readiness Guide (PDF).](surface-hub-site-readiness-guide.md)

2. Während der Surface Hub den Willkommensbildschirm anzeigt, verwenden Sie den Netzschalter, um den Surface Hub zu deaktivieren.

3. Verwenden Sie den Netzschalter, um den Surface Hub wieder zu aktivieren. Das Gerät wird gestartet und zeigt den Surface Hub-Logo-Bildschirm an. Wenn unter dem Surface Hub-Logo Sich drehende Punkte angezeigt werden, deaktivieren Sie den Surface Hub mithilfe des Netzschalters erneut.  

4. Wiederholen Sie Schritt 3 dreimal, oder bis surface Hub die Meldung "Vorbereiten der automatischen Reparatur" anzeigt. Nachdem diese Meldung angezeigt wurde, zeigt der Surface Hub den Windows RE-Bildschirm an.

5. Wählen Sie **erweiterte Optionen aus.**

6. Wählen Sie **"Aus der Cloud wiederherstellen" aus.** (Optional können Sie **"Zurücksetzen" auswählen.** Es wird **jedoch empfohlen, die Wiederherstellung** aus der Cloud zu verwenden.)

   ![Wiederherstellen aus der Cloud](images/recover-from-cloud.png)
7. Wenn Sie zur Eingabe des Bitlocker-Schlüssels aufgefordert werden, gehen Sie wie folgt vor:

   - Um die Informationen zu erhalten, die Bitlocker auf dem Surface Hub schützt, geben Sie den Bitlocker-Schlüssel ein.
   - Um die geschützten Informationen zu verwerfen, wählen **Sie "Dieses Laufwerk überspringen" aus.**  

8. Wenn Sie dazu aufgefordert werden, wählen Sie **"Neu installieren" aus.**

    ![Neuinstallation](images/reinstall.png)

9. Wählen Sie "Ja" aus, um den Datenträger neu **zupartitionieren.**

   ![Neu partitionieren](images/repartition.png)

   Zunächst lädt der Wiederherstellungsprozess das Betriebssystemimage aus der Cloud herunter.  

   ![Wird heruntergeladen: 97&](images/recover-progress.png)

   Wenn der Download abgeschlossen ist, stellt der Wiederherstellungsprozess den Surface Hub entsprechend den von Ihnen ausgewählten Optionen wieder bereit.
   

## Hilfe und Support zu Windows

Wenn Sie Fragen haben oder Hilfe benötigen, können [Sie eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)


## Verwandte Themen

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub-Administratorhandbuch](surface-hub-administrators-guide.md)
