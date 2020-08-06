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
# <span data-ttu-id="8fd56-104">Firmware-Update für Microsoft Surface Dock: technische Informationen für IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="8fd56-104">Microsoft Surface Dock Firmware Update: Technical information for IT admins</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fd56-105">Dieser Artikel enthält technische Anleitungen für IT-Administratoren.</span><span class="sxs-lookup"><span data-stu-id="8fd56-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="8fd56-106">Wenn Sie ein privater Benutzer sind, lesen Sie [Aktualisieren Ihrer Surface Dock-Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   auf der Microsoft-Support Website.</span><span class="sxs-lookup"><span data-stu-id="8fd56-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="8fd56-107">Die Anweisungen auf der Support Website entsprechen den allgemeinen Installationsschritten unten, aber dieser Artikel enthält zusätzliche Informationen zum überwachen, überprüfen und Bereitstellen des Updates auf mehreren Geräten in einem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="8fd56-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="8fd56-108">In diesem Artikel wird erläutert, wie Sie das Microsoft Surface Dock-Firmware-Update zum Aktualisieren der Surface Dock-Firmware verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fd56-108">This article explains how to use Microsoft Surface Dock Firmware Update to update Surface Dock firmware.</span></span> <span data-ttu-id="8fd56-109">Wenn Sie auf Ihrem Surface-Gerät installiert ist, wird alle an Ihr Surface-Gerät angeschlossenen Surface Docks aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="8fd56-110">Dieses Tool ersetzt das frühere Microsoft Surface Dock-Update Tool, das zuvor als Teil der Surface-Tools für den Download verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="8fd56-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="8fd56-111">Das frühere Tool wurde Surface_Dock_Updater_vx.xx.xxx.x.msi benannt (wobei x die Versionsnummer angibt) und steht nicht mehr zum Download zur Verfügung und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8fd56-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="8fd56-112">Installieren des Surface Dock-Firmware-Updates</span><span class="sxs-lookup"><span data-stu-id="8fd56-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="8fd56-113">In diesem Abschnitt wird beschrieben, wie Sie das Firmware-Update manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="8fd56-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="8fd56-114">Microsoft veröffentlicht in regelmäßigen Abständen neue Versionen des Surface Dock-Firmware-Updates.</span><span class="sxs-lookup"><span data-stu-id="8fd56-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="8fd56-115">Die MSI-Datei wird nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="8fd56-116">Wenn Sie das MSI auf Surface-Geräten bereitgestellt haben und eine neue Version der Firmware veröffentlicht wird, müssen Sie die neue Version bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="8fd56-117">Laden Sie das [Microsoft Surface Dock-Firmware-Update](https://www.microsoft.com/download/details.aspx?id=46703)herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="8fd56-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="8fd56-118">Für das Update ist ein Surface-Gerät erforderlich, auf dem Windows 10, Version 1803 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8fd56-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="8fd56-119">Beim Installieren der MSI-Datei werden Sie möglicherweise aufgefordert, Surface neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="8fd56-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="8fd56-120">Ein Neustart ist jedoch nicht erforderlich, um das Update durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="8fd56-121">Trennen Sie das Surface-Gerät vom Surface Dock (mit dem Netzteil), warten Sie 5 Sekunden, und stellen Sie die Verbindung wieder her.</span><span class="sxs-lookup"><span data-stu-id="8fd56-121">Disconnect your Surface device from the Surface Dock (using the power adapter), wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="8fd56-122">Mit dem Firmware-Update für Surface Dock wird das Dock im Hintergrund automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="8fd56-123">Es kann einige Minuten dauern, bis der Vorgang abgeschlossen ist, und wird auch dann fortgesetzt, wenn er unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="8fd56-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="8fd56-124">Überwachen des Firmware-Updates für Surface Dock</span><span class="sxs-lookup"><span data-stu-id="8fd56-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="8fd56-125">Dieser Abschnitt ist optional und bietet eine Übersicht über das Überwachen der Installation des Firmware-Updates.</span><span class="sxs-lookup"><span data-stu-id="8fd56-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="8fd56-126">So überwachen Sie das Update:</span><span class="sxs-lookup"><span data-stu-id="8fd56-126">To monitor the update:</span></span>

