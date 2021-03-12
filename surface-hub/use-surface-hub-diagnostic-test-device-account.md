---
title: Verwenden des Hardwarediagnosetools für Surface Hub zum Testen eines Gerätekontos
description: Verwenden des Hardwarediagnosetools für Surface Hub zum Testen eines Gerätekontos
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: Barrierefreiheiteinstellungen, Einstellungs-App, Erleichterte Bedienung
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 6661f2347d2f411ed11fe6057ede8ca2bab07c33
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406668"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a>Verwenden des Hardwarediagnosetools für Surface Hub zum Testen eines Gerätekontos

## <a name="introduction"></a>Einführung

> [!NOTE]
> Im Abschnitt "Kontoeinstellungen" des Surface Hub-Hardwarediagnosetools werden keine Informationen gesammelt. Die E-Mail und das Kennwort, die als Eingabe eingegeben werden, werden nur direkt in Ihrer Umgebung verwendet und nicht gesammelt oder an niemanden übertragen. Die Anmeldeinformationen bleiben nur so lange erhalten, bis die Anwendung geschlossen ist oder Sie die aktuelle Sitzung auf dem Surface Hub beenden.

> [!IMPORTANT]
> * Zum Ausführen dieser Anwendung sind keine Administratorrechte erforderlich.
> * Die Ergebnisse der Diagnose sollten mit Ihrem lokalen Administrator besprochen werden, bevor Sie einen Dienstanruf mit Microsoft öffnen.

### <a name="surface-hub-hardware-diagnostic"></a>Surface Hub Hardware Diagnostic

