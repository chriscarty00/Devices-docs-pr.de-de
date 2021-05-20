---
title: Surface Hub installiert möglicherweise Updates und könnte außerhalb der Wartungszeiten neu starten
description: Problembehandlungsinformationen für Surface Hub zu automatischen Updates
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Surface Hub, Wartungsfenster, Update
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577025"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a><span data-ttu-id="ec2d6-104">Surface Hub installiert möglicherweise Updates und könnte außerhalb der Wartungszeiten neu starten</span><span class="sxs-lookup"><span data-stu-id="ec2d6-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="ec2d6-105">Unter bestimmten Umständen installiert Surface Hub Updates während der Geschäftszeiten statt während des regulären Wartungsfensters.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="ec2d6-106">Das Gerät wird dann bei Bedarf neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="ec2d6-107">Sie können das Gerät erst verwenden, wenn der Prozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="ec2d6-108">Dies ist nicht das erwartete Verhalten, wenn ein Wartungsfenster fehlt.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="ec2d6-109">Er tritt nur auf, wenn das Gerät für einen langen Zeitraum veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <a name="cause"></a><span data-ttu-id="ec2d6-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="ec2d6-110">Cause</span></span>

<span data-ttu-id="ec2d6-111">Um sicherzustellen, dass Surface Hub während der Geschäftszeiten zur Verfügung steht, ist der Hub so konfiguriert, dass verwaltungstechnische Funktionen während eines Wartungsfensters ausführen, das in Einstellungen definiert ist (siehe "Verweise", unten).</span><span class="sxs-lookup"><span data-stu-id="ec2d6-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="ec2d6-112">Während dieses Wartungszeitraums installiert der Hub alle verfügbaren Updates automatisch über Windows Update oder Windows Update for Business (WUfB).</span><span class="sxs-lookup"><span data-stu-id="ec2d6-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB).</span></span> <span data-ttu-id="ec2d6-113">Sobald Updates abgeschlossen sind, kann der Hub neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="ec2d6-114">Updates können während des Wartungsfensters nur installiert werden, wenn Surface Hub aktiviert, aber nicht verwendet oder reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="ec2d6-115">Wenn die Surface Hub beispielsweise für eine Besprechung geplant ist, die 24 Stunden dauert, werden alle updates, die installiert werden sollen, zurückgestellt, bis der Hub während des nächsten Wartungsfensters verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="ec2d6-116">Wenn der Hub weiterhin ausgelastet ist und mehrere Wartungsfenster fehlen, beginnt der Hub schließlich mit der Installation und dem Herunterladen von Updates.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="ec2d6-117">Dies kann während oder außerhalb des Wartungsfensters auftreten.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="ec2d6-118">Sobald der Download und die Installation begonnen haben, kann das Gerät neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-118">Once the download and installation has begun, the device may restart.</span></span>

## <a name="to-avoid-this-issue"></a><span data-ttu-id="ec2d6-119">So vermeiden Sie dieses Problem</span><span class="sxs-lookup"><span data-stu-id="ec2d6-119">To avoid this issue</span></span>

<span data-ttu-id="ec2d6-120">Es ist wichtig, dass Sie Wartungszeit für Surface Hub verwaltungstechnische Funktionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="ec2d6-121">Das Reservieren der Surface Hub 24-Stunden-Intervalle oder die Verwendung des Geräts während des Wartungsfensters verzögert die Installation von Updates.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="ec2d6-122">Es wird empfohlen, den Hub während des geplanten Wartungszeitraums nicht zu verwenden oder zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="ec2d6-123">Ein Zwei-Stunden-Fenster sollte für die Aktualisierung reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="ec2d6-124">Eine Option, mit der Sie die Verfügbarkeit von Updates steuern können, ist Windows Update for Business.</span><span class="sxs-lookup"><span data-stu-id="ec2d6-124">One option that you can use to control the availability of updates is Windows Update for Business.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ec2d6-125">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="ec2d6-125">Learn more</span></span>
 
- [<span data-ttu-id="ec2d6-126">Aktualisieren des Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ec2d6-126">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 
- [<span data-ttu-id="ec2d6-127">Wartungsfenster</span><span class="sxs-lookup"><span data-stu-id="ec2d6-127">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 
