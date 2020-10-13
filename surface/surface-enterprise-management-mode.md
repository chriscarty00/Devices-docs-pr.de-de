---
title: Surface Enterprise-Verwaltungsmodus (Surface)
description: Sehen Sie sich an, wie diese Funktion von Surface Devices mit Surface UEFI Ihnen dabei hilft, die Firmwareeinstellungen in Ihrer Organisation zu sichern und zu verwalten.
keywords: UEFI, konfigurieren, Firmware, sicher, Semm
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
ms.date: 10/12/2020
ms.openlocfilehash: 463759d2dd01b9333d10a66c1781055f4a5217ac
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114643"
---
# Microsoft Surface Enterprise-Verwaltungsmodus

Der Microsoft Surface Enterprise Management Mode (Semm) ist eine Funktion von Surface Devices mit Surface UEFI, mit der Sie die Firmwareeinstellungen innerhalb Ihrer Organisation sichern und verwalten können. Mit Semm können IT-Experten Konfigurationen von UEFI-Einstellungen vorbereiten und auf einem Surface-Gerät installieren. Neben der Möglichkeit zum Konfigurieren von UEFI-Einstellungen verwendet Semm auch ein Zertifikat, um die Konfiguration vor unbefugten Manipulationen oder Entfernungen zu schützen. SEMM ist eine Voraussetzung, um einen Surface Hub 2S auf Windows 10 pro und Enterprise migrieren zu können.

>[!NOTE]
>SEMM ist nur auf Geräten mit Surface UEFI-Firmware verfügbar. Dies umfasst die meisten anderen Surface-Geräte einschließlich Surface pro 7, Surface pro X, Surface Hub 2S und Surface Laptop 3 Commercial SKUs mit einem Intel-Prozessor und Surface Laptop go. SEMM wird auf der 15 "Surface Laptop 3-SKU mit AMD-Prozessor (nur als Einzelhandels-SKU verfügbar) nicht unterstützt. 

Wenn Surface-Geräte von Semm konfiguriert und mit dem Semm-Zertifikat gesichert werden, gelten Sie als in Semm *registriert* . Wenn das Semm-Zertifikat entfernt und die Steuerung der UEFI-Einstellungen an den Benutzer des Geräts zurückgegeben wird, gilt das Surface-Gerät als "nicht *registriert* " in Semm.

Es gibt zwei administrative Optionen, die Sie zum Verwalten von Semm und Registrieren von Surface-Geräten verwenden können – ein eigenständiges Tool oder eine Integration in den Microsoft Endpoint Configuration Manager. Das eigenständige Tool "Semm", das so genannte Microsoft Surface UEFI Configurator, wird in diesem Artikel beschrieben. Weitere Informationen zum Verwalten von Semm mit Microsoft Endpoint Configuration Manager finden Sie unter [Verwenden von Microsoft Endpoint Configuration Manager zum Verwalten von Geräten mit Semm](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).


## Microsoft Surface UEFI-Konfigurator

Der primäre Arbeitsbereich von Semm ist Microsoft Surface UEFI Configurator, wie in Abbildung 1 dargestellt. Microsoft Surface UEFI Configurator ist ein Tool, mit dem Windows Installer-Pakete (MSI) oder WinPE-Bilder zum Registrieren, konfigurieren und Auflegen der Registrierung von Semm auf einem Surface-Gerät erstellt werden. Diese Pakete enthalten eine Konfigurationsdatei, in der die Einstellungen für UEFI angegeben sind. SEMM-Pakete enthalten auch ein Zertifikat, das in der Firmware installiert und gespeichert wird und verwendet wird, um die Signatur von Konfigurationsdateien zu überprüfen, bevor UEFI-Einstellungen angewendet werden.

>[!NOTE]
>Sie können jetzt den Surface UEFI Configurator und Semm verwenden, um Ports auf Surface Dock 2 zu verwalten. Weitere Informationen finden Sie unter [Secure Surface Dock 2-Anschlüsse mit Semm](secure-surface-dock-ports-semm.md).

