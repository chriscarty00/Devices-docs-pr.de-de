---
title: Verwalten von Einstellungen mit einem MDM-Anbieter (Surface Hub)
description: Microsoft Surface Hub bietet eine Unternehmensverwaltungslösung, mit der IT-Administratoren Richtlinien und Geschäftsanwendungen auf diesen Geräten mit einer Lösung für die mobile Geräteverwaltung (Mobile Device Management, MDM) verwalten können.
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: mobile Geräteverwaltung, MDM, Richtlinien verwalten
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: d96f5748533a2d83a0ca68cd42a0663506514d36
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834251"
---
# Verwalten von Einstellungen mit einem MDM-Anbieter (Surface Hub)

Surface Hub und andere Windows10-Geräte ermöglichen IT-Administratoren das Verwalten von Einstellungen und Richtlinien mithilfe eines Anbieters für die mobile Geräteverwaltung (Mobile Device Management, MDM). Eine integrierte Verwaltungskomponente kommuniziert mit dem Verwaltungsserver, sodass keine zusätzlichen Clients auf dem Gerät installiert werden müssen. Weitere Informationen finden Sie unter [Mobile Geräteverwaltung für Windows 10](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx) .

Surface Hub wurde mit den Microsoft-Erstanbieter-MDM-Anbietern validiert:
- Eigenständiges Microsoft Intune
- Lokales MDM mit Microsoft Endpoint Configuration Manager

Sie können Surface Hub-Geräte auch mithilfe von MDM-Lösungen von Drittanbietern verwalten, die mithilfe des MDM-Protokolls mit Windows10 kommunizieren können.

## <a href="" id="enroll-into-mdm"></a>Registrieren eines Surface Hub bei MDM
Sie können Ihre Surface Hubs mithilfe von Massen-, manuellen oder automatischen Registrierungen registrieren.

