---
title: Neuerungen des Windows 10 Team 2020-Updates
description: Sehen Sie sich die Neuigkeiten im neuesten Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update, an.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: f87b8f084b8731bfb329b6c52403d565bca03e3e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312051"
---
# Neuerungen des Windows 10 Team 2020-Updates

Windows 10 Team 2020 Update bietet wesentliche Verbesserungen bei der Gerätebereitstellung und Verwaltbarkeit zusammen mit den neuesten Windows 10-Features.

##  Bereitstellung und Verwaltbarkeit

- **Moderne Authentifizierung für Cloudgerätekonten.** Surface Hub unterstützt die auf Exchange Web Services (EWS) und Active Directory Authentication Library (ADAL) basierende Authentifizierung, um eine Verbindung mit Exchange herzustellen, sodass Kunden die Verwendung der Standardauthentifizierung nicht mehr verwenden können. Weitere Informationen finden Sie unter ["Moderne Authentifizierung" auf Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)
- **Mehr als 20 neue und aktualisierte Richtlinien für die mobile Geräteverwaltung (Mobile Device Management, MDM).**      Diese Richtlinien bieten IT-Administratoren eine verbesserte Kontrolle über mehrere Geräteeinstellungen, einschließlich: App-Updates aus dem Microsoft Store, Drahtlose Projektionseinstellungen wie Miracast über die Infrastruktur, Netzwerkeinstellungen wie Quality-of-Service und 802.1x verkabelte Authentifizierung sowie neue Datenschutz-/DSGVO-bezogene Einstellungen. Weitere Informationen finden Sie unter: 
- [Verwalten von Surface Hub 2S mit Microsoft Intune](surface-hub-2s-manage-intune.md).
- [Richtlinien-Konfigurationsdienstanbieter, die von MicrosoftSurface Hub unterstützt werden](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  Azure Active Directory-beigetretene Geräte

- **Einmaliges Anmelden (Single Sign-On, SSO) für Geräte,** die mit Azure AD verbunden sind. Wenn sich Benutzer mit ihren Microsoft 365-Anmeldeinformationen bei "Meine Besprechungen und Dateien" anmelden, fließen ihre Benutzeranmeldeinformationen nahtlos von App zu App – einschließlich Microsoft 365-Erfahrungen im Browser.
- **Bedingter Zugriff (Conditional Access, CA) für Azure AD-geräte.**       It admins can deploy device-level security policies to their Azure AD joined Surface Hub to control access to organizational resources in accordance with corporate security and compliance requirements.
- **Unterstützung für nicht-globale Administratoren für Geräte, die Azure AD beigetreten sind.** Kunden können eine präzisere Gruppe von Administratoren innerhalb ihrer Administratorhierarchie auswählen, um Surface Hub zu verwalten. Weitere Informationen finden Sie unter ["Konfigurieren von nicht globalen Administratorkonten auf Surface Hub 2S".](surface-hub-2s-nonglobal-admin.md)


## Browser und Stift

- **Unterstützung für das neue Microsoft Edge**. Microsoft Edge wurde für optimale Kompatibilitätsleistung, Sicherheit und Datenschutz neu erstellt. Weitere Informationen finden Sie unter ["Installieren und Konfigurieren des neuen Microsoft Edge auf Surface Hub".](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- - **Dual-Stift-Inking auf Surface Hub 2S**.   Benutzer können Whiteboards verwenden und mit zwei Surface Hub 2-Stiften nebeneinander auf Surface Hub 2S zusammenarbeiten. Die Firmwareupdates, die erforderlich sind, um die Frei-/Schreibfunktion mit zwei Stiften zu aktivieren, werden mit einem nachfolgenden Update veröffentlicht.

## Microsoft Teams  

- **Microsoft Teams wird standardmäßig installiert.**        Microsoft Teams ist als standardmäßige App für Besprechungen, Anrufe und Zusammenarbeit auf neuen Surface Hub-Geräten enthalten, die über MDM oder direkt auf Surface Hub mithilfe der App "Einstellungen" geändert oder konfiguriert werden können. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub).
- **Unterstützung für näherungs beitritt mit Microsoft Teams**.  Bei der Näherung können Benutzer geplante Microsoft Teams-Anrufe auf einem Surface Hub in der Nähe mit ihrem Laptop/Telefon oder nahtlos auf einen surface Hub in der Nähe umschließen. Windows 10 Team 2020 Update bietet unterstützung für die mobile Geräteverwaltung (Mobile Device Management, MDM), um den Näherungs beitritt zu konfigurieren. Weitere Informationen finden Sie unter: 

  - [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Microsoft Teams-Einstellungen auf Surface Hub verwalten](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Unterstützung für koordinierte Besprechungen mit Microsoft Teams**. In Besprechungsräumen, die über einen Surface Hub und ein Microsoft Teams -Raumgerät verfügen, oder räume mit zwei Surface Hub-Geräten ermöglichen koordinierte Besprechungen Benutzern, während einer Microsoft Teams-Besprechung auf einfache Weise beide Geräte zu nutzen. Mit einem einzigen Tippen können Benutzer von einem Gerät aus an einer Besprechung teilnehmen und die Bildschirmfläche maximieren, indem sie Videofeeds auf einem Gerät und ein digitales Whiteboard oder Inhalte auf dem anderen Gerät anzeigen. Windows 10 Team 2020 Update fügt Unterstützung für die mobile Geräteverwaltung (Mobile Device Management, MDM) hinzu, um koordinierte Besprechungen zu konfigurieren. Das Feature wird anschließend als Microsoft Teams Update über Microsoft Store.To weitere Informationen veröffentlicht. Weitere Informationen finden Sie unter Einrichten koordinierter Besprechungen mit Microsoft Teams Rooms und [Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)

## Sicherheit

- **Kennwortlose Anmeldung mithilfe von FIDO2-Sicherheitsschlüsseln**     Mithilfe von FIDO2-Sicherheitsschlüsseln können sich Kunden schnell und einfach bei Surface Hub anmelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. In Kombination mit Sign-On (Single Sign-On, SSO) ermöglicht dieses Feature eine schnelle und nahtlose Authentifizierung für Dateien, Apps und Websites während einer Besprechung. Weitere Informationen finden Sie unter [Konfigurieren der kennwortlosen Anmeldung auf Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)
- **Verbesserungen bei der kennwortlosen Anmeldung mit Microsoft Authenticator.**  Für Organisationen, die Azure AD verwenden, können Sich Benutzer mit der Microsoft Authenticator-App anmelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. Darüber hinaus können sich Benutzer mit ihren bevorzugten E-Mail-Aliasen in Azure AD zusätzlich zu ihrem Benutzerprinzipalnamen (UPN) anmelden. Weitere Informationen finden Sie unter ["Anmelden bei Surface Hub mit Microsoft Authenticator".](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## Weitere Informationen

- [Aktualisieren auf das Windows 10 Team-Rollout](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Windows 10 Team 2020 Update installieren](surface-hub-2020-update.md)  
 