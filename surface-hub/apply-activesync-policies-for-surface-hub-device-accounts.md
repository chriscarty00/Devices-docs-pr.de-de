---
title: Anwenden von ActiveSync-Richtlinien auf Gerätekonten (Surface Hub)
description: Das Gerätekonto von Microsoft Surface Hub nutzt zum Synchronisieren von E-Mail und Kalender ActiveSync. Dadurch können Benutzer an geplante Besprechungen teilnehmen und diese von Surface Hub aus starten sowie während der Besprechung erstellte Whiteboards per E-Mail senden.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, ActiveSync-Richtlinien
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4db5066c62f4e0e324a5cc3ddad027e00a2e18c9
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314408"
---
# Anwenden von ActiveSync-Richtlinien auf Gerätekonten (Surface Hub)


Das Gerätekonto in allen Versionen von Microsoft Surface Hub verwendet ActiveSync zum Synchronisieren von E-Mails und Kalendern. Dadurch können Benutzer an geplante Besprechungen teilnehmen und diese von Surface Hub aus starten sowie während der Besprechung erstellte Whiteboards per E-Mail senden.

Damit diese Features funktionieren, müssen die ActiveSync-Richtlinien für Ihre Organisation folgendermaßen konfiguriert werden:

-   Es darf keine globalen Richtlinien geben, die die Synchronisierung des Ressourcenpostfachs blockieren, das vom Surface Hub-Gerätekonto verwendet wird. Wenn eine solche Sperrrichtlinie vorlag, müssen Sie den Surface Hub als zulässiges Gerät hinzufügen.
-   Sie müssen eine Postfachrichtlinie für mobile Geräte festlegen, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist. Andere Einstellungen von Postfachrichtlinien für mobile Geräte sind nicht mit Surface Hub kompatibel.

## Zulassen der DeviceID

Ihre Organisation verfügt möglicherweise über eine globale Richtlinie, die die Synchronisierung von auf Surface Hubs bereitgestellten Gerätekonten verhindert. Informationen zum Konfigurieren dieser Eigenschaft finden Sie unter [Zulassen von Geräte-IDs für ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## Festlegen von PasswordEnabled

Das Gerätekonto muss über eine ActiveSync-Richtlinie verfügen, in der das **PasswordEnabled** -Attribut auf „False“ oder 0 festgelegt ist. Informationen zum Konfigurieren dieser Eigenschaft finden Sie unter [Erstellen einer Surface Hub-kompatiblen Microsoft Exchange ActiveSync-Richtlinie](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





