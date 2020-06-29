---
title: Bereitstellen von Apps für Surface Hub 2S mithilfe von Intune
description: Erfahren Sie, wie Sie Apps auf Surface Hub 2S mithilfe von InTune bereitstellen können.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833283"
---
# <span data-ttu-id="2e2b5-104">Bereitstellen von Apps für Surface Hub 2S mithilfe von Intune</span><span class="sxs-lookup"><span data-stu-id="2e2b5-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="2e2b5-105">Sie können zusätzliche apps installieren, um den Anforderungen Ihres Teams oder Ihrer Organisation zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="2e2b5-106">Richtlinien für Entwickler</span><span class="sxs-lookup"><span data-stu-id="2e2b5-106">Developer guidelines</span></span>

- <span data-ttu-id="2e2b5-107">Surface Hub führt ausschließlich [Apps für die universelle Windows-Plattform (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp) aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="2e2b5-108">Apps, die mit [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) erstellt wurden, führen Surface Hub nicht aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="2e2b5-109">Die Apps müssen für die [universelle Gerätefamilie](https://msdn.microsoft.com/library/windows/apps/dn894631) oder die Windows Team-Gerätefamilie entwickelt worden sein.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="2e2b5-110">Surface Hub unterstützt nur [Offline lizenzierte apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) aus dem [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span><span class="sxs-lookup"><span data-stu-id="2e2b5-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="2e2b5-111">Standardmäßig gilt, dass Apps Store-signiert sein müssen, um installiert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="2e2b5-112">Während Test und Entwicklung können Sie auch entwicklersignierte UWP-Apps ausführen, indem Sie das Gerät im Entwicklermodus ausführen.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="2e2b5-113">Beim entwickeln und Übermitteln von apps an den Microsoft Store legen Sie die Optionen für die Verfügbarkeit von Gerätefamilien und die organisatorische Lizenzierung fest, um sicherzustellen, dass Apps für die Ausführung auf Surface Hub verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="2e2b5-114">Sie benötigen Administratoranmeldeinformationen, um apps auf Surface Hub zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="2e2b5-115">Surface Hub wurde für die Verwendung in Besprechungsräumen und anderen freigegebenen Räumen entwickelt und verhindert, dass reguläre Benutzer auf den Microsoft Store zugreifen, um apps herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="2e2b5-116">Bereitstellungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2e2b5-116">Deployment guidelines</span></span>

<span data-ttu-id="2e2b5-117">Sie können UWP-Apps (universelle Windows-Plattform) für die Oberfläche von Hub 2S mithilfe von InTune bereitstellen, um die APP-Bereitstellung auf Geräten zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="2e2b5-118">Wenn Sie apps bereitstellen möchten, aktivieren Sie MDM für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="2e2b5-119">Wählen Sie im InTune-Portal **InTune** als ihre MDM-Autorität (empfohlen) aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![Wählen Sie MDM Authority aus.](images/sh2-set-intune5.png)

2. <span data-ttu-id="2e2b5-121">Aktivieren Sie den Microsoft Store for Business in InTune.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="2e2b5-122">Öffnen Sie InTune, und wählen Sie **Client**  >  **-Apps Microsoft Store for Business aus.**</span><span class="sxs-lookup"><span data-stu-id="2e2b5-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![Aktivieren von Store for Business](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="2e2b5-124">Öffnen Sie in InTune **Microsoft Store for Business** , und wählen Sie **Einstellungen**  >  **Distribute**  >  **Management Tools**aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="2e2b5-125">Wählen Sie **Microsoft InTune** als Verwaltungstool aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![Hinzufügen von InTune als Verwaltungstool](images/sh2-set-intune8.png)

4. <span data-ttu-id="2e2b5-127">Wählen Sie in Microsoft Store für Unternehmen die Option **Einstellungen**  >  **Shop**  >  **Shopping Experience**aus, und wählen Sie dann **Offline-Apps anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="2e2b5-128">Offline-Apps beziehen sich auf apps, die mit InTune synchronisiert und zentral auf einem Gerät bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="2e2b5-129">Nach dem Aktivieren des Offline Einkaufs können Sie offline Lizenzen für apps erwerben, die Sie mit InTune synchronisieren und als Geräte Lizenzierung bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="2e2b5-130">Wählen Sie in **InTune**  >  -**Client-apps**  >  **Microsoft Store für Unternehmen**die Option **Synchronisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="2e2b5-131">Suchen Sie auf der Seite Client-apps in der Liste apps nach der app.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="2e2b5-132">Weisen Sie die apps der gewünschten Gerätegruppe oder den gewünschten Gruppen zu.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="2e2b5-133">Wählen Sie **Zuordnungen**  >  **Gruppe hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* Zuweisen von apps zu Gruppen \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="2e2b5-135">Wählen Sie unter Zuordnungstyp die Option **erforderlich**aus.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-135">Under assignment type, choose **Required**.</span></span> <br>

![\* Zuweisen von apps zu Gruppen \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="2e2b5-137">Wählen Sie für die ausgewählten Gruppen die Option **Geräte Lizenzierung** aus, und wählen Sie dann **OK** aus, und speichern Sie die Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="2e2b5-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* Zuweisen von apps zu Gruppen \*](images/sh2-apps-assign.png)
