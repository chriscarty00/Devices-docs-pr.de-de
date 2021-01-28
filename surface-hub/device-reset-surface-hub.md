---
title: Zurücksetzen oder Wiederherstellen eines Surface Hub
description: Beschreibt die Zurücksetzungs- und Wiederherstellungsprozesse für den Surface Hub und enthält Anweisungen.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Zurücksetzen von Surface Hub, Wiederherstellen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304818"
---
# <span data-ttu-id="72344-104">Zurücksetzen oder Wiederherstellen eines Surface Hub</span><span class="sxs-lookup"><span data-stu-id="72344-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="72344-105">In diesem Artikel wird das Zurücksetzen oder Wiederherstellen eines Microsoft Surface beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72344-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="72344-106">[Beim Zurücksetzen des Surface Hub](#reset-a-surface-hub) wird das Betriebssystem auf das letzte kumulative Windows Update zurückgegeben, und alle lokalen Benutzerdateien und Konfigurationsinformationen werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="72344-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="72344-107">Die entfernten Informationen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="72344-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="72344-108">das Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="72344-108">The device account</span></span>
- <span data-ttu-id="72344-109">Kontoinformationen für die lokalen Administratoren des Geräts</span><span class="sxs-lookup"><span data-stu-id="72344-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="72344-110">Domänen- oder Azure AD-Join-Informationen</span><span class="sxs-lookup"><span data-stu-id="72344-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="72344-111">Registrierungsinformationen zur mobilen Geräteverwaltung (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="72344-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="72344-112">Konfigurationsinformationen, die mithilfe von MDM oder der App "Einstellungen" festgelegt wurden</span><span class="sxs-lookup"><span data-stu-id="72344-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="72344-113">[Durch das Wiederherstellen eines Surface Hub aus der Cloud](#recover-a-surface-hub-from-the-cloud) werden diese Informationen ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="72344-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="72344-114">Darüber hinaus lädt der Surface Hub ein neues Betriebssystemimage herunter und installiert es.</span><span class="sxs-lookup"><span data-stu-id="72344-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="72344-115">Sie können angeben, ob beim Wiederherstellungsprozess andere Informationen beibehalten werden, die auf dem Surface Hub gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="72344-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="72344-116">Dasselbe Betriebssystemimage wird vom [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) verwendet, wenn Sie einen Surface Hub wiederherstellen müssen, für den keine dieser Optionen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="72344-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <span data-ttu-id="72344-117">Zurücksetzen eines Surface Hub</span><span class="sxs-lookup"><span data-stu-id="72344-117">Reset a Surface Hub</span></span>

<span data-ttu-id="72344-118">Möglicherweise müssen Sie den Surface Hub aus folgenden Gründen zurücksetzen:</span><span class="sxs-lookup"><span data-stu-id="72344-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="72344-119">Sie löschen das Gerät für einen neuen Besprechungsraum neu und möchten es neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="72344-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="72344-120">Sie möchten die lokale Verwaltung des Geräts ändern.</span><span class="sxs-lookup"><span data-stu-id="72344-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="72344-121">Der Benutzername oder das Kennwort für das Gerätekonto oder das Administratorkonto ist verloren gegangen.</span><span class="sxs-lookup"><span data-stu-id="72344-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="72344-122">Nach der Installation eines Updates nimmt die Leistung des Geräts ab.</span><span class="sxs-lookup"><span data-stu-id="72344-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="72344-123">Wenn während des Zurücksetzens für längere Zeit ein leerer Bildschirm angezeigt wird, warten Sie, und ergreifen Sie keine Aktion.</span><span class="sxs-lookup"><span data-stu-id="72344-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="72344-124">Der Zurücksetzen des Geräts kann bis zu sechs Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="72344-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="72344-125">Deaktivieren oder trennen Sie den Surface Hub erst, wenn der Prozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="72344-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="72344-126">Wenn Sie den Vorgang unterbrechen, ist das Gerät nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="72344-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="72344-127">Das Gerät erfordert einen Garantiedienst, um wieder funktionsfähig zu werden.</span><span class="sxs-lookup"><span data-stu-id="72344-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="72344-128">Öffnen Sie **Einstellungen** auf dem Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="72344-128">On your Surface Hub, open **Settings**.</span></span>

   ![Abbildung der Einstellungs-App für Surface Hub.](images/sh-settings.png)

2. <span data-ttu-id="72344-130">Wählen **Sie "Update & Security" aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-130">Select **Update & Security**.</span></span>

   ![Abbildung der Gruppe "Update & Security" in der App "Einstellungen" für Surface Hub.](images/sh-settings-update-security.png)

3. <span data-ttu-id="72344-132">Wählen **Sie "Wiederherstellung"** aus, und wählen Sie dann unter **"Gerät zurücksetzen"** die Option **"Erste Schritte" aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="72344-133">Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, da Sie später dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="72344-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="72344-134">Weitere Informationen finden Sie unter ["Speichern des BitLocker-Schlüssels".](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="72344-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="72344-135">Wenn der Hub mit der Wiederherstellungspartition neu startet, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="72344-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="72344-136">Wenn Sie diese Eingabeaufforderung überspringen, kann die Zurücksetzung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="72344-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Abbildung der Option "Gerät zurücksetzen" in der App "Einstellungen" für Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="72344-138">Nach Abschluss des Zurücksetzungsprozesses startet Surface Hub das Programm für die [erste Ausführung](first-run-program-surface-hub.md) erneut.</span><span class="sxs-lookup"><span data-stu-id="72344-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="72344-139">Wenn beim Zurücksetzen ein Problem besteht, wird der Surface Hub wieder auf das zuvor vorhandene Betriebssystemimage zurückgesetzt, und dann wird die Willkommensbildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72344-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="72344-140">Wiederherstellen von Surface Hub-Gerät aus der Cloud</span><span class="sxs-lookup"><span data-stu-id="72344-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="72344-141">Wenn der Surface Hub aus einem bestimmten Grund nicht mehr verwendet werden kann, können Sie ihn ohne Unterstützung des Microsoft Support weiterhin aus der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="72344-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="72344-142">Surface Hub kann ein neues Betriebssystemimage aus der Cloud herunterladen und dieses Image verwenden, um das Betriebssystem neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="72344-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="72344-143">Unter den folgenden Umständen müssen Sie diese Art von Wiederherstellungsprozess möglicherweise verwenden:</span><span class="sxs-lookup"><span data-stu-id="72344-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="72344-144">Der Surface Hub oder die zugehörigen Konten sind in einen instabilen Zustand bzw.</span><span class="sxs-lookup"><span data-stu-id="72344-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="72344-145">Surface Hub ist gesperrt</span><span class="sxs-lookup"><span data-stu-id="72344-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="72344-146">Für **die Wiederherstellung aus dem Cloudprozess** ist eine kabelgebundene Verbindung erforderlich, die eine offene Internetverbindung (kein Proxy oder andere Authentifizierungsaufforderungen) bietet.</span><span class="sxs-lookup"><span data-stu-id="72344-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="72344-147">Wiederherstellen von Surface Hub in einem fehlerhaften Zustand</span><span class="sxs-lookup"><span data-stu-id="72344-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="72344-148">Wenn das Gerätekonto instabil wird oder beim Administratorkonto Probleme auftreten, können Sie den Cloudwiederherstellungsprozess mithilfe der App "Einstellungen" starten.</span><span class="sxs-lookup"><span data-stu-id="72344-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="72344-149">Sie sollten den Cloudwiederherstellungsprozess nur verwenden, [wenn](#reset-a-surface-hub) das Problem beim Zurücksetzen des Geräts nicht behoben wird.</span><span class="sxs-lookup"><span data-stu-id="72344-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="72344-150">Wählen Sie auf dem Surface Hub **"Einstellungen** &gt; **aktualisieren" & Sicherheitswiederherstellung** &gt; **aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="72344-151">Wählen **Sie unter "Aus Der Cloud wiederherstellen"** die Option **"Jetzt neu starten" aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![Aus der Cloud wiederherstellen](images/recover-from-the-cloud.png)

### <span data-ttu-id="72344-153">Wiederherstellen eines gesperrten Surface Hub-Geräts</span><span class="sxs-lookup"><span data-stu-id="72344-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="72344-154">In seltenen Fällen kann für einen Surface Hub ein Fehler auftreten, während am Ende einer Sitzung Benutzer- und App-Daten bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="72344-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="72344-155">In diesem Fall wird das Gerät automatisch neu gestartet und versucht, den Vorgang erneut zu starten.</span><span class="sxs-lookup"><span data-stu-id="72344-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="72344-156">Wenn dieser Vorgang jedoch wiederholt fehlschlägt, wird das Gerät automatisch gesperrt, um Benutzerdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="72344-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="72344-157">Um es zu entsperren, müssen Sie das [Gerät](#reset-a-surface-hub) zurücksetzen oder, falls dies nicht funktioniert, es aus der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="72344-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="72344-158">Suchen Sie den Netzschalter unten im Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="72344-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="72344-159">Der Netzschalter befindet sich neben der Netzkabelverbindung.</span><span class="sxs-lookup"><span data-stu-id="72344-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="72344-160">Weitere Informationen zum Netzschalter finden Sie im [Surface Hub Site Readiness Guide (PDF).](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="72344-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="72344-161">Während der Surface Hub den Willkommensbildschirm anzeigt, verwenden Sie den Netzschalter, um den Surface Hub zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="72344-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="72344-162">Verwenden Sie den Netzschalter, um den Surface Hub wieder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="72344-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="72344-163">Das Gerät wird gestartet und zeigt den Surface Hub-Logo-Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="72344-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="72344-164">Wenn unter dem Surface Hub-Logo Sich drehende Punkte angezeigt werden, deaktivieren Sie den Surface Hub mithilfe des Netzschalters erneut.</span><span class="sxs-lookup"><span data-stu-id="72344-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="72344-165">Wiederholen Sie Schritt 3 dreimal, oder bis surface Hub die Meldung "Vorbereiten der automatischen Reparatur" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="72344-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="72344-166">Nachdem diese Meldung angezeigt wurde, zeigt der Surface Hub den Windows RE-Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="72344-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

5. <span data-ttu-id="72344-167">Wählen Sie **erweiterte Optionen aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-167">Select **Advanced Options**.</span></span>

6. <span data-ttu-id="72344-168">Wählen Sie **"Aus der Cloud wiederherstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-168">Select **Recover from the cloud**.</span></span> <span data-ttu-id="72344-169">(Optional können Sie **"Zurücksetzen" auswählen.**</span><span class="sxs-lookup"><span data-stu-id="72344-169">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="72344-170">Es wird **jedoch empfohlen, die Wiederherstellung** aus der Cloud zu verwenden.)</span><span class="sxs-lookup"><span data-stu-id="72344-170">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Wiederherstellen aus der Cloud](images/recover-from-cloud.png)
7. <span data-ttu-id="72344-172">Wenn Sie zur Eingabe des Bitlocker-Schlüssels aufgefordert werden, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="72344-172">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="72344-173">Um die Informationen zu erhalten, die Bitlocker auf dem Surface Hub schützt, geben Sie den Bitlocker-Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="72344-173">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="72344-174">Um die geschützten Informationen zu verwerfen, wählen **Sie "Dieses Laufwerk überspringen" aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-174">To discard the protected information, select **Skip this drive**</span></span>  

8. <span data-ttu-id="72344-175">Wenn Sie dazu aufgefordert werden, wählen Sie **"Neu installieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="72344-175">When you are prompted, select **Reinstall**.</span></span>

    ![Neuinstallation](images/reinstall.png)

9. <span data-ttu-id="72344-177">Wählen Sie "Ja" aus, um den Datenträger neu **zupartitionieren.**</span><span class="sxs-lookup"><span data-stu-id="72344-177">To repartition the disk, select **Yes**.</span></span>

   ![Neu partitionieren](images/repartition.png)

   <span data-ttu-id="72344-179">Zunächst lädt der Wiederherstellungsprozess das Betriebssystemimage aus der Cloud herunter.</span><span class="sxs-lookup"><span data-stu-id="72344-179">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![Wird heruntergeladen: 97&](images/recover-progress.png)

   <span data-ttu-id="72344-181">Wenn der Download abgeschlossen ist, stellt der Wiederherstellungsprozess den Surface Hub entsprechend den von Ihnen ausgewählten Optionen wieder bereit.</span><span class="sxs-lookup"><span data-stu-id="72344-181">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="72344-182">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="72344-182">Contact Support</span></span>

<span data-ttu-id="72344-183">Wenn Sie Fragen haben oder Hilfe benötigen, können [Sie eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="72344-183">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="72344-184">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="72344-184">Related topics</span></span>

[<span data-ttu-id="72344-185">Verwalten von Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="72344-185">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="72344-186">Microsoft Surface Hub-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="72344-186">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
