---
title: Windows 10 Team 2020 Update installieren
description: Hier erhalten Sie das neueste Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470413"
---
# <a name="install-windows-10-team-2020-update"></a><span data-ttu-id="26863-104">Windows 10 Team 2020 Update installieren</span><span class="sxs-lookup"><span data-stu-id="26863-104">Install Windows 10 Team 2020 Update</span></span> 

<span data-ttu-id="26863-105">Das neue Surface Hub-Betriebssystem, **Windows 10 Team 2020 Update,** basierend auf Windows 10, Version 20H2, ist jetzt für Surface Hub 2S und den ursprünglichen Surface Hub (v1) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26863-105">The new Surface Hub operating system, **Windows 10 Team 2020 Update**, based on Windows 10 version 20H2, is now available for Surface Hub 2S and the original Surface Hub (v1).</span></span> 

- <span data-ttu-id="26863-106">Siehe auch: [Bekannte Probleme: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="26863-106">See also: [Known issues: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)</span></span>

## <a name="distribution"></a><span data-ttu-id="26863-107">Verteilung</span><span class="sxs-lookup"><span data-stu-id="26863-107">Distribution</span></span>

<span data-ttu-id="26863-108">Sie können Windows 2020 Update mit einer der folgenden Methoden abrufen:</span><span class="sxs-lookup"><span data-stu-id="26863-108">You can obtain Windows 2020 Update using one of the following methods:</span></span>

- <span data-ttu-id="26863-109">**Windows Update for Business**.</span><span class="sxs-lookup"><span data-stu-id="26863-109">**Windows Update for Business**.</span></span>
- <span data-ttu-id="26863-110">**Bare Metal Recovery (BMR) Image**.</span><span class="sxs-lookup"><span data-stu-id="26863-110">**Bare metal recovery (BMR) image**.</span></span> <span data-ttu-id="26863-111">Empfohlene Option für Kunden, die ihre Geräte zu Azure Active Directory hinzufügen oder nicht zulassen, dass ihre Geräte Updates aus dem Internet erhalten.</span><span class="sxs-lookup"><span data-stu-id="26863-111">Recommended option for customers who join their devices to Azure Active Directory or don’t allow their devices to receive updates from the internet.</span></span> <span data-ttu-id="26863-112">Informationen zu den ersten Schritte finden Sie unter [Herunterladen eines Wiederherstellungsimages für Surface](https://support.microsoft.com/surfacerecoveryimage).</span><span class="sxs-lookup"><span data-stu-id="26863-112">To get started, see [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>
- **<span data-ttu-id="26863-113">WindowsUpdate.</span><span class="sxs-lookup"><span data-stu-id="26863-113">Windows Update.</span></span>** <span data-ttu-id="26863-114">Die Verfügbarkeit variiert je nach Region/Land, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="26863-114">Availability varies by region/country, as noted in the following table:</span></span>

| <span data-ttu-id="26863-115">Phase</span><span class="sxs-lookup"><span data-stu-id="26863-115">Phase</span></span> | <span data-ttu-id="26863-116">Land/Region</span><span class="sxs-lookup"><span data-stu-id="26863-116">Country/Region</span></span>                         | <span data-ttu-id="26863-117">Starten</span><span class="sxs-lookup"><span data-stu-id="26863-117">Starting</span></span>          |
| ----- | -------------------------------------- | ----------------- |
| <span data-ttu-id="26863-118">1</span><span class="sxs-lookup"><span data-stu-id="26863-118">1</span></span>     | <span data-ttu-id="26863-119">NZ, Australien, Kanada, Belgien, Mexiko</span><span class="sxs-lookup"><span data-stu-id="26863-119">NZ, Australia, Canada, Belgium, Mexico</span></span> | <span data-ttu-id="26863-120">Oktober 2020</span><span class="sxs-lookup"><span data-stu-id="26863-120">October 2020</span></span>  |
| <span data-ttu-id="26863-121">2</span><span class="sxs-lookup"><span data-stu-id="26863-121">2</span></span>     | <span data-ttu-id="26863-122">Großbritannien, Japan, Schweiz, Italien</span><span class="sxs-lookup"><span data-stu-id="26863-122">UK, Japan, Switzerland, Italy</span></span>          | <span data-ttu-id="26863-123">November 2020</span><span class="sxs-lookup"><span data-stu-id="26863-123">November 2020</span></span> |
| <span data-ttu-id="26863-124">3</span><span class="sxs-lookup"><span data-stu-id="26863-124">3</span></span>     | <span data-ttu-id="26863-125">Deutschland, Niederlande</span><span class="sxs-lookup"><span data-stu-id="26863-125">Germany, Netherlands</span></span>                   | <span data-ttu-id="26863-126">Ende Februar 2021</span><span class="sxs-lookup"><span data-stu-id="26863-126">Late February 2021</span></span> |
| <span data-ttu-id="26863-127">4</span><span class="sxs-lookup"><span data-stu-id="26863-127">4</span></span>     | <span data-ttu-id="26863-128">Global</span><span class="sxs-lookup"><span data-stu-id="26863-128">Global</span></span>                                 | <span data-ttu-id="26863-129">Anfang März 2021</span><span class="sxs-lookup"><span data-stu-id="26863-129">Early March 2021</span></span> |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a><span data-ttu-id="26863-130">Servicing Surface Hubs with Windows 10 Team Edition version 1703</span><span class="sxs-lookup"><span data-stu-id="26863-130">Servicing Surface Hubs with Windows 10 Team Edition version 1703</span></span> 

<span data-ttu-id="26863-131">Die vollständige Wartungsunterstützung [für Windows 10 Team Edition, Version 1703,](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) wird voraussichtlich bis zum 16. März 2021 fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="26863-131">Full servicing support for [Windows 10 Team Edition version 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) is scheduled to continue until March 16, 2021.</span></span>

### <a name="2s-devices"></a><span data-ttu-id="26863-132">2S-Geräte</span><span class="sxs-lookup"><span data-stu-id="26863-132">2S devices</span></span> 

<span data-ttu-id="26863-133">Kunden in allen Regionen können ihre Surface Hub 2S-Geräte auf das Update 2020 über Windows Update, Windows Update for Business oder mithilfe des Bare Metal Recovery (BMR)-Images aktualisieren, wie unter [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="26863-133">Customers in all regions can update their Surface Hub 2S devices to the 2020 Update through Windows Update, Windows Update for Business or by using the bare metal recovery (BMR) image, as explained in [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

### <a name="v1-devices"></a><span data-ttu-id="26863-134">V1-Geräte</span><span class="sxs-lookup"><span data-stu-id="26863-134">V1 devices</span></span> 

<span data-ttu-id="26863-135">Kunden in allen Regionen können ihre Surface Hub v1-Geräte über Windows Update, Windows Update for Business oder mithilfe des Surface Hub-Wiederherstellungstools auf das 2020 Update [aktualisieren.](surface-hub-recovery-tool.md)</span><span class="sxs-lookup"><span data-stu-id="26863-135">Customers in all regions can update their Surface Hub v1 devices to the 2020 Update through Windows Update, Windows Update for Business, or by [using the Surface Hub Recovery Tool](surface-hub-recovery-tool.md).</span></span> <span data-ttu-id="26863-136">KB5000749 muss installiert sein, um das Update über die Zeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="26863-136">KB5000749 must be installed in order to receive the update over-the-air.</span></span> <span data-ttu-id="26863-137">Weitere Informationen finden Sie unter [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).</span><span class="sxs-lookup"><span data-stu-id="26863-137">To learn more, see [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).</span></span>
 
## <a name="whats-new"></a><span data-ttu-id="26863-138">Neuigkeiten </span><span class="sxs-lookup"><span data-stu-id="26863-138">What’s new</span></span>

<span data-ttu-id="26863-139">Windows 10 Team 2020 Update bietet neben den neuesten Windows 10-Features wesentliche Verbesserungen bei der Gerätebereitstellung und Verwaltbarkeit.</span><span class="sxs-lookup"><span data-stu-id="26863-139">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="26863-140">Weitere Informationen finden Sie unter [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="26863-140">To learn more, see [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).</span></span>
 
## <a name="before-you-begin"></a><span data-ttu-id="26863-141">Vorbemerkungen</span><span class="sxs-lookup"><span data-stu-id="26863-141">Before you begin</span></span>

<span data-ttu-id="26863-142">Stellen Sie vor der Installation von Windows 10 Team 2020 Update sicher, dass Sie den Ihrem Gerät zugeordneten BitLocker-Schlüssel speichern.</span><span class="sxs-lookup"><span data-stu-id="26863-142">Prior to installing Windows 10 Team 2020 Update, make sure you save the BitLocker key associated with your device.</span></span> 

**<span data-ttu-id="26863-143">So speichern Sie den BitLocker-Schlüssel manuell</span><span class="sxs-lookup"><span data-stu-id="26863-143">To manually save your BitLocker key</span></span>**

1. <span data-ttu-id="26863-144">Fügen Sie ein USB-Laufwerk in Surface Hub ein.</span><span class="sxs-lookup"><span data-stu-id="26863-144">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="26863-145">Öffnen Sie auf Surface Hub **Einstellungen,** und geben Sie ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="26863-145">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="26863-146">Navigieren Sie zu **Update & Security**  >  **Recovery**.</span><span class="sxs-lookup"><span data-stu-id="26863-146">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="26863-147">Wählen **Sie unter BitLocker**die Option **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="26863-147">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="26863-148">Der BitLocker-Schlüssel wird in einer Textdatei auf dem USB-Laufwerk gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26863-148">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="26863-149">Weitere Informationen finden Sie [unter Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="26863-149">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="26863-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26863-150">Learn more</span></span>

- [<span data-ttu-id="26863-151">Neues in Windows10 Team2020-Update</span><span class="sxs-lookup"><span data-stu-id="26863-151">What's new in Windows 10 Team 2020 Update</span></span>](surface-hub-2020-update-whats-new.md)
- [<span data-ttu-id="26863-152">Aktualisieren auf das Windows 10 Team-Rollout</span><span class="sxs-lookup"><span data-stu-id="26863-152">Update to the Windows 10 Team rollout</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
