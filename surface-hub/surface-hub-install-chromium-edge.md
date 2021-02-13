---
title: Das neue Microsoft Edge auf Surface Hub installieren und konfigurieren
description: Installieren und konfigurieren Sie das neue Microsoft Edge auf Surface Hub.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 2bc11fb18137ce21cba27368e0c12bbb9e73a4c2
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327309"
---
# Das neue Microsoft Edge auf Surface Hub installieren und konfigurieren

Windows 10 Team 2020 Update unterstützt das neue Microsoft Edge basierend auf Chromium (Version 85 und höher) als empfohlenen Browser für Surface Hub 2S und Surface Hub (v1). In diesem Artikel wird erläutert, wie Sie den Browser mit einer von drei Methoden installieren: einem Bereitstellungspaket, Microsoft Intune oder einem Drittanbieter für die mobile Geräteverwaltung (Mobile Device Management, MDM).

> [!IMPORTANT]
> Surface Hub-Geräte sind standardmäßig mit Microsoft Edge Legacy (Version 44) vorinstalliert. Nach der Installation [des 2020-Updates](surface-hub-2020-update.md)wird empfohlen, zum neuen Microsoft #A0 zu wechseln. Die Unterstützung [für Microsoft Edge Legacy](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) endet am 9. März 2021.

## Installieren von Microsoft Edge mithilfe eines Bereitstellungspakets

1. Laden Sie von einem PC das [Microsoft Edge-Bereitstellungspaket](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) in den Stammordner eines USB-Laufwerks herunter.
2. Fügen Sie das USB-Laufwerk in Surface Hub ein.
3. Öffnen Sie auf Surface Hub **"Einstellungen",** und geben Sie ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
4. Navigieren Sie zu **Surface Hub** > **Geräteverwaltung**. Wählen Sie unter **Bereitstellungspakete** die Option **Bereitstellungspaket hinzufügen oder entfernen** aus.
5. Wählen Sie **Paket hinzufügen** aus.
6. Wählen Sie das Microsoft Edge-Bereitstellungspaket und dann **"Hinzufügen" aus.**
7. Es wird eine Zusammenfassung der Änderungen angezeigt, die für das Bereitstellungspaket gelten. Wählen Sie **Ja, hinzufügen** aus.
8. Warten Sie, bis die Microsoft Edge-Installation abgeschlossen ist. Navigieren Sie nach der Installation zum Surface Hub-Startmenü, um auf das neue Microsoft Edge zu zugreifen.              

> [!NOTE]
> Wenn eine neuere Version von Microsoft Edge verfügbar ist, wird sie automatisch aktualisiert.
 
## Installieren von Microsoft Edge mit Intune
 
