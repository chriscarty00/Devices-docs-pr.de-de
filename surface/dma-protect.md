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
# DMA Protection auf Surface-Geräten

Der Direkte Speicherzugriffsschutz (Direct Memory Access, DMA) wurde entwickelt, um potenzielle Sicherheitsrisiken im Zusammenhang mit der Verwendung von Wechselmedien-SSDs oder externen Speichergeräten zu mindern. Neuere Geräte verfügen über standardmäßig aktivierten DMA-Schutz. Dazu gehören Surface Pro 7+ Surface Pro 7, Surface Laptop 3 und Surface Pro X.  Öffnen Sie zum Überprüfen des Vorhandenseins des Features für den DMA-Schutz auf Ihrem Gerät Systeminformationen (**Start**msinfo32.exe), wie in der  >  ** **folgenden Abbildung dargestellt.

![Systeminformationen mit aktivierter DMA Protection](images/systeminfodma.png)

Wenn ein austauschbares Surface-SSD manipuliert wird, wird das Gerät heruntergefahren. Der resultierende Neustart bewirkt, dass UEFI den Arbeitsspeicher löscht, und alle verbleibenden Daten löschen.
