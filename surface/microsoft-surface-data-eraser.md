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
ms.date: 05/17/2021
ms.openlocfilehash: d96581cd67e9cd4171fbb745aed4e9b34e2f0627
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576625"
---
# <a name="microsoft-surface-data-eraser"></a>Microsoft Surface Data Eraser

Erfahren Sie, wie Ihnen das Microsoft Surface Data Eraser-Tool helfen kann, Daten auf Surface-Geräten sicher zu löschen.

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) ist ein Tool, das von einem USB-Stick aus startet und eine sichere Löschung aller Daten von einem kompatiblen Surface-Gerät ermöglicht. Ein Microsoft Surface Data Eraser-USB-Stick erfordert nur die Möglichkeit, von einem USB-Stick aus zu starten. Der USB-Stick kann mit dem bereitgestellten Assistenten Microsoft Surface Data Eraser Wrapper leicht erstellt werden und ist einfach zu verwenden. Dank der einfachen Grafikschnittstelle ist keine Befehlszeile erforderlich. Weitere Informationen zu den Datenlöschfunktionen und anderen Methoden, die Microsoft während des Reparaturprozesses für Surface verwendet, finden Sie unter [Schutz Ihrer Daten beim Einschicken des Surface zur Reparatur](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Microsoft Surface Data Eraser verwendet den Formatierungsbefehl NVM Express (NVMe) zum Löschen von Daten, wie in [NIST Special Publication 800-88 Revision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) autorisiert.

Kompatible Surface-Geräte:

- Surface Book (alle Editionen)
- Surface Go (alle Editionen)
- Surface Pro X (alle Editionen)
- Surface Laptop (alle Editionen)
- Surface Laptop Go
- Surface Studio (alle Editionen)
- Surface Pro 2 und höher
- Surface 3
- Windows 10 Pro und Enterprise auf Surface Hub 2

Einige Szenarien, in denen Microsoft Surface Data Eraser hilfreich sein könnte, sind:

- Bereiten Sie ein Surface-Gerät vor, das zur Reparatur gesendet wird.
- AußerBetriebsetzen eines zu entfernende Surface-Geräts. Unternehmens- oder Organisationsnutzung.
- Verwenden Sie ein Surface-Gerät erneut für die Verwendung in einer neuen Abteilung oder für die Verwendung durch einen neuen Benutzer.
- Standardpraxis beim Durchführen einer neu bildverarbeitung für Geräte, die mit vertraulichen Daten verwendet werden.

>[!NOTE]
>Drittanbietergeräte, Surface-Geräte mit Windows RT (einschließlich Surface und Surface2) und Surface Pro sind nicht mit Microsoft Surface Data Eraser kompatibel.

>[!NOTE]
>Da die Möglichkeit zum Starten mit USB erforderlich ist, um Microsoft Surface Data Eraser auszuführen, wird das Microsoft Surface Data Eraser-Tool nicht funktionieren, wenn das Gerät nicht zum Starten vom USB-Stick aus konfiguriert ist oder wenn das Gerät nicht erfolgreich starten oder einen POST durchführen kann.

>[!NOTE]
>Surface Data Eraser auf Surface Studio und Surface Studio 2 kann bis zu 6 Minuten dauern, bis winPE gestartet wird, bevor die Datenträgerlöschung erfolgen kann.

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>Erstellen eines Microsoft Surface Data Eraser-USB-Sticks

Um einen Microsoft Surface Data Eraser-USB-Stick zu erstellen, müssen Sie zunächst das Microsoft Surface Data Eraser-Einrichtungstool aus dem Microsoft Download Center über den Link am Anfang dieses Artikels installieren. Ein Surface-Gerät ist nicht erforderlich, um den USB-Stick zu *erstellen*. Führen Sie diese Schritte aus, um das Microsoft Surface Data Eraser-Erstellungstool zu installieren, nachdem Sie die Installationsdatei auf den Computer heruntergeladen haben:

1. Führen Sie DataEraserSetup.msi Installationsdatei aus, die Sie aus dem [Microsoft Download Center heruntergeladen haben.](https://www.microsoft.com/download/details.aspx?id=46703)

2. Aktivieren Sie das Kontrollkästchen, um die Bestimmungen des Lizenzvertrags zu akzeptieren, und klicken Sie dann auf **Installieren**.

3. Klicken Sie auf **Fertig stellen**, um das Microsoft Surface Data Eraser-Einrichtungsfenster zu schließen.

Nachdem das Erstellungstool installiert ist, führen Sie die folgenden Schritte aus, um einen Microsoft Surface Data Eraser-USB-Stick zu erstellen. Bevor Sie diese Schritte beginnen, müssen Sie sicherstellen, dass Sie einen USB-3.0-Speicherstick mit 4 GB oder mehr an den Computer angeschlossen haben.

1. Starten Sie Microsoft Surface Data Eraser über das Startmenü oder den Startbildschirm.

2. Klicken Sie auf **Erstellen**, um mit der Microsoft Surface Data Eraser-USB-Erstellung zu beginnen.

3. Klicken Sie auf **Start**, um zu bestätigen, dass Sie einen USB-Speicherstick mit mindestens 4GB angeschlossen haben, wie in Abbildung1 dargestellt ist.

   ![Starten des Microsoft Surface Data Eraser-Tools](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Abbildung1. Starten des Microsoft Surface Data Eraser-Tools*
4. Wählen **Sie x64** für die meisten Surface-Geräte oder **** **ARM64** für Surface Pro X auf der Seite Architekturauswahl aus, wie in Abbildung 2 dargestellt. Wählen Sie **Weiter** aus.

    ![Architekturauswahl](images/dataeraser-arch.png "Architecture Selection")<br>
       *Abbildung2. Auswählen der Gerätearchitektur*

5. Wählen Sie das USB-Laufwerk Ihrer Wahl auf der Seite USB-Miniaturlaufwerkauswahl aus, wie in Abbildung 3 dargestellt, und klicken Sie dann auf **Start,** um mit dem **USB-Erstellungsprozess** zu beginnen. Das Laufwerk, das Sie auswählen, wird formatiert, und alle vorhandenen Daten auf dem Laufwerk gehen verloren.

   >[!TIP]
   >Wenn die Starttaste deaktiviert ist, sollten Sie sicherstellen, dass der Wechseldatenträger eine Gesamtkapazität von mindestens 4 GB hat.
  
   ![USB-Laufwerkauswahl](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Abbildung3. USB-Laufwerkauswahl*

6. Nach Abschluss des Erstellungsprozesses wurde das USB-Laufwerk formatiert, und alle Binärdateien wurden auf das USB-Laufwerk kopiert. Klicken Sie auf **Erfolg**.

7. Wenn der Bildschirm **Glückwunsch** angezeigt wird, können Sie den USB-Speicherstick auswerfen und entfernen. Dieser USB-Speicherstick kann jetzt in einem Surface-Gerät eingefügt werden, gestartet werden und alle Daten auf dem Gerät zurückgesetzt werden. Klicken **Sie auf Vollständig,** um den USB-Erstellungsprozess wie in Abbildung 4 dargestellt zu beenden.

   ![Surface Data Eraser-USB-Erstellung](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Abbildung 4. Abschließen der Microsoft Surface Data Eraser-USB-Erstellung*

8. Klicken Sie auf **X**, um Microsoft Surface Data Eraser zu schließen.

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>Verwenden eines Microsoft Surface Data Eraser-USB-Sticks

Nachdem Sie einen Microsoft Surface Data Eraser-USB-Stick erstellt haben, können Sie mithilfe des folgenden Verfahrens ein unterstütztes Surface-Gerät über den USB-Stick starten:

1. Schließen Sie den startbaren Microsoft Surface Data Eraser-USB-Stick an das unterstützte Surface-Gerät an.

2. Starten Sie das Surface-Gerät über den Microsoft Surface Data Eraser-USB-Stick. Gehen Sie zum Starten des Geräts vom USB-Stick folgendermaßen vor:

   a. Schalten Sie das Surface-Gerät aus.
   b. Halten Sie die **Leiser**-Taste gedrückt.
   c. Drücken Sie die **Ein/Aus**-Taste und lassen Sie sie dann los.
   d. Lassen Sie die **Leiser**-Taste los.

   >[!TIP]
   >Wenn Ihr Gerät mit diesen Schrittennicht mit USB nicht startet, müssen Sie möglicherweise die Option **Enable Alternate Boot Sequence** in der Surface-UEFI aktivieren. Weitere Informationen zur Surface UEFI-Startkonfiguration finden Sie unter [Verwalten der Surface UEFI-Einstellungen](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Wenn das Surface-Gerät gestartet wird, wird eine **SoftwareLicenseTerms-Textdatei** angezeigt, wie in Abbildung 5 dargestellt.

   ![Starten des Microsoft Surface Data Eraser-USB-Sticks](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Abbildung5. Starten des Microsoft Surface Data Eraser-USB-Sticks*

4. Lesen Sie die Softwarelizenzbedingungen, und schließen Sie die Editor-Datei.

5. Nehmen Sie die Softwarelizenzbedingungen an oder lehnen Sie diese ab, indem Sie **Annehmen** oder **Ablehnen** eingeben. Sie müssen die Lizenzbedingungen akzeptieren, um den Vorgang fortsetzen zu können.

6. Das Microsoft Surface Data Eraser-Skript erkennt die Speichergeräte, die in Ihrem Surface-Gerät vorhanden sind, und zeigt die Details des systemeigenen Speichergeräts an. Um den Vorgang fortzusetzen, drücken Sie **Y** (diese Aktion führt Microsoft Surface Data Eraser aus und entfernt alle Daten vom Speichergerät), oder drücken Sie **N** (diese Aktion fährt das Gerät herunter, ohne Daten zu entfernen).

   >[!CAUTION]
   >Das Microsoft Surface Data Eraser-Tool löscht alle Daten, einschließlich Windows-Betriebssystemdateien, die zum Starten des Geräts erforderlich sind, auf sichere Weise, sodass sie nicht wiederhergestellt werden können. Um ein Surface-Gerät zu starten, das mit Microsoft Surface Data Eraser bereinigt wurde, müssen Sie zunächst das Windows-Betriebssystem erneut installieren. Um Daten von einem Surface-Gerät zu entfernen, ohne das Windows-Betriebssystem zu entfernen, können Sie die Funktion **PC auffrischen** verwenden. Allerdings verhindert dies nicht, dass Ihre Daten mit forensischen Funktionen oder Datenwiederherstellungsfunktionen wiederhergestellt werden. Weitere Informationen finden Sie unter [Wiederherstellungsoptionen unter Windows10](https://support.microsoft.com/help/12415/windows-10-recovery-options).

   ![Die zu löschende Partition wird angezeigt.](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Abbildung6. Die Partition, die gelöscht werden soll, wird im Microsoft Surface Data Eraser-Tool angezeigt.*

7. Wenn Sie **Y** in Schritt 6 gedrückt haben, wird aufgrund der Löschung von Daten ein weiteres Dialogfeld angezeigt, um die Auswahl zu bestätigen.

8. Klicken Sie auf die Schaltfläche **Ja**, um mit dem Löschen von Daten auf dem Surface-Gerät fortzufahren.

   >[!TIP]
   >Wenn Sie Surface Data Eraser auf dem Surface Data Eraser-USB-Laufwerk ausführen, wird eine Protokolldatei im Ordner **SurfaceDataEraserLogs** erstellt.

## <a name="changes-and-updates"></a>Änderungen und Updates

Microsoft Surface Data Eraser wird in regelmäßigen Abständen von Microsoft aktualisiert. Informationen zu den Änderungen, die in jeder neuen Version bereitgestellt werden, finden Sie hier:

### <a name="3391390"></a>3.39.139.0

*Veröffentlichungsdatum: 13. April 2021*

Diese Version von Surface Data Eraser umfasst:

- Unterstützung für Surface Laptop 4

### <a name="2341390"></a>2.34.139.0

*Veröffentlichungsdatum: 15. Januar 2021*

Diese Version von Surface Data Eraser:

- Enthält Fehlerbehebungen

### <a name="333139"></a>3.33.139

*Veröffentlichungsdatum: 9. September 2020*

Diese Version von Surface Data Eraser enthält Fehlerbehebungen und bietet Unterstützung für: 

- Neuentwurf der Architektur, um die Notwendigkeit von Updates mit neuen Produktversionen zu reduzieren
- Benachrichtigung für neue Toolupdates verfügbar
- Telemetrie-Ergänzungen
- Windows 10 Pro und Enterprise auf Surface Hub 2

### <a name="330139"></a>3.30.139

*Veröffentlichungsdatum: 11. Mai 2020*

Diese Version von Surface Data Eraser bietet Unterstützung für:

- Surface Book 3
- Surface Go 2
- Neue SSD in Surface Go

### <a name="328137"></a>3.28.137

*Veröffentlichungsdatum: 11. Nov 2019*

Diese Version von Surface Data Eraser:

- Enthält Fehlerbehebungen

### <a name="version-321137"></a>Version 3.21.137

*Veröffentlichungsdatum: 21. Okt 2019*

Diese Version von Surface Data Eraser ist für x86 kompiliert und bietet Unterstützung für die folgenden Geräte:

- Surface Pro 7, Surface Pro X und Surface Laptop 3

### <a name="version-32780"></a>Version 3.2.78.0

*Veröffentlichungsdatum: 4. Dezember 2018*

Diese Version von Surface Data Eraser:

- Enthält Fehlerbehebungen

### <a name="version-32750"></a>Version 3.2.75.0

*Veröffentlichungsdatum: 12. November 2018*

Diese Version von Surface Data Eraser:

- Fügt Unterstützung für Surface Studio 2 hinzu
- Behebt Probleme mit der SD-Karte

### <a name="version-32690"></a>Version 3.2.69.0

*Veröffentlichungsdatum: 12. Oktober 2018*

Diese Version von Surface Data Eraser bietet Unterstützung für Folgendes:

- Surface Pro 6
- Surface Laptop 2

### <a name="version-32680"></a>Version 3.2.68.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Go

### <a name="version-32580"></a>Version 3.2.58.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Zusätzliche Speichergeräte (Laufwerke) für Surface Pro und Surface Laptop Geräte

### <a name="version-32460"></a>Version3.2.46.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Pro mit LTE Advanced

### <a name="version-32450"></a>Version3.2.45.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Book 2
- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 und höher kann verwendet werden, um Surface Pro- oder Surface Laptop-Geräte mit der 1-TB Speicheroption wiederherzustellen, wenn das Gerät zwei separate 512-GB-Volumes anzeigt, oder wenn beim Versuch, Windows 10 bereitzustellen oder zu installieren, Fehler auftreten. Weitere Informationen finden Sie unter [Surface Pro Modell 1796 und Surface Laptop 1TB zeigen zwei Laufwerke an](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives).

### <a name="version-32360"></a>Version3.2.36.0

Diese Version von Microsoft Surface Data Eraser fügt Unterstützung für Folgendes hinzu:

- Surface Pro
- Surface Laptop

>[!NOTE]
>Das Microsoft Surface Data Eraser-USB-Laufwerkerstellungstool kann nicht unter Windows10 s ausgeführt werden. Um einen Surface Laptop mit Windows10 S zu löschen, müssen Sie zunächst das Microsoft Surface Data Eraser-USB-Laufwerk auf einem anderen Computer mit Windows10 Pro oder Windows10 Enterprise erstellen.
