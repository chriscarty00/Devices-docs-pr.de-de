---
title: Zurücksetzen oder Wiederherstellen eines Surface Hub
description: Beschreibt die Reset- und Wiederherstellungsprozesse für Surface Hub und enthält Anweisungen.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Zurücksetzen von Surface Hub, Wiederherstellen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406628"
---
# <a name="reset-or-recover-a-surface-hub"></a><span data-ttu-id="a6bc6-104">Zurücksetzen oder Wiederherstellen eines Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a6bc6-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="a6bc6-105">In diesem Artikel wird das Zurücksetzen oder Wiederherstellen eines Microsoft Surface beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="a6bc6-106">[Beim Zurücksetzen des Surface Hub](#reset-a-surface-hub) wird das Betriebssystem auf das letzte kumulative Windows-Update zurückgegeben, und alle lokalen Benutzerdateien und Konfigurationsinformationen werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="a6bc6-107">Die entfernten Informationen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a6bc6-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="a6bc6-108">das Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="a6bc6-108">The device account</span></span>
- <span data-ttu-id="a6bc6-109">Kontoinformationen für die lokalen Administratoren des Geräts</span><span class="sxs-lookup"><span data-stu-id="a6bc6-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="a6bc6-110">Informationen zum Domänen- oder Azure AD-Beitritt</span><span class="sxs-lookup"><span data-stu-id="a6bc6-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="a6bc6-111">Registrierungsinformationen zur Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="a6bc6-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="a6bc6-112">Konfigurationsinformationen, die mithilfe von MDM oder der Einstellungs-App festgelegt wurden</span><span class="sxs-lookup"><span data-stu-id="a6bc6-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="a6bc6-113">[Beim Wiederherstellen eines Surface Hub aus der Cloud](#recover-a-surface-hub-from-the-cloud) werden diese Informationen ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="a6bc6-114">Darüber hinaus lädt Surface Hub ein neues Betriebssystemimage herunter und installiert es.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="a6bc6-115">Sie können angeben, ob beim Wiederherstellungsprozess andere Informationen beibehalten werden, die auf dem Surface Hub gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="a6bc6-116">Dasselbe Betriebssystemimage wird vom [Surface Hub-Wiederherstellungstool](surface-hub-recovery-tool.md) verwendet, wenn Sie einen Surface Hub wiederherstellen müssen, für den keine dieser Optionen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <a name="reset-a-surface-hub"></a><span data-ttu-id="a6bc6-117">Zurücksetzen eines Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a6bc6-117">Reset a Surface Hub</span></span>

<span data-ttu-id="a6bc6-118">Möglicherweise müssen Sie Ihren Surface Hub aus folgenden Gründen zurücksetzen:</span><span class="sxs-lookup"><span data-stu-id="a6bc6-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="a6bc6-119">Sie müssen das Gerät für einen neuen Besprechungsraum neu löschen und neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="a6bc6-120">Sie möchten die lokale Verwaltung des Geräts ändern.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="a6bc6-121">Der Benutzername oder das Kennwort für das Gerätekonto oder das Administratorkonto ist verloren gegangen.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="a6bc6-122">Nach der Installation eines Updates nimmt die Leistung des Geräts ab.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="a6bc6-123">Wenn während des Zurücksetzens ein leerer Bildschirm für längere Zeit angezeigt wird, warten Sie, und ergreifen Sie keine Aktion.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="a6bc6-124">Die Gerätezurücksetzung kann bis zu sechs Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="a6bc6-125">Deaktivieren oder trennen Sie den Surface Hub erst, wenn der Prozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="a6bc6-126">Wenn Sie den Prozess unterbrechen, ist das Gerät nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="a6bc6-127">Das Gerät erfordert einen Garantiedienst, um wieder funktionsfähig zu werden.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="a6bc6-128">Öffnen Sie **Einstellungen** auf dem Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-128">On your Surface Hub, open **Settings**.</span></span>

   ![Abbildung, die die Einstellungs-App für Surface Hub zeigt.](images/sh-settings.png)

2. <span data-ttu-id="a6bc6-130">Wählen **Sie Update & Security aus.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-130">Select **Update & Security**.</span></span>

   ![Abbildung, die update & security group in Settings app for Surface Hub zeigt.](images/sh-settings-update-security.png)

3. <span data-ttu-id="a6bc6-132">Wählen **Sie Wiederherstellung**aus, und wählen Sie dann unter **Gerät zurücksetzen**die Option Erste Schritte **aus.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a6bc6-133">Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, wie Sie später dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="a6bc6-134">Weitere Informationen finden Sie [unter Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a6bc6-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="a6bc6-135">Wenn der Hub mit der Wiederherstellungspartition neu gestartet wird, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="a6bc6-136">Wenn Sie diese Eingabeaufforderung überspringen, wird die Zurücksetzung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Abbildung, die die Option Geräte zurücksetzen in der App Einstellungen für Surface Hub zeigt.](images/sh-settings-reset-device.png)

   <span data-ttu-id="a6bc6-138">Nach Abschluss des Zurücksetzens startet Surface Hub das [erste Ausführungsprogramm](first-run-program-surface-hub.md) erneut.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="a6bc6-139">Wenn beim Zurücksetzen ein Problem besteht, wird der Surface Hub wieder auf das zuvor vorhandene Betriebssystemimage zurückgesetzt und dann der Willkommensbildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a><span data-ttu-id="a6bc6-140">Wiederherstellen von Surface Hub-Gerät aus der Cloud</span><span class="sxs-lookup"><span data-stu-id="a6bc6-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="a6bc6-141">Wenn der Surface Hub aus einem bestimmten Grund nicht mehr verwendet werden kann, können Sie ihn ohne Unterstützung durch den Microsoft Support weiterhin aus der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="a6bc6-142">Der Surface Hub kann ein neues Betriebssystemimage aus der Cloud herunterladen und dieses Image verwenden, um das Betriebssystem neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="a6bc6-143">Möglicherweise müssen Sie diese Art von Wiederherstellungsprozess unter den folgenden Umständen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a6bc6-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="a6bc6-144">Surface Hub oder die zugehörigen Konten haben einen instabilen Zustand</span><span class="sxs-lookup"><span data-stu-id="a6bc6-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="a6bc6-145">Der Surface Hub ist gesperrt</span><span class="sxs-lookup"><span data-stu-id="a6bc6-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="a6bc6-146">Für **die Wiederherstellung aus dem Cloudprozess** ist eine verkabelte Verbindung erforderlich, die eine offene Internetverbindung bietet (keine Proxy- oder andere Authentifizierungsaufforderungen).</span><span class="sxs-lookup"><span data-stu-id="a6bc6-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <a name="recover-a-surface-hub-in-a-bad-state"></a><span data-ttu-id="a6bc6-147">Wiederherstellen von Surface Hub in einem fehlerhaften Zustand</span><span class="sxs-lookup"><span data-stu-id="a6bc6-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="a6bc6-148">Wenn das Gerätekonto in einen instabilen Zustand gerät oder wenn beim Administratorkonto Probleme auftreten, können Sie die App Einstellungen verwenden, um den Cloudwiederherstellungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="a6bc6-149">Sie sollten den Cloudwiederherstellungsprozess nur verwenden, [wenn](#reset-a-surface-hub) das Problem durch den Gerätezurücksetzungsprozess nicht behoben wird.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="a6bc6-150">Wählen Sie auf Dem Surface Hub **einstellungen** &gt; **aktualisieren &** &gt; **Sicherheitswiederherstellung aus.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="a6bc6-151">Wählen **Sie unter Wiederherstellen aus der Cloud**die Option Jetzt neu starten **aus.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![Aus der Cloud wiederherstellen](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a><span data-ttu-id="a6bc6-153">Wiederherstellen eines gesperrten Surface Hub-Geräts</span><span class="sxs-lookup"><span data-stu-id="a6bc6-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="a6bc6-154">In seltenen Fällen kann für einen Surface Hub ein Fehler auftreten, während am Ende einer Sitzung Benutzer- und App-Daten bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="a6bc6-155">In diesem Fall wird das Gerät automatisch neu gestartet und versucht den Vorgang erneut.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="a6bc6-156">Wenn dieser Vorgang jedoch wiederholt fehlschlägt, wird das Gerät automatisch gesperrt, um Benutzerdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="a6bc6-157">Zum Entsperren müssen Sie [das Gerät](#reset-a-surface-hub) zurücksetzen oder, falls dies nicht funktioniert, aus der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="a6bc6-158">Suchen Sie den Netzschalter am unteren Rand von Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="a6bc6-159">Der Netzschalter befindet sich neben der Netzkabelverbindung.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="a6bc6-160">Weitere Informationen zum Netzschalter finden Sie im [Surface Hub Site Readiness Guide (PDF).](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="a6bc6-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="a6bc6-161">Während surface Hub den Willkommensbildschirm anzeigt, deaktivieren Sie den Surface Hub mithilfe des Netzschalters.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="a6bc6-162">Verwenden Sie den Netzschalter, um den Surface Hub wieder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="a6bc6-163">Das Gerät startet und zeigt den Surface Hub-Logo-Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="a6bc6-164">Wenn unter dem Surface Hub-Logo Spinnenpunkte angezeigt werden, verwenden Sie den Netzschalter, um den Surface Hub erneut zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="a6bc6-165">Wiederholen Sie Schritt 3 dreimal, oder bis der Surface Hub die Meldung "Automatische Reparatur vorbereiten" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="a6bc6-166">Nachdem diese Meldung angezeigt wurde, wird auf dem Surface Hub der Windows RE-Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

 
5. <span data-ttu-id="a6bc6-167">Wählen **Sie Zurücksetzen aus, um Windows erneut zu installieren.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-167">Select **Reset to re-install Windows**.</span></span> 
![Zurücksetzen auf Neuinstallation](images/recover-from-cloud.png)

8. <span data-ttu-id="a6bc6-169">Wählen Sie **Clouddownload aus.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-169">Select **Cloud download.**</span></span> 

   ![Clouddownload](images/recover-cloud-download.png)

>[!IMPORTANT]
><span data-ttu-id="a6bc6-171">Wenn eine Fehlermeldung angezeigt wird, die angibt, dass **der Download nicht möglich ist,** wählen Sie Abbrechen **aus,** und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-171">If you get an error message indicating **Unable to Download**, select **Cancel** and try again.</span></span>

9. <span data-ttu-id="a6bc6-172">Wählen **Sie Vollständiges Bereinigen des Laufwerks aus.**  
![ Wiederherstellen und vollständig bereinigtes Laufwerk</span><span class="sxs-lookup"><span data-stu-id="a6bc6-172">Select **Fully clean the drive.** 
![recover and fully clean drive</span></span>](images/recover-fully-clean-drive.png)

10. <span data-ttu-id="a6bc6-173">Sie werden **gefragt, ob Sie bereit sind, dieses Gerät zurückzusetzen?**.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-173">You will be asked **Are you ready to reset this device?**.</span></span> <span data-ttu-id="a6bc6-174">Wählen Sie **Zurücksetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-174">Select **Reset**.</span></span> 
![Zurücksetzen wiederherstellen und bestätigen](images/recover-confirm-reset.png)

11. <span data-ttu-id="a6bc6-176">Der Download beginnt, und der Wiederherstellungsprozess gibt das **Zurücksetzen dieses Geräts an.**</span><span class="sxs-lookup"><span data-stu-id="a6bc6-176">The download begins and the recovery process indicates **Resetting this device**.</span></span> 
![Wiederherstellung in Bearbeitung](images/recover-in-progress.png)

## <a name="contact-support"></a><span data-ttu-id="a6bc6-178">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="a6bc6-178">Contact Support</span></span>

<span data-ttu-id="a6bc6-179">Wenn Sie Fragen haben oder Hilfe benötigen, können Sie [eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="a6bc6-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a6bc6-180">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a6bc6-180">Related topics</span></span>

[<span data-ttu-id="a6bc6-181">Verwalten von Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a6bc6-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="a6bc6-182">Microsoft Surface Hub-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="a6bc6-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
