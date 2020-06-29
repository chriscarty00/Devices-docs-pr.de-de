---
title: Surface Hub 2S-Bereitstellungs Prüflisten
description: Überprüfen Sie Ihre Bereitstellung von Surface Hub 2S mithilfe von Pre-und Post-Deployment-Checklisten.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 3c30892a3ae4f534006aa32ad6d969b42a52cbf2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833793"
---
# Surface Hub 2S-Bereitstellungs Prüflisten

## Checkliste für Surface Hub 2S vor der Bereitstellung

|**Element**|**Antwort**|
|:------ |:------ |
|**Name des Geräte Kontos**| |
|**UPN des Geräte Kontos**| |
|**ActiveSync-Richtlinie**| |
|**Kalenderverarbeitungskonfiguration abgeschlossen**| ☐ Ja <br>  ☐ Nein |
|**Geräte freundlicher Name**| |
|**Geräte Host Name**| |
|**Zugehörigkeit**| ☐ Keine <br> ☐ Active Directory-Zugehörigkeit <br> ☐ Azure Active Directory |
|**Microsoft Teams-Modus**| ☐ Modus 0 <br> ☐ Modus 1 <br> ☐ Modus 2 |
|**Geräteverwaltung**| ☐ Ja, Microsoft InTune <br> ☐ Ja, anderer mobiler Geräte-Manager [MDM] <br> ☐ Keine |  
|**Proxy**| ☐ Automatische Konfiguration <br> ☐ Proxy Server <br> ☐-Proxy-Auto-config-Datei (PAC) |
|**Proxy Authentifizierung**| Anmeldeinformationen für ☐ Geräte Konto <br> ☐ Aufforderung zur Eingabe von Anmeldeinformationen |
|**Kennwortrotation**| ☐ Ein <br> ☐ Aus |
|**Zusätzliche Domänennamen für Skype for Business (nur lokal)**| |
|**Sitzungstimeout Zeit**| |
|**Sitzungstimeout Aktion**| ☐ Sitzung beenden <br> ☐ "Lebenslauf zulassen" |
|**Meine Besprechungen und Dateien**| ☐ Aktiviert <br> ☐ Deaktiviert |
|**Timeout für Sperrbildschirm**| |
|**Sleep-Idle-Timeout**| |
|**Bluetooth**| ☐ Ein <br> ☐ Aus |
|**Nur BitLocker-USB-Laufwerke verwenden**| ☐ Ein <br> ☐ Aus |
|**Installieren zusätzlicher Zertifikate (nur lokal)**| |
|**Windows Update**| ☐ Windows Update für Unternehmen <br> ☐ Windows Server Update Services [WSUS] |
|**Oberflächen-App-Lautsprechereinstellung**| ☐ Rolling-Ständer <br> ☐ Wandmontage |
|**IP-Adresse**| ☐ Verkabelt – DHCP <br> ☐ Wired – DHCP-Reservierung <br> ☐ Drahtlos – DHCP <br> ☐ Drahtlos – DHCP-Reservierung |

## Surface Hub 2S – Checkliste für nach der Bereitstellung

|**Überprüfen**|**Antwort**|
|:------|:---------|
|**Synchronisierung des Geräte Kontos**| ☐ Ja <br> ☐ Nein |
|**BitLocker-Taste**| ☐ In Datei gespeichert (keine Zugehörigkeit) <br> In Active Directory gespeicherte ☐ (AD-Zugehörigkeit) <br>☐ In Azure AD (Azure AD-Zugehörigkeit) gespeichert |
|**Gerätebetriebssystem-Updates**| ☐ Abgeschlossen |
|**Windows Store-Updates**| ☐ Automatisch <br> ☐ Handbuch |
|**Microsoft Teams-geplante Besprechung**| ☐ Bestätigungs-e-Mail erhalten <br> ☐ Besprechung wird auf dem Startbildschirm angezeigt <br>  ☐ Funktionen für die Verknüpfung mit einem Tastendruck <br> ☐ In der Lage, an Audio teilzunehmen <br> ☐ In der Lage, an Video teilzunehmen <br> ☐ Können den Bildschirm freigeben ||
|**Skype for Business-geplante Besprechung**| ☐ Bestätigungs-e-Mail erhalten <br> ☐ Besprechung wird auf dem Startbildschirm angezeigt <br> ☐ Ein-Finger-Join funktioniert ordnungsgemäß <br> ☐ In der Lage, an Audio teilzunehmen <br> ☐ In der Lage, an Video teilzunehmen <br> ☐ Können den Bildschirm freigeben <br> ☐ Kann Chatnachrichten senden/empfangen |
|**Geplante Besprechung, wenn Sie bereits eingeladen sind**| ☐ Besprechung abgelehnt |
|**Microsoft Teams Ad-hoc-Besprechung**| ☐ Andere Benutzer zur Arbeit einladen <br> ☐ In der Lage, an Audio teilzunehmen <br> ☐ In der Lage, an Video teilzunehmen <br> ☐ Können den Bildschirm freigeben |
|**Skype for Business-geplante Besprechung**| ☐ Andere Benutzer zur Arbeit einladen <br> ☐ In der Lage, an Audio teilzunehmen <br> ☐ In der Lage, an Video teilzunehmen <br> ☐ Können den Bildschirm freigeben <br> ☐ Kann Chatnachrichten senden/empfangen |
|**Microsoft Whiteboard**| ☐ Von Startseite starten <br> ☐ Start von Microsoft Teams | 
|**Eingehende Anrufe an Skype/Teams**| ☐ In der Lage, an Audio teilzunehmen<br>☐ In der Lage, an Video teilzunehmen <br> ☐ Können den Bildschirm freigeben <br> ☐ Kann Chatnachrichten senden/empfangen (nur Skype for Business) |
|**Eingehende Live-Videodatenströme**| ☐ Maximal 2 (Skype for Business) <br> ☐ Maximum 4 (Microsoft Teams) |
|**Verhalten des Microsoft Teams-Modus 0**| ☐ Skype for Business-Kachel auf der Startseite <br> ☐ Können an geplanten Skype for Business-Besprechungen teilnehmen (Skype UI) <br> ☐ Können an geplanten Teams-Besprechungen teilnehmen (Teams UI) |
|**Verhalten von Microsoft Teams im Modus 1**| Kachel "☐ Teams" auf "Willkommen/Start" <br> ☐ Können an geplanten Skype for Business-Besprechungen teilnehmen (Skype UI) <br> ☐ Können an geplanten Teams-Besprechungen teilnehmen (Teams UI) |
|**Verhalten von Microsoft Teams im Modus 2**| Kachel "☐ Teams" auf "Willkommen/Start" <br> ☐ Können an geplanten Teambesprechungen teilnehmen <br> ☐ Nicht teilnehmen an Skype for Business-Besprechungen |
