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
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4308ce1ea8ff382dc15706e68d2d706d0fd33f5f
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576755"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Verwalten von Surface Hub mit einem MDM-Anbieter

Surface Hub ermöglicht es IT-Administratoren, Einstellungen und Richtlinien mithilfe eines Mobile Device Management (MDM)-Anbieters wie Microsoft Intune. Surface Hub verfügt über eine integrierte Verwaltungskomponente, um mit dem Verwaltungsserver zu kommunizieren. Es ist nicht nötig, zusätzliche Clients auf dem Gerät zu installieren.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Registrieren Surface Hub bei der MDM-Verwaltung 

Sie können Surface bei Microsoft Intune oder einem anderen MDM-Anbieter über die manuelle oder automatische Registrierung registrieren.

### <a name="manual-enrollment"></a>Manuelle Registrierung

1. Öffnen Sie **Einstellungen** App, und melden Sie sich als lokaler Administrator an. Wählen **Surface Hub**  >  **Geräteverwaltung und** dann **+Geräteverwaltung aus.**
2. Sie werden aufgefordert, sich mit dem Für Ihren MDM-Anbieter zu verwendenden Konto zu registrieren. Nach der Authentifizierung registriert sich das Gerät automatisch bei Ihrem MDM-Anbieter.

> [!TIP]
> Wenn Sie Intune verwenden und die Serveradresse nicht erkannt wird, geben Sie **manage.microsoft.com**.
   
> [!NOTE]
> Die MDM-Registrierung verwendet die kontodetails, die für die Authentifizierung bereitgestellt werden. Das Konto muss über Berechtigungen zum Registrieren eines Windows-Geräts sowie einer Intune-Lizenz (oder der entsprechenden Registrierungspromissionen verfügen, die in Ihrem DRITTANBIETER konfiguriert sind).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Automatische Registrierung – Azure AD verbunden

