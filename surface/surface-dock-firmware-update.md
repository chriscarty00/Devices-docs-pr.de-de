---
title: Microsoft Surface Dock 1-Firmwareupdate
description: In diesem Artikel wird erläutert, wie Microsoft Surface Dock Firmware Update zum Installieren und Verwalten der Firmware auf dem ursprünglichen Surface Dock 1 verwendet wird. Wenn sie auf Ihrem Surface Gerät installiert ist, werden Surface Dock 1-Geräte aktualisiert, die an Ihr Surface Gerät angeschlossen sind.
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319209"
---
# <span data-ttu-id="cc0c3-104">Microsoft Surface Dock Firmware Update</span><span class="sxs-lookup"><span data-stu-id="cc0c3-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc0c3-105">Dieser Artikel enthält technische Anweisungen für IT-Administratoren.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="cc0c3-106">Wenn Sie ein Privatbenutzer sind, lesen Sie die Informationen zum Aktualisieren der [Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)auf der Microsoft   Support-Website.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="cc0c3-107">Die Anweisungen auf der Supportwebsite sind mit den allgemeinen Installationsschritten unten identisch, aber dieser Artikel enthält zusätzliche Informationen zum Überwachen, Überprüfen und Bereitstellen des Updates auf mehreren Geräten in einem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="cc0c3-108">In diesem Artikel wird erläutert, wie Microsoft Surface Dock Firmware Update zum Installieren und Verwalten der Firmware auf dem ursprünglichen Surface Dock 1 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="cc0c3-109">Bei der Installation auf dem Surface-Gerät werden Surface Dock 1-Geräte aktualisiert, die an das Surface Gerät angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="cc0c3-110">Dieser Artikel gilt nicht für Surface Dock 2, das Updates automatisch über Windows Update oder mithilfe von Microsoft Endpoint Configuration Manager oder anderen MSI-Bereitstellungstools empfängt.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="cc0c3-111">Weitere Informationen finden Sie unter ["Neues" in Surface Dock.](surface-dock-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="cc0c3-112">Dieses Tool ersetzt das frühere Microsoft Surface Dock Updater-Tool, das zuvor als Teil der Surface Tools für die IT zum Download verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="cc0c3-113">Das frühere Tool hieß Surface_Dock_Updater_vx.xx.xxx.x.msi (wobei x die Versionsnummer angibt) und ist nicht mehr zum Download verfügbar und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="cc0c3-114">Installieren des Surface Dock Firmware Update</span><span class="sxs-lookup"><span data-stu-id="cc0c3-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="cc0c3-115">In diesem Abschnitt wird beschrieben, wie Sie das Firmwareupdate manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="cc0c3-116">Microsoft veröffentlicht regelmäßig neue Versionen des Surface Dock Firmware Update.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="cc0c3-117">Die MSI-Datei wird nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="cc0c3-118">Wenn Sie die MSI auf den Geräten von Surface bereitgestellt haben und eine neue Version der Firmware veröffentlicht wird, müssen Sie die neue Version bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="cc0c3-119">Laden Sie das Dock [Firmware Update Microsoft Surface herunter, und installieren Sie es.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="cc0c3-120">Das Update erfordert ein Surface-Gerät mit Windows 10, Version 1803 oder höher.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="cc0c3-121">Beim Installieren der MSI-Datei werden Sie möglicherweise aufgefordert, Surface neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="cc0c3-122">Ein Neustart ist jedoch nicht erforderlich, um das Update durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="cc0c3-123">Trennen Sie das #A0 von Surface Dock, warten Sie ca. 5 Sekunden, und stellen Sie dann erneut eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="cc0c3-124">Das Surface Dock Firmware Update aktualisiert das Dock automatisch im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="cc0c3-125">Der Vorgang kann einige Minuten dauern und wird auch dann fortgesetzt, wenn er unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="cc0c3-126">Überwachen des Surface Dock-Firmwareupdates</span><span class="sxs-lookup"><span data-stu-id="cc0c3-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="cc0c3-127">Dieser Abschnitt ist optional und bietet eine Übersicht über die Überwachung der Installation des Firmwareupdates.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="cc0c3-128">So überwachen Sie das Update:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-128">To monitor the update:</span></span>