1. <span data-ttu-id="8fd56-127">Öffnen Sie die Ereignisanzeige, navigieren Sie zu **Windows-Protokollen > Anwendung**, und klicken Sie dann im rechten Bereich unter **Aktionen** auf **Aktuelles Protokoll filtern**, geben Sie **SurfaceDockFwUpdate** neben **Ereignisquellen**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fd56-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="8fd56-128">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="8fd56-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="8fd56-129">Installieren Sie das Update wie im [nächsten Abschnitt](#install-the-surface-dock-firmware-update) dieses Artikels beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fd56-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="8fd56-130">Das Ereignis 2007 mit dem folgenden Text zeigt eine erfolgreiche Aktualisierung an: das **Firmware-Update ist abgeschlossen. hr = 0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="8fd56-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="8fd56-131">Wenn das Update nicht erfolgreich ist, wird die Ereignis-ID 2007 als **Fehler** Ereignis anstelle von **Informationen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8fd56-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="8fd56-132">Darüber hinaus ist die in der Windows-Registrierung gemeldete Version nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="8fd56-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="8fd56-133">Nach Abschluss des Updates werden in der Windows-Registrierung aktualisierte DWORD-Werte angezeigt, die der aktuellen Version des Tools entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="8fd56-134">Weitere Informationen finden Sie im Abschnitt [Versions Referenz](#versions-reference) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="8fd56-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="8fd56-135">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8fd56-135">For example:</span></span>
    - <span data-ttu-id="8fd56-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="8fd56-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="8fd56-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="8fd56-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="8fd56-138">Wenn im Ereignistext die Meldung "die Beschreibung für die Ereignis-ID xxxx aus Quell-SurfaceDockFwUpdate nicht gefunden werden kann" angezeigt wird, wird dies erwartet und kann ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="8fd56-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="8fd56-139">Lesen Sie auch die folgenden Abschnitte in diesem Artikel:</span><span class="sxs-lookup"><span data-stu-id="8fd56-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="8fd56-140">Überprüfen des Abschlusses der Firmware-Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="8fd56-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="8fd56-141">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="8fd56-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="8fd56-142">Hinweise zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8fd56-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="8fd56-143">Versions Referenz</span><span class="sxs-lookup"><span data-stu-id="8fd56-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="8fd56-144">Netzwerkbereitstellung</span><span class="sxs-lookup"><span data-stu-id="8fd56-144">Network deployment</span></span>

