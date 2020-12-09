---
title: Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2
description: Dieser Artikel enthält Empfehlungen, mit denen Sie bei Verwendung eines personalisierten Touchscreen-und Stift Computers mit großem Touchscreen optimale Ergebnisse erzielen können.
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
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203556"
---
# Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2

Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um apps und Einstellungen auf dem Surface Hub 2 zu konfigurieren. Diese Schritte werden empfohlen, um die optimale Benutzerfreundlichkeit bei der Verwendung dieses personalisierten Touchscreen-und Stift Computers zu gewährleisten.

Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.

## Konfigurieren von Systemeinstellungen

1. Anmelden mit einem Konto, das über lokale Administratorrechte auf dem Gerät verfügt.  

    - Auf Azure AD-verbundenen Geräten wird der Benutzer, der die Azure AD-Verknüpfung ausführt, automatisch der lokalen Administratorgruppe hinzugefügt. Azure AD Global Administrators und Azure AD Devices-Administratoren sind <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> auch lokale Administratoren </a> . 
    
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

    1. Wählen Sie das **Tastatur** Symbol in der Taskleiste aus, um die Bildschirmtastatur anzuzeigen.
    
    2. Wählen Sie auf der Bildschirmtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.
    
    3. Wählen Sie in der obersten Zeile den neben letzten Tastaturtyp aus, um die QWERTY-Funktion zu aktivieren, und die letzte Option in der zweiten Zeile, um das Floating zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist. Weitere Informationen finden Sie in den folgenden Beispielen.

       ![Tastatureinstellungen](images/kbd.png)
 
3. Konfigurieren Sie die Einstellungen für die Soft-Tastatur.

    1. Wählen Sie auf der Bildschirmtastatur das Symbol **Einstellungen** aus, oder suchen Sie nach den **Eingabeeinstellungen**, und öffnen Sie Sie.
    
       ![Soft Keyboard-Einstellungen](images/sh2-softkeyboard.png)

    1. Aktivieren Sie alle Optionen unter Rechtschreibung, Eingabe und Bildschirmtastatur.


Das folgende Beispiel zeigt das Trackpad, das nützlich ist, um zu navigieren und Optionen auszuwählen. Die Bildschirmtastatur wird verwendet, um den Microsoft Store zu durchsuchen:

![Verwenden des Trackpads](images/store.png)

## Konfigurieren der Bluetooth-Tastatur und-Maus (optional)

Schließen Sie eine Tastatur und Maus an, wenn Sie das Gerät als Ihr primäres Windows-Gerät verwenden, oder verwenden Sie es häufig für die Eingabe oder die Genauigkeit der Arbeit.

Wenn sich Ihr Surface-Hub-Gerät in der Nähe eines PCs befindet, können Sie <a href="https://aka.ms/mm" target="_blank"> die Maus ohne Rahmen verwenden, </a> um nahtlos zwischen dem Surface-Hub und dem PC zu wechseln. Weitere Informationen finden Sie unter <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft-Download aus der Garage: Maus ohne Rahmen. </a>

## Beispiel für ein Taskleisten Layout

Nachdem Sie die folgenden Schritte zum Einrichten/Konfigurieren Ihres Surface Hub 2 für Windows 10 Professional oder Enterprise ausgeführt haben, empfiehlt es sich, die am häufigsten verwendeten Anwendungen auf der Taskleiste zu verwenden, um die einzelnen Anwendungen schnell zu starten. Nachfolgend finden Sie ein Beispiel dafür, wie Ihre Taskleiste aussehen könnte:

 ![Taskleisten Layout](images/taskblyt.png)
### Aktualisieren von installierten apps

So aktualisieren Sie alle installierten Store-Apps:

1. Öffnen Sie die Microsoft Store-App, und wählen Sie in der oberen rechten Ecke die Option Weitere Auslassungszeichen **anzeigen** aus.
2. Wählen Sie **Downloads und Updates aus.**
3. Wählen Sie **Updates abrufen** aus.

### Überprüfen und Installieren aller Windows-Updates
Nach der Migration zu Windows 10 Professional oder Windows 10 Enterprise sind möglicherweise Wartungs-und Funktionsupdates verfügbar, die Sie installieren können. 

- Wechseln Sie zu **Einstellungen**  >  **Aktualisieren & Sicherheits** >, und wählen Sie dann **auf Updates überprüfen**aus.
- Wenn Updates vorhanden sind, installieren Sie Sie, starten Sie den Computer neu, und wiederholen Sie den Vorgang, bis die folgende Meldung angezeigt wird:

> [!div class="mx-imgBorder"]
> ![Windows Update-Benachrichtigung "Sie sind aktuell"](images/wustatus.png)


## OneDrive for Business

Verwenden Sie <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business, </a> um Tools, Protokolle und andere Dateien auf einfache Weise zwischen allen ihren Arbeitsgeräten freizugeben.

- Mit OneDrive können Sie Ihre Arbeitsdateien zwischen ihren Laptops, dem Surface Hub-Desktop und ihren von InTune verwalteten mobilen Geräten freigeben. Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.

- Wenn Sie die Größe der Surface-Hub-SSD (128 GB) berücksichtigen und OneDrive auf Ihrem Surface Hub-Desktop Gerät konfigurieren, stellen Sie sicher, dass die Standardkonfiguration darin besteht, die Dateien online zu speichern und während der Verwendung Dateien herunterzuladen.

Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung **files on-Demand** fest, um **Speicherplatz zu sparen und während der Verwendung Dateien herunterzuladen**. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Abfragen und Einrichten von Dateien auf Anforderungsstatus in Windows </a> .

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
    
    2. Navigieren Sie zu und klicken Sie mit der rechten Maustaste auf Ihren SharePoint-Namen Beispiel: **contoso \ \<SharePoint Document Folder Name\> **.
    
    3. Wählen Sie **Speicherplatz freigeben**aus.
    
    4. In der Spalte Status wird der Status von Dateien und Ordnern angezeigt. Weitere Informationen finden Sie unter <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Synchronisieren von SharePoint-Dateien mit dem OneDrive-synchronisierungsclient </a> .
    
6. Teams-Kanaldateien werden auf SharePoint-Websites mit allen gleichen SharePoint-Dokumentfunktionen wie Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten gespeichert. So synchronisieren Sie Teams-Kanaldateien:

    1. Navigieren Sie zu dem Interessenbereich "Teams", und wählen Sie oben die Registerkarte " **Dateien** " aus. Wählen Sie dann **Synchronisieren**aus. Die Dateien werden synchronisiert und werden im Datei-Explorer auf dem **Desktop \ Contoso \<name of the Teams Channel\> **angezeigt.
    
    2. Verwenden Sie dasselbe Verfahren, das Sie zum Synchronisieren von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern, und laden Sie Sie nur herunter, wenn Sie Sie verwenden, indem Sie im Datei-Explorer auf den Namen des Teams-Kanals tippen und halten oder mit der rechten Maustaste darauf klicken und dann **Platz freigeben**auswählen.

## Surface Hub-Stifteinstellungen

**Koppeln des Bluetooth Surface Hub-Stifts**

Koppeln Sie den Stift, um die Stift-Firmware auf dem neuesten Stand zu halten, legen Sie die Tastenkombinationen für den Stift und die Akku Lade Informationen auf der Seite Bluetooth-Geräteeinstellungen oder in der Surface-App ab:

1. Wählen Sie **Start**  >  **Settings**  >  **Devices**aus.

2. Wählen Sie **Bluetooth oder anderes Gerät hinzufügen**aus.

3. Wählen Sie **Bluetooth**aus.

4. Entfernen Sie die Stift-Endstück-Taste und schütteln, um die Batterie Verbindung zu trennen.

5. Setzen Sie die Kappe wieder ein, und halten Sie die Kappe gedrückt, bis die Kopplungs-LED blinkt.

6. Wählen Sie auf den Surface Hub Bluetooth-Einstellungen die Option **Surface Hub 2 Pen**aus.

7. Führen Sie den Kopplungsvorgang aus. 

8. Wenn die Kopplung nicht erfolgreich ist, können Sie versuchen, den Stift erneut zu koppeln. Wenn dies nicht funktioniert, können Sie testen, ob der Akku aufgeladen wird, indem Sie überprüfen, ob der Stift in der Whiteboard-Anwendung funktioniert. Wenn dies nicht der Fall ist, ersetzen Sie die Batterie, und versuchen Sie dann, den Stift erneut zu koppeln. Falls erforderlich, starten Sie das Gerät neu, und versuchen Sie es dann erneut.