1. <span data-ttu-id="cc0c3-129">Öffnen Sie die Ereignisanzeige, navigieren Sie zu **"Windows-Protokolle >-Anwendung",** und klicken Sie dann im rechten Bereich unter "Aktionen" auf "Aktuelles Protokoll **filtern",** geben Sie **"SurfaceDockFwUpdate"** neben **"Ereignisquellen"** ein, und klicken Sie dann auf **"OK".** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cc0c3-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="cc0c3-130">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="cc0c3-131">Installieren Sie das Update wie im [nächsten Abschnitt dieses](#install-the-surface-dock-firmware-update) Artikels beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="cc0c3-132">Ereignis 2007 mit dem folgenden Text weist auf ein erfolgreiches Update hin: **Firmwareupdate abgeschlossen. hr=0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="cc0c3-133">Wenn das Update nicht erfolgreich ist, wird die Ereignis-ID 2007 als Fehlerereignis und nicht als **Information angezeigt.** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cc0c3-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="cc0c3-134">Darüber hinaus ist die in der Registrierung von Windows gemeldete Version nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="cc0c3-135">Nach Abschluss des Updates werden aktualisierte DWORD-Werte in der Windows-Registrierung angezeigt, die der aktuellen Version des Tools entspricht.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="cc0c3-136">Weitere Informationen finden Sie im Abschnitt ["Versionsreferenz"](#versions-reference) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="cc0c3-137">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-137">For example:</span></span>

    - <span data-ttu-id="cc0c3-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="cc0c3-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="cc0c3-140">Wenn im Ereignistext "Die Beschreibung für die Ereignis-ID xxxx aus der SurfaceDockFwUpdate-Quelle wurde nicht gefunden" angezeigt wird, wird dies erwartet und kann ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="cc0c3-141">Weitere Informationen finden Sie in den folgenden Abschnitten in diesem Artikel:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="cc0c3-142">So überprüfen Sie den Abschluss des Firmwareupdates</span><span class="sxs-lookup"><span data-stu-id="cc0c3-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="cc0c3-143">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="cc0c3-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="cc0c3-144">Hinweise zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cc0c3-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="cc0c3-145">Versionsreferenz</span><span class="sxs-lookup"><span data-stu-id="cc0c3-145">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="cc0c3-146">Netzwerkbereitstellung</span><span class="sxs-lookup"><span data-stu-id="cc0c3-146">Network deployment</span></span>

<span data-ttu-id="cc0c3-147">Sie können Windows Installer-Befehle (Msiexec.exe) verwenden, um Surface Dock Firmware Update auf mehreren Geräten in Ihrem Netzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="cc0c3-148">Wenn Sie Microsoft Endpoint Configuration Manager oder ein anderes Bereitstellungstool verwenden, geben Sie die folgende Syntax ein, um sicherzustellen, dass die Installation automatisch ist:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="cc0c3-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="cc0c3-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="cc0c3-150">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="cc0c3-151">Eine Protokolldatei wird standardmäßig nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-151">A log file is not created by default.</span></span> <span data-ttu-id="cc0c3-152">Zum Erstellen einer Protokolldatei müssen Sie "/l*v [path]" anfügen. Beispiel: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span><span class="sxs-lookup"><span data-stu-id="cc0c3-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="cc0c3-153">Weitere Informationen finden Sie in der [Dokumentation zu Befehlszeilenoptionen.](https://docs.microsoft.com/windows/win32/msi/command-line-options)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc0c3-154">Wenn Sie Surface Dock mit einer anderen Methode aktualisieren möchten, finden Sie weitere Informationen unter ["Aktualisieren](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) von Surface Dock".</span><span class="sxs-lookup"><span data-stu-id="cc0c3-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="cc0c3-155">Bereitstellung von Intune</span><span class="sxs-lookup"><span data-stu-id="cc0c3-155">Intune deployment</span></span>

<span data-ttu-id="cc0c3-156">Sie können Intune verwenden, um Surface Dock Firmware Update auf Ihre Geräte zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="cc0c3-157">Zuerst müssen Sie die MSI-Datei in das .intunewin-Format konvertieren, wie in der folgenden Dokumentation beschrieben: [Intune Eigenständig – Win32-App-Verwaltung.](https://docs.microsoft.com/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="cc0c3-158">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-158">Use the following command:</span></span>
  - **<span data-ttu-id="cc0c3-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="cc0c3-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="cc0c3-160">So überprüfen Sie den Abschluss des Firmwareupdates</span><span class="sxs-lookup"><span data-stu-id="cc0c3-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="cc0c3-161">Die Surface Dock Firmware besteht aus zwei Komponenten:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="cc0c3-162">**Komponente10:** Firmware der Microcontrollereinheit (McU)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="cc0c3-163">**Komponente20:** Firmware des Anzeigeports (DP).</span><span class="sxs-lookup"><span data-stu-id="cc0c3-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="cc0c3-164">Der erfolgreiche Abschluss des Surface Dock Firmware Update führt zu neuen Registrierungsschlüsselwerten für diese Firmwarekomponenten.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="cc0c3-165">So überprüfen Sie Updates:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-165">To verify updates:</span></span>**

1. <span data-ttu-id="cc0c3-166">Öffnen Sie Regedit, und navigieren Sie zum folgenden Registrierungspfad:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="cc0c3-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="cc0c3-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="cc0c3-168">Suchen Sie nach den Registrierungsschlüsseln **Component10CurrentFwVersion und Component20CurrentFwVersion,** die auf die Firmware verweisen, die sich derzeit auf dem Gerät befindet.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Installationsvorgang für das Surface Dock Firmware Update](images/regeditDock.png)

3. <span data-ttu-id="cc0c3-170">Überprüfen Sie, ob die neuen Registrierungsschlüsselwerte mit den aktualisierten Registrierungsschlüsselwerten übereinstimmen, die in der Versionsreferenz am Ende dieses Dokuments aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="cc0c3-171">Wenn die Werte übereinstimmen, wurde die Firmware erfolgreich aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="cc0c3-172">Wenn die Überprüfung nicht möglich ist, lesen Sie die Tipps zur Ereignisprotokollierung und Problembehandlung im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="cc0c3-173">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="cc0c3-173">Event logging</span></span>

**<span data-ttu-id="cc0c3-174">Tabelle1.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-174">Table 1.</span></span> <span data-ttu-id="cc0c3-175">Protokolldateien für Surface Dock Firmware Update</span><span class="sxs-lookup"><span data-stu-id="cc0c3-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="cc0c3-176">Log</span><span class="sxs-lookup"><span data-stu-id="cc0c3-176">Log</span></span>                              | <span data-ttu-id="cc0c3-177">Pfad</span><span class="sxs-lookup"><span data-stu-id="cc0c3-177">Location</span></span>                               | <span data-ttu-id="cc0c3-178">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="cc0c3-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cc0c3-179">Surface Dock Firmware Update log</span><span class="sxs-lookup"><span data-stu-id="cc0c3-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="cc0c3-180">Pfad muss angegeben werden (siehe Hinweis)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="cc0c3-181">In früheren Versionen dieses Tools wurden Ereignisse in Anwendungs- und Dienstprotokolle\Microsoft Surface Dock Updater geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="cc0c3-182">Windows Device Install log</span><span class="sxs-lookup"><span data-stu-id="cc0c3-182">Windows Device Install log</span></span>       | <span data-ttu-id="cc0c3-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="cc0c3-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="cc0c3-184">Weitere Informationen zur Verwendung des Geräteinstallationsprotokolls finden Sie in der [SetupAPI-Protokollierungsdokumentation.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)</span><span class="sxs-lookup"><span data-stu-id="cc0c3-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="cc0c3-185">Tabelle 2</span><span class="sxs-lookup"><span data-stu-id="cc0c3-185">Table 2.</span></span> <span data-ttu-id="cc0c3-186">Ereignisprotokoll-IDs für Surface Dock Firmware Update</span><span class="sxs-lookup"><span data-stu-id="cc0c3-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="cc0c3-187">Ereignisse werden im Anwendungsereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="cc0c3-188">Hinweis: In früheren Versionen dieses Tools wurden Ereignisse in Anwendungs- und Dienstprotokolle\Microsoft Surface Dock Updater geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="cc0c3-189">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="cc0c3-189">Event ID</span></span> | <span data-ttu-id="cc0c3-190">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="cc0c3-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="cc0c3-191">2001</span><span class="sxs-lookup"><span data-stu-id="cc0c3-191">2001</span></span>     | <span data-ttu-id="cc0c3-192">Das Firmwareupdate für Dock wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="cc0c3-193">2002</span><span class="sxs-lookup"><span data-stu-id="cc0c3-193">2002</span></span>     | <span data-ttu-id="cc0c3-194">Dock Firmware update skipped because dock is known to be up to date.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="cc0c3-195">2003</span><span class="sxs-lookup"><span data-stu-id="cc0c3-195">2003</span></span>     | <span data-ttu-id="cc0c3-196">Fehler beim Herunterladen der Firmwareversion durch das Dock-Firmware-Update.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="cc0c3-197">2004</span><span class="sxs-lookup"><span data-stu-id="cc0c3-197">2004</span></span>     | <span data-ttu-id="cc0c3-198">Abfragen der Firmwareversion.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="cc0c3-199">2005</span><span class="sxs-lookup"><span data-stu-id="cc0c3-199">2005</span></span>     | <span data-ttu-id="cc0c3-200">Die Firmware von Dock konnte das Update nicht starten.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="cc0c3-201">2006</span><span class="sxs-lookup"><span data-stu-id="cc0c3-201">2006</span></span>     | <span data-ttu-id="cc0c3-202">Fehler beim Senden von Angebots-/Nutzlastpaaren.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="cc0c3-203">2007</span><span class="sxs-lookup"><span data-stu-id="cc0c3-203">2007</span></span>     | <span data-ttu-id="cc0c3-204">Das Firmwareupdate wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="cc0c3-205">2008</span><span class="sxs-lookup"><span data-stu-id="cc0c3-205">2008</span></span>     | <span data-ttu-id="cc0c3-206">BEGIN Dock-Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="cc0c3-207">2011</span><span class="sxs-lookup"><span data-stu-id="cc0c3-207">2011</span></span>     | <span data-ttu-id="cc0c3-208">End dock telemetry.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-208">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="cc0c3-209">Hinweise zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cc0c3-209">Troubleshooting tips</span></span>

- <span data-ttu-id="cc0c3-210">Trennen Sie die Stromversorgung für Surface Dock vollständig vom Netzstrom, um Surface Dock zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="cc0c3-211">Trennen Sie alle Peripheriegeräte mit Ausnahme von Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="cc0c3-212">Deinstallieren Sie alle aktuellen Surface Dock-Firmwareupdates, und installieren Sie dann die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="cc0c3-213">Stellen Sie sicher, dass das Surface Dock getrennt ist, und lassen Sie dann genügend Zeit, bis das Update wie über eine LED im Ethernetport des Docks überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="cc0c3-214">Warten Sie, bis die LED nicht mehr blinkt, bevor Sie Surface Dock von der Stromversorgung trennen.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="cc0c3-215">Verbinden Sie Surface Dock mit einem anderen Gerät, um zu sehen, ob das Dock aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="cc0c3-216">Versionsreferenz</span><span class="sxs-lookup"><span data-stu-id="cc0c3-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="cc0c3-217">Die Installationsdatei wird im folgenden Namensformat veröffentlicht: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (z. B. Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) und wird standardmäßig unter "C:\Programme\SurfaceUpdate" installiert.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="cc0c3-218">Version 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="cc0c3-219">Veröffentlichungsdatum: 4. August 2020</span><span class="sxs-lookup"><span data-stu-id="cc0c3-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="cc0c3-220">Diese Version des Surface #A0 enthält Fehlerbehebungen und Unterstützung für:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="cc0c3-221">Aktualisieren von Surface Dock 1 mit Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="cc0c3-222">Wenn Sie Surface Pro X ausführen, laden Sie das herunter. ARM64-Build.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="cc0c3-223">Verwenden Sie für alle anderen Geräte den AMD64-Build.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="cc0c3-224">Registrierungsschlüsselwerte</span><span class="sxs-lookup"><span data-stu-id="cc0c3-224">Registry key values</span></span>

<span data-ttu-id="cc0c3-225">Die Registrierungswerte, die den Status von Firmwareupdates angeben, sind gegenüber der vorherigen Version dieses Tools unverändert:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="cc0c3-226">Component10CurrentFwVersion wurde auf **4ac3970 aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="cc0c3-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="cc0c3-227">Component20CurrentFwVersion wurde auf **4a1d570 aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="cc0c3-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <span data-ttu-id="cc0c3-228">Version 1.42.139</span><span class="sxs-lookup"><span data-stu-id="cc0c3-228">Version 1.42.139</span></span> 
*<span data-ttu-id="cc0c3-229">Veröffentlichungsdatum: 18. September 2019</span><span class="sxs-lookup"><span data-stu-id="cc0c3-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="cc0c3-230">Diese version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="cc0c3-231">Aktualisierte Registrierungsschlüsselwerte</span><span class="sxs-lookup"><span data-stu-id="cc0c3-231">Updated registry key values</span></span>

- <span data-ttu-id="cc0c3-232">Component10CurrentFwVersion wurde auf **4ac3970 aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="cc0c3-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="cc0c3-233">Component20CurrentFwVersion wurde auf **4a1d570 aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="cc0c3-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="cc0c3-234">Es bietet Unterstützung für Surface Pro 7 und Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cc0c3-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="cc0c3-235">Legacyversionen</span><span class="sxs-lookup"><span data-stu-id="cc0c3-235">Legacy versions</span></span>

### <span data-ttu-id="cc0c3-236">Version 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="cc0c3-237">Veröffentlichungsdatum: 10. Oktober 2018</span><span class="sxs-lookup"><span data-stu-id="cc0c3-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="cc0c3-238">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="cc0c3-239">Hinzufügen von Unterstützung für Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="cc0c3-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="cc0c3-240">Hinzufügen von Unterstützung für Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="cc0c3-240">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="cc0c3-241">Version 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="cc0c3-242">Veröffentlichungsdatum: 26. Juli 2018</span><span class="sxs-lookup"><span data-stu-id="cc0c3-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="cc0c3-243">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="cc0c3-244">Erhöhen der Updatezuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="cc0c3-244">Increase update reliability</span></span>
- <span data-ttu-id="cc0c3-245">Hinzufügen von Unterstützung für Surface Go</span><span class="sxs-lookup"><span data-stu-id="cc0c3-245">Add support for Surface Go</span></span>

### <span data-ttu-id="cc0c3-246">Version2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="cc0c3-247">Veröffentlichungsdatum: 29.Januar2018</span><span class="sxs-lookup"><span data-stu-id="cc0c3-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="cc0c3-248">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="cc0c3-249">Update für Surface Dock Hauptchipsatz-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="cc0c3-250">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="cc0c3-251">Verbesserte Anzeigestabilität für externe Displays bei Verwendung mit Surface Book oder Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="cc0c3-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="cc0c3-252">Darüber hinaus umfasst die Installation dieser Version von Surface Dock Updater auf Surface Book-Geräten Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="cc0c3-253">Update für Surface Book Basis-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="cc0c3-254">Neue Unterstützung für Surface Dock Firmware-Updates mit Verbesserungen für Surface Book-Geräte</span><span class="sxs-lookup"><span data-stu-id="cc0c3-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="cc0c3-255">Version2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="cc0c3-256">Veröffentlichungsdatum: 3. November2017</span><span class="sxs-lookup"><span data-stu-id="cc0c3-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="cc0c3-257">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cc0c3-258">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="cc0c3-259">Behebt ein Problem bei der Audiowiedergabe über passive Anzeigeport-Adapter</span><span class="sxs-lookup"><span data-stu-id="cc0c3-259">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="cc0c3-260">Version2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="cc0c3-261">Veröffentlichungsdatum: 19.06.2017</span><span class="sxs-lookup"><span data-stu-id="cc0c3-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="cc0c3-262">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cc0c3-263">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="cc0c3-263">Surface Laptop</span></span>
* <span data-ttu-id="cc0c3-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="cc0c3-264">Surface Pro</span></span>

### <span data-ttu-id="cc0c3-265">Version2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="cc0c3-266">Veröffentlichungsdatum: 7.April2017</span><span class="sxs-lookup"><span data-stu-id="cc0c3-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="cc0c3-267">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cc0c3-268">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="cc0c3-269">Erfordert Windows10</span><span class="sxs-lookup"><span data-stu-id="cc0c3-269">Requires Windows 10</span></span>

### <span data-ttu-id="cc0c3-270">Version2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="cc0c3-271">Veröffentlichungsdatum: 21.Oktober2016</span><span class="sxs-lookup"><span data-stu-id="cc0c3-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="cc0c3-272">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cc0c3-273">Update für SurfaceDock-USB-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="cc0c3-274">Verbesserte Zuverlässigkeit von Ethernet-, Audio- und USB-Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="cc0c3-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="cc0c3-275">Version1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="cc0c3-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="cc0c3-276">Veröffentlichungsdatum: 26.April2016</span><span class="sxs-lookup"><span data-stu-id="cc0c3-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="cc0c3-277">Diese Version von Surface Dock Updater fügt Unterstützung für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc0c3-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cc0c3-278">Firmwareupdate für Surface Dock Main-Chipsatz</span><span class="sxs-lookup"><span data-stu-id="cc0c3-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="cc0c3-279">Update für Surface Dock DisplayPort-Firmware</span><span class="sxs-lookup"><span data-stu-id="cc0c3-279">Update for Surface Dock DisplayPort firmware</span></span>

