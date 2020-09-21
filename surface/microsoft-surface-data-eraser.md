---
title: Microsoft Surface Data Eraser (Surface)
description: Erfahren Sie, wie Ihnen das Microsoft Surface Data Eraser-Tool helfen kann, Daten auf Surface-Geräten sicher zu löschen.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: Tool, USB, Daten, löschen
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 09/18/2020
ms.openlocfilehash: dc1a9b4480f37af6d74699a2e693ef8d5318da76
ms.sourcegitcommit: 8bd03770279d5e53446436781226ffd51eeec916
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "11029229"
---
# Microsoft Surface Data Eraser


Erfahren Sie, wie Ihnen das Microsoft Surface Data Eraser-Tool helfen kann, Daten auf Surface-Geräten sicher zu löschen.

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) ist ein Tool, das von einem USB-Stick aus startet und eine sichere Löschung aller Daten von einem kompatiblen Surface-Gerät ermöglicht. Ein Microsoft Surface Data Eraser-USB-Stick erfordert nur die Möglichkeit, von einem USB-Stick aus zu starten. Der USB-Stick kann mit dem bereitgestellten Assistenten Microsoft Surface Data Eraser Wrapper leicht erstellt werden und ist einfach zu verwenden. Dank der einfachen Grafikschnittstelle ist keine Befehlszeile erforderlich. Weitere Informationen zu den Datenlöschfunktionen und anderen Methoden, die Microsoft während des Reparaturprozesses für Surface verwendet, finden Sie unter [Schutz Ihrer Daten beim Einschicken des Surface zur Reparatur](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Microsoft Surface Data Eraser verwendet den Formatierungsbefehl NVM Express (NVMe) zum Löschen von Daten, wie in [NIST Special Publication 800-88 Revision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) autorisiert. 

Kompatible Surface-Geräte:

- DGM-Buch (alle Editionen)
- Surface Go (alle Editionen)
- Surface pro X (alle Editionen)
- Surface Laptop (alle Editionen)
- Surface Studio (alle Editionen)
- Surface pro 2 und höher
- Windows 10 pro und Enterprise auf Surface Hub 2

Einige Szenarien, in denen Microsoft Surface Data Eraser hilfreich sein könnte, sind:

-   Vorbereiten eines Surface-Geräts für die Reparatureinsendung

-   Außerbetriebnahme eines Surface-Geräts, das nicht mehr für Unternehmens- oder Organisationszwecke verwendet werden soll

-   Wiederverwenden eines Surface-Geräts für die Verwendung in einer neuen Abteilung oder durch einen neuen Benutzer

-   Standardverfahren beim Erstellen eines neuen Image für Geräte mit vertraulichen Daten

>[!NOTE]
>Drittanbietergeräte, Surface-Geräte mit Windows RT (einschließlich Surface und Surface2) und Surface Pro sind nicht mit Microsoft Surface Data Eraser kompatibel.

>[!NOTE]
>Da die Möglichkeit zum Starten mit USB erforderlich ist, um Microsoft Surface Data Eraser auszuführen, wird das Microsoft Surface Data Eraser-Tool nicht funktionieren, wenn das Gerät nicht zum Starten vom USB-Stick aus konfiguriert ist oder wenn das Gerät nicht erfolgreich starten oder einen POST durchführen kann.

>[!NOTE]
>DGM-Daten Radierer auf Surface Studio und Surface Studio 2 kann bis zu 6 Minuten dauern, bis die datenträgerlöschung in WinPE ausgeführt werden kann.


## Erstellen eines Microsoft Surface Data Eraser-USB-Sticks


Um einen Microsoft Surface Data Eraser-USB-Stick zu erstellen, müssen Sie zunächst das Microsoft Surface Data Eraser-Einrichtungstool aus dem Microsoft Download Center über den Link am Anfang dieses Artikels installieren. Ein Surface-Gerät ist nicht erforderlich, um den USB-Stick zu *erstellen*. Führen Sie diese Schritte aus, um das Microsoft Surface Data Eraser-Erstellungstool zu installieren, nachdem Sie die Installationsdatei auf den Computer heruntergeladen haben:

1.  Führen Sie die DataEraserSetup.msi Installationsdatei aus, die Sie aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703)heruntergeladen haben.

2.  Aktivieren Sie das Kontrollkästchen, um die Bestimmungen des Lizenzvertrags zu akzeptieren, und klicken Sie dann auf **Installieren**.

3.  Klicken Sie auf **Fertig stellen**, um das Microsoft Surface Data Eraser-Einrichtungsfenster zu schließen.

Nachdem das Erstellungstool installiert ist, führen Sie die folgenden Schritte aus, um einen Microsoft Surface Data Eraser-USB-Stick zu erstellen. Bevor Sie diese Schritte beginnen, müssen Sie sicherstellen, dass Sie einen USB-3.0-Speicherstick mit 4 GB oder mehr an den Computer angeschlossen haben.

1. Starten Sie Microsoft Surface Data Eraser über das Startmenü oder den Startbildschirm.

