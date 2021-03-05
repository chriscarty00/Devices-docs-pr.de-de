---
title: Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2
description: Dieser Artikel enthält Empfehlungen, um die beste Erfahrung bei der Verwendung eines personalisierten Touch- und Stiftcomputers mit großem Bildschirm sicherzustellen.
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
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393588"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>Konfigurieren von Windows 10 Pro oder Enterprise auf Surface Hub 2

Nachdem Sie den Installationsvorgang für die Migration zu Windows 10 Pro oder Enterprise abgeschlossen haben, können Sie die folgenden Schritte ausführen, um Apps und Einstellungen auf Ihrem Surface Hub 2 zu konfigurieren. Diese Schritte werden empfohlen, um die beste Erfahrung bei der Verwendung dieses personalisierten Touch- und Stiftcomputers mit großem Bildschirm zu gewährleisten.

Wenn Sie diese Schritte ausführen, ist es möglicherweise hilfreich, eine kabelgebundene oder drahtlose Tastatur und Maus zu verwenden.

## <a name="configure-system-settings"></a>Konfigurieren von Systemeinstellungen

1. Melden Sie sich mit einem Konto an, das über lokale Administratorrechte auf dem Gerät verfügt.  

    - Auf geräten, die azure AD beigetreten sind, wird der Benutzer, der den Azure AD-Beitritt ausführt, automatisch der lokalen Administratorgruppe hinzugefügt. Globale Azure AD-Administratoren und Azure AD-Geräteadministratoren <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> sind auch lokale </a> Administratoren. 
    
    - Sie können an einer **Eingabeaufforderung** Netzwerkadministratoren für lokale Gruppen eingeben, um die Konten mit lokalen Administratorrechten auflisten zu können.
    
2. Benennen Sie das Gerät mithilfe eines Anzeigenamens um, z. B. **benutzername-SHub-Desktop**.

3. Wählen **Sie Einstellungen**  >  **starten**  >  **Konten**  >  **synchronisieren Ihre Einstellungen aus,** und deaktivieren Sie die **Synchronisierungseinstellungen.** 

    - Die hier verwendeten Einstellungen sollen die beste Toucherfahrung für große Bildschirme ermöglichen, daher möchten Sie möglicherweise keine anderen Geräte synchronisieren.
    
4. Starten Sie das Gerät neu.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>Aktivieren der Touchtastatur und des Touchpads

1. Wählen **Sie**  >  **Starteinstellungen**  >  **Geräte**  >  **eingeben aus,** und aktivieren Sie Touchtastatur anzeigen, wenn sie sich nicht im **Tablet-Modus** befindet und keine Tastatur angeschlossen ist.

2. Tippen und halten Oder klicken Sie mit der rechten Maustaste auf die Taskleiste, und wählen Sie dann Touchtastaturschaltfläche **anzeigen** und **Touchpad anzeigen aus.** 

    - Die Touchtastatur ist hilfreich für direkte Benutzereingaben, und das virtuelle Touchpad hilft bei präzisen Auswahlen, zeigenden Bildschirmtipps oder als Alternative zum Tippen und Halten für rechtsklicken. 
    
    - Nachfolgend sehen Sie ein Beispiel.

      ![Toucheinstellungen](images/touch.png)

3. Konfigurieren Sie die Touchtastatur auf QWERTY und unverankert.

    1. Wählen Sie **das Tastatursymbol** auf der Taskleiste aus, um die Touchtastatur zu zeigen.
    
    1. Wählen Sie auf der Touchtastatur das Tastatursymbol in der oberen linken Ecke aus, um die Tastatureinstellungen zu öffnen.
    
    1. Wählen Sie den nächsten bis letzten Tastaturtyp in der oberen Zeile aus, um QWERTY zu aktivieren, und die letzte Option in der zweiten Zeile, um das Unverankerte zu aktivieren, was auf diesem großen Bildschirm sehr hilfreich ist. Weitere Informationen finden Sie in den folgenden Beispielen.

       ![Tastatureinstellungen](images/kbd.png)
 
4. Konfigurieren Sie die Softtastatureinstellungen.

    1. Wählen Sie **das Symbol** Einstellungen auf der Touchtastatur aus, oder suchen Sie nach **Eingabeeinstellungen,** und öffnen Sie sie.
    
       ![Softtastatureinstellungen](images/sh2-softkeyboard.png)

    1. Aktivieren Sie alle Optionen unter Rechtschreib-, Eingabe- und Touchtastatur.


