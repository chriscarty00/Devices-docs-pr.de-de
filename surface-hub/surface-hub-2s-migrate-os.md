---
title: Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2
description: In diesem Artikel wird beschrieben, wie Sie aus dem Windows 10-Team auf Surface Hub 2 zu Windows 10 pro oder Windows 10 Enterprise migrieren.
keywords: Surface Hub-Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 713bd2e76f144b4dca7c0fad5c584b06ea12b0b5
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154137"
---
# Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2

Surface Hub 2S ist mit dem Windows 10-Team vorinstalliert. Diese angepasste Edition von Windows 10 wurde entwickelt, um die Zusammenarbeit in Besprechungsraum Umgebungen zu vereinfachen. Sie haben jetzt die Möglichkeit, Windows 10 pro oder Enterprise zu verwenden, um Surface Hub 2S ähnlich wie jeden anderen PC zu verwenden. 

> [!IMPORTANT]
>Im Gegensatz zu einem typischen Upgrade oder einer Migration erfordert dieser Vorgang, wie in diesem Artikel beschrieben, eine normative Vorgehensweise. Überprüfen Sie die [Lösungskomponenten](#solution-components) und den [Migrations-und Installations Workflow,](#migration-and-installation-workflow-summary) bevor Sie fortfahren.


> [!NOTE]
> Wenn Sie Windows 10 pro oder Enterprise installieren, benötigen Sie eine neue Lizenz, die von Ihrer vorhandenen Windows 10-Team Lizenz getrennt ist. 


Starten Sie die Migration aus dem Windows 10-Team mithilfe eines separaten PCs und dem herunterladbaren Tool *Surface UEFI-Konfigurator*. Verwenden Sie das Tool zum Erstellen eines Pakets, das eine neue UEFI-Einstellung enthält, die Sie auf Surface Hub 2S anwenden.  

Die Oberflächen UEFI-Konfiguration funktioniert als Schnittstelle in Surface Enterprise Management Mode (Semm). Es wurde entwickelt, um die zentralisierte Verwaltung von Firmware-Einstellungen auf Surface-Geräten in einer Unternehmensumgebung zu vereinfachen. Weitere Informationen finden Sie in der [Dokumentation zu Microsoft Semm](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 

## Lösungskomponenten

- Surface Hub 2S-Gerät mit Windows 10 Team-Betriebssystem
- Separates Gerät mit Windows 10
- Surface UEFI Configurator-Tool zum Erstellen des Semm-Pakets
- Windows 10 pro-oder Enterprise-Betriebssystemabbild, Version 1903 oder höher
- Zwei USB-Laufwerke mit 16 GB Speicher, FAT32-Format
- Die Treiber und die Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2 Microsoft Windows Installer (MSI)-Datei
- Internetverbindung
- Imaging-Lösung (optional)

 
## Zusammenfassung der Migrations-und Installations Workflows

| Schritt  | Aktion                                                                                                 | Zusammenfassung                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Überprüfen Sie, ob die UEFI-Version auf Surface Hub 2S die Mindestanforderungen erfüllt.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Stellen Sie sicher, dass die UEFI-Version 694.2938.768.0 oder höher ist.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Laden Sie Surface UEFI Configurator und Surface Hub 2-Treiber und-Firmware herunter.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Wählen Sie auf der Seite [**Surface Tools für IT**](https://www.microsoft.com/download/details.aspx?id=46703) die Option **Download**aus. Wählen Sie dann den Surface UEFI-Konfigurator aus, und laden Sie ihn herunter **. MSI-Datei** und installieren Sie Sie auf einem separaten PC. Laden Sie die [Treiber und die Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2 MSI-Datei](https://www.microsoft.com/download/details.aspx?id=101974)herunter. Speichern Sie die Datei zur Verwendung in Schritt 5. |
| 3 | [Vorbereiten des Semm-Zertifikats](#prepare-the-semm-certificate)                                                                          | Bereiten Sie das für die Ausführung des Surface UEFI-Konfigurators erforderliche Zertifikat vor. Oder verwenden Sie das aktuelle Zertifikat.                                                                                                                                                                                                                                                                                                      |
| 4 | [SEMM-Paket erstellen.](#create-a-semm-package)                                                                               | Starten Sie den Surface UEFI Configurator, um ein Semm-Paket auf einem USB-Laufwerk zu erstellen, das die Konfigurationsdateien enthält, die Sie auf Surface Hub 2S anwenden müssen. Kopieren Sie diese Semm-Paketdateien in einen Ordner auf Ihrem PC.                                                                                                                                                                                          |
| 5 | [Vorbereiten des USB-Flashlaufwerks, das Windows 10-Bild, Semm-Paket und Treiber und Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2 enthält.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Erstellen Sie ein einzelnes USB-Laufwerk, das ein Windows 10-Abbild enthält. In diesem Beispiel wird das Laufwerk mit dem Namen *BOOTME*. Fügen Sie Ihre Treiber und Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2 (Schritt 2) und Semm-Paketdateien (Schritt 4) zum *BOOTME* -Laufwerk hinzu.                                                                                                                                                                                                  |
| 6 | [Aktualisieren Sie UEFI auf Surface Hub 2S, um die Betriebssystemmigration zu ermöglichen.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Verwenden Sie das *BOOTME* -Laufwerk zum Booten von Surface Hub 2S im UEFI-Menü, und installieren Sie das Semm-Paket.|
| 7 | [Installieren Sie Windows 10 pro oder Enterprise, Version 1903 oder höher.](#install-windows-10-pro-or-enterprise)                                        | Verwenden Sie das *BOOTME* -Laufwerk, um Windows 10 pro oder Enterprise, Version 1903 oder höher, zu installieren.                                                                                                                                                                                                                                                                                 |
| 8 | [Installieren Sie Treiber und Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Wenn Sie sicherstellen möchten, dass Ihr Gerät über alle neuesten Updates und Treiber verfügt, installieren Sie die [Treiber und die Firmware für Windows 10 pro und Enterprise OS in der MSI-Datei des Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).                                                                                                                                                                                                                                                                                  |
| 9 | [Vollständiges Konfigurieren von Surface Hub 2S als persönliches Produktivitäts Gerät.](#configure-recommended-settings)                                        |  Aktivieren Sie Empfohlene Einstellungen und Anwendungen zur Optimierung von Surface Hub 2S als persönliches Produktivitäts Gerät.                                                                                                                                                                                                                                                                    |

### Überprüfen der UEFI-Version auf Surface Hub 2S erfüllt die Mindestanforderungen

Bevor Sie Surface Hub vom Windows 10-Team auf Windows 10-Desktop migrieren, benötigen Sie eine UEFI-Version, die mindestens *694.2938.768.0*ist.
 
So überprüfen Sie die UEFI-Version auf Ihrem System:

1. Wählen Sie auf der Startseite Surface Hub 2S **Start**aus, und öffnen Sie dann die Surface-app (**alle apps**  >  -**Oberfläche**).

2. Wählen Sie **die Oberfläche** aus, um Informationen zum Surface Hub anzuzeigen, einschließlich der aktuellen UEFI-Version auf dem Gerät. 
   - Wenn die UEFI-Version *694.2938.768.0* oder höher ist, können Sie, wie in der folgenden Abbildung gezeigt, das Semm-Paket erstellen, um die Betriebssystemmigration zu aktivieren.

       ![Screenshot der Seite "Ihre Oberfläche" in der Surface-App](images/shm-fig1.png)
 
   - Wenn die UEFI-Version älter als *694.2938.768.0*ist, rufen Sie mithilfe von Windows Update eine aktuelle Version ab.

So aktualisieren Sie das UEFI mithilfe von Windows Update:

1. Registrieren Sie sich auf dem Surface Hub 2S als **Administrator**. 
    >[!Note]
    > Wenn Sie Ihren Benutzernamen oder Ihr Administratorkennwort nicht kennen, müssen Sie das Gerät zurücksetzen. Weitere Informationen finden Sie unter [Zurücksetzen und Wiederherstellen für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

1. Wechseln Sie zum Update für **alle apps**  >  **Settings**  >  **-Einstellungen und zur Sicherheit**von  >  **Windows Update**, und installieren Sie dann alle Updates. 
1. Starten Sie das Gerät neu. 
1. Überprüfen Sie die UEFI-Version mithilfe der Surface-app. 
2. Wiederholen Sie diese Schritte, bis die UEFI-Version *694.2938.768.0* oder höher ist.
3. Wenn das aktualisierte UEFI nach mehreren versuchen nicht angezeigt wird, überprüfen Sie den **Update Verlauf** , und suchen Sie nach Instanzen von fehlgeschlagenen Firmware-Installationen. Möglicherweise müssen Sie Ihr Gerät zurücksetzen (**Einstellungen**  >  **Aktualisieren & Sicherheits**  >  **Zurücksetzungs Gerät**).

### Herunterladen von Surface UEFI Configurator und Surface Hub 2-Treibern und-Firmware

Auf einem separaten PC:

1. Wählen Sie auf der [Seite Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703)die Option **Download**aus.  
1. Wählen Sie die MSI-Datei des Surface UEFI Configurator aus, und laden Sie Sie herunter, und installieren Sie Sie auf einem separaten PC. Das Tool für die Oberflächen UEFI-Konfiguration kann nicht auf einem Surface Hub 2S ausgeführt werden, während die Windows 10 Team Edition installiert ist.

1. Laden Sie die [MSI-Datei Surface Hub 2 Driver und Firmware Windows Installer](https://www.microsoft.com/download/details.aspx?id=101974)herunter. Sie verwenden diese Datei beim Installieren des neuen Betriebssystems.

### Vorbereiten des Semm-Zertifikats

Wenn Sie noch keine Oberflächen UEFI-Konfiguration verwendet haben, müssen Sie ein Zertifikat vorbereiten. Dieses Zertifikat stellt sicher, dass Sie nach der Registrierung eines Geräts in Semm die UEFI-Einstellungen nur mithilfe von Paketen ändern können, die mit dem genehmigten Zertifikat erstellt wurden. 

Wie Sie ein Zertifikat erhalten, hängt von der Größe oder Komplexität Ihrer Organisation ab:

- Unternehmensorganisationen verwalten in der Regel Ihre eigene Infrastruktur, um Zertifikate entsprechend den standardmäßigen Sicherheitsmethoden zu generieren.

- Mittelständische Unternehmen und andere Personen können Zertifikate von Partneranbietern erhalten. Diese Option wird für Organisationen empfohlen, die nicht über genügend IT-Fachkenntnisse oder ein dediziertes IT-Sicherheitsteam verfügen.

- Sie können auch ein selbstsigniertes Zertifikat mit einem PowerShell-Skript generieren. Weitere Informationen finden Sie unter Anforderungen für das [Surface Enterprise Management Mode-Zertifikat](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Oder Sie können PowerShell verwenden, um ein eigenes Zertifikat zu erstellen. Weitere Informationen finden Sie in der Dokumentation zu [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) .

Das Semm-Paket, das von Surface UEFI Configurator erstellt wird, muss mit einem Zertifikat gesichert werden. Das Zertifikat überprüft die Signatur von Konfigurationsdateien, bevor UEFI-Einstellungen angewendet werden können. Weitere Informationen finden Sie in der [Semm-Dokumentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 
 
### Erstellen eines Semm-Pakets

1. Installieren Sie auf einem separaten PC das Tool Surface UEFI Configurator, das Sie zuvor heruntergeladen haben. 

2. Öffnen Sie die Oberflächen UEFI-Konfiguration, und wählen Sie dann **Start**aus.

   ![Öffnen Sie die Oberflächen UEFI-Konfiguration.](images/shm-fig2.png)
   
3. Wählen Sie **Surface Devices**aus, und wählen Sie dann **weiter**aus.

   ![Wählen Sie Surface Devices aus.](images/shm-fig3.png)
  
4. Wählen Sie **Konfigurationspaket**aus.

   ![Wählen Sie Konfigurationspaket aus.](images/shm-fig4.png)
  
5. Wählen Sie **Zertifikatschutz**aus.

   ![Wählen Sie Zertifikatschutz aus.](images/shm-fig5.png)

   Sie werden aufgefordert, Ihre Datei "Certificate. pfx" hinzuzufügen.

   ![Fügen Sie Ihr Zertifikat hinzu.](images/shm-fig6.png)
   
7. Geben Sie Ihr Zertifikat Kennwort ein, und wählen Sie dann **OK**aus.

   ![Geben Sie Ihr Zertifikat Kennwort ein, und wählen Sie OK aus.](images/shm-fig7.png)

8. Wählen Sie **Kennwortschutz** aus, um ein Kennwort zu Surface UEFI hinzuzufügen. Sie benötigen dieses Kennwort, wenn Sie mit UEFI Booten. Wir *empfehlen dringend* , ein UEFI-Kennwort festzulegen, das Sie auf Surface Hub 2S verwenden werden.

   ![Wählen Sie Kennwortschutz aus.](images/shm-fig8.png)
   
9. Legen Sie ein UEFI-Kennwort ein, und wählen Sie dann **OK**aus.

   > [!IMPORTANT]
   > Speichern Sie das Kennwort an einem sicheren Ort, auf den Ihre IT-Administratoren zugreifen können, die Surface Hub verwalten. Wenn das Kennwort verloren geht, kann es nicht wiederhergestellt werden. 

   ![Geben Sie Ihr UEFI-Kennwort ein.](images/shm-fig9.png)

10. Wählen Sie **Surface Hub 2S**aus, und wählen Sie dann **weiter**aus.

    ![Wählen Sie Surface Hub 2S aus.](images/shm-fig10.png)
   
11. Wählen Sie **Weiter** aus.

    ![Wählen Sie Weiter aus.](images/shm-fig10a.png)

12. Wenn Sie die Installation von Windows 10 pro oder Enterprise zulassen möchten, aktivieren Sie **EnableOsMigration**, und wählen Sie dann **weiter**aus.

    ![Wählen Sie Enable O S Migration aus.](images/shm-fig11.png)
    
    ![Setzen Sie die Aktivierung der Betriebssystem Migration auf ein.](images/shm-fig12.png)

> [!NOTE]
> Nachdem Sie ein Semm-Paket angewendet haben, stehen im UEFI-Menü des Geräts alle UEFI-Einstellungen nicht zur Verfügung (gesperrt). Standardwerte für andere Einstellungen wie **IPv6 für PXE-Start** sind ebenfalls nicht verfügbar. 
>
>Wenn Sie die UEFI-Einstellungen nach Abschluss der Migration ändern möchten, wenden Sie ein weiteres Semm-Paket an, oder heben Sie die Registrierung des Geräts von Semm auf. Wenn Sie ein anderes Semm-Paket anwenden, um die UEFI-Einstellungen zu ändern, müssen Sie beim Erstellen des neuen Semm-Pakets das ursprüngliche Zertifikat verwenden. Verwenden Sie das Tool UEFI-Konfigurator, und geben Sie **EnableOSMigration** aus (nicht aktiviert, wie in den ursprünglichen Migrationsschritten gezeigt).

#### Speichern des Semm-Pakets auf einem USB-Laufwerk

1. Schließen Sie ein USB-Laufwerk an Ihren PC an. 
1. Wählen Sie **Hub 2S**aus, und wählen Sie dann **weiter**aus.

   ![USB auswählen](images/shm-fig13.png)

   > [!WARNING]
   > Alle vorhandenen Daten auf dem USB-Laufwerk werden gelöscht, wenn das Semm-Paket erstellt wird. Bevor Sie das Semm-Paket erstellen, entfernen Sie alle Dateien von dem USB-Laufwerk, das Sie speichern möchten.
   
2. Wählen Sie **Erstellen** aus.

   ![Wählen Sie Erstellen aus.](images/shm-fig14.png)

3. Erfassen Sie einen Screenshot dieser Seite, und wählen Sie dann **Beenden**aus. Ihr Semm-Paket ist nun fertig. Sie enthält das Semm-Paket *DfciUpdate. EDI* und eine Textdatei, die den Semm-Fingerabdruck enthält (die letzten beiden Zeichen des Fingerabdrucks des Zertifikats).

   ![Wählen Sie Ende aus.](images/shm-fig15.png)
   
4. Speichern Sie die letzten beiden Zeichen des Zertifikat Fingerabdrucks. Sie benötigen diese Zeichen, um Semm zu aktivieren, wenn Sie das Paket auf Surface Hub 2S anwenden.

### Vorbereiten eines USB-Flashlaufwerks mit einem Windows 10-Bild, Semm-Paket und Surface Hub 2-Treibern und-Firmware

Sie können ein Windows 10 pro-oder Enterprise-Abbild (Version 1903 oder höher) mithilfe einer der folgenden Optionen installieren:

- Ihre aktuelle Imaging-Lösung.

- [Surface-Bereitstellungs Beschleuniger](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) Verwenden Sie dieses Tool zum Erstellen eines startbaren Windows 10-Bilds. Das Bild kann alle aktuellen Updates für Windows 10, Office, andere von Ihnen ausgewählte apps sowie die erforderlichen Treiber und Firmware enthalten. 

- USB-Speicherstick, der ein Windows 10 pro-oder Enterprise-Bild enthält. Installieren Sie dann [Treiber und Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
Im folgenden Verfahren wird beschrieben, wie Sie ein USB-Flashlaufwerk von Installationsmedien erstellen und dann die Semm-Paketdateien und die Treiber und die Firmware für Windows 10 pro und das Enterprise-Betriebssystem in der MSI-Datei des Surface Hub 2 hinzufügen. Wenn Sie andere Bereitstellungsmethoden verwenden, wechseln Sie zum Abschnitt [Aktualisieren von UEFI auf Surface Hub 2S zum Aktivieren der Betriebssystemmigration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) in diesem Artikel.

> [!NOTE]
> Nachdem Sie die Installation abgeschlossen haben, benötigen Sie eine gültige Lizenz für Windows 10 pro oder Windows 10 Enterprise, die von Ihrer vorhandenen Windows 10-Team Lizenz getrennt ist.

1. Wenn Sie eine Windows 10 pro-Installation erstellen möchten, folgen Sie auf der Seite [**Herunterladen von Windows 10**](https://www.microsoft.com/software-download/windows10) den Anweisungen zum Herunterladen des Medien Erstellungstools. Wenn Sie Windows 10 Enterprise herunterladen möchten, wechseln Sie zum [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).

2. Legen Sie ein neues USB-Speicherlaufwerk ein. 
1. Öffnen Sie das Medien Erstellungstool, wählen Sie **Installationsmedien erstellen**aus, und wählen Sie dann **weiter**aus.

   ![Erstellen Sie Installationsmedien.](images/shm-fig16.png)
   
3. Wählen Sie eine Sprache aus, und wählen Sie dann **Windows 10** und **64-Bit (x64)** aus. Wählen Sie dann **weiter**aus.

   ![Wählen Sie Sprache aus, und wählen Sie Windows 10 und 64-Bit aus. Wählen Sie dann weiter aus.](images/shm-fig17.png)
   
4. Wählen Sie **USB-Flashlaufwerk**aus, und wählen Sie dann **weiter**aus.

   ![Wählen Sie U S B Flash Drive aus, und wählen Sie weiter aus.](images/shm-fig18.png)
   
5. Wenn der Download abgeschlossen ist, wählen Sie **Fertig stellen**aus.

   ![Wählen Sie „Fertig stellen“.](images/shm-fig19.png)
   
6. Kopieren Sie die Semm-Paketdateien und die Treiber und die Firmware für Windows 10 pro und das Enterprise-Betriebssystem auf Surface Hub 2 (die MSI-Datei) in das Stammverzeichnis des USB-Flashlaufwerks (*BOOTME*), das Ihr Windows 10-Abbild enthält. Das BOOTME-USB-Laufwerk enthält:

    - Ihr startbares Windows 10-Abbild
    
    - SEMM-Paketdateien (in das Stammverzeichnis des USB-Laufwerks kopiert).
    
      - *DfciUpdate. EDI*.
      - Textdatei mit dem Semm-Fingerabdruck (In diesem Beispiel ist die Datei *SurfaceUEFI_2020Aug25_1058.txt*.) Der automatisch generierte Datums Zeitstempel entspricht dem Datum, an dem Sie die Datei mithilfe von Surface UEFI Configurator erstellt haben.

   - Treiber und Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Kopieren Sie diese Datei in das Stammverzeichnis des USB-Laufwerks.

### Aktualisieren von UEFI auf Surface Hub 2S zur Aktivierung der Betriebssystemmigration

1. Legen Sie Ihr BOOTME-Laufwerk in den USB-Anschluss des Surface Hub 2S ein. Eine Liste der erforderlichen Dateien finden Sie im vorherigen Abschnitt.

2. So starten Sie in UEFI:

   1. Schalten Sie Ihren Surface Hub 2S aus (Herunterfahren).
   1. Halten Sie **Lautstärke +** gedrückt, und drücken Sie dann die Power-Taste, und lassen Sie sie los.
   1. Halten Sie die **Lautstärke +** gedrückt, bis das UEFI-Menü angezeigt wird.
   
      ![Drücken Sie die Lautstärketaste, und halten Sie sie gedrückt, bis das UEFI-Menü angezeigt wird.](images/shm-fig20.png)
      
3. Wenn das Gerät neu gestartet wird, geben Sie das UEFI-Kennwort ein, das Sie zuvor erstellt haben, falls zutreffend (dringend empfohlen).

   ![Geben Sie das UEFI-Kennwort ein.](images/shm-fig22.png)
   
4. Wählen Sie im UEFI-Menü die Option **Verwaltungs**  >  **Installation von USB aus**.

   ![Wählen Sie Verwaltung und Installation von U S B aus.](images/shm-fig21.png)
   
5. Wählen Sie **jetzt neu starten**aus, wie in der folgenden Abbildung dargestellt. Das Gerät wird neu gestartet. Es wird ein weißes Microsoft-Logo in der Mitte des Fensters angezeigt und dann heruntergefahren.

   ![Wählen Sie jetzt neu starten aus.](images/shm-fig25.png)
   
6. Drücken Sie die Power-Taste, und lassen Sie sie los. Aktivieren Sie im daraufhin angezeigten roten Fenster den Surface Enterprise-Verwaltungsmodus. 

7. Geben Sie den Daumenabdruck Ihres zweistelligen Zertifikats und das Kennwort für UEFI-Einstellungen ein. Wählen Sie dann **OK**aus.

   ![Geben Sie den Daumenabdruck Ihres zweistelligen Zertifikats und das Kennwort für UEFI-Einstellungen ein.](images/shm-fig23.png)
 
   > [!NOTE]
   > Nachdem Sie Semm auf Ihrem Gerät aktiviert haben, wird die neue UEFI-Einstellung **EnableOSMigration** angewendet. Sie können nicht mehr auf das Windows 10-Team zugreifen. Stattdessen müssen Sie mit dem nächsten Schritt fortfahren und Windows 10 pro oder Windows 10 Enterprise installieren. 

   Das Gerät wird neu gestartet. Es wird das weiße Logo in der Mitte des Bildschirms angezeigt und dann wieder heruntergefahren.

### Installieren von Windows 10 pro oder Enterprise

1. Wenn Ihr startfähiges Windows 10 pro-oder Enterprise-Laufwerk noch nicht im Surface Hub 2 USB-A-Port vorhanden ist, fügen Sie es jetzt ein. Drücken Sie dann die Power-Taste, und lassen Sie sie los. 

    Wenn das Gerät gestartet wird, wird das weiße Logo in der Mitte des Bildschirms angezeigt. Dann sehen Sie einen rotierenden Kreis unterhalb des weißen Logos.

3. Wenn das Gerät nicht automatisch auf das USB-Laufwerk bootet, schalten Sie das Gerät aus (ziehen Sie das Netzkabel ab, und schließen Sie es wieder an). Nachdem Sie das Netzkabel erneut angeschlossen haben, sollte das Gerät nach ein paar Sekunden gestartet werden. Dann sehen Sie das weiße Logo in der Mitte des Bildschirms. 

    Wenn das Gerät nicht aktiviert ist, drücken Sie die Power-Taste, und lassen Sie sie los. Nachdem Sie das Logo in der Mitte des Bildschirms angezeigt haben, halten Sie die Lautstärketaste gedrückt, bis Sie den Kreis unterhalb des weißen Logos sehen.
 
   ![Starten Sie Windows 10 vom Laufwerk U S B.](images/shm-fig26.png)
   
4. Befolgen Sie die Anweisungen zum Installieren von Windows 10 pro oder Enterprise (Version 1903 oder höher), wenn das OOBE-Setup (Out-of-Box Experience) gestartet wird.

### Installieren von Surface Hub 2-Treibern und-Firmware

Wenn Sie sicherstellen möchten, dass Ihr Gerät über alle neuesten Updates und Treiber verfügt, installieren Sie [Treiber und Firmware für Windows 10 pro und Enterprise OS auf Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
## Konfigurieren von empfohlenen Einstellungen

Informationen zum vollständigen Konfigurieren von Surface Hub 2S als persönliches Produktivitäts Gerät finden Sie unter [Konfigurieren von Windows 10 pro oder Enterprise auf Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Wenn die in diesem Artikel beschriebenen Schritte Ihr Gerät nicht erfolgreich zu Windows 10 pro oder Enterprise für Surface Hub 2 migrieren, [unterstützen Sie den Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## Zurücksetzen auf das Windows 10-Team

Wenn Sie Ihr Gerät auf das Windows 10-Team wiederherstellen möchten, lesen Sie [Zurücksetzen und Wiederherstellen für Surface Hub 2S](surface-hub-2s-recover-reset.md).

## Versionsverlauf

In der folgenden Tabelle sind die Änderungen an diesem Artikel zusammengefasst.

| Version | Date               | Beschreibung                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.2  | 29. September 2020 | Verschiedene Updates, die sich mit dem Usability-Feedback befassen.                                                        |
| v. 1.1  | 15. September 2020 | Eine zusätzliche Notiz in der Einleitung, in der die Lizenzierungsanforderungen für die Installation eines neuen Betriebssystems erläutert wurden. |
| v. 1.0  | 1. September 2020  | Neuer Artikel.                                                                                           |
