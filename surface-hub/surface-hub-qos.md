---
title: Implementieren von Quality of Service auf Surface Hub
ms.reviewer: ''
manager: laurawi
description: Erfahren Sie, wie Sie QoS auf Surface Hub konfigurieren.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470483"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="6d838-103">Implementieren der Dienstqualität (Quality of Service, QoS) auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6d838-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="6d838-104">Quality of Service (QoS) ist eine Kombination aus Netzwerktechnologien, mit der administratoren die Nutzung von Audio-/Video- und Anwendungsfreigabekommunikation in Echtzeit optimieren können.</span><span class="sxs-lookup"><span data-stu-id="6d838-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="6d838-105">Das Konfigurieren [von QoS für Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) auf dem Surface Hub kann über Ihren Mobile Device Management [(MDM)-Anbieter](manage-settings-with-mdm-for-surface-hub.md) oder über ein [Bereitstellungspaket durchgeführt werden.](provisioning-packages-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="6d838-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="6d838-106">In diesem Verfahren wird erläutert, wie Sie QoS für Surface Hub mithilfe von Microsoft Intune konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6d838-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="6d838-107">Erstellen Sie in Intune [eine benutzerdefinierte Richtlinie](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="6d838-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Dialogfelds zum Erstellen benutzerdefinierter Richtlinien in Intune](images/qos-create.png)

2. <span data-ttu-id="6d838-109">Wählen **Sie unter Benutzerdefinierte OMA-URI-Einstellungen**die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="6d838-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="6d838-110">Für jede hinzugefügte Einstellung geben Sie einen Namen, eine Beschreibung (optional), einen Datentyp, einen OMA-URI und einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="6d838-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines leeren OMA-URI-Einstellungsdialogfelds](images/qos-setting.png)

3. <span data-ttu-id="6d838-112">Fügen Sie die folgenden benutzerdefinierten OMA-URI-Einstellungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="6d838-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="6d838-113">Name</span><span class="sxs-lookup"><span data-stu-id="6d838-113">Name</span></span> | <span data-ttu-id="6d838-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6d838-114">Data type</span></span> | <span data-ttu-id="6d838-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="6d838-115">OMA-URI</span></span><br><span data-ttu-id="6d838-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="6d838-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="6d838-117">Wert</span><span class="sxs-lookup"><span data-stu-id="6d838-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="6d838-118">Audioquellenport</span><span class="sxs-lookup"><span data-stu-id="6d838-118">Audio Source Port</span></span> | <span data-ttu-id="6d838-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6d838-119">String</span></span> |  <span data-ttu-id="6d838-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="6d838-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="6d838-121">Die Werte von Ihrem Skype-Administrator erhalten</span><span class="sxs-lookup"><span data-stu-id="6d838-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="6d838-122">Audio DSCP</span><span class="sxs-lookup"><span data-stu-id="6d838-122">Audio DSCP</span></span> | <span data-ttu-id="6d838-123">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="6d838-123">Integer</span></span> |  <span data-ttu-id="6d838-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="6d838-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="6d838-125">46</span><span class="sxs-lookup"><span data-stu-id="6d838-125">46</span></span>
    <span data-ttu-id="6d838-126">Video Source Port</span><span class="sxs-lookup"><span data-stu-id="6d838-126">Video Source Port</span></span> | <span data-ttu-id="6d838-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6d838-127">String</span></span> |  <span data-ttu-id="6d838-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="6d838-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="6d838-129">Die Werte von Ihrem Skype-Administrator erhalten</span><span class="sxs-lookup"><span data-stu-id="6d838-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="6d838-130">Video DSCP</span><span class="sxs-lookup"><span data-stu-id="6d838-130">Video DSCP</span></span> | <span data-ttu-id="6d838-131">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="6d838-131">Integer</span></span> |  <span data-ttu-id="6d838-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="6d838-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="6d838-133">34</span><span class="sxs-lookup"><span data-stu-id="6d838-133">34</span></span>
    <span data-ttu-id="6d838-134">Name des Audioprozesses</span><span class="sxs-lookup"><span data-stu-id="6d838-134">Audio Process Name</span></span> | <span data-ttu-id="6d838-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6d838-135">String</span></span> |  <span data-ttu-id="6d838-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="6d838-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="6d838-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="6d838-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="6d838-138">Name des Videoprozesses</span><span class="sxs-lookup"><span data-stu-id="6d838-138">Video Process Name</span></span> | <span data-ttu-id="6d838-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6d838-139">String</span></span> |  <span data-ttu-id="6d838-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="6d838-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="6d838-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="6d838-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="6d838-142">Jeder **OMA-URI-Pfad** beginnt mit `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="6d838-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="6d838-143">Der vollständige Pfad für die Einstellung des Audioquellenports ist beispielsweise `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="6d838-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="6d838-144">Wenn die Richtlinie erstellt wurde, stellen Sie sie auf Surface Hub aus.</span><span class="sxs-lookup"><span data-stu-id="6d838-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="6d838-145">Derzeit können Sie die Einstellung **IPProtocolMatchCondition** im [NetworkQoSPolicy CSP nicht konfigurieren.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)</span><span class="sxs-lookup"><span data-stu-id="6d838-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="6d838-146">Wenn diese Einstellung konfiguriert ist, kann die Richtlinie nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d838-146">If this setting is configured, the policy will fail to apply.</span></span>
 
