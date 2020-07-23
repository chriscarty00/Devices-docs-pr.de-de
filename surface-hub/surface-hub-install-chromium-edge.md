---
title: Installieren und Konfigurieren des neuen Microsoft Edge auf Surface Hub
description: Installieren und konfigurieren Sie den neuen Microsoft Edge auf Surface Hub.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: cf4d909a8c06bddf2bb0b3e42259f0b69cd97109
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894101"
---
# Installieren und Konfigurieren des neuen Microsoft Edge auf Surface Hub

Das Windows 10-Team 2020-Update unterstützt den neuen Microsoft-Edge basierend auf Chrom (Version 85 und höher) als den empfohlenen Browser für Surface Hub. Sie können Microsoft Edge manuell mithilfe eines Bereitstellungspakets installieren, und zwar Remote mithilfe von Microsoft InTune oder Ihrem bevorzugten MDM-Anbieter (Mobile Device Management).

 Standardmäßig sind Surface-Hub-Geräte mit Microsoft Edge Legacy (Version 44) vorinstalliert.

> [!IMPORTANT]
> Surface Hub erfordert Version 85 oder höher des neuen Microsoft Edge, wobei die Verfügbarkeit auf den "[dev Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels)" begrenzt ist, um IT-Administratoren einen frühen Überblick über bevorstehende Edge-Funktionen zu geben und sich auf die nächste Beta Version vorzubereiten.  Die Unterstützung für den dev-Kanal ist vorübergehend für Windows-Insider zur Vorschau von Microsoft Edge aktiviert. (Normalerweise unterstützt Surface Hub nur Versionen, die im "stable-Kanal" veröffentlicht sind.) Weitere Informationen finden Sie unter [Übersicht über den Microsoft-Edge-Kanal.](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
 
### Installieren von Microsoft Edge dev Channel-Builds 

- Durch das Design wird Microsoft Edge dev Channel parallel zu Microsoft Edge Legacy installiert, und die Benutzer sehen im Startmenü von Surface Hub sowohl "Microsoft Edge dev" (Version 85) als auch "Microsoft Edge" (Version 44). Im Gegensatz dazu ersetzt Microsoft Edge stable-Kanal Microsoft Edge Legacy als Standardbrowser.
- Nach der Installation wird Microsoft Edge dev Channel nicht automatisch als angeheftete App angezeigt. Wählen Sie zum Öffnen **Start**  >  **alle apps**starten aus. Im Gegensatz dazu ersetzt Microsoft Edge stable-Kanal automatisch Microsoft Edge Legacy als angeheftete app in der Liste alle apps.
- Nachdem Version 85 auf stable-Kanal heraufgestuft wurde, wird der Microsoft Edge dev-Kanal automatisch aus dem Startmenü entfernt, und Sie müssen den Microsoft Edge stable-Kanal auf dem Surface Hub installieren.

> [!NOTE]
>  Zum Entfernen des neuen Microsoft Edge ist ein Geräte-Reset erforderlich. Weitere Informationen finden Sie unter [Zurücksetzen oder Wiederherstellen eines Surface-Hubs](https://docs.microsoft.com/surface-hub/device-reset-surface-hub) .

## Installieren von Microsoft Edge

### Installieren von Microsoft Edge mithilfe eines Bereitstellungspakets

1. Laden Sie das [Microsoft Edge Provisioning-Paket](https://aka.ms/HubEdge) (MicrosoftEdgeDevInstaller. ppkg) von einem PC in den Stammordner eines USB-Laufwerks herunter.
2. Legen Sie das USB-Laufwerk in Surface Hub ein.
3. Öffnen Sie auf dem Surface Hub **Einstellungen** , und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
4. Navigieren Sie zu **Surface Hub** > **Geräteverwaltung**. Wählen Sie unter **Bereitstellungspakete** die Option **Bereitstellungspaket hinzufügen oder entfernen** aus.
5. Wählen Sie **Paket hinzufügen** aus.
6. Wählen Sie das Microsoft Edge-Bereitstellungspaket aus, und wählen Sie **Hinzufügen**aus.
7. Eine Zusammenfassung der Änderungen, die das Bereitstellungspaket anwendet, wird angezeigt. Wählen Sie **Ja, hinzufügen** aus.
8. Warten Sie, bis die Microsoft Edge-Installation abgeschlossen ist. Nachdem die APP installiert wurde, navigieren Sie zum Startmenü von Surface Hub, um auf das neue Microsoft Edge zuzugreifen.              
Okay
> [!IMPORTANT]
>  Nach der Installation wird der Microsoft Edge dev-Kanal nicht automatisch als angeheftete App im Start Menü des Surface Hub angezeigt. Stattdessen finden die Benutzer Sie unter **Start**  >  **alle apps**starten. Wenn Sie das standardmäßige Startmenü-Layout verwenden, können Sie das Startmenü mit dem [Microsoft Edge-Bereitstellungspaket](https://aka.ms/HubEdge) installieren, um Microsoft Edge als angeheftete App hinzuzufügen. Weitere Informationen finden Sie im folgenden Abschnitt: [Anzeigen von Microsoft Edge im Microsoft Edge-Startmenü](#display-start).

> [!NOTE]
> Wenn eine neuere Version von Microsoft Edge verfügbar ist, wird Sie automatisch aktualisiert.
 
### Installieren von Microsoft Edge mithilfe von InTune
 
> [!NOTE]
> Das Surface-Hub-Gerät muss mit InTune registriert und verwaltet werden. Weitere Informationen finden Sie unter [Verwalten von Surface Hub 2S mit Microsoft InTune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Laden Sie das Microsoft Edge-Installationsprogramm von Microsoft herunter](https://www.microsoft.com/edge/business/download).
    - Verwenden der aktuellen Version von [dev Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(Version 85)**
    - **Windows 64-Bit** auswählen
2. [Fügen Sie das Microsoft Edge-Installationsprogramm als eine Branchen-APP zu Microsoft InTune hinzu](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - Wenn Sie die Verwendung von Microsoft Edge Update für die Behandlung automatischer Updates für Microsoft Edge auswählen, stellen Sie sicher, dass die **App-Version ignorieren** für den Bereich **app-Informationen** konfiguriert ist. Wenn Sie diese Einstellung auf " **Ja**" umstellen, wird die App-Version, die auf dem Surface Hub-Gerät installiert ist, nicht durch Microsoft InTune erzwungen.

 
### Installieren von Microsoft Edge mithilfe der Verwaltung mobiler Geräte

1. [Laden Sie das Microsoft Edge-Installationsprogramm von Microsoft herunter](https://www.microsoft.com/edge/business/download).
    - Verwenden der aktuellen Version von [dev Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(Version 85)**
    - **Windows 64-Bit** auswählen
2. Inszenieren Sie das Microsoft Edge-Installationsprogramm an einem gehosteten Speicherort, beispielsweise einer lokalen Dateifreigabe (\\server\share\MicrosoftEdgeEnterpriseX64.msi). Das Surface-Hub-Gerät muss über die Berechtigung für den Zugriff auf den gehosteten Speicherort verfügen.
3. Verwenden Sie [EnterpriseDesktopAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) über Ihren MDM-Anbieter, um Microsoft Edge zu installieren.

 

## Konfigurieren von Microsoft Edge

### Standardmäßige Microsoft Edge-Richtlinien für Surface Hub
Microsoft Edge ist mit den folgenden Richtlinien vorkonfiguriert, um eine optimierte Oberfläche für Surface Hub bereitzustellen.
 
> [!NOTE]
>  Wir empfehlen, den Standardwert für diese Richtlinien beizubehalten.
 

| Microsoft Edge-Richtlinie                                                                                                    | Empfohlene Benutzeroberfläche                                                                                                                                                                                                                                               | Standardwert |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Importieren Sie Datentypen und Einstellungen nicht automatisch aus Microsoft Edge Legacy. Dadurch wird verhindert, dass Benutzerprofile mit den freigegebenen Einstellungen des Surface-Hubs geändert werden.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Microsoft Edge-Prozesse können auch nach dem Schließen des letzten Browserfensters weiterhin im Hintergrund ausgeführt werden, sodass während einer Sitzung schneller auf Web-Apps zugegriffen werden kann.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Benutzern das Erstellen neuer Profile in Microsoft Edge nicht gestatten. Dies vereinfacht das Browsen und die Anmeldung.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Ermöglicht nur einem Benutzer die Anmeldung bei Microsoft Edge. Dadurch wird das Browsen und die Anmeldung vereinfacht                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Ermöglicht Benutzern, einmaliges Anmelden (Single Sign-on, SSO) in Microsoft Edge zu genießen. Wenn ein Benutzer bei Surface Hub angemeldet ist, können seine Anmeldeinformationen auf unterstützte Websites übertragen werden, ohne dass diese erneut authentifiziert werden müssen.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Verhindert, dass Benutzer, die keine Administratoren sind, neue Erweiterungen in Microsoft Edge installieren. Verwenden Sie [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist), um eine Liste der Erweiterungen zu konfigurieren, die standardmäßig installiert werden sollen. | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Blendet den ersten Ausführungsverlauf und den Begrüßungsbildschirm aus, der normalerweise angezeigt wird, wenn Benutzer Microsoft Edge zum ersten Mal ausführen. Da Surface Hub ein freigegebenes Gerät ist, wird dadurch die Benutzerfreundlichkeit vereinfacht.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deaktiviert den InPrivate-Modus. Da durch die End-Sitzung bereits durchsuchte Daten gelöscht werden, wird dadurch das Browsen und die Anmeldung vereinfacht.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Zeigt die Office 365-Feed-Erfahrung auf neuen Registerkarten. Wenn ein Benutzer bei Surface Hub angemeldet ist, ermöglicht dies schnellen Zugriff auf seine Dateien und Inhalte auf Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Wenn ein Benutzer bei Surface Hub angemeldet ist, wird ein nicht zu entfernendes Profil mit seinem organisationskonto erstellt. Dadurch wird die einmalige Anmeldung (Single Sign-on, SSO) vereinfacht.                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Deaktiviert das Drucken in Microsoft Edge. Surface Hub unterstützt kein drucken.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Ermöglicht Microsoft Edge die proaktive Authentifizierung von angemeldeten Benutzern mit Microsoft-Diensten. Dadurch wird die einmalige Anmeldung (Single Sign-on, SSO) vereinfacht.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Speichert Dateien automatisch im Ordner "Downloads", anstatt die Benutzer zu Fragen, wo die Datei gespeichert werden soll. Dadurch wird das Browsen vereinfacht.                                                                                                                             | 0                 |

 
### Konfigurieren von Microsoft Edge-Richtlinien

Verwenden Sie [Microsoft Edge-Browser Richtlinien](https://docs.microsoft.com/deployedge/microsoft-edge-policies) zum Konfigurieren von Browsereinstellungen in Microsoft Edge. Diese Richtlinien können mit folgenden Methoden angewendet werden:

- [Microsoft InTune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Ihr bevorzugter MDM-Anbieter (Mobile Device Management), der die ADMX-Einnahme unterstützt](https://docs.microsoft.com/deployedge/configure-edge-with-mdm), oder
- [Bereitstellen von Paketen mithilfe der ADMX-Einnahme im Windows-Konfigurations-Designer](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Konfigurieren von Microsoft Edge-updates

Standardmäßig wird Microsoft Edge automatisch aktualisiert. Verwenden Sie [Microsoft Edge Update-Richtlinien](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) , um die Einstellungen für Microsoft Edge Update zu konfigurieren.
Beachten Sie, dass Surface Hub die folgenden Microsoft Edge Update-Richtlinien nicht unterstützt:

- **Allowsxs** – auf Surface Hub ersetzt Microsoft Edge stable-Kanal immer Microsoft Edge Legacy.
- **CreateDesktopShortcut** – Surface Hub verwendet keine Desktop Tastenkombinationen.

> [!NOTE]
>  Microsoft Edge erfordert zur Unterstützung der zugehörigen Features eine Internetverbindung. Stellen Sie sicher, dass die [erforderlichen Domänen-URLs](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) zur Zulassungsliste hinzugefügt werden, um die Kommunikation über Firewalls und andere Sicherheitsmechanismen zu gewährleisten.
 
### <a name="display-start"></a> Anzeigen von Microsoft Edge im Startmenü von Surface Hub

Nach der Installation wird der Microsoft Edge dev-Kanal nicht automatisch als angeheftete App im Start Menü des Surface Hub angezeigt. Stattdessen finden die Benutzer Sie unter **Start**  >  **alle apps**starten.
Wenn Sie das standardmäßige Startmenü-Layout verwenden, können Sie das Startmenü mit dem Microsoft Edge-Bereitstellungspaket installieren, um Microsoft Edge als angeheftete App hinzuzufügen.
Wenn Sie ein angepasstes Startmenü-Layout anwenden möchten, verwenden Sie die folgende XML-Datei, um eine angeheftete Kachel für Microsoft Edge hinzuzufügen.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge Dev\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Weitere Informationen finden Sie unter [Konfigurieren des Surface Hub-Start Menüs](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 
> [!NOTE]
> Das neue Microsoft Edge unterstützt keine angehefteten Websites und Links mithilfe von SecondaryTiles.

## Verwandte Links

- [Microsoft Edge-Dokumentation](https://docs.microsoft.com/microsoft-edge/)

