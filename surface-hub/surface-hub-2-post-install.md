---
title: Windows 10 für Surface Hub 2-Konfiguration nach der Installation
description: Windows 10 für Surface Hub 2-Konfiguration nach der Installation
keywords: Surface Hub, Windows 10, Desktop, Installation, Konfiguration
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: d6a1cdb2cac01b48c80e0fa4b7ccb6d3bcdb76ac
ms.sourcegitcommit: 6618e8fe05628aa8b17654584657eff0f784dbfd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986508"
---
# Windows 10 für Surface Hub 2-Konfiguration nach der Installation

**Gilt für: Surface Hub 2S** 

Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um apps und Einstellungen auf dem Surface Hub 2 zu konfigurieren. Diese Schritte werden empfohlen, um die optimale Benutzerfreundlichkeit bei der Verwendung dieses personalisierten Touchscreen-und Stift Computers zu gewährleisten.

Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.

## Konfigurieren von Systemeinstellungen

1. Anmelden mit einem Konto, das über lokale Administratorrechte auf dem Gerät verfügt.  
    - Auf Azure AD-verbundenen Geräten wird der Benutzer, der die Azure AD-Verknüpfung ausführt, automatisch der lokalen Administratorgruppe hinzugefügt. Azure AD Global Administrators und Azure AD Devices-Administratoren sind [auch lokale Administratoren](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin). 
    - Sie können **net localgroup-Administratoren** an einer Eingabeaufforderung eingeben, um die Konten aufzulisten, die über lokale Administratorrechte verfügen.
2. Benennen Sie das Gerät mit einem Anzeigenamen um, beispielsweise: **username-SHub-Desktop**.
3. Wählen Sie **Start**  >  **Einstellungen**  >  -**Konten**  >  **Synchronisieren Sie Ihre Einstellungen** aus, und deaktivieren Sie die **Synchronisierungseinstellungen** . 
    - Die hier verwendeten Einstellungen dienen dazu, die optimale Touchscreen-Bildschirmoberfläche zu aktivieren, und daher möchten Sie möglicherweise keine anderen Geräte synchronisieren.
4. Starten Sie das Gerät neu.

## Aktivieren der Bildschirmtastatur und des Touchpads

1. Tippen und halten oder klicken Sie mit der rechten Maustaste auf die Taskleiste, und wählen Sie dann die Schaltfläche **Bildschirmtastatur anzeigen** und die **Schaltfläche Touchpad anzeigen**aus. 
    - Die Bildschirmtastatur ist für die direkte Benutzereingabe hilfreich, und das virtuelle Touchpad hilft bei der präzisen Auswahl, dem Hovern des Bildschirms oder als Alternative zum Tippen und halten für das Klicken mit der rechten Maustaste. 
    - Nachfolgend sehen Sie ein Beispiel.

     ![Touch-Einstellungen](images/touch.png)

2. Konfigurieren Sie die Bildschirmtastatur auf QWERTY und unverankert.
    1. Wählen Sie das Tastatursymbol in der Taskleiste aus, um die Bildschirmtastatur anzuzeigen.
    2. Wählen Sie auf der Bildschirmtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.
    3. Wählen Sie in der obersten Zeile den neben letzten Tastaturtyp aus, um die QWERTY-Funktion zu aktivieren, und die letzte Option in der zweiten Zeile, um das Floating zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist. Weitere Informationen finden Sie in den folgenden Beispielen.

     ![Tastatureinstellungen](images/kbd.png)

3. Konfigurieren Sie die Einstellungen für die Soft-Tastatur.
    1. Suchen nach und Öffnen von **Eingabeeinstellungen** 
    2. Aktivieren Sie alle Optionen unter Rechtschreibung, Eingabe und Bildschirmtastatur.


Das folgende Beispiel zeigt das Trackpad, das nützlich ist, um zu navigieren und Optionen auszuwählen. Die Bildschirmtastatur wird verwendet, um den Microsoft Store zu durchsuchen:

![Verwenden des Trackpads](images/store.png)

