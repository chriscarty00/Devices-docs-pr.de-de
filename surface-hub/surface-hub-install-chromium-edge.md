---
title: Das neue Microsoft Edge auf Surface Hub installieren und konfigurieren
description: Installieren und Konfigurieren der neuen Microsoft Edge auf Surface Hub.
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
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576725"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>Das neue Microsoft Edge auf Surface Hub installieren und konfigurieren

Windows 10 Team 2020 Update unterstützt die neue Microsoft Edge basierend auf Chromium (Version 85 und höher) als empfohlener Browser für Surface Hub 2S und Surface Hub (v1). In diesem Artikel wird erläutert, wie Sie den Browser mit einer von drei Methoden installieren: einem Bereitstellungspaket, Microsoft Intune oder einem Drittanbieter für die mobile Geräteverwaltung (Mobile Device Management, MDM).

> [!IMPORTANT]
> Standardmäßig sind Surface Hub Geräte mit Vorgängerversion von Microsoft Edge (Version 44) vorinstalliert. Nach der Installation [des 2020-Updates](surface-hub-2020-update.md)wird empfohlen, zum neuen Browser Microsoft Edge wechseln. Die Unterstützung [für Vorgängerversion von Microsoft Edge](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) endet am 9. März 2021.

> [!NOTE]
> Der Wischen von oben auf dem Bildschirm, um den Vollbildmodus zu beenden, erfordert zwei Finger mit der neuen Microsoft Edge. Die Vollbildaktion beenden ist auch im Kontextmenü verfügbar, das nach einer langen Touchtaste angezeigt wird.


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>Installieren Microsoft Edge mithilfe eines Bereitstellungspakets

1. Laden Sie von einem PC [das Microsoft Edge Bereitstellungspaket](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) in den Stammordner eines USB-Laufwerks herunter.
2. Fügen Sie das USB-Laufwerk in Surface Hub.
3. Öffnen Surface Hub **Sie** Einstellungen, und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
4. Navigieren Sie zu **Surface Hub** > **Geräteverwaltung**. Wählen Sie unter **Bereitstellungspakete** die Option **Bereitstellungspaket hinzufügen oder entfernen** aus.
5. Wählen Sie **Paket hinzufügen** aus.
6. Wählen Sie Microsoft Edge Bereitstellungspaket aus, und wählen Sie **Hinzufügen aus.**
7. Es wird eine Zusammenfassung der Änderungen angezeigt, die vom Bereitstellungspaket angewendet werden. Wählen Sie **Ja, hinzufügen** aus.
8. Warten Sie, bis die Microsoft Edge abgeschlossen ist. Navigieren Sie nach der Installation zum Menü Surface Hub Start, um auf die neue Microsoft Edge.              

> [!NOTE]
> Wenn eine neuere Version von Microsoft Edge verfügbar ist, wird sie automatisch aktualisiert.
 
## <a name="install-microsoft-edge-using-intune"></a>Installieren Microsoft Edge mithilfe von Intune
 
> [!NOTE]
> Um diese Installationsmethode zu verwenden, muss das Surface Hub mit Intune registriert und verwaltet werden. Weitere Informationen finden Sie unter [Manage Surface Hub 2S with MDM](manage-settings-with-mdm-for-surface-hub.md).
 

