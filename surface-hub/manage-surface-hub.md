---
title: Verwalten von Microsoft Surface Hub
description: Verwalten des Surface Hub nach Abschluss des Programms für die Erstausführung
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub verwalten
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 5e7fca007549d8804a756ef2a042f092f0acb1c3
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387442"
---
# <a name="manage-microsoft-surface-hub"></a>Verwalten von Microsoft Surface Hub

Nach der erst eingerichteten Microsoft Surface Hub können Geräteeinstellungen und -konfigurationen auf verschiedene Weise geändert oder geändert werden:

- **Lokale Verwaltung** – Jeder Surface Hub kann mithilfe der **Einstellungs**-App auf dem Gerät lokal konfiguriert werden. Um die Änderung der Einstellungen durch nicht autorisierte Benutzer zu verhindern, sind zum Öffnen der Einstellungs-App Administratoranmeldeinformationen erforderlich. Weitere Informationen finden Sie unter [Lokale Verwaltung von Surface Hub-Einstellungen](local-management-surface-hub-settings.md).
- **Remoteverwaltung** – Surface Hub ermöglicht es IT-Administratoren, Einstellungen und Richtlinien mithilfe eines Mobile Device Management (MDM)-Anbieters zu verwalten, z. B. Microsoft Intune, Microsoft Endpoint Configuration Manager und andere Drittanbieter. Darüber hinaus können Administratoren Surface Hubs mithilfe von Azure Monitor überwachen.  Weitere Informationen finden Sie unter Verwalten von Einstellungen [mit einem MDM-Anbieter](manage-settings-with-mdm-for-surface-hub.md)und Überwachen von [Surface Hubs mit Azure Monitor, um deren Integrität nachverfolgt zu werden.](https://docs.microsoft.com/azure/azure-monitor/insights/surface-hubs) 

> [!NOTE]
> Diese Verwaltungsmethoden schließen sich nicht gegenseitig aus. Geräte können sowohl lokal als auch remote verwaltet werden, wenn Sie dies möchten. MdM-Richtlinien und -Einstellungen überschreiben jedoch lokale Änderungen, wenn Surface Hub mit dem Verwaltungsserver synchronisiert wird. 

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Informationen zum Verwalten und Aktualisieren von Surface Hub.

| Thema | Beschreibung |
| ----- | ----------- |
| [Surface Hub-Remoteverwaltung](remote-surface-hub-management.md) |Themen, die sich auf die Remoteverwaltung des Surface Hub beziehen. Enthalten Informationen zum Installieren von Apps, zum Verwalten von Einstellungen mit MDM und zum Überwachen mithilfe von Operations Management Suite. |
| [Verwalten von Surface Hub-Einstellungen](manage-surface-hub-settings.md) |Themen, die sich auf die Verwaltung von Surface Hub-Einstellungen beziehen: Barrierefreiheit, Gerätekonto, Gerätezurücksetzung, vollqualifizierter Domänenname, Windows Update-Einstellungen und Drahtlosnetzwerk. |
| [Installieren von Apps auf Surface Hub]( https://technet.microsoft.com/itpro/surface-hub/install-apps-on-surface-hub) | Administratoren können Apps entweder aus dem Microsoft Store oder dem Microsoft Store für Unternehmen installieren.|
[Konfigurieren des Surface Hub-Startmenüs](surface-hub-start-menu.md) | Verwenden Sie MDM, um das Startmenü für Surface Hub benutzerdefiniert anzupassen.
| [Einrichten und Verwenden von Microsoft Whiteboard](whiteboard-collaboration.md)  | Das aktuelle Update von Microsoft Whiteboard kann zwei Surface Hubs für die Zusammenarbeit in Echtzeit auf dem gleichen Board enthalten.   |
| [Beenden einer Besprechung mit Sitzung beenden](https://technet.microsoft.com/itpro/surface-hub/finishing-your-surface-hub-meeting) | Am Ende einer Besprechung können Benutzer auf **Sitzung beenden** tippen, um vertrauliche Daten zu entfernen und das Gerät für die nächste Besprechung vorzubereiten.|
| [Melden Sie sich bei Surface Hub mit Microsoft Authenticator an](surface-hub-authenticator-app.md) | Sie können sich auf einem Surface Hub ohne Kennwort mithilfe der Microsoft Authenticator-App auf Android und iOS anmelden.   |
| [Speichern des BitLocker-Schlüssels](https://technet.microsoft.com/itpro/surface-hub/save-bitlocker-key-surface-hub) | Jeder Surface Hub wird automatisch mit BitLocker-Laufwerkverschlüsselungssoftware eingerichtet. Microsoft empfiehlt nachdrücklich, die BitLocker-Wiederherstellungsschlüssel unbedingt zu sichern.|
| [Verbinden anderer Geräte und deren Anzeige mit Surface Hub](https://technet.microsoft.com/itpro/surface-hub/connect-and-display-with-surface-hub) | Sie können andere Geräte mit Ihrem Surface Hub verbinden, um Inhalte anzuzeigen.|
| [Miracast auf vorhandenen Funknetzwerken oder LAN](miracast-over-infrastructure.md) | Sie können Miracast auf Ihrem Drahtlosnetzwerk oder LAN mit Surface Hub verwenden. |
 [Aktivieren Sie 802.1x kabelgebundene Authentifizierung](enable-8021x-wired-authentication.md) | Die MDM-Richtlinien für die 802.1x kabelgebundene Authentifizierung wurde auf Surface Hub-Geräten aktiviert. 
| [Verwenden eines Raumsteuerungssystems](https://technet.microsoft.com/itpro/surface-hub/use-room-control-system-with-surface-hub) | Raumsteuerungssysteme können mit Microsoft Surface Hub verwendet werden.|
[Verwenden des Wiederherstellungstools für Surface Hub](surface-hub-recovery-tool.md) | Verwenden Sie das Surface Hub-Wiederherstellungstool, um die Surface Hub-SSD neu zu abbilden.
[Ersatz-SSD für Surface Hub](surface-hub-ssd-replacement.md) | Erfahren Sie, wie Sie das Festkörperlaufwerk in Ihrem Surface Hub entfernen und ersetzen.

## <a name="related-topics"></a>Verwandte Themen

- [Anzeigen des Power BI-Darstellungsmodus auf Surface Hub und Windows10](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