![Microsoft Surface UEFI-Konfigurator](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Abbildung1. Microsoft Surface UEFI-Konfigurator*


Sie können das Tool Microsoft Surface UEFI Configurator in drei Modi verwenden:

* [Oberflächen-UEFI-Konfigurationspaket](#configuration-package). Verwenden Sie diesen Modus zum Erstellen eines Oberflächen UEFI-Konfigurationspakets zum Registrieren eines Surface-Geräts in Semm und zum Konfigurieren von UEFI-Einstellungen auf registrierten Geräten.
* [Oberflächen-UEFI-Reset-Paket](#reset-package). Verwenden Sie diesen Modus, um die Registrierung eines Surface-Geräts von Semm aufzuheben.
* [Oberflächen-UEFI-Wiederherstellungsanforderung](#recovery-request) Verwenden Sie diesen Modus, um auf eine Wiederherstellungsanforderung zu reagieren, um die Registrierung eines Surface-Geräts von Semm aufzuheben, bei dem ein Reset-Paketvorgang nicht erfolgreich ist.


#### Microsoft Surface UEFI-Konfigurator herunterladen

Sie können den Microsoft Surface UEFI Configurator über die Seite [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.

### Konfigurationspaket

Oberflächen UEFI-Konfigurationspakete sind der primäre Mechanismus zum Implementieren und Verwalten von Semm auf Surface-Geräten. Diese Pakete enthalten eine Konfigurationsdatei mit UEFI-Einstellungen, die während der Erstellung des Pakets in Microsoft Surface UEFI Configurator und einer Zertifikatsdatei angegeben wurden, wie in Abbildung 2 zu sehen ist. Wenn ein Konfigurationspaket zum ersten Mal auf einem Surface-Gerät ausgeführt wird, das noch nicht in Semm registriert ist, stellt es die Zertifikatdatei in der Firmware des Geräts bereit und registriert das Gerät in Semm. Wenn Sie ein Gerät in Semm registrieren, werden Sie aufgefordert, den Vorgang zu bestätigen, indem Sie die letzten beiden Ziffern des Semm-Zertifikat Fingerabdrucks angeben, bevor die Zertifikatdatei gespeichert und die Registrierung abgeschlossen werden kann. Diese Bestätigung setzt voraus, dass ein Benutzer zum Zeitpunkt der Registrierung physisch auf dem Gerät anwesend ist, um die Bestätigung durchzuführen.

![Sichern eines Semm-Konfigurationspakets mit einem Zertifikat](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Abbildung2. Sichern eines Semm-Konfigurationspakets mit einem Zertifikat*

Weitere Informationen zu den Anforderungen für das Semm-Zertifikat finden Sie in diesem Artikel im Abschnitt für die [Zertifikatanforderungen für Surface Enterprise-Verwaltungsmodus](#surface-enterprise-management-mode-certificate-requirements) .

>[!NOTE]
>Sie können auch ein UEFI-Kennwort mit Semm angeben, das erforderlich ist, um die Seiten **Security**, **Devices**, **Boot Configuration**oder **Enterprise Management** von Surface UEFI anzuzeigen.

Nachdem ein Gerät in Semm registriert wurde, wird die Konfigurationsdatei gelesen, und die in der Datei angegebenen Einstellungen werden auf UEFI angewendet. Wenn Sie ein Konfigurationspaket auf einem Gerät ausführen, das bereits in Semm registriert ist, wird die Signatur der Konfigurationsdatei mit dem Zertifikat überprüft, das in der Geräte-Firmware gespeichert ist. Wenn die Signatur nicht übereinstimmt, werden keine Änderungen auf das Gerät angewendet.

### Aktivieren oder Deaktivieren von Geräten in Surface UEFI mit Semm

In der folgenden Liste sind alle verfügbaren Geräte aufgeführt, die Sie in Semm verwalten können:

* Docking-USB-Anschluss
* On-Board-Audio
* DGPU
* Type Cover
* Micro SD-Karte
* Frontkamera
* Rückwärtige Kamera
* Infrarotkamera für Windows Hello
* Nur Bluetooth
* WLAN und Bluetooth
*              LTE           

 >[!NOTE]
>Die integrierten Geräte, die auf der Seite UEFI-Geräte angezeigt werden, können je nach Gerät oder Unternehmensumgebung unterschiedlich sein. Beispielsweise wird die Seite UEFI-Geräte auf Surface pro X nicht unterstützt. LTE wird nur auf LTE-Geräten angezeigt. 
### Konfigurieren von erweiterten Einstellungen mit Semm
**Tabelle1. Erweiterte Einstellungen**

| Einstellung                            | Beschreibung                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 für PXE-Start                  | Ermöglicht Ihnen die Verwaltung der IPv6-Unterstützung für den PXE-Start. Wenn Sie diese Einstellung nicht konfigurieren, ist die IPv6-Unterstützung für den PXE-Start deaktiviert.                                                                               |
| Alternativer Start                     | Ermöglicht es Ihnen, die Verwendung einer alternativen Startreihenfolge zu verwalten, um direkt mit einem USB-oder Ethernet-Gerät zu booten, indem Sie beim Booten sowohl die Lautstärketaste als auch die Power-Taste drücken. Wenn Sie diese Einstellung nicht konfigurieren, ist alternativer Start aktiviert. |
| Sperre дер Startreihenfolge                    | Ermöglicht es Ihnen, die Startreihenfolge zu sperren, um Änderungen zu verhindern. Wenn Sie diese Einstellung nicht konfigurieren, ist die Startreihenfolge gesperrt.                                                                                                        |
| USB-Start                           | Ermöglicht es Ihnen, das Booten auf USB-Geräten zu verwalten. Wenn Sie diese Einstellung nicht konfigurieren, ist der USB-Start aktiviert.                                                                                                                 |
| Netzwerkstapel                      | Ermöglicht das Verwalten von Netzwerkstapel-Start Einstellungen. Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit zum Verwalten von Netzwerkstapel-Start Einstellungen deaktiviert.                                                                                                           |
| Automatisches Einschalten                      | Ermöglicht es Ihnen, die Einstellungen für das automatische Einschalten von Booten zu verwalten. Wenn Sie diese Einstellung nicht konfigurieren, ist die automatische Stromversorgung aktiviert.                                                                                                        |
| Simultanes Multi-Threading (SMT) | Ermöglicht das Verwalten von simultanem Multi-Threading (SMT) zum Aktivieren oder Deaktivieren von Hyperthreading. Wenn Sie diese Einstellung nicht konfigurieren, ist SMT aktiviert.                                                  |
|Aktivieren der Batterie Grenze| Ermöglicht es Ihnen, die Funktion der Batterie Grenze zu verwalten. Wenn Sie diese Einstellung nicht konfigurieren, ist die Batterie Grenze aktiviert. |
| Sicherheit                           | Zeigt die Seite "DGM-UEFI- **Sicherheit** " an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite Sicherheit angezeigt.                                                                                                                 |
| Geräte                            | Zeigt die Seite "Surface UEFI **Devices** " an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite Geräte angezeigt.                                                                                                                     |
| Start                               | Zeigt die Oberfläche UEFI- **Start** Seite an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Startseite angezeigt.                                                                                                                                                            |
| DateTime                           | Zeigt die Seite "DGM-UEFI- **DateTime** " an. Wenn Sie diese Einstellung nicht konfigurieren, wird die Seite DateTime angezeigt.                                                                                                                |
| EnableOSMigration                          | Ermöglicht die Migration von Surface Hub 2 vom Windows 10-Team zu Windows 10 pro oder Enterprise. Wenn Sie diese Einstellung nicht konfigurieren, können Surface Hub 2-Geräte nur Windows 10 Team OS ausführen.   Hinweis: das duale Booten zwischen Windows 10 Team und Windows 10 pro/Enterprise ist auf Surface Hub 2 nicht verfügbar.                                                                                                           |


>[!NOTE]
>Wenn Sie ein Semm-Konfigurationspaket erstellen, werden auf der **erfolgreichen** Seite zwei Zeichen angezeigt, wie in Abbildung 3 zu sehen ist.

![Anzeige des Fingerabdrucks des Zertifikats](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Abbildung3. Anzeige der letzten beiden Zeichen des Zertifikat Fingerabdrucks auf der Seite "erfolgreich"*

Diese Zeichen sind die letzten beiden Zeichen des Zertifikat Fingerabdrucks und sollten geschrieben oder aufgezeichnet werden. Die Zeichen sind erforderlich, um die Registrierung in Semm auf einem Surface-Gerät zu bestätigen, wie in Abbildung 4 zu sehen ist.

![Registrierungsbestätigung in Semm](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Abbildung 4. Registrierungsbestätigung in Semm mit dem Fingerabdruck des Semm-Zertifikats*

>[!NOTE]
>Administratoren mit Zugriff auf die Zertifikatsdatei (. pfx) können den Fingerabdruck jederzeit lesen, indem Sie die PFX-Datei in certmgr öffnen. Gehen Sie folgendermaßen vor, um den Fingerabdruck mit certmgr anzuzeigen:
>1. Klicken Sie mit der rechten Maustaste auf die PFX-Datei, und klicken Sie dann auf **Öffnen**.
>2. Erweitern Sie den Ordner im Navigationsbereich.
>3. Klicken Sie auf **Zertifikate**.
>4. Klicken Sie im Hauptfenster mit der rechten Maustaste auf das Zertifikat, und klicken Sie dann auf **Öffnen**.
>5. Klicken Sie auf die Registerkarte **Details** .
>6. Im Dropdownmenü **anzeigen** muss nur **alle** oder **nur Eigenschaften** ausgewählt sein.
>7. Wählen Sie das Feld **Daumenabdruck**aus.

Zum Registrieren eines Surface-Geräts in Semm oder zum Anwenden der UEFI-Konfiguration aus einem Konfigurationspaket müssen Sie lediglich die MSI-Datei mit Administratorrechten auf dem vorgesehenen Surface-Gerät ausführen. Sie können Anwendungs Bereitstellungstechnologien oder Bereitstellungstechnologien für Betriebssysteme wie [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) oder das [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741)verwenden. Wenn Sie ein Gerät in Semm registrieren, müssen Sie physisch anwesend sein, um die Registrierung auf dem Gerät bestätigen zu können. Benutzerinteraktionen sind nicht erforderlich, wenn Sie eine Konfiguration auf Geräte anwenden, die bereits in Semm registriert sind.

Eine Schritt-für-Schritt-Anleitung zum Registrieren eines Surface-Geräts in Semm oder zum Anwenden einer Oberflächen UEFI-Konfiguration mit Semm finden Sie unter [registrieren und Konfigurieren von Surface-Geräten mit Semm](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).

### Paket zurücksetzen

Ein Oberflächen UEFI-Zurücksetzungs Paket wird verwendet, um nur eine Aufgabe auszuführen, um die Registrierung eines Surface-Geräts von Semm aufzuheben. Das Paket "Zurücksetzen" enthält signierte Anweisungen, um das Semm-Zertifikat aus der Firmware des Geräts zu entfernen und die UEFI-Einstellungen auf den Werksstandard zurückzusetzen. Wie bei einem Oberflächen UEFI-Konfigurationspaket muss ein Reset-Paket mit dem gleichen Semm-Zertifikat signiert sein, das auf dem Surface-Gerät bereitgestellt wird. Wenn Sie ein Semm-Zurücksetzungs Paket erstellen, müssen Sie die Seriennummer des Surface-Geräts angeben, das Sie zurücksetzen möchten. SEMM-Reset-Pakete sind nicht universell und für ein Gerät spezifisch.

### Wiederherstellungsanforderung

In einigen Szenarien ist es möglicherweise nicht möglich, ein UEFI-Reset-Paket zu verwenden. (Wenn beispielsweise Windows auf dem Surface-Gerät unbrauchbar wird.) In diesen Szenarien können Sie die Registrierung des Surface-Geräts von Semm über die **Enterprise-Verwaltungs** Seite des Surface UEFI (siehe Abbildung 5) mit einem Wiederherstellungs Anforderungsvorgang Aufhebung.

![Initiieren einer Semm-Wiederherstellungsanforderung](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Abbildung5. Initiieren einer Semm-Wiederherstellungsanforderung auf der Seite "Unternehmensverwaltung"*

Wenn Sie den Prozess auf der Seite **Unternehmensverwaltung** verwenden, um Semm auf einem Surface-Gerät zurückzusetzen, wird eine Reset-Anforderung bereitgestellt. Diese Reset-Anforderung kann als Datei auf einem USB-Laufwerk gespeichert, als Text kopiert oder als QR-Code mit einem mobilen Gerät gelesen werden, damit Sie einfach per e-Mail oder Nachrichten gesendet werden können. Verwenden Sie die Option Microsoft Surface UEFI Configurator Reset Request, um eine Reset Request-Datei zu laden oder den Reset Request Text oder QR-Code einzugeben. Microsoft Surface UEFI Configurator generiert einen Verifizierungscode, der auf dem Surface-Gerät eingegeben werden kann. Wenn Sie den Code auf dem Surface-Gerät eingeben und auf " **neu starten**" klicken, wird das Gerät von Semm nicht registriert. 

>[!NOTE]
>Eine Reset-Anforderung läuft zwei Stunden nach der Erstellung ab.

Eine Schritt-für-Schritt-Exemplarische Vorgehensweise zum Aufteilen der Registrierung von Surface Devices von Semm finden Sie unter Aufteilen der [Registrierung von Surface Devices from Semm](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).

## Zertifikatanforderungen für den Surface Enterprise-Verwaltungsmodus
Für die Verwendung von Semm mit dem Microsoft Surface UEFI-Konfigurator ist ein Zertifikat erforderlich, um die Signatur von Konfigurationsdateien zu überprüfen, bevor UEFI-Einstellungen angewendet werden können. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts in Semm nur Pakete, die mit dem genehmigten Zertifikat erstellt wurden, verwendet werden können, um die Einstellungen von UEFI zu ändern.

>[!NOTE]
>Das Semm-Zertifikat ist erforderlich, um Änderungen an den Semm-oder Oberflächen UEFI-Einstellungen auf registrierten Surface-Geräten durchzuführen. Wenn das Semm-Zertifikat beschädigt ist oder verloren geht, kann Semm nicht entfernt oder zurückgesetzt werden. Verwalten Sie Ihr Semm-Zertifikat entsprechend mit einer geeigneten Lösung für Sicherung und Wiederherstellung.

Pakete, die mit dem Microsoft Surface UEFI Configurator-Tool erstellt wurden, sind mit einem Zertifikat signiert. Dieses Zertifikat stellt sicher, dass nach der Registrierung eines Geräts in Semm nur Pakete, die mit dem genehmigten Zertifikat erstellt wurden, verwendet werden können, um die Einstellungen von UEFI zu ändern. 
### Empfohlene Zertifikateinstellungen
Die folgenden Einstellungen werden für das Semm-Zertifikat empfohlen:

* **Schlüsselalgorithmus** – RSA 
* **Schlüssellänge** – 2048
* **Hash Algorithmus** – SHA-256
* **Typ** – SSL-Server Authentifizierung
* **Schlüsselverwendung** – digitale Signatur, Schlüssel Verschlüsselung
* **Anbieter** – Microsoft Enhanced RSA und AES Cryptographic Provider
* **Ablaufdatum** – 15 Monate nach der Erstellung des Zertifikats
* **Schlüssel Export Richtlinie** – exportierbar

Außerdem wird empfohlen, das Semm-Zertifikat in einer PKI-Architektur (zweistufig) zu authentifizieren, in der die Zwischenzertifizierungsstelle für Semm dediziert ist und die Zertifikatsperrung aktiviert. Weitere Informationen zu einer zweistufigen PKI-Konfiguration finden Sie unter [Test Labor Handbuch: Bereitstelleneiner AD CS-Two-Tier PKI-Hierarchie](https://technet.microsoft.com/library/hh831348).

### Selbstsigniertes Zertifikat 
Sie können das folgende Beispiel-PowerShell-Skript verwenden, um ein selbstsigniertes Zertifikat zur Verwendung in Szenarien mit Machbarkeitsstudie zu erstellen.
Wenn Sie dieses Skript verwenden möchten, kopieren Sie den folgenden Text in den Editor, und speichern Sie die Datei als PowerShell-Skript (ps1). Hinweis: Dieses Skript erstellt ein Zertifikat mit einem Kennwort von `12345678` . Das von diesem Skript generierte Zertifikat wird für Produktionsumgebungen nicht empfohlen.
  
   ```
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
>Zur Verwendung mit Semm und Microsoft Surface UEFI Configurator muss das Zertifikat mit dem privaten Schlüssel und mit Kennwortschutz exportiert werden. Der Microsoft Surface UEFI Configurator fordert Sie auf, die Semm-Zertifikatsdatei (. pfx) und das Zertifikat Kennwort auszuwählen, wenn dies erforderlich ist.

1.  Erstellen Sie einen Ordner auf Ihrem Laufwerk C:, in dem Sie das Skript speichern können. Beispiel: C:\SEMM.
2.  Kopieren Sie das Beispielskript in den Editor oder den entsprechenden Text-Editor, und speichern Sie die Datei als PowerShell-Skript (ps1).
3.  Melden Sie sich bei Ihrem PC mit Administratoranmeldeinformationen an, und öffnen Sie eine erhöhte PowerShell-Sitzung.
4.  Stellen Sie sicher, dass Ihre Berechtigungen so eingestellt sind, dass Skripts ausgeführt werden können. Standardmäßig werden Skripts nur ausgeführt, wenn Sie die Ausführungsrichtlinie ändern. Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).
5.  Geben Sie an der Eingabeaufforderung den vollständigen Pfad des Skripts ein, und drücken Sie dann die EINGABETASTE. Das Skript erstellt ein Demo Zertifikat mit dem Namen "TempOwner. pfx".

Alternativ können Sie mit PowerShell ein eigenes selbstsigniertes Zertifikat erstellen. Weitere Informationen finden Sie in der folgenden PowerShell-Dokumentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).




>[!NOTE]
>Für Organisationen, die einen offlinestamm in Ihrer PKI-Infrastruktur verwenden, muss der Microsoft Surface UEFI-Konfigurator in einer Umgebung ausgeführt werden, die mit der Stammzertifizierungsstelle verbunden ist, um das Semm-Zertifikat zu authentifizieren. Die von Microsoft Surface UEFI Configurator generierten Pakete können als Dateien übertragen werden und können daher außerhalb der Offline-Netzwerkumgebung mit Wechselmedien wie einem USB-Stick übertragen werden.

### Häufig gestellte Fragen zum Verwalten von Zertifikaten

Die empfohlene *Mindestlänge beträgt* 15 Monate. Sie können ein Zertifikat verwenden, das in weniger als 15 Monaten abläuft, oder ein Zertifikat verwenden, das in mehr als 15 Monaten abläuft.

>[!NOTE] 
>Wenn ein Zertifikat abläuft, wird es nicht automatisch verlängert. 


**Hat ein abgelaufenes Zertifikat Auswirkungen auf die Funktionalität von Semm-registrierten Geräten?**<br><br>
Nein, ein Zertifikat hat nur Auswirkungen auf die Verwaltungsaufgaben für IT-Administratoren in Semm und hat keine Auswirkungen auf die Gerätefunktionalität, wenn es abläuft.


**Müssen das Semm-Paket und-Zertifikat auf allen Computern, auf denen es installiert ist, aktualisiert werden?**

Wenn Semm Reset oder Recovery funktionieren soll, muss das Zertifikat gültig und nicht abgelaufen sein. 

**Können Massen Zurücksetzungs Pakete für jede Oberfläche erstellt werden, die wir bestellen? Kann eine erstellt werden, mit der alle Computer in unserer Umgebung zurückgesetzt werden?**

Die PowerShell-Beispiele zum Erstellen eines Konfigurationspakets für einen bestimmten Gerätetyp können auch verwendet werden, um ein Reset-Paket zu erstellen, das unabhängig von der Seriennummer ist. Wenn das Zertifikat weiterhin gültig ist, können Sie mithilfe von PowerShell ein Reset-Paket erstellen, um Semm zurückzusetzen.

## Versionsverlauf


### Version 2.78.139.0

Diese Version von Semm umfasst:

- Unterstützung für Surface Notebook Go und Surface pro X
- Benachrichtigungen für die neue Version
- Möglichkeit zum Erstellen benutzerdefinierter Pakete zum Ändern des Besitzers
- Fehlerbehebungen




### Version 2.73.136.0

Diese Version von Semm umfasst:

- Audiofunktionen können nun auf DGM-Hub2S mit Semm deaktiviert werden
- Unterstützung für Surface pro X für Dock 2
- Unterstützung für UEFI-Manager für Verwandte Vorgänge in Dock 2
- Fehlerbehebung für das Surface go-Paket zurücksetzen
- Unterstützung für die Migration von Surface Hub 2-Geräten von Windows 10 Team OS zu Windows 10 pro oder Enterprise.

### Version 2.71.139.0

Diese Version von Semm bietet Unterstützung für Surface Dock 2-Verwaltungsfeatures für Surface Book 3, Surface Laptop 3 und Surface pro 7, einschließlich:

- Aktivieren von Audio (sperren/entsperren), Ethernet-und USB-Anschlüssen
- Möglichkeit zum Erstellen von Dock-Paketen für authentifizierte und nicht authentifizierte Hosts

### Version 2.70.130.0

Diese Version von Semm umfasst:

- Unterstützung für Surface Go 2
- Unterstützung für DGM-Buch 3
- Fehlerbehebungen


### Version 2.59.139.0

* Unterstützung für Surface pro 7, Surface pro X und Surface Laptop 3 13,5 "und 15"-Modelle mit Intel-Prozessor. Hinweis: Surface Laptop 3 15 "AMD-Prozessor wird nicht unterstützt.

- Unterstützung für Wake-on-Power-Feature

### Version 2.54.139.0
* Unterstützung für Surface Hub 2S
* Fehlerbehebungen

### Version 2.43.136.0
* Unterstützung für die Aktivierung/Deaktivierung von simulatenous-multibedrohungs 
* Getrennte Optionen für WLAN und Bluetooth für einige Geräte 
* Akku Grenze für Surface Studio entfernt 

### Version 2.26.136.0
* Unterstützung für Surface Studio 2 hinzufügen
* Funktion für Batterie Grenze

### Version 2.21.136.0
* Unterstützung für Surface pro 6 hinzufügen
* Unterstützung für Surface Laptop 2 hinzufügen

### Version 2.14.136.0
* Unterstützung für Surface go hinzufügen

### Version2.9.136.0
* Unterstützung für Surface Book 2 hinzufügen
* Unterstützung für Surface pro LTE hinzufügen
* Verbesserungen der Barrierefreiheit

### Version 1.0.74.0
* Unterstützung für Surface Laptop hinzufügen
* Unterstützung für Surface pro hinzufügen
* Fehlerbehebungen und allgemeine Verbesserungen

## Verwandte Themen

- [Registrieren und Konfigurieren von Surface-Geräten mit SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Aufheben der Registrierung von Surface-Geräten bei SEMM](unenroll-surface-devices-from-semm.md)
- [Sichern von Surface Dock 2-Ports mit SEMM](secure-surface-dock-ports-semm.md)
