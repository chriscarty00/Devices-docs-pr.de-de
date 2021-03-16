---
title: Verwalten von Einstellungen für Surface Hub 2S mit Intune
description: Hier erfahren Sie, wie Sie Einstellungen für Surface Hub 2S mit Intune aktualisieren und verwalten können.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 406fcc58bdb09d7fd47966cd17123d55faec2b65
ms.sourcegitcommit: ea853f2dba67e63e6df33538670fd581e17facab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "11408790"
---
# <a name="manage-surface-hub-2s-with-intune"></a>Verwalten von Einstellungen für Surface Hub 2S mit Intune

## <a name="register-surface-hub-2s-with-intune"></a>Registrieren von Surface Hub 2S mit Intune

Surface Hub 2S ermöglichen IT-Administratoren das Verwalten von Einstellungen und Richtlinien mithilfe eines Anbieters für die mobile Geräteverwaltung (Mobile Device Management, MDM). Surface Hub 2S hat eine integrierte Verwaltungskomponente, um mit dem Verwaltungsserver zu kommunizieren, sodass keine zusätzlichen Clients auf dem Gerät installiert werden müssen.

### <a name="manual-registration"></a>Manuelle Registrierung

1. Öffnen Sie **die App** Einstellungen auf Surface Hub 2S, und melden Sie sich als lokaler Administrator an. Wählen Sie **Surface Hub** > **Geräteverwaltung** und wählen Sie dann **+** zum Hinzufügen.
2. Sie werden aufgefordert, sich mit dem Konto anzumelden, das für Intune verwendet werden soll. Nach der Authentifizierung wird das Gerät automatisch bei Intune registriert.

   ![Registrieren von Surface Hub 2S mit Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> Das für die Authentifizierung verwendete Konto ist das Intune-Registrierungskonto und muss für Intune lizenziert sein.

### <a name="auto-registration--azure-active-directory-affiliated"></a>Automatische Registrierung – Azure Active Directory Affiliated

Während des erstmaligen Einrichtungsvorgangs wird beim Zuordnen eines Surface Hubs zu einem Azure AD-Mandanten, für den die automatische Intune-Registrierung aktiviert ist, das Gerät automatisch bei Intune registriert. Weitere Informationen finden Sie unter [Intune-Registrierungsmethoden für Windows-Geräte](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Die Azure AD-Zugehörigkeit und die automatische Intune-Registrierung sind erforderlich, damit der Surface Hub ein „konformes Gerät“ im Intune ist. 

## <a name="managing-windows-10-team-settings-with-intune"></a>Verwalten von Windows 10-Teameinstellungen mit Intune

1. Melden Sie sich **bei Microsoft Endpoint Manager**an, wählen Sie **Gerätekonfigurationsprofile**  >  **Erstellen**eines  >  **Profils aus.** 
2. Wählen **Sie unter Plattform**die Option Windows **10 und höher**  >  **Vorlagen**Geräteeinschränkungen  >  **(Windows 10 Team)** aus, und wählen Sie dann Erstellen **aus.** 
3. Sie können nun vordefinierte Geräteeinschränkungseinstellungen für Surface Hub und Surface Hub 2S durchsuchen und auswählen.

 ![Festlegen von Geräteeinschränkungen für Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Diese Einstellungen umfassen die folgenden Kategorien: Apps und Erfahrung, Einblicke in den Betrieb von Azure, Wartung, Sitzung und Drahtlose Projektion.  

## <a name="supported-configuration-service-providers-csps"></a>Unterstützte Konfigurationsdienstanbieter (CSPs)

Zusätzlich zu den direkt über die Intune-Konsole verfügbaren Richtlinien gibt es zahlreiche Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die Registrierungsschlüsseln oder Dateien zuordnungen. 

Microsoft stellt in der Regel neue CSPs mit jeder neuen Version des Betriebssystems Windows 10 zur Verfügung. Das [Windows 10 Team 2020 Update](surface-hub-2020-update.md) enthält mehr als 20 neue und aktualisierte Geräteverwaltungsrichtlinien für Surface Hub und Surface Hub 2S. Diese MDM-Richtlinien bieten IT-Administratoren eine verbesserte Kontrolle über App-Updates aus dem Microsoft Store, Drahtlose Projektionseinstellungen wie Miracast über die Infrastruktur, Netzwerkeinstellungen wie Quality-Of-Service und 802.1x verkabelte Authentifizierung sowie neue Datenschutz-/DSGVO-bezogenen Einstellungen.

Weitere Informationen finden Sie in den folgenden Ressourcen: 

- [Referenz zum Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub-Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Richtlinien-Konfigurationsdienstanbieter, die von MicrosoftSurface Hub unterstützt werden](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Neues in Surface Hub Team 2020 Update](surface-hub-2020-update-whats-new.md)

## <a name="quality-of-service-qos-settings"></a>Quality of Service (QoS, Dienstqualität) – Einstellungen

Um eine optimale Video- und Audioqualität auf dem Surface Hub 2S zu gewährleisten, fügen Sie die folgenden QoS-Einstellungen zum Gerät hinzu. 

### <a name="microsoft-teams-qos-settings"></a>Microsoft Teams QoS – Einstellungen 

| Name | Beschreibung | OMA-URI | Typ | Wert |
|:------ |:------------- |:--------- |:------ |:------- |
|**Audio-Ports**| Audio-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Zeichenfolge  | 3478-3479 |
|**Audio DSCP**| Markierung der Audio-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Ganze Zahl | 46 |
|**Video-Port**| Video-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Zeichenfolge  | 3480 |
|**Video DSCP**| Markierung der Video-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Ganze Zahl | 34 |
|**Freigabeport**| Freigabeportbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | Zeichenfolge  | 3481 |
|**Freigeben von DSCP**| Kennzeichnung von Freigabeports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | Ganze Zahl | 18 |
|**P2P Audio-Ports**| Audio-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Zeichenfolge  | 50000-50019 |
|**P2P Audio DSCP**| Markierung der Audio-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Ganze Zahl | 46 |
|**P2P Video Ports**| Video-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Zeichenfolge  | 50020-50039 |
|**P2P Video DSCP**| Markierung der Video-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Ganze Zahl | 34 |
|**P2P-Freigabeports**| Freigabeportbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | Zeichenfolge  | 50040-50059 |
|**P2P Sharing DSCP**| Kennzeichnung von Freigabeports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | Ganze Zahl | 18 |


### <a name="skype-for-business-qos-settings"></a>Skype for Business QoS – Einstellungen

| Name                 | Beschreibung           | OMA-URI                                                                    | Typ    | Wert                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Audio-Ports          | Audio-Portbereich      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | Zeichenfolge  | 50000-50019                    |
| Audio DSCP           | Markierung der Audio-Ports   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Ganze Zahl | 46                             |
| Audio-Medienquelle   | Name der Skype-App        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | Zeichenfolge  | Microsoft.PPISkype.Windows.exe |
| Video Ports          | Video-Portbereich      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | Zeichenfolge  | 50020-50039                    |
| Video DSCP           | Markierung der Video-Ports   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Ganze Zahl | 34                             |
| Video-Medienquelle   | Name der Skype-App        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | Zeichenfolge  | Microsoft.PPISkype.Windows.exe |
| Freigabeports        | Freigabeportbereich    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | Zeichenfolge  | 50040-50059                    |
| Freigeben von DSCP         | Kennzeichnung von Freigabeports | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | Ganze Zahl | 18                             |
| Freigeben von Medienquellen | Name der Skype-App        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | Zeichenfolge  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> In beiden Tabellen werden standardmäßige Portbereiche angezeigt. Administratoren können die Portbereiche in der Systemsteuerung in Skype for Business und Teams ändern.

## <a name="microsoft-teams-settings"></a>Microsoft Teams-Einstellungen

Sie können verschiedene Microsoft Teams-Einstellungen mithilfe von Intune konfigurieren.

### <a name="modes"></a>Modi

Surface Hub 2S wird mit Microsoft Teams im Modus 0 installiert, der sowohl Microsoft Teams als auch Skype for Business unterstützt. Die Modi funktionieren wie unten beschrieben:

- Modus 0 – Skype for Business mit Microsoft Teams für geplante Besprechungen.
- Modus 1 – Microsoft Teams mit Skype for Business für geplante Besprechungen.
- Modus 2 – Nur Microsoft Teams.

Um den Modus anzupassen, fügen Sie einem benutzerdefinierten Gerätekonfigurationsprofil die [folgenden Einstellungen hinzu.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Name | Beschreibung | OMA-URI | Typ | Wert |
|:--- |:--- |:--- |:--- |:--- |
|**ID der Teams-App**|Name der App|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Zeichenfolge| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modus der Teams-App**|Teams-Modus|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Ganze Zahl| 0 oder 1 oder 2|

### <a name="coordinated-meetings-and-proximity-join"></a>Teilnahme an koordinierten Besprechungen und Näherung

Teams Coordinated Meeting and proximity join features can [be configured through an XML file](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) deployed via an Intune profile.
