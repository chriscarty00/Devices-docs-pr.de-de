---
title: Installieren von Windows 10 Team 2020 Update Preview-Build
description: Das neueste Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update, ist jetzt verfügbar.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894111"
---
# Installieren von Windows 10 Team 2020 Update Preview-Build 

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
2. Navigieren Sie zu **Update & Security**  >  **Windows Insider-Programm** , und wählen Sie dann **Erste Schritte**aus.
3. Folgen Sie den Anweisungen, um sich als Windows-Insider zu registrieren, indem Sie entweder Ihr geschäftliches Konto (empfohlen) oder Ihr persönliches Microsoft-Konto verwenden. Detaillierte Informationen zu den Vorteilen der Registrierung für Ihr geschäftliches Konto finden Sie unter [registrieren für das Windows-Insider-Programm für Unternehmen](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
4. Wählen Sie unter **Insider-Einstellungen auswählen die**Option **schnell**aus.
5. Ermöglichen Sie es dem Surface Hub, den Preview-Build und die erforderlichen Firmware-Updates in den nächsten 3 bis 4 Tagen automatisch zu installieren. Das Gerät lädt die Updates während der täglichen [Wartung](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)automatisch herunter und installiert sie. Zum Beispiel:

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
 
## Bekannte Probleme: Windows 10 Team 2020 Update Preview-Build

### Probleme mit Grafik-, Audio-und Benutzeroberflächen 

Bei der Installation des Preview-Builds können verschiedene Grafiken und Probleme mit der Benutzeroberfläche auftreten, aber die erforderlichen Firmware-Updates werden später nicht sofort installiert. Microsoft plant, diese Probleme im Releasebuild des Windows 10 Team 2020-Updates zu beheben.

### Surface Hub 84-inch: Probleme mit Grafiken und Benutzeroberflächen

Wenn Sie den Preview-Build auf einem 84-Zoll-Gerät der ersten Generation installieren, können verschiedene Grafik-und Benutzeroberflächen Probleme auftreten. Der Surface-Hub 84-inch wird in der endgültigen Version von Windows 10 Team 2020-Update unterstützt.

### Die Anmeldung ist betroffen, wenn Richtlinien für den bedingten Zugriff angewendet werden.

- Beim Anmelden bei apps wie Microsoft Whiteboard tritt ein Fehler auf. Benutzer müssen sich zunächst über [meine Besprechungen und Dateien](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) über das Startmenü anmelden.

- Die Anmeldung schlägt fehl, wenn Ihr Benutzerkonto bei einem anderen Azure AD-Mandanten registriert ist als der von Surface Hub zu Azure AD Join verwendete.

Microsoft plant, diese Probleme im Releasebuild des Windows 10 Team 2020-Updates zu beheben.

### Windows Update fordert Sie auf, neue Treiber zu installieren, wenn keine verfügbar sind

Wenn Sie zu **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows Update** wechseln, nachdem Sie das Windows 10 Team 2020-Update und die erforderlichen Firmware-Updates installiert haben, wird möglicherweise die folgende Fehlermeldung angezeigt: 

- "Ein aktueller Treiber auf Ihrem PC ist möglicherweise besser als der Treiber, den wir installieren möchten. Wir versuchen weiterhin, zu installieren. " 

Dieser Fehler kann problemlos ignoriert werden. Microsoft untersucht dieses Problem aktiv.

### Surface Hub-Richtlinien können nicht über Bereitstellungspakete installiert werden

Bereitstellungspakete, die Richtlinien des Surface Hub Configuration Service Provider (CSP) verwenden, können nicht installiert werden. Verwenden Sie zurzeit Microsoft InTune oder einen anderen MDM-Anbieter (Mobile Device Management), um Surface Hub-Richtlinien anzuwenden. Microsoft plant, dieses Problem im Releasebuild des Windows 10 Team 2020-Updates zu beheben.

### Aufforderung zum vorzeitigen Entfernen des USB-Laufwerks während der ersten Ausführung

Wenn Sie ein Bereitstellungspaket zum Einrichten von Surface Hub während der ersten Ausführung verwenden, werden Sie aufgefordert, das USB-Laufwerk zu entfernen, bevor das Gerät die Konfigurationsdatei Surface Hub lesen kann. Ignorieren Sie die Nachricht, wenn Sie eine configure-Datei zum Einrichten Ihres Geräte Kontos verwenden. Microsoft untersucht dieses Problem aktiv.
 
### Proxyeinstellungen können während der ersten Ausführung nicht eingerichtet werden

Wenn Sie einen Proxy verwenden, um eine Verbindung mit dem Internet herzustellen, haben Sie möglicherweise während des ersten Ausführungs Programms eine begrenzte Internet Verbindung. Microsoft plant, dieses Problem im Releasebuild des Windows 10 Team 2020-Updates zu beheben.
 
### Wenn Sie Apps aus dem Microsoft Store herunterladen, wird ein Fehler angezeigt.

Wenn Sie eine APP aus dem Microsoft Store herunterladen möchten, wird eine Aufforderung zur Anmeldung angezeigt. Ein bekanntes Problem bewirkt, dass während der Anmeldung ein Fehler angezeigt wird, aber dies hat keinen Einfluss auf die Möglichkeit, apps herunterzuladen. Microsoft untersucht dieses Problem aktiv.

### Surface Hub 2S verliert zeitweilig eine WLAN-Verbindung

Versuchen Sie, das Gerät zu trennen und wieder einzustecken, oder verwenden Sie ein Ethernet-Kabel, um eine Verbindung mit dem Internet herzustellen. Microsoft untersucht dieses Problem aktiv.

### Surface Hub 2S wird zeitweilig nicht mehr aus dem Ruhezustand fortgesetzt

Surface Hub 2S kann zeitweise nicht vollständig aus dem Ruhezustand fortgesetzt werden und scheint auf einem Bildschirm mit dem Microsoft-Logo nicht mehr zu reagieren. Versuchen Sie, das Gerät zu trennen und wieder einzustecken. 

So verhindern Sie dieses Problem:

1. Öffnen Sie auf Surface Hub die **Einstellungen** , und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
2. Navigieren Sie zu **Surface Hub**  >  **Session & Power**. 
3. Verwenden Sie unter **Wenn das Gerät in den Ruhezustand wechselt, diese Energieeinstellung**, und wählen Sie **verbundener Standbymodus aus.**
4. Legen Sie unter **Wenn niemand anwesend ist, das Gerät in den Ruhezustand**, und wählen Sie **nie aus.**

Microsoft plant, dieses Problem in einem Firmware-Update vor der endgültigen Version des Windows 10 Team 2020-Updates zu beheben.

### Projektions Probleme, wenn die Connect-APP nicht angezeigt wird

- Wenn Sie ein Kabel zu Project to Surface Hub verwenden, funktioniert touchback nicht mehr, wenn Sie von der Connect-APP entfernt navigieren.
- Wenn Sie Project to Surface Hub mithilfe von Miracast projizieren, wird die drahtlose Verbindung kurz nach dem Verlassen der App "verbinden" gelöscht.

Microsoft untersucht diese Probleme aktiv.

### Skype for Business verwendet keinen Proxy für Mediendatenverkehr

Bei einigen Geräten, die einen Proxy verwenden, kann sich Skype for Business anmelden, aber nicht den Proxy Server für Mediendatenverkehr verwenden. Microsoft untersucht dieses Problem aktiv.

Wir laden Sie ein, ihre Einblicke und Vorschläge mit dem Microsoft-Support zu teilen.

## Mehr erfahren

- [Neues Surface Hub-Betriebssystemupdate für die öffentliche Vorschau verfügbar.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Erste Schritte mit dem Windows-Insider-Programm für Unternehmen](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)