Das folgende Beispiel zeigt das Trackpad, das zum Navigieren und Auswählen von Optionen hilfreich ist. Die Bildschirmtastatur wird zum Durchsuchen des Microsoft Store verwendet:

![Verwenden des Trackpads](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Konfigurieren Bluetooth Tastatur und Maus (optional)

Verbinden Sie Tastatur und Maus, wenn Sie das Gerät als primäres Windows-Gerät verwenden oder es häufig zur Eingabe oder Genauigkeit verwenden.

Wenn sich Ihr Surface Hub-Gerät in der Nähe eines PCs befindet, können Sie Mouse ohne Rahmen verwenden, um nahtlos zwischen Surface Hub und <a href="https://aka.ms/mm" target="_blank"> </a> PC zu wechseln. Weitere Informationen finden Sie unter <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders. </a>

## <a name="example-of-taskbar-layout"></a>Beispiel für das Taskleistenlayout

Nachdem Sie die folgenden Schritte zum Einrichten/Konfigurieren Ihres Surface Hub 2 für Windows 10 Professional oder Enterprise abgeschlossen haben, wird empfohlen, die am häufigsten verwendeten Anwendungen an die Taskleiste anheften zu können, um die einzelnen Anwendungen schnell und einfach zu starten. Im Folgenden finden Sie ein Beispiel dafür, wie Ihre Taskleiste aussehen könnte:

 ![Taskleistenlayout](images/taskblyt.png)
### <a name="update-installed-apps"></a>Aktualisieren installierter Apps

So aktualisieren Sie alle installierten Store-Apps:

1. Öffnen Sie die Microsoft Store-App, und wählen Sie die **Option Weitere** Auslassungspunkte in der oberen rechten Ecke aus.
2. Wählen Sie **Downloads und Updates aus.**
3. Wählen Sie **Updates erhalten aus.**

### <a name="scan-for-and-install-all-windows-updates"></a>Überprüfen und Installieren aller Windows-Updates
Nach der Migration zu Windows 10 Professional oder Windows 10 Enterprise stehen Möglicherweise Wartungs- und Funktionsupdates zur Installation zur Verfügung. 

- Wechseln Sie **zu Einstellungen**Update & Security >, und wählen Sie dann  >  **** Nach Updates **suchen aus.**
- Wenn Updates verfügbar sind, installieren Sie sie, starten Sie den Vorgang neu, und wiederholen Sie den Vorgang, bis die folgende Benachrichtigung angezeigt wird:

> [!div class="mx-imgBorder"]
> ![Benachrichtigung "Sie sind auf dem neuesten Stand" für Windows Update](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive for Business

Verwenden Sie OneDrive for Business zum einfachen Freigeben von Tools, Protokollen und anderen Dateien <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> zwischen allen Arbeitsgeräten.

- Mit OneDrive können Sie Ihre Arbeitsdateien zwischen Ihren Laptops, Surface Hub Desktop und Ihren von Intune verwalteten mobilen Geräten freigeben. Dateien können auf jedem Gerät bearbeitet werden, und alle mit dem Netzwerk verbundenen Geräte werden mit den Änderungen aktualisiert.

- Wenn Sie die Größe der Surface Hub-SSD (128 GB) bedenken, müssen Sie beim Konfigurieren von OneDrive auf Ihrem Surface Hub Desktop-Gerät sicherstellen, dass die Standardkonfiguration die Onlinespeicherung der Dateien und das Herunterladen von Dateien während der Verwendung ist.

Wenn Sie OneDrive so konfigurieren möchten, dass Dateien nur bei Bedarf heruntergeladen werden, legen Sie die Einstellung Dateien **bei** Bedarf auf Speicherplatz sparen und Dateien während der Verwendung **herunter.** Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows </a> .

![#A0](images/onedrive.png)

> [!NOTE]
> Sie können diese Schritte auch wiederholen, um ein persönliches OneDrive zu konfigurieren, aber achten Sie darauf, speicherplatzsparend zu sein und dateien nur nach Bedarf herunterzuladen.

## <a name="sharepoint-and-teams"></a>SharePoint und Teams

SharePoint- und #A0 können mithilfe des #A1 auch lokal mit Ihren Desktopgeräten synchronisiert werden, z. B. Laptops und Surface Hubs.

So synchronisieren Sie interne Unternehmensdateien mit Ihrem lokalen Laufwerk mit der OneDrive-Synchronisierungs-App:

1. Wechseln Sie zu einer SharePoint-Website, und navigieren Sie zum Dokumentverzeichnis auf oberster Ebene für Dateien, die Sie auf Ihrem lokalen Gerät anzeigen oder bearbeiten möchten.

2. Wählen Sie auf der **Schaltfläche Synchronisieren** oben im SharePoint-Menüband aus.

3. Wählen Sie **im Popup** Öffnen aus Diese **Website versucht, Microsoft OneDrive zu öffnen.**

4. Vergewissern Sie sich, dass die #A0 mit Ihrem lokalen Laufwerk synchronisiert werden, indem Sie das #A1 unten rechts auf der Taskleiste auswählen.

5. Überprüfen Sie, ob die Konfiguration so festgelegt ist, dass die Dateien online bleiben, und laden Sie die Dateien nur so herunter, wie Sie sie verwenden:

    1. Öffnen Sie den Datei-Explorer.
    
    2. Navigieren Sie zu Und klicken Sie mit der rechten Maustaste auf Ihren #A0 z. B. **Contoso \ \<SharePoint Document Folder Name\> **.
    
    3. Wählen **Sie Speicherplatz frei.**
    
    4. In der Spalte Status wird der Status von Dateien und Ordnern angezeigt. Weitere Informationen finden Sie unter <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client </a> .
    
6. Teams Channel-Dateien werden auf SharePoint-Websites mit derselben SharePoint-Dokumentfunktionalität gespeichert, einschließlich Versionsverlauf und Synchronisierung mit Ihren lokalen Desktopgeräten. So synchronisieren Sie Teams Channel-Dateien:

    1. Navigieren Sie zum Teams-Kanal von Interesse, und wählen **Sie** oben die Registerkarte Dateien aus. Wählen Sie dann **Synchronisieren aus.** Die Dateien beginnen mit der Synchronisierung und werden im Datei-Explorer unter **Desktop \ Contoso \ angezeigt. \<name of the Teams Channel\> **
    
    2. Verwenden Sie das gleiche Verfahren, das Sie für die Synchronisierung von SharePoint-Websites verwendet haben, um die Dateien in der Cloud zu speichern und sie nur herunterzuladen, wenn Sie sie verwenden, indem Sie im Namen des Teams-Kanals auf Datei-Explorer tippen und diese halten oder mit der rechten Maustaste klicken und dann **Speicherplatz**freigeben auswählen.

## <a name="surface-hub-pen-settings"></a>Surface Hub-Stifteinstellungen

**Koppeln Bluetooth Surface Hub Pen**

Koppeln Sie den Stift, um die Stiftfirmware auf dem neuesten Stand zu halten, legen Sie die Stiftverknüpfungen ein und erhalten Sie Akkuladeinformationen auf der Seite Bluetooth Geräteeinstellungen oder in der Surface-App:

1. Wählen **Sie**  >  **Starteinstellungen**  >  **Geräte aus.**

2. Wählen **Sie Bluetooth oder ein anderes Gerät hinzufügen aus.**

3. Wählen **Sie Bluetooth**aus.

4. Entfernen Sie die Stift-Tail-Taste, und wackeln Sie, um die Akkuverbindung zu trennen.

5. Setzen Sie die Kappe wieder ein, und drücken Und halten Sie die Kappe, bis die Kopplungs-LED blinkt.

6. Wählen Sie unter Surface Hub Bluetooth Surface **Hub 2 Pen aus.**

7. Schließen Sie den Kopplungsvorgang ab. 

8. Wenn die Kopplung nicht erfolgreich ist, können Sie versuchen, den Stift erneut zu koppeln. Wenn dies nicht funktioniert, können Sie testen, ob der Akku geladen ist, indem Sie überprüfen, ob der Stift in der Whiteboard-Anwendung funktioniert. Wenn nicht, ersetzen Sie den Akku, und versuchen Sie dann, den Stift erneut zu koppeln. Starten Sie das Gerät bei Bedarf neu, und versuchen Sie es dann erneut.

**Festlegen von Stiftverknüpfungen** Der Surface Hub-Stift verfügt über eine Verknüpfungsschaltfläche, die manchmal als "Tail Click" bezeichnet wird. Zum Konfigurieren von Verknüpfungen müssen Sie den Stift zuerst koppeln, wie zuvor beschrieben.

1. Suchen Sie nach Stift, und wählen **& Windows Ink-Einstellungen aus.**

2. Wählen Sie am unteren Rand der Seite die Option Stiftverknüpfungen aus, die das Dialogfeld öffnen, wie hier gezeigt:

   ![Stiftverknüpfungen](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>Kamerakonfiguration

Sie können die Kamera oben oder auf beiden Seiten des Geräts einhängen. Stellen Sie die Kamera an einer Position ein, um den Kamerawinkel zu optimieren, wenn Sie den Hub mit einem Desktopständer anstelle eines Einkaufswagens verwenden oder sich in der Nähe des Hubs befinden. Die Kamera wird nicht automatisch gedreht, daher benötigen Sie eine 2mm-Hextaste, um die Kamera manuell zu drehen. 

Weitere Informationen zum seitlichen Einhängen der Kamera und zum manuellen Drehen der Kamera finden Sie unter Ausrichtung der <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S-Kameralinse. </a>

## <a name="windows-hello-configuration"></a>Windows Hello-Konfiguration

Surface Hub 2S mit Windows 10 Enterprise ermöglicht die vollständige Suite von Win32-Desktopanwendungen sowie biometrische Windows Hello-Optionen. Das Surface Hub 2 Fingerprint Reader-Zubehör kann an einen beliebigen USB-C-Port auf dem Gerät angeschlossen werden. 

Informationen zum Bestellen eines Surface Hub 2-Fingerabdrucklesers oder zum Anzeigen technischer Spezifikationen finden Sie unter (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a> . 

Nachdem Sie den Fingerabdruckleser eingefügt haben, wählen Sie ****  >  **Starteinstellungen**  >  **Konten**  >  **Anmeldeoptionen**Windows Hello Fingerprint aus,  >  **** um Ihren Fingerabdruck zu registrieren.

Verwenden Sie ein Windows Hello-zertifiziertes Gerät für die Gesichtserkennung. Die Surface Hub 2S-Kamera unterstützt keine Windows Hello-Gesichtserkennung.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>Aktivieren eines Verknüpfungssymbols für den Sperrbildschirm auf der Taskleiste

So fügen Sie der Taskleiste ein Symbol hinzu, das die Sperre mit einem Touchscreen aktiviert, ähnlich der Windows-L-Tastenkombination: 

1.  Tippen und halten oder klicken Sie mit der rechten Maustaste auf den Desktop, wählen **Sie Neue**  >  **Verknüpfung**  >  **Durchsuchen**  >  **Desktop**  >  **OK**Weiter  >  **aus.**

1.  Geben Sie einen Namen für die Verknüpfung an, z. **B. Pc sperren,** und wählen Sie dann **Fertig stellen aus.**

1.  Klicken oder tippen Sie mit der rechten Maustaste auf die neu erstellte Verknüpfung auf dem Desktop, und wählen Sie **Eigenschaften aus.** Geben Sie **auf** der Registerkarte Verknüpfung im Feld **Ziel** Folgendes ein: **Rundll32.exe User32.dll,LockWorkStation**

1.  Wählen Sie **die Schaltfläche Symbol** ändern aus, navigieren Sie zu **C:\Windows\System32\imageres.dll** und wählen Sie ein zu verwendende Symbol aus. 

    Siehe hierzu das folgende Beispiel:

    ![Auswählen eines Symbols](images/lock.png)
    
1.  Wählen **Sie OK** aus, um die Verknüpfung zu speichern.

1.  Klicken oder tippen Sie mit der rechten Maustaste auf die Verknüpfung, und wählen **Sie An Taskleiste anheften aus.**

1. Nachdem Sie die Sperrverknüpfung an die Taskleiste angeheftet haben, können Sie sie auf dem Desktop löschen.

## <a name="applications"></a>Anwendungen


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

So installieren Sie das Microsoft Whiteboard:

 - Wählen Sie das **Symbol Windows Ink Workspace** unten rechts auf der Taskleiste aus, und laden Sie **Whiteboard herunter.**
 
   ![Freihandarbeitsbereich](images/ink.png) 

Alternativ können Sie Whiteboard aus dem Microsoft Store installieren:

1. Öffnen Sie die Microsoft Store-App, und suchen Sie **nach Whiteboard**.

2. Wählen **Sie Nein,** dank der Anmeldung und Verwendung auf allen Geräten.

3. Pin Whiteboard an die Taskleiste.

### <a name="surface-app"></a>Surface-App

1. Suchen Sie im Microsoft Store nach **Surface**.

2. Legen Sie **den Filter Verfügbar** auf Alle Geräte **.**

3. Installieren Sie die **Surface-App.** Dies sollte die erste aufgeführte App sein. Möglicherweise müssen Sie Ihre MSA dem Store zuordnen, um die App zu installieren.

4. Heften Sie **die Surface-App** an die Taskleiste an.

### <a name="snip--sketch"></a>Ausschneiden und skizzieren

1. Öffnen Sie **die Snip-&** Sketch-App, undheften Sie sie an die Taskleiste.

2. Wählen Sie die Auslassungspunkte in der oberen rechten Ecke aus, und wählen Sie dann **Einstellungen aus.**

3. Aktivieren **Sie unter**Einstellungen die Option Automatische Kopie in die **Zwischenablage,** **Snips**speichern und **Mehrere Fenster** (optional).

### <a name="microsoft-office"></a>Microsoft Office

1. Öffnen Sie das <a href="https://portal.office.com/account#installs" target="_blank"> Office-Portal, </a> und installieren Sie die gewünschten Anwendungen.

2. Heften Sie die gewünschten Office-Anwendungen an die Taskleiste an.

3. Wenn Outlook installiert ist, stellen Sie sicher, dass Outlook OST nur den Cache der letzten zwei Wochen speichert. Dadurch werden die Datenträgernutzung und die Einrichtungszeit deutlich reduziert.

    - Wählen **Sie**  >  **Dateikontoeinstellungen aus,** und wählen Sie Ihr Konto aus.
    
    - Wählen **Sie Ändern** aus, und legen Sie den Schieberegler für den **Exchange-Cache-Modus auf** 14 Tage.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Herunterladen und Installieren <a href="https://teams.microsoft.com/downloads" target="_blank"> von Microsoft Teams </a> .

2. Konfigurieren Sie Einstellungen für die Anwendung automatischen Start (optional).

3. Heften Sie Teams an die Taskleiste an.

4. Erwägen Sie die Reduzierung von Teams-Benachrichtigungen auf dem Gerät, um Ablenkungen zu vermeiden (optional).

   ![Teams-Benachrichtigungen](images/teams.png)

### <a name="connect-app"></a>Verbinden der App

> [!IMPORTANT]
> In Windows 10, Version 2004 und höher, ist die Connect-App für die drahtlose Projektion mit Miracast nicht standardmäßig installiert, steht aber als optionales Feature zur Verfügung. Wenn Sie Windows Version 2004 oder höher installiert (oder auf diese aktualisiert haben), wird möglicherweise Folgendes auf dem Bildschirm Projecting to this PC in den Einstellungen angezeigt:

![Project to this PC](images/sh2-project.png) 


1. Wenn Sie die App auf der Einstellungsseite "Auf diesen PC projiziert" installieren möchten, wählen Sie Optionale **Features**Hinzufügen eines Features aus, und installieren Sie dann  >  **** die **App "Drahtlosanzeige".**

2. Wählen Sie unter Einige Windows- und Android-Geräte auf diesen PC projiziert werden, wenn Sie sagen, es **ist OK,** wählen Sie:

    - **Überall verfügbar,** wenn sich das Gerät nicht in einem Unternehmensnetzwerk befindet.
    - Wählen Sie andernfalls **Überall verfügbar in sicheren Netzwerken aus.**
    
3. Wählen **Sie unter Projekt auf diesen PC fragen**die Option Nur **erstes Mal aus.**

4. Wählen **Sie unter PIN für die Kopplung benötigen**die Option Nie **aus.**

5. Suchen Sie nach Connect, um die App zu starten und an die Taskleiste **anheften.**

6. Öffnen Sie die App. Während die App geöffnet ist, klicken Sie mit der rechten Maustaste auf das Symbol App verbinden auf der Taskleiste, und wählen Sie **Pin an Taskleiste aus.**

7. Schließen Sie dann die Connect-App. **Project to this PC** might not work unless the app has been run at least once.

Empfohlene Konfiguration, wenn nicht im Unternehmensnetzwerk:

![Einstellungen zu Hause](images/project1.png)

Empfohlene Konfiguration im Unternehmensnetzwerk:

![Einstellungen bei der Arbeit](images/project2.png)

### <a name="your-phone"></a>Ihr Smartphone

Die **App "Ihr Telefon"** wird standardmäßig unter Windows 10 installiert. Wenn sie nicht vorhanden ist, können Sie sie auch aus dem Windows Store installieren.

Weitere Informationen zum Einrichten der App finden Sie unter Einrichten Ihres Telefons unter Windows 10 und Synchronisieren von Daten <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> zwischen Ihrem PC und Ihrem </a> Smartphone. Weitere Informationen finden Sie unter Beheben häufiger Probleme mit Der App Für Ihr <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Telefon unter Windows 10 </a> .

###  <a name="fancy-zones"></a>Ausgefallene Zonen


**Fancy Zones** ist Teil einer Sammlung von Tools namens <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> auf GitHub. Es ist eine hervorragende Möglichkeit, die Bildschirmfläche auf einem Surface Hub 2 zu nutzen, indem Sie feste Layouts auf Ihrem Display definieren können ("Zonen"), und wählen Sie dann aus, welche App dann in jeder Zone ausgeführt wird. 


Das [PowerToys-Wiki](https://github.com/microsoft/PowerToys/wiki) enthält Anweisungen zum Verwenden und Anpassen der einzelnen Tools, einschließlich [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). Auf einer hohen Ebene – nach der Installation von PowerToys können Sie ein benutzerdefiniertes Layout auswählen oder erstellen und dann die Umschalttaste gedrückt halten und Tastaturtasten ziehen oder verwenden, um eine laufende App in bestimmte Zonen zu verschieben. Die Verwendung Bluetooth oder USB-Tastatur und -Maus hilft dabei, oder Sie können die Bildschirmtastatur und das Touchpad verwenden.

**Tipps für Power toys**
- Um E-Mail-Benachrichtigungen über PowerToys-Releaseupdates auf GitHub zu erhalten, klicken Sie oben auf der Seite auf die Schaltfläche ["Registrieren".](https://github.com/microsoft/PowerToys/releases)
- Sobald PowerToys installiert ist, können Sie Windows-Benachrichtigungen empfangen und/oder die neuesten Updates herunterladen und installieren, indem Sie die PowerToys-Einstellungen **konfigurieren,** um Updates automatisch auf herunterzuladen.
- Um zu den PowerToys-Einstellungen zu wechseln, wählen Sie auf der Taskleiste das Nach oben karat **Ausführen** von Apps aus, und klicken oder drücken Sie mit der rechten Maustaste das PowerToys-Symbol, bis das Menü angezeigt wird. Wählen Sie "Einstellungen" aus.
- Aktivieren Sie am unteren Rand der Seite PowerToys-Einstellungen updates **automatisch** herunterladen.
- Wenn ein Update veröffentlicht wurde, wird eine Windows-Benachrichtigung angezeigt, mit der Sie die Möglichkeit erhalten, wann das Update installiert werden soll.


### <a name="edge-chromium-browser"></a>Edge Chromium-Browser

Laden Sie den neuen <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium-Browser herunter, und installieren Sie </a> sie.


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub Hardware Diagnostic Tool

Das <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic </a> Tool, das kostenlos im Microsoft Store verfügbar ist. Das Tool soll Ihnen dabei helfen, sicherzustellen, dass Ihr Surface Hub optimal ist. Es enthält Tests, um festzustellen, ob Ihre Firmware auf dem neuesten Stand ist und ordnungsgemäß konfiguriert ist. Mit interaktiven Tests können Sie bestätigen, dass wesentliche Funktionen wie erwartet funktionieren. Wenn Probleme auftreten, können Ergebnisse gespeichert und für das Surface Hub-Support-Team freigegeben werden. Klicken Sie auf den Link, um ihn aus dem Microsoft Store zu installieren, undheften Sie die Anwendung dann an Die Taskleiste.

## <a name="additional-settings"></a>Zusätzliche Einstellungen

### <a name="pen-tail-select-to-launch-whiteboard"></a>Stiftschweif auswählen, um Whiteboard zu starten

1. Suchen Sie **nach Stift,** und wählen **& Windows Ink-Einstellungen aus.**

2. Klicken Sie am unteren Rand der Seite unter **Stiftverknüpfungen** **auf** **Microsoft Whiteboard auswählen.** 

### <a name="power-management"></a>Energieverwaltung

Es stehen mehrere Energieeinstellungen zur Verfügung, um die bestmögliche Erfahrung mit Windows 10 Pro oder Enterprise auf Surface Hub 2 zu erhalten. Dies umfasst Bildschirm- und PC-Timeouts und die Interaktion mit der integrierten Erkennung von Anwesenheitseinstellungen (Doppler), dem Bildschirmschoner und Kennwortschutz und anschließend gegebenenfalls, wie Gruppenrichtlinieneinstellungen für Laptop-/Desktopbenutzer umgepasst werden.

Windows 10 Pro oder Enterprise auf Surface Hub 2 verhindert, dass der Bildschirm mit Touch-, Maus- und Tastaturaktionen sowie der integrierten Erkennung von Personenbelegung (Doppler) in den Ruhezustand geht. Die Erkennung von Personenbelegung ist standardmäßig aktiviert, kann jedoch bei Bedarf in UEFI deaktiviert werden, indem die Geräteoption im Surface UEFI Configurator-Tool entweder als Teil der anfänglichen Migration oder durch Erstellen und Anwenden eines späteren UEFI-Konfigurationspakets umgeschaltet wird. 

**Energieverwaltung: Einstellungen für bildschirm- und PC-Ruhezustand**

1. Wählen **Sie**  >  **Starteinstellungen**  >  **System**  >  **power & sleep aus.**

2. Legen Sie den Schieberegler für den Energiemodus auf **Beste Leistung .**

3. Konfigurieren Sie Bildschirm- und Ruhezustandswerte nach Ihren Vorstellungen, während gleichzeitig die Erkennung von Doppler-Anwesenheitserkennungen verwendet wird, die das Gerät aufweckt, wenn Bewegungen erkannt werden. Daher wird empfohlen, bildschirm nach **2** Stunden und den PC nach 4 Stunden auf Deaktivieren **zu setzen.**

**Energieverwaltung: Bildschirmschoner**

1. Suchen Sie **nach Sperrbildschirm,** und öffnen Sie **Sperrbildschirmeinstellungen.**

2. Konfigurieren **Sie Bildschirmtimeouteinstellungen** und **Bildschirmschonereinstellungen** nach Ihren Wünschen. Empfohlene Standardwerte sind:

   - Bildschirmschoner für (Keine) oder einen Bildschirmschoner Ihrer Wahl.
   - Wartezeit bis zu 15 Minuten.
   - Zeigen Sie beim Fortsetzen den Anmeldebildschirm an.


**Energieverwaltung: Gruppenrichtlinie**

Bevor Sie das folgende Verfahren ausführen, sollten Sie bei Ihrer IT-Abteilung nach Genehmigung suchen, um ein Surface Hub 2S-Gerät von der globalen Energieverwaltungsrichtlinie auszuschließen. Einige Energieverwaltungseinstellungen können die Anwesenheitserkennungsfunktion deaktivieren.

1. Suchen Sie **nach Software Center,** und öffnen Sie es.

2. Wählen Sie **Optionen**aus.

3. Erweitern Sie **die Energieverwaltung,** und wählen Sie Energieeinstellungen aus meiner IT-Abteilung nicht auf **diesen Computer anwenden aus.**

   ![Softwareeinstellungen](images/soft-cntr.png)

### <a name="storage-sense"></a>Speicheroptimierung

Der Surface Hub 2 verfügt über eine 128-GB-SSD für lokalen Speicher. Daher ist es erforderlich, die Verwendung von Speichereinsparungen während der normalen Nutzung zu berücksichtigen.  So konfigurieren Sie Speichersinn:

1.  Suchen Sie **nach Speichereinstellungen**, die unter **Systemeinstellungen gefunden werden.**

2.  Wählen **Sie unter Einstellungen**die Option **Speichersinn aktivieren aus,** um die Seite **Speichereinstellungen** zu öffnen.

3.  Aktivieren Sie Speichersinn auf **Ein.**

4.  Wählen **Sie Speichersinn konfigurieren aus, oder führen** Sie ihn jetzt aus, und konfigurieren Sie die Einstellungen so, dass Dateien so weit wie möglich online bleiben (aufgrund des begrenzten Speicherplatzes auf dem Laufwerk).

Empfohlene Einstellungen:

- Führen Sie Speichersinn = jeden Tag aus.
- Löschen temporärer Dateien, die meine Apps nicht verwenden = Alle 14 Tage (mindestens).
- Löschen Sie Dateien in meinem Downloadordner, wenn sie seit mehr als 30 Tagen dort sind.
- OneDrive: Inhalte werden nur online verfügbar, wenn sie nicht länger als = 30 Tage geöffnet werden.

### <a name="tablet-mode"></a>Tabletmodus

Aktivieren Sie den Tablet-Modus, wenn dies für Barrierefreiheitsanforderungen gewünscht ist.


### <a name="sound-settings"></a>Soundeinstellungen

1. Suchen Sie nach **Sounds-Einstellungen,** und öffnen Sie diese Seite.

2. Wählen **Sie rechts die Soundsteuerung** aus, und wählen Sie die Registerkarte **Sounds** aus.

3. Legen **Sie unter Programmereignisse** **Geräte verbinden und** **Gerätetrennung auf** Keine **festlegen.**

### <a name="silence-notifications"></a>Stille Benachrichtigungen

1. Suchen Sie nach **Fokushilfe,** und öffnen Sie diese Seite.

2. Wählen Sie **nur Alarme aus.** Dadurch werden flyouts für konstante Benachrichtigungen vermieden.

### <a name="disk-cleanup"></a>Datenträgerbereinigung

1. Suchen Sie **nach Datenträgerbereinigung,** und öffnen Sie diese App.

2. Wählen **Sie unter Zu löschende**Dateien die Dateien aus, die Sie löschen möchten. 

3. Wählen Sie **außerdem Systemdateien bereinigen aus.**

## <a name="complete-and-verify"></a>Abschließen und Überprüfen

1. Suchen Sie nach allen Windows-Updates, und installieren Sie sie.

2. Aktualisieren der Gruppenrichtlinie.

   1. Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten **gpupdate /force /boot /wait:0 ein.**
   
3. Starten Sie das Gerät neu.

4. Überprüfen Sie Taskleisten-Apps.

   - Connect App
   - Sperrsymbol
   - Ausschneiden und skizzieren
   - Teams (falls zutreffend)
   - Office Apps (falls zutreffend)
   - Surface App
   - Whiteboard
    
5. Überprüfen Sie die Anwesenheitserkennung.

   - Die Anwesenheitserkennung ist ein grünes Symbol in der Systemleiste.
    
6. Überprüfen Sie, ob die Projektierung auf diesen PC mit der Connect App aktiviert ist. Führen Sie nach dem  **Konfigurieren von Project für diese PC-Einstellungen** die Connect-App mindestens einmal aus. (Anschließend muss die Connect-App nicht ausgeführt werden, um auf Surface Hub zu projiziert werden.)

7. Überprüfen Sie die Energie- und Ruhezustandseinstellungen.

    - Bildschirmschoner: 15 Minuten, festgelegt auf (keine), Mystify oder Blank; stellen Sie sicher, dass das Kontrollkästchen zum Erfordern eines Kennworts aktiviert ist.
    - Bildschirm: **Nach 2 Stunden deaktivieren.**
    - PC: **Nach 4 Stunden deaktivieren.**
    
8. Überprüfen Sie, ob Windows Hello funktioniert.

9. Überprüfen Sie, ob die Synchronisierung Ihrer Einstellungen deaktiviert ist.

10. Überprüfen Sie Start-Apps.

> [!TIP]
> Nach der Installation und Konfiguration von Windows 10 kann Surface Hub 2S wie jedes andere Windows 10-Gerät verwaltet werden.

## <a name="related-topics"></a>Verwandte Themen

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2</a>
