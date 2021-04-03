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
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474732"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>Anwenden von ActiveSync-Richtlinien auf Gerätekonten (Surface Hub)


Surface Hubs mit Active Directory-Gerätekonten (bereitgestellt auf dem Hub im Format **Domäne\Benutzername)** und lokale Exchange-Dienste nutzen ActiveSync zum Synchronisieren von E-Mails und Kalendern. Dadurch können Benutzer an geplante Besprechungen teilnehmen und diese von Surface Hub aus starten sowie während der Besprechung erstellte Whiteboards per E-Mail senden.

Damit diese Features funktionieren, müssen die ActiveSync-Richtlinien für Ihre Organisation folgendermaßen konfiguriert werden:

-   Es darf keine globalen Richtlinien geben, die die Synchronisierung des Ressourcenpostfachs blockieren, das vom Surface Hub-Gerätekonto verwendet wird. Wenn eine solche Sperrrichtlinie vorlag, müssen Sie den Surface Hub als zulässiges Gerät hinzufügen.
-   Sie müssen eine Postfachrichtlinie für mobile Geräte festlegen, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist. Andere Einstellungen von Postfachrichtlinien für mobile Geräte sind nicht mit Surface Hub kompatibel.

## <a name="allowing-the-deviceid"></a>Zulassen der DeviceID

Ihre Organisation verfügt möglicherweise über eine globale Richtlinie, die die Synchronisierung von auf Surface Hubs bereitgestellten Gerätekonten verhindert. Informationen zum Konfigurieren dieser Eigenschaft finden Sie unter [Zulassen von Geräte-IDs für ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## <a name="setting-passwordenabled"></a>Festlegen von PasswordEnabled

Das Gerätekonto muss über eine ActiveSync-Richtlinie verfügen, in der das **PasswordEnabled** -Attribut auf „False“ oder 0 festgelegt ist. Informationen zum Konfigurieren dieser Eigenschaft finden Sie unter [Erstellen einer Surface Hub-kompatiblen Microsoft Exchange ActiveSync-Richtlinie](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





