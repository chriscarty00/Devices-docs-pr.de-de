---
title: Registrieren und Konfigurieren von Surface-Geräten mit Semm (Surface)
description: Erfahren Sie, wie Sie ein Oberflächen UEFI-Konfigurationspaket erstellen, um die Einstellungen von Surface UEFI zu steuern, und ein Surface-Gerät in Semm registrieren.
keywords: Surface Enterprise-Verwaltung
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833481"
---
# Registrieren und Konfigurieren von Surface-Geräten mit SEMM

Mit Microsoft Surface Enterprise Management Mode (Semm) können Sie die Einstellungen von Surface UEFI auf einem Surface-Gerät sicher konfigurieren und diese Einstellungen auf Surface-Geräten in Ihrer Organisation verwalten. Wenn ein Surface-Gerät von Semm verwaltet wird, gilt dieses Gerät als *registriert* (manchmal auch als "aktiviert" bezeichnet). In diesem Artikel wird gezeigt, wie Sie ein Oberflächen UEFI-Konfigurationspaket erstellen, das nicht nur die Einstellungen von Surface UEFI steuert, sondern auch ein Surface-Gerät in Semm registriert.

Eine allgemeinere Übersicht über Semm finden Sie unter [Microsoft Surface Enterprise-Verwaltungsmodus](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Eine optimierte Methode zur Verwaltung der Firmware aus der Cloud auf Surface pro 7, Surface pro X und Surface Laptop 3 ist nun über die öffentliche Vorschau verfügbar. Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).

> [!NOTE]
> SEMM wird auf Surface pro X nur über den UEFI-Manager unterstützt. Weitere Informationen finden Sie unter [bereitstellen, verwalten und warten von Surface pro X](surface-pro-arm-app-management.md).