**Einrichten von Stifttasten Kombinationen** Der Surface-Hub-Stift hat eine Verknüpfungsschaltfläche, die manchmal auch als "Schwanz Klick" bezeichnet wird. Für das Konfigurieren von Tastenkombinationen müssen Sie den Stift zunächst wie zuvor beschrieben koppeln.

1. Suchen Sie nach Stift, und wählen Sie **Stift & Windows Ink-Einstellungen**aus.

2. Wählen Sie am unteren Rand der Seite Stifttasten Kombinationen aus, die das Dialogfeld öffnen, das hier angezeigt wird:

   ![Stifttasten Kombinationen](images/sh2-pen-shortcuts.png)

## Kamerakonfiguration

Sie können die Kamera oben oder an jeder Seite des Geräts montieren. Montieren Sie die Kamera in einer Position, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktop-Standfuß statt mit einem Wagen verwenden oder sich in der Nähe des Hubs befinden. Da die Kamera nicht automatisch gedreht wird, benötigen Sie eine 2mm-Sechskant-Taste, um die Kamera manuell zu drehen. 

Weitere Informationen dazu, wie Sie die Kamera seitlich montieren und die Kamera manuell drehen können, finden Sie unter <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S-Kameralinsen Ausrichtung </a> .

## Windows Hello-Konfiguration

Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen. Der Surface Hub 2-Fingerabdruckleser-Zubehör kann an einen beliebigen USB-C-Anschluss des Geräts angeschlossen werden. 

