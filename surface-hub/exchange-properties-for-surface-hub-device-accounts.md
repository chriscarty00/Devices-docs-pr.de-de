---
title: Microsoft Exchange-Eigenschaften (Surface Hub)
description: Einige Microsoft Exchange-Eigenschaften des Gerätekontos müssen auf bestimmte Werte festgelegt werden, um das bestmögliche Besprechungsergebnis auf Microsoft Surface Hub zu erzielen.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Microsoft Exchange-Eigenschaften, Gerätekonto, Surface Hub, Windows PowerShell-Cmdlet
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833697"
---
# <span data-ttu-id="eabc6-104">Microsoft Exchange-Eigenschaften (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="eabc6-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="eabc6-105">Einige Microsoft Exchange-Eigenschaften des Gerätekontos müssen auf bestimmte Werte festgelegt werden, um das bestmögliche Besprechungsergebnis auf Microsoft Surface Hub zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="eabc6-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="eabc6-106">In der folgenden Tabelle werden verschiedene auf PowerShell-Cmdlet-Parametern basierende Exchange-Eigenschaften, ihr Zweck und die Werte, auf die sie festgelegt werden sollten, aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="eabc6-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eabc6-107">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eabc6-107">Property</span></span></th>
<th align="left"><span data-ttu-id="eabc6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eabc6-108">Description</span></span></th>
<th align="left"><span data-ttu-id="eabc6-109">Wert</span><span class="sxs-lookup"><span data-stu-id="eabc6-109">Value</span></span></th>
<th align="left"><span data-ttu-id="eabc6-110">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="eabc6-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eabc6-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="eabc6-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-112">Der AutomateProcessing-Parameter aktiviert oder deaktiviert die Kalenderverarbeitung für das Postfach.</span><span class="sxs-lookup"><span data-stu-id="eabc6-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="eabc6-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-114">Surface Hub kann Besprechungsanfragen basierend auf der Verfügbarkeit automatisch annehmen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="eabc6-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eabc6-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="eabc6-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-116">Der AddOrganizerToSubject-Parameter gibt an, ob der Name des Besprechungsorganisators als Betreff der Besprechungsanfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eabc6-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-117">$False</span><span class="sxs-lookup"><span data-stu-id="eabc6-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-118">Der Besprechungsorganisator wird auf der Willkommensseite nicht zweimal angezeigt (statt als Organisator und im Betreff der Besprechung).</span><span class="sxs-lookup"><span data-stu-id="eabc6-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eabc6-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="eabc6-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-120">Der AllowConflicts-Parameter gibt an, ob miteinander in Konflikt stehende Besprechungsanfragen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="eabc6-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-121">$False</span><span class="sxs-lookup"><span data-stu-id="eabc6-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-122">Surface Hub lehnt Besprechungsanfragen ab, die mit der Uhrzeit einer anderen Besprechung in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="eabc6-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eabc6-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="eabc6-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-124">Der DeleteComments-Parameter gibt an, ob Text im Nachrichtentext eingehender Besprechungsanfragen entfernt oder beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="eabc6-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-125">$False</span><span class="sxs-lookup"><span data-stu-id="eabc6-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-126">Der Nachrichtentext von Besprechungen kann beibehalten und von einem Surface Hub abgerufen werden, wenn Sie ihn während einer Besprechung benötigen.</span><span class="sxs-lookup"><span data-stu-id="eabc6-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eabc6-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="eabc6-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-128">Der DeleteSubject-Parameter gibt an, ob der Betreff eingehender Besprechungsanfragen entfernt oder beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="eabc6-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-129">$False</span><span class="sxs-lookup"><span data-stu-id="eabc6-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-130">Die Betreffs von Besprechungsanfragen können auf dem Surface Hub angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eabc6-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eabc6-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="eabc6-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-132">Der RemovePrivateProperty-Parameter gibt an, ob das Kennzeichen „Privat“ für eingehende Besprechungsanfragen gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="eabc6-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-133">$False</span><span class="sxs-lookup"><span data-stu-id="eabc6-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-134">Private Besprechungsbetreffs werden auf der Willkommensseite als „privat“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eabc6-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eabc6-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="eabc6-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-136">Der AddAdditionalResponse-Parameter gibt an, ob weitere Informationen aus dem Ressourcenpostfach als Antwort auf Besprechungsanfragen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eabc6-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-137">$True</span><span class="sxs-lookup"><span data-stu-id="eabc6-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-138">Wenn eine Antwort auf eine Besprechungsanfrage gesendet wird, wird benutzerdefinierter Text in der Antwort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="eabc6-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eabc6-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="eabc6-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-140">Der AdditionalResponse-Parameter gibt die in Antworten auf Besprechungsanfragen enthaltenen zusätzlichen Informationen an.</span><span class="sxs-lookup"><span data-stu-id="eabc6-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="eabc6-141">Hinweis </strong> dieser Text wird nicht gesendet, es sei denn, AddAdditionalResponse ist auf $true festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eabc6-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="eabc6-142">Die zusätzliche Antwort kann verwendet werden, um Benutzer darüber zu informieren, wie Surface Hub verwendet wird, oder um sie auf Ressourcen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="eabc6-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eabc6-143">Durch das Hinzufügen einer zusätzlichen Antwortnachricht kann Benutzern eine Einführung in die Nutzung von Surface Hub in ihrer Besprechung gegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eabc6-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





