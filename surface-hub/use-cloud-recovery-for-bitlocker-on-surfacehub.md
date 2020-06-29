---
title: Verwenden der Cloud-Wiederherstellung für BitLocker auf einem Surface Hub
description: Verwenden der Cloud-Wiederherstellung für BitLocker auf einem Surface Hub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Barrierefreiheiteinstellungen, Einstellungs-App, Erleichterte Bedienung
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832671"
---
# <span data-ttu-id="38d65-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="38d65-104">Summary</span></span>

<span data-ttu-id="38d65-105">In diesem Artikel wird beschrieben, wie Sie die Cloud-Wiederherstellungsfunktion verwenden, wenn Sie unerwartet von BitLocker auf einem Surface Hub-Gerät dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="38d65-105">This article describes how to use the cloud recovery function if you are unexpectedly prompted by BitLocker on a Surface Hub device.</span></span>

> [!NOTE]
> <span data-ttu-id="38d65-106">Führen Sie die folgenden Schritte nur aus, wenn ein BitLocker-Wiederherstellungsschlüssel nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="38d65-106">You should follow these steps only if a BitLocker recovery key isn't available.</span></span>

> [!WARNING]
> * <span data-ttu-id="38d65-107">Durch diesen Wiederherstellungsprozess werden die Inhalte des internen Laufwerks gelöscht.</span><span class="sxs-lookup"><span data-stu-id="38d65-107">This recovery process deletes the contents of the internal drive.</span></span> <span data-ttu-id="38d65-108">Wenn der Prozess fehlschlägt, wird das interne Laufwerk vollständig unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="38d65-108">If the process fails, the internal drive will become completely unusable.</span></span> <span data-ttu-id="38d65-109">In diesem Fall müssen Sie bei Microsoft eine Serviceanfrage für eine Lösung protokollieren.</span><span class="sxs-lookup"><span data-stu-id="38d65-109">If this occurs, you will have to log a service request with Microsoft for a resolution.</span></span>
> * <span data-ttu-id="38d65-110">Nachdem der Wiederherstellungsvorgang abgeschlossen ist, wird das Gerät auf die Werkseinstellungen zurückgesetzt und wieder in den Zustand "außerhalb des Felds" zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="38d65-110">After the recovery process is complete, the device will be reset to the factory settings and returned to its Out of Box Experience state.</span></span>
> * <span data-ttu-id="38d65-111">Nach der Wiederherstellung muss der Surface-Hub vollständig neu konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="38d65-111">After the recovery, the Surface Hub must be completely reconfigured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38d65-112">Dieser Vorgang erfordert eine offene Internet Verbindung, die keinen Proxy oder eine andere Authentifizierungsmethode verwendet.</span><span class="sxs-lookup"><span data-stu-id="38d65-112">This process requires an open Internet connection that does not use a proxy or other authentication method.</span></span>

## <span data-ttu-id="38d65-113">Cloud-Wiederherstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="38d65-113">Cloud recovery process</span></span>

<span data-ttu-id="38d65-114">Führen Sie die folgenden Schritte aus, um eine Cloud-Wiederherstellung durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="38d65-114">To perform a cloud recovery, follow these steps:</span></span>

1. <span data-ttu-id="38d65-115">Wählen Sie **ESC, um weitere Wiederherstellungsoptionen anzuzeigen**.</span><span class="sxs-lookup"><span data-stu-id="38d65-115">Select **Press Esc for more recovery options**.</span></span>

   ![Screenshot von Escape](images/01-escape.png)

1. <span data-ttu-id="38d65-117">Wählen Sie **dieses Laufwerk überspringen**aus.</span><span class="sxs-lookup"><span data-stu-id="38d65-117">Select **Skip this drive**.</span></span>

   ![Screenshot von "dieses Laufwerk überspringen"](images/02-skip-this-drive.png)

1. <span data-ttu-id="38d65-119">Wählen Sie **in der Cloud wiederherstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="38d65-119">Select **Recover from the cloud**.</span></span>

   ![Screenshot der Wiederherstellung aus der Cloud](images/03-recover-from-cloud.png)

1. <span data-ttu-id="38d65-121">Wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="38d65-121">Select **Yes**.</span></span>

   ![Screenshot von "Ja"](images/04-yes.png)

1. <span data-ttu-id="38d65-123">Wählen Sie **erneut installieren**aus.</span><span class="sxs-lookup"><span data-stu-id="38d65-123">Select **Reinstall**.</span></span>

   ![Screenshot der Neuinstallation](images/05a-reinstall.png)

   ![Screenshot des Downloads](images/05b-downloading.png)

1. <span data-ttu-id="38d65-126">Nachdem der Cloud-Wiederherstellungsvorgang abgeschlossen ist, starten Sie die Neukonfiguration mithilfe der **out-of-Box-Erfahrung**.</span><span class="sxs-lookup"><span data-stu-id="38d65-126">After the cloud recovery process is complete, start the reconfiguration by using the **Out of Box Experience**.</span></span>

   ![Screenshot von Out-of-the-Box](images/06-out-of-box.png)

## <span data-ttu-id="38d65-128">Fehlermeldung "etwas ist schief gelaufen"</span><span class="sxs-lookup"><span data-stu-id="38d65-128">"Something went Wrong" error message</span></span>

<span data-ttu-id="38d65-129">Dieser Fehler wird in der Regel durch Netzwerkprobleme verursacht, die während des Wiederherstellungs Downloads auftreten.</span><span class="sxs-lookup"><span data-stu-id="38d65-129">This error is usually caused by network issues that occur during the recovery download.</span></span> <span data-ttu-id="38d65-130">Wenn dieses Problem auftritt, deaktivieren Sie den Hub nicht, da Sie ihn nicht erneut starten können.</span><span class="sxs-lookup"><span data-stu-id="38d65-130">When this issue occurs, don't turn off the Hub because you won't be able to restart it.</span></span> <span data-ttu-id="38d65-131">Wenn diese Fehlermeldung angezeigt wird, kehren Sie zum Schritt "aus der Cloud wiederherstellen" zurück, und starten Sie den Wiederherstellungsprozess erneut.</span><span class="sxs-lookup"><span data-stu-id="38d65-131">If you receive this error message, return to the "Recover from the cloud" step, and then restart the recovery process.</span></span>

1. <span data-ttu-id="38d65-132">Wählen Sie **Abbrechen**aus.</span><span class="sxs-lookup"><span data-stu-id="38d65-132">Select **Cancel**.</span></span>

   ![Screenshot von "Abbrechen"](images/07-cancel.png)

1. <span data-ttu-id="38d65-134">Wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="38d65-134">Select **Troubleshoot**.</span></span>

   ![Screenshot der Problembehandlung](images/08-troubleshoot.png)

1. <span data-ttu-id="38d65-136">Wählen Sie **in der Cloud wiederherstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="38d65-136">Select **Recover from the cloud**.</span></span>

   ![Screenshot der Wiederherstellung aus der Cloud](images/09-recover-from-cloud2.png)

1. <span data-ttu-id="38d65-138">Wenn der Fehler " **kabelgebundenes Netzwerk nicht gefunden** " auftritt, wählen Sie **Abbrechen**aus, und lassen Sie den Surface Hub das kabelgebundene Netzwerk wieder entdecken.</span><span class="sxs-lookup"><span data-stu-id="38d65-138">If the **Wired network isn't found** error occurs, select **Cancel**, and then let the Surface Hub rediscover the wired network.</span></span>

   ![Screenshot eines kabelgebundenen Netzwerks wurde nicht gefunden](images/10-cancel.png)