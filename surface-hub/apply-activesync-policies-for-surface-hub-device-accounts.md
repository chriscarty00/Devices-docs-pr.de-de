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
ms.openlocfilehash: e8181ec499364c48586f5218983f667331788fc3
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470443"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="287ee-105">Anwenden von ActiveSync-Richtlinien auf Gerätekonten (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="287ee-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="287ee-106">Surface Hubs, die das Windows 10 Team 1703-Betriebssystem verwenden, verwenden ActiveSync, um E-Mails und Kalender des Gerätekontos zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="287ee-106">Surface Hubs using the Windows 10 Team 1703 operating system make use of ActiveSync to sync mail and calendar of the device account.</span></span> <span data-ttu-id="287ee-107">Dadurch können Benutzer an geplante Besprechungen teilnehmen und diese von Surface Hub aus starten sowie während der Besprechung erstellte Whiteboards per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="287ee-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="287ee-108">Damit diese Features funktionieren, müssen die ActiveSync-Richtlinien für Ihre Organisation folgendermaßen konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="287ee-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="287ee-109">Es darf keine globalen Richtlinien geben, die die Synchronisierung des Ressourcenpostfachs blockieren, das vom Surface Hub-Gerätekonto verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="287ee-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="287ee-110">Wenn eine solche Sperrrichtlinie vorlag, müssen Sie den Surface Hub als zulässiges Gerät hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="287ee-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="287ee-111">Sie müssen eine Postfachrichtlinie für mobile Geräte festlegen, in der die **PasswordEnabled** -Eigenschaft auf „False“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="287ee-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="287ee-112">Andere Einstellungen von Postfachrichtlinien für mobile Geräte sind nicht mit Surface Hub kompatibel.</span><span class="sxs-lookup"><span data-stu-id="287ee-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="287ee-113">Zulassen der DeviceID</span><span class="sxs-lookup"><span data-stu-id="287ee-113">Allowing the DeviceID</span></span>

<span data-ttu-id="287ee-114">Ihre Organisation verfügt möglicherweise über eine globale Richtlinie, die die Synchronisierung von auf Surface Hubs bereitgestellten Gerätekonten verhindert.</span><span class="sxs-lookup"><span data-stu-id="287ee-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="287ee-115">Informationen zum Konfigurieren dieser Eigenschaft finden Sie unter [Zulassen von Geräte-IDs für ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span><span class="sxs-lookup"><span data-stu-id="287ee-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="287ee-116">Festlegen von PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="287ee-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="287ee-117">Das Gerätekonto muss über eine ActiveSync-Richtlinie verfügen, in der das **PasswordEnabled** -Attribut auf „False“ oder 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="287ee-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="287ee-118">Informationen zum Konfigurieren dieser Eigenschaft finden Sie unter [Erstellen einer Surface Hub-kompatiblen Microsoft Exchange ActiveSync-Richtlinie](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="287ee-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





