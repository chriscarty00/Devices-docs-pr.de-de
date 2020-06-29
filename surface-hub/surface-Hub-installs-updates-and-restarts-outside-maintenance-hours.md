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
# Surface Hub installiert möglicherweise Updates und könnte außerhalb der Wartungszeiten neu starten

Unter bestimmten Umständen installiert Surface Hub Updates während der Geschäftszeiten anstatt während des normalen Wartungsfensters. Wenn dies erforderlich ist, wird das Gerät neu gestartet. Sie können das Gerät erst dann verwenden, wenn der Vorgang abgeschlossen ist.

> [!NOTE]  
> Dieses Verhalten wird nicht erwartet, wenn ein Wartungsfenster fehlt. Sie tritt nur auf, wenn das Gerät lange Zeit veraltet ist.

## Ursache
Um sicherzustellen, dass Surface Hub während der Geschäftszeiten zur Verwendung zur Verfügung steht, ist der Hub für die Ausführung von administrativen Funktionen während eines in den Einstellungen definierten Wartungsfensters konfiguriert (siehe "Verweise" unten). Während dieses Wartungszeitraums installiert der Hub automatisch alle verfügbaren Updates über Windows Update oder Windows Server Update Service (WSUS). Sobald Updates abgeschlossen sind, kann der Hub neu gestartet werden.

Updates können nur im Wartungsfenster installiert werden, wenn der Surface-Hub aktiviert, aber nicht verwendet oder reserviert ist. Wenn der Surface-Hub beispielsweise für eine Besprechung geplant ist, die 24 Stunden dauert, werden alle Updates, die für die Installation geplant sind, verzögert, bis der Hub im nächsten Wartungsfenster verfügbar ist. Wenn der Hub weiterhin ausgelastet ist und mehrere Wartungsfenster nicht vorhanden ist, beginnt der Hub schließlich mit der Installation und dem Herunterladen von Updates. Dies kann während oder außerhalb des Wartungsfensters erfolgen. Nachdem der Download und die Installation begonnen haben, kann das Gerät neu gestartet werden.

## So vermeiden Sie dieses Problem

Es ist wichtig, dass Sie die Wartungszeit für Surface Hub beiseite legen, um administrative Funktionen auszuführen. Das Reservieren des Surface Hub für 24-Stunden-Intervalle oder das Verwenden des Geräts während des Wartungsfensters verzögert die Installation von Updates. Wir empfehlen, den Hub während des geplanten Wartungszeitraums nicht zu verwenden oder zu reservieren. Ein zweistündiges Fenster sollte für die Aktualisierung reserviert werden.

Eine Option, die Sie verwenden können, um die Verfügbarkeit von Updates zu steuern, ist der Windows Server Update-Dienst (WSUS). WSUS bietet die Kontrolle darüber, welche Updates wann installiert werden.

## Verweise 
 
[Aktualisieren des Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 

[Wartungsfenster](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[Bereitstellen von Windows10-Updates mit Windows Server Update Services (WSUS)](/windows/deployment/update/waas-manage-updates-wsus) 


