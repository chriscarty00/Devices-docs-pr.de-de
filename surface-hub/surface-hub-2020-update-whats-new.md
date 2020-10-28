---
title: Neuerungen im Windows 10 Team 2020-Update
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
ms.openlocfilehash: afc583ddf2d3aba9f487a3238e2b64d6e5876ada
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142937"
---
# Neuerungen im Windows 10 Team 2020-Update

Das Windows 10-Team 2020-Update bietet wichtige Verbesserungen bei der Gerätebereitstellung und-Verwaltbarkeit zusammen mit den neuesten Windows 10-Features.

##  Bereitstellung und Verwaltbarkeit

- Moderne Authentifizierung für Cloud-Geräte Konten: Surface Hub unterstützt Exchange-Webdienste (EWS) und Active Directory Authentication Library (Adal)-basierte Authentifizierung zum Herstellen einer Verbindung mit Exchange, sodass Kunden die Verwendung der Standardauthentifizierung als veraltet eingestuft werden. Ausführliche Informationen finden Sie unter [moderne Authentifizierung auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth).
- Mehr als 20 neue und aktualisierte MDM-Richtlinien (Mobile Device Management): mit diesen Richtlinien können IT-Administratoren die Kontrolle über mehrere Geräteeinstellungen verbessern, einschließlich: APP-Updates aus dem Microsoft Store, drahtlos Projektions Einstellungen wie Miracast over Infrastructure, Netzwerkeinstellungen wie Quality-of-Service-und 802.1 x-kabelgebundene Authentifizierung sowie neue Einstellungen für den Datenschutz/dsgvo.

##  Azure Active Directory-verbundene Geräte

- Einmaliges Anmelden (SSO) für mit Azure AD verbundene Geräte. Wenn Benutzer sich mit Ihren Microsoft 365-Anmeldeinformationen für "meine Besprechungen und Dateien" anmelden, fließen Ihre Benutzeranmeldeinformationen nahtlos von APP zu app – einschließlich Microsoft 365-Erfahrungen im Browser.
- Bedingter Zugriff (ca) für Azure AD-verbundene Geräte.        IT-Administratoren können Sicherheitsrichtlinien auf Geräteebene für Ihren Azure AD-Joined Surface-Hub bereitstellen, um den Zugriff auf organisatorische Ressourcen in Übereinstimmung mit den Sicherheits-und Compliance-Anforderungen der Unternehmen zu kontrollieren.
- Unterstützung für nicht-globale Administratoren für Azure AD-verbundene Geräte.        Kunden können eine feinere Gruppe von Administratoren in ihrer Administrator Hierarchie auswählen, um Surface Hub zu verwalten. Weitere Informationen finden Sie unter [Administratorgruppenverwaltung](https://docs.microsoft.com/surface-hub/admin-group-management-for-surface-hub).


## Weitere Funktionen


- Unterstützung für den neuen Microsoft Edge. Microsoft Edge wurde für optimale Kompatibilitäts Leistung, Sicherheit und Datenschutz neu erstellt. Weitere Informationen finden Sie unter [Installieren und Konfigurieren des neuen Microsoft Edge auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge).
- Bereitstellen von Microsoft Teams schnellere Microsoft Teams ist als standardmäßige Besprechungs-, Anruf-und Zusammenarbeits-App auf neuen Surface-Hub-Geräten enthalten, die über MDM oder direkt auf Surface Hub mithilfe der Einstellungs-APP geändert oder konfiguriert werden können. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub).
- Support für Proximity Join mit Microsoft Teams Proximity Join ermöglicht es Benutzern, geplante Microsoft Teams-Anrufe auf einem nahe gelegenen Surface-Hub mithilfe Ihres Laptops/Telefons zu führen oder eine in-Progress-Besprechung nahtlos in einen nahe gelegenen Surface-Hub umzuschalten. Das Windows 10-Team 2020-Update fügt die Mobile Device Management (MDM)-Unterstützung hinzu, um Proximity Join zu konfigurieren, und das Feature wird anschließend als Microsoft Teams-Update über den Microsoft Store veröffentlicht.
- Unterstützung für koordinierte Besprechungen mit Microsoft Teams in Besprechungsräumen mit einem Surface-Hub und einem Microsoft Teams-Raumgerät oder mit Räumen mit zwei Surface-Hub-Geräten, koordinierte Besprechungen ermöglichen Benutzern, auf einfache Weise beide Geräte während einer Microsoft Teams-Besprechung zu nutzen. Mit einem einzigen Fingertipp können Benutzer von einem Gerät aus an einer Besprechung teilnehmen und den Bildschirm "Real Estate" maximieren, indem Sie Video Feeds auf einem Gerät und ein digitales Whiteboard oder einen Inhalt auf der anderen Seite anzeigen. Das Windows 10-Team 2020-Update fügt die Mobile Device Management (MDM)-Unterstützung hinzu, um koordinierte Besprechungen zu konfigurieren, und das Feature wird anschließend als Microsoft Teams-Update über den Microsoft Store veröffentlicht.
- Ohne kennwortanmeldung mithilfe von FIDO2-Sicherheitsschlüsseln mithilfe von FIDO2-Sicherheitsschlüsseln können Kunden sich schnell und einfach bei Surface Hub anmelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. In Kombination mit Single Sign-On (SSO) bietet dieses Feature eine schnelle und nahtlose Authentifizierung für Dateien, Apps und Websites während einer Besprechung. Weitere Informationen finden Sie unter [Konfigurieren der Kenn Wort ungeschützten Anmeldung auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate).
- Verbesserungen bei der kennwortbasierten Anmeldung mit Microsoft Authenticator für Organisationen, die Azure AD verwenden, können Benutzer die Microsoft Authenticator-App verwenden, um sich anzumelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. Darüber hinaus können sich Benutzer zusätzlich zum Benutzerprinzipalnamen (User Principal Name, UPN) mit Ihren bevorzugten e-Mail-Aliasen in Azure AD anmelden. Weitere Informationen finden Sie unter [Anmelden bei Surface Hub mit Microsoft Authenticator](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app).
- Doppel Stift-Freihandeingabe auf Surface Hub 2S-Benutzern können Whiteboards und die Zusammenarbeit nebeneinander auf Surface Hub 2S mithilfe von zwei Surface Hub 2-stiften erfolgen. Die für die Aktivierung der Doppel Stift-Freihandeingabe erforderlichen Firmware-Updates werden mit einem nachfolgenden Update veröffentlicht.

 
 
 
