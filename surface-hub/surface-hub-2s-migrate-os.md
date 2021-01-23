---
title: Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2
description: Informationen zum Migrieren von Windows 10 Team auf Surface Hub 2 zu Windows 10 Pro oder Windows 10 Enterprise.
keywords: Surface Hub Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297638"
---
# Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2

- [Versionsverlauf des Artikels](#version-history)

Surface Hub 2S ist mit Windows 10 Team installiert. Diese angepasste Edition von Windows 10 erleichtert die Zusammenarbeit in Besprechungsraumumgebungen. Sie können jetzt Windows 10 Pro oder Enterprise ausführen, um Surface Hub 2S ähnlich wie jeder andere PC zu verwenden.

> [!IMPORTANT]
> Für diesen Migrationsprozess müssen Sie das in diesem Artikel beschriebene Verfahren befolgen. Bevor Sie fortfahren, lesen Sie [lösungskomponenten](#solution-components) und [Migrations- und Installationsworkflow.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Wenn Sie Windows 10 Pro oder Enterprise installieren, benötigen Sie eine neue Lizenz, die von Ihrer vorhandenen Windows 10 -Teamlizenz getrennt ist.

Starten Sie die Migration von Windows 10 Team mit einem separaten PC und dem herunterladbaren *Surface UEFI Configurator-Tool.* Das Tool erstellt ein Paket mit einer neuen UEFI-Einstellung, die Sie auf Surface Hub 2S anwenden.  

Surface UEFI Configurator funktioniert als Schnittstelle im Surface Enterprise Management Mode (SEMM). Sie ermöglicht die zentrale Verwaltung von Firmwareeinstellungen auf Surface-Geräten in einer Unternehmensumgebung. Weitere Informationen finden Sie unter [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 
## Lösungskomponenten

- Surface Hub 2S-Gerät mit Windows 10 Team
- Separates Gerät unter Windows 10
- Surface -UEFI-Konfiguratortool zum Erstellen des SEMM-Pakets
- Windows 10 Pro- oder Enterprise-Betriebssystemimage, Version 1903 oder höher
- Zwei USB-Laufwerke mit 16 GB Speicher im FAT32-Format
- Treiber und Firmware für Windows 10 Pro und Enterprise in einer Surface Hub 2-Microsoft Windows Installer (MSI)-Datei
- Internetverbindung
- Imaginglösung (optional)
 
## Migrations- und Installationsworkflowzusammenfassung

| Schritt  | Aktion                                                                                                 | Zusammenfassung                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Überprüfen Sie die UEFI-Version auf dem Surface Hub 2S.](#verify-the-uefi-version-on-surface-hub-2s)                                  | Die UEFI-Version muss Version *694.2938.768.0* oder höher sein.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Laden Sie surface UEFI Configurator und die Surface Hub 2-Treiber und -Firmware herunter.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Wählen Sie **[auf der Seite "Surface Tools for IT"](https://www.microsoft.com/download/details.aspx?id=46703)** </a> die Option **"Herunterladen" aus.** Wählen Sie dann die **Surface UEFI Configurator -MSI-Datei**aus, und laden Sie sie herunter, und installieren Sie sie auf einem separaten PC. Laden Sie außerdem die [MSI-Datei "Drivers and firmware" für Windows 10 Pro und Enterprise OS auf Surface Hub 2 herunter.](https://www.microsoft.com/download/details.aspx?id=101974)</a> Speichern Sie dieses Paket für die Verwendung in Schritt 5. |
| 3 | [Bereiten Sie das SEMM-Zertifikat vor.](#prepare-the-semm-certificate)                                                                          | Bereiten Sie das Zertifikat vor, das zum Ausführen des Surface UEFI Configurator erforderlich ist, oder verwenden Sie das aktuelle Zertifikat.                                                                                                                                                                                                                                                                                                      |
| 4 | [Erstellen Sie ein SEMM-Paket.](#create-a-semm-package)                                                                               | Starten Sie den Surface UEFI-Konfigurator, um ein "SEMM"-Paket auf einem USB-Laufwerk zu erstellen. Dieses Paket enthält die Konfigurationsdateien, die Sie auf Surface Hub 2S anwenden müssen. Kopieren Sie diese SEMM-Paketdateien in einen Ordner auf Ihrem PC.                                                                                                                                                                                          |
| 5 | [Laden Sie einen USB-Speicherlaufwerk mit Dem Windows 10-Image, dem SEMM-Paket sowie Treibern und Firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Erstellen Sie ein USB-Laufwerk, das ein Windows 10-Image enthält. In diesem Beispiel heißt das Laufwerk *BOOTME*. Fügen Sie die Treiber und die Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 (aus Schritt 2) und die "SEMM"-Paketdateien (aus Schritt 4) dem Laufwerk *BOOTME* hinzu.                                                                                                                                                                                                  |
| 6 | [Aktualisieren Sie die UEFI auf Surface Hub 2S, um die Betriebssystemmigration zu aktivieren.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Verwenden Sie *das BOOTME-Laufwerk,* um surface Hub 2S über das Menü UEFI zu starten und das SEMM-Paket zu installieren.|
| 7 | [Installieren Sie Windows 10 Pro oder Enterprise.](#install-windows-10-pro-or-enterprise)                                        | Verwenden Sie *das BOOTME-Laufwerk,* um Windows 10 Pro oder Enterprise, Version 1903 oder höher, zu installieren.                                                                                                                                                                                                                                                                                 |
| 8 | [Installieren Sie Treiber und Firmware für Windows 10 Pro und Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Um sicherzustellen, dass Ihr Gerät über die neuesten Updates und Treiber verfügt, installieren Sie die Treiber und firmware für <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro und Enterprise OS auf Surface Hub 2 MSI-Datei.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Konfigurieren Sie Surface Hub 2S als persönliches Produktivitätsgerät.](#configure-recommended-settings)                                        |  Aktivieren Sie die empfohlenen Einstellungen und Anwendungen, um Surface Hub 2S als persönliches Produktivitätsgerät zu optimieren.                                                                                                                                                                                                                                                                    |

### Überprüfen der UEFI-Version auf Surface Hub 2S

Bevor Sie Surface Hub von Windows 10 Team zu Windows 10 Desktop migrieren, benötigen Sie UEFI Version *694.2938.768.0* oder höher.
 
**So überprüfen Sie die UEFI-Version auf Ihrem System:**

1. Wählen Sie auf der Surface Hub 2S-Startseite die Option **"Start"** aus, und öffnen Sie dann die Surface App (**All Apps**  >  **Surface**).

2. Wählen **Sie Ihr Surface** aus, um Informationen zu Surface Hub, einschließlich der aktuellen UEFI-Version auf dem Gerät, anzeigen zu können. 
   - Wenn die UEFI-Version *694.2938.768.0* oder höher ist, wie in der folgenden Abbildung gezeigt, können Sie das "SEMM"-Paket zum Aktivieren der Betriebssystemmigration erstellen.

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)
 
   - Wenn die UEFI-Version vor Version *694.2938.768.0*liegt, verwenden Sie eine der folgenden Methoden, um eine neuere Version zu erhalten.
   
#### Aktualisieren von UEFI über Windows Update

1. Melden Sie sich auf Surface Hub 2S als **Administrator an.**

    >[!Note]
    > Wenn Sie Ihren Benutzernamen oder Ihr Administratorkennwort nicht kennen, müssen Sie das Gerät zurücksetzen. Weitere Informationen finden Sie unter [Zurücksetzen und Wiederherstellung für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

1. Wechseln Sie **zu "Alle**  >  **Apps–**  >  **Einstellungsupdate" und**  >  **"Sicherheit",** und installieren Sie alle Updates.
1. Starten Sie das Gerät neu.
1. Überprüfen Sie die UEFI-Version mithilfe der Surface-App. Wenn die Version UEFI nicht Version *694.2938.768.0* oder höher ist, wiederholen Sie diese Schritte, oder verwenden Sie das folgende Verfahren, um die neueste Version von UEFI zu erhalten.

#### Aktualisieren der UEFI über bare Metal Recovery (BMR)-Image

1.  Wechseln Sie zur [Surface-Wiederherstellungswebsite,](https://support.microsoft.com/surfacerecoveryimage) und wählen **Sie Surface Hub 2S aus.**
3.  Geben Sie ihre Seriennummer des Hubs ein. Sie befindet sich auf der Rückseite des Hubs neben der Stromverbindung.
4.  Befolgen Sie die Anweisungen zum Herunterladen des Images auf ein formatiertes USB-Laufwerk, indem Sie das Windows 10 Team 2020 Update installieren.
5.  Nach dem Update wird das Setup der Out-of-Box-Experience (OOBE) auf dem Gerät durchgeführt. Sie müssen das Setup nicht abschließen. Die UEFI-Version ist bereits aktualisiert. Schalten Sie stattdessen das Gerät herunter, indem Sie den Netzschalter gedrückt halten, bis der Bildschirm ausgeschaltet wird.

### Herunterladen von Surface UEFI Configurator- und Surface Hub 2-Treibern und -Firmware

Führen Sie auf einem separaten PC die folgenden Schritte aus:

1. Wählen Sie <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> auf der Seite "Surface Tools for </a> IT" die Option **"Herunterladen" aus.**  
1. Wählen Sie die Surface UEFI Configurator-MSI-Datei aus, laden Sie sie herunter, und installieren Sie sie auf einem separaten PC. Das Surface UEFI Configurator-Tool kann nicht auf einem Surface Hub 2S ausgeführt werden, während Windows 10 Team Edition installiert ist.

1. Laden Sie die [Windows Installer -MSI-Datei für Surface Hub 2-Treiber und -Firmware herunter.](https://www.microsoft.com/download/details.aspx?id=101974) Sie verwenden diese Datei bei der Installation des neuen Betriebssystems.

### Vorbereiten des SEMM-Zertifikats

Wenn Sie surface UEFI Configurator noch nicht verwendet haben, müssen Sie ein Zertifikat vorbereiten. Dieses Zertifikat stellt sicher, dass Sie nach der Registrierung eines Geräts bei SEMM nur mithilfe von Paketen, die mit dem genehmigten Zertifikat erstellt werden, die Einstellungen für die UEFI ändern können.

Wie Sie ein Zertifikat erhalten, hängt von der Größe oder Komplexität Ihrer Organisation ab:

- Unternehmensorganisationen verwalten in der Regel ihre eigene Infrastruktur, um Zertifikate gemäß den Standardsicherheitsmethoden zu generieren.

- Mittelständische Unternehmen und andere Unternehmen entscheiden sich häufig dafür, Zertifikate von Partneranbietern zu erhalten. Diese Option wird für Organisationen empfohlen, die nicht über so viel IT-Know-how verfügen oder kein dediziertes IT-Sicherheitsteam haben.

- Alternativ können Sie ein selbst signiertes Zertifikat mithilfe eines PowerShell-Skripts generieren. Weitere Informationen finden Sie unter den Zertifikatanforderungen für den [Surface Enterprise-Verwaltungsmodus.](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) Sie können auch PowerShell verwenden, um Ein eigenes Zertifikat zu erstellen. Weitere Informationen finden Sie in der [Dokumentation "New-SelfSignedCertificate".](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)

Das semm-Paket, das Surface UEFI Configurator erstellt, muss mit einem Zertifikat gesichert werden. Das Zertifikat überprüft die Signatur von Konfigurationsdateien, bevor die UEFI-Einstellungen angewendet werden können. Weitere Informationen finden Sie in der [SEMM-Dokumentation.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
### Erstellen eines "SEMM"-Pakets

1. Installieren Sie auf einem separaten PC das Surface UEFI Configurator-Tool, das Sie zuvor heruntergeladen haben.

1. Öffnen Sie den Surface UEFI-Konfigurator, und wählen Sie dann **"Start" aus.**

   ![Surface UEFI Configurator start screen.](images/shm-fig2.png)
   
1. Wählen **Sie "Surface Devices"** und dann **"Next" aus.**

   ![Screenshot shows the Surface Devices option selected.](images/shm-fig3.png)
  
1. Wählen Sie **das Konfigurationspaket aus.**

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. Wählen Sie **Zertifikatschutz aus.**

   ![Screenshot shows were to choose "Select Certificate Protection".](images/shm-fig5.png)

   Sie werden aufgefordert, Ihre Zertifikat-PFX-Datei hinzuzufügen.

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)
   
1. Geben Sie Ihr Zertifikatkennwort ein, und wählen Sie dann **OK aus.**

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. Wählen **Sie Kennwortschutz** aus, um dem Surface UEFI ein Kennwort hinzuzufügen. Sie benötigen dieses Kennwort, wenn Sie mit der UEFI starten. *Es wird dringend empfohlen, dass Sie ein UEFI-Kennwort festlegen, das Sie auf Surface Hub 2S verwenden.*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)
   
1. Legen Sie ein UEFI-Kennwort ein, und wählen Sie dann **OK aus.**

   > [!IMPORTANT]
   > Speichern Sie das Kennwort an einem sicheren Ort, auf den Ihre IT-Administratoren, die Surface Hub verwalten, zugriffen können. *Wenn dieses Kennwort verloren geht, kann es nicht wiederhergestellt werden.*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. Wählen **Sie Surface Hub 2S**und dann Weiter **aus.**

    ![Screenshot shows where to select Surface Hub 2S.](images/shm-fig10.png)
   
1. Wählen Sie **erneut "Weiter"** aus.

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. Um die Installation von Windows 10 Pro oder Enterprise zu ermöglichen, aktivieren Sie **"EnableOsMigration",** und wählen Sie dann **"Weiter" aus.**

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![Screenshot shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### Verwalten der REGISTRIERUNG von SEMM

Die Registrierung eines Geräts bei SEMM wirkt sich darauf aus, wie Sie es verwalten können. Nachdem Sie beispielsweise ein "SEMM"-Paket angewendet haben, sind alle UEFI-Einstellungen im Menü "UEFI" des Geräts nicht verfügbar (gesperrt). Standardwerte für andere Einstellungen wie **IPv6 für den PXE-Start** sind ebenfalls nicht verfügbar.

Wenn Sie die UEFI-Einstellungen nach Abschluss der Migration ändern möchten, wenden Sie ein anderes "SEMM"-Paket an, oder stellen Sie die Registrierung des Geräts bei SEMM auf. Wenn Sie ein weiteres "SEMM"-Paket anwenden, um die Einstellungen der UEFI zu ändern, müssen Sie beim Erstellen des neuen "SEMM"-Pakets das ursprüngliche Zertifikat verwenden. Verwenden Sie das UEFI-Konfigurator-Tool, ** und lassen Sie **"EnableOSMigration"** deaktiviert *(nicht* wie in den ursprünglichen Migrationsschritten).

#### Wenn Sie mit Partnern zusammenarbeiten

Wenn Ihr Unternehmen die Surface Hub 2-Migration zu Windows 10 Pro oder Enterprise auslagern, sollte der Partner das SEMM-Zertifikat, das SEMM-Paket und das Kennwort für UEFI an Sie übertragen. Oder Sie können die Registrierung nach der Migration des Hubs sofort von SEMM entfernen. Dieser Schritt ermöglicht die lokale Verwaltung von UEFI und die Übertragung des Geräts an eine andere Partei. Es wird jedoch dringend empfohlen, ein UEFI-Kennwort zu verwenden, das nach der Migration konfiguriert werden kann. Weitere Informationen finden Sie unter [Verwalten von Surface UEFI-Einstellungen.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### So verwenden Sie ein Rollback auf Windows 10 Team

Wenn Sie Ihr Gerät nach der Migration im Windows 10-Team wiederherstellen möchten, wie weiter unten [in](#to-roll-back-to-windows-10-team)diesem Artikel beschrieben, wird empfohlen, die Registrierung des Hubs bei SEMM zu wiederherstellen. Weitere Informationen finden Sie unter ["Unenroll Surface devices from SEMM".](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

#### Speichern des "SEMM"-Pakets auf einem USB-Laufwerk

1. Schließen Sie ein USB-Laufwerk an Ihren PC an.
1. Wählen **Sie Hub 2S**und dann **"Weiter" aus.**

   ![Screenshot shows where to select Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > Alle vorhandenen Daten auf dem USB-Laufwerk werden gelöscht, wenn das "SEMM"-Paket erstellt wird. Entfernen Sie vor dem Erstellen des SEMM-Pakets alle benötigten Dateien vom USB-Laufwerk.
   
1. Wählen Sie **Erstellen** aus.

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. Erfassen Sie einen Screenshot dieser Seite, und wählen Sie dann **"Ende" aus.** Ihr SEMM-Paket ist jetzt bereit. Sie enthält das SEMM-Paket *DfciUpdate.dfi* und eine ** Textdatei, die den SEMM-Fingerabdruck enthält, der die letzten beiden Zeichen des Fingerabdrucks des Zertifikats ist.

   ![Screenshot shows where to select End.](images/shm-fig15.png)
   
4. Speichern Sie die letzten beiden Zeichen des Zertifikatfingerabdrucks. Sie benötigen diese Zeichen, um SEMM zu aktivieren, wenn Sie das Paket auf Surface Hub 2S anwenden.

### Laden eines USB-Flashlaufwerks mit einem Windows 10-Image, einem SEMM-Paket und Surface Hub 2-Treibern und -Firmware

Sie können ein Windows 10 Pro- oder Enterprise-Image (Version *1903* oder höher) mit einer der folgenden Optionen installieren:

- Ihre aktuelle Imageerstellungslösung.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator). Verwenden Sie dieses Tool, um ein startbares Windows 10-Image zu erstellen. Das Image kann alle aktuellen Windows 10-Updates, Microsoft Office, andere Apps sowie die erforderlichen Treiber und Firmware enthalten.

- Ein USB-Speicherlaufwerk, das ein Windows 10 Pro- oder Enterprise-Image enthält. Installieren Sie dann [Treiber und Firmware für Windows 10 Pro und Enterprise auf](https://www.microsoft.com/download/details.aspx?id=101974) Surface Hub 2.
 
In den folgenden Schritten wird gezeigt, wie Sie ein USB-Flashlaufwerk von Installationsmedien erstellen und dann die SEMM-Paketdateien sowie die Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2-MSI-Dateien hinzufügen. Wenn Sie eine andere Bereitstellungsmethode verwenden, wechseln Sie zum Abschnitt "Aktualisieren von [UEFI auf Surface Hub 2S",](#update-uefi-on-surface-hub-2s-to-enable-os-migration) um den Abschnitt zur Betriebssystemmigration in diesem Artikel zu aktivieren.

> [!NOTE]
> Nachdem Sie die Installation abgeschlossen haben, benötigen Sie eine gültige Lizenz für Windows 10 Pro oder Windows 10 Enterprise, die von Ihrer vorhandenen Windows 10 -Teamlizenz getrennt ist.

1. Befolgen Sie zum Erstellen einer Windows 10 Pro-Installation die Anweisungen zum Herunterladen des Medienerstellungstools unter [Windows 10 herunterladen.](https://www.microsoft.com/software-download/windows10) Um Windows 10 Enterprise herunterzuladen, wechseln Sie zum [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

1. Fügen Sie ein neues USB-Speicherlaufwerk ein.
1. Öffnen Sie das Medienerstellungstool, wählen **Sie "Installationsmedium erstellen"** und dann **"Weiter" aus.**

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)
   
3. Wählen Sie eine Sprache und dann **Windows 10 und** **64-Bit (x64) aus.** Wählen Sie dann **"Weiter" aus.**

   ![Screenshot shows where you select the language, O S edition, and architecture type.](images/shm-fig17.png)
   
4. Wählen **Sie "USB-Speicherlaufwerk"** und dann **"Weiter" aus.**

   ![Screenshot shows where to select U S S B flash drive.](images/shm-fig18.png)
   
5. Wenn der Download abgeschlossen ist, wählen Sie **"Fertig stellen" aus.**

   ![Der Bildschirm meldet, dass das Laufwerk "U S B" bereit ist und eine Schaltfläche "Fertig stellen" enthält.](images/shm-fig19.png)
   
6. Kopieren Sie die SEMM-Paketdateien und die Treiber und firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 (die MSI-Datei) in das Stammverzeichnis des USB-Flashlaufwerks (*BOOTME*), das Ihr Windows 10-Image enthält. Das BOOTME-USB-Laufwerk enthält:

    - Ihr startbares Windows 10-Image.
    
    - Die SEMM-Paketdateien, die in das Stammverzeichnis des USB-Laufwerks kopiert wurden:
    
      - *DfciUpdate.dfi*.
      - Eine Textdatei mit dem SEMM-Fingerabdruck. (In diesem Beispiel ist die Datei *SurfaceUEFI_2020Aug25_1058.txt*.) Der automatisch generierte Datums-/Uhrzeitstempel entspricht dem Datum, an dem Sie die Datei mithilfe von Surface UEFI Configurator erstellt haben.

   - Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Kopieren Sie diese Datei in das Stammverzeichnis des USB-Laufwerks.

### Aktualisieren von UEFI auf Surface Hub 2S zum Aktivieren der Betriebssystemmigration

1. Fügen Sie das BOOTME-Laufwerk an den USB-A-Port auf dem Surface Hub 2S ein. Eine Liste der erforderlichen Inhalte finden Sie im vorherigen Abschnitt.

1. So starten Sie UEFI:

   1. Deaktivieren (Herunterfahren) des Surface Hub 2S.
   1. Halten Sie Volume **+** gedrückt, und drücken Sie dann den Netzschalter, und lassen Sie ihn los. Halten Sie **"Volume +" so lange** bei, bis das Menü "UEFI" angezeigt wird.
   
      ![In der Zeichnung werden die Lautstärke- und Netztasten angezeigt.](images/shm-fig20.png)
      
3. Geben Sie beim Neustart des Geräts das zuvor erstellte UEFI-Kennwort ein (falls erforderlich).

   ![Bildschirm "Systemkennwort".](images/shm-fig22.png)
   
4. Wählen Sie im Menü "UEFI" die Option **"Verwaltung" aus.** Wählen Sie dann **"Von USB installieren" aus.**

   ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)
   
5. Wählen **Sie jetzt Neu starten**aus, wie in der folgenden Abbildung gezeigt. Das Gerät wird neu gestartet. In der Mitte des Fensters wird ein weißes Microsoft-Logo angezeigt und anschließend heruntergefahren.

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. Drücken und loslassen Sie den Netzschalter. Wählen Sie im angezeigten roten Dialogfeld den Surface Enterprise-Verwaltungsmodus aus.

7. Geben Sie ihren aus zwei Zeichen gedruckten Zertifikatfingerabdruck und ihr Kennwort für die UEFI-Einstellungen ein. Wählen Sie dann **OK aus.**

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > Nachdem Sie SEMM auf Ihrem Gerät aktiviert haben, wird die neue UEFI-Einstellung **"EnableOSMigration"** angewendet. Sie können nicht mehr auf Windows 10 Team zugreifen. Stattdessen müssen Sie mit dem nächsten Schritt fortfahren und Windows 10 Pro oder Windows 10 Enterprise installieren.

   Das Gerät wird neu gestartet. Das weiße Logo wird in der Mitte des Bildschirms angezeigt und dann erneut heruntergefahren.

### Installieren von Windows 10 Pro oder Enterprise

1. Wenn sich ihr startbares Windows 10 Pro- oder Unternehmenslaufwerk noch nicht im Surface Hub 2-USB-A-Port befindet, fügen Sie es jetzt ein. Drücken und lassen Sie dann den Netzschalter los.

    Wenn das Gerät gestartet wird, wird das weiße Logo in der Mitte des Bildschirms angezeigt. Anschließend wird unter dem weißen Logo ein sich drehenden Kreis angezeigt.

3. Wenn das Surface-Gerät nicht automatisch mit dem USB-Laufwerk startet, schalten Sie das Gerät aus (ziehen Sie das Netzkabel ab, und schließen Sie es dann wieder an). Nachdem Sie das Netzkabel wieder angeschlossen haben, sollte das Gerät nach einigen Sekunden gestartet werden. Dann wird das weiße Logo in der Mitte des Bildschirms angezeigt.

    Wenn das Gerät nicht einschalten kann, drücken Sie den Netzschalter, und lassen Sie ihn los. Unmittelbar nachdem das Logo in der Mitte des Bildschirms angezeigt wird, drücken und halten Sie die Lautstärketaste gedrückt, bis der sich drehende Kreis unter dem weißen Logo angezeigt wird.
 
   ![Bild der Lautstärke- und Netztasten.](images/shm-fig26.png)
   
4. Wenn das Setup der out-of-Box Experience (OOBE) gestartet wird, folgen Sie den Anweisungen zum Installieren von Windows 10 Pro oder Enterprise (Version 1903 oder höher).

### Installieren von Surface Hub 2-Treibern und -Firmware

Installieren Sie Treiber und Firmware für Windows [10 Pro](https://www.microsoft.com/download/details.aspx?id=101974)und Enterprise, um sicherzustellen, dass Surface Hub 2 auf dem neuesten Stand ist. Starten Sie dann das Gerät neu. Lassen Sie das Surface eine Stunde lang eingeschaltet, und starten Sie es dann erneut. Sie werden nicht zum zweiten Neustart aufgefordert. Durch diese Unterbrechung und den zusätzlichen Neustart wird sichergestellt, dass die Firmware vollständig aktualisiert wurde.
 
## Konfigurieren empfohlener Einstellungen

Informationen zum Konfigurieren von Surface Hub 2S als persönliches Produktivitätsgerät finden Sie unter "Konfigurieren von [Windows 10 Pro oder Enterprise auf Surface Hub 2".](surface-hub-2-post-install.md)

> [!NOTE]
>Wenn Sie Ihr Gerät nicht erfolgreich zu Windows 10 Pro oder Enterprise für Surface Hub 2 migrieren können, indem Sie die in diesem Artikel beschriebenen Schritte ausführen, wenden Sie sich an den [Surface Hub-Support.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## So verwenden Sie ein Rollback auf Windows 10 Team

Wenn Sie Ihr Gerät in Windows 10 Team wiederherstellen möchten, lesen Sie "Zurücksetzen und Wiederherstellung [für Surface Hub 2S".](surface-hub-2s-recover-reset.md)

> [!NOTE]
> Bevor Sie ein Rollback auf Windows 10 Team erstellen, wird empfohlen, die Registrierung des Surface Hub von SEMM zu entsperren. Weitere Informationen finden Sie unter ["Registrieren von Surface-Geräten über SEMM".](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## Versionsverlauf

In der folgenden Tabelle sind die Änderungen an diesem Artikel zusammengefasst.

| Version | Date               | Beschreibung                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14. Dezember 2020 | Enthält [](#install-surface-hub-2-drivers-and-firmware) weitere Informationen zum Installieren der MSI-Datei für "Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2", und informiert Sie, dass je nach Zustand des Systems möglicherweise ein zweiter Neustart erforderlich ist.                                                          |
| v. 1.3  | 3. Dezember 2020 | Aktualisiert mit Anleitungen zum [Verwalten der SEMM-Registrierung.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29. September 2020 | Verschiedene Updates für Feedback zur Benutzerfreundlichkeit.                                                        |
| v. 1.1  | 15. September 2020 | Zusätzliche Hinweise in der Einführung, in der die Lizenzierungsanforderungen für die Installation eines neuen Betriebssystems erläutert werden. |
| v. 1.0  | 1. September 2020  | Neuer Artikel.                                                                                           |
