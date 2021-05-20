---
title: Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2
description: So migrieren Sie von Windows 10 Team Surface Hub 2 zu Windows 10 Pro oder Windows 10 Enterprise.
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
ms.openlocfilehash: 5e2eaa88fe0e5677c78cb5a7d49802ed71d4b902
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576745"
---
# <a name="migrate-to-windows-10-pro-or-enterprise-on-surface-hub-2"></a>Migrieren zu Windows 10 Pro oder Enterprise auf Surface Hub 2

- [Artikelversionsverlauf](#version-history)

Surface Hub 2S ist mit Windows 10 Team installiert. Diese angepasste Edition von Windows 10 erleichtert die Zusammenarbeit in Besprechungsraumumgebungen. Sie können jetzt stattdessen Windows 10 Pro oder Enterprise ausführen, um Ihre Surface Hub 2S wie jeden anderen PC zu verwenden.

> [!IMPORTANT]
> Dieser Migrationsprozess erfordert, dass Sie das in diesem Artikel beschriebene Verfahren befolgen. Bevor Sie fortfahren, lesen Sie [Lösungskomponenten](#solution-components) und [Migrations- und Installationsworkflow](#migration-and-installation-workflow-summary).

> [!NOTE]
> Wenn Sie Windows 10 Pro oder Enterprise installieren, benötigen Sie eine neue Lizenz, die von Ihrer vorhandenen Lizenz Windows 10 Team ist.

Starten Sie die Migration von Windows 10 Team mit einem separaten PC und dem herunterladbaren *Surface UEFI Configurator-Tool.* Das Tool erstellt ein Paket, das eine neue UEFI-Einstellung enthält, die Sie auf die Surface Hub 2S anwenden.  

Surface UEFI Configurator funktioniert als Schnittstelle in den Surface Enterprise Management Mode (SEMM). Es ermöglicht die zentrale Verwaltung von Firmwareeinstellungen auf Surface-Geräten in einer Unternehmensumgebung. Weitere Informationen finden Sie unter [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 
## <a name="solution-components"></a>Lösungskomponenten

- Surface Hub 2S-Gerät, auf dem Windows 10 Team
- Separates Gerät, auf dem Windows 10
- Surface UEFI Configurator-Tool zum Erstellen des SEMM-Pakets
- Windows 10 Pro oder Enterprise Betriebssystemabbild, Version 1903 oder höher
- Zwei USB-Laufwerke mit 16 GB Speicher im FAT32-Format
- Treiber und Firmware für Windows 10 Pro und Enterprise in Surface Hub 2 Microsoft Windows Installer (MSI)-Datei
- Internetverbindung
- Imaging-Lösung (optional)
 
## <a name="migration-and-installation-workflow-summary"></a>Zusammenfassung des Migrations- und Installationsworkflows

| Schritt  | Aktion                                                                                                 | Zusammenfassung                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Überprüfen Sie die UEFI-Version auf der Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).                                  | Die UEFI-Version muss Version *694.2938.768.0* oder höher sein.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Laden Sie Surface UEFI Configurator und die Surface Hub 2 Treiber und Firmware herunter.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Wählen Sie **[auf der Seite Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** die Option Download </a> **aus.** Wählen Sie dann die **Surface UEFI Configurator-MSI-Datei**aus, und laden Sie sie herunter, und installieren Sie sie auf einem separaten PC. Laden Sie auch [die Treiber und Firmware für Windows 10 Pro und Enterprise Betriebssystem unter Surface Hub 2 MSI-Datei herunter.](https://www.microsoft.com/download/details.aspx?id=101974)</a> Speichern Sie dieses Paket für die Verwendung in Schritt 5. |
| 3 | [Bereiten Sie das SEMM-Zertifikat vor.](#prepare-the-semm-certificate)                                                                          | Bereiten Sie das Zertifikat vor, das zum Ausführen von Surface UEFI Configurator erforderlich ist, oder verwenden Sie Ihr aktuelles Zertifikat.                                                                                                                                                                                                                                                                                                      |
| 4 | [Erstellen Sie ein SEMM-Paket.](#create-a-semm-package)                                                                               | Starten Sie Surface UEFI Configurator, um ein SEMM-Paket auf einem USB-Laufwerk zu erstellen. Dieses Paket enthält die Konfigurationsdateien, die Sie auf 2S anwenden Surface Hub müssen. Kopieren Sie diese SEMM-Paketdateien in einen Ordner auf Ihrem PC.                                                                                                                                                                                          |
| 5 | [Laden Sie ein USB-Flashlaufwerk mit Windows 10 Image, dem SEMM-Paket sowie Treibern und Firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Erstellen Sie ein USB-Laufwerk, das ein Windows 10 enthält. In diesem Beispiel heißt das Laufwerk *BOOTME*. Fügen Sie die Treiber und firmware für Windows 10 Pro und Enterprise Betriebssystem auf Surface Hub 2 (aus Schritt 2) und die SEMM-Paketdateien (aus Schritt 4) dem *BOOTME-Laufwerk* hinzu.                                                                                                                                                                                                  |
| 6 | [Aktualisieren Sie das UEFI auf der Surface Hub 2S, um die Migration des Betriebssystems zu aktivieren.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Verwenden Sie *das BOOTME-Laufwerk,* um Surface Hub 2S in das UEFI-Menü zu starten und das SEMM-Paket zu installieren.|
| 7 | [Installieren Windows 10 Pro oder Enterprise.](#install-windows-10-pro-or-enterprise)                                        | Verwenden Sie *das BOOTME-Laufwerk,* um Windows 10 Pro oder Enterprise Version 1903 oder höher zu installieren.                                                                                                                                                                                                                                                                                 |
| 8 | [Installieren Sie Treiber und Firmware für Windows 10 Pro und Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Um sicherzustellen, dass Ihr Gerät über alle neuesten Updates und Treiber verfügt, installieren Sie die Treiber und Firmware für Windows 10 Pro und Enterprise Betriebssystem unter <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2-MSI-Datei.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Konfigurieren Surface Hub 2S als persönliches Produktivitätsgerät.](#configure-recommended-settings)                                        |  Aktivieren Sie die empfohlenen Einstellungen und Anwendungen, um Surface Hub 2S als persönliches Produktivitätsgerät zu optimieren.                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>Überprüfen der UEFI-Version auf Surface Hub 2S

Bevor Sie Surface Hub von Windows 10 Team zu Windows 10 Desktop migrieren, benötigen Sie UEFI Version *694.2938.768.0* oder höher.
 
**So überprüfen Sie die UEFI-Version auf Ihrem System:**

1. Wählen Sie Surface Hub 2S-Startseite **Start**aus, und öffnen Sie dann die Surface-App (**Alle Apps**  >  **Surface**).

2. Wählen **Sie Surface aus,** um Informationen zu Surface Hub, einschließlich der aktuellen UEFI-Version auf dem Gerät. 
   - Wenn die UEFI-Version *694.2938.768.0* oder höher ist, wie in der folgenden Abbildung gezeigt, können Sie das SEMM-Paket erstellen, um die Betriebssystemmigration zu aktivieren.

       ![Screenshot zeigt die Seite "Ihr Surface" in der Surface-App.](images/shm-fig1.png)
 
   - Wenn die UEFI-Version vor Version *694.2938.768.0*liegt, verwenden Sie eine der folgenden Methoden, um eine neuere Version zu erhalten.
   
#### <a name="update-uefi-via-windows-update"></a>Aktualisieren von UEFI über Windows Update

1. Melden Sie Surface Hub 2S als **Administrator an.**

    >[!Note]
    > Wenn Sie Ihren Benutzernamen oder Ihr Administratorkennwort nicht kennen, müssen Sie das Gerät zurücksetzen. Weitere Informationen finden Sie unter [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

1. Wechseln Sie **zu Alle Apps**  >  **Einstellungen**Update and  >  **Security**  >  **Windows Update**, und installieren Sie alle Updates.
1. Starten Sie das Gerät neu.
1. Überprüfen Sie die UEFI-Version mithilfe der Surface-App. Wenn die UEFI-Version nicht Version *694.2938.768.0* oder höher ist, wiederholen Sie diese Schritte, oder verwenden Sie das folgende Verfahren, um die neueste UEFI-Version zu erhalten.

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>Aktualisieren des UEFI über bare Metal Recovery (BMR)-Image

1.  Wechseln Sie zur [Surface-Wiederherstellungswebsite,](https://support.microsoft.com/surfacerecoveryimage) und wählen **Surface Hub 2S aus.**
3.  Geben Sie Ihre Hub-Seriennummer ein. Sie befindet sich auf der Rückseite des Hubs neben der Netzverbindung.
4.  Befolgen Sie die Anweisungen, um das Image auf ein formatiertes USB-Laufwerk herunterzuladen, indem Sie das Windows 10 Team 2020 Update installieren.
5.  Nach dem Update wird das OOBE-Setup (Out-of-Box Experience) des Geräts durchgeführt. Sie müssen das Setup nicht abschließen. Die UEFI-Version ist bereits aktualisiert. Schalten Sie stattdessen das Gerät herunter, indem Sie die Netzschaltfläche gedrückt halten, bis der Bildschirm ausgeschaltet ist.

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>Herunterladen von Surface UEFI Configurator und Surface Hub 2 Treibern und Firmware

Führen Sie auf einem separaten PC die folgenden Schritte aus:

1. Wählen Sie <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> auf der Seite Surface Tools for IT die Option Download </a> **aus.**  
1. Wählen Sie die Surface UEFI Configurator-MSI-Datei aus, und laden Sie sie herunter, und installieren Sie sie auf einem separaten PC. Das Surface UEFI Configurator-Tool kann nicht auf einem Surface Hub 2S ausgeführt werden, Windows 10 Team installiert ist.

1. Laden Sie [die Surface Hub 2 Treiber und firmware Windows Installer MSI-Datei herunter.](https://www.microsoft.com/download/details.aspx?id=101974) Sie verwenden diese Datei, wenn Sie das neue Betriebssystem installieren.

### <a name="prepare-the-semm-certificate"></a>Vorbereiten des SEMM-Zertifikats

Wenn Sie Surface UEFI Configurator noch nicht verwendet haben, müssen Sie ein Zertifikat vorbereiten. Dieses Zertifikat stellt sicher, dass Sie nach der Registrierung eines Geräts in SEMM nur mithilfe von Paketen, die mit dem genehmigten Zertifikat erstellt werden, UEFI-Einstellungen ändern können.

Wie Sie ein Zertifikat erhalten, hängt von der Größe oder Komplexität Ihrer Organisation ab:

- Enterprise Organisationen verwalten in der Regel ihre eigene Infrastruktur, um Zertifikate gemäß den standardmäßigen Sicherheitspraktiken zu generieren.

- Mittelständische Unternehmen und andere Unternehmen entscheiden sich häufig dafür, Zertifikate von Partneranbietern zu erhalten. Diese Option wird für Organisationen empfohlen, die nicht über so viel IT-Kompetenz verfügen oder über ein dediziertes IT-Sicherheitsteam verfügen.

- Alternativ können Sie ein selbst signiertes Zertifikat mithilfe eines PowerShell-Skripts generieren. Weitere Informationen finden Sie unter [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Oder Sie können PowerShell verwenden, um ein eigenes Zertifikat zu erstellen. Weitere Informationen finden Sie in der [Selbst signierten Zertifikatdokumentation.](https://docs.microsoft.com/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate)

Das von Surface UEFI Configurator erstellte SEMM-Paket muss mit einem Zertifikat gesichert werden. Das Zertifikat überprüft die Signatur von Konfigurationsdateien, bevor UEFI-Einstellungen angewendet werden können. Weitere Informationen finden Sie in der [SEMM-Dokumentation.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
### <a name="create-a-semm-package"></a>Erstellen eines SEMM-Pakets

1. Installieren Sie auf einem separaten PC das Surface UEFI Configurator-Tool, das Sie zuvor heruntergeladen haben.

1. Öffnen Sie Surface UEFI Configurator, und wählen Sie dann **Start aus.**

   ![Surface UEFI Configurator Startbildschirm.](images/shm-fig2.png)
   
1. Wählen **Sie Surface Devices**aus, und wählen Sie dann Weiter **aus.**

   ![Screenshot zeigt die ausgewählte Option Surface Devices.](images/shm-fig3.png)
  
1. Wählen Sie **Konfigurationspaket aus.**

   ![Screenshot zeigt "Konfigurationspaket auswählen" ausgewählt.](images/shm-fig4.png)
  
1. Wählen Sie **Zertifikatschutz aus.**

   ![Screenshotshows sollten "Zertifikatschutz auswählen" auswählen.](images/shm-fig5.png)

   Sie werden aufgefordert, Ihre PFX-Zertifikatdatei hinzuzufügen.

   ![Screenshot zeigt, wo Die Zertifikatdatei hinzugefügt werden soll.](images/shm-fig6.png)
   
1. Geben Sie Ihr Zertifikatkennwort ein, und wählen Sie **dann OK aus.**

   ![Screenshot zeigt Felder zum Eingeben und Bestätigen Ihres Zertifikatkennworts.](images/shm-fig7.png)

1. Wählen **Sie Kennwortschutz aus,** um dem Surface UEFI ein Kennwort hinzuzufügen. Sie benötigen dieses Kennwort, wenn Sie das UEFI starten. *Es wird dringend empfohlen, dass Sie ein UEFI-Kennwort festlegen, das Sie in Surface Hub 2S verwenden.*

   ![Screenshot zeigt, wo Kennwortschutz ausgewählt werden soll.](images/shm-fig8.png)
   
1. Legen Sie ein UEFI-Kennwort ein, und wählen Sie dann **OK aus.**

   > [!IMPORTANT]
   > Speichern Sie das Kennwort an einem sicheren Ort, auf den Ihre IT-Administratoren, die das Kennwort verwalten, Surface Hub. *Wenn dieses Kennwort verloren geht, kann es nicht wiederhergestellt werden.*

   ![Screenshot zeigt, wo Sie das UEFI-Kennwort festlegen.](images/shm-fig9.png)

1. Wählen **Surface Hub 2S**aus, und wählen Sie dann **Weiter aus.**

    ![Screenshot zeigt, wo sie Surface Hub 2S auswählen.](images/shm-fig10.png)
   
1. Wählen **Sie erneut Weiter** aus.

    ![Screenshot zeigt die Option Weiter unter "Wählen Sie welche Komponenten" aus.](images/shm-fig10a.png)

1. Um die Installation von Windows 10 Pro oder Enterprise zu ermöglichen, aktivieren Sie **EnableOsMigration**, und wählen Sie dann **Weiter aus.**

    ![Screenshot zeigt, wo O S-Migration aktivieren ausgewählt werden soll.](images/shm-fig11.png)
    
    ![Screenshot zeigt, auf wo die Betriebssystemmigration aktivieren festgelegt werden soll.](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>Verwalten der SEMM-Registrierung

Die Registrierung eines Geräts bei SEMM wirkt sich darauf aus, wie Sie es verwalten können. Nachdem Sie beispielsweise ein SEMM-Paket angewendet haben, sind alle UEFI-Einstellungen im UEFI-Menü des Geräts nicht verfügbar (gesperrt). Standardwerte für andere Einstellungen wie **IPv6 für den PXE-Start** sind ebenfalls nicht verfügbar.

Wenn Sie die UEFI-Einstellungen nach Abschluss der Migration ändern möchten, wenden Sie ein anderes SEMM-Paket an, oder entrollen Sie das Gerät von SEMM. Wenn Sie ein anderes SEMM-Paket anwenden, um die UEFI-Einstellungen zu ändern, müssen Sie beim Erstellen des neuen SEMM-Pakets das ursprüngliche Zertifikat verwenden. Verwenden Sie das UEFI Configurator-Tool, ** und lassen **Sie EnableOSMigration** deaktiviert *(nicht* wie in den ursprünglichen Migrationsschritten).

#### <a name="if-you-work-with-partners"></a>Wenn Sie mit Partnern arbeiten

Wenn Ihr Unternehmen die Surface Hub 2-Migration zu Windows 10 Pro oder Enterprise auslagern, möchten Sie möglicherweise, dass der Partner das SEMM-Zertifikat, das SEMM-Paket und das UEFI-Kennwort an Sie übertübert. Nach der Migration des Hubs können Sie es auch sofort von SEMM entfernen. Dieser Schritt ermöglicht die lokale Verwaltung von UEFI und die Übertragung des Geräts an eine andere Partei. Es wird jedoch dringend empfohlen, ein UEFI-Kennwort zu verwenden, das nach der Migration konfiguriert werden kann. Weitere Informationen finden Sie unter [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings). 

#### <a name="to-roll-back-to-windows-10-team"></a>So rollen Sie ein Rollback zu Windows 10 Team

Wenn Sie ihr Gerät nach Windows 10 Team Migration wiederherstellen möchten, wie weiter unten [in](#to-roll-back-to-windows-10-team)diesem Artikel beschrieben, wird empfohlen, die Registrierung des Hubs von SEMM zu entf nenrolln. Weitere Informationen finden Sie unter [Entenroll](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)surface devices from SEMM .

#### <a name="save-the-semm-package-to-a-usb-drive"></a>Speichern des SEMM-Pakets auf einem USB-Laufwerk

1. Verbinden sie ein USB-Laufwerk auf Ihren PC.
1. Wählen **Sie Hub 2S**aus, und wählen Sie dann **Weiter aus.**

   ![Screenshot zeigt, wo Hub 2S ausgewählt werden soll](images/shm-fig13.png)

   > [!WARNING]
   > Alle vorhandenen Daten auf dem USB-Laufwerk werden gelöscht, wenn das SEMM-Paket erstellt wird. Entfernen Sie vor dem Erstellen des SEMM-Pakets alle benötigten Dateien vom USB-Laufwerk.
   
1. Wählen Sie **Erstellen** aus.

   ![Screenshot zeigt, wo Sie Build auswählen.](images/shm-fig14.png)

1. Erfassen Sie einen Screenshot dieser Seite, und wählen Sie dann **End aus.** Ihr SEMM-Paket ist jetzt bereit. Es enthält das SEMM-Paket *DfciUpdate.dfi* und eine ** Textdatei, die den SEMM-Fingerabdruck enthält, der die letzten beiden Zeichen des Fingerabdrucks des Zertifikats ist.

   ![Screenshot zeigt, wo End ausgewählt werden soll.](images/shm-fig15.png)
   
4. Speichern Sie die letzten beiden Zeichen des Zertifikatfingerabdrucks. Sie benötigen diese Zeichen, um SEMM zu aktivieren, wenn Sie das Paket auf Surface Hub 2S anwenden.

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>Laden eines USB-Flashlaufwerks mit Windows 10 Image, SEMM-Paket und Surface Hub 2 Treibern und Firmware

Sie können ein Windows 10 Pro oder Enterprise (Version *1903* oder höher) mithilfe einer der folgenden Optionen installieren:

- Ihre aktuelle Imageerstellungslösung.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator). Verwenden Sie dieses Tool, um ein startbares Windows 10 erstellen. Das Bild kann alle aktuellen Windows 10, Microsoft Office, andere Apps sowie die erforderlichen Treiber und Firmware enthalten.

- Ein USB-Flashlaufwerk, das ein Windows 10 Pro oder Enterprise enthält. Installieren Sie dann [Treiber und Firmware für Windows 10 Pro und Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) auf Surface Hub 2.
 
In den folgenden Schritten wird gezeigt, wie Sie ein USB-Flashlaufwerk von Installationsmedien erstellen und dann die SEMM-Paketdateien sowie die Treiber und Firmware für Windows 10 Pro und Enterprise Os auf Surface Hub 2-MSI-Datei hinzufügen. Wenn Sie eine andere Bereitstellungsmethode verwenden, wechseln Sie zum Abschnitt [Update UEFI on Surface Hub 2S,](#update-uefi-on-surface-hub-2s-to-enable-os-migration) um die Betriebssystemmigration in diesem Artikel zu aktivieren.

> [!NOTE]
> Nachdem Sie die Installation abgeschlossen haben, benötigen Sie eine gültige Lizenz für Windows 10 Pro oder Windows 10 Enterprise, die von Ihrer vorhandenen Windows 10 Team ist.

1. Um eine Windows 10 Pro zu erstellen, befolgen Sie die Anweisungen zum Herunterladen des Medienerstellungstools [unter Download Windows 10](https://www.microsoft.com/software-download/windows10). Um Windows 10 Enterprise herunterzuladen, wechseln Sie zum [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).

1. Fügen Sie ein neues USB-Speicherlaufwerk ein.
1. Öffnen Sie das Medienerstellungstool, wählen **Sie Installationsmedien erstellen**aus, und wählen Sie dann **Weiter aus.**

   ![Screenshot zeigt die Option zum Erstellen von Installationsmedien.](images/shm-fig16.png)
   
3. Wählen Sie eine Sprache aus, und wählen Sie **dann Windows 10** **und 64-Bit (x64) aus.** Wählen Sie dann **Weiter aus.**

   ![Screenshot zeigt, wo Sie die Sprache, die O S-Edition und den Architekturtyp auswählen.](images/shm-fig17.png)
   
4. Wählen **Sie USB-Flashlaufwerk**aus, und wählen Sie dann **Weiter aus.**

   ![Screenshot zeigt, wo Sie das U S B-Flashlaufwerk auswählen.](images/shm-fig18.png)
   
5. Wenn der Download abgeschlossen ist, wählen Sie **Fertig stellen aus.**

   ![Der Bildschirm meldet, dass das Laufwerk U S B bereit ist und eine Schaltfläche Fertig stellen enthält.](images/shm-fig19.png)
   
6. Kopieren Sie die SEMM-Paketdateien sowie die Treiber und Firmware für Windows 10 Pro und Enterprise Os auf Surface Hub 2 (die MSI-Datei) in den Stamm des USB-Flashlaufwerks (*BOOTME*), das Ihr Windows 10-Image enthält. Das BOOTME-USB-Laufwerk enthält:

    - Ihr Windows 10 startbares Image.
    
    - Die in den Stamm des USB-Laufwerks kopierten SEMM-Paketdateien:
    
      - *DfciUpdate.dfi*.
      - Eine Textdatei, die den SEMM-Fingerabdruck enthält. (In diesem Beispiel ist die Datei *SurfaceUEFI_2020Aug25_1058.txt*.) Der automatisch generierte Datums-/Uhrzeitstempel entspricht dem Datum, an dem Sie die Datei mithilfe von Surface UEFI Configurator erstellt haben.

   - Die Treiber und firmware für Windows 10 Pro und Enterprise Betriebssystem auf Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Kopieren Sie diese Datei in den Stamm des USB-Laufwerks.

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>Aktualisieren von UEFI auf Surface Hub 2S zum Aktivieren der Betriebssystemmigration

1. Fügen Sie Ihr BOOTME-Laufwerk in den USB-A-Port Surface Hub 2S ein. Eine Liste der erforderlichen Inhalte finden Sie im vorherigen Abschnitt.

1. So starten Sie UEFI:

   1. Deaktivieren (Herunterfahren) der Surface Hub 2S.
   1. Halten Sie **Volume + gedrückt,** und drücken Sie dann die Netzschaltfläche, und lassen Sie sie los. Halten Sie **Volume + so lange fest,** bis das UEFI-Menü angezeigt wird.
   
      ![Die Zeichnung zeigt die Lautstärke- und Netzschaltflächen an.](images/shm-fig20.png)
      
3. Geben Sie beim Neustart des Geräts das zuvor erstellte UEFI-Kennwort ein (empfohlen).

   ![Systemkennwortbildschirm.](images/shm-fig22.png)
   
4. Wählen Sie im Menü UEFI die Option **Verwaltung aus.** Wählen Sie dann **Installieren aus USB aus.**

   ![Screenshot zeigt, wo Sie Verwaltung und dann "Installieren aus U S B" auswählen.](images/shm-fig21.png)
   
5. Wählen **Sie Jetzt neu starten**aus, wie die folgende Abbildung zeigt. Das Gerät wird neu gestartet. In der Mitte des Fensters wird ein weißes Microsoft-Logo angezeigt und dann heruntergefahren.

   ![Screenshot zeigt eine Meldung, in der Sie zum Neustart aufgefordert werden.](images/shm-fig25.png)
   
6. Drücken und loslassen Sie die Netzschaltfläche. Wählen Sie im angezeigten roten Dialogfeld Surface Enterprise Verwaltungsmodus aus.

7. Geben Sie Ihren zweizeichen-Zertifikatfingerabdruck und Ihr Kennwort für die UEFI-Einstellungen ein. Wählen Sie dann **OK aus.**

   ![Screenshot zeigt das Dialogfeld Bestätigungsaktivierung, in dem Sie Ihren zwei zeichen-Zertifikatfingerabdruck und Ihr Kennwort für die UEFI-Einstellungen eingeben.](images/shm-fig23.png)
 
   > [!NOTE]
   > Nachdem Sie SEMM auf Ihrem Gerät aktiviert haben, wird die neue UEFI-Einstellung **EnableOSMigration** angewendet. Sie können nicht mehr auf Windows 10 Team. Stattdessen müssen Sie mit dem nächsten Schritt fortfahren und Windows 10 Pro oder Windows 10 Enterprise.

   Das Gerät wird neu gestartet. Es zeigt das weiße Logo in der Mitte des Bildschirms an und wird dann erneut heruntergefahren.

### <a name="install-windows-10-pro-or-enterprise"></a>Installieren Windows 10 Pro oder Enterprise

1. Wenn sich Windows 10 Pro oder Enterprise Laufwerk noch nicht im Surface Hub 2-USB-A-Port befindet, fügen Sie es jetzt ein. Drücken Sie dann die Netzschaltfläche, und lassen Sie sie los.

    Wenn das Gerät gestartet wird, wird das weiße Logo in der Mitte des Bildschirms angezeigt. Anschließend wird ein Kreis unter dem weißen Logo angezeigt.

3. Wenn das Surface-Gerät nicht automatisch auf dem USB-Laufwerk gestartet wird, schalten Sie das Gerät aus (trennen Sie das Netzkabel, und schließen Sie es dann wieder an). Nachdem Sie das Netzkabel wieder angeschlossen haben, sollte das Gerät nach einigen Sekunden gestartet werden. Dann wird das weiße Logo in der Mitte des Bildschirms angezeigt.

    Wenn das Gerät nicht einschalten kann, drücken und lassen Sie die Netzschaltfläche los. Drücken Und halten Sie unmittelbar nach dem Anzeigen des Logos in der Mitte des Bildschirms die Taste Volume down gedrückt, bis der Kreis unter dem weißen Logo angezeigt wird.
 
   ![Abbildung der Lautstärke- und Netzschaltflächen.](images/shm-fig26.png)
   
4. Wenn das OOBE(Out-of-Box Experience)-Setup gestartet wird, befolgen Sie die Anweisungen zum Installieren von Windows 10 Pro oder Enterprise (Version 1903 oder höher).

### <a name="install-surface-hub-2-drivers-and-firmware"></a>Installieren Surface Hub 2 Treibern und Firmware

Um sicherzustellen, dass Surface Hub 2 auf dem neuesten Stand ist, installieren Sie Treiber und Firmware für Windows 10 Pro [und Enterprise](https://www.microsoft.com/download/details.aspx?id=101974). Starten Sie das Gerät neu. Halten Sie Surface für eine Stunde eingeschaltet, und starten Sie es erneut neu. Sie werden nicht zum zweiten Neustart aufgefordert. Diese Pause und der zusätzliche Neustart stellen sicher, dass die Firmware vollständig aktualisiert wurde.
 
## <a name="configure-recommended-settings"></a>Konfigurieren empfohlener Einstellungen

Informationen zum Konfigurieren Surface Hub 2S als persönliches Produktivitätsgerät finden Sie unter [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Wenn Sie Ihr Gerät nicht erfolgreich zu Windows 10 Pro oder Enterprise für Surface Hub 2 migrieren können, indem Sie die in diesem Artikel beschriebenen Schritte ausführen, wenden Sie sich an Surface Hub [Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="to-roll-back-to-windows-10-team"></a>So rollen Sie ein Rollback zu Windows 10 Team

Wenn Sie Ihr Gerät auf einem Windows 10 Team wiederherstellen möchten, lesen Sie [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).

> [!NOTE]
> Bevor Sie ein Rollback zu Windows 10 Team, wird empfohlen, zuerst die Registrierung Surface Hub SEMM zu entrollen. Weitere Informationen finden Sie unter [Entenroll](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)surface devices from SEMM .

## <a name="version-history"></a>Versionsverlauf

In der folgenden Tabelle werden die Änderungen an diesem Artikel zusammengefasst.

| Version | Datum               | Beschreibung                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14. Dezember 2020 | Enthält [](#install-surface-hub-2-drivers-and-firmware) weitere Informationen zum Installieren der MSI-Datei für "Treiber und Firmware für Windows 10 Pro und Enterprise Os on Surface Hub 2", und es wird erklärt, dass je nach Systemzustand möglicherweise ein zweiter Neustart erforderlich ist.                                                          |
| v. 1.3  | 3. Dezember 2020 | Mit Anleitungen zum Verwalten [der SEMM-Registrierung aktualisiert.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29. September 2020 | Verschiedene Updates, die Feedback zur Benutzerfreundlichkeit ansprechen.                                                        |
| v. 1.1  | 15. September 2020 | In der Einführung wurde ein zusätzlicher Hinweis platziert, der die Lizenzierungsanforderungen für die Installation eines neuen Betriebssystems erläutert. |
| v. 1.0  | 1. September 2020  | Neuer Artikel.                                                                                           |
