---
title: Surface Enterprise Management Mode (Surface)
description: Erfahren Sie, wie Dieses Feature von Surface-Geräten mit Surface UEFI Ihnen hilft, Firmwareeinstellungen in Ihrer Organisation zu sichern und zu verwalten.
keywords: uefi, configure, firmware, secure, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 04/16/2021
ms.openlocfilehash: 3c7eea524daa3210a329c41536f4c47a2c012bcf
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576585"
---
# <a name="microsoft-surface-enterprise-management-mode"></a>Microsoft Surface Enterprise-Verwaltungsmodus

Microsoft Surface Enterprise Management Mode (SEMM) ist ein Feature von Surface-Geräten mit Surface Unified Extensible Firmware Interface (UEFI). Sie können SEMM verwenden, um:

- Sichern und Verwalten von Firmwareeinstellungen in Ihrer Organisation.
- Bereiten Sie UEFI-Einstellungen vor, und installieren Sie sie auf einem Surface-Gerät. 

SEMM verwendet auch ein Zertifikat, um die Konfiguration vor unbefugten Manipulationen oder Entfernungen zu schützen. Zum Migrieren eines Surface Hub 2S zu Windows 10 Pro oder Windows Enterprise ist SEMM erforderlich.

>[!NOTE]
>SEMM ist nur auf Geräten mit Surface UEFI-Firmware verfügbar. Dies umfasst die meisten anderen Surface-Geräte, darunter Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 kommerzielle SKUs mit einem Intel-Prozessor, Surface Laptop 4 kommerzielle SKUs mit AMD-Prozessor, Surface Laptop 3 kommerzielle SKUs mit einem Intel-Prozessor und Surface Laptop Go. SEMM wird auf der 15"-Surface Laptop 3-SKU mit AMD-Prozessor (nur als SKU im Einzelhandel verfügbar) nicht unterstützt. 

Wenn Surface-Geräte von SEMM konfiguriert und mit dem SEMM-Zertifikat gesichert werden, gelten sie als *bei* SEMM registriert. Wenn das SEMM-Zertifikat entfernt wird und die Steuerung der UEFI-Einstellungen an den Benutzer des Geräts zurückgegeben wird, wird das Surface-Gerät *in* SEMM als nicht mehr installiert betrachtet.

Es gibt zwei administrative Optionen, die Sie verwenden können, um SEMM zu verwalten und Surface-Geräte zu registrieren:

- Das eigenständige SEMM-Tool, Microsoft Surface UEFI Configurator, wird in diesem Artikel beschrieben. 

- Integration in Microsoft Endpoint Configuration Manager. Weitere Informationen finden Sie unter [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).

