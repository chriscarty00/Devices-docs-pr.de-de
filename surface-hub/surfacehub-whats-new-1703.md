---
title: Neuigkeiten in Windows 10, Version1703, für Surface Hub
description: Windows10, Version1703 (Creators Update) enthält neue Features für Microsoft Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: bdc6e384839606fe6138c75e190d68a84679f5b4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832689"
---
# <span data-ttu-id="db47d-103">Neuigkeiten in Windows10, Version1703, für Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="db47d-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="db47d-104">Hier ist Surface Hub-Techniker Jordanien Marchese bei der Präsentation von Updates für Microsoft Surface Hub mit Windows10, Version 1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="db47d-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="db47d-105">Windows10, Version1703 (auch als das Creators Update bezeichnet) führt die folgenden Änderungen für Microsoft Surface Hub ein.</span><span class="sxs-lookup"><span data-stu-id="db47d-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="db47d-106">Neue Einstellungen</span><span class="sxs-lookup"><span data-stu-id="db47d-106">New settings</span></span>

<span data-ttu-id="db47d-107">Der Verwaltung mobiler Geräte (Mobile Device Management, MDM) und den Konfigurationsdienstanbietern (Configuration Service Providers, CSPs) wurden zur Erweiterung der Surface Hub-Verwaltungsfunktionen Einstellungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="db47d-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="db47d-108">[Die neuen Einstellungen umfassen](manage-settings-with-mdm-for-surface-hub.md):</span><span class="sxs-lookup"><span data-stu-id="db47d-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="db47d-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="db47d-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="db47d-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="db47d-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="db47d-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="db47d-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="db47d-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="db47d-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="db47d-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="db47d-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="db47d-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="db47d-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="db47d-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="db47d-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="db47d-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="db47d-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="db47d-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="db47d-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="db47d-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="db47d-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="db47d-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="db47d-119">System/AllowStorageCard</span></span>

<span data-ttu-id="db47d-120">Sowie Einstellungen, basierend auf der neuen [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) und [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span><span class="sxs-lookup"><span data-stu-id="db47d-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="db47d-121">Bereitstellungs-Assistent</span><span class="sxs-lookup"><span data-stu-id="db47d-121">Provisioning wizard</span></span>

<span data-ttu-id="db47d-122">Ein benutzerfreundlicher Assistent unterstützt Sie beim schnellen Erstellen von Bereitstellungspaketen, die Sie auf mehrere Surface Hub-Geräte anwenden können. Darüber hinaus umfasst er Massenbeitritt zu Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db47d-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="db47d-123">Hier erfahren Sie, wie Sie ein Bereitstellungspaket für Surface Hub erstellen können.</span><span class="sxs-lookup"><span data-stu-id="db47d-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![Schritte beim Bereitstellungsassistenten für Surface Hub-Geräte](images/wcd-wizard.png)
    
## <span data-ttu-id="db47d-125">Miracast auf Ihren vorhandenen Funknetzwerken oder LAN</span><span class="sxs-lookup"><span data-stu-id="db47d-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="db47d-126">Microsoft hat Microsoft die Möglichkeit erweitert, [einen Miracast-Datenstrom über ein lokales Netzwerk](miracast-over-infrastructure.md) anstatt über eine direkte drahtlose Verbindung zu senden.</span><span class="sxs-lookup"><span data-stu-id="db47d-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="db47d-127">Cloud-Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="db47d-127">Cloud recovery</span></span>

<span data-ttu-id="db47d-128">Beim Zurücksetzen eines Surface Hub-Geräts besteht jetzt die Möglichkeit, einen Werksbuild des Betriebssystems aus der Cloud herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="db47d-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="db47d-129">Hier erfahren Sie mehr über die Cloud-Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="db47d-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="db47d-130">Die Cloud-Wiederherstellung funktioniert nicht, wenn Sie Proxyserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="db47d-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![Neuinstallation](images/reinstall.png)
    
## <span data-ttu-id="db47d-132">Sitzung beenden</span><span class="sxs-lookup"><span data-stu-id="db47d-132">End session</span></span>

<span data-ttu-id="db47d-133">**Fertig** ist jetzt **Sitzung beenden**.</span><span class="sxs-lookup"><span data-stu-id="db47d-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="db47d-134">Hier erfahren Sie, wie Sie „Sitzung beenden” verwenden können.</span><span class="sxs-lookup"><span data-stu-id="db47d-134">Learn how to use End session.</span></span>](i-am-done-finishing-your-surface-hub-meeting.md) 

![Sitzung beenden](images/end-session.png)



 

 