> [!NOTE]
> Das Surface Hub-Gerät muss mit Intune registriert und verwaltet werden. Weitere Informationen finden Sie unter [Verwalten von Surface Hub 2S mit Microsoft Intune.](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [Laden Sie das Microsoft Edge-Installationsprogramm herunter.](https://www.microsoft.com/edge/business/download)
    - Verwenden der aktuellen Version des [Stable-Kanals](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(Version 85)**
    - Windows **64-Bit auswählen**
2. [Fügen Sie das Microsoft Edge-Installationsprogramm als Line-of-Business-App zu Microsoft Intune hinzu.](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - Wenn Sie microsoft Edge Update verwenden möchten, um automatische Updates **** für Microsoft Edge zu behandeln, müssen Sie die Einstellung "App-Version ignorieren" im Bereich **"App-Informationen"** konfigurieren. Wenn Sie diese Einstellung auf **"Ja"** setzen, erzwingt Microsoft Intune nicht die App-Version, die auf dem Surface Hub-Gerät installiert ist.

## Installieren von Microsoft Edge mithilfe eines Drittanbieters für mdm

1. [Laden Sie das Microsoft Edge-Installationsprogramm von Microsoft herunter.](https://www.microsoft.com/edge/business/download)
    - Verwenden der aktuellen Version des [Stable-Kanals](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(Version 85)**
    - Windows **64-Bit auswählen**
2. Stellen Sie das Microsoft Edge-Installationsprogramm an einem gehosteten Speicherort, z. B. einer lokalen Dateifreigabe (\\server\share\MicrosoftEdgeEnterpriseX64.msi). Das Surface Hub-Gerät muss über die Berechtigung zum Zugriff auf den gehosteten Speicherort verfügen.
3. Verwenden [Sie den #A0 (Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) über Ihren MDM-Anbieter, um Microsoft Edge zu installieren.

## Konfigurieren von Microsoft Edge

### Standardrichtlinien für Microsoft Edge für Surface Hub

Microsoft Edge ist mit den folgenden Richtlinieneinstellungen vorkonfiguriert, um eine optimierte Oberfläche für Surface Hub zu bieten.
 
> [!TIP]
> Es wird empfohlen, den Standardwert für diese Richtlinieneinstellungen zu behalten.
 

| Richtlinieneinstellung                                                                                                   | Empfohlene Erfahrung                                                                                                                                                                                                                                               | Standardwert |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Importieren Sie Datentypen und Einstellungen nicht automatisch aus der Vorgängerdatei von Microsoft Edge. Dadurch wird verhindert, dass die Profile angemeldeter Benutzer mit freigegebenen Einstellungen vom Surface Hub geändert werden.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Zulassen, dass Microsoft Edge-Prozesse auch nach dem Schließen des letzten Browserfensters im Hintergrund ausgeführt werden, sodass während einer Sitzung schneller auf Web Apps zugegriffen werden kann.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Benutzer dürfen keine neuen Profile in Microsoft Edge erstellen. Dies vereinfacht das Browsen und die angemeldete Benutzererfahrung.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Ermöglicht nur einem Benutzer die Anmeldung bei Microsoft Edge. Dies vereinfacht das Browsen und die angemeldete Benutzererfahrung.                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Ermöglicht Benutzern die Verwendung von single Sign-On (SSO) in Microsoft Edge. Wenn ein Benutzer bei Surface Hub angemeldet ist, können seine Anmeldeinformationen zu unterstützten Websites fließen, ohne dass er sich erneut authentifizieren muss.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Verhindert, dass Benutzer, die keine Administratoren sind, neue Erweiterungen in Microsoft Edge installieren. Verwenden Sie [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist), um eine Liste von Erweiterungen zu konfigurieren, die standardmäßig installiert werden sollen. | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Blendet die Erste Ausführung und den Begrüßungsbildschirm aus, der normalerweise angezeigt wird, wenn Benutzer Microsoft Edge zum ersten Mal ausführen. Da Surface Hub ein freigegebenes Gerät ist, vereinfacht dies die Benutzerfreundlichkeit.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deaktiviert den InPrivate-Modus. Da "Sitzung beenden" bereits Browserdaten löschen, vereinfacht dies das Browsen und die angemeldete Erfahrung.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Zeigt die Office 365-Feederfahrung auf neuen Registerkartenseiten an. Wenn ein Benutzer bei Surface Hub angemeldet ist, ermöglicht dies schnellen Zugriff auf seine Dateien und Inhalte in Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Wenn ein Benutzer bei Surface Hub angemeldet ist, wird ein nicht wechselbares Profil mit dem Organisationskonto erstellt. Dadurch wird die Single Sign-On (SSO) vereinfacht.                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Deaktiviert das Drucken in Microsoft Edge. Surface Hub unterstützt das Drucken nicht.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Ermöglicht Microsoft Edge die proaktive Authentifizierung angemeldeter Benutzer mit Microsoft-Diensten. Dadurch wird die Single Sign-On (SSO) vereinfacht.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Speichert Dateien automatisch im Ordner "Downloads", anstatt benutzer zu fragen, wo die Datei gespeichert werden soll. Dies vereinfacht die Browsererfahrung.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Bereitstellende progressive Web Apps (PWAs) werden derzeit unter dem Windows 10 Team-Betriebssystem nicht unterstützt.  Beachten Sie auch, dass die Microsoft Edge-Richtlinieneinstellung [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) auf Surface Hub nicht unterstützt wird. 

### Konfigurieren von Microsoft Edge-Richtlinieneinstellungen

Verwenden [Sie Microsoft Edge-Browserrichtlinien,](https://docs.microsoft.com/deployedge/microsoft-edge-policies) um Browsereinstellungen in Microsoft Edge zu konfigurieren. Diese Richtlinien können mit folgenden Maßnahmen angewendet werden:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Ihr bevorzugter Anbieter für die mobile Geräteverwaltung (Mobile Device Management, MDM), der die ADMX-Erfassung unterstützt,](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)oder
- [Bereitstellen von Paketen mithilfe der ADMX-Erfassung im Windows-Konfigurations-Designer.](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Konfigurieren von Microsoft Edge-Updates

Standardmäßig wird Microsoft Edge automatisch aktualisiert. Verwenden [Sie Microsoft Edge-Updaterichtlinien,](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) um Einstellungen für Microsoft Edge Update zu konfigurieren.
Beachten Sie, dass Surface Hub die folgenden Microsoft Edge-Updaterichtlinien nicht unterstützt:

- **Allowsxs** – Auf Surface Hub ersetzt der Microsoft Edge Stable-Kanal immer Microsoft Edge Legacy.
- **CreateDesktopShortcut** – Surface Hub verwendet keine Desktopverknüpfungen.

> [!TIP]
>  Microsoft Edge erfordert zur Unterstützung der zugehörigen Features eine Internetverbindung. Stellen Sie sicher, [dass die erforderlichen Domänen-URLs](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) der Liste "Zulassen" hinzugefügt werden, um die Kommunikation über Firewalls und andere Sicherheitsmechanismen sicherzustellen.

## Verwandte Links

- [Dokumentation für Microsoft Edge](https://docs.microsoft.com/microsoft-edge/)