## Konfigurieren der Bluetooth-Tastatur und-Maus (optional)

Schließen Sie eine Tastatur und Maus an, wenn Sie das Gerät als Ihr primäres Windows-Gerät verwenden, oder verwenden Sie es häufig für die Eingabe oder die Genauigkeit der Arbeit.

Wenn sich Ihr Surface-Hub-Gerät in der Nähe eines PCs befindet, können Sie die [Maus ohne Rahmen](https://aka.ms/mm) verwenden, um nahtlos zwischen dem Surface-Hub und dem PC zu wechseln. Weitere Informationen finden Sie unter [Microsoft-Download aus der Garage: Maus ohne Rahmen](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).

## OneDrive for Business

Verwenden Sie [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) , um Tools, Protokolle und andere Dateien auf einfache Weise zwischen allen ihren Arbeitsgeräten freizugeben.

- Mit OneDrive können Sie Ihre Arbeitsdateien zwischen ihren Laptops, dem Surface Hub-Desktop und ihren von InTune verwalteten mobilen Geräten freigeben. Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.
- Wenn Sie die Größe der Surface-Hub-SSD (128 GB) berücksichtigen und OneDrive auf Ihrem Surface Hub-Desktop Gerät konfigurieren, stellen Sie sicher, dass die Standardkonfiguration darin besteht, die Dateien online zu speichern und während der Verwendung Dateien herunterzuladen.

Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung **files on-Demand** fest, um **Speicherplatz zu sparen und während der Verwendung Dateien herunterzuladen**. Weitere Informationen finden Sie unter [Abfragen und Einrichten von Dateien auf Anforderungsstatus in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).

![OneDrive-Einstellungen](images/onedrive.png)

> [!NOTE]
> Sie können diese Schritte auch wiederholen, um eine persönliche OneDrive zu konfigurieren, aber achten Sie darauf, den Speicherplatz zu sparen und nur Dateien herunterzuladen, wenn Sie Sie benötigen.

## SharePoint und Teams

SharePoint-und Teams-Kanaldateien können mithilfe des OneDrive-Synchronisierungsmoduls auch lokal mit ihren Desktopgeräten wie Laptops und Surface Hubs synchronisiert werden.

So synchronisieren Sie interne Unternehmensdateien mit der OneDrive-Synchronisierungs-App auf Ihr lokales Laufwerk:

1. Wechseln Sie zu einer SharePoint-Website, und navigieren Sie zum Dokumentverzeichnis auf oberster Ebene für Dateien, die Sie auf Ihrem lokalen Gerät anzeigen oder bearbeiten möchten.
2. Wählen Sie auf der Schaltfläche " **Synchronisieren** " oben im SharePoint-Menüband aus.
3. Wählen Sie auf **Öffnen** im Popupfenster aus, auf dem **diese Website versucht, Microsoft OneDrive zu öffnen**.
4. Überprüfen Sie, ob die SharePoint-Dateien mit Ihrem lokalen Laufwerk synchronisiert werden, indem Sie auf das OneDrive-Symbol unten rechts in der Taskleiste klicken.
5. Überprüfen Sie, ob die Konfiguration so eingestellt ist, dass die Dateien online bleiben, und laden Sie die Dateien nur während der Verwendung herunter.
    1. Öffnen Sie den Datei-Explorer.
    2. Navigieren Sie zu und wählen Sie mit der rechten Maustaste auf dem **Microsoft \ \<SharePoint Document Folder Name\> **aus.
    3. Wählen Sie **Speicherplatz freigeben**aus.
    4. In der Spalte Status wird der Status von Dateien und Ordnern angezeigt. Weitere Informationen finden Sie unter [Synchronisieren von SharePoint-Dateien mit dem OneDrive-synchronisierungsclient](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).
6. Teams-Kanaldateien werden auf SharePoint-Websites mit allen gleichen SharePoint-Dokumentfunktionen wie Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten gespeichert. So synchronisieren Sie Teams-Kanaldateien:
    1. Navigieren Sie zu dem Interessenbereich "Teams", und wählen Sie oben auf der Registerkarte " **Dateien** " aus. Wählen Sie dann **Synchronisieren**aus. Die Dateien werden synchronisiert und werden im Datei-Explorer unter **Desktop \ Microsoft \ \<name of the Teams Channel\> **angezeigt.
    2. Verwenden Sie dasselbe Verfahren, das Sie zum Synchronisieren von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern, und laden Sie Sie nur herunter, wenn Sie Sie verwenden, indem Sie im Datei-Explorer auf den Namen des Teams-Kanals tippen und halten oder mit der rechten Maustaste darauf klicken und dann **Platz freigeben**auswählen.

## Koppeln des Surface Hub-Stifts

So koppeln Sie das Stift Gerät:

1. Wählen Sie **Start**  >  **Settings**  >  **Devices**aus.
2. Wählen Sie **Bluetooth oder anderes Gerät hinzufügen**aus.
3. Wählen Sie **Bluetooth**aus.
4. Entfernen Sie die Stift-Endstück-Taste und schütteln, um die Batterie Verbindung zu trennen.
5. Setzen Sie die Kappe wieder ein, und halten Sie die Kappe gedrückt, bis die Kopplungs-LED blinkt.
6. Wählen Sie auf den Surface Hub Bluetooth-Einstellungen die Option **Surface Hub 2 Pen**aus.
7. Führen Sie den Kopplungsvorgang aus. 
8. Wenn die Kopplung nicht erfolgreich ist, versuchen Sie, den Stift erneut zu koppeln. Falls erforderlich, starten Sie das Gerät neu, und versuchen Sie es dann erneut.

## Kamerakonfiguration

Sie können die Kamera oben oder an jeder Seite des Geräts montieren. Montieren Sie die Kamera in einer Position, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktop-Standfuß statt mit einem Wagen verwenden oder sich in der Nähe des Hubs befinden. Da die Kamera nicht automatisch gedreht wird, benötigen Sie eine 2mm-Sechskant-Taste, um die Kamera manuell zu drehen. 

Weitere Informationen dazu, wie Sie die Kamera seitlich montieren und die Kamera manuell drehen können, finden Sie unter [Surface Hub 2S-Kameralinsen Ausrichtung](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).

## Windows Hello-Konfiguration

Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen. Der Surface Hub 2-Fingerabdruckleser-Zubehör kann an einen beliebigen USB-C-Anschluss des Geräts angeschlossen werden. 

> <i>Der Surface Hub 2-Fingerabdruckleser steht demnächst zum Kauf zur Verfügung. Bitte besuchen Sie diese Seite, um weitere Informationen zu erhalten, einschließlich des Kaufs.</i>

Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie **Start**  >  **Einstellungen**  >  **Accounts**  >  für die**Anmeldeoptionen**  >  **Windows Hello Fingerabdruck** aus, um Ihren Fingerabdruck einzuschreiben.

Verwenden Sie ein Windows Hello Certified-Gerät für die Flächen Erkennung. Die Surface Hub 2S-Kamera unterstützt keine Windows Hello Face-Erkennung.

## Aktivieren eines Symbol Symbols für den Sperrbildschirm auf der Taskleiste

So fügen Sie der Taskleiste ein Symbol hinzu, das eine Touchscreen-Sperre ähnlich der Windows-L-Tastenkombination ermöglicht: 

1.  Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen Sie **neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**  >  **weiter**aus.
2.  Geben Sie einen Namen für die Verknüpfung ein, beispielsweise " **mein PC sperren**", und wählen Sie dann **Fertig stellen**aus.
3.  Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften**aus. Geben Sie auf der Registerkarte **Verknüpfung** im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll, Lock Workstation**
4.  Wählen Sie die Schaltfläche **Symbol ändern** aus, und navigieren Sie zu **C:\Windows\System32\imageres.dll** , und wählen Sie ein Symbol aus, das Sie verwenden möchten. 
5. Siehe hierzu das folgende Beispiel:

    ![Wählen Sie ein Symbol aus.](images/lock.png)
6.  Wählen Sie **OK** aus, um die Verknüpfung zu speichern.
7.  Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die Verknüpfung, und wählen Sie **an Taskleiste anheften**aus.

## Anwendungen

### Aktualisieren von installierten apps

So aktualisieren Sie alle installierten Store-Apps:

1. Öffnen Sie die Microsoft Store-App, und wählen Sie in der oberen rechten Ecke die Option Weitere Auslassungszeichen **anzeigen** aus.
2. Wählen Sie **Downloads und Updates**aus.
2. Wählen Sie **Updates abrufen**aus.

### Microsoft Whiteboard

So installieren Sie das Microsoft Whiteboard:

1. Wählen Sie unten rechts in der Taskleiste das Symbol frei Hand Arbeitsbereich von **Windows Ink Workspace** aus ![ ](images/ink.png) , und laden Sie **Whiteboard**herunter.

Sie können Whiteboard auch über den Microsoft Store installieren:

1. Öffnen Sie die Microsoft Store-App, und suchen Sie nach **Whiteboard**.
2. Wählen Sie " **Nein** ", wenn Sie sich anmelden und geräteübergreifend verwenden.
3. Anheften des Whiteboards an die Taskleiste

### Surface-App

1. Suchen Sie im Microsoft Store nach **Surface**.
2. Setzen Sie den **verfügbaren** Filter auf **alle Geräte**.
3. Installieren Sie die **Surface** -app. Dies sollte die erste aufgelistete APP sein. Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die APP installieren zu können.
4. Anheften Sie die **Surface** -APP an die Taskleiste.

### Snip-& Skizze

1. Öffnen Sie die APP **Snip & Sketch** , und fixieren Sie Sie an die Taskleiste.
2. Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen**aus.
3. Aktivieren Sie in **Einstellungen** **die Option automatisch in Zwischenablage kopieren**, **snips speichern**und **mehrere Fenster** (optional).

### Microsoft Office

1. Öffnen Sie das [Office-Portal](https://portal.office.com/account#installs) , und installieren Sie die gewünschten Anwendungen.
2. Anheften Sie die gewünschten Office-Anwendungen an die Taskleiste.
3. Wenn Outlook installiert ist, müssen Sie Outlook Ost so einstellen, dass nur der letzte zwei Wochen-Cache gespeichert wird. Dadurch werden die Datenträgernutzung und die Einrichtungszeit erheblich reduziert.
    - Wählen Sie **Datei**  >  **Kontoeinstellungen** aus, und wählen Sie Ihr Konto aus.
    - Wählen Sie **ändern** aus, und legen Sie den Schieberegler für die **Verwendung des Exchange-Cache-Modus** auf 14 Tage.

### Microsoft Teams

1. Laden Sie [Microsoft Teams](https://teams.microsoft.com/downloads)herunter, und installieren Sie Sie.
2. Konfigurieren Sie die Einstellungen für die automatische Startanwendung (optional).
3. Anheften von Teams an die Taskleiste.
4. Sie können die Benachrichtigungen für Teams auf dem Gerät reduzieren, um Ablenkungen zu vermeiden (optional).

  ![Teams-Benachrichtigungen](images/teams.png)

### Connect-App

> [!IMPORTANT]
> In Windows 10, Version 2004 und höher, ist die Connect-App für drahtlose Projektion unter Verwendung von Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung. Wenn Sie die APP installieren möchten, wählen Sie unter **Einstellungen**  >  **apps**  >  **optionale Features**  >  **ein Feature hinzufügen** aus, und installieren Sie dann die **drahtlose Anzeige** -app.

1. Suchen Sie nach **Connect**.
2. Öffnen Sie die APP, und schließen Sie Sie dann (**Project auf diesem PC** funktioniert möglicherweise nicht, wenn die APP mindestens einmal ausgeführt wurde).
3. Tippen und halten oder klicken Sie mit der rechten Maustaste, um die Taskleiste zu anheften.
4. Suchen Sie nach **Projektions Einstellungen**.
5. **Wenn Sie unter Windows-und Android-Geräten auf diesen PC projizieren können, wenn Sie sagen, dass es in Ordnung ist**, wählen Sie **überall verfügbar** aus, wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet. Andernfalls können Sie **überall in sicheren Netzwerken verfügbar**wählen.
6. Wählen Sie unter **Projekt auf diesem PC anfordern**die Option **nur erstes Mal**aus.
7. Wählen Sie unter **PIN für Kopplung anfordern**die Option **nie**aus.

Empfohlene Konfiguration, wenn Sie sich nicht im Unternehmensnetzwerk befinden:

  ![Einstellungen zu Hause](images/project1.png)

Empfohlene Konfiguration im Unternehmensnetzwerk:

  ![Einstellungen bei der Arbeit](images/project2.png)

### Ihr Smartphone

Die APP **Ihres Telefons** wird unter Windows 10 standardmäßig installiert. Wenn Sie nicht vorhanden ist, können Sie Sie auch aus dem Windows Store installieren.

Informationen zum Einrichten der App finden Sie unter so wird es [gemacht: Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten zwischen Ihrem PC und Smartphone](https://www.windowscentral.com/how-set-your-phone-windows-10). Weitere Informationen finden Sie unter [Beheben häufig auftretender Probleme mit ihrer Telefon-APP unter Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).

### Super Fancy Zones

**Super fancy Zones** hilft Benutzern beim Anordnen von Windows zum Maximieren von Bildschirm Immobilien. Sie ist jetzt in [PowerToys](https://github.com/microsoft/PowerToys/releases) auf GitHub enthalten.

### Edge Chrom-Browser

Laden Sie den neuen [Edge Chrom-Browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL)herunter, und installieren Sie ihn.

## Zusätzliche Einstellungen

### Stift Schwanz auswählen, um Whiteboard zu starten

1. Suchen Sie nach **Stift** , und wählen Sie **Stift & Windows Ink-Einstellungen**aus.
2. **Klicken Sie** am unteren Rand der Seite unter **Stifttasten Kombinationen** auf **Microsoft Whiteboard**auswählen. 

### Energie-und Ruhezustandseinstellungen

1. Wählen Sie **Start**  >  **Einstellungen**  >  **System**  >  **Power & Sleep**aus.
2. Stellen Sie den Power Mode-Schieberegler auf **optimale Leistung**ein.
3. Konfigurieren Sie die Werte für Bildschirm und Ruhemodus nach Ihren Wünschen.

### Bildschirmschoner

1. Suchen Sie nach **dem Sperrbildschirm** , und öffnen Sie die Einstellungen für den **Sperrbildschirm**.
2. Konfigurieren Sie die Einstellungen für das **Bildschirm Timeout** und die **Bildschirmschonereinstellungen** nach Ihren Wünschen.

### Speicheroptimierung

Der Surface Hub 2 verfügt über eine 128 GB-SSD für den lokalen Speicher, daher ist es notwendig, die Verwendung von Speicher Sparmaßnahmen während der normalen Nutzung zu überdenken.  So konfigurieren Sie den Speicher Sinn:

1.  Suchen Sie nach den **Speichereinstellungen**, die unter **System Einstellungen**gefunden werden.
2.  Wählen Sie unter **Einstellungen**die Option **Speicher Sinn aktivieren** aus, um die Seite **Speicher** Einstellungen zu öffnen.
3.  Stellen Sie den Speicher Sinn auf **ein**.
4.  Wählen Sie **Speicher Sinn konfigurieren aus, oder führen Sie es jetzt** aus, und konfigurieren Sie die Einstellungen so, dass Dateien so weit wie möglich online bleiben (aufgrund des geringen Festplattenspeichers).

Empfohlene Einstellungen:
- Führen Sie den Speicher Sinn = jeden Tag aus.
- Löschen Sie temporäre Dateien, die meine apps nicht verwenden = alle 14 Tage (mindestens).
- Löschen Sie Dateien im Ordner "Downloads", wenn Sie über mehr als = 30 Tage vorhanden sind.
- OneDrive: Inhalt wird online – nur, wenn er nicht mehr als = 30 Tage geöffnet ist.

### Tabletmodus

Aktivieren Sie den Tablet-Modus, wenn dies für Barrierefreiheitsanforderungen erforderlich ist.

### Energieverwaltung

> [!NOTE]
> Bevor Sie das folgende Verfahren ausführen, erkundigen Sie sich bei Ihrer IT-Abteilung, ob ein Surface Hub 2S-Gerät aus der globalen Energieverwaltungsrichtlinie ausgeschlossen werden soll. Einige Energieverwaltungseinstellungen können die Anwesenheits Erkennungsfunktion deaktivieren.

1. Suchen Sie nach **Software Center** , und öffnen Sie Sie.
2. Wählen Sie im Navigationsbereich **Optionen** aus.
3. Erweitern Sie den Abschnitt **Energieverwaltung** , und aktivieren Sie das Kontrollkästchen **Energieeinstellungen von meiner IT-Abteilung auf diesem Computer nicht anwenden**.

  ![Software Einstellungen](images/soft-cntr.png)

### Sound Einstellungen

1. Suchen Sie nach **Sounds-Einstellungen** , und öffnen Sie diese Seite.
2. Wählen Sie auf der rechten Seite **Sound Control Panel** aus, und klicken Sie auf die Registerkarte **Sounds** .
3. Klicken Sie unter **Programmereignisse** auf **Gerät verbinden** und **Gerät trennen** mit **keiner**.

### Benachrichtigungen zum Schweigen

1. Suchen Sie nach **Fokus Unterstützung** , und öffnen Sie diese Seite.
2. Wählen Sie **nur Erinnerungen**aus. Dadurch werden keine Konstanten Benachrichtigungs Flyouts vermieden.

### Datenträgerbereinigung

1. Suchen Sie nach **Datenträgerbereinigung** , und öffnen Sie diese APP.
2. Wählen Sie unter **zu löschende Dateien**die Dateien aus, die Sie löschen möchten. 
3. Wählen Sie auch **Systemdateien bereinigen**aus.

## Fertig stellen und überprüfen

1. Suchen Sie nach allen Windows-Updates, und installieren Sie Sie.
2. Aktualisieren von Gruppenrichtlinien
    1. Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate force/Boot/Wait: 0**ein.
3. Starten Sie das Gerät neu.
4. Überprüfen der Taskleisten-apps
    - Connect-App
    - Symbol "Sperren"
    - Snip-& Skizze
    - Teams (falls zutreffend)
    - Office-Apps (falls zutreffend)
    - Surface-App
    - Whiteboard
5. Überprüfen Sie die Anwesenheitserkennung.
    - Die Anwesenheitserkennung ist ein grünes Symbol in der Taskleiste.
6. Überprüfen Sie, ob das projizieren auf diesen PC mit der Connect-App aktiviert ist (die Anwendung muss vor dem Herstellen der Verbindung nicht ausgeführt werden).
7. Überprüfen Sie die Energie-und Ruhezustandseinstellungen.
    - Bildschirmschoner: 15 Minuten, auf (keine), Mystify oder leer; Kontrollkästchen zum Anfordern eines Kennworts ist aktiviert
    - Bildschirm: 2 Stunden
    - PC: 4 Stunden
8. Überprüfen Sie, ob Windows Hello funktioniert.
9. Überprüfen Sie die Energieeinstellungen.
10. Überprüfen der Synchronisierung Ihre Einstellungen sind deaktiviert.
11. Überprüfen von Start-apps.

> [!TIP]
> Nach der Installation und Konfiguration von Windows 10 kann der Surface Hub 2S genauso wie jedes andere Windows 10-Gerät verwaltet werden.

## Verwandte Themen

[Migrieren zu Windows 10 pro oder Enterprise auf Surface Hub 2](surface-hub-2s-migrate-os.md)
