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
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832911"
---
# <span data-ttu-id="1f356-103">Implementieren von Quality of Service (QoS) auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1f356-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="1f356-104">Quality of Service (QoS) ist eine Kombination aus Netzwerktechnologien, mit deren Hilfe Administratoren die Erfahrung von Audio/Video-und Anwendungsfreigabe-Kommunikation in Echtzeit optimieren können.</span><span class="sxs-lookup"><span data-stu-id="1f356-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="1f356-105">Die Konfiguration von [QoS für Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) auf dem Surface Hub kann mithilfe des [MDM-Anbieters (Mobile Device Management)](manage-settings-with-mdm-for-surface-hub.md) oder über ein [Bereitstellungspaket](provisioning-packages-for-surface-hub.md)erfolgen.</span><span class="sxs-lookup"><span data-stu-id="1f356-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="1f356-106">In diesem Verfahren wird erläutert, wie Sie QoS für Surface Hub mithilfe von Microsoft InTune konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f356-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="1f356-107">Erstellen Sie in InTune [eine benutzerdefinierte Richtlinie](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="1f356-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Screenshot des Dialogfelds zum Erstellen benutzerdefinierter Richtlinien in InTune](images/qos-create.png)

2. <span data-ttu-id="1f356-109">Wählen Sie unter **benutzerdefinierte Oma-URI-Einstellungen**die Option **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="1f356-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="1f356-110">Für jede Einstellung, die Sie hinzufügen, geben Sie einen Namen, eine Beschreibung (optional), einen Datentyp, einen Oma-URI und einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="1f356-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![Screenshot eines leeren Dialogfelds für OMA-URI-Einstellungen](images/qos-setting.png)

3. <span data-ttu-id="1f356-112">Fügen Sie die folgenden benutzerdefinierten Oma-URI-Einstellungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="1f356-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="1f356-113">Name</span><span class="sxs-lookup"><span data-stu-id="1f356-113">Name</span></span> | <span data-ttu-id="1f356-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1f356-114">Data type</span></span> | <span data-ttu-id="1f356-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="1f356-115">OMA-URI</span></span><br><span data-ttu-id="1f356-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="1f356-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="1f356-117">Wert</span><span class="sxs-lookup"><span data-stu-id="1f356-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="1f356-118">Audioquellen-Port</span><span class="sxs-lookup"><span data-stu-id="1f356-118">Audio Source Port</span></span> | <span data-ttu-id="1f356-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1f356-119">String</span></span> |  <span data-ttu-id="1f356-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="1f356-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="1f356-121">Holen Sie sich die Werte Ihres Skype-Administrators</span><span class="sxs-lookup"><span data-stu-id="1f356-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="1f356-122">Audio DSCP</span><span class="sxs-lookup"><span data-stu-id="1f356-122">Audio DSCP</span></span> | <span data-ttu-id="1f356-123">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1f356-123">Integer</span></span> |  <span data-ttu-id="1f356-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="1f356-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="1f356-125">46</span><span class="sxs-lookup"><span data-stu-id="1f356-125">46</span></span>
    <span data-ttu-id="1f356-126">Video Quell Port</span><span class="sxs-lookup"><span data-stu-id="1f356-126">Video Source Port</span></span> | <span data-ttu-id="1f356-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1f356-127">String</span></span> |  <span data-ttu-id="1f356-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="1f356-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="1f356-129">Holen Sie sich die Werte Ihres Skype-Administrators</span><span class="sxs-lookup"><span data-stu-id="1f356-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="1f356-130">Video DSCP</span><span class="sxs-lookup"><span data-stu-id="1f356-130">Video DSCP</span></span> | <span data-ttu-id="1f356-131">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1f356-131">Integer</span></span> |  <span data-ttu-id="1f356-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="1f356-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="1f356-133">34</span><span class="sxs-lookup"><span data-stu-id="1f356-133">34</span></span>
    <span data-ttu-id="1f356-134">Name des Audio-Prozesses</span><span class="sxs-lookup"><span data-stu-id="1f356-134">Audio Process Name</span></span> | <span data-ttu-id="1f356-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1f356-135">String</span></span> |  <span data-ttu-id="1f356-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="1f356-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="1f356-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="1f356-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="1f356-138">Name des Video Prozesses</span><span class="sxs-lookup"><span data-stu-id="1f356-138">Video Process Name</span></span> | <span data-ttu-id="1f356-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1f356-139">String</span></span> |  <span data-ttu-id="1f356-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="1f356-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="1f356-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="1f356-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="1f356-142">Jeder **Oma-URI-** Pfad beginnt mit `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="1f356-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="1f356-143">Der vollständige Pfad für die Audioquellen-Porteinstellung wird beispielsweise sein `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="1f356-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="1f356-144">Wenn die Richtlinie erstellt wurde, [Stellen Sie Sie auf dem Surface Hub bereit.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="1f356-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="1f356-145">Derzeit können Sie die Einstellung **IPProtocolMatchCondition** im [NetworkQoSPolicy-CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f356-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="1f356-146">Wenn diese Einstellung konfiguriert ist, kann die Richtlinie nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f356-146">If this setting is configured, the policy will fail to apply.</span></span>
 
