---
title: Zurücksetzen oder Wiederherstellen eines Surface Hub
description: Beschreibt die Reset- und Wiederherstellungsprozesse für Surface Hub und enthält Anweisungen.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Zurücksetzen von Surface Hub, Wiederherstellen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 8d9a4f995abda4e005e8136ace62e10fb564c9b8
ms.sourcegitcommit: ea853f2dba67e63e6df33538670fd581e17facab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "11408810"
---
# <a name="reset-or-recover-a-surface-hub"></a>Zurücksetzen oder Wiederherstellen eines Surface Hub

In diesem Artikel wird das Zurücksetzen oder Wiederherstellen eines Microsoft Surface beschrieben.  

[Beim Zurücksetzen des Surface Hub](#reset-a-surface-hub) wird das Betriebssystem auf das letzte kumulative Windows-Update zurückgegeben, und alle lokalen Benutzerdateien und Konfigurationsinformationen werden entfernt. Die entfernten Informationen umfassen Folgendes:

- das Gerätekonto
- Kontoinformationen für die lokalen Administratoren des Geräts
- Informationen zum Domänen- oder Azure AD-Beitritt
- Registrierungsinformationen zur Mobile Device Management (MDM)
- Konfigurationsinformationen, die mithilfe von MDM oder der Einstellungs-App festgelegt wurden

[Beim Wiederherstellen eines Surface Hub aus der Cloud](#recover-a-surface-hub-from-the-cloud) werden diese Informationen ebenfalls entfernt. Darüber hinaus lädt Surface Hub ein neues Betriebssystemimage herunter und installiert es. Sie können angeben, ob beim Wiederherstellungsprozess andere Informationen beibehalten werden, die auf dem Surface Hub gespeichert sind. Dasselbe Betriebssystemimage wird vom [Surface Hub-Wiederherstellungstool](surface-hub-recovery-tool.md) verwendet, wenn Sie einen Surface Hub wiederherstellen müssen, für den keine dieser Optionen verwendet werden kann.

## <a name="reset-a-surface-hub"></a>Zurücksetzen eines Surface Hub

Möglicherweise müssen Sie Ihren Surface Hub aus folgenden Gründen zurücksetzen:

- Sie verwenden das Gerät für einen neuen Besprechungsraum um und möchten es neu konfigurieren.
- Sie möchten die lokale Verwaltung des Geräts ändern.
- Der Benutzername oder das Kennwort für das Gerätekonto oder das Administratorkonto ist verloren gegangen.
- Nach der Installation eines Updates nimmt die Leistung des Geräts ab.

Wenn während des Zurücksetzens ein leerer Bildschirm für längere Zeit angezeigt wird, warten Sie, und ergreifen Sie keine Aktion.

> [!WARNING]
> Die Gerätezurücksetzung kann bis zu sechs Stunden dauern. Deaktivieren oder trennen Sie den Surface Hub erst, wenn der Prozess abgeschlossen ist. Wenn Sie den Prozess unterbrechen, ist das Gerät nicht mehr funktionsfähig. Das Gerät erfordert einen Garantiedienst, um wieder funktionsfähig zu werden.

1. Öffnen Sie **Einstellungen** auf dem Surface Hub.

   > [!div class="mx-imgBorder"]
   > ![Abbildung, die die Einstellungs-App für Surface Hub zeigt.](images/sh-settings.png)

2. Wählen **Sie Update & Security aus.**

   > [!div class="mx-imgBorder"]
   > ![Abbildung, die update & security group in Settings app for Surface Hub zeigt.](images/sh-settings-update-security.png)

3. Wählen **Sie Wiederherstellung**aus, und wählen Sie dann unter **Gerät zurücksetzen**die Option Erste Schritte **aus.**

   > [!IMPORTANT]
   > Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, wie Sie später dazu aufgefordert werden. Weitere Informationen finden Sie [unter Save your BitLocker key](save-bitlocker-key-surface-hub.md). Wenn der Hub mit der Wiederherstellungspartition neu gestartet wird, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert. Wenn Sie diese Eingabeaufforderung überspringen, wird die Zurücksetzung fehlschlagen.
   
   > [!div class="mx-imgBorder"]
   > ![Abbildung, die die Option Geräte zurücksetzen in der App Einstellungen für Surface Hub zeigt.](images/sh-settings-reset-device.png)

   Nach Abschluss des Zurücksetzens startet Surface Hub das [erste Ausführungsprogramm](first-run-program-surface-hub.md) erneut. Wenn beim Zurücksetzen ein Problem besteht, wird der Surface Hub wieder auf das zuvor vorhandene Betriebssystemimage zurückgesetzt und dann der Willkommensbildschirm angezeigt.

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>Wiederherstellen von Surface Hub-Gerät aus der Cloud

Wenn der Surface Hub aus einem bestimmten Grund nicht mehr verwendet werden kann, können Sie ihn ohne Unterstützung durch den Microsoft Support weiterhin aus der Cloud wiederherstellen. Der Surface Hub kann ein neues Betriebssystemimage aus der Cloud herunterladen und dieses Image verwenden, um das Betriebssystem neu zu installieren.

Möglicherweise müssen Sie diese Art von Wiederherstellungsprozess unter den folgenden Umständen verwenden:

- [Surface Hub oder die zugehörigen Konten haben einen instabilen Zustand](#recover-a-surface-hub-in-a-bad-state)
- [Der Surface Hub ist gesperrt](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>Für **die Wiederherstellung aus dem Cloudprozess** ist eine verkabelte Verbindung erforderlich, die eine offene Internetverbindung bietet (keine Proxy- oder andere Authentifizierungsaufforderungen).

### <a name="recover-a-surface-hub-in-a-bad-state"></a>Wiederherstellen von Surface Hub in einem fehlerhaften Zustand

Wenn das Gerätekonto in einen instabilen Zustand gerät oder wenn beim Administratorkonto Probleme auftreten, können Sie die App Einstellungen verwenden, um den Cloudwiederherstellungsprozess zu starten. Sie sollten den Cloudwiederherstellungsprozess nur verwenden, [wenn](#reset-a-surface-hub) das Problem durch den Gerätezurücksetzungsprozess nicht behoben wird.

1. Wählen Sie auf Dem Surface Hub **einstellungen** &gt; **aktualisieren &** &gt; **Sicherheitswiederherstellung aus.**

2. Wählen **Sie unter Wiederherstellen aus der Cloud**die Option Jetzt neu starten **aus.**

   > [!div class="mx-imgBorder"]
   > ![Aus der Cloud wiederherstellen](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>Wiederherstellen eines gesperrten Surface Hub-Geräts

In seltenen Fällen kann für einen Surface Hub ein Fehler auftreten, während am Ende einer Sitzung Benutzer- und App-Daten bereinigt werden. In diesem Fall wird das Gerät automatisch neu gestartet und versucht den Vorgang erneut. Wenn dieser Vorgang jedoch wiederholt fehlschlägt, wird das Gerät automatisch gesperrt, um Benutzerdaten zu schützen. Zum Entsperren müssen Sie [das Gerät](#reset-a-surface-hub) zurücksetzen oder, falls dies nicht funktioniert, aus der Cloud wiederherstellen.

1. Suchen Sie den Netzschalter am unteren Rand von Surface Hub. Der Netzschalter befindet sich neben der Netzkabelverbindung. Weitere Informationen zum Netzschalter finden Sie im [Surface Hub Site Readiness Guide (PDF).](surface-hub-site-readiness-guide.md)

2. Während surface Hub den Willkommensbildschirm anzeigt, deaktivieren Sie den Surface Hub mithilfe des Netzschalters.

3. Verwenden Sie den Netzschalter, um den Surface Hub wieder zu aktivieren. Das Gerät startet und zeigt den Surface Hub-Logo-Bildschirm an. Wenn unter dem Surface Hub-Logo Spinnenpunkte angezeigt werden, verwenden Sie den Netzschalter, um den Surface Hub erneut zu deaktivieren.  

4. Wiederholen Sie Schritt 3 dreimal, oder bis der Surface Hub die Meldung "Automatische Reparatur vorbereiten" anzeigt. Nachdem diese Meldung angezeigt wurde, wird auf dem Surface Hub der Windows RE-Bildschirm angezeigt.
 
5. Wählen Sie **Zurücksetzen** aus. 

6. Wenn Sie zur Eingabe des BitLocker-Schlüssels aufgefordert werden, gehen Sie wie folgt vor:
   - Um die Informationen zu erhalten, die BitLocker auf dem Surface Hub schützt, geben Sie die BitLocker-Taste ein.
   - Wenn Sie die geschützten Informationen verwerfen möchten, wählen Sie Dieses Laufwerk überspringen aus.

7. Wählen Sie **Clouddownload aus.** 

   ![Clouddownload](images/recover-cloud-download.png)

   >[!IMPORTANT]
   >Wenn eine Fehlermeldung angezeigt wird, die angibt, dass **der Download nicht möglich ist,** wählen Sie **Abbrechen** und dann **erneut** zurücksetzen aus.

8. Wählen **Sie Vollständiges Bereinigen des Laufwerks aus.**
 
   ![Wiederherstellen und vollständig bereinigtes Laufwerk](images/recover-fully-clean-drive.png)

9. Sie werden **gefragt, ob Sie bereit sind, dieses Gerät zurückzusetzen?**. Wählen Sie **Zurücksetzen** aus. 
   
   ![Zurücksetzen wiederherstellen und bestätigen](images/recover-confirm-reset.png)

10. Der Download beginnt, und der Wiederherstellungsprozess gibt das **Zurücksetzen dieses Geräts an.**

    ![Wiederherstellung in Bearbeitung](images/recover-in-progress.png)

## <a name="contact-support"></a>Hilfe und Support zu Windows

Wenn Sie Fragen haben oder Hilfe benötigen, können Sie [eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)


## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub-Administratorhandbuch](surface-hub-administrators-guide.md)
