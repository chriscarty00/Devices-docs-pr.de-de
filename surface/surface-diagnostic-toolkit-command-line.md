---
title: Ausführen von Surface-Diagnosetoolkit für Unternehmen mithilfe von Befehlen
description: Ausführen des Surface Diagnostic Toolkit in einer Befehlskonsole
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832239"
---
# Ausführen von Surface-Diagnosetoolkit für Unternehmen mithilfe von Befehlen

Wenn Sie das Surface Diagnostic Toolkit (unstrukturiertes Toolkit) an der Eingabeaufforderung ausführen, müssen Sie die Std-App-Konsole herunterladen. Nachdem die Installation abgeschlossen ist, können Sie an einer Eingabeaufforderung über die Windows-Befehlskonsole (cmd.exe) oder mithilfe von Windows PowerShell, einschließlich der PowerShell Integrated Scripting Environment (ISE), Unterstützung für die automatische Vervollständigung von Befehlen, kopieren/einfügen und anderen Features ausführen.  Eine Liste der unterstützten Surface-Geräte finden Sie unter [Bereitstellen des Surface Diagnostics Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Zum Ausführen von "mit"-Funktionen mithilfe von Befehlen müssen Sie beim Administratorkonto angemeldet sein oder bei einem Konto angemeldet sein, das Mitglied der Gruppe "Administratoren" auf Ihrem Surface-Gerät ist.

## Ausführen der APP-Konsole

Herunterladen und Installieren der APP-Konsole auf der [Seite Surface Tools für IT-Download](https://www.microsoft.com/download/details.aspx?id=46703) Sie können die Windows-Eingabeaufforderung (cmd.exe) oder Windows PowerShell verwenden, um Folgendes zu tun: 

- Alle Protokolldateien sammeln.
- Führen Sie die Integritäts Diagnose mithilfe von Best Practice Analyzer aus.
- Überprüfen Sie das Update auf fehlende Firmware-oder Treiberupdates.

>[!NOTE]
>In dieser Version unterstützt die APP-Konsole nur einzelne Befehle. Für die Ausführung mehrerer Befehlszeilenoptionen muss die Console-exe separat für jeden Befehl ausgeführt werden. 

Standardmäßig werden Ausgabedateien am gleichen Speicherort wie die Konsolen-APP gespeichert. In der folgenden Tabelle finden Sie eine vollständige Liste der Befehle.

Befehl | Anmerkungen
--- | ---
-Datacollector "Ausgabedatei" | Sammelt Systemdetails in einer ZIP-Datei. "Ausgabedatei" ist der Dateipfad zum Erstellen einer ZIP-Datei für Systemdetails.<br><br>**Beispiel**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-BPA "Ausgabedatei" | Überprüft mehrere Einstellungen und Integritätsindikatoren auf dem Gerät. "Ausgabedatei" ist der Dateipfad, in dem der HTML-Bericht erstellt wird.<br><br>**Beispiel**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-Windows | Überprüft die Windows Update Online-Server auf fehlende Firmware-und/oder Treiberupdates.<br><br>**Beispiel**:<br>Microsoft.Surface.Diagnostics.App.Console.exe-Windows
-Garantie "Ausgabedatei" | Überprüft die Garantieinformationen auf dem Gerät (gültig oder ungültig). Die optionale "Ausgabedatei" ist der Dateipfad zum Erstellen der XML-Datei. <br><br>**Beispiel**: <br>Microsoft.Surface.Diagnostics.App.Console.exe – Garantie "warranty.xml"


>[!NOTE]
>Sie können ein Konfigurations Verwaltungstool wie Microsoft Endpoint Configuration Manager verwenden, um die APP-Konsole für die APP Remote auf Zielgeräten auszuführen. Sie können auch eine ZIP-Datei mit der Konsolen-APP und den entsprechenden Konsolenbefehlen erstellen und die softwareverteilungsprozesse Ihrer Organisation bereitstellen. 

## Ausführen von Best Practice Analyzer 

Sie können BPA-Tests für Schlüsselkomponenten wie BitLocker, Secure Boot und Trusted Platform Module (TPM) ausführen und die Ergebnisse dann in einer freigegebenen Datei ausgeben. Das Tool generiert eine Reihe von Tabellen mit farbcodierten Überschriften und Zustands Deskriptoren sowie Anleitungen zur Lösung des Problems. 

- Grün zeigt an, dass die Komponente in einem optimalen Zustand (optimal) ausgeführt wird.
- Orange zeigt an, dass die Komponente nicht in einem optimalen Zustand ausgeführt wird (nicht optimal).
- Rot zeigt an, dass sich die Komponente in einem anormalen Zustand befindet. 

### Beispiel für die Ausgabe von BPA-Ergebnissen

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob BitLocker auf dem Systemlaufwerk aktiviert ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Schutz für</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Es wird dringend empfohlen, BitLocker zu aktivieren, um Ihre Daten zu schützen.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Sicherer Start</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob der sichere Start aktiviert ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Wahr</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Es wird dringend empfohlen, Secure Boot zu aktivieren, um Ihren PC zu schützen.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Trusted Platform Module</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Stellt sicher, dass das TPM funktionsfähig ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Wahr</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Ohne ein funktionierendes TPM funktionieren sicherheitsbasierte Funktionen wie BitLocker möglicherweise nicht ordnungsgemäß.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Verbundener Standbymodus</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob verbundener Standbymodus aktiviert ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Wahr</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Verbundener Standby-Modus ermöglicht einem Surface-Gerät das Empfangen von Updates und Benachrichtigungen, während es nicht verwendet wird. Für optimale Benutzerfreundlichkeit sollte der angeschlossene Standbymodus aktiviert sein.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob Bluetooth aktiviert ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Aktiviert</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Debugmodus</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob sich das Betriebssystem im Debugmodus befindet.</td></tr>
<tr><td><strong>Wert</strong></td><td>Normal</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Die Option Debug-Start aktiviert oder deaktiviert das Kernel Debuggen des Windows-Betriebssystems. Wenn Sie diese Option aktivieren, kann dies zu Systeminstabilität führen und verhindern, dass DRM (Digital Rights Abwicklungs)-geschützte Medien wiedergegeben werden.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Testen der Signierung</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob Test Signierung aktiviert ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Normal</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Testsignierung ist eine Windows-Starteinstellung, die nur zum Testen von Pre-Release-Treibern verwendet werden sollte.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Aktiver Energiesparplan</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob der richtige Energiesparplan aktiv ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Ausgeglichen</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Es wird dringend empfohlen, den Energiesparplan "Ausbalanciert" zu verwenden, um die Produktivität und die Akkulaufzeit zu maximieren.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob das Gerät mit Windows-Updates auf dem neuesten Stand ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>Microsoft Silverlight (KB4023307), Definitions Update für Windows Defender Antivirus-KB2267602 (Definition 1.279.1433.0)</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="ff9500">Nicht optimal</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Wenn Sie die neuesten Windows-Updates nutzen, stellen Sie sicher, dass Sie die neueste Firmware und Treiber installiert haben. Es wird empfohlen, das Gerät immer auf dem neuesten Stand zu halten.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Freier Speicherplatz auf der Festplatte</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Überprüft, ob der Speicherplatz auf der Festplatte gering ist.</td></tr>
<tr><td><strong>Wert</strong></td><td>66%</td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Um eine optimale Leistung zu erzielen, sollte Ihre Festplatte mindestens 10% ihrer Kapazität als freier Speicherplatz aufweisen.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Nicht funktionierende Geräte</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Liste der nicht funktionierenden Geräte im Geräte-Manager</td></tr>
<tr><td><strong>Wert</strong></td><td></td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Nicht funktionierende Geräte im Geräte-Manager können zu unvorhersehbaren Problemen mit Oberflächen Geräten führen, wie etwa, aber nicht ausschließlich, keine Strom Ersparnisse für die jeweilige Hardwarekomponente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Externer Monitor</font></th></tr>
<tr><td><strong>Beschreibung:</strong></td><td>Sucht nach einem externen Monitor, der möglicherweise Kompatibilitätsprobleme aufweist.</td></tr>
<tr><td><strong>Wert</strong></td><td></td></tr>
<tr><td><strong>Bedingung</strong></td><td><font color="00ff00">Optimale</font></td></tr>
<tr><td><strong>Führung</strong></td><td>Erkundigen Sie sich beim Originalgerätehersteller, ob Sie mit Ihrem Surface-Gerät kompatibel sind.</td></tr>
</table>
