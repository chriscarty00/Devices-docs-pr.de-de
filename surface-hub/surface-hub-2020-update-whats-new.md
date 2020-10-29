---
title: Neuerungen des Windows 10 Team 2020-Updates
description: Schauen Sie sich die Neuerungen im neuesten Update des Surface Hub-Betriebssystems, Windows 10 Team 2020-Update, an.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: Medium
ms.openlocfilehash: accdc8519ad90b5137e2b8f340290d9a7214e696
ms.sourcegitcommit: b4cfb718274fd632661f9112e9fd086a2ad45640
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "11143630"
---
# Neuerungen des Windows 10 Team 2020-Updates

Das Windows 10-Team 2020-Update bietet wichtige Verbesserungen bei der Gerätebereitstellung und-Verwaltbarkeit zusammen mit den neuesten Windows 10-Features.

##  Bereitstellung und Verwaltbarkeit

- **Moderne Authentifizierung für Cloud-Geräte Konten**. Surface Hub unterstützt Exchange-Webdienste (EWS) und Active Directory Authentication Library (Adal)-basierte Authentifizierung, um eine Verbindung mit Exchange herzustellen, sodass Kunden die Verwendung der Standardauthentifizierung als veraltet eingestuft werden. Ausführliche Informationen finden Sie unter [moderne Authentifizierung auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth).
- **Mehr als 20 neue und aktualisierte MDM-Richtlinien (Mobile Device Management)**.      Mit diesen Richtlinien können IT-Administratoren die Kontrolle über mehrere Geräteeinstellungen verbessern, einschließlich: APP-Updates aus dem Microsoft Store, drahtlos Projektions Einstellungen wie Miracast over Infrastructure, Netzwerkeinstellungen wie Quality-of-Service-und 802.1 x-kabelgebundene Authentifizierung sowie neue Einstellungen für den Datenschutz/dsgvo.

##  Azure Active Directory-verbundene Geräte

- **Einmaliges Anmelden (SSO) für mit Azure AD verbundene Geräte**. Wenn Benutzer sich mit Ihren Microsoft 365-Anmeldeinformationen für "meine Besprechungen und Dateien" anmelden, fließen Ihre Benutzeranmeldeinformationen nahtlos von APP zu app – einschließlich Microsoft 365-Erfahrungen im Browser.
- **Bedingter Zugriff (ca) für Azure AD-verbundene Geräte**.       IT-Administratoren können Sicherheitsrichtlinien auf Geräteebene für Ihren Azure AD-Joined Surface-Hub bereitstellen, um den Zugriff auf organisatorische Ressourcen in Übereinstimmung mit den Sicherheits-und Compliance-Anforderungen der Unternehmen zu kontrollieren.
- **Unterstützung für nicht-globale Administratoren für Azure AD-verbundene Geräte**.       Kunden können eine feinere Gruppe von Administratoren in ihrer Administrator Hierarchie auswählen, um Surface Hub zu verwalten. Weitere Informationen finden Sie unter [Administratorgruppenverwaltung](https://docs.microsoft.com/surface-hub/admin-group-management-for-surface-hub).


## Weitere Funktionen


- **Unterstützung für den neuen Microsoft Edge**. Microsoft Edge wurde für optimale Kompatibilitäts Leistung, Sicherheit und Datenschutz neu erstellt. Weitere Informationen finden Sie unter [Installieren und Konfigurieren des neuen Microsoft Edge auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge).
- **Microsoft Teams standardmäßig installiert**.        Microsoft Teams ist als Standard-Besprechungs-, Anruf-und Zusammenarbeits-App auf neuen Surface-Hub-Geräten enthalten, die über MDM oder direkt auf Surface Hub mithilfe der Einstellungs-APP geändert oder konfiguriert werden können. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub).
- **Support für Proximity Join mit Microsoft Teams**.  Mit Proximity Join können Benutzer in einem nahe gelegenen Surface-Hub mithilfe Ihres Laptops/Telefons geplante Microsoft Teams-Anrufe tätigen oder eine in-Progress-Besprechung nahtlos in einen nahe gelegenen Surface-Hub umleiten. Das Windows 10-Team 2020-Update fügt die Mobile Device Management (MDM)-Unterstützung hinzu, um Proximity Join zu konfigurieren, und das Feature wird anschließend als Microsoft Teams-Update über den Microsoft Store veröffentlicht.
- **Unterstützung für koordinierte Besprechungen mit Microsoft Teams**. In Besprechungsräumen mit einem Surface-Hub und einem Microsoft Teams-Raumgerät oder Leerzeichen mit zwei Surface-Hub-Geräten ermöglichen koordinierte Besprechungen Benutzern die einfache Nutzung beider Geräte während einer Microsoft Teams-Besprechung. Mit einem einzigen Fingertipp können Benutzer von einem Gerät aus an einer Besprechung teilnehmen und den Bildschirm "Real Estate" maximieren, indem Sie Video Feeds auf einem Gerät und ein digitales Whiteboard oder einen Inhalt auf der anderen Seite anzeigen. Das Windows 10-Team 2020-Update fügt die Mobile Device Management (MDM)-Unterstützung hinzu, um koordinierte Besprechungen zu konfigurieren, und das Feature wird anschließend als Microsoft Teams-Update über den Microsoft Store veröffentlicht.
- **Kenn Wort lose Anmeldung mithilfe von FIDO2-Sicherheitsschlüsseln**     Mithilfe von FIDO2-Sicherheitsschlüsseln können Kunden sich schnell und einfach bei Surface Hub anmelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. In Kombination mit Single Sign-On (SSO) bietet dieses Feature eine schnelle und nahtlose Authentifizierung für Dateien, Apps und Websites während einer Besprechung. Weitere Informationen finden Sie unter [Konfigurieren der Kenn Wort ungeschützten Anmeldung auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate).
- **Verbesserungen bei der Kenn Wort ungeschützten Anmeldung mit Microsoft Authenticator**.  Für Organisationen, die Azure AD verwenden, können Benutzer die Microsoft Authenticator-App verwenden, um sich anzumelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. Darüber hinaus können sich Benutzer zusätzlich zum Benutzerprinzipalnamen (User Principal Name, UPN) mit Ihren bevorzugten e-Mail-Aliasen in Azure AD anmelden. Weitere Informationen finden Sie unter [Anmelden bei Surface Hub mit Microsoft Authenticator](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app).
- **Doppel Stift-Freihandeingabe auf Surface Hub 2S**   Benutzer können über zwei Surface Hub 2-Stifte nebeneinander auf Surface Hub 2S Whiteboards und zusammenarbeiten. Die für die Aktivierung der Doppel Stift-Freihandeingabe erforderlichen Firmware-Updates werden mit einem nachfolgenden Update veröffentlicht.

 
 
 
