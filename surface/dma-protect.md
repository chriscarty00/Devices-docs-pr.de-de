---
title: Oberflächen DMA-Schutz
description: Dieser Artikel beschreibt den DMA-Schutz auf kompatiblen Surface-Geräten.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832848"
---
# <span data-ttu-id="972eb-103">DMA-Schutz auf Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="972eb-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="972eb-104">Der DMA-Schutz (Direct Memory Access) wurde entwickelt, um potenzielle Sicherheitsrisiken zu minimieren, die mit der Verwendung von wechselbaren SSDs oder externen Speichergeräten verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="972eb-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="972eb-105">Neuere Surface-Geräte verfügen standardmäßig über einen DMA-Schutz.</span><span class="sxs-lookup"><span data-stu-id="972eb-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="972eb-106">Dazu gehören Surface pro 7, Surface Laptop 3 und Surface pro X.  Um das vorhanden sein der DMA-Schutzfunktion auf Ihrem Gerät zu überprüfen, öffnen Sie System Informationen (**Start**  >  **msinfo32.exe**), wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="972eb-106">These include Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![System Informationen mit aktiviertem DMA-Schutz](images/systeminfodma.png)

<span data-ttu-id="972eb-108">Wenn eine bewegliche SSD-Oberfläche manipuliert wird, wird das Gerät die Stromversorgung abschalten.</span><span class="sxs-lookup"><span data-stu-id="972eb-108">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="972eb-109">Der resultierende Neustart bewirkt, dass UEFI den Arbeitsspeicher löscht, um alle restlichen Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="972eb-109">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
