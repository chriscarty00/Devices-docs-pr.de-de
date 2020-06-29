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
# DMA-Schutz auf Surface-Geräten

Der DMA-Schutz (Direct Memory Access) wurde entwickelt, um potenzielle Sicherheitsrisiken zu minimieren, die mit der Verwendung von wechselbaren SSDs oder externen Speichergeräten verbunden sind. Neuere Surface-Geräte verfügen standardmäßig über einen DMA-Schutz. Dazu gehören Surface pro 7, Surface Laptop 3 und Surface pro X.  Um das vorhanden sein der DMA-Schutzfunktion auf Ihrem Gerät zu überprüfen, öffnen Sie System Informationen (**Start**  >  **msinfo32.exe**), wie in der folgenden Abbildung dargestellt.

![System Informationen mit aktiviertem DMA-Schutz](images/systeminfodma.png)

Wenn eine bewegliche SSD-Oberfläche manipuliert wird, wird das Gerät die Stromversorgung abschalten. Der resultierende Neustart bewirkt, dass UEFI den Arbeitsspeicher löscht, um alle restlichen Daten zu löschen.
