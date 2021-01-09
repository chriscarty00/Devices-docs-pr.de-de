---
title: Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2
description: In diesem Artikel wird beschrieben, wie Sie von Windows 10 Team auf Surface Hub 2 zu Windows 10 Pro oder Windows 10 Enterprise migrieren.
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
ms.openlocfilehash: 9878e64e414f4fe9ec3abfbd49adf233edc1da1d
ms.sourcegitcommit: 53d1eac8840fafbcd155798fce0d8c843f48dca3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "11255487"
---
# Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2

- [Versionsverlauf des Artikels](#version-history)

Surface Hub 2S ist mit Windows 10 Team vorinstalliert. Diese angepasste Edition von Windows 10 wurde entwickelt, um die Zusammenarbeit in Besprechungsraumumgebungen zu erleichtern. Jetzt können Sie Windows 10 Pro oder Enterprise ausführen, um Surface Hub 2S wie jeden anderen PC zu verwenden. 

> [!IMPORTANT]
>Im Gegensatz zu einem typischen Upgrade oder einer typischen Migration müssen Sie bei diesem Vorgang ein bestimmtes Verfahren befolgen, wie in diesem Artikel beschrieben. Überprüfen Sie die [Lösungskomponenten](#solution-components) [und den Migrations- und Installationsworkflow,](#migration-and-installation-workflow-summary) bevor Sie fortfahren.


> [!NOTE]
> Wenn Sie Windows 10 Pro oder Enterprise installieren, benötigen Sie eine neue Lizenz, die von Ihrer vorhandenen Windows 10 -Teamlizenz getrennt ist. 


Starten Sie die Migration von Windows 10 Team mit einem separaten PC und dem herunterladbaren *Tool Surface UEFI Configurator.* Verwenden Sie das Tool, um ein Paket zu erstellen, das eine neue UEFI-Einstellung enthält, die Sie auf Surface Hub 2S anwenden.  

Surface UEFI Configurator funktioniert als Schnittstelle im Surface Enterprise Management Mode (SEMM). Es wurde entwickelt, um die zentrale Verwaltung von Firmwareeinstellungen auf Surface-Geräten in einer Unternehmensumgebung zu erleichtern. Weitere Informationen finden Sie in der <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> Microsoft SEMM-Dokumentation. </a>
 

## Lösungskomponenten

- Surface Hub 2S-Gerät, auf dem das Betriebssystem Windows 10 Team ausgeführt wird
- Separates Gerät unter Windows 10
- Surface -UEFI-Konfiguratortool zum Erstellen des SEMM-Pakets
- Windows 10 Pro- oder Enterprise-Betriebssystemimage, Version 1903 oder höher
- Zwei USB-Laufwerke mit 16 GB Speicher im FAT32-Format
- Die Datei "Drivers and Firmware for Windows 10 Pro and Enterprise OS" auf Surface Hub 2 Microsoft Windows Installer (MSI)
- Internetverbindung
- Imaginglösung (optional)

 
## Migrations- und Installationsworkflowzusammenfassung

| Schritt  | Aktion                                                                                                 | Zusammenfassung                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Stellen Sie sicher, dass die UEFI-Version auf Surface Hub 2S die Mindestanforderungen erfüllt.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Stellen Sie sicher, dass die UEFI-Version 694.2938.768.0 oder höher ist.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Laden Sie Surface UEFI Configurator- und Surface Hub 2-Treiber und -Firmware herunter.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Wählen Sie <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **auf der Seite "Surface Tools for IT"** </a> die Option **"Herunterladen" aus.** Wählen Sie dann den **Surface UEFI Configurator aus, und laden Sie es herunter. MSI-Datei,** und installieren Sie sie auf einem separaten PC. Laden Sie <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> die MSI-Datei "Drivers and Firmware" für Windows 10 Pro und Enterprise os auf Surface Hub 2 herunter.</a> Speichern Sie es für die Verwendung in Schritt 5. |
| 3 | [Vorbereiten des SEMM-Zertifikats.](#prepare-the-semm-certificate)                                                                          | Bereiten Sie das Zertifikat vor, das zum Ausführen des Surface UEFI Configurator erforderlich ist. Oder verwenden Sie Ihr aktuelles Zertifikat.                                                                                                                                                                                                                                                                                                      |
| 4 | [Erstellen Sie das SEMM-Paket.](#create-a-semm-package)                                                                               | Starten Sie den Surface UEFI-Konfigurator, um ein "SEMM"-Paket auf einem USB-Laufwerk zu erstellen, das die Konfigurationsdateien enthält, die Sie auf Surface Hub 2S anwenden müssen. Kopieren Sie diese SEMM-Paketdateien in einen Ordner auf Ihrem PC.                                                                                                                                                                                          |
| 5 | [Bereiten Sie ein USB-Flashlaufwerk vor, das Windows 10-Image, das PAKET SEMM sowie Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 enthält.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Erstellen Sie ein einzelnes USB-Laufwerk, das ein Windows 10-Image enthält. In diesem Beispiel heißt das Laufwerk *BOOTME*. Fügen Sie die Treiber und die Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 (Schritt 2) und die Paketdateien für SEMM (Schritt 4) dem LAUFWERK *BOOTME* hinzu.                                                                                                                                                                                                  |
| 6 | [Aktualisieren Sie UEFI auf Surface Hub 2S, um die Migration des Betriebssystems zu aktivieren.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Verwenden Sie *das BOOTME-Laufwerk,* um Surface Hub 2S im Menü "UEFI" zu starten und das "SEMM"-Paket zu installieren.|
| 7 | [Installieren Sie Windows 10 Pro oder Enterprise, Version 1903 oder höher.](#install-windows-10-pro-or-enterprise)                                        | Verwenden Sie *das BOOTME-Laufwerk,* um Windows 10 Pro oder Enterprise, Version 1903 oder höher, zu installieren.                                                                                                                                                                                                                                                                                 |
| 8 | [Installieren Sie Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Um sicherzustellen, dass Ihr Gerät über die neuesten Updates und Treiber verfügt, installieren Sie die MSI-Datei "Drivers and Firmware" für <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro und Enterprise auf Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Konfigurieren Sie Surface Hub 2S vollständig als persönliches Produktivitätsgerät.](#configure-recommended-settings)                                        |  Aktivieren Sie empfohlene Einstellungen und Anwendungen, um Surface Hub 2S als persönliches Produktivitätsgerät zu optimieren.                                                                                                                                                                                                                                                                    |

### Überprüfen, ob die UEFI-Version auf Surface Hub 2S die Mindestanforderungen erfüllt

Bevor Sie Surface Hub von Windows 10 Team zu Windows 10 Desktop migrieren, benötigen Sie eine UEFI-Version, die mindestens *694.2938.768.0*ist.
 
**So überprüfen Sie die UEFI-Version auf Ihrem System:**

1. Wählen Sie auf der Surface Hub 2S-Startseite die Option **"Start"** aus, und öffnen Sie dann die Surface-App (**Alle Apps**  >  **Surface**).

2. Wählen **Sie Ihr Surface** aus, um Informationen zu Surface Hub, einschließlich der aktuellen UEFI-Version auf dem Gerät, anzeigen zu können. 
   - Wenn die UEFI-Version *694.2938.768.0* oder höher ist, wie in der folgenden Abbildung gezeigt, können Sie das "SEMM"-Paket zum Aktivieren der Betriebssystemmigration erstellen.

       ![Screenshot der Seite "Surface" in der Surface-App.](images/shm-fig1.png)
 
   - Wenn die Version UEFI vor Version 694.2938.768.0 liegt, müssen Sie eine aktuelle Version abrufen, indem Sie entweder das Image des Window 10 Team 2020 Update Bare Metal Recovery (BMR) installieren oder Windows Update verwenden.
   
**So aktualisieren Sie UEFI über Windows Update:**

1. Melden Sie sich auf Surface Hub 2S als **Administrator an.** 

    >[!Note]
    > Wenn Sie Ihren Benutzernamen oder Ihr Administratorkennwort nicht kennen, müssen Sie das Gerät zurücksetzen. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Zurücksetzen und Wiederherstellung für Surface Hub 2S.</a>

1. Wechseln Sie **zu "Alle**  >  **Apps–**  >  **Einstellungsupdate"** und  >  **"Sicherheit",** und installieren Sie dann alle Updates. 

1. Starten Sie das Gerät neu. 

1. Überprüfen Sie die UEFI-Version mithilfe der Surface-App.

1. Wenn die Version UEFI zu diesem Zeitpunkt noch nicht Version 694.2938.768.0 oder höher ist, können Sie entweder die oben genannten Schritte wiederholen oder die neueste UEFI erhalten, indem Sie das Windows 10 Team 2020 Update Bare Metal Recovery (BMR)-Image installieren.

**So aktualisieren Sie UEFI über bare Metal Recovery (BMR)-Image:**

1.  Wechseln Sie zur [Surface-Wiederherstellungswebsite,](https://support.microsoft.com/surfacerecoveryimage) und wählen **Sie Surface Hub 2S aus.**

3.  Geben Sie Die Seriennummer des Hubs ein (die sich auf der Rückseite des Hubs neben der Netzverbindung befindet).

4.  Befolgen Sie die Anweisungen zum Herunterladen des Images auf ein formatiertes USB-Laufwerk, indem Sie das Windows 10 Team 2020 Update installieren.

5.  Nachdem das Update abgeschlossen ist und das Gerät beim ersten Setup der OOBE eintsprecht, müssen Sie die OOBE nicht abschließen, die UEFI-Version wird aktualisiert. Schalten Sie stattdessen das Gerät herunter, indem Sie den Netzschalter gedrückt halten, bis der Bildschirm ausgeschaltet wird. 

### Herunterladen von Surface UEFI Configurator- und Surface Hub 2-Treibern und -Firmware

Auf einem separaten PC:

1. Wählen Sie <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> auf der Seite "Surface Tools for </a> IT" die Option **"Herunterladen" aus.**

1. Wählen Sie die Surface UEFI Configurator-MSI-Datei aus, und laden Sie sie herunter, und installieren Sie sie auf einem separaten PC. Das Surface UEFI Configurator-Tool kann nicht auf einem Surface Hub 2S ausgeführt werden, während die Windows 10 Team Edition installiert ist.

1. Laden Sie die <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows Installer -MSI-Datei für Surface Hub 2 Drivers and Firmware </a> herunter. Sie verwenden diese Datei bei der Installation des neuen Betriebssystems.

### Vorbereiten des SEMM-Zertifikats

Wenn Sie surface UEFI Configurator noch nicht verwendet haben, müssen Sie ein Zertifikat vorbereiten. Dieses Zertifikat stellt sicher, dass Sie nach der Registrierung eines Geräts bei SEMM nur mithilfe von Paketen, die mit dem genehmigten Zertifikat erstellt werden, die Einstellungen für die UEFI ändern können. 

Wie Sie ein Zertifikat erhalten, hängt von der Größe oder Komplexität Ihrer Organisation ab:

- Unternehmensorganisationen verwalten in der Regel ihre eigene Infrastruktur, um Zertifikate gemäß den Standardsicherheitsmethoden zu generieren.

- Mittelständische Unternehmen und andere Unternehmen können zertifikate von Partneranbietern erhalten. Diese Option wird für Organisationen empfohlen, die nicht über ausreichendes IT-Know-how oder ein dediziertes IT-Sicherheitsteam verfügen.

- Alternativ können Sie ein selbst signiertes Zertifikat mithilfe eines PowerShell-Skripts generieren. Weitere Informationen finden Sie unter den Zertifikatanforderungen für <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> den Surface Enterprise-Verwaltungsmodus. </a> Sie können auch PowerShell verwenden, um Ein eigenes Zertifikat zu erstellen. Weitere Informationen finden Sie in der <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> Dokumentation "New-SelfSignedCertificate". </a>

Das semm-Paket, das Surface UEFI Configurator erstellt, muss durch ein Zertifikat gesichert werden. Das Zertifikat überprüft die Signatur von Konfigurationsdateien, bevor die UEFI-Einstellungen angewendet werden können. Weitere Informationen finden Sie in der <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM-Dokumentation. </a>
 
 
### Erstellen eines "SEMM"-Pakets

1. Installieren Sie auf einem separaten PC das Surface UEFI Configurator-Tool, das Sie zuvor heruntergeladen haben. 

2. Öffnen Sie den Surface UEFI-Konfigurator, und wählen Sie dann **"Start" aus.**

   ![Öffnen Sie den Surface UEFI-Konfigurator.](images/shm-fig2.png)
   
3. Wählen **Sie "Surface Devices"** und dann **"Next" aus.**

   ![Wählen Sie Surface Devices aus.](images/shm-fig3.png)
  
4. Wählen Sie **das Konfigurationspaket aus.**

   ![Wählen Sie "Konfigurationspaket" aus.](images/shm-fig4.png)
  
5. Wählen Sie **Zertifikatschutz aus.**

   ![Wählen Sie Zertifikatschutz aus.](images/shm-fig5.png)

   Sie werden aufgefordert, Ihre Zertifikat-PFX-Datei hinzuzufügen.

   ![Fügen Sie Ihr Zertifikat hinzu.](images/shm-fig6.png)
   
7. Geben Sie Ihr Zertifikatkennwort ein, und wählen Sie dann **OK aus.**

   ![Geben Sie Ihr Zertifikatkennwort ein, und wählen Sie "OK" aus.](images/shm-fig7.png)

8. Wählen **Sie Kennwortschutz aus,** um Surface UEFI ein Kennwort hinzuzufügen. Sie benötigen dieses Kennwort, wenn Sie mit UEFI starten. Es *wird dringend empfohlen,* ein UEFI-Kennwort für Surface Hub 2S zu verwenden.

   ![Wählen Sie "Kennwortschutz" aus.](images/shm-fig8.png)
   
9. Legen Sie ein UEFI-Kennwort ein, und wählen Sie dann **OK aus.**

   > [!IMPORTANT]
   > Speichern Sie das Kennwort an einem sicheren Ort, auf den Ihre IT-Administratoren, die Surface Hub verwalten, zugriffen können. Wenn das Kennwort verloren geht, kann es nicht wiederhergestellt werden. 

   ![Geben Sie Ihr UEFI-Kennwort ein.](images/shm-fig9.png)

10. Wählen **Sie Surface Hub 2S**und dann Weiter **aus.**

    ![Wählen Sie Surface Hub 2S aus.](images/shm-fig10.png)
   
11. Wählen Sie **Weiter** aus.

    ![Wählen Sie Weiter aus.](images/shm-fig10a.png)

12. Um die Installation von Windows 10 Pro oder Enterprise zu ermöglichen, aktivieren Sie **"EnableOsMigration",** und wählen Sie dann **"Weiter" aus.**

    ![Wählen Sie "O S-Migration aktivieren" aus.](images/shm-fig11.png)
    
    ![Legen Sie "Betriebssystemmigration aktivieren" auf "Ein" festgelegt.](images/shm-fig12.png)

### Verwalten der REGISTRIERUNG von SEMM

Die Registrierung von Geräten bei SEMM wirkt sich darauf aus, wie Sie das Gerät in Zukunft verwalten können. Nachdem Sie beispielsweise ein "SEMM"-Paket angewendet haben, sind im Menü "UEFI" des Geräts alle UEFI-Einstellungen nicht verfügbar (gesperrt). Standardwerte für andere Einstellungen wie **IPv6 für den PXE-Start** sind ebenfalls nicht verfügbar. 

Wenn Sie die UEFI-Einstellungen nach Abschluss der Migration ändern möchten, wenden Sie ein anderes "SEMM"-Paket an, oder stellen Sie die Registrierung des Geräts bei SEMM auf. Wenn Sie ein weiteres "SEMM"-Paket anwenden, um die Einstellungen der UEFI zu ändern, müssen Sie beim Erstellen des neuen "SEMM"-Pakets das ursprüngliche Zertifikat verwenden. Verwenden Sie das UEFI-Konfigurator-Tool, und lassen Sie **"EnableOSMigration"** deaktiviert (nicht aktiviert, wie in den ursprünglichen Migrationsschritten gezeigt).

#### Zusammenarbeit mit Partnern

Wenn Ihr Unternehmen die Migration zu Windows 10 Pro oder Enterprise auf Surface Hub 2 auslagern, sollte der Partner das SEMM-Zertifikat, das SEMM-Paket und das Kennwort für UEFI an Sie übertragen.  Alternativ können Sie nach der Migration des Hubs die Registrierung von SEMM sofort wieder auflösen, wodurch die lokale Verwaltung der UEFI und die Übertragung des Geräts an eine andere Partei ermöglicht wird. Dennoch wird dringend empfohlen, ein UEFI-Kennwort zu verwenden, das nach der Migration konfiguriert werden kann. Weitere Informationen finden Sie unter [Verwalten von Surface UEFI-Einstellungen.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Zurück zum Windows 10-Team

Wenn Sie ihr Gerät nach der Migration wie unten beschrieben in Windows 10 Team wiederherstellen [möchten,](#roll-back-to-windows-10-team)wird empfohlen, die Registrierung des Hubs von SEMM zu entfernen. Weitere Informationen finden Sie unter ["Registrieren von Surface-Geräten über SEMM".](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)


#### Speichern des "SEMM"-Pakets auf einem USB-Laufwerk

1. Schließen Sie ein USB-Laufwerk an Ihren PC an. 

1. Wählen **Sie Hub 2S**und dann **"Weiter" aus.**

   ![USB auswählen](images/shm-fig13.png)

   > [!WARNING]
   > Alle vorhandenen Daten auf dem USB-Laufwerk werden gelöscht, wenn das "SEMM"-Paket erstellt wird. Entfernen Sie vor dem Erstellen des SEMM-Pakets alle Dateien vom USB-Laufwerk, das Sie speichern möchten.
   
2. Wählen Sie **Erstellen** aus.

   ![Wählen Sie Erstellen aus.](images/shm-fig14.png)

3. Erfassen Sie einen Screenshot dieser Seite, und wählen Sie dann **"Ende" aus.** Ihr SEMM-Paket ist jetzt bereit. Sie enthält das SEMM-Paket *"DfciUpdate.dfi"* und eine Textdatei mit dem SEMM-Fingerabdruck (die letzten beiden Zeichen des Fingerabdrucks des Zertifikats).

   ![Wählen Sie "Ende" aus.](images/shm-fig15.png)
   
4. Speichern Sie die letzten beiden Zeichen des Zertifikatfingerabdrucks. Sie benötigen diese Zeichen, um SEMM zu aktivieren, wenn Sie das Paket auf Surface Hub 2S anwenden.

### Vorbereiten eines USB-Flashlaufwerks, das ein Windows 10-Image, ein SEMM-Paket und Surface Hub 2-Treiber und -Firmware enthält

Sie können ein Windows 10 Pro- oder Enterprise-Image (Version 1903 oder höher) mit einer der folgenden Optionen installieren:

- Ihre aktuelle Imageerstellungslösung.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Surface Deployment Accelerator </a> . Verwenden Sie dieses Tool, um ein startbares Windows 10-Image zu erstellen. Das Image kann alle aktuellen Windows 10-Updates, Office, andere apps, die Sie auswählen, sowie die erforderlichen Treiber und Firmware enthalten. 

- USB-Speicherlaufwerk, das ein Windows 10 Pro- oder Enterprise-Image enthält. Installieren Sie dann <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2. </a>
 
Im folgenden Verfahren wird beschrieben, wie Sie ein USB-Flashlaufwerk von Installationsmedien erstellen und dann die PAKETdateien für SEMM sowie die Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2-MSI-Dateien hinzufügen. Wenn Sie andere Bereitstellungsmethoden verwenden, wechseln Sie zum Abschnitt "Aktualisieren von [UEFI auf Surface Hub 2S",](#update-uefi-on-surface-hub-2s-to-enable-os-migration) um den Abschnitt zur Betriebssystemmigration in diesem Artikel zu aktivieren.

> [!NOTE]
> Nachdem Sie die Installation abgeschlossen haben, benötigen Sie eine gültige Lizenz für Windows 10 Pro oder Windows 10 Enterprise, die von Ihrer vorhandenen Windows 10 -Teamlizenz getrennt ist.

1. Befolgen Sie zum Erstellen einer Windows 10 Pro-Installation auf der Seite "Windows 10 herunterladen" die Anweisungen zum Herunterladen des <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> </a> Medienerstellungstools. Um Windows 10 Enterprise herunterzuladen, wechseln Sie zum <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service </a> Center.

1. Fügen Sie ein neues USB-Speicherlaufwerk ein. 

1. Öffnen Sie das Medienerstellungstool, wählen **Sie "Installationsmedium erstellen"** und dann **"Weiter" aus.**

   ![Erstellen Sie Installationsmedien.](images/shm-fig16.png)
   
1. Wählen Sie eine Sprache und dann **Windows 10 und** **64-Bit (x64) aus.** Wählen Sie dann **"Weiter" aus.**

   ![Wählen Sie die Sprache aus, und wählen Sie Windows 10 und 64-Bit aus. Wählen Sie dann "Weiter" aus.](images/shm-fig17.png)
   
1. Wählen **Sie "USB-Speicherlaufwerk"** und dann **"Weiter" aus.**

   ![Wählen Sie "U S B-Flashlaufwerk" und dann "Weiter" aus.](images/shm-fig18.png)
   
1. Wenn der Download abgeschlossen ist, wählen Sie **"Fertig stellen" aus.**

   ![Wählen Sie „Fertig stellen“.](images/shm-fig19.png)
   
1. Kopieren Sie die SEMM-Paketdateien und die Treiber und firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 (die MSI-Datei) in das Stammverzeichnis des USB-Flashlaufwerks (*BOOTME*), das Ihr Windows 10-Image enthält. Das BOOTME-USB-Laufwerk enthält:

    - Ihr startbares Windows 10-Image.
    
    - SEMM-Paketdateien (in das Stammverzeichnis des USB-Laufwerks kopiert).
    
      - *DfciUpdate.dfi*.
      - Textdatei mit dem SEMM-Fingerabdruck. (In diesem Beispiel ist die Datei *SurfaceUEFI_2020Aug25_1058.txt*.) Der automatisch generierte Datums-/Uhrzeitstempel entspricht dem Datum, an dem Sie die Datei mithilfe des Surface -UEFI-Konfigurators erstellt haben.

   - Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Kopieren Sie diese Datei in das Stammverzeichnis des USB-Laufwerks.

### Aktualisieren von UEFI auf Surface Hub 2S zum Aktivieren der Betriebssystemmigration

1. Fügen Sie das BOOTME-Laufwerk in den USB-A-Port auf Surface Hub 2S ein. Eine Liste der erforderlichen Dateien finden Sie im vorherigen Abschnitt.

2. So starten Sie UEFI:

   1. Deaktivieren (Herunterfahren) des Surface Hub 2S.
   1. Halten Sie Volume **+** gedrückt, und drücken Sie dann den Netzschalter, und lassen Sie ihn los.
   1. Halten Sie **"Volume +" so lange** bei, bis das Menü "UEFI" angezeigt wird.
   
      ![Halten Sie die Lautstärketaste gedrückt, bis das Menü "UEFI" angezeigt wird.](images/shm-fig20.png)
      
3. Wenn das Gerät neu gestartet wird, geben Sie das zuvor erstellte UEFI-Kennwort ein (falls zutreffend (dringend empfohlen).

   ![Geben Sie das Kennwort für die UEFI ein.](images/shm-fig22.png)
   
4. Wählen Sie im Menü ****"UEFI" die Option  >  **"Management Install from USB" aus.**

   ![Wählen Sie "Verwaltung und Installation in U S B" aus.](images/shm-fig21.png)
   
5. Wählen **Sie jetzt Neu starten**aus, wie in der folgenden Abbildung gezeigt. Das Gerät wird neu gestartet. In der Mitte des Fensters wird ein weißes Microsoft-Logo angezeigt, das dann heruntergefahren wird.

   ![Wählen Sie jetzt "Neu starten" aus.](images/shm-fig25.png)
   
6. Drücken und loslassen Sie den Netzschalter. Aktivieren Sie im angezeigten roten Fenster den Surface Enterprise-Verwaltungsmodus. 

7. Geben Sie ihren aus zwei Zeichen gedruckten Zertifikatfingerabdruck und ihr Kennwort für die UEFI-Einstellungen ein. Wählen Sie dann **OK aus.**

   ![Geben Sie ihren aus zwei Zeichen gedruckten Zertifikatfingerabdruck und ihr Kennwort für die UEFI-Einstellungen ein.](images/shm-fig23.png)
 
   > [!NOTE]
   > Nachdem Sie SEMM auf Ihrem Gerät aktiviert haben, wird die neue UEFI-Einstellung **"EnableOSMigration"** angewendet. Sie können nicht mehr auf Windows 10 Team zugreifen. Stattdessen müssen Sie mit dem nächsten Schritt fortfahren und Windows 10 Pro oder Windows 10 Enterprise installieren. 

   Das Gerät wird neu gestartet. Das weiße Logo wird in der Mitte des Bildschirms angezeigt und dann erneut heruntergefahren.

### Installieren von Windows 10 Pro oder Enterprise

1. Wenn sich ihr startbares Windows 10 Pro- oder Unternehmenslaufwerk noch nicht im Surface Hub 2-USB-A-Port befindet, fügen Sie es jetzt ein. Drücken und lassen Sie dann den Netzschalter los. 

    Wenn das Gerät gestartet wird, wird das weiße Logo in der Mitte des Bildschirms angezeigt. Dann sehen Sie einen sich drehenden Kreis unter dem weißen Logo.

3. Wenn das Gerät nicht automatisch mit dem USB-Laufwerk startet, schalten Sie das Gerät aus (ziehen Sie das Netzkabel aus, und schließen Sie es wieder an). Nachdem Sie das Netzkabel wieder angeschlossen haben, sollte das Gerät nach einigen Sekunden gestartet werden. Dann wird das weiße Logo in der Mitte des Bildschirms angezeigt. 

    Wenn das Gerät nicht einschalten kann, drücken Sie den Netzschalter, und lassen Sie ihn los. Unmittelbar nachdem das Logo in der Mitte des Bildschirms angezeigt wird, drücken und halten Sie die Schaltfläche "Volume **-"** gedrückt, bis der sich drehende Kreis unter dem weißen Logo angezeigt wird.
 
   ![Starten Sie windows 10 vom Laufwerk "U S B".](images/shm-fig26.png)
   
4. Wenn das Setup der out-of-Box Experience (OOBE) gestartet wird, folgen Sie den Anweisungen zum Installieren von Windows 10 Pro oder Enterprise (Version 1903 oder höher).

### Installieren von Surface Hub 2-Treibern und -Firmware

Um sicherzustellen, dass Ihr Gerät über die neuesten Updates und Treiber verfügt, installieren Sie Treiber und Firmware für <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro und Enterprise OS auf Surface Hub 2. </a> Starten Sie das Gerät nach der Installation der Treiber- und Firmware-MSI neu. Nachdem Sie den Hub wieder ein netziert haben, schalten Sie den PC eine Stunde lang ein, und starten Sie das Gerät erneut. Sie werden nicht zum zweiten Neustart aufgefordert. Je nach Zustand des Computers vor der Migration zu Windows 10 Pro oder Enterprise kann dieser zweite Schritt erforderlich sein, um sicherzustellen, dass die Firmware aktualisiert wurde.
 
## Konfigurieren empfohlener Einstellungen

Informationen zum vollständigen Konfigurieren von Surface Hub 2S als persönliches Produktivitätsgerät finden Sie unter "Konfigurieren von <a href="surface-hub-2-post-install.md" target="_blank"> Windows 10 Pro oder Enterprise auf Surface Hub 2". </a>

> [!NOTE]
>Wenn die in diesem Artikel beschriebenen Schritte ihr Gerät nicht erfolgreich zu Windows 10 Pro oder Enterprise für Surface Hub 2 migrieren, wenden Sie sich an <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> den Surface Hub-Support. </a>

## Rollback auf Windows 10 Team

Wenn Sie Ihr Gerät in Windows 10 Team wiederherstellen möchten, lesen Sie "Zurücksetzen und Wiederherstellung <a href="surface-hub-2s-recover-reset.md" target="_blank"> für Surface Hub 2S". </a>

> [!NOTE]
> Bevor Sie ein Rollback auf Windows 10 Team erstellen, empfiehlt es sich, die Registrierung von Hub bei SEMM zu entsperren. Weitere Informationen finden Sie unter ["Registrieren von Surface-Geräten über SEMM".](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## Versionsverlauf

In der folgenden Tabelle sind die Änderungen an diesem Artikel zusammengefasst.

| Version | Date               | Beschreibung                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14. Dezember 2020 | Enthält [](#install-surface-hub-2-drivers-and-firmware) weitere Informationen zum Installieren der MSI-Datei für "Treiber und Firmware für Windows 10 Pro und Enterprise OS auf Surface Hub 2", und informiert Sie, dass je nach Zustand des Systems möglicherweise ein zweiter Neustart erforderlich ist.                                                          |
| v. 1.3  | 3. Dezember 2020 | Aktualisiert mit Anleitungen zum [Verwalten der SEMM-Registrierung.](#managing-semm-enrollment)                                                       |
| v. 1.2  | 29. September 2020 | Verschiedene Updates für Feedback zur Benutzerfreundlichkeit.                                                        |
| v. 1.1  | 15. September 2020 | Zusätzliche Hinweise in der Einführung, in der die Lizenzierungsanforderungen für die Installation eines neuen Betriebssystems erläutert werden. |
| v. 1.0  | 1. September 2020  | Neuer Artikel.                                                                                           |
