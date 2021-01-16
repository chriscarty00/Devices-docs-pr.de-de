---
title: Surface Enterprise Management Mode (Surface)
description: Erfahren Sie, wie Sie mit diesem Feature von Surface-Geräten mit Surface UEFI Firmwareeinstellungen in Ihrer Organisation sichern und verwalten können.
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
ms.date: 01/15/2021
ms.openlocfilehash: e6f81639253c646f5d3956243a80f4d61c91028a
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271419"
---
# Microsoft Surface Unternehmensverwaltungsmodus

Microsoft Surface Enterprise Management Mode (SEMM) ist ein Feature von Surface-Geräten mit Surface UEFI, mit dem Sie Firmwareeinstellungen innerhalb Ihrer Organisation sichern und verwalten können. Mit SEMM können IT-Experten Konfigurationen von UEFI-Einstellungen vorbereiten und auf einem Surface-Gerät installieren. Neben der Möglichkeit zum Konfigurieren von UEFI-Einstellungen verwendet SEMM auch ein Zertifikat, um die Konfiguration vor unbefugter Manipulation oder Entfernung zu schützen. SEMM ist eine Voraussetzung für die Migration eines Surface Hub 2S zu Windows 10 Pro und Enterprise.

>[!NOTE]
>SEMM ist nur auf Geräten mit Surface -UEFI-Firmware verfügbar. Dies umfasst die meisten anderen Surface-Geräte, einschließlich Surface Pro 7+, Surface Pro X, Surface Hub 2S und Surface Laptop 3 kommerzielle SKUs mit einem Intel-Prozessor und Surface Laptop Go. SEMM wird auf der 15"-Surface Laptop 3-SKU mit AMD-Prozessor nicht unterstützt (nur als SKU für den Einzelhandel verfügbar). 

Wenn Surface-Geräte von SEMM konfiguriert und durch das SEMM-Zertifikat gesichert werden, gelten sie als *bei* SEMM registriert. Wenn das SEMM-Zertifikat entfernt wird und die Steuerung der UEFI-Einstellungen an den Benutzer des Geräts zurückgegeben wird, gilt das Surface-Gerät als nicht *in* SEMM registrierungsbeeinigt.

Es gibt zwei administrative Optionen, die Sie zum Verwalten von SEMM und zum Registrieren von Surface-Geräten verwenden können: ein eigenständiges Tool oder die Integration in Microsoft Endpoint Configuration Manager. Das eigenständige TOOL SEMM, das als Microsoft Surface UEFI Configurator bezeichnet wird, wird in diesem Artikel beschrieben. Weitere Informationen zum Verwalten von SEMM mit Microsoft Endpoint Configuration Manager finden Sie unter Verwenden von Microsoft Endpoint Configuration Manager zum Verwalten von Geräten [mit SEMM.](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)


## Microsoft Surface UEFI Configurator

Der primäre Arbeitsbereich von SEMM ist Microsoft Surface UEFI-Konfigurator, wie in Abbildung 1 dargestellt. Microsoft Surface UEFI Configurator ist ein Tool zum Erstellen von Windows Installer (MSI)-Paketen oder WinPE-Images, die zum Registrieren, Konfigurieren und Entfernen der Registrierung von SEMM auf einem Surface-Gerät verwendet werden. Diese Pakete enthalten eine Konfigurationsdatei, in der die Einstellungen für UEFI angegeben sind. DIESM-Pakete enthalten auch ein Zertifikat, das installiert und in der Firmware gespeichert wird und zum Überprüfen der Signatur von Konfigurationsdateien verwendet wird, bevor die UEFI-Einstellungen angewendet werden.

>[!NOTE]
>Sie können jetzt Surface UEFI Configurator und SEMM verwenden, um Ports auf Surface Dock 2 zu verwalten. Weitere Informationen finden Sie unter [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).

