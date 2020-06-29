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
# Microsoft Exchange-Eigenschaften (Surface Hub)


Einige Microsoft Exchange-Eigenschaften des Gerätekontos müssen auf bestimmte Werte festgelegt werden, um das bestmögliche Besprechungsergebnis auf Microsoft Surface Hub zu erzielen. In der folgenden Tabelle werden verschiedene auf PowerShell-Cmdlet-Parametern basierende Exchange-Eigenschaften, ihr Zweck und die Werte, auf die sie festgelegt werden sollten, aufgelistet:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Eigenschaft</th>
<th align="left">Beschreibung</th>
<th align="left">Wert</th>
<th align="left">Auswirkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>Der AutomateProcessing-Parameter aktiviert oder deaktiviert die Kalenderverarbeitung für das Postfach.</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>Surface Hub kann Besprechungsanfragen basierend auf der Verfügbarkeit automatisch annehmen oder ablehnen.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>Der AddOrganizerToSubject-Parameter gibt an, ob der Name des Besprechungsorganisators als Betreff der Besprechungsanfrage verwendet wird.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Der Besprechungsorganisator wird auf der Willkommensseite nicht zweimal angezeigt (statt als Organisator und im Betreff der Besprechung).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>Der AllowConflicts-Parameter gibt an, ob miteinander in Konflikt stehende Besprechungsanfragen zulässig sind.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Surface Hub lehnt Besprechungsanfragen ab, die mit der Uhrzeit einer anderen Besprechung in Konflikt stehen.</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>Der DeleteComments-Parameter gibt an, ob Text im Nachrichtentext eingehender Besprechungsanfragen entfernt oder beibehalten wird.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Der Nachrichtentext von Besprechungen kann beibehalten und von einem Surface Hub abgerufen werden, wenn Sie ihn während einer Besprechung benötigen.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>Der DeleteSubject-Parameter gibt an, ob der Betreff eingehender Besprechungsanfragen entfernt oder beibehalten wird.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Die Betreffs von Besprechungsanfragen können auf dem Surface Hub angezeigt werden.</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>Der RemovePrivateProperty-Parameter gibt an, ob das Kennzeichen „Privat“ für eingehende Besprechungsanfragen gelöscht wird.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Private Besprechungsbetreffs werden auf der Willkommensseite als „privat“ angezeigt.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>Der AddAdditionalResponse-Parameter gibt an, ob weitere Informationen aus dem Ressourcenpostfach als Antwort auf Besprechungsanfragen gesendet werden.</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>Wenn eine Antwort auf eine Besprechungsanfrage gesendet wird, wird benutzerdefinierter Text in der Antwort bereitgestellt.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>Der AdditionalResponse-Parameter gibt die in Antworten auf Besprechungsanfragen enthaltenen zusätzlichen Informationen an.</p>
<div class="alert">
<strong>Hinweis </strong> dieser Text wird nicht gesendet, es sei denn, AddAdditionalResponse ist auf $true festzulegen.
</div>
<div>
 
</div></td>
<td align="left"><p>Die zusätzliche Antwort kann verwendet werden, um Benutzer darüber zu informieren, wie Surface Hub verwendet wird, oder um sie auf Ressourcen zu verweisen.</p></td>
<td align="left"><p>Durch das Hinzufügen einer zusätzlichen Antwortnachricht kann Benutzern eine Einführung in die Nutzung von Surface Hub in ihrer Besprechung gegeben werden.</p></td>
</tr>
</tbody>
</table>

 

 

 





