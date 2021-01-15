---
title: Surface DMA Protection
description: In diesem Artikel wird der Schutz vor Datenma auf kompatiblen Geräten mit Surface beschrieben.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270620"
---
# <span data-ttu-id="f33ac-103">DMA Protection auf Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="f33ac-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="f33ac-104">Der Direkte Speicherzugriffsschutz (Direct Memory Access, DMA) wurde entwickelt, um potenzielle Sicherheitsrisiken im Zusammenhang mit der Verwendung von Wechselmedien-SSDs oder externen Speichergeräten zu mindern.</span><span class="sxs-lookup"><span data-stu-id="f33ac-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="f33ac-105">Neuere Geräte verfügen über standardmäßig aktivierten DMA-Schutz.</span><span class="sxs-lookup"><span data-stu-id="f33ac-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="f33ac-106">Dazu gehören Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="f33ac-106">These include Surface Pro 7+.</span></span> <span data-ttu-id="f33ac-107">Surface Pro 7, Surface Laptop 3 und Surface Pro X.  Öffnen Sie zum Überprüfen des Vorhandenseins des Features für den DMA-Schutz auf Ihrem Gerät Systeminformationen (**Start**msinfo32.exe), wie in der  >  \*\* \*\*folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f33ac-107">Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Systeminformationen mit aktivierter DMA Protection](images/systeminfodma.png)

<span data-ttu-id="f33ac-109">Wenn ein austauschbares Surface-SSD manipuliert wird, wird das Gerät heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="f33ac-109">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="f33ac-110">Der resultierende Neustart bewirkt, dass UEFI den Arbeitsspeicher löscht, und alle verbleibenden Daten löschen.</span><span class="sxs-lookup"><span data-stu-id="f33ac-110">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
