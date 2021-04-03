---
title: Neues in Windows10 Team2020-Update
description: Sehen Sie sich an, was im neuesten Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update, neu ist.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 14e08cf099ac441f7b2b3b76366406868ac6c056
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470423"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Neues in Windows10 Team2020-Update

Windows 10 Team 2020 Update bietet neben den neuesten Windows 10-Features wesentliche Verbesserungen bei der Gerätebereitstellung und Verwaltbarkeit.

##  <a name="deployment-and-manageability"></a>Bereitstellung und Verwaltbarkeit

- **Moderne Authentifizierung für Cloudgerätekonten**. Surface Hub unterstützt die exchange-Webdienste (EWS) und die ADAL-basierte Authentifizierung (Active Directory Authentication Library), um eine Verbindung mit Exchange herzustellen, sodass Kunden die Verwendung der Standardauthentifizierung nicht mehr verwenden können. Weitere Informationen finden Sie unter [Moderne Authentifizierung auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth).
- **Mehr als 20 neue und aktualisierte Richtlinieneinstellungen für die Verwaltung mobiler Geräte (Mobile Device Management, MDM).**  Diese Richtlinieneinstellungen bieten IT-Administratoren eine verbesserte Kontrolle über mehrere Geräteeinstellungen, einschließlich: App-Updates aus dem Microsoft Store, Drahtlose Projektionseinstellungen wie Miracast über die Infrastruktur, Netzwerkeinstellungen wie Quality-Of-Service und 802.1x verkabelte Authentifizierung sowie neue Datenschutz-/DSGVO-bezogenen Einstellungen. Zu den neuen Konfigurationsdienstanbietern (CsPs) gehören: 

  - [Konten-Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) 
  - [Firewall-CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) 
  - [RemoteWipe-Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 

Weitere Informationen finden Sie unter: 
- [CSPs, die im Microsoft Surface werden](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Verwalten von Surface Hub mit einem MDM-Anbieter](manage-settings-with-mdm-for-surface-hub.md)


##  <a name="azure-active-directory-joined-devices"></a>Azure Active Directory-beigetretene Geräte

- **Einmaliges Anmelden (Single Sign-On, SSO) für Azure AD-beigetretene Geräte**. Wenn sich Benutzer mit ihren Microsoft 365-Anmeldeinformationen bei "Meine Besprechungen und Dateien" anmelden, fließen ihre Benutzeranmeldeinformationen nahtlos von App zu App – einschließlich Microsoft 365-Erfahrungen im Browser.
- **Bedingter Zugriff (Conditional Access, CA) für Azure AD-beigetretene Geräte**.       IT-Administratoren können Sicherheitsrichtlinien auf Geräteebene auf ihrem in Azure AD beigetretenen Surface Hub bereitstellen, um den Zugriff auf Organisationsressourcen gemäß den Sicherheits- und Complianceanforderungen des Unternehmens zu steuern.
- **Unterstützung für nicht-globale Administratoren für Azure AD-beigetretene Geräte**. Kunden können einen differenzierteren Satz von Administratoren innerhalb ihrer Administratorhierarchie auswählen, um Surface Hub zu verwalten. Weitere Informationen finden Sie unter [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="browser-and-pen"></a>Browser und Stift

- **Unterstützung für das neue Microsoft Edge**. Microsoft Edge wurde für optimale Kompatibilitätsleistung, Sicherheit und Datenschutz neu erstellt. Weitere Informationen finden Sie unter [Installieren und Konfigurieren des neuen Microsoft Edge auf Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge).
- **Dual-Stift-Inking auf Surface Hub 2S**.   Benutzer können mit zwei Surface Hub 2-Stiften nebeneinander auf Surface Hub 2S arbeiten und whiteboarden und zusammenarbeiten. Die Firmwareupdates, die erforderlich sind, um die Freibefüllung mit zwei Stiften zu aktivieren, werden mit einem nachfolgenden Update veröffentlicht.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams standardmäßig installiert.**        Microsoft Teams ist als Standard-App für Besprechungen, Anrufe und Zusammenarbeit auf neuen Surface Hub-Geräten enthalten, die über MDM oder direkt auf Surface Hub mithilfe der Einstellungs-App geändert oder konfiguriert werden können. Weitere Informationen finden Sie unter [Deploy Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub).
- **Unterstützung für näherungshilfe bei Microsoft Teams**.  Die Näherungsbeschließung ermöglicht Es Benutzern, geplante Microsoft Teams-Anrufe auf einem in der Nähe gelegenen Surface Hub mit ihrem Laptop/Smartphone zu übernehmen oder eine aktuelle Besprechung nahtlos auf einen in der Nähe gelegenen Surface Hub zu überwechseln. Windows 10 Team 2020 Update fügt Unterstützung für die Mobile Geräteverwaltung (Mobile Device Management, MDM) hinzu, um den Näherungs beitritt zu konfigurieren. Weitere Informationen finden Sie unter: 

  - [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Microsoft Teams-Einstellungen auf Surface Hub verwalten](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Support für koordinierte Besprechungen mit Microsoft Teams**. In Besprechungsräumen, die über einen Surface Hub und ein Microsoft Teams Room-Gerät verfügen, oder Räume mit zwei Surface Hub-Geräten ermöglichen koordinierte Besprechungen Benutzern die einfache Nutzung beider Geräte während einer Microsoft Teams-Besprechung. Mit einem einzigen Tippen können Benutzer von einem Gerät aus an einer Besprechung teilnehmen und die Bildschirmfläche maximieren, indem sie Videofeeds auf einem Gerät und ein digitales Whiteboard oder Inhalte auf dem anderen Gerät anzeigen. Windows 10 Team 2020 Update fügt Unterstützung für die Mobile Geräteverwaltung (Mobile Device Management, MDM) zum Konfigurieren koordinierter Besprechungen hinzu, und das Feature wird anschließend als Microsoft Teams-Update über Microsoft Store.To weitere Informationen veröffentlicht. Weitere Informationen finden Sie unter Einrichten koordinierter Besprechungen mit [Microsoft Teams-Räumen](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)und Surface Hub .

## <a name="security"></a>Sicherheit

- **Kennwortlose Anmeldung mithilfe von FIDO2-Sicherheitsschlüsseln**     Mithilfe von FIDO2-Sicherheitsschlüsseln können sich Kunden schnell und einfach bei Surface Hub anmelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. In Kombination mit Sign-On (Single Sign-On, SSO) bietet dieses Feature eine schnelle und nahtlose Authentifizierung für Dateien, Apps und Websites während einer Besprechung. Weitere Informationen finden Sie unter [Configure passwordless sign-in on Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate).
- **Verbesserungen bei der kennwortlosen Anmeldung mithilfe von Microsoft Authenticator**.  Für Organisationen, die Azure AD verwenden, können Sich Benutzer mit der Microsoft Authenticator-App anmelden, ohne Benutzernamen und Kennwörter eingeben zu müssen. Darüber hinaus können sich Benutzer über ihre bevorzugten E-Mail-Aliase in Azure AD zusätzlich zu ihrem Benutzerprinzipalnamen (User Principal Name, UPN) anmelden. Weitere Informationen finden Sie unter [Sign in to Surface Hub with Microsoft Authenticator](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app).


## <a name="learn-more"></a>Weitere Informationen

- [Aktualisieren auf das Windows 10 Team-Rollout](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Windows 10 Team 2020 Update installieren](surface-hub-2020-update.md)  
 