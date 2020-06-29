---
title: Surface-Diagnosetoolkit für Unternehmen im Desktopmodus verwenden
description: So verwenden Sie die Funktion "nachfragen", damit Benutzer in Ihrer Organisation das Tool ausführen können, um Probleme mit dem Surface-Gerät zu erkennen und zu diagnostizieren.
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
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832218"
---
# Surface-Diagnosetoolkit für Unternehmen im Desktopmodus verwenden

In diesem Thema wird erläutert, wie Sie mit dem Surface Diagnostic Toolkit (unstrukturiertes Toolkit) Benutzern in Ihrer Organisation das Tool zum Ermitteln und Diagnostizieren von Problemen mit dem Surface-Gerät zur Verfügung stellen. Durch das erfolgreiche Ausführen von "mit" können Sie schnell feststellen, ob ein gemeldetes Problem durch fehlerhafte Hardware oder Benutzer verursacht wurde. Eine Liste der unterstützten Surface-Geräte finden Sie unter [Bereitstellen des Surface Diagnostics Toolkit for Business](surface-diagnostic-toolkit-business.md).


1. Weisen Sie den Benutzer an, das unstrukturierte [Paket](surface-diagnostic-toolkit-business.md#create-custom-sdt) von einem Softwareverteilungspunkt oder einer Netzwerkfreigabe zu installieren. Nachdem die Installation abgeschlossen ist, können Sie den Benutzer durch eine Reihe von Tests führen. 

2. Beginnen Sie auf der Startseite, die es Benutzern ermöglicht, eine Beschreibung des Problems einzugeben, und klicken Sie auf **weiter**, wie in Abbildung 1 dargestellt.

    ![Starten Sie "im Desktopmodus" ](images/sdt-desk-1.png)
 *, Abbildung 1. Im Desktopmodus*

3. Wenn für das Gerät die neuesten Updates angezeigt werden, klicken Sie auf **weiter** , um zum Katalog der verfügbaren Tests zu gelangen, wie in Abbildung 2 zu sehen ist.

    ![Wählen Sie aus den Optionen in der Sonderoptionen ](images/sdt-desk-2.png)
 *Abbildung 2 aus. Wählen Sie aus den Optionen für eine Option aus* .

4. Sie können auswählen, dass alle Diagnosetests ausgeführt werden. Wenn Sie bereits ein bestimmtes Problem wie eine fehlerhafte Anzeige oder ein Netzteil-Problem vermuten, klicken Sie auf **auswählen** , um aus den verfügbaren Tests auszuwählen, und klicken Sie auf **ausgewählt ausführen**, wie in Abbildung 3 dargestellt. Einzelheiten zu den einzelnen Tests finden Sie in der folgenden Tabelle. 

    ![Wählen Sie Hardwaretests aus ](images/sdt-desk-3.png)
 *Abbildung 3 aus. Hardwaretests auswählen*

    Hardware Test | Beschreibung
    --- | ---
    Netzteil und Akku |  Überprüft, ob die Stromversorgung optimal funktioniert
    Anzeige und Sound   | Überprüft Helligkeit, hängende oder tote Pixel, Lautsprecher und Mikrofonfunktion
    Anschlüsse und Zubehör   | Überprüft Zubehör, Bildschirm Befestigung und USB-Funktion
    Konnektivität |  Überprüft die Bluetooth-, Wireless-und LTE-Konnektivität
    Sicherheit    | Überprüfung von sicherheitsrelevanten Problemen
    Toucheingabe   | Überprüfung von Berührungs bezogenen Problemen
    Tastatur und Fingereingabe |    Überprüft die integrierte Tastaturverbindung und den Typ der Abdeckung
    Sensoren | Überprüft die Funktionsweise unterschiedlicher Sensoren im Gerät
    Hardware |  Überprüfung von Problemen mit verschiedenen Hardwarekomponenten wie Grafikkarte und Kamera





<span id="multiple" />

## Ausführen mehrerer Hardwaretests zur Behebung von Problemen

Sie ist als interaktives Tool konzipiert, das eine Reihe von Tests ausführt. Bei jedem Test bietet Ihnen das Unternehmen eine Anleitung, in der die Art des Tests zusammengefasst wird und welche Benutzer erwarten sollten, damit der Test erfolgreich ist. Wenn Sie beispielsweise diagnostizieren möchten, ob die Anzeigehelligkeit ordnungsgemäß funktioniert, beginnt die Helligkeits Anzeige mit 0 (null) und erhöht die Helligkeit auf 100 Prozent **Yes** , und **No** die Benutzer werden aufgefordert, zu bestätigen, dass die Helligkeit wie erwartet funktioniert, wie in Abbildung 4 zu sehen ist. 

Wenn die Funktionalität für jeden Test nicht erwartungsgemäß funktioniert und der Benutzer auf **Nein**klickt, generiert Sie einen Bericht über die möglichen Ursachen und Möglichkeiten zur Problembehandlung. 

![Ausführen der Hardwarediagnose ](images/sdt-desk-4.png)
 *Abbildung 4. Ausführen der Hardwarediagnose*

1. Wenn die Helligkeit erfolgreich von 0-100 Prozent wie erwartet eingestellt wird, führen Sie den Benutzer aus, klicken Sie auf **Ja** , und klicken Sie dann auf **weiter**. 
2. Wenn die Helligkeit von 0-100 Prozent nicht erwartungsgemäß angepasst werden kann, verweisen Sie den Benutzer auf **Nein** , und klicken Sie dann auf **weiter**. 
3. Führen Sie die Benutzer durch die restlichen Tests nach Bedarf. Nach Abschluss des Vorgangs stellt das Unternehmen automatisch eine Zusammenfassung des Berichts auf hoher Ebene bereit, einschließlich der möglichen Ursachen für Hardwareprobleme zusammen mit Anleitungen für die Lösung.


### Reparieren von Anwendungen

Mit "mit" können Sie Anwendungen diagnostizieren und reparieren, die möglicherweise Probleme verursachen, wie in Abbildung 5 zu sehen ist.

![Ausführen von Reparaturen ](images/sdt-desk-5.png)
 *Abbildung 5. Ausführen von Reparaturen*
<span id="logs" />

### Generieren von Protokollen zum Analysieren von Problemen 

In Abbildung 6 wird die umfassende Protokollierungs fähige Diagnoseunterstützung für Anwendungen, Treiber, Hardware und Betriebssystemprobleme bereitgestellt.

![Generieren von Protokollen ](images/sdt-desk-6.png)
 *Abbildung 6. Generieren von Protokollen*

<span id="detailed-report" />

### Generieren eines detaillierten Berichts, der die Geräte-vs. optimale Konfiguration vergleicht

Basierend auf den Protokollen generiert Sie einen Bericht für Software-und Firmware-basierte Probleme, die Sie an einem bevorzugten Speicherort speichern können.

## Verwandte Themen

- [Ausführen von Surface-Diagnosetoolkit für Unternehmen mithilfe von Befehlen](surface-diagnostic-toolkit-command-line.md)