#### Herunterladen und Installieren des Microsoft Surface UEFI-Konfigurators
Das Tool zum Erstellen von Semm-Paketen ist Microsoft Surface UEFI Configurator. Sie können den Microsoft Surface UEFI Configurator über die Seite [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.
Führen Sie die Microsoft Surface UEFI Configurator-Datei (MSI) aus, um mit der Installation des Tools zu beginnen. Wenn das Installationsprogramm abgeschlossen ist, suchen Sie im Abschnitt alle apps Ihres Start Menüs nach dem Microsoft Surface UEFI Configurator.

>[!NOTE]
>Der Microsoft Surface UEFI-Konfigurator wird nur unter Windows 10 unterstützt.

## Erstellen eines Oberflächen UEFI-Konfigurationspakets

Das Oberflächen UEFI-Konfigurationspaket führt sowohl die Rolle der Anwendung einer neuen Konfiguration von DGM-UEFI-Einstellungen auf ein mit Semm verwaltetes Surface-Gerät als auch die Rolle der Registrierung von Surface-Geräten in Semm aus. Für die Erstellung eines Konfigurationspakets müssen Sie über ein Signaturzertifikat verfügen, das mit Semm verwendet werden muss, um die Konfiguration der UEFI-Einstellungen auf jedem Surface-Gerät zu sichern. Weitere Informationen zu den Anforderungen für das Semm-Zertifikat finden Sie unter [Microsoft Surface Enterprise-Verwaltungsmodus](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Führen Sie die folgenden Schritte aus, um ein Oberflächen UEFI-Konfigurationspaket zu erstellen:

1. Öffnen Sie den Microsoft Surface UEFI-Konfigurator über das Startmenü.
2. Klicken Sie auf **Start**.
3. Klicken Sie auf **Konfigurationspaket**, wie in Abbildung 1 dargestellt.

   ![Erstellen eines Pakets für die Semm-Registrierung](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Abbildung1. Auswählen des Konfigurationspakets zum Erstellen eines Pakets für Semm-Registrierung und-Konfiguration*

4. Klicken Sie auf **Zertifikatschutz** , um die exportierte Zertifikatsdatei mit privatem Schlüssel (. pfx) hinzuzufügen, wie in Abbildung 2 dargestellt. Navigieren Sie zum Speicherort der Zertifikatsdatei, wählen Sie die Datei aus, und klicken Sie dann auf **OK**.

   ![Hinzufügen des SEM-Zertifikats und des Surface UEFI-Kennworts zum Konfigurationspaket](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Abbildung2. Hinzufügen des Semm-Zertifikats und des Surface UEFI-Kennworts zu einem Oberflächen UEFI-Konfigurationspaket*

5. Wenn Sie aufgefordert werden, das Zertifikat Kennwort zu bestätigen, geben Sie das Kennwort für Ihre Zertifikatsdatei ein, bestätigen Sie es, und klicken Sie dann auf **OK**.
6. Klicken Sie auf **Kennwortschutz** , um der Oberfläche UEFI ein Kennwort hinzuzufügen. Dieses Kennwort ist erforderlich, wenn Sie mit UEFI Booten. Wenn dieses Kennwort nicht eingegeben wird, werden nur die Seiten " **PC-Informationen**", " **Informationen zu**", " **Unternehmensverwaltung**" und " **Beenden** " angezeigt. Dieser Schritt ist optional.
7. Wenn Sie dazu aufgefordert werden, geben Sie das ausgewählte Kennwort für das Surface UEFI ein, bestätigen Sie es, und klicken Sie dann auf **OK**. Wenn Sie ein vorhandenes UEFI-Kennwort löschen möchten, lassen Sie das Kennwortfeld leer.
8. Wenn Sie nicht möchten, dass das DGM-UEFI-Paket auf ein bestimmtes Gerät angewendet wird, klicken Sie auf der Seite Wählen Sie den DGM-Typ aus, die **Sie ausrichten möchten** auf den Schieberegler unter dem entsprechenden DGM-Buch oder Surface pro 4-Bild, sodass es sich in der Position **aus** befindet. (Siehe Abbildung 3.)
   > [!NOTE] 
   > Sie müssen ein Gerät auswählen, da keine standardmäßig ausgewählt ist.

   ![Auswählen von Geräten für die Paket Kompatibilität](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Abbildung3. Auswählen der Geräte für die Paket Kompatibilität*

9. Klicken Sie auf **Weiter**.
10. Wenn Sie eine Komponente auf verwalteten Oberflächen Geräten deaktivieren möchten, klicken Sie auf der Seite Wählen Sie die Komponenten aus, die **Sie aktivieren oder** deaktivieren möchten auf den Schieberegler neben einem Gerät oder einer Gruppe von Geräten, die Sie deaktivieren möchten, damit sich der Schieberegler in der Position **aus** befindet. (Siehe Abbildung 4.) Die Standardkonfiguration für jedes Gerät ist **aktiviert**. Klicken Sie auf die Schaltfläche **Zurücksetzen** , wenn Sie alle Schieberegler an die Standardposition zurückgeben möchten.

    ![Deaktivieren oder Aktivieren von DGM-Komponenten](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Abbildung 4. Deaktivieren oder Aktivieren einzelner DGM-Komponenten*

11. Klicken Sie auf **Weiter**.
12. Klicken Sie auf der Seite **"Erweiterte Einstellungen für Ihre Geräte auswählen** " auf den Schieberegler neben der gewünschten Einstellung, um die Optionen für "Surface UEFI" oder die Anzeige von Oberflächen UEFI- **Seiten zu aktivieren** oder **zu deaktivieren (siehe** Abbildung 5). Im Abschnitt **UEFI-Vorderseite** können Sie die Schieberegler für **Sicherheit**, **Geräte**und **Start** verwenden, um zu steuern, welche Seiten Benutzern zur Verfügung stehen, die in die Oberfläche von UEFI Booten. (Weitere Informationen zu den UEFI-Oberflächeneinstellungen finden Sie unter [Verwalten von Oberflächen UEFI-Einstellungen](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Klicken Sie auf **Erstellen** , wenn Sie alle Optionen zum Generieren und Speichern des Pakets ausgewählt haben.

    ![Steuern erweiterter Oberflächen-UEFI-Einstellungen und UEFI-DGM-Seiten](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Abbildung5. Steuern erweiterter DGM-UEFI-Einstellungen und UEFI-DGM-Seiten mit Semm*

13. Geben Sie im Dialogfeld **Speichern** unter einen Namen für das Oberflächen UEFI-Konfigurationspaket an, navigieren Sie zu dem Speicherort, an dem Sie die Datei speichern möchten, und klicken Sie dann auf **Speichern**.
14. Wenn das Paket erstellt und gespeichert wird, wird die Seite **erfolgreich** angezeigt.

>[!NOTE]
>Zeichnen Sie die auf dieser Seite angezeigten Fingerabdruck Zeichen auf, wie in Abbildung 6 dargestellt. Sie benötigen diese Zeichen, um die Registrierung von neuen Surface-Geräten in Semm zu bestätigen. Klicken Sie auf **Beenden** , um die Paketerstellung abzuschließen, und schließen Sie den Microsoft Surface UEFI-Konfigurator.

![Anzeige der Fingerabdruck Zeichen des Zertifikats](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*Abbildung6. Die letzten beiden Zeichen des Fingerabdrucks des Zertifikats werden auf der Seite "erfolgreich" angezeigt.*

Nachdem Sie das Oberflächen UEFI-Konfigurationspaket erstellt haben, können Sie Surface-Geräte registrieren oder konfigurieren.

>[!NOTE]
>Wenn ein Oberflächen UEFI-Konfigurationspaket erstellt wird, wird auf dem Desktop eine Protokolldatei mit Details zu den Einstellungen und Optionen des Konfigurationspakets erstellt.

## Registrieren eines Surface-Geräts in Semm
Beim Ausführen des Oberflächen UEFI-Konfigurationspakets werden die Konfigurationsdateien Semm Certificate und Surface UEFI im Firmwarespeicher des Surface-Geräts bereitgestellt. Wenn das Surface-Gerät neu gestartet wird, verarbeitet Surface UEFI diese Dateien und beginnt den Prozess der Anwendung der Oberflächen UEFI-Konfiguration oder der Registrierung des Surface-Geräts in Semm, wie in Abbildung 7 dargestellt.

![SEMM-Prozess für die Konfiguration von DGM-UEFI oder-Registrierung](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Abbildung7. Der Semm-Prozess für die Konfiguration von Surface UEFI oder die Registrierung eines Surface-Geräts*

Bevor Sie mit dem Verfahren zum Registrieren eines Surface-Geräts in Semm beginnen, stellen Sie sicher, dass Sie die letzten beiden Zeichen des Zertifikat Fingerabdrucks zur Hand haben. Sie benötigen diese Zeichen, um die Registrierung des Geräts zu bestätigen (siehe Abbildung 6).

Führen Sie die folgenden Schritte aus, um ein Surface-Gerät in Semm mit einem Surface UEFI-Konfigurationspaket zu registrieren:

1. Führen Sie die MSI-Datei des Surface UEFI-Konfigurationspakets auf dem Surface-Gerät aus, das Sie in Semm registrieren möchten. Dadurch wird die Oberflächen UEFI-Konfigurationsdatei in der Firmware des Geräts bereitgestellt.
2. Aktivieren Sie das Kontrollkästchen **Ich akzeptiere die Bedingungen im Lizenzvertrag** , um den Endbenutzer-Lizenzvertrag (EULA) zu akzeptieren, und klicken Sie dann auf **Installieren** , um den Installationsvorgang zu starten.
3. Klicken Sie auf **Fertig stellen** , um die Installation des Oberflächen UEFI-Konfigurationspakets abzuschließen, und starten Sie das Surface-Gerät neu, wenn Sie dazu aufgefordert werden.
4. Mit dem UEFI-DGM wird die Konfigurationsdatei geladen, und es wird festgestellt, dass Semm auf dem Gerät nicht aktiviert ist. Surface UEFI beginnt den Semm-Registrierungsprozess wie folgt:
   * Der Oberflächen UEFI überprüft, ob die Semm-Konfigurationsdatei ein Semm-Zertifikat enthält.
   * Mit der Oberfläche UEFI werden Sie aufgefordert, die letzten beiden Zeichen des Zertifikat Fingerabdrucks einzugeben, um die Registrierung des Surface-Geräts in Semm zu bestätigen, wie in Abbildung 8 zu sehen ist.

      ![SEMM-Registrierung erfordert die letzten beiden Zeichen des Zertifikat Fingerabdrucks](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Abbildung8. Für die Registrierung in Semm sind die letzten beiden Zeichen des Zertifikat Fingerabdrucks erforderlich.*

   * Oberflächen UEFI speichert das Semm-Zertifikat in der Firmware und wendet die Konfigurationseinstellungen an, die in der Oberflächen UEFI-Konfigurationsdatei angegeben sind.
   
5. Das Surface-Gerät ist jetzt in Semm registriert und startet Windows.

Sie können überprüfen, ob ein Surface-Gerät erfolgreich in Semm registriert wurde, indem Sie in den **Programmen und Funktionen** (wie in Abbildung 9 gezeigt) nach dem **Microsoft Surface-Konfigurationspaket** suchen, oder in den Ereignissen, die im **Microsoft Surface UEFI-Konfigurations** Protokoll gespeichert sind, das unter **Anwendungen und Dienstprotokolle** in der Ereignisanzeige (siehe Abbildung 10) zu finden ist.

![Überprüfen der Registrierung des Surface-Geräts in Semm in "Programme und Features"](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*Abbildung9. Überprüfen der Registrierung eines Surface-Geräts in Semm in "Programme und Features"*

![Überprüfen der Registrierung des Surface-Geräts in Semm in der Ereignisanzeige](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*Abbildung10. Überprüfen der Registrierung eines Surface-Geräts in Semm in der Ereignisanzeige*

Sie können auch überprüfen, ob das Gerät in Semm in Surface UEFI registriert ist – während das Gerät registriert ist, enthält Surface UEFI die **Enterprise-Verwaltungs** Seite (siehe Abbildung 11).

![Seite "Surface UEFI Enterprise-Verwaltung"](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*Abbildung11. Die Seite "Surface UEFI Enterprise-Verwaltung"*


## Konfigurieren von Oberflächen UEFI-Einstellungen mit Semm

Nachdem ein Gerät in Semm registriert wurde, können Sie mit demselben Semm-Zertifikat signierte Oberflächen UEFI-Konfigurationspakete ausführen, um neue UEFI-Oberflächeneinstellungen anzuwenden. Diese Einstellungen werden beim nächsten Booten des Geräts automatisch angewendet, ohne dass eine Interaktion des Benutzers erfolgt. Mit Anwendungs Bereitstellungslösungen wie Microsoft Endpoint Configuration Manager können Sie Oberflächen UEFI-Konfigurationspakete auf Surface-Geräten bereitstellen, um die Einstellungen in Surface UEFI zu ändern oder zu verwalten.

Weitere Informationen zum Bereitstellen von Windows Installer-Dateien (MSI) mit Configuration Manager finden Sie unter [bereitstellen und Verwalten von Anwendungen mit Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).

Wenn Sie das Surface-UEFI mit einem Kennwort gesichert haben, werden Benutzern ohne das Kennwort, das versuchen soll, auf den Surface-UEFI zu booten, nur die **PC-Informationen** **, Informationen zu** **Enterprise Management**und **Exit** -Seiten angezeigt.

Wenn Sie die Oberfläche UEFI nicht mit einem Kennwort gesichert haben oder ein Benutzer das Kennwort richtig eingibt, werden die mit Semm konfigurierten Einstellungen abgeblendet (nicht verfügbar), und der Text, den einige Einstellungen von Ihrer Organisation verwaltet werden, wird oben auf der Seite angezeigt, wie in Abbildung 12 dargestellt.

![Einstellungen, die von Semm verwaltet werden, sind in Surface UEFI deaktiviert](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*Abbildung 12 Einstellungen, die von Semm verwaltet werden, werden in Surface UEFI deaktiviert*
