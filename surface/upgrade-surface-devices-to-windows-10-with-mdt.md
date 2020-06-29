---
title: Aktualisieren von Surface-Geräten auf Windows 10 mit Microsoft Deployment Toolkit (Surface)
description: Erfahren Sie, wie Sie eine Windows 10-Upgrade-Bereitstellung auf Ihren Surface-Geräten durchführen.
keywords: Windows 10 Surface, Upgrade, anpassen, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833169"
---
# <span data-ttu-id="5e92e-104">Aktualisieren von Surface-Geräten auf Windows 10 mit Microsoft Deployment Toolkit</span><span class="sxs-lookup"><span data-stu-id="5e92e-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="5e92e-105">Betrifft</span><span class="sxs-lookup"><span data-stu-id="5e92e-105">Applies to</span></span>
- <span data-ttu-id="5e92e-106">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="5e92e-106">Surface Pro 6</span></span>
- <span data-ttu-id="5e92e-107">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="5e92e-107">Surface Laptop 2</span></span>
- <span data-ttu-id="5e92e-108">Surface Go</span><span class="sxs-lookup"><span data-stu-id="5e92e-108">Surface Go</span></span>
- <span data-ttu-id="5e92e-109">Surface Go mit LTE</span><span class="sxs-lookup"><span data-stu-id="5e92e-109">Surface Go with LTE</span></span>
- <span data-ttu-id="5e92e-110">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="5e92e-110">Surface Book 2</span></span>
- <span data-ttu-id="5e92e-111">Surface Pro mit LTE Advanced (Modell 1807)</span><span class="sxs-lookup"><span data-stu-id="5e92e-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="5e92e-112">Surface Pro (Modell 1796)</span><span class="sxs-lookup"><span data-stu-id="5e92e-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="5e92e-113">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="5e92e-113">Surface Laptop</span></span>
- <span data-ttu-id="5e92e-114">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="5e92e-114">Surface Studio</span></span>
- <span data-ttu-id="5e92e-115">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="5e92e-115">Surface Studio 2</span></span>
- <span data-ttu-id="5e92e-116">Surface Book</span><span class="sxs-lookup"><span data-stu-id="5e92e-116">Surface Book</span></span>
- <span data-ttu-id="5e92e-117">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="5e92e-117">Surface Pro 4</span></span>
- <span data-ttu-id="5e92e-118">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="5e92e-118">Surface 3 LTE</span></span>
- <span data-ttu-id="5e92e-119">Surface3</span><span class="sxs-lookup"><span data-stu-id="5e92e-119">Surface 3</span></span>
- <span data-ttu-id="5e92e-120">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="5e92e-120">Surface Pro 3</span></span>
- <span data-ttu-id="5e92e-121">Surface Pro 2</span><span class="sxs-lookup"><span data-stu-id="5e92e-121">Surface Pro 2</span></span>
- <span data-ttu-id="5e92e-122">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="5e92e-122">Surface Pro</span></span>
- <span data-ttu-id="5e92e-123">Windows 10</span><span class="sxs-lookup"><span data-stu-id="5e92e-123">Windows 10</span></span>

<span data-ttu-id="5e92e-124">Neben der herkömmlichen Bereitstellungsmethode von reimaging-Geräten können Administratoren, die Oberflächen-Devices mit Windows 8,1 oder Windows 10 upgraden möchten, die Möglichkeit haben, Upgrades bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5e92e-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="5e92e-125">Wenn Sie eine Upgrade-Bereitstellung durchführen, kann Windows 10 auf Geräte angewendet werden, ohne Benutzer, Apps oder Konfiguration zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="5e92e-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="5e92e-126">Die Benutzer der bereitgestellten Geräte können die Geräte einfach weiterhin mit den gleichen apps und Einstellungen verwenden, die Sie vor dem Upgrade verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="5e92e-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="5e92e-127">Aktuelle Informationen zum Upgrade von Surface-Geräten mit MDT finden Sie unter [Ausführen eines in-Place-Upgrades auf Windows 10 mit MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="5e92e-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

