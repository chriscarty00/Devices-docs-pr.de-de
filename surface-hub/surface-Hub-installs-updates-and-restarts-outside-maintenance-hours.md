---
title: Surface Hub installiert möglicherweise Updates und könnte außerhalb der Wartungszeiten neu starten
description: Informationen zur Problembehandlung für Surface Hub bezüglich automatischer Updates
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Surface Hub, Wartungsfenster, aktualisieren
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833820"
---
# <span data-ttu-id="9f3ff-104">Surface Hub installiert möglicherweise Updates und könnte außerhalb der Wartungszeiten neu starten</span><span class="sxs-lookup"><span data-stu-id="9f3ff-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="9f3ff-105">Unter bestimmten Umständen installiert Surface Hub Updates während der Geschäftszeiten anstatt während des normalen Wartungsfensters.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="9f3ff-106">Wenn dies erforderlich ist, wird das Gerät neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="9f3ff-107">Sie können das Gerät erst dann verwenden, wenn der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="9f3ff-108">Dieses Verhalten wird nicht erwartet, wenn ein Wartungsfenster fehlt.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="9f3ff-109">Sie tritt nur auf, wenn das Gerät lange Zeit veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="9f3ff-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="9f3ff-110">Cause</span></span>
<span data-ttu-id="9f3ff-111">Um sicherzustellen, dass Surface Hub während der Geschäftszeiten zur Verwendung zur Verfügung steht, ist der Hub für die Ausführung von administrativen Funktionen während eines in den Einstellungen definierten Wartungsfensters konfiguriert (siehe "Verweise" unten).</span><span class="sxs-lookup"><span data-stu-id="9f3ff-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="9f3ff-112">Während dieses Wartungszeitraums installiert der Hub automatisch alle verfügbaren Updates über Windows Update oder Windows Server Update Service (WSUS).</span><span class="sxs-lookup"><span data-stu-id="9f3ff-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="9f3ff-113">Sobald Updates abgeschlossen sind, kann der Hub neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="9f3ff-114">Updates können nur im Wartungsfenster installiert werden, wenn der Surface-Hub aktiviert, aber nicht verwendet oder reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="9f3ff-115">Wenn der Surface-Hub beispielsweise für eine Besprechung geplant ist, die 24 Stunden dauert, werden alle Updates, die für die Installation geplant sind, verzögert, bis der Hub im nächsten Wartungsfenster verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="9f3ff-116">Wenn der Hub weiterhin ausgelastet ist und mehrere Wartungsfenster nicht vorhanden ist, beginnt der Hub schließlich mit der Installation und dem Herunterladen von Updates.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="9f3ff-117">Dies kann während oder außerhalb des Wartungsfensters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="9f3ff-118">Nachdem der Download und die Installation begonnen haben, kann das Gerät neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="9f3ff-119">So vermeiden Sie dieses Problem</span><span class="sxs-lookup"><span data-stu-id="9f3ff-119">To avoid this issue</span></span>

<span data-ttu-id="9f3ff-120">Es ist wichtig, dass Sie die Wartungszeit für Surface Hub beiseite legen, um administrative Funktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="9f3ff-121">Das Reservieren des Surface Hub für 24-Stunden-Intervalle oder das Verwenden des Geräts während des Wartungsfensters verzögert die Installation von Updates.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="9f3ff-122">Wir empfehlen, den Hub während des geplanten Wartungszeitraums nicht zu verwenden oder zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="9f3ff-123">Ein zweistündiges Fenster sollte für die Aktualisierung reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="9f3ff-124">Eine Option, die Sie verwenden können, um die Verfügbarkeit von Updates zu steuern, ist der Windows Server Update-Dienst (WSUS).</span><span class="sxs-lookup"><span data-stu-id="9f3ff-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="9f3ff-125">WSUS bietet die Kontrolle darüber, welche Updates wann installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f3ff-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="9f3ff-126">Verweise</span><span class="sxs-lookup"><span data-stu-id="9f3ff-126">References</span></span> 
 
[<span data-ttu-id="9f3ff-127">Aktualisieren des Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9f3ff-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="9f3ff-128">Wartungsfenster</span><span class="sxs-lookup"><span data-stu-id="9f3ff-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="9f3ff-129">Bereitstellen von Windows10-Updates mit Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="9f3ff-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 


