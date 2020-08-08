---
title: Installieren der Vorabversion des Windows10 Team2020-Updates
description: Das neueste Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update, ist jetzt verfügbar.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 79e6c35deba5c4635945c3b376a1069e3df324d9
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918915"
---
# Installieren der Vorabversion des Windows10 Team2020-Updates 

Das neueste Update des Surface Hub-Betriebssystems, **Windows 10 Team 2020-Update**, ist jetzt ohne zusätzliche Kosten für die Surface Hub 50-Zoll-und Surface Hub 2S 55-Zoll-Geräte aus dem [Windows-Insider-Programm](https://insider.windows.com)verfügbar. Das 84-Zoll-Surface-Hub-Modell wird in der endgültigen Version von Windows 10 Team 2020-Update unterstützt.

Das Windows 10-Team 2020-Update bietet wichtige Verbesserungen bei der Gerätebereitstellung und-Verwaltbarkeit zusammen mit den neuesten Windows 10-Features. Wenn Sie mehr über die Neuerungen erfahren möchten, lesen Sie den folgenden Blogbeitrag: [Neues Surface Hub-Betriebssystemupdate, das für die öffentliche Vorschau freigegeben wurde.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) Informationen zu bekannten Problemen finden Sie unten im Abschnitt "bekannte Probleme".
 
## Voraussetzungen

- Registrieren Sie sich beim [Windows-Insider-Programm](https://insider.windows.com/).
- Laden Sie das Windows 10 Team 2020 Update Preview Build aus dem Windows-Insider-Programm fast Channel herunter.
- Nachdem Sie den Preview-Build installiert haben, laden Sie die erforderlichen Firmware-Updates herunter. Hinweis: Firmware-Updates können nicht deinstalliert werden, auch wenn Sie sich entschließen, das Windows-Insider-Programm zu belassen.

## Vorbereiten des Surface Hub

Bevor Sie beginnen, überprüfen Sie, ob Ihr Surface Hub über die neuesten Updates von Windows Update verfügt, und stellen Sie sicher, dass Sie den BitLocker-Schlüssel speichern, der Ihrem Gerät zugeordnet ist.

**So suchen Sie manuell nach Updates:**

1. Öffnen Sie auf Surface Hub die **Einstellungen** , und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
2. Navigieren Sie zu **Update & Security**  >  **Windows Update** , und wählen Sie dann **auf Updates überprüfen**aus.

Weitere Informationen finden Sie unter [Verwalten von Windows-Updates auf Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).

**So speichern Sie den BitLocker-Schlüssel manuell:**

1. Legen Sie ein USB-Laufwerk in Surface Hub ein.
2. Öffnen Sie auf Surface Hub die **Einstellungen** , und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
3. Navigieren Sie zu **Update & Security**  >  **Recovery**.
4. Wählen Sie unter **BitLocker**die Option **Speichern**aus. Der BitLocker-Schlüssel wird in einer Textdatei auf dem USB-Laufwerk gespeichert.

Weitere Informationen finden Sie unter [Speichern des BitLocker-Schlüssels](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).
 
## Installieren des Windows 10 Team 2020 Update Preview-Builds

1. Öffnen Sie auf Surface Hub die **Einstellungen** , und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
2. Navigieren Sie zu **Datenschutz > Diagnose & Feedback** und **vollständig** für die Diagnosedaten. 
3. Navigieren Sie zu **Update & Security**  >  **Windows Insider-Programm** , und wählen Sie dann **Erste Schritte**aus.
4. Folgen Sie den Anweisungen, um sich als Windows-Insider zu registrieren, indem Sie entweder Ihr geschäftliches Konto (empfohlen) oder Ihr persönliches Microsoft-Konto verwenden. Detaillierte Informationen zu den Vorteilen der Registrierung für Ihr geschäftliches Konto finden Sie unter [registrieren für das Windows-Insider-Programm für Unternehmen](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
5. Wählen Sie unter **Insider-Einstellungen auswählen die**Option **schnell**aus.
6. Ermöglichen Sie es dem Surface Hub, den Preview-Build und die erforderlichen Firmware-Updates in den nächsten 3 bis 4 Tagen automatisch zu installieren. Das Gerät lädt die Updates während der täglichen [Wartung](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)automatisch herunter und installiert sie. Zum Beispiel:

- Im ersten Wartungsfenster beginnt Surface Hub mit dem Herunterladen des Preview-Builds von Windows Update.
- Während eines zweiten Wartungsfensters wird das Gerät neu gestartet, um das Update abzuschließen.
- Während eines dritten Wartungsfensters werden die erforderlichen Firmware-Updates vom Gerät heruntergeladen und installiert.

> [!IMPORTANT]
> Microsoft empfiehlt, den Surface Hub für 3-4 Tage zu reservieren, damit das Gerät die Installation des Preview-Builds und die erforderlichen Firmware-Updates abschließen kann. Wenn Sie das Gerät während dieses Vorgangs verwenden, können Sie Probleme mit der Grafik-, Audio-und Benutzeroberfläche auftreten.

### Wenn Sie sich für die manuelle Installation des Preview-Builds und der erforderlichen Firmware-Updates entscheiden:

1. Nachdem Sie sich beim Windows-Insider-Programm registriert haben, wechseln Sie zu **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows Update** , und wählen Sie auf **Updates überprüfen** aus, um den Preview-Build zu installieren.
2. Nachdem die Vorschau Erstellung installiert wurde (es kann bis zu 14 Stunden dauern), wählen Sie **jetzt neu starten** aus, um die Installation abzuschließen.
3. Wechseln Sie nach dem Neustart des Geräts zu **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows Update**, und wählen Sie auf **Updates überprüfen aus, um erforderliche Firmware-Updates zu installieren**.
4. Sobald die Firmware installiert ist, wählen Sie **jetzt neu starten**aus.

> [!WARNING]
> Möglicherweise werden Grafiken, Audio-und Benutzeroberflächen Probleme angezeigt, wenn Sie den Vorschau-Build installieren, ohne die erforderlichen Firmware-Updates zu installieren.

> [!NOTE]
> Wenn Sie das Windows-Insider-Programm verlässt und ihren Surface-Hub auf eine ältere Version des Betriebssystems zurücksetzen möchten, müssen Sie zunächst [Ihr Gerät zurücksetzen](https://docs.microsoft.com/surface-hub/device-reset-surface-hub). Anschließend müssen Sie das [erst Ausführungsprogramm](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) durchlaufen, um Ihr Gerät neu zu konfigurieren.
 

## Mehr erfahren

- [Bekannte Probleme: Windows 10 Team 2020-Update](surface-hub-2020-team-update-known-issues.md)
- [Neues Surface Hub-Betriebssystemupdate für die öffentliche Vorschau verfügbar.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Erste Schritte mit dem Windows-Insider-Programm für Unternehmen](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)