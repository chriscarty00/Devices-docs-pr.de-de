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
ms.openlocfilehash: 3b3b5ed47e3a34369c6890aac051436db1f42347
ms.sourcegitcommit: f8f32455b1230742c58ee74004cbaaad037069b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328209"
---
# Verwalten von Einstellungen für Surface Hub 2S mit Intune

## Registrieren von Surface Hub 2S mit Intune

Surface Hub 2S ermöglichen IT-Administratoren das Verwalten von Einstellungen und Richtlinien mithilfe eines Anbieters für die mobile Geräteverwaltung (Mobile Device Management, MDM). Surface Hub 2S hat eine integrierte Verwaltungskomponente, um mit dem Verwaltungsserver zu kommunizieren, sodass keine zusätzlichen Clients auf dem Gerät installiert werden müssen.

### Manuelle Registrierung

1. Öffnen Sie **die App** "Einstellungen" auf Surface Hub 2S, und melden Sie sich als lokaler Administrator an. Wählen Sie **Surface Hub** > **Geräteverwaltung** und wählen Sie dann **+** zum Hinzufügen.
2. Sie werden aufgefordert, sich mit dem Konto anzumelden, das für Intune verwendet werden soll. Nach der Authentifizierung wird das Gerät automatisch bei Intune registriert.

   ![Registrieren von Surface Hub 2S mit Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> Das für die Authentifizierung verwendete Konto ist das Intune-Registrierungskonto und muss für Intune lizenziert sein.

### Automatische Registrierung – Azure Active Directory Affiliated

Während des erstmaligen Einrichtungsvorgangs wird beim Zuordnen eines Surface Hubs zu einem Azure AD-Mandanten, für den die automatische Intune-Registrierung aktiviert ist, das Gerät automatisch bei Intune registriert. Weitere Informationen finden Sie unter [Intune-Registrierungsmethoden für Windows-Geräte](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Die Azure AD-Zugehörigkeit und die automatische Intune-Registrierung sind erforderlich, damit der Surface Hub ein „konformes Gerät“ im Intune ist. 

## Verwalten von Windows 10-Teameinstellungen mit Intune

1. Melden Sie sich **bei Microsoft Endpoint Manager an,** wählen Sie ****  >  **"Gerätekonfigurationsprofile**  >  **erstellen" aus.** 
2. Wählen **Sie unter "Plattform"** die Geräteeinschränkungen für Windows **10**und höher  >  **(Windows 10 Team)** und dann "Erstellen" **aus.** 
3. Sie können jetzt voreingestellte Geräteeinschränkungseinstellungen für Surface Hub und Surface Hub 2S durchsuchen und auswählen.

 ![Festlegen von Geräteeinschränkungen für Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Diese Einstellungen umfassen die folgenden Kategorien: Apps und Erfahrung, Einblicke in den Betrieb von Azure, Wartung, Sitzung und Drahtlose Projektion.  

## Unterstützte Konfigurationsdienstanbieter (Configuration Service Providers, CSPs)

Zusätzlich zu den direkt über die Intune-Konsole verfügbaren Richtlinien gibt es zahlreiche Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die Registrierungsschlüsseln oder Dateien zugewiesen sind. 

Microsoft stellt in der Regel neue CSPs mit jeder neuen Version des Windows 10-Betriebssystems zur Verfügung. Das [Windows 10 Team 2020 Update](surface-hub-2020-update.md) enthält mehr als 20 neue und aktualisierte Geräteverwaltungsrichtlinien für Surface Hub und Surface Hub 2S. Diese Richtlinien von MDM bieten IT-Administratoren verbesserte Kontrolle über App-Updates aus dem Microsoft Store, Drahtlose Projektionseinstellungen wie Miracast über die Infrastruktur, Netzwerkeinstellungen wie Quality-of-Service und 802.1x verkabelte Authentifizierung sowie neue Einstellungen im Zusammenhang mit Datenschutz/DSGVO.

Weitere Informationen finden Sie in den folgenden Ressourcen: 

- [Referenz zum Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub-Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Richtlinien-Konfigurationsdienstanbieter, die von MicrosoftSurface Hub unterstützt werden](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Neues im Surface Hub Team 2020 Update](surface-hub-2020-update-whats-new.md)

## Quality of Service (QoS, Dienstqualität) – Einstellungen

Um eine optimale Video- und Audioqualität auf dem Surface Hub 2S zu gewährleisten, fügen Sie die folgenden QoS-Einstellungen zum Gerät hinzu. 

### Microsoft Teams QoS – Einstellungen 

| Name | Beschreibung | OMA-URI | Typ | Wert |
|:------ |:------------- |:--------- |:------ |:------- |
|**Audio-Ports**| Audio-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Zeichenfolge  | 3478-3479 |
|**Audio DSCP**| Markierung der Audio-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Ganze Zahl | 46 |
|**Video-Port**| Video-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Zeichenfolge  | 3480 |
|**Video DSCP**| Markierung der Video-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Ganze Zahl | 34 |
|**Freigabeport**| Freigabeportbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | Zeichenfolge  | 3481 |
|**Freigabe von DSCP**| Freigabeportmarkierung | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | Ganze Zahl | 18 |
|**P2P Audio-Ports**| Audio-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Zeichenfolge  | 50000-50019 |
|**P2P Audio DSCP**| Markierung der Audio-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Ganze Zahl | 46 |
|**P2P Video Ports**| Video-Portbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Zeichenfolge  | 50020-50039 |
|**P2P Video DSCP**| Markierung der Video-Ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Ganze Zahl | 34 |
|**P2P-Freigabeports**| Freigabeportbereich | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | Zeichenfolge  | 50040-50059 |
|**P2P Sharing DSCP**| Freigabeportmarkierung | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | Ganze Zahl | 18 |


### Skype for Business QoS – Einstellungen

| Name                 | Beschreibung           | OMA-URI                                                                    | Typ    | Wert                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Audio-Ports          | Audio-Portbereich      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | Zeichenfolge  | 50000-50019                    |
| Audio DSCP           | Markierung der Audio-Ports   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Ganze Zahl | 46                             |
| Audio-Medienquelle   | Name der Skype-App        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | Zeichenfolge  | Microsoft.PPISkype.Windows.exe |
| Video Ports          | Video-Portbereich      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | Zeichenfolge  | 50020-50039                    |
| Video DSCP           | Markierung der Video-Ports   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Ganze Zahl | 34                             |
| Video-Medienquelle   | Name der Skype-App        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | Zeichenfolge  | Microsoft.PPISkype.Windows.exe |
| Freigabeports        | Freigabeportbereich    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | Zeichenfolge  | 50040-50059                    |
| Freigabe von DSCP         | Freigabeportmarkierung | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | Ganze Zahl | 18                             |
| Freigeben der Medienquelle | Name der Skype-App        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | Zeichenfolge  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> In beiden Tabellen werden standardmäßige Portbereiche angezeigt. Administratoren können die Portbereiche in der Systemsteuerung in Skype for Business und Teams ändern.

## Microsoft Teams-Einstellungen

Sie können verschiedene Microsoft Teams-Einstellungen mit Intune konfigurieren.

### Modi

Surface Hub 2S wird mit Microsoft Teams im Modus 0 installiert, der sowohl Microsoft Teams als auch Skype for Business unterstützt. Die Modi funktionieren wie unten beschrieben:

- Modus 0 – Skype for Business mit Microsoft Teams für geplante Besprechungen.
- Modus 1 – Microsoft Teams mit Skype for Business für geplante Besprechungen.
- Modus 2 – Nur Microsoft Teams.

Um den Modus anzupassen, fügen Sie die folgenden Einstellungen zu einem [benutzerdefinierten Gerätekonfigurationsprofil hinzu.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Name | Beschreibung | OMA-URI | Typ | Wert |
|:--- |:--- |:--- |:--- |:--- |
|**ID der Teams-App**|Name der App|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Zeichenfolge| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modus der Teams-App**|Teams-Modus|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Ganze Zahl| 0 oder 1 oder 2|

### Koordinierte Besprechungen und Näherungsgespräche

Teams Coordinated Meeting- und [](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) Näherungs-Join-Features können über eine über ein Intune-Profil bereitgestellte XML-Datei konfiguriert werden.
