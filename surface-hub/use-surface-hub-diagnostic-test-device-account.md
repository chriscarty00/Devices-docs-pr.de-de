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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832680"
---
# Verwenden des Hardwarediagnosetools für Surface Hub zum Testen eines Gerätekontos

## Einführung

> [!NOTE]
> Im Abschnitt "Kontoeinstellungen" des Surface Hub Hardware-Diagnosetools werden keine Informationen erfasst. Die e-Mail-Adresse und das Kennwort, die als Eingabe eingegeben werden, werden nur direkt in Ihrer Umgebung verwendet und nicht erfasst oder an andere Personen übertragen. Die Anmeldeinformationen bleiben nur solange bestehen, bis die Anwendung geschlossen ist, oder Sie beenden die aktuelle Sitzung auf dem Surface Hub.

> [!IMPORTANT]
> * Zum Ausführen dieser Anwendung sind keine Administrator Rechte erforderlich.
> * Die Ergebnisse der Diagnose sollten mit Ihrem lokalen Administrator besprochen werden, bevor Sie einen Service-Anruf mit Microsoft öffnen.

### Surface Hub-Hardware Diagnose

Standardmäßig ist die [Surface Hub-Hardware Diagnose](https://www.microsoft.com/store/apps/9nblggh51f2g) Anwendung in früheren Versionen des Surface Hub-Systems nicht installiert. Die Anwendung steht kostenlos im Microsoft Store zur Verfügung. Zum Installieren der Anwendung sind Administrator Rechte erforderlich.

   ![Screenshot der Hardware Diagnose](images/01-diagnostic.png)

## Informationen zum Hardware-Diagnose Tool Surface Hub

Das Surface-Hub-Hardware-Diagnosetool ist ein einfach zu navigierendes Tool, mit dem der Benutzer viele der Hardware Komponenten innerhalb des Surface Hub-Geräts testen kann. Mit diesem Tool können Sie auch ein Surface Hub-Geräte Konto testen und überprüfen. In diesem Artikel wird beschrieben, wie Sie den Konto Einstellungstest innerhalb des Surface Hub Hardware-Diagnosetools verwenden.

> [!NOTE]
> Das Geräte Konto für den Surface Hub sollte erstellt werden, bevor eine Prüfung durchgeführt wird. Das Surface Hub-Administrator Handbuch enthält Anweisungen und PowerShell-Skripts, die Ihnen beim Erstellen von lokalen, Online-(Office365) oder hybriden Geräte Konten helfen. Weitere Informationen finden Sie im Leitfaden unter [Erstellen und Testen eines Geräte Kontos (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) .

### Testprozess für Geräte Konten

1. Navigieren Sie zu **allen apps**, und suchen Sie dann nach der Surface Hub-Hardware Diagnoseanwendung.

    ![Screenshot aller apps](images/02-all-apps.png)

1. Wenn die Anwendung gestartet wird, enthält die **Willkommens** Seite ein Textfenster, um den Grund für das Testen des Hubs zu dokumentieren. Diese Notiz kann zusammen mit den Diagnoseergebnissen nach Abschluss des Tests auf USB gespeichert werden. Nachdem Sie die Eingabe einer Notiz abgeschlossen haben, wählen Sie die Schaltfläche **weiter** aus.

    ![Screenshot der Willkommensseite](images/03-welcome.png)

1. Der nächste Bildschirm bietet Ihnen die Möglichkeit, alle oder einige der Surface Hub-Komponenten zu testen. Um mit dem Testen des Geräte Kontos zu beginnen, wählen Sie das Symbol **Testergebnisse** aus.

    ![Screenshot der Test Ergebnisse](images/04-test-results-1.png)

    ![Screenshot der Test Ergebnisse](images/05-test-results-2.png)

1. Wählen Sie **Kontoeinstellungen**aus.  

    ![Screenshot der Kontoeinstellungen](images/06-account-settings.png)

    Der Bildschirm Kontoeinstellungen wird verwendet, um Ihr Geräte Konto zu testen.

    ![Screenshot der Details zur Kontoeinstellungen](images/07-account-settings-details.png)

1. Geben Sie die e-Mail-Adresse Ihres Geräte Kontos ein. Das Kennwort ist optional, wird aber empfohlen. Wählen Sie die Schaltfläche **Testkonto** aus, wenn Sie den Vorgang fortsetzen möchten.

    ![Screenshot des Test Kontos](images/08-test-account.png)

1. Überprüfen Sie nach Abschluss der Tests die Ergebnisse für die vier Testbereiche. Jeder Abschnitt kann erweitert oder reduziert werden, indem Sie das Plus-oder Minus Zeichen neben den einzelnen Themen auswählen.

    **Network**

    ![Screenshot des Netzwerks](images/09-network.png)

    **Umgebung**

    ![Screenshot der Umgebung](images/10-environment.png)

    **Zertifikate**

    ![Screenshot der Zertifikate](images/11-certificates.png)

    **Trust-Modell**

    ![Screenshot des Trust-Modells](images/12-trust-model.png)

## Anhang

### Feld Nachrichten und-Auflösung

#### Network

Feld |Erfolgreich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
Internet Konnektivität |Gerät verfügt über eine Internet Verbindung |Gerät hat keine Internet Verbindung |Überprüft die Internetkonnektivität, einschließlich der Proxyverbindung |
HTTP-Version |1.1 |1.0 |Wenn HTTP 1,0 gefunden wird, führt dies zu Problemen mit Wu und Store |
Direkte Internet Verbindung |Gerät verfügt über ein Proxy konfiguriertes Gerät hat keinen Proxy konfiguriert |n.v. |Informations. Befindet sich Ihr Gerät hinter einem Proxy? |
Proxy Adresse | | |Wenn konfiguriert, gibt Proxyadresse zurück. |
Proxy Authentifizierung |Proxy erfordert keine Authentifizierung |Proxy erfordert Proxy-Authentifizierung |Das Ergebnis kann ein falsch positiver Effekt sein, wenn ein Benutzer bereits über eine offene Sitzung in Edge verfügt und über den Proxy authentifiziert wurde. |
Proxy-auth-Typen | | |Wenn Proxyauthentifizierung verwendet wird, geben Sie die vom Proxy angekündigten Authentifizierungsmethoden zurück.  |

#### Umgebung

Feld |Erfolgreich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
SIP-Domäne | | |Informations.  |
Skype-Umgebung |Skype for Business Online, Skype for Business onprem, Skype for Business-Hybrid |Informations. |Der Typ der Umgebung wurde erkannt. Hinweis: Hybrid kann nur erkannt werden, wenn das Kennwort eingegeben wurde.
LyncDiscover-FQDN | | |Informations. Zeigt das LyncDiscover-DNS-Ergebnis an |
LyncDiscover-URI | | |Informations. Zeigt die URL an, die zum Ausführen eines LyncDiscover in Ihrer Umgebung verwendet wird.|
LyncDiscover |Verbindung erfolgreich |Verbindung fehlgeschlagen |Antwort des LyncDiscover-Webdiensts. |
SIP-Pool-Hostname | | |Informations. Anzeigen des von LyncDiscover entdeckten SIP-Pool namens |

#### Zertifikate (nur in-Premise-Hybrid)

LyncDiscover-Zertifikat

Feld |Erfolgreich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
LyncDiscover CERT CN | | |Informations. Zeigt den allgemeinen Namen LD CERT an |
LyncDiscover CERT-Zertifizierungsstelle | | |Informations. Zeigt die LD CERT-Zertifizierungsstelle an |
LyncDiscover CERT-Stammzertifizierungsstelle | | |Informations. Zeigt die LD CERT-Stammzertifizierungsstelle an, sofern verfügbar. |
LD-Vertrauens Status |Zertifikat ist vertrauenswürdig. |Zertifikat nicht vertrauenswürdig ist, fügen Sie die Stammzertifizierungsstelle hinzu. |Überprüfen Sie das Zertifikat für den lokalen CERT-Speicher. Gibt positive zurück, wenn der Computer dem Zertifikat vertraut.|[Herunterladen und Bereitstellen von Skype for Business-Zertifikaten mithilfe von PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Unterstützte Elemente für Surface Hub-Bereitstellungspakete](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP-Pool-Zertifizierung

Feld |Erfolgreich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
SIP-Pool CERT CN | | |Inhalt |
SIP-Pool-CERT-Zertifizierungsstelle | | |Inhalt |
SIP-Pool-Vertrauens Status |Zertifikat ist vertrauenswürdig. |Zertifikat nicht vertrauenswürdig ist, fügen Sie die Stammzertifizierungsstelle hinzu. |Überprüfen Sie das Zertifikat für den lokalen Zertifikatspeicher, und geben Sie einen positiven Wert zurück, wenn die Geräte dem Zertifikat vertrauen. |
SIP-Pool CERT-Stammzertifizierungsstelle | | |Informationen. Anzeigen der SIP-Pool CERT-Stammzertifizierungsstelle (sofern verfügbar) |

#### Trust-Modell (nur lokales Hybrid)

Feld |Erfolgreich |Fehler |Kommentar |Verweis
|------|------|------|------|------|
Status des Trust-Modells |Das Problem mit dem Trust-Modell wurde nicht erkannt. |SIP-Domäne und Server Domäne sind unterschiedlich Bitte fügen Sie die folgenden Domänen hinzu. |Überprüfen Sie den LD-FQDN/LD-Servernamen/Pool Servernamen für das Problem des Vertrauensmodells. 
Domänen Name (n) | | |Geben Sie die Liste der Domänen zurück, die der SFB hinzugefügt werden soll, um eine Verbindung herzustellen. |
