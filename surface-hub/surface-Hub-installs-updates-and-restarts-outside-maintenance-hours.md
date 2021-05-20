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
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a>Surface Hub installiert möglicherweise Updates und könnte außerhalb der Wartungszeiten neu starten

Unter bestimmten Umständen installiert Surface Hub Updates während der Geschäftszeiten statt während des regulären Wartungsfensters. Das Gerät wird dann bei Bedarf neu gestartet. Sie können das Gerät erst verwenden, wenn der Prozess abgeschlossen ist.

> [!NOTE]  
> Dies ist nicht das erwartete Verhalten, wenn ein Wartungsfenster fehlt. Er tritt nur auf, wenn das Gerät für einen langen Zeitraum veraltet ist.

## <a name="cause"></a>Ursache

Um sicherzustellen, dass Surface Hub während der Geschäftszeiten zur Verfügung steht, ist der Hub so konfiguriert, dass verwaltungstechnische Funktionen während eines Wartungsfensters ausführen, das in Einstellungen definiert ist (siehe "Verweise", unten). Während dieses Wartungszeitraums installiert der Hub alle verfügbaren Updates automatisch über Windows Update oder Windows Update for Business (WUfB). Sobald Updates abgeschlossen sind, kann der Hub neu gestartet werden.

Updates können während des Wartungsfensters nur installiert werden, wenn Surface Hub aktiviert, aber nicht verwendet oder reserviert ist. Wenn die Surface Hub beispielsweise für eine Besprechung geplant ist, die 24 Stunden dauert, werden alle updates, die installiert werden sollen, zurückgestellt, bis der Hub während des nächsten Wartungsfensters verfügbar ist. Wenn der Hub weiterhin ausgelastet ist und mehrere Wartungsfenster fehlen, beginnt der Hub schließlich mit der Installation und dem Herunterladen von Updates. Dies kann während oder außerhalb des Wartungsfensters auftreten. Sobald der Download und die Installation begonnen haben, kann das Gerät neu gestartet werden.

## <a name="to-avoid-this-issue"></a>So vermeiden Sie dieses Problem

Es ist wichtig, dass Sie Wartungszeit für Surface Hub verwaltungstechnische Funktionen festlegen. Das Reservieren der Surface Hub 24-Stunden-Intervalle oder die Verwendung des Geräts während des Wartungsfensters verzögert die Installation von Updates. Es wird empfohlen, den Hub während des geplanten Wartungszeitraums nicht zu verwenden oder zu reservieren. Ein Zwei-Stunden-Fenster sollte für die Aktualisierung reserviert werden.

Eine Option, mit der Sie die Verfügbarkeit von Updates steuern können, ist Windows Update for Business.

## <a name="learn-more"></a>Mehr erfahren
 
- [Aktualisieren des Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 
- [Wartungsfenster](manage-windows-updates-for-surface-hub.md#maintenance-window) 