Standardmäßig ist die [Surface Hub-Hardwarediagnoseanwendung](https://www.microsoft.com/store/apps/9nblggh51f2g) in früheren Versionen des Surface Hub-Systems nicht installiert. Die Anwendung ist kostenlos im Microsoft Store verfügbar. Zum Installieren der Anwendung sind Administratorrechte erforderlich.

   ![Screenshot der Hardwarediagnose](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a>Informationen zum Surface Hub Hardware Diagnostic Tool

Das Surface Hub-Hardwarediagnosetool ist ein leicht zu navigierendes Tool, mit dem der Benutzer viele der Hardwarekomponenten innerhalb des Surface Hub-Geräts testen kann. Dieses Tool kann auch ein Surface Hub-Gerätekonto testen und überprüfen. In diesem Artikel wird beschrieben, wie Sie den Test "Kontoeinstellungen" im Surface Hub-Hardwarediagnosetool verwenden.

> [!NOTE]
> Das Gerätekonto für den Surface Hub sollte erstellt werden, bevor tests durchgeführt werden. Das Surface Hub-Administratorhandbuch enthält Anweisungen und PowerShell-Skripts, mit deren Hilfe Sie lokale, online (Office365) oder Hybridgerätekonten erstellen können. Weitere Informationen finden Sie im Thema Erstellen und Testen eines Gerätekontos [(Surface Hub).](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)

### <a name="device-account-testing-process"></a>Testprozess für Gerätekonto

1. Navigieren Sie **zu Alle Apps,** und suchen Sie dann die Surface Hub Hardware Diagnostic-Anwendung.

    ![Screenshot aller Apps](images/02-all-apps.png)

1. Wenn die Anwendung gestartet wird, stellt die **Willkommensseite** ein Textfenster zur Verfügung, um den Grund zu dokumentieren, warum Sie den Hub testen. Dieser Hinweis kann zusammen mit den Diagnoseergebnissen nach Abschluss der Tests auf USB gespeichert werden. Nachdem Sie die Eingabe einer Notiz abgeschlossen haben, wählen Sie die Schaltfläche **Weiter** aus.

    >[!NOTE]
    >Ändern Sie beim Speichern von Diagnoseergebnissen nicht den Standardpfad, oder wählen Sie ein Unterverzeichnis aus. Die Dateien können später über die Datei-Explorer-App kopiert werden.

    ![Screenshot von Willkommen](images/03-welcome.png)

1. Auf dem nächsten Bildschirm können Sie alle oder einige Surface Hub-Komponenten testen. Um mit dem Testen des Gerätekontos zu beginnen, wählen Sie das **Symbol Testergebnisse** aus.

    ![Screenshot der Testoptionen](images/04-test-results-1.png)

    ![Screenshot der Testergebnisse](images/05-test-results-2.png)

1. Wählen **Sie Kontoeinstellungen aus.**  

    ![Screenshot der Kontoeinstellungen](images/06-account-settings.png)

    Der Bildschirm Kontoeinstellungen wird zum Testen Ihres Gerätekontos verwendet.

    ![Screenshot der Kontoeinstellungen](images/07-account-settings-details.png)

1. Geben Sie die E-Mail-Adresse Ihres Gerätekontos ein. Das Kennwort ist optional, wird jedoch empfohlen. Wählen Sie **die Schaltfläche Konto testen** aus, wenn Sie zum Fortfahren bereit sind.

    ![Screenshot des Testkontos](images/08-test-account.png)

1. Überprüfen Sie nach Abschluss der Tests die Ergebnisse für die vier Testbereiche. Jeder Abschnitt kann durch Auswählen des Plus- oder Minuszeichens neben jedem Thema erweitert oder reduziert werden.

    **Network**

    ![Screenshot des Netzwerks](images/09-network.png)

    **Umgebung**

    ![Screenshot der Umgebung](images/10-environment.png)

    **Zertifikate**

    ![Screenshot von Zertifikaten](images/11-certificates.png)

    **Vertrauensstellungsmodell**

    ![Screenshot des Vertrauensstellungsmodells](images/12-trust-model.png)

## <a name="appendix"></a>Anhang

### <a name="field-messages-and-resolution"></a>Feldmeldungen und -auflösung

#### <a name="network"></a>Network

Feld |Möglich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
Internetkonnektivität |Gerät verfügt über Internetverbindung |Gerät hat keine Internetverbindung |Überprüft die Internetverbindung, einschließlich der Proxyverbindung |
HTTP-Version |1.1 |1.0 |Wenn HTTP 1.0 gefunden wurde, verursacht dies ein Problem mit WU und Store |
Direkte Internetverbindung |Gerät verfügt über einen Proxy konfiguriertEs Gerät hat keinen Proxy konfiguriert |n.a. |Informationell. Befindet sich Ihr Gerät hinter einem Proxy? |
Proxyadresse | | |Wenn konfiguriert, gibt Proxyadresse zurück. |
Proxyauthentifizierung |Proxy erfordert keine Authentifizierung |Proxy erfordert Proxyauth |Das Ergebnis kann ein falsch positives Ergebnis sein, wenn ein Benutzer bereits über eine geöffnete Sitzung in Edge verfügt und sich über den Proxy authentifiziert hat. |
Proxy-Authentifizierungstypen | | |Wenn die Proxyauthentifizierung verwendet wird, geben Sie die vom Proxy angekündigten Authentifizierungsmethoden zurück.  |

#### <a name="environment"></a>Umgebung

Feld |Möglich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
SIP-Domäne | | |Informationell.  |
Skype-Umgebung |Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid |Informationell. |Welche Art von Umgebung erkannt wurde. Hinweis: Hybrid kann nur erkannt werden, wenn das Kennwort eingegeben wird.
LyncDiscover-FQDN | | |Informationell. Zeigt das LyncDiscover-DNS-Ergebnis an |
LyncDiscover-URI | | |Informationell. Zeigt die URL an, die zum Ausführen einer LyncDiscover in Ihrer Umgebung verwendet wird.|
LyncDiscover |Verbindung erfolgreich |Verbindung fehlgeschlagen |Antwort vom LyncDiscover-Webdienst. |
SIP-Pool-Hostname | | |Informationell. Anzeigen des aus LyncDiscover ermittelten SIP-Poolnamens |

#### <a name="certificates-in-premises-hybrid-only"></a>Zertifikate (nur lokale Hybride)

LyncDiscover-Zertifikat

Feld |Möglich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
LyncDiscover Cert CN | | |Informationell. Zeigt den #A0 Common name an |
LyncDiscover Cert CA | | |Informationell. Zeigt die #A0 an |
LyncDiscover Cert Stammzertifizierungsstelle | | |Informationell. Zeigt die LD Cert-Stammzertifizierungsstelle an, sofern verfügbar. |
LD Trust Status |Das Zertifikat ist vertrauenswürdig. |Zertifikat ist nicht vertrauenswürdig, fügen Sie bitte die Stammzertifizierungsstelle hinzu. |Überprüfen Sie das Zertifikat mit dem lokalen Zertifikatspeicher. Gibt positive Ergebnisse zurück, wenn der Computer dem Zertifikat vertraut.|[Herunterladen und Bereitstellen von Skype for Business-Zertifikaten mithilfe von PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Unterstützte Elemente für Surface Hub-Bereitstellungspakete](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP-Poolzertifizierung

Feld |Möglich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
SIP-Pool-Cert-CN | | |(INHALT) |
#A0 | | |(INHALT) |
SIP-Pool-Vertrauensstatus |Das Zertifikat ist vertrauenswürdig. |Zertifikat ist nicht vertrauenswürdig, fügen Sie bitte die Stammzertifizierungsstelle hinzu. |Überprüfen Sie das Zertifikat mit dem lokalen Zertifikatspeicher, und geben Sie ein Positives zurück, wenn die Geräte dem Zertifikat vertrauen. |
SIP-Pool-Zertifikatstammzertifizierungsstelle | | |Informationen. Zeigen Sie die SIP-Pool-Cert-Stammzertifizierungsstelle an, sofern verfügbar. |

#### <a name="trust-model-on-premises-hybrid-only"></a>Vertrauensstellungsmodell (nur lokale Hybridbereitstellung)

Feld |Möglich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
Status des Vertrauensstellungsmodells |Kein Vertrauensstellungsmodellproblem erkannt. |SIP-Domäne und Serverdomäne unterscheiden sich, fügen Sie bitte die folgenden Domänen hinzu. |Überprüfen Sie den NAMEN des LD-FQDN/LD-Servernamens/Poolservers auf das Problem mit dem Vertrauensstellungsmodell. 
Domänenname(n) | | |Gibt die Liste der Domänen zurück, die hinzugefügt werden sollen, damit SFB eine Verbindung herstellen kann. |