Während des anfänglichen Setupprozesses wird das Gerät automatisch bei Intune registriert, wenn Surface Hub mit einem Azure Active Directory(AD)-Mandanten, für den die automatische Registrierung von Intune aktiviert ist, affiliiert wird. Weitere Informationen finden Sie unter [Intune-Registrierungsmethoden für Windows Geräte](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Die Azure AD-Zugehörigkeit und die automatische Intune-Registrierung sind erforderlich, damit der Surface Hub ein „konformes Gerät“ im Intune ist. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Verwalten Surface Hub Windows 10 Team Einstellungen mit Intune

Der basisbasierte Baustein der Richtlinieneinstellungenverwaltung in Intune und anderen MDM-Anbietern ist das XML-basierte Open Mobile Alliance-Device Management (OMA-DM)-Protokoll. Windows 10 implementiert OMA-DM XML über einen von vielen verfügbaren Konfigurationsdienstanbietern (Configuration Service Providers, CSPs) mit Namen wie AccountManagement CSP, DeviceStatus CSP, WiFi-CSP und so weiter. Eine vollständige Liste finden Sie unter [csPs supported in Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

Microsoft Intune und andere MDM-Anbieter verwenden CSPs, um eine Benutzeroberfläche zu liefern, mit der Sie Richtlinieneinstellungen in Konfigurationsprofilen konfigurieren können. Intune verwendet den Surface Hub-CSP für sein integriertes Profil – Geräteeinschränkungen **(Windows 10 Team),** mit dem Sie grundlegende Einstellungen konfigurieren können, z. B. verhindern, dass Surface Hub "aufwacht", wenn sich jemand in der Nähe seines Näherungsbereichs bewegt. Zum Verwalten von Hubeinstellungen und -features außerhalb des integrierten Profils von Intune müssen Sie ein benutzerdefiniertes Profil verwenden, wie [unten gezeigt.](#create-custom-configuration-profile) 

Zusammenfassend können Sie die folgenden Optionen zum Konfigurieren und Verwalten von Richtlinieneinstellungen in Intune verwenden: 
 
- **Erstellen Sie ein Geräteeinschränkungsprofil.** Verwenden Sie das integrierte Profil von Intune, und konfigurieren Sie die Einstellungen direkt in der Intune-Benutzeroberfläche. Weitere [Informationen finden Sie unter Create device restriction profile](#create-device-restriction-profile).
- **Erstellen Sie ein Gerätekonfigurationsprofil.**  Wählen Sie eine Vorlage aus, die sich auf ein bestimmtes Feature oder eine bestimmte Technologie wie Microsoft Defender oder Sicherheitszertifikate konzentriert. Weitere [Informationen finden Sie unter Create Device configuration profile](#create-device-configuration-profile).
- **Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil.**  Erweitern Sie Ihren Verwaltungsbereich mithilfe eines OMA Uniform Resource Identifier (OMA-URI) von allen [csPs,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)die in Microsoft Surface Hub. Weitere [Informationen finden Sie unter Erstellen eines benutzerdefinierten Konfigurationsprofils.](#create-custom-configuration-profile)

> [!NOTE]
> Profile sollten Gerätegruppen zugewiesen werden, die die registrierten Surface Hub enthalten.

## <a name="create-device-restriction-profile"></a>Erstellen eines Geräteeinschränkungsprofils

1. Melden Sie sich bei [**Microsoft Endpoint Manager Admin Center an,**](https://endpoint.microsoft.com/)wählen **Sie**  >  **GeräteKonfigurationsprofile**  >  **+** **Erstellen eines Profils aus.**
2. Wählen **Sie unter Plattform**Windows 10 und höher **aus.** >
3. Wählen Sie unter ******Profiltyp** **Vorlagen** und dann **Geräteeinschränkungen (Windows 10 Team) aus.**
4. Wählen **Sie Erstellen**aus, fügen Sie einen Namen hinzu, und wählen Sie dann Weiter **aus.**
6. Sie können nun in den folgenden Kategorien Surface Hub einstellungen für voreingestellte Geräteeinschränkungen durchsuchen und auswählen: Apps und Erfahrung, Einblicke in den Betrieb von Azure, Wartung, Sitzung und Drahtlose Projektion. Das in der folgenden Abbildung gezeigte Beispiel gibt ein 4-Stunden-Wartungsfenster und ein 15-minütiges Timeout für Bildschirm, Ruhezustand und Fortsetzung der Sitzung an.

     ![Konfigurieren Surface Hub Einstellungen mit dem Intune-Geräteeinschränkungsprofil](images/sh-device-restrictions.png)

Weitere Informationen zum Erstellen und Verwalten von Profilen finden Sie unter [Restrict devices features using policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
Weitere Informationen zum Verwalten von Surface Hub und Einstellungen finden Sie [unter Surface Hub Windows 10 Team Geräteeinschränkungen in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Erstellen eines Gerätekonfigurationsprofils

1. Melden Sie sich [**bei Microsoft Endpoint Manager Admin Center an,**](https://endpoint.microsoft.com/)wählen Sie ****  >  **Gerätekonfigurationsprofile**  >  **+ Profil erstellen aus.**
2. Wählen **Sie unter Plattform**Windows 10 und höher **aus.** >
3. Wählen **Sie unter**Profiltyp **Vorlagen** aus, und wählen Sie aus den folgenden Vorlagen aus, die auf der Surface Hub:

    - Geräteeinschränkungen (Windows 10 Team), wie im [vorherigen Abschnitt beschrieben.](#create-device-restriction-profile)
    - Microsoft Defender for Endpoint (Windows 10 Desktop)
    - #A0
    - IMPORTIERTES #A0
    - SCEP-Zertifikat
    - Vertrauenswürdiges Zertifikat

## <a name="create-custom-configuration-profile"></a>Erstellen eines benutzerdefinierten Konfigurationsprofils

Sie können den Verwaltungsbereich [erweitern,](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) indem Sie ein benutzerdefiniertes Profil mithilfe eines OMA-URI aus einem der csPs erstellen, die in diesem [Microsoft Surface Hub.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) Jede Einstellung in einem CSP verfügt über einen entsprechenden OMA-URI, den Sie mithilfe von benutzerdefinierten Konfigurationsprofilen in Intune festlegen können. Für Details zu den csPs, die von Surface Hub unterstützt werden, können Sie auf die folgenden Ressourcen verweisen: 

- [Referenz zum Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Richtlinien-Konfigurationsdienstanbieter, die von MicrosoftSurface Hub unterstützt werden](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub-Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> Die Verwaltung des Gerätekontos mithilfe von Einstellungen von [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) ist derzeit mit Intune nicht möglich und erfordert die Verwendung eines Drittanbieters für MDM.

Um CSP-basierte Richtlinieneinstellungen zu implementieren, generieren Sie zunächst einen OMA-URI und fügen ihn dann einem benutzerdefinierten Konfigurationsprofil in Intune hinzu.

### <a name="generate-oma-uri-for-target-setting"></a>Generieren von OMA-URI für die Zieleinstellung
 
So generieren Sie den OMA-URI für jede Einstellung:

1. Identifizieren Sie [in der #A0](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)den Stammknoten des CSP. Im Allgemeinen sieht dies wie **./Vendor/MSFT/ aus. <name of CSP> ** 
    - **Beispiel:** Der Stammknoten des [SurfaceHub-CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) ist **./Vendor/MSFT/SurfaceHub**.
2. Identifizieren Sie den Knotenpfad für die Einstellung, die Sie verwenden möchten. 
    - **Beispiel:** Der Knotenpfad für die Einstellung zum Aktivieren der drahtlosen Projektion ist **InBoxApps/WirelessProjection/Enabled**.
3. Fügen Sie den Knotenpfad dem Stammknoten an, um den OMA-URI zu generieren. 
    - **Beispiel:** Der OMA-URI für die Einstellung zum Aktivieren der drahtlosen Projektion ist **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. Der Datentyp wird auch in der CSP-Dokumentation angegeben. Die am häufigsten verwendeten Datentypen sind:
    - char (Zeichenfolge)
    - int (ganze Zahl)
    - bool (boolescher Wert)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Hinzufügen von OMA-URI zum benutzerdefinierten Konfigurationsprofil

1. Wählen sie Endpoint Manager ****  >  **Gerätekonfigurationsprofile**  >  **Erstellen eines Profils aus.**
2. Wählen Sie unter Plattform **Windows 10 und höher aus.** Wählen Sie unter Profil **die Option Benutzerdefiniert**aus, und wählen Sie dann **Erstellen aus.**
3. Fügen Sie einen Namen und eine optionale Beschreibung hinzu, und wählen Sie dann **Weiter aus.**
4. Wählen **Sie unter Konfigurationseinstellungen**  >  **OMA-URI Einstellungen**die Option Hinzufügen **aus.**

  
## <a name="manage-specific-surface-hub-features"></a>Verwalten bestimmter Surface Hub Features

In diesem Abschnitt werden Informationen zu Features beschrieben, die Sie über Intune oder einen anderen MDM-Anbieter verwalten können. Dies umfasst Folgendes:

- [Quality of Service (QoS)](#quality-of-service-settings)
- [Microsoft Teams und Skype for Business](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>Dienstqualitätseinstellungen

Um eine optimale Video- und Audioqualität auf Surface Hub, fügen Sie dem Gerät die folgenden QoS-Einstellungen hinzu. 

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


#### <a name="skype-for-business-qos-settings"></a>Skype for Business QoS – Einstellungen

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

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams und Skype for Business Einstellungen

Sie können ein benutzerdefiniertes Konfigurationsprofil erstellen, um Teams koordinierte Besprechungen, näherer Beitritt und andere Features zu verwalten. Weitere Informationen finden Sie unter [Manage Microsoft Teams configuration on Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config).

#### <a name="changing-default-business-communications-platform"></a>Ändern der Standardmäßigen Geschäftskommunikationsplattform

Die Standardmäßige Geschäftskommunikationsplattform auf Surface Hub hängt davon ab, wie Sie Windows 10 Team 2020 Update installieren (auch bekannt als Windows 10 20H2). Wenn Sie ein erneutes Image Surface Hub 20H2 Windows 10, wird Microsoft Teams als Standard festgelegt, Skype for Business verfügbar ist (Modus 1). Wenn Sie Ihren Hub von einer früheren Betriebssystemversion aktualisieren, bleibt Skype for Business als Standard, mit Teams-Funktionalität verfügbar (Modus 0), es sei denn, Sie haben Teams als Standard konfiguriert. 

Um die Standardinstallation zu ändern, verwenden Sie ein [benutzerdefiniertes Profil,](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) indem Sie den Teams wie folgt festlegen:  

- Modus 0 – Skype for Business mit Microsoft Teams für geplante Besprechungen.
- Modus 1 – Microsoft Teams mit Skype for Business für geplante Besprechungen.
- Modus 2 – Nur Microsoft Teams.

| Name | Beschreibung | OMA-URI | Typ | Wert |
|:--- |:--- |:--- |:--- |:--- |
|**ID der Teams-App**|Name der App|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Zeichenfolge| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modus der Teams-App**|Teams-Modus|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Ganze Zahl| 0 oder 1 oder 2|