> [!NOTE]
> SEMM wird nur für Surface Pro X über den UEFI-Manager unterstützt. Sie können den UEFI Manager von [Surface Tools for IT herunterladen.](https://www.microsoft.com/download/details.aspx?id=46703) Weitere Informationen finden Sie unter [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).


## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI Configurator

Der primäre Arbeitsbereich von SEMM ist Microsoft Surface UEFI Configurator, wie in Abbildung 1 dargestellt. 

Sie können den Microsoft Surface UEFI Configurator verwenden, um:

- Erstellen Windows Installationspaketen (.msi).
- Verwenden Sie WinPE-Images, um SEMM auf einem Surface-Gerät zu registrieren, zu konfigurieren und zu entrollen. 

Diese Pakete enthalten eine Konfigurationsdatei, die die UEFI-Einstellungen angibt. SEMM-Pakete enthalten auch ein Zertifikat, das installiert und in der Firmware gespeichert ist und verwendet wird, um die Signatur von Konfigurationsdateien zu überprüfen, bevor UEFI-Einstellungen angewendet werden.

>[!TIP]
>Sie können jetzt Surface UEFI Configurator und SEMM verwenden, um Ports auf Surface Dock 2 zu verwalten. Weitere Informationen finden Sie unter [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).

![Microsoft Surface UEFI Configurator](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Abbildung1. Microsoft Surface UEFI Configurator*

Sie können das tool Microsoft Surface UEFI Configurator in drei Modi verwenden:

- [Surface UEFI Configuration Package](#configuration-package). Verwenden Sie diesen Modus, um ein Surface UEFI-Konfigurationspaket zu erstellen, um ein Surface-Gerät in SEMM zu registrieren und UEFI-Einstellungen auf registrierten Geräten zu konfigurieren.
- [Surface UEFI Reset Package](#reset-package). Verwenden Sie diesen Modus, um ein Surface-Gerät von SEMM zu entrollen.
- [Surface UEFI-Wiederherstellungsanforderung](#recovery-request). Verwenden Sie diesen Modus, um auf eine Wiederherstellungsanforderung zu reagieren, um ein Surface-Gerät von SEMM zu entrolln, bei dem ein Reset Package-Vorgang nicht erfolgreich war.

#### <a name="download-microsoft-surface-uefi-configurator"></a>Herunterladen Microsoft Surface UEFI Configurator

Sie können Microsoft Surface UEFI Configurator von der [Seite Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.

### <a name="configuration-package"></a>Konfigurationspaket

Surface UEFI-Konfigurationspakete sind der primäre Mechanismus zum Implementieren und Verwalten von SEMM auf Surface-Geräten. Diese Pakete enthalten eine Konfigurationsdatei und eine Zertifikatdatei, wie in Abbildung 2 dargestellt. Die Konfigurationsdatei enthält UEFI-Einstellungen, die angegeben werden, wenn das Paket in Microsoft Surface UEFI Configurator erstellt wird. Wenn ein Konfigurationspaket zum ersten Mal auf einem Surface-Gerät ausgeführt wird, das noch nicht bei SEMM registriert ist, wird die Zertifikatdatei in der Firmware des Geräts gespeichert und das Gerät in SEMM registriert. Beim Registrieren eines Geräts in SEMM und vor dem Speichern des Zertifikats und dem Abschluss der Registrierung werden Sie aufgefordert, den Vorgang zu bestätigen, indem Sie die letzten beiden Ziffern des SEMM-Zertifikatfingerabdrucks bereitstellen. Für diese Bestätigung muss ein Benutzer während der Registrierung physisch auf dem Gerät vorhanden sein, um die Bestätigung durchzuführen.

![Sichern eines SEMM-Konfigurationspakets mit einem Zertifikat](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Abbildung2. Sichern eines SEMM-Konfigurationspakets mit einem Zertifikat*

Weitere Informationen zu den Anforderungen für das SEMM-Zertifikat finden Sie im Abschnitt [Surface Enterprise Management Mode Certificate Requirements](#surface-enterprise-management-mode-certificate-requirements) weiter unten in diesem Artikel.

>[!TIP]
>Sie haben die Möglichkeit, ein UEFI-Kennwort mit SEMM zu benötigen. Wenn Sie dies tun, ist das Kennwort **** erforderlich, um die Seiten **Sicherheit,** **Geräte,** Startkonfiguration und Enterprise **von** Surface UEFI anzeigen zu können.

Nachdem ein Gerät in SEMM registriert wurde, wird die Konfigurationsdatei gelesen, und die in der Datei angegebenen Einstellungen werden auf UEFI angewendet. Wenn Sie ein Konfigurationspaket auf einem Gerät ausführen, das bereits bei SEMM registriert ist, wird die Signatur der Konfigurationsdatei mit dem Zertifikat überprüft, das in der Gerätefirmware gespeichert ist. Wenn die Signatur nicht übereinstimmen, werden keine Änderungen auf das Gerät angewendet.

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>Aktivieren oder Deaktivieren von Geräten in Surface UEFI mit SEMM

Die folgende Liste enthält alle verfügbaren Geräte, die Sie in SEMM verwalten können:

- Docking-USB-Port
- On-Board-Audio
- Digitale Grafikverarbeitungseinheit
- Typabdeckung
- Mikro-SD-Karte
- Kamera vorne
- Rückfahrkamera
- Infrarotkamera (für Windows Hello)
- Bluetooth
- Drahtlosnetzwerk und Bluetooth
- Langfristige Weiterentwicklung (LTE)

 >[!NOTE]
>Auf der Seite UEFI-Geräte können die integrierten Geräte je nach Gerät oder Unternehmensumgebung variieren. Die Seite "UEFI-Geräte" wird beispielsweise auf X nicht Surface Pro unterstützt. LTE wird nur auf LTE-ausgestatteten Geräten angezeigt. 
### <a name="configure-advanced-settings-with-semm"></a>Konfigurieren erweiterter Einstellungen mit SEMM
**Tabelle 1: Erweiterte Einstellungen**

| Einstellung                            | Beschreibung                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 für PXE-Start                  | Ermöglicht ihnen die Verwaltung der IPv6-Unterstützung für den PXE-Start. Wenn Sie diese Einstellung nicht konfigurieren, ist die IPv6-Unterstützung für den PXE-Start deaktiviert.                                                                               |
| Alternativer Start                     | Ermöglicht es Ihnen, die Verwendung einer alternativen Startreihenfolge zu verwalten, um direkt auf ein USB- oder Ethernetgerät zu starten, indem Sie während des Startvorganges sowohl die Volume Down-Taste als auch die Power-Taste drücken. Wenn Sie diese Einstellung nicht konfigurieren, ist der alternative Start aktiviert. |
| Sperre дер Startreihenfolge                    | Ermöglicht es Ihnen, die Startreihenfolge zu sperren, um Änderungen zu verhindern. Wenn Sie diese Einstellung nicht konfigurieren, ist die Startreihenfolgessperre deaktiviert.                                                                                                        |
| USB-Start                           | Ermöglicht ihnen das Verwalten des Startens auf USB-Geräten. Wenn Sie diese Einstellung nicht konfigurieren, ist der USB-Start aktiviert.                                                                                                                 |
| Netzwerkstapel                      | Ermöglicht ihnen das Verwalten von Starteinstellungen für den Netzwerkstapel. Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit zum Verwalten von Netzwerkstapelstarteinstellungen deaktiviert.                                                                                                           |
| Automatisches Ein-/Aus                      | Ermöglicht ihnen die Verwaltung der Einstellungen für den automatischen Ein-/Aus-Start. Wenn Sie diese Einstellung nicht konfigurieren, ist die automatische Aktivierung aktiviert.                                                                                                        |
| Gleichzeitiges Multithreading (Simultaneous Multi-Threading, SMT) | Ermöglicht ihnen das Verwalten von Gleichzeitiger Mehrthreading (Simultaneous Multi-Threading, SMT), um Hyperthreading zu aktivieren oder zu deaktivieren. Wenn Sie diese Einstellung nicht konfigurieren, ist SMT aktiviert.                                                  |
|Aktivieren des Akkulimits| Ermöglicht ihnen die Verwaltung der Funktionalität für den Akkugrenzwert. Wenn Sie diese Einstellung nicht konfigurieren, ist der Akkugrenzwert aktiviert. |
| Sicherheit                           | Zeigt die Seite Surface UEFI **Security** an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite Sicherheit angezeigt.                                                                                                                 |
| Geräte                            | Zeigt die Seite Surface UEFI **Devices** an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite Geräte angezeigt.                                                                                                                     |
| Start                               | Zeigt die Seite Surface **UEFI-Start** an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Startseite angezeigt.                                                                                                                                                            |
| DateTime                           | Zeigt die Seite Surface UEFI **DateTime** an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite DateTime angezeigt.                                                                                                                |
| EnableOSMigration                          | Ermöglicht das Migrieren von Surface Hub 2 von Windows 10 Team zu Windows 10 Pro oder Enterprise. Wenn Sie diese Einstellung nicht konfigurieren, Surface Hub 2 Geräte nur das Betriebssystem Windows 10 Team ausführen. Hinweis: Das duale Starten zwischen Windows 10 Team und Windows 10 Pro/Enterprise ist unter Surface Hub 2 nicht verfügbar.                                                                                                           |


>[!NOTE]
>Wenn Sie ein SEMM-Konfigurationspaket erstellen, werden zwei Zeichen auf der Seite **Erfolgreich** angezeigt, wie in Abbildung 3 dargestellt.

![Anzeige des Zertifikatfingerabdrucks](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Abbildung3. Anzeigen der letzten beiden Zeichen des Zertifikatfingerabdrucks auf der Seite Erfolgreich*

Diese Zeichen sind die letzten beiden Zeichen des Zertifikatfingerabdrucks und sollten notiert oder aufgezeichnet werden. Die Zeichen sind erforderlich, um die Registrierung in SEMM auf einem Surface-Gerät zu bestätigen, wie in Abbildung 4 dargestellt.

![Registrierungsbestätigung in SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Abbildung 4. Registrierungsbestätigung in SEMM mit dem FINGERABDRUCK des SEMM-Zertifikats*

>[!NOTE]
>Administratoren mit Zugriff auf die Zertifikatdatei (PFX) können den Fingerabdruck jederzeit lesen, indem sie die #A0 in CertMgr öffnen. So zeigen Sie den Fingerabdruck mit CertMgr an:
>1. Wählen Sie die PFX-Datei aus, und halten Sie sie fest (oder klicken Sie mit der rechten Maustaste), und wählen Sie **dann Öffnen aus.**
>2. Erweitern Sie im Navigationsbereich den Ordner.
>3. Wählen Sie **Zertifikate aus.**
>4. Wählen Sie im Hauptbereich Ihr Zertifikat aus, halten Sie es (oder klicken Sie mit der rechten Maustaste), und wählen Sie **dann Öffnen aus.**
>5. Wählen Sie die **Registerkarte Details** aus.
>6. Im **Dropdownmenü** Anzeigen müssen **Nur Alle oder** **Eigenschaften** ausgewählt sein.
>7. Wählen Sie das **Feld Fingerabdruck** aus.

Um ein Surface-Gerät in SEMM zu registrieren oder die UEFI-Konfiguration aus einem Konfigurationspaket anzuwenden, führen Sie die .msi-Datei mit Administratorrechten auf dem vorgesehenen Surface-Gerät aus. Sie können Anwendungsbereitstellungs- oder Betriebssystembereitstellungstechnologien wie Microsoft Endpoint Configuration Manager [oder](https://technet.microsoft.com/library/mt346023) [das Microsoft Deployment Toolkit verwenden.](https://technet.microsoft.com/windows/dn475741) Wenn Sie ein Gerät bei SEMM registrieren, müssen Sie physisch vorhanden sein, um die Registrierung auf dem Gerät zu bestätigen. Wenn Sie eine Konfiguration auf Geräte anwenden, die bereits in SEMM registriert sind, ist keine Benutzerinteraktion erforderlich.

Eine schrittweise exemplarische Vorgehensweise zum Registrieren eines Surface-Geräts in SEMM oder anwenden einer Surface UEFI-Konfiguration mit SEMM finden Sie unter Registrieren und Konfigurieren von [Surface-Geräten mit SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).

### <a name="reset-package"></a>Paket zurücksetzen

Ein Surface UEFI-Reset-Paket wird verwendet, um nur eine Aufgabe auszuführen, um ein Surface-Gerät von SEMM zu entrollen. Das Reset-Paket enthält signierte Anweisungen zum Entfernen des SEMM-Zertifikats aus der Firmware des Geräts und zum Zurücksetzen der UEFI-Einstellungen auf die Werkseinstellungen. Wie bei einem Surface UEFI-Konfigurationspaket muss ein Resetpaket mit demselben SEMM-Zertifikat signiert werden, das auf dem Surface-Gerät bereitgestellt wird. Wenn Sie ein SEMM-Reset-Paket erstellen, müssen Sie die Seriennummer des Surface-Geräts, das Sie zurücksetzen möchten, liefern. SEMM-Reset-Pakete sind nicht universell – sie sind spezifisch für ein Gerät.

### <a name="recovery-request"></a>Wiederherstellungsanforderung

In einigen Szenarien ist es möglicherweise nicht möglich, ein Surface UEFI-Reset-Paket zu verwenden. (Wenn z. B. Windows auf dem Surface-Gerät nicht mehr verwendet werden kann.) In diesen Szenarien können Sie die Registrierung des Surface-Geräts von SEMM über die **Enterprise-Verwaltungsseite** von Surface UEFI (siehe Abbildung 5) mit einem Wiederherstellungsanforderungsvorgang entrolln.

> [!div class="mx-imgBorder"]
> ![Initiieren einer SEMM-Wiederherstellungsanforderung](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Abbildung5. Initiieren einer SEMM-Wiederherstellungsanforderung auf Enterprise Verwaltungsseite*

Wenn Sie den Prozess auf der **Enterprise-Verwaltungsseite** verwenden, um SEMM auf einem Surface-Gerät zurückzusetzen, erhalten Sie eine Reset-Anforderung. Diese Reset-Anforderung kann als Datei auf einem USB-Laufwerk gespeichert, als Text kopiert oder als QR-Code mit einem mobilen Gerät gelesen werden, um problemlos per E-Mail oder Nachricht gesendet zu werden. Verwenden Sie Microsoft Surface Option UEFI Configurator Reset Request, um eine Anforderungsdatei zurücksetzen zu laden oder den Text oder QR-Code zurücksetzen ein. Microsoft Surface UEFI Configurator generiert einen Überprüfungscode, der auf dem Surface-Gerät eingegeben werden kann. Wenn Sie den Code auf dem Surface-Gerät eingeben und **Neustart**auswählen, wird das Gerät aus SEMM entrollt. 

>[!NOTE]
>Eine Reset-Anforderung läuft zwei Stunden nach ihrer Ersetzung ab.

Eine schrittweise exemplarische Vorgehensweise zum Entrollen von Surface-Geräten von SEMM finden Sie unter [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Surface Enterprise Management Mode-Zertifikatanforderungen
Wenn Sie SEMM mit Microsoft Surface UEFI Configurator verwenden und UEFI-Einstellungen anwenden möchten, ist ein Zertifikat erforderlich, um die Signatur von Konfigurationsdateien zu überprüfen. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts bei SEMM nur pakete verwendet werden können, die mit dem genehmigten Zertifikat erstellt wurden, um die UEFI-Einstellungen zu ändern.

>[!NOTE]
>Zum Ändern von SEMM- oder Surface -UEFI-Einstellungen auf registrierten Surface-Geräten ist das SEMM-Zertifikat erforderlich. Wenn das SEMM-Zertifikat beschädigt oder verloren geht, kann SEMM nicht entfernt oder zurückgesetzt werden. Verwalten Ihres SEMM-Zertifikats entsprechend mit einer geeigneten Lösung für Sicherung und Wiederherstellung

Pakete, die mit dem Microsoft Surface UEFI Configurator-Tool erstellt wurden, werden mit einem Zertifikat signiert. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts bei SEMM nur pakete verwendet werden können, die mit dem genehmigten Zertifikat erstellt wurden, um die Einstellungen von UEFI zu ändern. 
### <a name="recommended-certificate-settings"></a>Empfohlene Zertifikateinstellungen
Für das SEMM-Zertifikat werden die folgenden Einstellungen empfohlen:

- **Schlüsselalgorithmus** – RSA 
- **Schlüssellänge** – 2048
- **Hashalgorithmus** – SHA-256
- **Typ** – SSL-Serverauthentifizierung
- **Schlüsselverwendung** – Digitale Signatur, Schlüsselentschlüsselung
- **Anbieter** – Microsoft Enhanced RSA and AES Cryptographic Provider
- **Ablaufdatum** – 15 Monate nach der Zertifikaterstellung
- **Wichtige Exportrichtlinie** – Exportierbar

Es wird außerdem empfohlen, das SEMM-Zertifikat in einer zweistufigen Public Key Infrastructure (PKI)-Architektur zu authentifizieren, bei der die Zwischenzertifizierungsstelle (Intermediate Certification Authority, CA) für SEMM zuständig ist, wodurch die Zertifikatsperrung aktiviert wird. Weitere Informationen zu einer zweistufigen PKI-Konfiguration finden Sie unter [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).

### <a name="self-signed-certificate"></a>Selbst signiertes Zertifikat 
Mit dem folgenden PowerShell-Beispielskript können Sie ein selbst signiertes Zertifikat für die Verwendung in Proof-of-Concept-Szenarien erstellen.
Kopieren Sie zum Verwenden dieses Skripts den folgenden Text in Editor, und speichern Sie die Datei dann als PowerShell-Skript (.ps1). 

> [!NOTE]
> Dieses Skript erstellt ein Zertifikat mit dem Kennwort `12345678` . Das von diesem Skript generierte Zertifikat wird für Produktionsumgebungen nicht empfohlen.
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
>Für die Verwendung mit SEMM und Microsoft Surface UEFI Configurator muss das Zertifikat mit dem privaten Schlüssel und mit Kennwortschutz exportiert werden. Microsoft Surface UEFI Configurator fordert Sie auf, die SEMM-Zertifikatdatei (PFX) und das Zertifikatkennwort auszuwählen.

So erstellen Sie ein selbst signiertes Zertifikat:
1.  Erstellen Sie auf dem Laufwerk C: den Ordner, in dem Sie das Skript speichern. Beispiel: C:\SEMM.
2.  Kopieren Sie das Beispielskript in Editor (oder einem entsprechenden Texteditor), und speichern Sie die Datei dann als PowerShell-Skript (.ps1).
3.  Melden Sie sich mit Administratoranmeldeinformationen bei Ihrem Computer an, und öffnen Sie dann eine PowerShell-Sitzung mit erhöhten Rechten.
4.  Stellen Sie sicher, dass Ihre Berechtigungen so festgelegt sind, dass Skripts ausgeführt werden können. Standardmäßig wird die Ausführung von Skripts blockiert, es sei denn, Sie ändern die Ausführungsrichtlinie. Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).
5.  Geben Sie an der Eingabeaufforderung den vollständigen Pfad des Skripts ein, und drücken Sie dann die **EINGABETASTE**. Das Skript erstellt ein Demozertifikat mit dem Namen TempOwner.pfx.

Alternativ können Sie ein eigenes selbst signiertes Zertifikat mit PowerShell erstellen. Weitere Informationen finden Sie unter [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).

>[!NOTE]
>Für Organisationen, die einen Offlinestamm in ihrer PKI-Infrastruktur verwenden, muss Microsoft Surface UEFI Configurator in einer Umgebung ausgeführt werden, die mit der Stammzertifizierungsstelle verbunden ist, um das SEMM-Zertifikat zu authentifizieren. Die von Microsoft Surface UEFI Configurator generierten Pakete können als Dateien übertragen werden, sodass sie mit Wechselspeicher, z. B. einem USB-Stick, außerhalb der Offlinenetzwerkumgebung übertragen werden können.

### <a name="managing-certificates-faq"></a>Verwalten von Zertifikaten häufig gestellte Fragen

Die empfohlene *Mindestlänge* beträgt 15 Monate. Sie können ein Zertifikat verwenden, das in weniger als 15 Monaten abläuft, oder ein Zertifikat verwenden, das in länger als 15 Monaten abläuft.

>[!NOTE] 
>Wenn ein Zertifikat abläuft, wird es nicht automatisch verlängert. 

**Wirkt sich ein abgelaufenes Zertifikat auf die Funktionalität von SEMM-registrierten Geräten aus?**<br><br>
Nein, ein Zertifikat wirkt sich nur auf die Verwaltungsaufgaben von IT-Administratoren in SEMM aus und hat keine Auswirkungen auf die Gerätefunktionalität, wenn es abläuft.

**Müssen das SEMM-Paket und das Zertifikat auf allen Computern aktualisiert werden, auf der es installiert ist?**<br><br>
Wenn das Zurücksetzen oder Die Wiederherstellung von SEMM funktionieren soll, muss das Zertifikat gültig und nicht abgelaufen sein. 

**Können Massenzurücksetzungspakete für jede von uns bestellte Oberfläche erstellt werden? Kann eine erstellt werden, die alle Computer in unserer Umgebung zurück setzt?**<br><br>
Die PowerShell-Beispiele, die ein Konfigurationspaket für einen bestimmten Gerätetyp erstellen, können auch zum Erstellen eines reset-Pakets verwendet werden, das unabhängig von der Seriennummer ist. Wenn das Zertifikat noch gültig ist, können Sie mithilfe von PowerShell ein Resetpaket erstellen, um SEMM zurückzusetzen.

## <a name="version-history"></a>Versionsverlauf


### <a name="version-2831390"></a>Version 2.83.139.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Laptop 4
- Unterstützung für gleichzeitiges Multithreading für Surface Pro 7
- Entfernen veralteter SEMM-Einstellungen  
- Verbesserte MSI-Signatur 

### <a name="version-2791390"></a>Version 2.79.139.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Pro 7+.
- Verbesserungen bei der Benutzerfreundlichkeit.

### <a name="version-2781390"></a>Version 2.78.139.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Laptop Go and Surface Pro X.
- Benachrichtigungen für neue Versionsversionen.
- Die Möglichkeit, benutzerdefinierte Pakete zu erstellen, um den Besitz zu ändern.
- Fehlerbehebungen.

### <a name="version-2731360"></a>Version 2.73.136.0

Diese Version von SEMM umfasst:

- Die Möglichkeit, Audio auf Surface Hub2S mithilfe von SEMM zu deaktivieren.
- Unterstützung für Surface Pro X für Dock 2.
- Unterstützung für UEFI Manager für Dock 2-bezogene Vorgänge.
- Behebung eines Surface Go-Reset-Paketfehlers.
- Unterstützung für die Migration von Surface Hub 2 Geräten von Windows 10 Team betriebssystem zu Windows 10 Pro oder Enterprise.

### <a name="version-2711390"></a>Version 2.71.139.0

Diese Version von SEMM bietet Unterstützung für Surface Dock 2-Verwaltungsfeatures für Surface Book 3, Surface Laptop 3 und Surface Pro 7. Enthält Folgendes:

- Die Möglichkeit, Audio (Sperren/Entsperren) sowie Ethernet- und USB-Ports zu aktivieren.
- Die Möglichkeit, Dockpakete für authentifizierte und nicht authentifizierte Hosts zu erstellen.

### <a name="version-2701300"></a>Version 2.70.130.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Go 2.
- Unterstützung für Surface Book 3.
- Fehlerbehebungen.

### <a name="version-2591390"></a>Version 2.59.139.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Pro 7-, Surface Pro X- und Surface Laptop 3 13,5" und 15"-Modelle mit Intel-Prozessor. 
    >[!NOTE]
    >Surface Laptop 3 15"-AMD-Prozessor wird nicht unterstützt.
- Unterstützung für das Aktivierungs-on-Power-Feature.

### <a name="version-2541390"></a>Version 2.54.139.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Hub 2S.
- Fehlerbehebungen.

### <a name="version-2431360"></a>Version 2.43.136.0

Diese Version von SEMM umfasst:

- Unterstützung zum Aktivieren/Deaktivieren des gleichzeitigen Multithreadings.
- Separate Optionen für drahtlose Netzwerke und Bluetooth für einige Geräte.
- Der Akkugrenzwert wurde für Surface Studio.

### <a name="version-2261360"></a>Version 2.26.136.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Studio 2.
- Funktion "Battery Limit".

### <a name="version-2211360"></a>Version 2.21.136.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Pro 6.
- Unterstützung für Surface Laptop 2.

### <a name="version-2141360"></a>Version 2.14.136.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Go.

### <a name="version-291360"></a>Version2.9.136.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Book 2.
- Unterstützung für Surface Pro LTE.
- Verbesserungen bei der Barrierefreiheit.

### <a name="version-10740"></a>Version 1.0.74.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Laptop.
- Unterstützung für Surface Pro.
- Fehlerbehebungen und allgemeine Verbesserungen.

## <a name="related-topics"></a>Verwandte Themen

- [Registrieren und Konfigurieren von Surface-Geräten mit SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Aufheben der Registrierung von Surface-Geräten bei SEMM](unenroll-surface-devices-from-semm.md)
- [Sichern von Surface Dock 2-Ports mit SEMM](secure-surface-dock-ports-semm.md)