### Massenregistrierung
**So konfigurieren Sie die Massenregistrierung**
- Surface Hub unterstützt den [Konfigurationsdienstanbieter (CSP) für Bereitstellungen](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) für MDM- Massenregistrierungen. Weitere Informationen finden Sie unter [Windows10-Massenregistrierung](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
– ODER –
- Wenn Sie über eine lokale Microsoft Endpoint Configuration Manager-Infrastruktur verfügen, lesen Sie so wird es [gemacht: Massenregistrierung von Geräten mit der lokalen Verwaltung mobiler Geräte im Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### Manuelle Registrierung
**So konfigurieren Sie die manuelle Registrierung**
1. Öffnen Sie **Einstellungen** auf dem Surface Hub.
2. Geben Sie bei Aufforderung die Geräteadministrator-Anmeldeinformationen ein.
3. Wählen Sie **Dieses Gerät** aus, und navigieren Sie zu **Geräteverwaltung**.
4. Wählen Sie unter **Geräteverwaltung** **+ Geräteverwaltung** aus.
5. Folgen Sie den Anweisungen im Dialogfeld, um eine Verbindung mit Ihrem MDM-Anbieter herzustellen.

### Automatische Registrierung über Azure Active Directory Join

Surface Hub unterstützt jetzt die Möglichkeit zur automatischen Registrierung in InTune, indem das Gerät mit Azure Active Directory verknüpft wird. 

Der erste Schritt besteht darin, die automatische MDM-Registrierung einzurichten. Weitere Informationen finden Sie unter [Aktivieren der automatischen Registrierung von Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

Wenn Geräte während der ersten Ausführung eingerichtet werden, wählen Sie dann die Option zum beitreten zu Azure Active Directory aus, siehe [Einrichten von Administratoren für dieses Gerät](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page) .

## Verwalten von Surface Hub-Einstellungen mit MDM

Für die Verwaltung einiger [Surface Hub-CSP-Einstellungen](#supported-surface-hub-csp-settings) und [Windows10-Einstellungen](#supported-windows-10-settings) können Sie MDM verwenden. Abhängig vom verwendeten MDM-Anbieter können Sie diese Einstellungen möglicherweise über eine integrierte Benutzeroberfläche oder durch die Bereitstellung von benutzerdefiniertem SyncML festlegen. Microsoft InTune und Microsoft Endpoint Configuration Manager stellen integrierte Erfahrungen bereit, mit denen Sie Richtlinienvorlagen für Surface Hub erstellen können. Lesen Sie die Dokumentation Ihres MDM-Anbieters, um mehr über das Erstellen und Bereitstellen von SyncML zu erfahren.

### Unterstützte Surface Hub-CSP-Einstellungen

Sie können die Surface Hub-Einstellungen in der folgenden Tabelle mit MDM konfigurieren. In der Tabelle wird angegeben, ob die Einstellung für Microsoft InTune, Microsoft Endpoint Configuration Manager oder SyncML unterstützt wird.

Weitere Informationen finden Sie unter [SurfaceHub-Konfigurationsdienstanbieter](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Einstellung                                      |                                                    Knoten im SurfaceHub-CSP                                                    |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Wartungsstunden                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Ja                        |                       Ja                       |             Ja             |
|              Automatisches Aktivieren des Bildschirms mittels Bewegungssensoren               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Ja                        |                       Ja                       |             Ja             |
|                      Anfordern einer PIN für die drahtlose Projektion                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Ja                        |                       Ja                       |             Ja             |
|                            Aktivieren der drahtlosen Projektion                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Ja                        | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                 Miracast-Kanal für die drahtlose Projektion                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Ja                        | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|              Verknüpfung mit dem Operations Management Suite-Arbeitsbereich               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Ja                        | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                         Hintergrundbild der Willkommensseite                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Ja                        | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               Anzeige von Besprechungsinformationen auf der Willkommensseite                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Ja                        | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.] (#example-Manage-Surface-Hub-Settings-with-Microsoft-Endpoint-Configuration-Manager |             Ja             |
|                      Anzeigename für die drahtlose Projektion                       |                                                     Properties/FriendlyName                                                      | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                   Gerätekonto einschließlich Kennwortrotation                    | DeviceAccount/*`<name_of_policy>`* <br> Weitere Informationen finden Sie unter [SurfaceHub-CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        Nein                        |                       Nein                        |             Ja             |
|                               Skype-Domäne angeben                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               App "Verbinden" bei Initiieren der Projektion automatisch starten               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                                Standardlautstärke festlegen                                |                                                     Properties/DefaultVolume                                                     |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                                Bildschirmtimeout festlegen                                |                                                     Properties/ScreenTimeout                                                     |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                               Sitzungstimeout festlegen                                |                                                    Properties/SessionTimeout                                                     |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                                Timeout für Standby festlegen                                 |                                                     Properties/SleepTimeout                                                      |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                   Fortsetzen der Sitzung zulassen, nachdem sich der Bildschirm im Leerlauf befand                   |                                                  Properties/AllowSessionResume                                                   |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|             Zulassen, dass das Gerätekonto für die Proxyauthentifizierung verwendet wird             |                                                  Properties/AllowAutoProxyAuth                                                   |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
| Automatisches Auffüllen des Anmeldedialogfelds mit eingeladenen Teilnehmern aus geplanten Besprechungen deaktivieren |                                               Properties/DisableSignInSuggestions                                                |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|              Funktion "My meetings and files" im Startmenü deaktivieren               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    Ja </br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                     Festlegen von LanProfile für die verkabelte 802.1x-Authentifizierung                     |                                                         Dot3/LanProfile                                                          | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                    Festlegen von EapUserData für die verkabelte 802.1x-Authentifizierung                     |                                                         Dot3/EapUserData                                                         | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

### Unterstützte Windows10-Einstellungen

Zusätzlich zu den Surface Hub-spezifischen Einstellungen sind zahlreiche Einstellungen verfügbar, die allen Windows10-Geräten gemeinsam sind. Diese Einstellungen werden in der [Referenz zum Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) definiert. 

Die folgenden Tabelle enthalten Informationen zu Windows10-Einstellungen, die für Surface Hub überprüft wurden. Es gibt jeweils eine Tabelle mit den Einstellungen für folgende Bereiche: Sicherheit, Browser, Windows-Updates, Windows Defender, Remoteneustart, Zertifikate und Protokolle. Jede Tabelle gibt an, ob die Einstellung mit Microsoft InTune, Microsoft Endpoint Configuration Manager oder SyncML unterstützt wird.

#### Sicherheitseinstellungen

|      Einstellung       |                                            Details                                             |                                                                          CSP-Referenz                                                                           |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Bluetooth zulassen   |                      Lassen Sie diese Einstellung aktiviert, um Bluetooth-Peripheriegeräte zu unterstützen.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Ja. <br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
| Bluetooth-Richtlinien | Verwenden Sie diese Einstellung, um den Namen des Bluetooth-Geräts festzulegen und Werbung, Erkennung und automatische Kopplung zu blockieren. |                     Bluetooth/*`<name of policy>`* <br> Weitere Informationen finden Sie unter [Richtlinien-CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    Ja. <br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|    Kamera zulassen    |                           Lassen Sie diese Einstellung aktiviert, um Skype for Business verwenden zu können.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Ja. <br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|   Standort zulassen   |                        Lassen Sie diese Einstellung aktiviert, um Apps wie Karten zu unterstützen.                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Ja. <br> .                    | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|  Telemetrie zulassen   |                    Lassen Sie diese Einstellung aktiviert, um Microsoft bei der Verbesserung von Surface Hub zu unterstützen.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Ja. <br>                     | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|  USB-Laufwerke zulassen  |                     Lassen Sie diese Einstellung aktiviert, um USB-Laufwerke auf Surface Hub zu unterstützen.                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden. 

#### Browsereinstellungen

|                          Einstellung                          |                                                                        Details                                                                        |                                                                             CSP-Referenz                                                                              |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Startseiten                         |                                               Verwenden Sie diese Einstellung, um die Standardstartseiten in Microsoft Edge zu konfigurieren.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                       Cookies zulassen                       |                    Surface Hub löscht Cookies am Ende einer Sitzung automatisch. Verwenden Sie diese Einstellung, um innerhalb einer Sitzung Cookies zu blockieren.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                   Entwicklertools zulassen                   |                                                   Verwenden Sie diese Einstellung, um zu verhindern, dass Benutzer F12-Entwicklungstools verwenden.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                    Nicht verfolgen (Do not track) zulassen                     |                                                          Verwenden Sie diese Einstellung, um Do Not Track-Header zu verwenden.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                       Popups zulassen                       |                                                         Verwenden Sie diese Einstellung, um Popupfenster im Browser zu blockieren.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                 Suchvorschläge zulassen                  |                                                  Verwenden Sie diese Einstellung, um Suchvorschläge in der Adressleiste zu blockieren.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|                     Windows Defender-SmartScreen zulassen                     |                                                       Aktivieren Sie diese Option, um den SmartScreen-Windows Defender zu aktivieren.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
| Verhindern, dass Windows Defender-SmartScreen-Warnungen für Websites ignoriert werden |     Verwenden Sie für zusätzliche Sicherheit, um zu verhindern, dass Benutzer Windows Defender-SmartScreen-Warnungen ignorieren, und verhindern Sie, dass Sie auf potenziell schädliche Websites zugreifen.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|  Verhindern, dass Windows Defender-SmartScreen-Warnungen für Dateien ignoriert werden   | Verwenden Sie für zusätzliche Sicherheit, um zu verhindern, dass Benutzer Windows Defender-SmartScreen-Warnungen ignorieren, und verhindern Sie, dass nicht überprüfte Dateien von Microsoft Edge heruntergeladen werden. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Windows Update-Einstellungen

|                      Einstellung                      |                                                                                                           Details                                                                                                            |                                                                    CSP-Referenz                                                                    |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Current Branch oder Current Branch for Business verwenden |                                                       Verwenden Sie diese Einstellung, um Windows Update for Business zu konfigurieren. Weitere Informationen finden Sie unter [Windows-Updates](manage-windows-updates-for-surface-hub.md).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               Zurückstellen von Featureupdates               |                                                                                                          Siehe oben.                                                                                                          | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               Zurückstellen von Qualitätsupdates               |                                                                                                          Siehe oben.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               Unterbrechen von Featureupdates               |                                                                                                          Siehe oben.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               Unterbrechen von Qualitätsupdates               |                                                                                                          Siehe oben.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|           Konfigurieren des Geräts für die Verwendung von WSUS            |                                            Verwenden Sie diese Einstellung, um den Surface Hub mit WSUS anstelle von Windows Update zu verbinden. Weitere Informationen finden Sie unter [Windows-Updates](manage-windows-updates-for-surface-hub.md).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|               Übermittlungsoptimierung               | Verwenden Sie die Peer-to-Peer-Inhaltsfreigabe, um Bandbreitenprobleme während Aktualisierungen zu reduzieren. Details hierzu finden Sie unter [Konfigurieren der Übermittlungsoptimierung für Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization). |         Übermittlungsoptimierung/*`<name of policy>`* <br> Weitere Informationen finden Sie unter [Richtlinien-CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Windows Defender-Einstellungen

|      Einstellung      |                                              Details                                               |                                                     CSP-Referenz                                                      |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Defender-Richtlinien |            Verwenden Sie diese Einstellung, um verschiedene Defender-Einstellungen zu konfigurieren, einschließlich der Planung der Überprüfungszeit.            | Defender/*`<name of policy>`* <br> Weitere Informationen finden Sie unter [Richtlinien-CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
|  Defender-Status  | Verwenden Sie diese Informationen, um einen Defender-Scan zu initiieren, ein Security Intelligence-Update zu erzwingen und alle erkannten Bedrohungen abzufragen. |                   [Defender-Konfigurationsdienstanbieter](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Ja                        |                       Ja                       |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Remoteneustart

|                       Einstellung                        |                                                          Details                                                          |                                                             CSP-Referenz                                                             |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Gerät sofort neu starten             | Verwenden Sie diese Einstellung in Verbindung mit OMS, um die Supportkosten zu minimieren. Weitere Informationen finden Sie unter [Überwachen des Microsoft Surface Hub](monitor-surface-hub.md). |        ./Vendor/MSFT/Reboot/RebootNow <br> Siehe [Neustarten des CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Ja                        |                       Nein.                        |             Ja             |
|    Neustarten des Geräts zu einem geplanten Datum und einer geplanten Uhrzeit    |                                                        Siehe oben.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> Siehe [Neustarten des CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |
| Tägliches Neustarten des Geräts zu einem geplanten Datum und einer geplanten Uhrzeit |                                                        Siehe oben.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> Siehe [Neustarten des CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Zertifikate installieren

|             Einstellung             |                           Details                            |                                           CSP-Referenz                                            |                                                         Unterstützt durch<br>Intune?                                                          |                                                                  Unterstützt durch<br>Konfigurations-Manager?                                                                  | Unterstützt durch<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Vertrauenswürdige ZS-Zertifikate installieren | Verwenden Sie diese Einstellung, um vertrauenswürdige Stamm- und Zwischen-ZS-Zertifikate bereitzustellen. | [RootCATrustedCertificates CSP](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Ja <br> Weitere Informationen finden Sie unter [Konfigurieren von Intune-Zertifikatprofilen](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Ja <br> Weitere Informationen finden Sie unter [Erstellen von Zertifikat Profilen im Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Ja             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Protokolle erfassen

|     Einstellung      |                      Details                       |                                     CSP-Referenz                                      | Unterstützt durch<br>Intune? | Unterstützt durch<br>Konfigurations-Manager? | Unterstützt durch<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| ETW-Protokolle erfassen | Verwenden Sie diese Einstellung, um ETW-Protokolle remote von Surface Hub zu erfassen. | [DiagnosticLog CSP](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            Nein             |                    Nein                    |             Ja             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Netzwerkrichtlinien für QoS festlegen

|        Einstellung         |                                                            Details                                                             |                                                    CSP-Referenz                                                     |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Netzwerkrichtlinien für QoS festlegen | Verwenden Sie eine QoS-Richtlinie zum Ausführen von Aktionen auf dem Netzwerkverkehr. Dies ist hilfreich für die Priorisierung von Skype-Paketen. | [Netzwerk-QoS-Richtlinie-Konfigurationsdienstanbieter](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Netzwerk-Proxy festlegen

|      Einstellung      |                               Details                               |                                                CSP-Referenz                                                 |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Netzwerk-Proxy festlegen | Wird verwendet, um einen Proxyserver für Ethernet und WLAN-Verbindungen festzulegen. | [Netzwerkproxy-Konfigurationsdienstanbieter](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

#### Startmenü konfigurieren

|       Einstellung        |                                                                       Details                                                                        |                                                        CSP-Referenz                                                         |            Unterstützt durch<br>Intune?             |    Unterstützt durch<br>Konfigurations-Manager?     | Unterstützt durch<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Startmenü konfigurieren | Wird verwendet, um festzulegen, welche Apps im Startmenü angezeigt werden. Unter [Konfigurieren des Surface Hub-Startmenüs](surface-hub-start-menu.md) finden Sie weitere Informationen. | [Policy CSP: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Ja <br> [Verwenden Sie eine benutzerdefinierte Richtlinie.](#example-manage-surface-hub-settings-with-microsoft-intune) | Ja.<br> [Verwenden Sie eine benutzerdefinierte Einstellung.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Ja             |

\*Mit SyncML unterstützte Einstellungen können auch in einem Bereitstellungspaket des Windows-Konfigurations-Designers konfiguriert werden.

### OMA-URIs für Einstellungen generieren 
Sie müssen den OMA-URI einer Einstellung verwenden, um eine benutzerdefinierte Richtlinie in InTune oder eine benutzerdefinierte Einstellung in Microsoft Endpoint Configuration Manager zu erstellen.

**So generieren Sie den OMA-URI für eine Einstellung in der CSP-Dokumentation**
1. Identifizieren Sie in der CSP-Dokumentation den Stammknotens des CSP. Im Allgemeinen sieht dieser wie folgt aus: `./Vendor/MSFT/<name of CSP>` <br>
*Der Stammknoten für den [SurfaceHub-CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) ist beispielsweise `./Vendor/MSFT/SurfaceHub`.*
2. Identifizieren Sie den Knotenpfad für die Einstellung, die Sie verwenden möchten. <br>
*Der Knotenpfad für die Einstellung zum Aktivieren der drahtlosen Projektion ist beispielsweise `InBoxApps/WirelessProjection/Enabled`.*
3. Fügen Sie den Knotenpfad dem Stammknoten an, um den OMA-URI zu generieren. <br>
*Der OMA-URI für die Einstellung zum Aktivieren der drahtlosen Projektion ist beispielsweise `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`.*

Der Datentyp wird auch in der CSP-Dokumentation angegeben. Die am häufigsten verwendeten Datentypen sind:
- char (Zeichenfolge)
- int (ganze Zahl)
- bool (boolescher Wert)


## Beispiel: Verwalten von Surface Hub-Einstellungen mit Microsoft Intune

Sie können Microsoft Intune zum Verwalten von Surface Hub-Einstellungen verwenden. Führen Sie für benutzerdefinierte Einstellungen Sie die Schritte unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](https://docs.microsoft.com/intune/custom-settings-configure) durch. Für **Plattform**, wählen Sie **Windows10 und höher** und im **Profiltyp** die Option **Geräteeinschränkungen (Windows10 Team)** aus.



## Beispiel: Verwalten von Surface Hub-Einstellungen mit Microsoft Endpoint Configuration Manager
Configuration Manager unterstützt die Verwaltung moderner Geräte, für die der Configuration Manager-Client keine Verwaltung benötigt, einschließlich Surface Hub. Wenn Sie bereits Configuration Manager zum Verwalten anderer Geräte in Ihrer Organisation verwenden, können Sie die Configuration Manager-Konsole weiterhin als einzigen Standort zum Verwalten von Surface Hubs verwenden.

> [!NOTE]
> Diese Anweisungen basieren auf der aktuellen Verzweigung von Configuration Manager.

**So erstellen Sie ein Konfigurationselement für Surface Hub-Einstellungen**

1. Klicken Sie im Arbeitsbereich **Bestand und Kompatibilität** der Konfigurations-Manager-Konsole auf **Übersicht** > **Kompatibilitätseinstellungen** > **Konfigurationselemente**.
2. Klicken Sie auf der Registerkarte **Start** in der Gruppe **Erstellen** auf **Konfigurationselement erstellen**.
3. Geben Sie auf der Seite **Allgemein** des Assistenten zum Erstellen von Konfigurationselementen einen Namen und optional eine Beschreibung für das Konfigurationselement an.
4. Wählen Sie unter **Einstellungen für Geräte, die ohne den Konfigurations-Manager-Client verwaltet werden** die Option **Windows 8.1 und Windows 10** aus, und klicken Sie dann auf **Weiter**.

    ![Beispiel für die Benutzeroberfläche](images/configmgr-create.png)
5. Erweitern Sie auf der Seite **Unterstützte Plattformen** die Option **Windows10**, und wählen Sie **Alle Geräte mit Windows 10 Team und höher** aus. Heben Sie die Auswahl für die anderen Windows-Plattformen auf, und klicken Sie dann auf **Weiter**.

    ![Plattform auswählen](images/configmgr-platform.png)
7. Wählen Sie auf der Seite **Geräteeinstellungen** unter **Geräteeinstellungsgruppen** die Option **Windows10 Team** aus.


8. Konfigurieren Sie auf der Seite **Windows10 Team** die Einstellungen, die Sie benötigen.

    ![Windows 10 Team](images/configmgr-team.png)
9. Sie müssen benutzerdefinierte Einstellungen erstellen, um Einstellungen zu verwalten, die nicht auf der Seite für Windows10 Team verfügbar sind. Aktivieren Sie auf der Seite **Geräteeinstellungen** das Kontrollkästchen **Zusätzliche Einstellungen konfigurieren, die in den Standardeinstellungsgruppen nicht enthalten sind**.

    ![Zusätzliche Einstellungen](images/configmgr-additional.png)
10. Klicken Sie auf der Seite **Zusätzliche Einstellungen** auf **Hinzufügen**.
11. Klicken Sie im Dialogfeld **Einstellungen durchsuchen** auf **Einstellung erstellen**.
12. Geben Sie im Dialogfeld **Einstellung erstellen** auf der Registerkarte **Allgemein** einen Namen und optional eine Beschreibung für die benutzerdefinierte Einstellung an.
13. Wählen Sie unter **Einstellungstyp** **OMA-URI** aus.
14. Füllen Sie das Formular zum Erstellen einer neuen Einstellung aus, und klicken Sie dann auf **OK**.

    ![OMA-URI-Einstellung](images/configmgr-oma-uri.png)
15. Wählen Sie im Dialogfeld **Einstellungen durchsuchen** unter **Verfügbare Einstellungen** die von Ihnen erstellte neue Einstellung aus, und klicken Sie dann auf **Auswählen**.
16. Füllen Sie im Dialogfeld **Regel erstellen** das Formular zum Festlegen einer Regel für die Einstellung aus, und klicken Sie dann auf **OK**.
17. Wiederholen Sie die Schritte9 bis 15 für jede benutzerdefinierte Einstellung, die Sie dem Konfigurationselement hinzufügen möchten.
18. Wenn Sie fertig sind, klicken Sie im Dialogfeld **Einstellungen durchsuchen** auf **Schließen**.
19. Führen Sie den Assistenten bis zum Ende aus. <br> Sie können das neue Konfigurationselement im Knoten **Konfigurationselemente** des Arbeitsbereichs **Bestand und Kompatibilität** anzeigen.

Weitere Informationen finden Sie unter [Erstellen von Konfigurationselementen für Windows 8,1-und Windows 10-Geräte, die ohne den Microsoft Endpoint Configuration Manager-Client verwaltet](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client)werden.

## Verwandte Themen

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)











