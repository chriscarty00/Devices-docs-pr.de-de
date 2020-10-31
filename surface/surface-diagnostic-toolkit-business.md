---
title: Surface-Diagnosetoolkit für Unternehmen bereitstellen
description: In diesem Thema wird die Verwendung des Surface Diagnostics Toolkit for Business erläutert.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145960"
---
# Surface-Diagnosetoolkit für Unternehmen bereitstellen

Mit dem Microsoft Surface Diagnostics Toolkit for Business (Unternehmen) können IT-Administratoren Hardware-, Software-und Firmware-Probleme mit Surface-Geräten schnell untersuchen, beheben und beheben. Darüber hinaus können Sie eine Reihe von Diagnosetests und Software Reparaturen durchführen, um Einblicke in die Geräte Integrität und Anleitungen für das Beheben von Problemen zu erhalten. 

Im speziellen bietet Ihnen das Unternehmen in der folgenden Funktion die folgenden Möglichkeiten:

- [Passen Sie das Paket an.](#preparing-the-sdt-package-for-distribution)
- [Führen Sie die App mithilfe von Befehlen aus.](surface-diagnostic-toolkit-command-line.md)
- [Führen Sie mehrere Hardwaretests aus, um Probleme zu beheben.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Generieren von Protokollen zum Analysieren von Problemen](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Ausführlicher Bericht zum Vergleich von Device vs optimaler Konfiguration](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Primäre Szenarien und Ressourcen zum herunterladen 

Laden Sie die in der folgenden Tabelle aufgelisteten Komponenten herunter, um Sie zu Unternehmen.


Modus |  Primäre Szenarien | Herunterladen | Mehr erfahren
--- | --- | --- | ---
Desktopmodus |  Unterstützen Sie Benutzer beim Ausführen von "auf Ihren Surface Devices", um Probleme zu beheben.<br>Erstellen Sie ein benutzerdefiniertes Paket, das auf einem oder mehreren Oberflächen-Geräten bereitgestellt werden soll, sodass Benutzer bestimmte Protokolle zum Sammeln und analysieren auswählen können. | Verteilbares MSI-Paket:<br>Microsoft Surface Diagnostics Toolkit für Business-Installationsprogramm<br>[Surface-Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) | [Verwenden des Surface Diagnostic Toolkit im Desktopmodus](surface-diagnostic-toolkit-desktop-mode.md)
Befehlszeile |  Direkte Problembehandlung von Surface Devices Remote ohne Benutzerinteraktion mithilfe von Standardtools wie Configuration Manager Sie umfasst die folgenden Befehle:<br>`-DataCollector` sammelt alle Protokolldateien<br>`-bpa` führt die Integritäts Diagnose mithilfe von Best Practice Analyzer aus.<br>`-windowsupdate` überprüft Windows Update auf fehlende Firmware-oder Treiberupdates.<br>`-warranty` überprüft die Gewährleistungsinformationen. <br><br>| App für die APP-Konsole:<br>Microsoft Surface Diagnostics-App-Konsole<br>[Surface-Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) | [Ausführen des Surface Diagnostic Toolkit mithilfe von Befehlen](surface-diagnostic-toolkit-command-line.md)

## Unterstützte Geräte 

Für Unternehmens-Devices (Surface 3 und höher) werden die folgenden Geräte unterstützt:

- Surface Laptop go
- DGM-Buch 3
- Surface Go 2
- Surface Pro X
- Surface Pro 7
- Surface Laptop 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Surface Go mit LTE
- Surface Book 2
- Surface Pro mit LTE Advanced (Modell 1807)
- Surface Pro (Modell 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface3
- Surface Pro 3

## Installieren des Surface Diagnostics Toolkit for Business

So erstellen Sie ein unstrukturiertes Paket, das Sie an Benutzer in Ihrer Organisation verteilen können:

1. Mit dem Administrator Konto können Sie sich bei Ihrem Surface-Gerät anmelden.
2. Laden Sie das Windows Installer-Paket (. msi) auf der [Seite Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) herunter, und kopieren Sie es an eine bevorzugte Position auf dem Surface-Gerät, beispielsweise Desktop.
3. Der Assistent für die strukturierte Einrichtung wird angezeigt, wie in Abbildung 1 dargestellt. Klicken Sie auf **Weiter**. 

    >[!NOTE]
    >Wenn der Setup-Assistent nicht angezeigt wird, stellen Sie sicher, dass Sie beim Administrator Konto auf Ihrem Computer angemeldet sind. 

    ![Willkommen beim Setup-Assistenten für Surface Diagnostics Toolkit](images/sdt-1.png)

    *Abbildung1. Setup-Assistent für Surface Diagnostics Toolkit*

4. Klicken Sie auf **weiter**, um den Endbenutzer-Lizenzvertrag (EULA) zu akzeptieren, wenn der Assistent für die strukturierte Installation angezeigt wird.

5. Ändern Sie auf dem Bildschirm Installationsoptionen den Standard Installationsspeicherort, falls gewünscht. 
6. Wählen Sie unter Setuptyp die Option **erweitert**aus. 

    >[!NOTE]
    >Die Standardoption ermöglicht es Benutzern, das Diagnosetool direkt auf dem Surface-Gerät auszuführen, vorausgesetzt, dass Sie mit einem Administrator Konto bei Ihrem Gerät angemeldet sind. 
    
     ![Installationsoptionen: erweitert](images/sdt-install.png)

7. Klicken Sie auf **weiter** , und klicken Sie dann auf **Installieren**. 

## Installieren über die Befehlszeile
Wenn Sie möchten, können Sie an einer Eingabeaufforderung die Option "unstrukturierte" installieren und ein benutzerdefiniertes Flag einrichten, um das Tool im Administratormodus zu installieren. In der folgenden Option werden die Flags für die Installation angezeigt:

- `SENDTELEMETRY` sendet Telemetrie-Daten an Microsoft. Das Flag akzeptiert `0` für deaktiviert oder `1` für aktiviert. Der Standardwert lautet " `1` Telemetrie senden".
- `ADMINMODE` konfiguriert das Tool, das im Administratormodus installiert werden soll. Das Flag akzeptiert den `0` Client Modus oder den `1` IT-Administrator Modus. Der Standardwert lautet `0`.

### So installieren Sie "von" in der Befehlszeile:

1. Öffnen Sie eine Eingabeaufforderung, und geben Sie Folgendes ein:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Beispiel:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Suchen von "nach" auf Ihrem Surface-Gerät

Sowohl die Sonderanwendungen als auch die APP-Konsole sind unter installiert `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Zusätzlich zu der exe-Datei installiert die Datei eine JSON-Datei und eine admin.dll-Datei (modules\admin.dll), wie in Abbildung 2 dargestellt.

![Liste der im Datei-Explorer installierten Dateien](images/sdt-2.png)

*Abbildung2. Dateien, die von "unstrukturierte" installiert wurden*

## Vorbereiten des unstrukturierten Pakets für die Verteilung

Durch das Erstellen eines benutzerdefinierten Pakets können Sie das Tool auf bestimmte bekannte Probleme ausrichten.

1. Klicken Sie auf **Start > ausführen**, geben Sie **Surface** ein, und klicken Sie dann auf **Surface Diagnostics Toolkit for Business**. 
2. Wenn das Tool geöffnet wird, klicken Sie auf **benutzerdefiniertes Paket erstellen**, wie in Abbildung 3 dargestellt.

    ![Option ' benutzerdefiniertes Paket erstellen '](images/sdt-3.png)

    *Abbildung3. Erstellen eines benutzerdefinierten Pakets*

### Einstellungen für Sprache und Telemetrie

  Beim Erstellen eines Pakets können Sie Spracheinstellungen auswählen oder das Senden von Telemetrie-Informationen an Microsoft deaktivieren. Standardmäßig sendet die datentelemetrie an Microsoft, die zur Verbesserung der Anwendung in Übereinstimmung mit den [Datenschutzbestimmungen von Microsoft](https://privacy.microsoft.com/privacystatement)verwendet wird. Wenn Sie ablehnen möchten, deaktivieren Sie das Kontrollkästchen beim Erstellen eines benutzerdefinierten Pakets, wie unten dargestellt. Oder deaktivieren Sie das Kontrollkästchen **Telemetrie an Microsoft senden** auf der Seite " **Installationsoptionen** " während der Einrichtung des Programms. 

>[!NOTE]
>Diese Einstellung hat keinen Einfluss auf die minimale Telemetrie, die auf Microsoft-Servern automatisch gespeichert wird, wenn Tests und Reparaturen ausgeführt werden, bei denen eine Internet Verbindung erforderlich ist, beispielsweise Windows Update und Software Reparatur, oder Feedback über die Schaltflächen Lächeln oder missbilligen in der APP-Symbolleiste bereitgestellt wird. 


![Auswählen von Sprach-und Telemetrie-Einstellungen](images/sdt-4.png)

*Abbildung 4. Auswählen von Sprach-und Telemetrie-Einstellungen*


### Windows Update-Seite

Wählen Sie die für Ihre Organisation geeignete Option aus. Die meisten Organisationen mit mehreren Benutzern wählen in der Regel aus, um Updates über Windows Server Update Services (WSUS) zu erhalten, wie in Abbildung 5 zu sehen ist. Wenn Sie lokale Windows Update-Pakete oder WSUS verwenden, geben Sie den Pfad entsprechend ein. 

![Windows Update-Option auswählen](images/sdt-5.png)

*Abbildung5. Windows Update-Option*

### Seite "Software Reparatur"

Auf diese Weise können Sie die Option zum Ausführen von Software Reparatur Updates auswählen oder entfernen. 

![Option "Software Reparatur" auswählen](images/sdt-6.png)

*Abbildung6. Option für Software Reparatur*

### Sammeln von Protokollen und Speichern der Paketseite

Sie können auswählen, dass eine große Auswahl von Protokollen für Anwendungen, Treiber, Hardware und das Betriebssystem ausgeführt werden soll. Klicken Sie auf den entsprechenden Bereich, und wählen Sie im Menü verfügbare Protokolle aus. Anschließend können Sie das Paket auf einem Softwareverteilungspunkt oder einem entsprechenden Speicherort speichern, auf den Benutzer zugreifen können. 

![Auswählen von Protokolloptionen](images/sdt-7.png)

*Abbildung7. Protokolloption und Paket speichern*

## Nächste Schritte

- [Surface-Diagnosetoolkit für Unternehmen im Desktopmodus verwenden](surface-diagnostic-toolkit-desktop-mode.md)
- [Verwenden von Surface Diagnostics Toolkit for Business mithilfe von Befehlen](surface-diagnostic-toolkit-command-line.md)

## Änderungen und Updates

### Version 2.124.139.0

Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:

- Nahtloser integrierter Support
- Speichern aller Testergebnisse
- Überprüfen, ob das Bild Benutzerdefiniert erstellt wurde
- Einbeziehen von Warnungen aus dem Geräte-Manager
- Dock-Firmware-Version
- Kennzeichnen von Festplatten als potenzielle Fehler im Speichertest
- Link "Store entfernen" 

### Version 2.121.139
*Veröffentlichungsdatum: Juli 31 2020*<br>
Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:

- Nahtlose Unterstützung
- Fehlerbehebungen

### Version 2.94.139.0
*Veröffentlichungsdatum: 11. Mai 2020*<br>
Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:

- Möglichkeit, Windows Update zu überspringen, um eine Hardwareüberprüfung durchzuführen.
- Möglichkeit zum Empfang von Benachrichtigungen über die neueste Version des Updates
- Surface Go 2
- DGM-Buch 3
- Statusanzeige anzeigen


### Version 2.43.139.0
*Veröffentlichungsdatum: 21. Oktober 2019*<br>
Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:

- Surface Pro 7
- Surface Laptop 3

### Version 2.42.139.0
*Veröffentlichungsdatum: 24. September 2019*<br>
Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen: 
- Möglichkeit zum Herunterladen von Hardwareberichten
- Möglichkeit, den Microsoft-Support direkt über das Tool zu kontaktieren. <br>

### Version 2.41.139.0
*Veröffentlichungsdatum: Juni 24, 2019*<br>
Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen: 
- Informationen zu Treiberversionen, die in Protokollen und Berichten enthalten sind.
- Möglichkeit, Feedback zur APP bereitzustellen.<br>


### Version 2.36.139.0
*Veröffentlichungsdatum: April 26, 2019*<br>
Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen: 
- Erweiterte Setup Option zum Entsperren von Administratorfunktionen über die Benutzeroberfläche des Installationsprogramms, ohne dass die Befehlszeilenkonfiguration erforderlich ist.
- Verbesserungen bei der Barrierefreiheit
- Einstellungen für die Oberflächen Helligkeitssteuerung, die in Protokollen enthalten sind.
- Link zum Kompatibilitäts Support für externe Monitore im Berichts-Generator