1. [Laden Sie das Microsoft Edge herunter.](https://www.microsoft.com/edge/business/download)
    - Verwenden der aktuellen Version des [Stable-Kanals](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(Version 85)**
    - Auswählen **Windows 64-Bit**
2. [Fügen Sie das Microsoft Edge als Line-of-Business-App zu Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - Wenn Sie die App Microsoft Edge Update, um automatische Updates für Microsoft Edge zu behandeln, konfigurieren Sie unbedingt die Einstellung App-Version ignorieren für den **App-Informationsbereich.** **** Wenn Sie diese Einstellung auf Ja **Microsoft Intune,** erzwingt die App-Version, die auf dem Gerät installiert ist, Surface Hub wird.

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>Installieren Microsoft Edge mithilfe eines Drittanbieters für MDM

1. [Laden Sie das Microsoft Edge von Microsoft herunter.](https://www.microsoft.com/edge/business/download)
    - Verwenden der aktuellen Version des [Stable-Kanals](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(Version 85)**
    - Auswählen **Windows 64-Bit**
2. Stage the Microsoft Edge installer on a hosted location, such as a local file share (\\server\share\MicrosoftEdgeEnterpriseX64.msi). Das Surface Hub gerät muss über die Berechtigung zum Zugriff auf den gehosteten Speicherort verfügen.
3. Verwenden [Sie enterpriseDesktopAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) über Ihren #A0 zum Installieren Microsoft Edge.

## <a name="configure-microsoft-edge"></a>Konfigurieren von Microsoft Edge

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>Standardrichtlinien Microsoft Edge Richtlinien für Surface Hub

Microsoft Edge ist mit den folgenden Richtliniensetttings vorkonfiguriert, um eine optimierte Benutzererfahrung für Surface Hub.
 
> [!TIP]
> Es wird empfohlen, den Standardwert für diese Richtlinieneinstellungen zu behalten.
 

| Richtlinieneinstellung                                                                                                   | Empfohlene Erfahrung                                                                                                                                                                                                                                               | Standardwert |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Importieren Sie nicht automatisch Datentypen und Einstellungen aus Vorgängerversion von Microsoft Edge. Dadurch wird verhindert, dass die Profile angemeldeter Benutzer mit freigegebenen Einstellungen aus der Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Lassen Microsoft Edge, dass die Prozesse auch nach dem Schließen des letzten Browserfensters im Hintergrund ausgeführt werden, sodass während einer Sitzung schneller auf Web-Apps zugegriffen werden kann.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Benutzer dürfen keine neuen Profile in einem Microsoft Edge. Dies vereinfacht das Browsen und die angemeldete Benutzererfahrung.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Ermöglicht es nur einem Benutzer, sich bei einer Microsoft Edge. Dies vereinfacht das Browsen und die angemeldete Benutzererfahrung.                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Ermöglicht Benutzern die Sign-On (Single Sign-On, SSO) in Microsoft Edge. Wenn ein Benutzer bei Surface Hub angemeldet ist, können seine Anmeldeinformationen zu unterstützten Websites fließen, ohne dass er sich erneut authentifizieren muss.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Verhindert, dass Benutzer, die keine Administratoren sind, neue Erweiterungen in Microsoft Edge. Verwenden Sie [ExtensionInstallForcelist,](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist)um eine Liste der standardmäßig zu installierende Erweiterungen zu konfigurieren. | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Blendet die erste Ausführungserfahrung und den Begrüßungsbildschirm aus, der normalerweise angezeigt wird, wenn Benutzer Microsoft Edge ausführen. Da Surface Hub ein freigegebenes Gerät ist, vereinfacht dies die Benutzeroberfläche.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deaktiviert den InPrivate-Modus. Da end session bereits Browserdaten löschen, vereinfacht dies das Browsen und die angemeldete Benutzererfahrung.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Zeigt die Office 365 auf neuen Registerkartenseiten an. Wenn ein Benutzer bei Surface Hub angemeldet ist, ermöglicht dies einen schnellen Zugriff auf seine Dateien und Inhalte auf Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Wenn ein Benutzer bei einem Surface Hub, wird ein nicht austauschbares Profil mit dem Organisationskonto erstellt. Dies vereinfacht die Sign-On (Single Sign-On).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Deaktiviert das Drucken in Microsoft Edge. Surface Hub unterstützt das Drucken nicht.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Ermöglicht Microsoft Edge proaktive Authentifizierung angemeldeter Benutzer mit Microsoft-Dienste. Dies vereinfacht die Sign-On (Single Sign-On).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Speichert Dateien automatisch im Ordner Downloads, anstatt Benutzer zu fragen, wo die Datei gespeichert werden soll. Dies vereinfacht die Browsererfahrung.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Bereitstellende progressive Web apps (PWAs) werden derzeit nicht auf dem Windows 10 Team unterstützt.  Beachten Sie außerdem, dass Microsoft Edge [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) nicht unterstützt wird, wenn Surface Hub. 

### <a name="configure-microsoft-edge-policy-settings"></a>Konfigurieren Microsoft Edge Richtlinieneinstellungen

Verwenden [Microsoft Edge Browserrichtlinien](https://docs.microsoft.com/deployedge/microsoft-edge-policies) zum Konfigurieren von Browsereinstellungen in Microsoft Edge. Diese Richtlinien können mit folgenden Maßnahmen angewendet werden:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Ihr bevorzugter Mobile Device Management (MDM)-Anbieter, der ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)unterstützt, oder
- [Bereitstellen von Paketen mithilfe der ADMX-Ingestion in Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### <a name="configure-microsoft-edge-updates"></a>Konfigurieren Microsoft Edge Updates

Standardmäßig wird Microsoft Edge automatisch aktualisiert. Verwenden [Microsoft Edge Updaterichtlinien](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) zum Konfigurieren von Einstellungen für Microsoft Edge Update.
Beachten Sie, Surface Hub die folgenden Updaterichtlinien Microsoft Edge unterstützt:

- **Allowsxs** – Bei Surface Hub Microsoft Edge stable-Kanal immer Vorgängerversion von Microsoft Edge.
- **CreateDesktopShortcut** – Surface Hub verwendet keine Desktopverknüpfungen.

> [!TIP]
>  Microsoft Edge erfordert zur Unterstützung der zugehörigen Features eine Internetverbindung. Stellen Sie [sicher, dass die erforderlichen Domänen-URLs](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) zur Liste Zulassen hinzugefügt werden, um die Kommunikation über Firewalls und andere Sicherheitsmechanismen sicherzustellen.

## <a name="related-links"></a>Verwandte Links

- [Dokumentation für Microsoft Edge](https://docs.microsoft.com/microsoft-edge/)

