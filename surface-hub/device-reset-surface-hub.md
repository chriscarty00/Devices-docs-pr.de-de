---
title: Zurücksetzen oder Wiederherstellen eines Surface-Hubs
description: Beschreibt die Zurücksetzungs-und Wiederherstellungsprozesse für den Surface Hub und enthält Anweisungen.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Oberflächen Nabe zurücksetzen, wiederherstellen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104817"
---
# <span data-ttu-id="4055f-104">Zurücksetzen oder Wiederherstellen eines Surface-Hubs</span><span class="sxs-lookup"><span data-stu-id="4055f-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="4055f-105">In diesem Artikel wird beschrieben, wie Sie einen Microsoft Surface-Hub zurücksetzen oder wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="4055f-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="4055f-106">[Beim Zurücksetzen des Surface-Hubs](#reset-a-surface-hub) wird sein Betriebssystem auf das letzte kumulative Windows-Update zurückgesetzt, und alle lokalen Benutzer Dateien und Konfigurationsinformationen werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="4055f-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="4055f-107">Die Informationen, die entfernt werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4055f-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="4055f-108">das Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="4055f-108">The device account</span></span>
- <span data-ttu-id="4055f-109">Kontoinformationen für die lokalen Administratoren des Geräts</span><span class="sxs-lookup"><span data-stu-id="4055f-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="4055f-110">Domain-Join-oder Azure AD-Join-Informationen</span><span class="sxs-lookup"><span data-stu-id="4055f-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="4055f-111">Informationen zur Mobile Device Management (MDM)-Registrierung</span><span class="sxs-lookup"><span data-stu-id="4055f-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="4055f-112">Konfigurationsinformationen, die mithilfe von MDM oder der Einstellungs-APP festgesetzt wurden</span><span class="sxs-lookup"><span data-stu-id="4055f-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="4055f-113">Wenn Sie [einen Surface-Hub aus der Cloud wiederherstellen](#recover-a-surface-hub-from-the-cloud) , werden diese Informationen ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="4055f-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="4055f-114">Darüber hinaus downloadet der Surface Hub ein neues Betriebssystemabbild und installiert es.</span><span class="sxs-lookup"><span data-stu-id="4055f-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="4055f-115">Sie können angeben, ob beim Wiederherstellungsvorgang andere Informationen beibehalten werden sollen, die auf dem Surface Hub gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4055f-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span>

## <span data-ttu-id="4055f-116">Zurücksetzen eines Surface-Hubs</span><span class="sxs-lookup"><span data-stu-id="4055f-116">Reset a Surface Hub</span></span>

<span data-ttu-id="4055f-117">Möglicherweise müssen Sie den Surface-Hub aus folgenden Gründen zurücksetzen:</span><span class="sxs-lookup"><span data-stu-id="4055f-117">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="4055f-118">Sie purposing das Gerät erneut für einen neuen Besprechungsraum und möchten es neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4055f-118">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="4055f-119">Sie möchten die lokale Verwaltung des Geräts ändern.</span><span class="sxs-lookup"><span data-stu-id="4055f-119">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="4055f-120">Der Benutzername oder das Kennwort für das Geräte Konto oder das Administrator Konto ging verloren.</span><span class="sxs-lookup"><span data-stu-id="4055f-120">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="4055f-121">Nachdem Sie ein Update installiert haben, sinkt die Leistung des Geräts.</span><span class="sxs-lookup"><span data-stu-id="4055f-121">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="4055f-122">Wenn während des Reset-Vorgangs ein leerer Bildschirm für längere Zeit angezeigt wird, warten Sie bitte, und nehmen Sie keine Aktion vor.</span><span class="sxs-lookup"><span data-stu-id="4055f-122">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="4055f-123">Der Geräte Zurücksetzungsvorgang kann bis zu sechs Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="4055f-123">The device reset process may take up to six hours.</span></span> <span data-ttu-id="4055f-124">Schalten Sie den Surface Hub erst ab, wenn Sie den Vorgang beenden.</span><span class="sxs-lookup"><span data-stu-id="4055f-124">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="4055f-125">Wenn Sie den Vorgang unterbrechen, wird das Gerät nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="4055f-125">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="4055f-126">Das Gerät erfordert Gewährleistungs Service, um wieder funktionsfähig zu werden.</span><span class="sxs-lookup"><span data-stu-id="4055f-126">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="4055f-127">Öffnen Sie **Einstellungen** auf dem Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="4055f-127">On your Surface Hub, open **Settings**.</span></span>

   ![Abbildung mit der Einstellungs-APP für Surface Hub](images/sh-settings.png)

1. <span data-ttu-id="4055f-129">Wählen Sie **Update & Security**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-129">Select **Update & Security**.</span></span>

   ![Abbildung, die das Update & Sicherheitsgruppe in der Einstellungs-APP für Surface Hub zeigt.](images/sh-settings-update-security.png)

1. <span data-ttu-id="4055f-131">Wählen Sie **Wiederherstellen**aus, und wählen Sie dann unter **Gerät zurücksetzen**die Option **Erste Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-131">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   ![Abbildung, die die Option "Gerät zurücksetzen" in der Einstellungs-APP für Surface Hub zeigt.](images/sh-settings-reset-device.png)

   <span data-ttu-id="4055f-133">Nachdem der Zurücksetzungsvorgang abgeschlossen ist, startet der Surface-Hub das [erste Ausführungsprogramm](first-run-program-surface-hub.md) erneut.</span><span class="sxs-lookup"><span data-stu-id="4055f-133">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="4055f-134">Wenn der Reset-Prozess auf ein Problem stößt, wird der Surface-Hub wieder auf das zuvor vorhandene Betriebssystembild gerollt und dann der Begrüßungsbildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4055f-134">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="4055f-135">Wiederherstellen von Surface Hub-Gerät aus der Cloud</span><span class="sxs-lookup"><span data-stu-id="4055f-135">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="4055f-136">Wenn der Surface-Hub aus irgendeinem Grund unbrauchbar wird, können Sie ihn weiterhin ohne Unterstützung durch den Microsoft-Support aus der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="4055f-136">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="4055f-137">Mit dem Surface Hub können Sie ein neues Betriebssystemabbild aus der Cloud herunterladen und dieses Bild verwenden, um das Betriebssystem neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4055f-137">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="4055f-138">Möglicherweise müssen Sie diese Art des Wiederherstellungsprozesses unter den folgenden Umständen verwenden:</span><span class="sxs-lookup"><span data-stu-id="4055f-138">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="4055f-139">Der Surface-Hub oder die zugehörigen Konten haben einen instabilen Zustand eingegeben.</span><span class="sxs-lookup"><span data-stu-id="4055f-139">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="4055f-140">Der Surface-Hub ist gesperrt</span><span class="sxs-lookup"><span data-stu-id="4055f-140">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="4055f-141">Der Prozess " **Wiederherstellen aus der Cloud** " erfordert eine Kabelverbindung, die eine offene Internetverbindung (keine Proxy-oder andere Authentifizierungs Aufforderungen) bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4055f-141">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="4055f-142">Wiederherstellen von Surface Hub in einem fehlerhaften Zustand</span><span class="sxs-lookup"><span data-stu-id="4055f-142">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="4055f-143">Wenn das Geräte Konto in einen instabilen Zustand gelangt oder wenn beim Administratorkonto Probleme auftreten, können Sie die app "Einstellungen" verwenden, um den Cloud-Wiederherstellungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="4055f-143">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="4055f-144">Sie sollten den Cloud-Wiederherstellungsprozess nur verwenden, wenn das Problem durch das [Zurücksetzen des Geräts](#reset-a-surface-hub) nicht behoben wird.</span><span class="sxs-lookup"><span data-stu-id="4055f-144">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="4055f-145">Wählen Sie auf dem Surface Hub die Option **Einstellungen** &gt; **Aktualisieren & Security** &gt; **Recovery**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-145">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

1. <span data-ttu-id="4055f-146">Wählen Sie unter **aus der Cloud wiederherstellen die**Option **jetzt neu starten**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-146">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![Aus der Cloud wiederherstellen](images/recover-from-the-cloud.png)

### <span data-ttu-id="4055f-148">Wiederherstellen eines gesperrten Surface Hub-Geräts</span><span class="sxs-lookup"><span data-stu-id="4055f-148">Recover a locked Surface Hub</span></span>

<span data-ttu-id="4055f-149">In seltenen Fällen kann für einen Surface Hub ein Fehler auftreten, während am Ende einer Sitzung Benutzer- und App-Daten bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="4055f-149">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="4055f-150">In diesem Fall wird das Gerät automatisch neu gestartet und versucht, den Vorgang erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4055f-150">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="4055f-151">Wenn dieser Vorgang jedoch wiederholt fehlschlägt, sperrt das Gerät automatisch, um Benutzerdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4055f-151">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="4055f-152">Wenn Sie die Sperre aufheben möchten, müssen Sie [das Gerät zurücksetzen](#reset-a-surface-hub) oder, falls das nicht funktioniert, es aus der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="4055f-152">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="4055f-153">Suchen Sie den Netzschalter an der Unterkante des Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="4055f-153">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="4055f-154">Der Netzschalter befindet sich neben dem Netzkabel.</span><span class="sxs-lookup"><span data-stu-id="4055f-154">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="4055f-155">Weitere Informationen zum Netzschalter finden Sie im [Readiness-Leitfaden zur Surface Hub-Website (PDF)](surface-hub-site-readiness-guide.md).</span><span class="sxs-lookup"><span data-stu-id="4055f-155">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

1. <span data-ttu-id="4055f-156">Wenn der Surface-Hub den Begrüßungsbildschirm anzeigt, verwenden Sie den Netzschalter, um den Surface Hub zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4055f-156">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

1. <span data-ttu-id="4055f-157">Verwenden Sie den Netzschalter, um den Surface Hub wieder einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="4055f-157">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="4055f-158">Das Gerät wird gestartet, und der Bildschirm des Surface Hub-Logos wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4055f-158">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="4055f-159">Wenn sich drehende Punkte unterhalb des Surface Hub-Logos befinden, verwenden Sie den Netzschalter, um den Surface Hub wieder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4055f-159">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

1. <span data-ttu-id="4055f-160">Wiederholen Sie den Schritt 3 3 Mal, oder bis der Surface-Hub die Meldung "Automatische Reparatur wird vorbereitet" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="4055f-160">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="4055f-161">Nachdem diese Meldung angezeigt wird, zeigt der Surface-Hub den Windows RE-Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="4055f-161">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

1. <span data-ttu-id="4055f-162">Wählen Sie **Erweiterte Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-162">Select **Advanced Options**.</span></span>

1. <span data-ttu-id="4055f-163">Wählen Sie **in der Cloud wiederherstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="4055f-163">Select **Recover from the cloud**.</span></span> <span data-ttu-id="4055f-164">(Optional können Sie " **Zurücksetzen**" auswählen.</span><span class="sxs-lookup"><span data-stu-id="4055f-164">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="4055f-165">Die **Wiederherstellung aus der Cloud** ist jedoch die empfohlene Vorgehensweise.)</span><span class="sxs-lookup"><span data-stu-id="4055f-165">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Wiederherstellen aus der Cloud](images/recover-from-cloud.png)
1. <span data-ttu-id="4055f-167">Wenn Sie aufgefordert werden, den BitLocker-Schlüssel einzugeben, führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4055f-167">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="4055f-168">Wenn Sie die Informationen beibehalten möchten, die BitLocker auf dem Surface-Hub schützt, geben Sie den BitLocker-Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="4055f-168">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="4055f-169">Wenn Sie die geschützten Informationen verwerfen möchten, wählen Sie **dieses Laufwerk überspringen** aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-169">To discard the protected information, select **Skip this drive**</span></span>  

1. <span data-ttu-id="4055f-170">Wenn Sie dazu aufgefordert werden, wählen Sie **erneut installieren**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-170">When you are prompted, select **Reinstall**.</span></span>

    ![Neuinstallation](images/reinstall.png)

1. <span data-ttu-id="4055f-172">Wenn Sie den Datenträger neu partitionieren möchten, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="4055f-172">To repartition the disk, select **Yes**.</span></span>

   ![Neu partitionieren](images/repartition.png)

   <span data-ttu-id="4055f-174">Zunächst downloadet der Wiederherstellungsvorgang das Betriebssystemabbild aus der Cloud.</span><span class="sxs-lookup"><span data-stu-id="4055f-174">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![Wird heruntergeladen: 97&](images/recover-progress.png)

   <span data-ttu-id="4055f-176">Wenn der Download abgeschlossen ist, stellt der Wiederherstellungsprozess den Surface-Hub entsprechend den von Ihnen ausgewählten Optionen wieder her.</span><span class="sxs-lookup"><span data-stu-id="4055f-176">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="4055f-177">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="4055f-177">Contact Support</span></span>

<span data-ttu-id="4055f-178">Wenn Sie Fragen haben oder Hilfe benötigen, können Sie [eine Supportanfrage erstellen](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="4055f-178">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="4055f-179">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4055f-179">Related topics</span></span>

[<span data-ttu-id="4055f-180">Verwalten von Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="4055f-180">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="4055f-181">Microsoft Surface Hub-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="4055f-181">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