![Microsoft Surface UEFI Configurator](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Abbildung1. Microsoft Surface UEFI Configurator*


Sie können das Tool Microsoft Surface UEFI Configurator in drei Modi verwenden:

* [Surface UEFI Configuration Package](#configuration-package). Verwenden Sie diesen Modus, um ein Surface -UEFI-Konfigurationspaket zu erstellen, um ein Surface-Gerät bei SEMM zu registrieren und um die Einstellungen für UEFI auf registrierten Geräten zu konfigurieren.
* [Surface UEFI Reset Package](#reset-package). Verwenden Sie diesen Modus, um die Registrierung eines Surface-Geräts von SEMM auf zu entsenken.
* [Surface UEFI Recovery Request](#recovery-request). Verwenden Sie diesen Modus, um auf eine Wiederherstellungsanforderung zu reagieren, um die Registrierung eines Surface-Geräts von SEMM aufzusetzen, bei dem ein Vorgang zum Zurücksetzen des Pakets nicht erfolgreich war.


#### Herunterladen Microsoft Surface UEFI Configurator

Sie können den Microsoft Surface UEFI Configurator von der Seite ["Surface Tools für IT"](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.

### Konfigurationspaket

Surface -UEFI-Konfigurationspakete sind der primäre Mechanismus zum Implementieren und Verwalten von SEMM auf Surface-Geräten. Diese Pakete enthalten eine Konfigurationsdatei mit UEFI-Einstellungen, die während der Erstellung des Pakets in Microsoft Surface UEFI Configurator angegeben wurden, sowie eine Zertifikatsdatei, wie in Abbildung 2 dargestellt. Wenn ein Konfigurationspaket zum ersten Mal auf einem Surface-Gerät ausgeführt wird, das noch nicht bei SEMM registriert ist, wird die Zertifikatsdatei in der Firmware des Geräts und das Gerät bei SEMM registriert. Wenn Sie ein Gerät bei SEMM registrieren, werden Sie aufgefordert, den Vorgang zu bestätigen, indem Sie die letzten beiden Ziffern des Fingerabdrucks des SEMM-Zertifikats bereitstellen, bevor die Zertifikatsdatei gespeichert wird und die Registrierung abgeschlossen werden kann. Für diese Bestätigung muss ein Benutzer zum Zeitpunkt der Registrierung physisch auf dem Gerät vorhanden sein, um die Bestätigung durchzuführen.

![Sichern eines SEMM-Konfigurationspakets mit einem Zertifikat](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Abbildung2. Sichern eines SEMM-Konfigurationspakets mit einem Zertifikat*

Weitere Informationen zu den Anforderungen für das Zertifikat des [Surface Enterprise Management Mode](#surface-enterprise-management-mode-certificate-requirements) finden Sie im Abschnitt zu den Zertifikatanforderungen für den Surface Enterprise-Verwaltungsmodus.

>[!NOTE]
>Sie können auch ein UEFI-Kennwort mit SEMM angeben, das zum Anzeigen der Seiten **"Sicherheit",** ****"Geräte", **"Startkonfiguration"** oder **"Unternehmensverwaltung"** von Surface UEFI erforderlich ist.

Nachdem ein Gerät bei SEMM registriert wurde, wird die Konfigurationsdatei gelesen, und die in der Datei angegebenen Einstellungen werden auf UEFI angewendet. Wenn Sie ein Konfigurationspaket auf einem Gerät ausführen, das bereits in SEMM registriert ist, wird die Signatur der Konfigurationsdatei mit dem Zertifikat überprüft, das in der Gerätefirmware gespeichert ist. Wenn die Signatur nicht übereinstimmen, werden keine Änderungen auf das Gerät angewendet.

### Aktivieren oder Deaktivieren von Geräten auf Surface UEFI mit SEMM

In der folgenden Liste sind alle verfügbaren Geräte aufgeführt, die Sie in SEMM verwalten können:

* Docking-USB-Port
* On-Board-Audio
* DGPU
* Type Cover
* Micro-SD-Karte
* Frontkamera
* Rückwärtige Kamera
* Infrarotkamera für Windows Hello
* Nur Bluetooth
* WLAN und Bluetooth
*              LTE           

 >[!NOTE]
>Die integrierten Geräte, die auf der Seite "UEFI-Geräte" angezeigt werden, können je nach Gerät oder Unternehmensumgebung variieren. Beispielsweise wird die Seite "UEFI-Geräte" auf X nicht Surface Pro unterstützt. LTE wird nur auf MIT LTE ausgestatteten Geräten angezeigt. 
### Konfigurieren erweiterter Einstellungen mit SEMM
**Tabelle1. Erweiterte Einstellungen**

| Einstellung                            | Beschreibung                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 für PXE-Start                  | Ermöglicht ihnen die Verwaltung der IPv6-Unterstützung für den PXE-Start. Wenn Sie diese Einstellung nicht konfigurieren, ist die Unterstützung von IPv6 für den PXE-Start deaktiviert.                                                                               |
| Alternativer Start                     | Ermöglicht es Ihnen, die Verwendung einer alternativen Startreihenfolge zu verwalten, um direkt mit einem USB- oder Ethernetgerät zu starten, indem Sie während des Starts sowohl die Taste "Volume Down" als auch die Ein-/Aus-Taste drücken. Wenn Sie diese Einstellung nicht konfigurieren, ist der alternative Start aktiviert. |
| Sperre дер Startreihenfolge                    | Ermöglicht es Ihnen, die Startreihenfolge zu sperren, um Änderungen zu verhindern. Wenn Sie diese Einstellung nicht konfigurieren, ist die Startreihenfolgesperre deaktiviert.                                                                                                        |
| USB-Start                           | Ermöglicht Ihnen das Verwalten des Startes auf USB-Geräten. Wenn Sie diese Einstellung nicht konfigurieren, ist der USB-Start aktiviert.                                                                                                                 |
| Netzwerkstapel                      | Ermöglicht ihnen das Verwalten von Netzwerkstapelstarteinstellungen. Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit zum Verwalten von Netzwerkstapelstarteinstellungen deaktiviert.                                                                                                           |
| Automatisches Ein-/Aus                      | Ermöglicht ihnen die Verwaltung der Einstellungen für den automatischen Ein-/Aus-Start. Wenn Sie diese Einstellung nicht konfigurieren, ist die automatische Aktivierung aktiviert.                                                                                                        |
| Gleichzeitiges Multithreading (Simultaneous Multi-Threading, SMT) | Ermöglicht ihnen die Verwaltung von gleichzeitigen Multithreading (Simultaneous Multi-Threading, SMT), um Hyperthreading zu aktivieren oder zu deaktivieren. Wenn Sie diese Einstellung nicht konfigurieren, ist SMT aktiviert.                                                  |
|Aktivieren des Akkulimits| Ermöglicht es Ihnen, die Funktionalität des Akkulimits zu verwalten. Wenn Sie diese Einstellung nicht konfigurieren, ist der Akkugrenzwert aktiviert. |
| Sicherheit                           | Zeigt die Seite "Surface UEFI **Security"** an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite "Sicherheit" angezeigt.                                                                                                                 |
| Geräte                            | Zeigt die Seite "Surface UEFI **Devices"** an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite "Geräte" angezeigt.                                                                                                                     |
| Start                               | Zeigt die Surface **** -UEFI-Startseite an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Startseite angezeigt.                                                                                                                                                            |
| DateTime                           | Zeigt die Seite **"DateTime"** für Surface UEFI an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite "DateTime" angezeigt.                                                                                                                |
| EnableOSMigration                          | Ermöglicht die Migration von Surface Hub 2 von Windows 10 Team zu Windows 10 Pro oder Enterprise. Wenn Sie diese Einstellung nicht konfigurieren, können Surface Hub 2-Geräte nur Windows 10 Team os ausführen.   Hinweis: Der duale Start zwischen Windows 10 Team und Windows 10 Pro/Enterprise ist auf Surface Hub 2 nicht verfügbar.                                                                                                           |


>[!NOTE]
>Wenn Sie ein SEMM-Konfigurationspaket erstellen, **** werden auf der Seite "Erfolgreich" zwei Zeichen angezeigt, wie in Abbildung 3 dargestellt.

![Anzeige des Zertifikatfingerabdrucks](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Abbildung3. Anzeigen der letzten beiden Zeichen des Zertifikatfingerabdrucks auf der Seite "Erfolgreich"*

Diese Zeichen sind die letzten beiden Zeichen des Zertifikatfingerabdrucks und sollten notiert oder aufgezeichnet werden. Die Zeichen sind erforderlich, um die Registrierung in SEMM auf einem Surface-Gerät zu bestätigen, wie in Abbildung 4 dargestellt.

![Registrierungsbestätigung in SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Abbildung 4. Registrierungsbestätigung in SEMM mit dem Fingerabdruck des SEMM-Zertifikats*

>[!NOTE]
>Administratoren mit Zugriff auf die Zertifikatsdatei (PFX) können den Fingerabdruck jederzeit lesen, indem sie die #A0 in CertMgr öffnen. Gehen Sie wie folgt vor, um den Fingerabdruck mit CertMgr anzeigen zu können:
>1. Klicken Sie mit der rechten Maustaste auf die PFX-Datei, und klicken Sie dann auf **"Öffnen".**
>2. Erweitern Sie den Ordner im Navigationsbereich.
>3. Klicken Sie auf **Zertifikate**.
>4. Klicken Sie im Hauptbereich mit der rechten Maustaste auf Ihr Zertifikat, und klicken Sie dann auf **"Öffnen".**
>5. Klicken Sie auf **die Registerkarte "Details".**
>6. **Im** **Dropdownmenü "Anzeigen"** **** müssen alle oder nur Eigenschaften ausgewählt sein.
>7. Wählen Sie das Feld **Fingerabdruck aus.**

Zum Registrieren eines Surface-Geräts in SEMM oder zum Anwenden der UEFI-Konfiguration aus einem Konfigurationspaket müssen Sie nur die .msi-Datei mit Administratorrechten auf dem vorgesehenen Surface-Gerät ausführen. Sie können Anwendungsbereitstellungs- oder Betriebssystembereitstellungstechnologien wie [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) oder das Microsoft Deployment Toolkit [verwenden.](https://technet.microsoft.com/windows/dn475741) Wenn Sie ein Gerät bei SEMM registrieren, müssen Sie physisch anwesend sein, um die Registrierung auf dem Gerät zu bestätigen. Benutzerinteraktionen sind nicht erforderlich, wenn Sie eine Konfiguration auf Geräte anwenden, die bereits bei SEMM registriert sind.

Eine schrittweise exemplarische Vorgehensweise zum Registrieren eines Surface-Geräts bei SEMM oder zum Anwenden einer Surface -UEFI-Konfiguration mit SEMM finden Sie unter Registrieren und Konfigurieren von Surface-Geräten [mit SEMM.](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)

### Paket zurücksetzen

Ein Surface -UEFI-Zurücksetzungspaket wird verwendet, um nur eine Aufgabe auszuführen – um die Registrierung eines Surface-Geräts von SEMM aufzusetzen. Das Zurücksetzungspaket enthält signierte Anweisungen zum Entfernen des ZERTIFIKATs aus der Firmware des Geräts und zum Zurücksetzen der UEFI-Einstellungen auf die Werkseinstellungen. Wie bei einem Surface -UEFI-Konfigurationspaket muss ein Zurücksetzungspaket mit demselben SEMM-Zertifikat signiert sein, das auf dem Surface Gerät bereitgestellt wird. Wenn Sie ein Paket für die SEMM-Zurücksetzung erstellen, müssen Sie die Seriennummer des Surface-Geräts, das Sie zurücksetzen möchten, verwenden. SEMM-Reset-Pakete sind nicht universell und spezifisch für ein Gerät.

### Wiederherstellungsanforderung

In einigen Szenarien ist es möglicherweise unmöglich, ein Surface UEFI-Reset-Paket zu verwenden. (Beispiel: Wenn Windows auf dem Surface Gerät nicht mehr verwendet werden kann.) In diesen Szenarien können Sie die Registrierung des Surface-Geräts von SEMM über die Seite **"Unternehmensverwaltung"** von Surface UEFI (siehe Abbildung 5) mit einem Wiederherstellungsanforderungsvorgang auffangen.

![Initiieren einer SEMM-Wiederherstellungsanforderung](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Abbildung5. Initiieren einer SEMM-Wiederherstellungsanforderung auf der Seite "Enterprise Management"*

Wenn Sie den Vorgang auf der Seite **"Unternehmensverwaltung"** zum Zurücksetzen von SEMM auf einem Surface-Gerät verwenden, erhalten Sie eine Zurücksetzungsanforderung. Diese Anforderung zum Zurücksetzen kann als Datei auf einem USB-Laufwerk gespeichert, als Text kopiert oder als QR-Code mit einem mobilen Gerät gelesen werden, um einfach per E-Mail oder Nachricht gesendet zu werden. Verwenden Sie die Microsoft Surface UEFI Configurator Reset Request, um eine Anforderungsdatei zum Zurücksetzen zu laden, oder geben Sie den Text "Anforderung zurücksetzen" oder den QR-Code ein. Microsoft Surface UEFI Configurator generiert einen Überprüfungscode, der auf dem Surface Gerät eingegeben werden kann. Wenn Sie den Code auf dem Surface-Gerät eingeben und auf **"Neu**starten" klicken, wird die Registrierung des Geräts von SEMM entfernt. 

>[!NOTE]
>Eine Zurücksetzungsanforderung läuft zwei Stunden nach ihrer Ersetzung ab.

Eine schrittweise exemplarische Vorgehensweise zum Entenrolln von Surface-Geräten von SEMM finden Sie unter ["Unenroll Surface devices from SEMM".](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)

## Zertifikatanforderungen für den Surface Enterprise-Verwaltungsmodus
Die Verwendung von SEMM Microsoft Surface UEFI Configurator erfordert ein Zertifikat, um die Signatur von Konfigurationsdateien zu überprüfen, bevor die UEFI-Einstellungen angewendet werden können. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts bei SEMM nur pakete verwendet werden können, die mit dem genehmigten Zertifikat erstellt wurden, um die Einstellungen von UEFI zu ändern.

>[!NOTE]
>Das SEMM-Zertifikat ist erforderlich, um änderungen an den SEMM- oder Surface -UEFI-Einstellungen auf registrierten Surface-Geräten durchzuführen. Wenn das SEMM-Zertifikat beschädigt ist oder verloren geht, kann SEMM nicht entfernt oder zurückgesetzt werden. Verwalten Sie Ihr SEMM-Zertifikat entsprechend mit einer geeigneten Lösung für Sicherung und Wiederherstellung.

Mit dem Tool Microsoft Surface UEFI Configurator erstellte Pakete werden mit einem Zertifikat signiert. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts bei SEMM nur pakete verwendet werden können, die mit dem genehmigten Zertifikat erstellt wurden, um die Einstellungen von UEFI zu ändern. 
### Empfohlene Zertifikateinstellungen
Die folgenden Einstellungen werden für das SEMM-Zertifikat empfohlen:

* **Schlüsselalgorithmus** – RSA 
* **Schlüssellänge** – 2048
* **Hashalgorithmus** – SHA-256
* **Typ** – SSL-Server-Authentifizierung
* **Schlüsselverwendung** – Digitale Signatur, Schlüsselentschlüsselung
* **Anbieter** – Microsoft Enhanced RSA und AES Cryptographic Provider
* **Ablaufdatum –** 15 Monate nach Erstellung des Zertifikats
* **Schlüsselexportrichtlinie** – exportierbar

Es wird außerdem empfohlen, das ZERTIFIKAT in einer zweistufigen Public Key Infrastructure (PKI)-Architektur zu authentifizieren, bei der die Zwischenzertifizierungsstelle (Intermediate Certification Authority, CA) für SEMM degiert ist, wodurch die Zertifikatsperrung aktiviert wird. Weitere Informationen zu einer zweistufigen PKI-Konfiguration finden Sie im [Test lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).

### Selbst signiertes Zertifikat 
Sie können das folgende Beispiel-PowerShell-Skript verwenden, um ein selbst signiertes Zertifikat für die Verwendung in Proof-of-Concept-Szenarien zu erstellen.
Um dieses Skript zu verwenden, kopieren Sie den folgenden Text in Editor, und speichern Sie die Datei als PowerShell-Skript (PS1). 

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
>Für die Verwendung mit SEMM und Microsoft Surface UEFI Configurator muss das Zertifikat mit dem privaten Schlüssel und mit Kennwortschutz exportiert werden. Microsoft Surface UEFI Configurator fordert Sie auf, bei Bedarf die Zertifikatsdatei (PFX) und das Zertifikatkennwort auszuwählen.

1.  Erstellen Sie einen Ordner auf Ihrem Laufwerk "C:", in dem Sie das Skript speichern. Beispiel: C:\SEMM.
2.  Kopieren Sie das Beispielskript in Editor oder einen entsprechenden Text-Editor, und speichern Sie die Datei als PowerShell-Skript (PS1).
3.  Melden Sie sich mit Administratoranmeldeinformationen bei Ihrem PC an, und öffnen Sie eine PowerShell-Sitzung mit erhöhten Rechten.
4.  Stellen Sie sicher, dass Ihre Berechtigungen so festgelegt sind, dass Skripts ausgeführt werden können. Standardmäßig wird die Ausführung von Skripts blockiert, es sei denn, Sie ändern die Ausführungsrichtlinie. Weitere Informationen finden Sie unter ["Ausführungsrichtlinien".](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)
5.  Geben Sie an der Eingabeaufforderung den vollständigen Pfad des Skripts ein, und drücken Sie dann die EINGABETASTE. Das Skript erstellt ein Demozertifikat mit dem Namen "TempOwner.pfx".

Alternativ können Sie ein eigenes selbst signiertes Zertifikat mit PowerShell erstellen. Weitere Informationen finden Sie in der folgenden PowerShell-Dokumentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).




>[!NOTE]
>Für Organisationen, die einen Offlinestamm in ihrer PKI-Infrastruktur verwenden, muss Microsoft Surface UEFI Configurator in einer Umgebung ausgeführt werden, die mit der Stammzertifizierungsstelle verbunden ist, um das ZERTIFIKAT zu authentifizieren. Die von Microsoft Surface UEFI Configurator generierten Pakete können als Dateien übertragen und daher mit Wechselmedien, z. B. einem USB-Stick, außerhalb der Offlinenetzwerkumgebung übertragen werden.

### Häufig gestellte Fragen zum Verwalten von Zertifikaten

Die empfohlene *Mindestlänge* beträgt 15 Monate. Sie können ein Zertifikat verwenden, das in weniger als 15 Monaten abläuft, oder ein Zertifikat verwenden, das länger als 15 Monate abläuft.

>[!NOTE] 
>Wenn ein Zertifikat abläuft, wird es nicht automatisch verlängert. 


**Wirkt sich ein abgelaufenes Zertifikat auf die Funktionalität von SEMM-registrierten Geräten aus?**<br><br>
Nein, ein Zertifikat wirkt sich nur auf Verwaltungsaufgaben von IT-Administratoren in SEMM aus und hat keine Auswirkungen auf die Gerätefunktionalität, wenn es abläuft.


**Müssen das SEMM-Paket und das Zertifikat auf allen Computern aktualisiert werden, auf der es installiert ist?**

Wenn die Zurücksetzung oder Wiederherstellung von SEMM funktionieren soll, muss das Zertifikat gültig und nicht abgelaufen sein. 

**Können Massenzurücksetzungspakete für jede oberfläche erstellt werden, die wir bestellen? Kann eine erstellt werden, die alle Computer in unserer Umgebung zurück setzt?**

Die PowerShell-Beispiele, die ein Konfigurationspaket für einen bestimmten Gerätetyp erstellen, können auch verwendet werden, um ein Zurücksetzungspaket zu erstellen, das unabhängig von seriennummern ist. Wenn das Zertifikat noch gültig ist, können Sie ein Zurücksetzungspaket mithilfe von PowerShell erstellen, um SEMM zurückzusetzen.

## Versionsverlauf

### Version 2.79.139.0

Diese Version von SEMM umfasst:
- Unterstützung für Surface Pro 7+
- Verbesserungen der Benutzerfreundlichkeit


### Version 2.78.139.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Laptop Go and Surface Pro X
- Benachrichtigungen für neue Version
- Möglichkeit zum Erstellen von benutzerdefinierten Paketen zum Ändern des Besitzes
- Fehlerbehebungen

### Version 2.73.136.0

Diese Version von SEMM umfasst:

- Audio kann jetzt auf Surface Hub2S mithilfe von SEMM deaktiviert werden
- Unterstützung für Surface Pro X für Dock 2
- Unterstützung für UEFI Manager für Vorgänge im Zusammenhang mit Dock 2
- Problembehebt für das Zurücksetzen des Surface Go-Pakets
- Unterstützung für die Migration von Surface Hub 2-Geräten vom Windows 10 Team-Betriebssystem zu Windows 10 Pro oder Enterprise.

### Version 2.71.139.0

Diese Version von SEMM bietet Unterstützung für Surface Dock 2-Verwaltungsfeatures für Surface Book 3, Surface Laptop 3 und Surface Pro 7, einschließlich:

- Aktivieren von Audio (Sperren/Entsperren), Ethernet- und USB-Ports
- Möglichkeit zum Erstellen von Dockpaketen für authentifizierte und nicht authentifizierte Hosts

### Version 2.70.130.0

Diese Version von SEMM umfasst:

- Unterstützung für Surface Go 2
- Unterstützung für Surface Book 3
- Fehlerbehebungen


### Version 2.59.139.0

* Unterstützung für Surface Pro 7-, Surface Pro X- und Surface Laptop 3 13,5" und 15"-Modelle mit Intel-Prozessor. Hinweis: Der Surface Laptop 3 15"-AMD-Prozessor wird nicht unterstützt.

- Unterstützung für Wake on Power

### Version 2.54.139.0
* Unterstützung für Surface Hub 2S
* Fehlerbehebungen

### Version 2.43.136.0
* Unterstützung zum Aktivieren/Deaktivieren simulierter Multithring 
* Separate Optionen für WLAN und Bluetooth für einige Geräte 
* Für Surface Studio wurde der Akkugrenzwert entfernt 

### Version 2.26.136.0
* Hinzufügen von Unterstützung zu Surface Studio 2
* Funktion "Akkugrenzwert"

### Version 2.21.136.0
* Hinzufügen von Unterstützung zu Surface Pro 6
* Hinzufügen von Unterstützung für Surface Laptop 2

### Version 2.14.136.0
* Hinzufügen von Unterstützung für Surface Go

### Version2.9.136.0
* Hinzufügen von Unterstützung für Surface Book 2
* Hinzufügen von Unterstützung für Surface Pro LTE
* Verbesserungen der Barrierefreiheit

### Version 1.0.74.0
* Hinzufügen von Unterstützung für Surface Laptop
* Hinzufügen von Unterstützung für Surface Pro
* Fehlerbehebungen und allgemeine Verbesserung

## Verwandte Themen

- [Registrieren und Konfigurieren von Surface-Geräten mit SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Aufheben der Registrierung von Surface-Geräten bei SEMM](unenroll-surface-devices-from-semm.md)
- [Sichern von Surface Dock 2-Ports mit SEMM](secure-surface-dock-ports-semm.md)