<span data-ttu-id="8fd56-145">Sie können Windows Installer-Befehle (Msiexec.exe) verwenden, um das Surface Dock-Firmware-Update auf mehreren Geräten in Ihrem Netzwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="8fd56-146">Wenn Sie den Microsoft Endpoint Configuration Manager oder ein anderes Bereitstellungstool verwenden, geben Sie die folgende Syntax ein, um sicherzustellen, dass die Installation stumm ist:</span><span class="sxs-lookup"><span data-stu-id="8fd56-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="8fd56-147">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="8fd56-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="8fd56-148">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8fd56-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="8fd56-149">Standardmäßig wird keine Protokolldatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="8fd56-149">A log file is not created by default.</span></span> <span data-ttu-id="8fd56-150">Um eine Protokolldatei zu erstellen, müssen Sie "/l*v [path]" anfügen. Beispiel: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI. log "</span><span class="sxs-lookup"><span data-stu-id="8fd56-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="8fd56-151">Weitere Informationen finden Sie in der [Befehlszeilenoptionen](https://docs.microsoft.com/windows/win32/msi/command-line-options) -Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="8fd56-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fd56-152">Wenn Sie das Surface Dock mit einer anderen Methode aktualisieren möchten, finden Sie weitere Informationen unter [Aktualisieren des Surface Docks](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) .</span><span class="sxs-lookup"><span data-stu-id="8fd56-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="8fd56-153">InTune-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8fd56-153">Intune deployment</span></span>

<span data-ttu-id="8fd56-154">Sie können InTune verwenden, um das Firmware-Update für Surface Dock auf Ihre Geräte zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="8fd56-155">Zunächst müssen Sie die MSI-Datei in das intunewin-Format konvertieren, wie in der folgenden Dokumentation beschrieben: [InTune Standalone-Win32-App-Verwaltung](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="8fd56-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="8fd56-156">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="8fd56-156">Use the following command:</span></span>
  - **<span data-ttu-id="8fd56-157">msiexec/i \<path to msi file\> /quiet/q</span><span class="sxs-lookup"><span data-stu-id="8fd56-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="8fd56-158">Überprüfen des Abschlusses des Firmware-Updates</span><span class="sxs-lookup"><span data-stu-id="8fd56-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="8fd56-159">Die Surface Dock-Firmware besteht aus zwei Komponenten:</span><span class="sxs-lookup"><span data-stu-id="8fd56-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="8fd56-160">**Component10:** Mikrocontroller-Einheit (MCU)-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="8fd56-161">**Component20:** Display Port (DP)-Firmware.</span><span class="sxs-lookup"><span data-stu-id="8fd56-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="8fd56-162">Beim erfolgreichen Abschluss der Aktualisierung der Surface Dock-Firmware werden neue Registrierungsschlüsselwerte für diese Firmware-Komponenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8fd56-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="8fd56-163">So überprüfen Sie Updates:</span><span class="sxs-lookup"><span data-stu-id="8fd56-163">To verify updates:</span></span>**

1. <span data-ttu-id="8fd56-164">Öffnen Sie regedit, und navigieren Sie zum folgenden Registrierungspfad:</span><span class="sxs-lookup"><span data-stu-id="8fd56-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="8fd56-165">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="8fd56-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="8fd56-166">Suchen Sie nach den Registrierungsschlüsseln: **Component10CurrentFwVersion und Component20CurrentFwVersion**, die auf die aktuell auf dem Gerät befindliche Firmware verweisen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Installationsvorgang für Surface Dock-Firmware-Aktualisierung](images/regeditDock.png)

3. <span data-ttu-id="8fd56-168">Überprüfen Sie, ob die neuen Registrierungsschlüsselwerte den aktualisierten Registrierungsschlüsselwerten entsprechen, die im Versions Verweis am Ende dieses Dokuments aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="8fd56-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="8fd56-169">Wenn die Werte übereinstimmen, wurde die Firmware erfolgreich aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="8fd56-170">Wenn Sie nicht überprüft werden können, überprüfen Sie die Ereignisprotokollierung und die Tipps zur Problembehandlung im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="8fd56-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="8fd56-171">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="8fd56-171">Event logging</span></span>

**<span data-ttu-id="8fd56-172">Tabelle1.</span><span class="sxs-lookup"><span data-stu-id="8fd56-172">Table 1.</span></span> <span data-ttu-id="8fd56-173">Protokolldateien für das Surface Dock-Firmware-Update</span><span class="sxs-lookup"><span data-stu-id="8fd56-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="8fd56-174">Log</span><span class="sxs-lookup"><span data-stu-id="8fd56-174">Log</span></span>                              | <span data-ttu-id="8fd56-175">Pfad</span><span class="sxs-lookup"><span data-stu-id="8fd56-175">Location</span></span>                               | <span data-ttu-id="8fd56-176">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="8fd56-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="8fd56-177">Firmware-Update Protokoll für Surface Dock</span><span class="sxs-lookup"><span data-stu-id="8fd56-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="8fd56-178">Pfad muss angegeben werden (siehe Hinweis)</span><span class="sxs-lookup"><span data-stu-id="8fd56-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="8fd56-179">In früheren Versionen dieses Tools wurden Ereignisse in Anwendungen und Dienste Logs\Microsoft Surface Dock-Updater geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fd56-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="8fd56-180">Windows-Geräte Installationsprotokoll</span><span class="sxs-lookup"><span data-stu-id="8fd56-180">Windows Device Install log</span></span>       | <span data-ttu-id="8fd56-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="8fd56-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="8fd56-182">Weitere Informationen zur Verwendung des Geräte Installationsprotokolls finden Sie in der [Setupapi](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) -Protokoll Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="8fd56-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="8fd56-183">Tabelle 2</span><span class="sxs-lookup"><span data-stu-id="8fd56-183">Table 2.</span></span> <span data-ttu-id="8fd56-184">Ereignisprotokoll-IDs für das Surface Dock-Firmware-Update</span><span class="sxs-lookup"><span data-stu-id="8fd56-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="8fd56-185">Ereignisse werden im Anwendungsereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="8fd56-186">Hinweis: frühere Versionen dieses Tools haben Ereignisse in Anwendungen und Dienste Logs\Microsoft Surface Dock-Updater geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fd56-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="8fd56-187">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8fd56-187">Event ID</span></span> | <span data-ttu-id="8fd56-188">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="8fd56-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="8fd56-189">2001</span><span class="sxs-lookup"><span data-stu-id="8fd56-189">2001</span></span>     | <span data-ttu-id="8fd56-190">Das Dock-Firmware-Update wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="8fd56-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="8fd56-191">2002</span><span class="sxs-lookup"><span data-stu-id="8fd56-191">2002</span></span>     | <span data-ttu-id="8fd56-192">Die Dock-Firmware-Aktualisierung wurde übersprungen, da Dock bekanntermaßen auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="8fd56-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="8fd56-193">2003</span><span class="sxs-lookup"><span data-stu-id="8fd56-193">2003</span></span>     | <span data-ttu-id="8fd56-194">Bei der Aktualisierung der Dock-Firmware konnte keine Firmware-Version abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8fd56-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="8fd56-195">2004</span><span class="sxs-lookup"><span data-stu-id="8fd56-195">2004</span></span>     | <span data-ttu-id="8fd56-196">Abfrage der Firmware-Version.</span><span class="sxs-lookup"><span data-stu-id="8fd56-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="8fd56-197">2005</span><span class="sxs-lookup"><span data-stu-id="8fd56-197">2005</span></span>     | <span data-ttu-id="8fd56-198">Die Dock-Firmware konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="8fd56-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="8fd56-199">2006</span><span class="sxs-lookup"><span data-stu-id="8fd56-199">2006</span></span>     | <span data-ttu-id="8fd56-200">Fehler beim Senden von Angebot/Nutzlast-Paaren.</span><span class="sxs-lookup"><span data-stu-id="8fd56-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="8fd56-201">2007</span><span class="sxs-lookup"><span data-stu-id="8fd56-201">2007</span></span>     | <span data-ttu-id="8fd56-202">Firmware-Aktualisierung ist nicht mehr erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8fd56-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="8fd56-203">2008</span><span class="sxs-lookup"><span data-stu-id="8fd56-203">2008</span></span>     | <span data-ttu-id="8fd56-204">Beginnen Sie mit der Dock Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="8fd56-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="8fd56-205">2011</span><span class="sxs-lookup"><span data-stu-id="8fd56-205">2011</span></span>     | <span data-ttu-id="8fd56-206">Beenden der Dock-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="8fd56-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="8fd56-207">Hinweise zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8fd56-207">Troubleshooting tips</span></span>

- <span data-ttu-id="8fd56-208">Trennen Sie die Stromversorgung für Surface Dock komplett vom Netzteil, um die Surface-Docking-Station zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="8fd56-209">Trennen Sie alle Peripheriegeräte außer der Surface-Docking-Station.</span><span class="sxs-lookup"><span data-stu-id="8fd56-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="8fd56-210">Deinstallieren Sie das aktuelle Surface Dock-Firmware-Update, und installieren Sie dann die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="8fd56-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="8fd56-211">Stellen Sie sicher, dass die Surface-Docking-Station getrennt ist, und lassen Sie dann genügend Zeit für die Ausführung des Updates über eine LED im Ethernet-Port des Docks zu.</span><span class="sxs-lookup"><span data-stu-id="8fd56-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="8fd56-212">Warten Sie, bis die LED aufhört zu blinken, bevor Sie die Docking-Station aus dem Stromnetz ziehen.</span><span class="sxs-lookup"><span data-stu-id="8fd56-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="8fd56-213">Verbinden Sie das Surface Dock mit einem anderen Gerät, um festzustellen, ob es in der Lage ist, das Dock zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8fd56-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="8fd56-214">Versions Referenz</span><span class="sxs-lookup"><span data-stu-id="8fd56-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="8fd56-215">Die Installationsdatei wird mit dem folgenden Benennungsformat freigegeben: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) und wird standardmäßig auf C:\Program Files\SurfaceUpdate. installiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="8fd56-216">Version 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-216">Version 1.53.139.0</span></span>
*<span data-ttu-id="8fd56-217">Veröffentlichungsdatum: 4. August 2020</span><span class="sxs-lookup"><span data-stu-id="8fd56-217">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="8fd56-218">Diese Version des Surface Dock-Firmware-Updates enthält Fehlerbehebungen und Support für:</span><span class="sxs-lookup"><span data-stu-id="8fd56-218">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="8fd56-219">Aktualisieren des Surface Dock 1 mit Surface pro X</span><span class="sxs-lookup"><span data-stu-id="8fd56-219">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="8fd56-220">Wenn Sie Surface pro X ausführen, laden Sie die. ARM64-Build.</span><span class="sxs-lookup"><span data-stu-id="8fd56-220">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="8fd56-221">Verwenden Sie für alle anderen Geräte den amd64-Build.</span><span class="sxs-lookup"><span data-stu-id="8fd56-221">For all other devices, use the AMD64 build.</span></span> 
 


### <span data-ttu-id="8fd56-222">Version 1.42.139</span><span class="sxs-lookup"><span data-stu-id="8fd56-222">Version 1.42.139</span></span> 
*<span data-ttu-id="8fd56-223">Veröffentlichungsdatum: September 18 2019</span><span class="sxs-lookup"><span data-stu-id="8fd56-223">Release Date: September 18 2019</span></span>*

<span data-ttu-id="8fd56-224">Diese Version, die in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI enthalten ist, aktualisiert die Firmware im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="8fd56-224">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="8fd56-225">Aktualisierte Registrierungsschlüsselwerte:</span><span class="sxs-lookup"><span data-stu-id="8fd56-225">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="8fd56-226">Component10CurrentFwVersion auf **4ac3970**aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="8fd56-227">Component20CurrentFwVersion auf **4a1d570**aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8fd56-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="8fd56-228">Es wird Unterstützung für Surface pro 7 und Surface Laptop 3 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8fd56-228">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="8fd56-229">Legacy Versionen</span><span class="sxs-lookup"><span data-stu-id="8fd56-229">Legacy versions</span></span>

### <span data-ttu-id="8fd56-230">Version 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-230">Version 2.23.139.0</span></span>
*<span data-ttu-id="8fd56-231">Veröffentlichungsdatum: 10 Oktober 2018</span><span class="sxs-lookup"><span data-stu-id="8fd56-231">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="8fd56-232">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-232">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="8fd56-233">Unterstützung für Surface pro 6 hinzufügen</span><span class="sxs-lookup"><span data-stu-id="8fd56-233">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="8fd56-234">Unterstützung für Surface Laptop 2 hinzufügen</span><span class="sxs-lookup"><span data-stu-id="8fd56-234">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="8fd56-235">Version 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-235">Version 2.22.139.0</span></span>
*<span data-ttu-id="8fd56-236">Veröffentlichungsdatum: 26 Juli 2018</span><span class="sxs-lookup"><span data-stu-id="8fd56-236">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="8fd56-237">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-237">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="8fd56-238">Höhere Zuverlässigkeit der Updates</span><span class="sxs-lookup"><span data-stu-id="8fd56-238">Increase update reliability</span></span>
- <span data-ttu-id="8fd56-239">Hinzufügen von Unterstützung für Surface go</span><span class="sxs-lookup"><span data-stu-id="8fd56-239">Add support for Surface Go</span></span>

### <span data-ttu-id="8fd56-240">Version2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-240">Version 2.12.136.0</span></span>
*<span data-ttu-id="8fd56-241">Veröffentlichungsdatum: 29.Januar2018</span><span class="sxs-lookup"><span data-stu-id="8fd56-241">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="8fd56-242">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-242">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="8fd56-243">Update für Surface Dock Hauptchipsatz-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-243">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="8fd56-244">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-244">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="8fd56-245">Verbesserte Anzeigestabilität für externe Displays bei Verwendung mit Surface Book oder Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="8fd56-245">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="8fd56-246">Darüber hinaus umfasst die Installation dieser Version von Surface Dock Updater auf Surface Book-Geräten Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8fd56-246">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="8fd56-247">Update für Surface Book Basis-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-247">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="8fd56-248">Neue Unterstützung für Surface Dock Firmware-Updates mit Verbesserungen für Surface Book-Geräte</span><span class="sxs-lookup"><span data-stu-id="8fd56-248">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="8fd56-249">Version2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-249">Version 2.9.136.0</span></span>
*<span data-ttu-id="8fd56-250">Veröffentlichungsdatum: 3. November2017</span><span class="sxs-lookup"><span data-stu-id="8fd56-250">Release date: November 3, 2017</span></span>*

<span data-ttu-id="8fd56-251">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-251">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="8fd56-252">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-252">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="8fd56-253">Behebt ein Problem bei der Audiowiedergabe über passive Anzeigeport-Adapter</span><span class="sxs-lookup"><span data-stu-id="8fd56-253">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="8fd56-254">Version2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-254">Version 2.1.15.0</span></span>
*<span data-ttu-id="8fd56-255">Veröffentlichungsdatum: 19.06.2017</span><span class="sxs-lookup"><span data-stu-id="8fd56-255">Release date: June 19, 2017</span></span>*

<span data-ttu-id="8fd56-256">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-256">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="8fd56-257">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="8fd56-257">Surface Laptop</span></span>
* <span data-ttu-id="8fd56-258">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8fd56-258">Surface Pro</span></span>

### <span data-ttu-id="8fd56-259">Version2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-259">Version 2.1.6.0</span></span>
*<span data-ttu-id="8fd56-260">Veröffentlichungsdatum: 7.April2017</span><span class="sxs-lookup"><span data-stu-id="8fd56-260">Release date: April 7, 2017</span></span>*

<span data-ttu-id="8fd56-261">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-261">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="8fd56-262">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-262">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="8fd56-263">Erfordert Windows10</span><span class="sxs-lookup"><span data-stu-id="8fd56-263">Requires Windows 10</span></span>

### <span data-ttu-id="8fd56-264">Version2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-264">Version 2.0.22.0</span></span>
*<span data-ttu-id="8fd56-265">Veröffentlichungsdatum: 21.Oktober2016</span><span class="sxs-lookup"><span data-stu-id="8fd56-265">Release date: October 21, 2016</span></span>*

<span data-ttu-id="8fd56-266">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-266">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="8fd56-267">Update für SurfaceDock-USB-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-267">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="8fd56-268">Verbesserte Zuverlässigkeit von Ethernet-, Audio- und USB-Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="8fd56-268">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="8fd56-269">Version1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="8fd56-269">Version 1.0.8.0</span></span>
*<span data-ttu-id="8fd56-270">Veröffentlichungsdatum: 26.April2016</span><span class="sxs-lookup"><span data-stu-id="8fd56-270">Release date: April 26, 2016</span></span>*

<span data-ttu-id="8fd56-271">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="8fd56-271">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="8fd56-272">Firmwareupdate für Surface Dock Main-Chipsatz</span><span class="sxs-lookup"><span data-stu-id="8fd56-272">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="8fd56-273">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="8fd56-273">Update for Surface Dock DisplayPort firmware</span></span>