2. Klicken Sie auf **Erstellen**, um mit der Microsoft Surface Data Eraser-USB-Erstellung zu beginnen. 

3. Klicken Sie auf **Start**, um zu bestätigen, dass Sie einen USB-Speicherstick mit mindestens 4GB angeschlossen haben, wie in Abbildung1 dargestellt ist.

   ![Starten des Microsoft Surface Data Eraser-Tools](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Abbildung1. Starten des Microsoft Surface Data Eraser-Tools*
4.  Wählen Sie **x64** für die meisten Surface-Geräte oder  **ARM64** für Surface pro X auf der Seite **Architektur Auswahl** aus, wie in Abbildung 2 dargestellt. Wählen Sie **Weiter** aus.

    ![Architektur Auswahl](images/dataeraser-arch.png "Architecture Selection")<br>
       *Abbildung2. Gerätearchitektur auswählen*
    

4. Wählen Sie auf der Auswahlseite des **USB-Thumb-Laufwerks** das USB-Laufwerk Ihrer Wahl aus, wie in Abbildung 3 gezeigt, und klicken Sie dann auf **Start** , um mit dem USB-Erstellungsprozess zu beginnen. Das Laufwerk, das Sie auswählen, wird formatiert, und alle vorhandenen Daten auf dem Laufwerk gehen verloren.

   >[!NOTE]
   >Wenn die Starttaste deaktiviert ist, sollten Sie sicherstellen, dass der Wechseldatenträger eine Gesamtkapazität von mindestens 4 GB hat.
  
   ![USB-Laufwerkauswahl](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Abbildung3. USB-Laufwerkauswahl*

5. Nach Abschluss des Erstellungsprozesses wurde das USB-Laufwerk formatiert, und alle Binärdateien wurden auf das USB-Laufwerk kopiert. Klicken Sie auf **Erfolg**.

6. Wenn der Bildschirm **Glückwunsch** angezeigt wird, können Sie den USB-Speicherstick auswerfen und entfernen. Dieser USB-Speicherstick kann jetzt in einem Surface-Gerät eingefügt werden, gestartet werden und alle Daten auf dem Gerät zurückgesetzt werden. Klicken Sie auf **Fertig** stellen, um den USB-Erstellungsprozess abzuschließen, wie in Abbildung 4 zu sehen ist.

   ![Surface Data Eraser-USB-Erstellung](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Abbildung 4. Abschließen der Microsoft Surface Data Eraser-USB-Erstellung*

7. Klicken Sie auf **X**, um Microsoft Surface Data Eraser zu schließen.

## Verwenden eines Microsoft Surface Data Eraser-USB-Sticks


Nachdem Sie einen Microsoft Surface Data Eraser-USB-Stick erstellt haben, können Sie mithilfe des folgenden Verfahrens ein unterstütztes Surface-Gerät über den USB-Stick starten:

1. Schließen Sie den startbaren Microsoft Surface Data Eraser-USB-Stick an das unterstützte Surface-Gerät an.

2. Starten Sie das Surface-Gerät über den Microsoft Surface Data Eraser-USB-Stick. Gehen Sie zum Starten des Geräts vom USB-Stick folgendermaßen vor:

   a. Schalten Sie das Surface-Gerät aus.

   b. Halten Sie die **Leiser**-Taste gedrückt.

   c. Drücken Sie die **Ein/Aus**-Taste und lassen Sie sie dann los.

   d. Lassen Sie die **Leiser**-Taste los.
    
   >[!NOTE]
   >Wenn Ihr Gerät mit diesen Schrittennicht mit USB nicht startet, müssen Sie möglicherweise die Option **Enable Alternate Boot Sequence** in der Surface-UEFI aktivieren. Weitere Informationen zur Surface UEFI-Startkonfiguration finden Sie unter [Verwalten der Surface UEFI-Einstellungen](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Wenn das Surface-Gerät bootet, wird eine **SoftwareLicenseTerms** -Textdatei angezeigt, wie in Abbildung 5 zu sehen ist.

   ![Starten des Microsoft Surface Data Eraser-USB-Sticks](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Abbildung5. Starten des Microsoft Surface Data Eraser-USB-Sticks*

4. Lesen Sie die Softwarelizenzbedingungen, und schließen Sie die Editor-Datei.

5. Nehmen Sie die Softwarelizenzbedingungen an oder lehnen Sie diese ab, indem Sie **Annehmen** oder **Ablehnen** eingeben. Sie müssen die Lizenzbedingungen akzeptieren, um den Vorgang fortsetzen zu können.

6. Das Microsoft Surface Data Eraser-Skript erkennt die Speichergeräte, die in Ihrem Surface-Gerät vorhanden sind, und zeigt die Details des systemeigenen Speichergeräts an. Um den Vorgang fortzusetzen, drücken Sie **Y** (diese Aktion führt Microsoft Surface Data Eraser aus und entfernt alle Daten vom Speichergerät), oder drücken Sie **N** (diese Aktion fährt das Gerät herunter, ohne Daten zu entfernen).

   >[!NOTE]
   >Das Microsoft Surface Data Eraser-Tool löscht alle Daten, einschließlich Windows-Betriebssystemdateien, die zum Starten des Geräts erforderlich sind, auf sichere Weise, sodass sie nicht wiederhergestellt werden können. Um ein Surface-Gerät zu starten, das mit Microsoft Surface Data Eraser bereinigt wurde, müssen Sie zunächst das Windows-Betriebssystem erneut installieren. Um Daten von einem Surface-Gerät zu entfernen, ohne das Windows-Betriebssystem zu entfernen, können Sie die Funktion **PC auffrischen** verwenden. Allerdings verhindert dies nicht, dass Ihre Daten mit forensischen Funktionen oder Datenwiederherstellungsfunktionen wiederhergestellt werden. Weitere Informationen finden Sie unter [Wiederherstellungsoptionen unter Windows10](https://support.microsoft.com/help/12415/windows-10-recovery-options).

   ![Die zu löschende Partition wird angezeigt.](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Abbildung6. Die Partition, die gelöscht werden soll, wird im Microsoft Surface Data Eraser-Tool angezeigt.*

7. Wenn Sie **Y** in Schritt 6 gedrückt haben, wird aufgrund der Löschung von Daten ein weiteres Dialogfeld angezeigt, um die Auswahl zu bestätigen.

8. Klicken Sie auf die Schaltfläche **Ja**, um mit dem Löschen von Daten auf dem Surface-Gerät fortzufahren.

   >[!NOTE]
   >Wenn Sie Surface Data Eraser auf dem Surface Data Eraser-USB-Laufwerk ausführen, wird eine Protokolldatei im Ordner **SurfaceDataEraserLogs** erstellt.

## Änderungen und Updates

Microsoft Surface Data Eraser wird in regelmäßigen Abständen von Microsoft aktualisiert. Informationen zu den Änderungen, die in jeder neuen Version bereitgestellt werden, finden Sie hier:

### 3.33.139
*Veröffentlichungsdatum: 9. September 2020*

Diese Version von Surface Data Eraser enthält Fehlerbehebungen und fügt Unterstützung für Folgendes hinzu: 

- Erneutes Entwerfen von Architekturen, um die Aktualisierung mit neuen Produktversionen zu verringern
- Benachrichtigung für neue Tool Updates verfügbar
- Telemetrie-Ergänzungen
- Windows 10 pro und Enterprise auf Surface Hub 2


### 3.30.139
*Veröffentlichungsdatum: 11 Mai 2020*

Diese Version von Surface Data Eraser bietet Unterstützung für: 
- DGM-Buch 3
- Surface Go 2
- Neue SSD in Surface go

### 3.28.137
*Veröffentlichungsdatum: 11 Nov 2019* Diese Version von Surface Data Eraser:

- Enthält Fehlerbehebungen

### Version 3.21.137
*Veröffentlichungsdatum: 21 Okt 2019* Diese Version von Surface Data Eraser wird für x86 kompiliert und unterstützt die folgenden Geräte:

- Unterstützt Surface pro 7, Surface pro X und Surface Laptop 3

### Version 3.2.78.0
*Veröffentlichungsdatum: 4 Dez 2018*

Diese Version von Surface Data Eraser:

- Enthält Fehlerbehebungen


### Version 3.2.75.0
*Veröffentlichungsdatum: 12 November 2018*

Diese Version von Surface Data Eraser:

- Unterstützung für Surface Studio 2
- Behebt Probleme mit der SD-Karte

### Version 3.2.69.0
*Veröffentlichungsdatum: 12 Oktober 2018*

Diese Version von Surface Data Eraser bietet Unterstützung für die folgenden Optionen:

- Surface Pro 6
- Surface Laptop 2

### Version 3.2.68.0
Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Go


### Version 3.2.58.0
Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Zusätzliche Speichergeräte (Laufwerke) für Surface pro-und Surface-Laptop Geräte


### Version3.2.46.0
Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Pro mit LTE Advanced


### Version3.2.45.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Book 2

- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 und höher kann verwendet werden, um Surface Pro- oder Surface Laptop-Geräte mit der 1-TB Speicheroption wiederherzustellen, wenn das Gerät zwei separate 512-GB-Volumes anzeigt, oder wenn beim Versuch, Windows 10 bereitzustellen oder zu installieren, Fehler auftreten. Weitere Informationen finden Sie unter [Surface Pro Modell 1796 und Surface Laptop 1TB zeigen zwei Laufwerke an](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives).


### Version3.2.36.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Pro

- Surface Laptop

>[!NOTE]
>Das Microsoft Surface Data Eraser-USB-Laufwerkerstellungstool kann nicht unter Windows10 s ausgeführt werden. Um einen Surface Laptop mit Windows10 S zu löschen, müssen Sie zunächst das Microsoft Surface Data Eraser-USB-Laufwerk auf einem anderen Computer mit Windows10 Pro oder Windows10 Enterprise erstellen.
