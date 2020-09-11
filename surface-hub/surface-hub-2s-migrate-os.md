---
title: Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2
description: In diesem Artikel wird beschrieben, wie Sie von Windows 10 Team auf Surface Hub 2 zu Windows 10 pro oder Windows 10 Enterprise migrieren.
keywords: Surface Hub-Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/09/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 5431cb9c11fbcfadf0ef517164521c237fb6b3bb
ms.sourcegitcommit: 75940bb1ab4e08c96736923859c7dd673dcf8d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009623"
---
# Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2

## Einführung

Surface Hub 2S ist mit dem Windows 10-Team vorinstalliert, einer angepassten Edition von Windows 10, die eine einfache Zusammenarbeit in Besprechungsraum Umgebungen ermöglicht. Sie haben jetzt die Möglichkeit, Windows 10 pro oder Enterprise zu verwenden, um Surface Hub 2S ähnlich wie jeden anderen PC zu verwenden. 

> [!IMPORTANT]
>Im Gegensatz zu einem typischen Upgrade oder einer Migration erfordert dieser Vorgang, wie auf dieser Seite beschrieben, eine normative Vorgehensweise. Überprüfen Sie die [Lösungskomponenten](#solution-components) und den [Migrations Workflow](#migration-workflow-summary) , bevor Sie fortfahren.

Sie starten die Migration von einem Windows 10-Team mit einem separaten PC und einem herunterladbaren Tool – **Surface UEFI Configurator** – zum Erstellen eines Pakets, das eine neue UEFI-Einstellung enthält, die Sie auf Surface Hub 2S anwenden.  Die Oberflächen UEFI-Konfiguration fungiert als Schnittstelle in Surface Enterprise Management Mode (Semm), die die zentralisierte Verwaltung von Firmwareeinstellungen auf Surface-Geräten in einer Unternehmensumgebung vereinfacht. Weitere Informationen zu Semm finden Sie in der [Dokumentation zu Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 

## Lösungskomponenten

- Surface Hub 2S-Gerät mit Windows 10 Team-Betriebssystem
- Separates Gerät mit Windows 10
- Tool für die Oberflächen UEFI-Konfiguration
- Windows 10 pro-oder Enterprise-Betriebssystemabbild, Version 1903 oder höher
- Zwei USB-Laufwerke mit 16 GB Speicher, FAT32-Format
- Treiber und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2, Windows Installer. MSI-Datei
- Internetverbindung
- Imaging-Lösung (optional)

 
## Zusammenfassung des Migrations Workflows

| Schritt  | Aktion                                                                                                 | Zusammenfassung                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Überprüfen der UEFI-Version auf Surface Hub 2S erfüllt die Mindestanforderungen](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Stellen Sie sicher, dass die UEFI-Version 694.2938.768.0 oder höher ist.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Herunterladen von Surface UEFI Configurator und Surface Hub 2-Treibern und-Firmware](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Laden Sie den [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) von Surface Tools herunter, und installieren Sie ihn auf einem separaten PC. Laden Sie [Treiber und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2 herunter. MSI-Datei](https://www.microsoft.com/download/details.aspx?id=101974) , und speichern Sie Sie zur Verwendung in Schritt 5. |
| 3 | [Vorbereiten des Semm-Zertifikats](#prepare-semm-certificate)                                                                          | Vorbereiten des erforderlichen Zertifikats für die Ausführung des Surface UEFI-Konfigurators oder Verwenden des aktuellen Zertifikats.                                                                                                                                                                                                                                                                                                      |
| 4 | [Erstellen eines Semm-Pakets](#create-semm-package)                                                                               | Starten Sie den Surface UEFI Configurator, um ein Semm-Paket auf einem USB-Laufwerk zu erstellen, das die erforderlichen Konfigurationsdateien enthält, die auf Surface Hub 2S angewendet werden sollen. Kopieren Sie diese Semm-Paketdateien in einen Ordner auf Ihrem PC.                                                                                                                                                                                          |
| 5 | [Vorbereiten des USB-Flashlaufwerks mit Windows 10-Bild, Semm-Paket und Treibern und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Erstellen Sie ein einzelnes USB-Laufwerk (mit dem Namen **BOOTME** in diesem Beispiel), das ein Windows 10-Abbild enthält. Fügen Sie Ihre Treiber und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2 (Schritt 2) und Semm-Paketdateien (Schritt 4) zum **BOOTME** -Laufwerk hinzu.                                                                                                                                                                                                  |
| 6 | [Aktualisieren von UEFI auf Surface Hub 2S zur Aktivierung der Betriebssystemmigration](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Verwenden Sie das **BOOTME** -Laufwerk zum Booten von Surface Hub 2S zum UEFI-Menü, und installieren Sie Semm-Paket.|
| 7 | [Installieren von Windows 10 pro oder Enterprise, Version 1903 oder höher](#install-windows-10-pro-or-enterprise)                                        | Verwenden Sie das **BOOTME** -Laufwerk, um **Windows 10 pro oder Enterprise** , Version 1903 oder höher, zu installieren.                                                                                                                                                                                                                                                                                 |
| 8 | [Installieren von Treibern und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2](#install-surface-hub-2-drivers-and-firmware)                                        | Wenn Sie sicherstellen möchten, dass Ihr Gerät über alle neuesten Updates und Treiber verfügt, installieren Sie [Treiber und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2. MSI-Datei](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                  |
| 9 | [Vollständiges Konfigurieren des Surface Hub 2S als persönliches Produktivitäts Gerät](#next-steps)                                        |  Aktivieren Sie den Satz empfohlener Einstellungen und Anwendungen zur Optimierung der Verwendung von Surface Hub 2S als persönliches Produktivitäts Gerät.                                                                                                                                                                                                                                                                    |

### Überprüfen der UEFI-Version auf Surface Hub 2S erfüllt die Mindestanforderungen

Die minimale UEFI-Version, die vor der Migration des Surface Hub von Windows 10-Team zu Windows 10-Desktop erforderlich ist, ist **694.2938.768.0**.
 
**So überprüfen Sie die aktuelle UEFI-Version auf Ihrem System:**

1. Klicken Sie auf der Startseite des Surface Hub 2S auf **Start** , und öffnen Sie die **SurfaceApp** (**alle apps**  >  -**Oberfläche**).

2. Wählen Sie **die Oberfläche** aus, um Informationen zum Surface-Hub anzuzeigen, einschließlich der aktuellen Version des UEFI auf dem Gerät. Wenn die UEFI-Version **694.2938.768.0** oder höher ist, wie unten dargestellt, kann UEFI für Sie das Semm-Paket erstellen, um die Betriebssystemmigration zu aktivieren.

    ![Oberfläche-APP öffnen & DGM auswählen](images/shm-fig1.png)
 
3. Wenn die UEFI-Version älter als Version **694.2938.768.0**ist, müssen Sie mithilfe von Windows Update eine aktuelle Version abrufen.

**So aktualisieren Sie UEFI über Windows Update:**
1. Registrieren Sie sich auf dem Surface Hub 2S als Administrator, wechseln Sie zu **"** **alle apps**-  >  **Einstellungen** >  **Aktualisieren" und "Sicherheit**  >  **Windows Update** ", und installieren Sie alle Updates, und starten Sie dann das Gerät neu. Überprüfen Sie die UEFI-Version mithilfe der Surface-app. Hinweis: Wenn Sie Ihren Benutzernamen oder Ihr Administratorkennwort nicht kennen, müssen Sie das Gerät zurücksetzen. Weitere Informationen finden Sie unter [Zurücksetzen und Wiederherstellen für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

2. Wiederholen Sie diese Schritte, bis die UEFI-Version **694.2938.768.0** oder höher ist.

3. Wenn das aktualisierte UEFI nach mehreren versuchen immer noch nicht angezeigt wird, überprüfen Sie den **Update Verlauf** , und suchen Sie nach Instanzen von fehlgeschlagenen Firmware-Installationen. Möglicherweise müssen Sie Ihr Gerät zurücksetzen (**Einstellungen**  >  **Aktualisieren & Sicherheits**  >  **Zurücksetzungs Gerät**).

### Herunterladen von Surface UEFI Configurator und Surface Hub 2-Treibern und-Firmware

Auf einem separaten PC:

- Laden Sie den Microsoft [Surface UEFI-Konfigurator](https://www.microsoft.com/download/details.aspx?id=46703) herunter, und installieren Sie ihn unter Surface Tools. Die Oberflächen UEFI-Konfiguration kann nicht auf Surface Hub 2S ausgeführt werden, während das Windows 10-Team installiert ist.

- Herunterladen von [Surface Hub 2-Treibern und Firmware-Windows Installer. MSI-Datei](https://www.microsoft.com/download/details.aspx?id=101974) , die bei der Installation des neuen Betriebssystems angewendet werden soll.

### Vorbereiten des Semm-Zertifikats

Wenn Sie das Surface UEFI Configurator zum ersten Mal verwenden, müssen Sie ein Zertifikat vorbereiten. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts in Semm nur Pakete verwendet werden können, die mit dem genehmigten Zertifikat erstellt wurden, um UEFI-Einstellungen zu ändern. Die Art und Weise, wie Sie ein Zertifikat erwerben, hängt von der Größe oder Komplexität Ihrer Organisation ab:

- Große Unternehmensorganisationen verwalten in der Regel Ihre eigene Zertifikatinfrastruktur, um Zertifikate pro Standardsicherheitsverfahren zu generieren.

- Mittelständische Unternehmen und andere Personen können beschließen, ein Zertifikat von Drittanbietern zu erhalten. Dies ist die empfohlene Option für Organisationen ohne genügend IT-Fachkenntnisse oder dediziertes IT-Sicherheitsteam.

- Sie können auch ein selbstsigniertes Zertifikat mit einem PowerShell-Skript pro der folgenden Dokumentation generieren: [Zertifikatanforderungen für den Surface Enterprise-Verwaltungsmodus](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Oder verwenden Sie PowerShell zum Erstellen eines eigenen Zertifikats pro der folgenden Dokumentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).

Das Semm-Paket muss mit einem Zertifikat gesichert werden, um die Signatur von Konfigurationsdateien zu überprüfen, bevor UEFI-Einstellungen angewendet werden können. Weitere Informationen finden Sie unter Dokumentation zu [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .
 
 
### Erstellen eines Semm-Pakets

1. Öffnen Sie die **Oberflächen UEFI-Konfiguration** , und wählen Sie **Start**aus.

   ![Oberflächen UEFI-Konfigurator öffnen](images/shm-fig2.png)
   
2. Wählen Sie **Surface Devices** aus, und wählen Sie dann **weiter**aus.

   ![Surface Devices auswählen](images/shm-fig3.png)
  
3. Wählen Sie **Konfigurationspaket**aus.

   ![Konfigurationspaket auswählen](images/shm-fig4.png)
  
4. Wählen Sie **Zertifikatschutz**aus.

   ![Zertifikatschutz auswählen](images/shm-fig5.png)

5. Sie werden aufgefordert, die Datei "Certificate. pfx" hinzuzufügen.

   ![Sie werden aufgefordert, Ihr Zertifikat hinzuzufügen.](images/shm-fig6.png)
   
6. Geben Sie Ihr **Zertifikat Kennwort ein** , und wählen Sie **OK**aus.

   ![Geben Sie Ihr Zertifikat Kennwort ein, und wählen Sie OK aus.](images/shm-fig7.png)

7. Wählen Sie **Kennwortschutz** aus, um ein Kennwort zu Surface UEFI hinzuzufügen. Dieses Kennwort ist erforderlich, wenn Sie mit UEFI Booten. Es wird **dringend empfohlen** , ein UEFI-Kennwort festzulegen, das Sie auf Surface Hub 2S verwenden werden.

   ![Klicken Sie auf Kennwortschutz.](images/shm-fig8.png)
   
8. Legen Sie ein **UEFI-Kennwort** ein, und wählen Sie **OK**aus.

   ![Geben Sie Ihr UEFI-Kennwort ein.](images/shm-fig9.png)

   > [!IMPORTANT]
   > Notieren Sie sich Ihr Kennwort. Wenn Sie Ihr Kennwort vergessen oder verlieren, gibt es keinen Wiederherstellungsvorgang. 

9. Wählen Sie **Surface Hub 2S** aus, und wählen Sie dann **weiter**aus.

   ![Surface Hub 2S auswählen](images/shm-fig10.png)
   
10. Wählen Sie **Weiter** aus.

    ![Wählen Sie weiter aus.](images/shm-fig10a.png)

11. Wenn Sie die Installation von Windows 10 pro oder Enterprise zulassen möchten, wählen Sie **EnableOsMigration aus.**

    ![Wählen Sie Betriebssystem Migration aktivieren aus.](images/shm-fig11.png)
    
12. Legen Sie **EnableOSMigration** auf **ein** , und wählen Sie **weiter**aus.

    ![Festlegen der Aktivierung der Betriebssystem Migration auf ein](images/shm-fig12.png)

> [!NOTE]
> Nachdem Sie ein Semm-Paket angewendet haben, werden alle UEFI-Einstellungen im UEFI-Menü auf dem Gerät abgeblendet (gesperrt) angezeigt. Dies umfasst Standardwerte für andere Einstellungen wie IPv6 für PXE-Start. Um UEFI-Einstellungen zu ändern, müssen Sie ein weiteres Semm-Paket anwenden oder das Gerät von Semm aufheben.

#### Speichern des Semm-Pakets auf einem USB-Laufwerk

1. Schließen Sie ein USB-Laufwerk an Ihren PC an. Wählen Sie **Hub 2S** aus, und wählen Sie dann **weiter**aus.

   ![USB auswählen](images/shm-fig13.png)
   
2. Wählen Sie **Erstellen** aus.

   ![Wählen Sie erstellen aus.](images/shm-fig14.png)

3. Erfassen Sie einen Screenshot dieser Seite, und wählen Sie dann **Beenden**aus. Ihr Semm-Paket ist nun bereit und enthält das Semm-Paket **DfciUpdate. EDI** und eine Textdatei mit dem Semm-Fingerabdruck (die letzten beiden Zeichen des Fingerabdrucks des Zertifikats).

   ![Ende auswählen](images/shm-fig15.png)
   
4. Speichern Sie die letzten 2 Zeichen des Zertifikat Fingerabdrucks, die zum Aktivieren von Semm erforderlich sind, wenn Sie das Paket auf Surface Hub 2S anwenden.

### Vorbereiten des USB-Flashlaufwerks mit Windows 10-Bild, Semm-Paket und Surface Hub 2-Treibern und-Firmware

Sie können ein Windows 10 pro-oder Enterprise-Abbild (Version 1903 oder höher) mithilfe einer der folgenden Optionen installieren:

- Ihre aktuelle Imaging-Lösung.

- Der [Surface-Bereitstellungs Beschleuniger](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) ermöglicht Ihnen das Erstellen eines startbaren Windows 10-Bilds, das alle aktuellen Windows 10-Updates, Office, andere Apps ihrer Wahl sowie die erforderlichen Treiber und Firmware umfassen kann. 

- USB-Speicherstick mit Windows 10 pro oder Enterprise-Image, gefolgt von der Installation von  [Treibern und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 

In diesem Verfahren wird beschrieben, wie Sie ein USB-Flashlaufwerk von Installationsmedien erstellen und dann die Semm-Paketdateien und-Treiber und-Firmware für Windows 10 pro und Enterprise auf Surface Hub 2 hinzufügen. MSI-Datei. Wenn Sie andere Bereitstellungsmethoden verwenden, fahren Sie mit dem folgenden Abschnitt fort: [Aktualisieren von UEFI auf Surface Hub 2S zur Aktivierung der Betriebssystemmigration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).

> [!NOTE]
> Nach der Installation benötigen Sie eine gültige Lizenz für Windows 10 pro oder Windows 10 Enterprise.

1. Wenn Sie eine Windows 10 pro-Installation erstellen möchten, folgen Sie den Anweisungen auf der Seite [Herunterladen von Windows 10](https://www.microsoft.com/software-download/windows10) für die Verwendung des **Medien Erstellungs** Tools. Wenn Sie Windows 10 Enterprise herunterladen möchten, wechseln Sie zum [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

2. Legen Sie ein neues **USB-Speicher** Laufwerk ein. Starten Sie das **Medien Erstellungs** Tool, wählen Sie **Installationsmedien erstellen** aus, und wählen Sie dann **weiter**aus.

   ![Erstellen von Installationsmedien](images/shm-fig16.png)
   
3. Wählen Sie Sprache, Windows 10 und 64-Bit (x64) aus, und wählen Sie dann **weiter**aus.

   ![Wählen Sie Sprache, Windows 10 und 64-Bit aus & wählen Sie weiter aus.](images/shm-fig17.png)
   
4. Wählen Sie **USB-Flash Drive** und dann **weiter**aus.

   ![Wählen Sie USB-Flashlaufwerk und dann weiter aus.](images/shm-fig18.png)
   
5. Wenn der Download abgeschlossen ist, wählen Sie **Fertig stellen**aus.

   ![Wählen Sie fertig stellen aus.](images/shm-fig19.png)
   
6. Kopieren Sie die Semm-Paketdateien und-Treiber und-Firmware für Windows 10 pro und Enterprise auf Surface Hub 2. MSI auf dem USB-Stick (**BOOTME**) mit Ihrem Windows 10-Bild:

    - DfciUpdate. EDI
    - Textdatei mit dem Semm-Fingerabdruck (In diesem Beispiel: SurfaceUEFI_2020Aug25_1058.txt)
    - Treiber und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)

### Aktualisieren von UEFI auf Surface Hub 2S zur Aktivierung der Betriebssystemmigration

Verwenden Sie Ihr **BOOTME** -Laufwerk, um die Semm-Paketdateien zu installieren und das UEFI zu aktualisieren, wodurch Surface Hub für die Ausführung von Windows 10 pro oder Enterprise aktiviert wird. Starten Sie dann vom **BOOTME** -Laufwerk, um Windows 10 zu installieren.

1. Fügen Sie Ihr **BOOTME** -Laufwerk mit Semm-Paketdateien, Treibern und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2 ein. MSI und Windows 10 installieren Dateien in den USB-Anschluss des Surface Hub 2S.  

2. So starten Sie in UEFI:

   1. Schalten Sie den Surface Hub 2S zunächst aus (Herunterfahren).
   1. Halten Sie **Lautstärke +** gedrückt, und drücken Sie dann die **Power** -Taste, und lassen Sie sie los.
   1. Halten Sie die **Lautstärke +** gedrückt, bis das UEFI-Menü angezeigt wird.
   
      ![Halten Sie die Lautstärke + gedrückt, bis das UEFI-Menü angezeigt wird](images/shm-fig20.png)
      
3. Wenn das Gerät neu gestartet wird, geben Sie das UEFI-Kennwort ein, das Sie zuvor erstellt haben, falls zutreffend (dringend empfohlen).

   ![Wenn das Gerät neu gestartet wird, geben Sie Ihr UEFI-paassword](images/shm-fig22.png)
   
4. Wählen Sie im UEFI-Menü die Option **Verwaltungs**  >  **Installation von USB aus**.

   ![Auswählen von Verwaltungs & von USB installieren](images/shm-fig21.png)
   
5. Wählen Sie **jetzt neu starten**aus, wie unten dargestellt. Das Gerät wird neu gestartet und zeigt das weiße 4-Quadrat-Logo in der Mitte des Bildschirms an und wird dann heruntergefahren.

   ![Wählen Sie jetzt neu starten aus.](images/shm-fig25.png)
   
6. Wenn Sie die Power-Taste drücken und loslassen, wird ein Roter Bildschirm eingeblendet, in dem Sie aufgefordert werden, den Surface Enterprise-Verwaltungsmodus zu aktivieren. 

7. Geben Sie den **Daumenabdruck**Ihres zweistelligen Zertifikats, das **Kennwort für UEFI-Einstellungen** ein, und wählen Sie dann **OK**aus.

   ![Geben Sie den Daumenabdruck Ihres 2-stelligen Zertifikats ein](images/shm-fig23.png)
 
   > [!NOTE]
   > Nachdem Sie Semm auf Ihrem Gerät aktiviert haben, wird die neue UEFI-Einstellung **EnableOSMigration** angewendet. Sie sind nicht mehr in der Lage, auf das Windows 10-Team zuzugreifen, und müssen mit dem nächsten Schritt fortfahren und Windows 10 pro oder Windows 10 Enterprise installieren. 

8. Das Gerät wird neu gestartet, zeigt das weiße 4-Quadrat-Logo in der Mitte des Bildschirms an und wird dann wieder geschlossen.

### Installieren von Windows 10 pro oder Enterprise

1. Wenn Ihr startbares Windows 10 pro-oder Enterprise-Laufwerk noch nicht im Surface Hub 2 USB-A-Port vorhanden ist, legen Sie es jetzt ein, und drücken Sie dann die Power-Taste, und lassen Sie sie los.

2. Wenn das Gerät gestartet wird, sehen Sie das weiße 4-Quadrat in der Mitte des Bildschirms, und dann sehen Sie einen rotierenden Kreis unter dem weißen viereckigen Logo.

3. Wenn das Gerät nicht automatisch auf das USB-Laufwerk bootet, schalten Sie das Gerät aus (ziehen Sie das Netzkabel ab, und schließen Sie es wieder an). Nachdem Sie das Netzkabel wieder angeschlossen haben, sollte das Gerät nach ein paar Sekunden mit dem weißen 4-quadratischen Logo in der Mitte des Bildschirms Booten, oder Sie können den Netzschalter drücken und loslassen, um das Gerät wieder einzuschalten. Nachdem Sie das viereckige Logo in der Mitte des Bildschirms angezeigt haben, halten Sie die Lautstärketaste gedrückt, bis Sie den Kreis unterhalb des weißen viereckigen Logos sehen.
 
   ![Starten Sie Windows 10 von USB](images/shm-fig26.png)
   
4. Befolgen Sie die Anweisungen zum Installieren von Windows 10 pro oder Enterprise (Version 1903 oder höher), wenn das Setup für die Out-of-Box-Experience (OOBE) gestartet wird.

### Installieren von Surface Hub 2-Treibern und-Firmware

 - Wenn Sie sicherstellen möchten, dass Ihr Gerät über alle neuesten Updates und Treiber verfügt, installieren Sie [Treiber und Firmware für Windows 10 pro und Enterprise auf Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
### Nächste Schritte

Informationen zum vollständigen Konfigurieren von Surface Hub 2S als persönliches Produktivitäts Gerät finden Sie unter [Konfigurieren von Windows 10 pro oder Enterprise auf Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Wenn Sie die in diesem Dokument beschriebenen Schritte bei der Migration Ihres Geräts zu Windows 10 pro oder Enterprise für Surface Hub 2 nicht erfolgreich ausführen, wenden Sie sich bitte an den [Surface Hub-Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

