---
title: Firmware-Update für Microsoft Surface Dock – technische Informationen für IT-Administratoren
description: In diesem Artikel wird erläutert, wie Sie das Microsoft Surface Dock-Firmware-Update zum Aktualisieren der Surface Dock-Firmware verwenden. Wenn Sie auf Ihrem Surface-Gerät installiert ist, wird alle an Ihr Surface-Gerät angeschlossenen Surface Docks aktualisiert.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 8/05/2020
ms.openlocfilehash: 331d5122c6c64a99dad48ff6e5a90f38ce3d4ed4
ms.sourcegitcommit: 603bcb41dc1b7dd92d3bab1601fa6336480e1218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "10916026"
---
# Firmware-Update für Microsoft Surface Dock: technische Informationen für IT-Administratoren

> [!IMPORTANT]
> Dieser Artikel enthält technische Anleitungen für IT-Administratoren. Wenn Sie ein privater Benutzer sind, lesen Sie [Aktualisieren Ihrer Surface Dock-Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   auf der Microsoft-Support Website. Die Anweisungen auf der Support Website entsprechen den allgemeinen Installationsschritten unten, aber dieser Artikel enthält zusätzliche Informationen zum überwachen, überprüfen und Bereitstellen des Updates auf mehreren Geräten in einem Netzwerk.

In diesem Artikel wird erläutert, wie Sie das Microsoft Surface Dock-Firmware-Update zum Aktualisieren der Surface Dock-Firmware verwenden. Wenn Sie auf Ihrem Surface-Gerät installiert ist, wird alle an Ihr Surface-Gerät angeschlossenen Surface Docks aktualisiert. 

Dieses Tool ersetzt das frühere Microsoft Surface Dock-Update Tool, das zuvor als Teil der Surface-Tools für den Download verfügbar war. Das frühere Tool wurde Surface_Dock_Updater_vx.xx.xxx.x.msi benannt (wobei x die Versionsnummer angibt) und steht nicht mehr zum Download zur Verfügung und sollte nicht verwendet werden.

## Installieren des Surface Dock-Firmware-Updates

In diesem Abschnitt wird beschrieben, wie Sie das Firmware-Update manuell installieren.

> [!NOTE]
> Microsoft veröffentlicht in regelmäßigen Abständen neue Versionen des Surface Dock-Firmware-Updates. Die MSI-Datei wird nicht automatisch aktualisiert. Wenn Sie das MSI auf Surface-Geräten bereitgestellt haben und eine neue Version der Firmware veröffentlicht wird, müssen Sie die neue Version bereitstellen.

1. Laden Sie das [Microsoft Surface Dock-Firmware-Update](https://www.microsoft.com/download/details.aspx?id=46703)herunter und installieren Sie es.
    - Für das Update ist ein Surface-Gerät erforderlich, auf dem Windows 10, Version 1803 oder höher ausgeführt wird.
    - Beim Installieren der MSI-Datei werden Sie möglicherweise aufgefordert, Surface neu zu starten. Ein Neustart ist jedoch nicht erforderlich, um das Update durchzuführen.

2. Trennen Sie das Surface-Gerät vom Surface Dock (mit dem Netzteil), warten Sie 5 Sekunden, und stellen Sie die Verbindung wieder her. Mit dem Firmware-Update für Surface Dock wird das Dock im Hintergrund automatisch aktualisiert. Es kann einige Minuten dauern, bis der Vorgang abgeschlossen ist, und wird auch dann fortgesetzt, wenn er unterbrochen wird. 

## Überwachen des Firmware-Updates für Surface Dock

Dieser Abschnitt ist optional und bietet eine Übersicht über das Überwachen der Installation des Firmware-Updates. 

So überwachen Sie das Update:

1. Öffnen Sie die Ereignisanzeige, navigieren Sie zu **Windows-Protokollen > Anwendung**, und klicken Sie dann im rechten Bereich unter **Aktionen** auf **Aktuelles Protokoll filtern**, geben Sie **SurfaceDockFwUpdate** neben **Ereignisquellen**ein, und klicken Sie dann auf **OK**.

2. Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl ein:

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Installieren Sie das Update wie im [nächsten Abschnitt](#install-the-surface-dock-firmware-update) dieses Artikels beschrieben.
4. Das Ereignis 2007 mit dem folgenden Text zeigt eine erfolgreiche Aktualisierung an: das **Firmware-Update ist abgeschlossen. hr = 0 DriverTelementry EventCode = 2007**. 
    - Wenn das Update nicht erfolgreich ist, wird die Ereignis-ID 2007 als **Fehler** Ereignis anstelle von **Informationen**angezeigt. Darüber hinaus ist die in der Windows-Registrierung gemeldete Version nicht aktuell.
5. Nach Abschluss des Updates werden in der Windows-Registrierung aktualisierte DWORD-Werte angezeigt, die der aktuellen Version des Tools entsprechen. Weitere Informationen finden Sie im Abschnitt [Versions Referenz](#versions-reference) in diesem Artikel. Zum Beispiel:
    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Wenn im Ereignistext die Meldung "die Beschreibung für die Ereignis-ID xxxx aus Quell-SurfaceDockFwUpdate nicht gefunden werden kann" angezeigt wird, wird dies erwartet und kann ignoriert werden.

Lesen Sie auch die folgenden Abschnitte in diesem Artikel: 
  - [Überprüfen des Abschlusses der Firmware-Aktualisierung](#how-to-verify-completion-of-the-firmware-update)
  - [Ereignisprotokollierung](#event-logging)
  - [Hinweise zur Problembehandlung](#troubleshooting-tips)
  - [Versions Referenz](#versions-reference)

## Netzwerkbereitstellung

Sie können Windows Installer-Befehle (Msiexec.exe) verwenden, um das Surface Dock-Firmware-Update auf mehreren Geräten in Ihrem Netzwerk bereitzustellen. Wenn Sie den Microsoft Endpoint Configuration Manager oder ein anderes Bereitstellungstool verwenden, geben Sie die folgende Syntax ein, um sicherzustellen, dass die Installation stumm ist:

- **Msiexec.exe/i \<path to msi file\> /quiet/norestart** 

  Zum Beispiel:
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > Standardmäßig wird keine Protokolldatei erstellt. Um eine Protokolldatei zu erstellen, müssen Sie "/l*v [path]" anfügen. Beispiel: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI. log "

  Weitere Informationen finden Sie in der [Befehlszeilenoptionen](https://docs.microsoft.com/windows/win32/msi/command-line-options) -Dokumentation.

> [!IMPORTANT]
> Wenn Sie das Surface Dock mit einer anderen Methode aktualisieren möchten, finden Sie weitere Informationen unter [Aktualisieren des Surface Docks](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) .

## InTune-Bereitstellung

Sie können InTune verwenden, um das Firmware-Update für Surface Dock auf Ihre Geräte zu verteilen. Zunächst müssen Sie die MSI-Datei in das intunewin-Format konvertieren, wie in der folgenden Dokumentation beschrieben: [InTune Standalone-Win32-App-Verwaltung](https://docs.microsoft.com/intune/apps/apps-win32-app-management).

Verwenden Sie den folgenden Befehl:
  - **msiexec/i \<path to msi file\> /quiet/q**

## Überprüfen des Abschlusses des Firmware-Updates

Die Surface Dock-Firmware besteht aus zwei Komponenten:

- **Component10:** Mikrocontroller-Einheit (MCU)-Firmware
- **Component20:** Display Port (DP)-Firmware.

Beim erfolgreichen Abschluss der Aktualisierung der Surface Dock-Firmware werden neue Registrierungsschlüsselwerte für diese Firmware-Komponenten angezeigt.

**So überprüfen Sie Updates:**

1. Öffnen Sie regedit, und navigieren Sie zum folgenden Registrierungspfad:

    - **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Suchen Sie nach den Registrierungsschlüsseln: **Component10CurrentFwVersion und Component20CurrentFwVersion**, die auf die aktuell auf dem Gerät befindliche Firmware verweisen.

   ![Installationsvorgang für Surface Dock-Firmware-Aktualisierung](images/regeditDock.png)

3. Überprüfen Sie, ob die neuen Registrierungsschlüsselwerte den aktualisierten Registrierungsschlüsselwerten entsprechen, die im Versions Verweis am Ende dieses Dokuments aufgeführt sind. Wenn die Werte übereinstimmen, wurde die Firmware erfolgreich aktualisiert.

4. Wenn Sie nicht überprüft werden können, überprüfen Sie die Ereignisprotokollierung und die Tipps zur Problembehandlung im nächsten Abschnitt.

## Ereignisprotokollierung

**Tabelle1. Protokolldateien für das Surface Dock-Firmware-Update**

| Log                              | Pfad                               | Anmerkungen                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firmware-Update Protokoll für Surface Dock | Pfad muss angegeben werden (siehe Hinweis) | In früheren Versionen dieses Tools wurden Ereignisse in Anwendungen und Dienste Logs\Microsoft Surface Dock-Updater geschrieben.                                                                                                  |
| Windows-Geräte Installationsprotokoll       | %windir%\inf\setupapi.dev.log           | Weitere Informationen zur Verwendung des Geräte Installationsprotokolls finden Sie in der [Setupapi](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) -Protokoll Dokumentation. |


**Tabelle 2 Ereignisprotokoll-IDs für das Surface Dock-Firmware-Update**<br>
Ereignisse werden im Anwendungsereignisprotokoll protokolliert.  Hinweis: frühere Versionen dieses Tools haben Ereignisse in Anwendungen und Dienste Logs\Microsoft Surface Dock-Updater geschrieben.

| Ereignis-ID | Ereignistyp                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Das Dock-Firmware-Update wurde gestartet.                                    |
| 2002     | Die Dock-Firmware-Aktualisierung wurde übersprungen, da Dock bekanntermaßen auf dem neuesten Stand ist. |
| 2003     | Bei der Aktualisierung der Dock-Firmware konnte keine Firmware-Version abgerufen werden.                 |
| 2004     | Abfrage der Firmware-Version.                                       |
| 2005     | Die Dock-Firmware konnte nicht gestartet werden.                                |
| 2006     | Fehler beim Senden von Angebot/Nutzlast-Paaren.                                  |
| 2007     | Firmware-Aktualisierung ist nicht mehr erfolgreich.                                            |
| 2008     | Beginnen Sie mit der Dock Telemetrie.                                                |
| 2011     | Beenden der Dock-Telemetrie                                                  |

## Hinweise zur Problembehandlung

- Trennen Sie die Stromversorgung für Surface Dock komplett vom Netzteil, um die Surface-Docking-Station zurückzusetzen.
- Trennen Sie alle Peripheriegeräte außer der Surface-Docking-Station.
- Deinstallieren Sie das aktuelle Surface Dock-Firmware-Update, und installieren Sie dann die neueste Version.
- Stellen Sie sicher, dass die Surface-Docking-Station getrennt ist, und lassen Sie dann genügend Zeit für die Ausführung des Updates über eine LED im Ethernet-Port des Docks zu. Warten Sie, bis die LED aufhört zu blinken, bevor Sie die Docking-Station aus dem Stromnetz ziehen.
- Verbinden Sie das Surface Dock mit einem anderen Gerät, um festzustellen, ob es in der Lage ist, das Dock zu aktualisieren.

## Versions Referenz

>[!NOTE]
>Die Installationsdatei wird mit dem folgenden Benennungsformat freigegeben: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) und wird standardmäßig auf C:\Program Files\SurfaceUpdate. installiert.

### Version 1.53.139.0
*Veröffentlichungsdatum: 4. August 2020*

Diese Version des Surface Dock-Firmware-Updates enthält Fehlerbehebungen und Support für:
- Aktualisieren des Surface Dock 1 mit Surface pro X 
   > [!NOTE]
   > Wenn Sie Surface pro X ausführen, laden Sie die. ARM64-Build. Verwenden Sie für alle anderen Geräte den amd64-Build. 
 


### Version 1.42.139 
*Veröffentlichungsdatum: September 18 2019*

Diese Version, die in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI enthalten ist, aktualisiert die Firmware im Hintergrund. 
**Aktualisierte Registrierungsschlüsselwerte:**<br>

- Component10CurrentFwVersion auf **4ac3970**aktualisiert.
- Component20CurrentFwVersion auf **4a1d570**aktualisiert.

Es wird Unterstützung für Surface pro 7 und Surface Laptop 3 hinzugefügt.

## Legacy Versionen

### Version 2.23.139.0
*Veröffentlichungsdatum: 10 Oktober 2018*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

- Unterstützung für Surface pro 6 hinzufügen
- Unterstützung für Surface Laptop 2 hinzufügen


### Version 2.22.139.0
*Veröffentlichungsdatum: 26 Juli 2018*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

- Höhere Zuverlässigkeit der Updates
- Hinzufügen von Unterstützung für Surface go

### Version2.12.136.0
*Veröffentlichungsdatum: 29.Januar2018*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:
* Update für Surface Dock Hauptchipsatz-Firmware
* Update für Surface Dock DisplayPort-Firmware
* Verbesserte Anzeigestabilität für externe Displays bei Verwendung mit Surface Book oder Surface Book 2

Darüber hinaus umfasst die Installation dieser Version von Surface Dock Updater auf Surface Book-Geräten Folgendes:
* Update für Surface Book Basis-Firmware
* Neue Unterstützung für Surface Dock Firmware-Updates mit Verbesserungen für Surface Book-Geräte


### Version2.9.136.0
*Veröffentlichungsdatum: 3. November2017*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

* Update für Surface Dock DisplayPort-Firmware
* Behebt ein Problem bei der Audiowiedergabe über passive Anzeigeport-Adapter

### Version2.1.15.0
*Veröffentlichungsdatum: 19.06.2017*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

* Surface Laptop
* Surface Pro

### Version2.1.6.0
*Veröffentlichungsdatum: 7.April2017*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

* Update für Surface Dock DisplayPort-Firmware
* Erfordert Windows10

### Version2.0.22.0
*Veröffentlichungsdatum: 21.Oktober2016*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

* Update für SurfaceDock-USB-Firmware
* Verbesserte Zuverlässigkeit von Ethernet-, Audio- und USB-Anschlüssen

### Version1.0.8.0
*Veröffentlichungsdatum: 26.April2016*

Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:

* Firmwareupdate für Surface Dock Main-Chipsatz
* Update für Surface Dock DisplayPort-Firmware