Wenn Sie einen Surface Hub 2-Fingerabdruckleser bestellen oder technische Daten anzeigen möchten, lesen Sie (Surface-Hub-2-Essential-Add-ons.MD "target =" _blank ">Essential Add-ons für Windows 10 pro und Enterprise auf Surface Hub 2 </a> . 

Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie **Start**  >  **Einstellungen**  >  **Accounts**  >  für die**Anmeldeoptionen**  >  **Windows Hello Fingerabdruck** aus, um Ihren Fingerabdruck einzuschreiben.

Verwenden Sie ein Windows Hello Certified-Gerät für die Flächen Erkennung. Die Surface Hub 2S-Kamera unterstützt keine Windows Hello Face-Erkennung.

## Aktivieren eines Symbol Symbols für den Sperrbildschirm auf der Taskleiste

So fügen Sie der Taskleiste ein Symbol hinzu, das eine Touchscreen-Sperre ähnlich der Windows-L-Tastenkombination ermöglicht: 

1.  Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen Sie **neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**  >  **weiter**aus.

1.  Geben Sie einen Namen für die Verknüpfung ein, beispielsweise " **mein PC sperren**", und wählen Sie dann **Fertig stellen**aus.

1.  Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften**aus. Geben Sie auf der Registerkarte **Verknüpfung** im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll, Lock Workstation**

1.  Wählen Sie die Schaltfläche **Symbol ändern** aus, und navigieren Sie zu **C:\Windows\System32\imageres.dll** , und wählen Sie ein Symbol aus, das Sie verwenden möchten. 

    Siehe hierzu das folgende Beispiel:

    ![Wählen Sie ein Symbol aus.](images/lock.png)
    
1.  Wählen Sie **OK** aus, um die Verknüpfung zu speichern.

1.  Klicken Sie mit der rechten Maustaste, oder tippen und halten Sie die Verknüpfung, und wählen Sie **an Taskleiste anheften**aus.

1. Nachdem Sie die Tastenkombination "Sperren" an die Taskleiste angeheftet haben, können Sie Sie vom Desktop löschen.

## Anwendungen


### Microsoft Whiteboard

So installieren Sie das Microsoft Whiteboard:

 - Wählen Sie unten rechts in der Taskleiste das Symbol für den **Windows-Freihand-Arbeitsbereich** aus, und laden Sie **Whiteboard**herunter.
 
   ![Freihand-Arbeitsbereich](images/ink.png) 

Sie können Whiteboard auch über den Microsoft Store installieren:

1. Öffnen Sie die Microsoft Store-App, und suchen Sie nach **Whiteboard**.

2. Wählen Sie " **Nein** ", wenn Sie sich anmelden und geräteübergreifend verwenden.

3. Anheften des Whiteboards an die Taskleiste

### Surface-App

1. Suchen Sie im Microsoft Store nach **Surface**.

2. Setzen Sie den **verfügbaren** Filter auf **alle Geräte**.

3. Installieren Sie die **Surface** -app. Dies sollte die erste aufgelistete APP sein. Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die APP installieren zu können.

4. Anheften Sie die **Surface** -APP an die Taskleiste.

### Ausschneiden und skizzieren

1. Öffnen Sie die APP **Snip & Sketch** , und fixieren Sie Sie an die Taskleiste.

2. Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen**aus.

3. Aktivieren Sie in **Einstellungen** **die Option automatisch in Zwischenablage kopieren**, **snips speichern**und **mehrere Fenster** (optional).

### Microsoft Office

1. Öffnen <a href="https://portal.office.com/account#installs" target="_blank"> Sie das Office </a> -Portal, und installieren Sie die gewünschten Anwendungen.

2. Anheften Sie die gewünschten Office-Anwendungen an die Taskleiste.

3. Wenn Outlook installiert ist, müssen Sie Outlook Ost so einstellen, dass nur der letzte zwei Wochen-Cache gespeichert wird. Dadurch werden die Datenträgernutzung und die Einrichtungszeit erheblich reduziert.

    - Wählen Sie **Datei**  >  **Kontoeinstellungen** aus, und wählen Sie Ihr Konto aus.
    
    - Wählen Sie **ändern** aus, und legen Sie den Schieberegler für die **Verwendung des Exchange-Cache-Modus** auf 14 Tage.

### Microsoft Teams

1. Laden Sie Microsoft Teams herunter, und installieren Sie Sie <a href="https://teams.microsoft.com/downloads" target="_blank"> </a> .

2. Konfigurieren Sie die Einstellungen für die automatische Startanwendung (optional).

3. Anheften von Teams an die Taskleiste.

4. Sie können die Benachrichtigungen für Teams auf dem Gerät reduzieren, um Ablenkungen zu vermeiden (optional).

   ![Teams-Benachrichtigungen](images/teams.png)

### Connect-App

> [!IMPORTANT]
> In Windows 10, Version 2004 und höher, ist die Connect-App für drahtlose Projektion unter Verwendung von Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung. Wenn Sie Windows-Version 2004 oder höher installiert (oder aktualisiert) haben, wird möglicherweise auf dem Bildschirm Projektion auf diesen PC unter Einstellungen Folgendes angezeigt:

![Projekt auf diesem PC](images/sh2-project.png) 


1. Wenn Sie die APP auf der Seite "auf diesen PC projizieren" installieren möchten, wählen Sie **optionale Features**  >  **Add a Feature** und dann die **drahtlose Anzeige** -App aus.

2. Unter **einigen Windows-und Android-Geräten können Sie auf diesen PC projizieren, wenn Sie sagen, dass es in Ordnung ist**, wählen Sie:

    - **Überall verfügbar** , wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet.
    - Wählen Sie andernfalls **überall in sicheren Netzwerken verfügbar**aus.
    
3. Wählen Sie unter **Projekt auf diesem PC anfordern**die Option **nur erstes Mal**aus.

4. Wählen Sie unter **PIN für Kopplung anfordern**die Option **nie**aus.

5. Wenn Sie die app starten und an die Taskleiste anheften möchten, suchen Sie nach **Connect**.

6. Öffnen Sie die app. Klicken Sie, während die APP geöffnet ist, mit der rechten Maustaste auf das Symbol "App verbinden" auf der Taskleiste, und wählen Sie **an Taskleiste anheften**aus.

7. Schließen Sie dann die Connect-app. **Project auf diesem PC** funktioniert möglicherweise nur, wenn die APP mindestens einmal ausgeführt wurde.

Empfohlene Konfiguration, wenn Sie sich nicht im Unternehmensnetzwerk befinden:

![Einstellungen zu Hause](images/project1.png)

Empfohlene Konfiguration im Unternehmensnetzwerk:

![Einstellungen bei der Arbeit](images/project2.png)

### Ihr Smartphone

Die APP **Ihres Telefons** wird unter Windows 10 standardmäßig installiert. Wenn Sie nicht vorhanden ist, können Sie Sie auch aus dem Windows Store installieren.

Informationen zum Einrichten der App finden Sie unter so wird es <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> gemacht: Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten zwischen Ihrem PC und Smartphone </a> . Weitere Informationen finden Sie unter <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Beheben häufig auftretender Probleme mit ihrer Telefon-APP unter Windows 10 </a> .

###  Fancy Zones


**Fancy Zones** ist Teil einer Sammlung von Tools namens <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> auf GitHub. Es ist eine großartige Möglichkeit, um den Bildschirm "Real Estate" auf einem Surface Hub 2 zu verwenden, indem Sie die Möglichkeit haben, feste Layouts auf dem Display ("Zonen") zu definieren, und dann auszuwählen, welche app dann in den einzelnen Zonen ausgeführt werden soll. 


Das [PowerToys-wiki](https://github.com/microsoft/PowerToys/wiki) enthält Anleitungen zum verwenden und Anpassen der einzelnen Tools, einschließlich [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). Auf einem hohen Niveau – nach der Installation von PowerToys können Sie ein benutzerdefiniertes Layout auswählen oder erstellen und dann die UMSCHALTTASTE gedrückt halten und die Tastenkombination ziehen oder verwenden, um eine ausgeführte app in bestimmte Zonen zu verschieben. Die Verwendung einer Bluetooth-oder USB-Tastatur und-Maus hilft Ihnen dabei, oder Sie können die Bildschirmtastatur und das Touchpad verwenden.

**Power Toys-Tipps**
- Um e-Mail-Benachrichtigungen über PowerToys-Versionsupdates auf GitHub zu erhalten, klicken Sie oben auf der [Seite](https://github.com/microsoft/PowerToys/releases)auf die Schaltfläche "Anmelden".
- Sobald PowerToys installiert ist, können Sie Windows-Benachrichtigungen empfangen und/oder die neuesten Updates herunterladen und installieren, indem Sie die Einstellungen für den PowerToys- **Download automatisch** auf ein konfigurieren.
- Um zu den PowerToys-Einstellungen zu gelangen, wählen Sie in der Taskleiste die auf Carat **ausgeführten apps** aus, und klicken Sie dann mit der rechten Maustaste, oder halten Sie das PowerToys-Symbol gedrückt, bis das Menü angezeigt wird. Wählen Sie "Einstellungen" aus.
- Aktivieren Sie unten auf der Seite PowerToys-Einstellungen die Option **Updates automatisch herunterladen** auf ein.
- Wenn ein Update veröffentlicht wurde, wird eine Windows-Benachrichtigung angezeigt, die Ihnen die Möglichkeit bietet, das Update zu installieren.


### Edge Chrom-Browser

Laden Sie den neuen Edge Chrom-Browser herunter, und installieren Sie ihn <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> </a> .


### Surface Hub-Hardware Diagnosetool

Das <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub-Hardware Diagnosetool ist </a> kostenlos im Microsoft Store erhältlich. Das Tool ist so konzipiert, dass Sie sicherstellen können, dass Ihr Surface Hub optimal ausgeführt wird. Sie enthält Tests, um festzustellen, ob Ihre Firmware auf dem neuesten Stand ist und richtig konfiguriert ist. Interaktive Tests ermöglichen Ihnen, zu bestätigen, dass die wesentlichen Funktionen wie erwartet funktionieren. Wenn Probleme auftreten, können Ergebnisse gespeichert und für das Surface Hub-Support-Team freigegeben werden. Klicken Sie auf den Link, um ihn aus dem Microsoft Store zu installieren, und anheften Sie die Anwendung dann an Ihre Taskleiste.

## Zusätzliche Einstellungen

### Stift Schwanz auswählen, um Whiteboard zu starten

1. Suchen Sie nach **Stift** , und wählen Sie **Stift & Windows Ink-Einstellungen**aus.

2. **Klicken Sie** am unteren Rand der Seite unter **Stifttasten Kombinationen** auf **Microsoft Whiteboard**auswählen. 

### Energieverwaltung

Es stehen mehrere Energieeinstellungen zur Verfügung, mit denen Sie Windows 10 pro oder Enterprise auf Surface Hub 2 optimal nutzen können. Dazu gehören Bildschirm-und PC-Timeouts sowie deren Interaktion mit der integrierten Anwesenheitserkennung (Human Presence Detection, Doppler), dem Bildschirmschoner und dem Kennwortschutz und dann, wenn angemessen, wie die Energieeinstellungen für Gruppenrichtlinien, die für Laptops/Desktopbenutzer vorgesehen sind.

Mit Windows 10 pro oder Enterprise auf Surface Hub 2 können Sie den Bildschirm nicht über die Fingereingabe, Maus-und Tastaturaktionen sowie über die integrierte Erkennung für die menschliche Benutzungs Erkennung (Human Auslastung Detection, Doppler) in den Standbymodus versetzen. Die Erkennung für die menschliche Auslastung ist standardmäßig aktiviert, kann aber bei Bedarf in UEFI deaktiviert werden, indem die Option Device im Surface UEFI Configurator-Tool entweder als Teil der anfänglichen Migration oder durch Erstellen und Anwenden eines späteren UEFI-Konfigurationspakets deaktiviert wird. 

**Energieverwaltung: Bildschirm-und PC-Ruhemodus-Einstellungen**

1. Wählen Sie **Start**  >  **Einstellungen**  >  **System**  >  **Power & Sleep**aus.

2. Stellen Sie den Power Mode-Schieberegler auf **optimale Leistung**ein.

3. Konfigurieren Sie die Einstellungen für den Bildschirm und den Ruhezustand nach Ihren wünschen, während Sie auch die Doppler-Anwesenheitserkennung erfassen, die das Gerät aktiviert, wenn Bewegungen erkannt werden. Daher empfiehlt es sich, den Bildschirm so zu konfigurieren, dass er **nach 2 Stunden ausgeschaltet** wird und der PC **nach 4 Stunden ausgeschaltet wird.**

**Energieverwaltung: Bildschirmschoner**

1. Suchen Sie nach **dem Sperrbildschirm** , und öffnen Sie die Einstellungen für den **Sperrbildschirm**.

2. Konfigurieren Sie die Einstellungen für das **Bildschirm Timeout** und die **Bildschirmschonereinstellungen** nach Ihren Wünschen. Empfohlene Standardwerte:

   - Bildschirmschoner (ohne) oder Bildschirmschoner Ihrer Wahl.
   - Wartezeit auf 15 Minuten.
   - Zeigen Sie auf Resume den Anmeldebildschirm an.


**Energieverwaltung: Gruppenrichtlinien**

Bevor Sie das folgende Verfahren ausführen, erkundigen Sie sich bei Ihrer IT-Abteilung, ob ein Surface Hub 2S-Gerät aus der globalen Energieverwaltungsrichtlinie ausgeschlossen werden soll. Einige Energieverwaltungseinstellungen können die Anwesenheits Erkennungsfunktion deaktivieren.

1. Suchen Sie nach **Software Center** , und öffnen Sie Sie.

2. Wählen Sie **Optionen**aus.

3. Erweitern Sie die **Energieverwaltung**  , und wählen Sie **auf diesem Computer keine Energieeinstellungen von meiner IT-Abteilung anwenden aus**.

   ![Software Einstellungen](images/soft-cntr.png)

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

2. Aktualisieren Sie die Gruppenrichtlinien.

   1. Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate force/Boot/Wait: 0**ein.
   
3. Starten Sie das Gerät neu.

4. Überprüfen der Taskleisten-apps

   - Connect-App
   - Symbol "Sperren"
   - Ausschneiden und skizzieren
   - Teams (falls zutreffend)
   - Office-Apps (falls zutreffend)
   - Surface-App
   - Whiteboard
    
5. Überprüfen Sie die Anwesenheitserkennung.

   - Die Anwesenheitserkennung ist ein grünes Symbol in der Taskleiste.
    
6. Überprüfen Sie, ob das projizieren auf diesen PC mit der Connect-App aktiviert ist. Nachdem  **Sie Project auf diese PC** -Einstellungen konfiguriert haben, führen Sie die Connect-App mindestens einmal aus. (Anschließend muss die Connect-APP nicht ausgeführt werden, damit Project to Surface Hub projiziert werden kann.)

7. Überprüfen Sie die Energie-und Ruhezustandseinstellungen.

    - Bildschirmschoner: 15 Minuten, auf (keine), Mystify oder leer; Stellen Sie sicher, dass das Kontrollkästchen für das Anfordern eines Kennworts aktiviert ist.
    - Bildschirm: Ausschalten **nach 2 Stunden**.
    - PC: Ausschalten  **nach 4 Stunden**.
    
8. Überprüfen Sie, ob Windows Hello funktioniert.

9. Überprüfen der Synchronisierung Ihre Einstellungen sind deaktiviert.

10. Überprüfen von Start-apps.

> [!TIP]
> Nach der Installation und Konfiguration von Windows 10 kann der Surface Hub 2S genauso wie jedes andere Windows 10-Gerät verwaltet werden.

## Verwandte Themen

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2</a>
