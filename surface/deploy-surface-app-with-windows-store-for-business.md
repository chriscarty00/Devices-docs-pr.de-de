---
title: Bereitstelleneiner Surface-App mit Microsoft Store für Unternehmen oder Microsoft Store für Bildung (Surface)
description: Hier erfahren Sie, wie Sie Surface-App mit Microsoft Store for Business oder Microsoft Store für Education hinzufügen und herunterladen sowie Surface-App mit PowerShell und MDT installieren.
keywords: Surface-APP, APP, Bereitstellung, anpassen
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114713"
---
# <span data-ttu-id="8fc45-104">Bereitstelleneiner Surface-App mit Microsoft Store für Unternehmen und Bildungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="8fc45-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="8fc45-105">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="8fc45-105">Applies to</span></span>**

- <span data-ttu-id="8fc45-106">Surface Laptop go</span><span class="sxs-lookup"><span data-stu-id="8fc45-106">Surface Laptop Go</span></span>
- <span data-ttu-id="8fc45-107">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8fc45-107">Surface Pro 7</span></span>
- <span data-ttu-id="8fc45-108">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="8fc45-108">Surface Laptop 3</span></span>
- <span data-ttu-id="8fc45-109">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="8fc45-109">Surface Pro 6</span></span>
- <span data-ttu-id="8fc45-110">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="8fc45-110">Surface Laptop 2</span></span>
- <span data-ttu-id="8fc45-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="8fc45-111">Surface Go</span></span>
- <span data-ttu-id="8fc45-112">Surface Go mit LTE</span><span class="sxs-lookup"><span data-stu-id="8fc45-112">Surface Go with LTE</span></span>
- <span data-ttu-id="8fc45-113">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="8fc45-113">Surface Book 2</span></span>
- <span data-ttu-id="8fc45-114">Surface Pro mit LTE Advanced (Modell 1807)</span><span class="sxs-lookup"><span data-stu-id="8fc45-114">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="8fc45-115">Surface Pro (Modell 1796)</span><span class="sxs-lookup"><span data-stu-id="8fc45-115">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="8fc45-116">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="8fc45-116">Surface Laptop</span></span>
- <span data-ttu-id="8fc45-117">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="8fc45-117">Surface Studio</span></span>
- <span data-ttu-id="8fc45-118">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="8fc45-118">Surface Studio 2</span></span>
- <span data-ttu-id="8fc45-119">Surface Book</span><span class="sxs-lookup"><span data-stu-id="8fc45-119">Surface Book</span></span>
- <span data-ttu-id="8fc45-120">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8fc45-120">Surface Pro 4</span></span>
- <span data-ttu-id="8fc45-121">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="8fc45-121">Surface 3 LTE</span></span>
- <span data-ttu-id="8fc45-122">Surface3</span><span class="sxs-lookup"><span data-stu-id="8fc45-122">Surface 3</span></span>
- <span data-ttu-id="8fc45-123">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="8fc45-123">Surface Pro 3</span></span>


<span data-ttu-id="8fc45-124">Die Surface-APP ist eine einfache Microsoft Store-App, die die Kontrolle über viele oberflächenspezifische Einstellungen und Optionen bietet, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="8fc45-124">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="8fc45-125">Aktivieren oder Deaktivieren der Windows-Taste auf dem Surface-Gerät 
</span><span class="sxs-lookup"><span data-stu-id="8fc45-125">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="8fc45-126">Anpassen der Empfindlichkeit des Surface-Stifts 
</span><span class="sxs-lookup"><span data-stu-id="8fc45-126">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="8fc45-127">Anpassen der Tastenaktionen des Surface-Stifts 
</span><span class="sxs-lookup"><span data-stu-id="8fc45-127">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="8fc45-128">Aktivieren oder Deaktivieren der Audioerweiterungen des Surface-Geräts 
</span><span class="sxs-lookup"><span data-stu-id="8fc45-128">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="8fc45-129">Schneller Zugriff auf Support Dokumentation und-Informationen für Ihr Gerät</span><span class="sxs-lookup"><span data-stu-id="8fc45-129">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="8fc45-130">Für Kunden, die Windows Update verwenden, wird normalerweise die Surface-App als Teil der automatischen Updates empfangen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-130">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="8fc45-131">Wenn Ihre Organisation jedoch Bilder für die Bereitstellung auf Ihren Surface-Geräten vorbereitet, möchten Sie möglicherweise die Surface-app (vormals Surface Hub genannt) in ihren Imaging-und Bereitstellungsprozess einbeziehen, anstatt die Benutzer jedes einzelnen Geräts zum herunterladen und Installieren der APP aus dem Microsoft Store oder Ihrem Microsoft Store für Unternehmen zu verpflichten.</span><span class="sxs-lookup"><span data-stu-id="8fc45-131">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="8fc45-132">Dieser Artikel gilt nicht für Surface pro X. Weitere Informationen finden Sie unter [bereitstellen, verwalten und warten von Surface pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="8fc45-132">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="8fc45-133">Übersicht über DGM-apps</span><span class="sxs-lookup"><span data-stu-id="8fc45-133">Surface app overview</span></span>

<span data-ttu-id="8fc45-134">Die Surface-App steht als kostenloser Download aus dem [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8fc45-134">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="8fc45-135">Benutzer können Sie aus dem Microsoft Store herunterladen und installieren, doch wenn Ihre Organisation stattdessen Microsoft Store für Unternehmen verwendet, müssen Sie Sie dem Inventar Ihres Shops hinzufügen und die APP möglicherweise als Teil des Windows-Bereitstellungsprozesses einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-135">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="8fc45-136">Diese Prozesse werden in diesem Artikel behandelt.</span><span class="sxs-lookup"><span data-stu-id="8fc45-136">These processes are discussed throughout this article.</span></span> <span data-ttu-id="8fc45-137">Weitere Informationen zu Microsoft Store für Unternehmen finden Sie unter [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) im Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="8fc45-137">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="8fc45-138">Hinzufügen einer Surface-APP zu einem Microsoft Store for Business-Konto</span><span class="sxs-lookup"><span data-stu-id="8fc45-138">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="8fc45-139">Bevor Benutzer eine APP aus dem Microsoft Store for Business-Konto eines Unternehmens installieren oder bereitstellen können, müssen die gewünschten apps zunächst den Benutzern eines Unternehmens zur Verfügung gestellt und lizenziert werden.</span><span class="sxs-lookup"><span data-stu-id="8fc45-139">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="8fc45-140">Wenn Sie dies noch nicht getan haben, erstellen Sie ein [Microsoft Store for Business-Konto](https://www.microsoft.com/business-store).</span><span class="sxs-lookup"><span data-stu-id="8fc45-140">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="8fc45-141">Melden Sie sich beim Portal an.</span><span class="sxs-lookup"><span data-stu-id="8fc45-141">Log on to the portal.</span></span> 

3. <span data-ttu-id="8fc45-142">Aktivieren der Offline Lizenzierung: Klicken Sie auf **Verwalten->Store-Einstellungen**, und aktivieren Sie dann das Kontrollkästchen **Offline lizenzierte Apps für Personen, die im Store einkaufen** , wie in Abbildung 1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8fc45-142">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="8fc45-143">Weitere Informationen zu den Microsoft Store for Business-App-Lizenzierungsmodellen finden Sie unter [apps im Microsoft Store for Business und Education](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="8fc45-143">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Kontrollkästchen "Offline-Lizenzen-apps anzeigen"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="8fc45-145">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="8fc45-145">Figure 1.</span></span> <span data-ttu-id="8fc45-146">Aktivieren von Apps für die Offlineverwendung</span><span class="sxs-lookup"><span data-stu-id="8fc45-146">Enable apps for offline use</span></span>*

4. <span data-ttu-id="8fc45-147">Fügen Sie Surface-APP zu Ihrem Microsoft Store for Business-Konto hinzu, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8fc45-147">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="8fc45-148">Klicken Sie auf das Menü **Shop** .</span><span class="sxs-lookup"><span data-stu-id="8fc45-148">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="8fc45-149">Geben Sie im Suchfeld Surface- **App**ein, und klicken Sie dann auf das Symbol suchen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-149">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="8fc45-150">Nachdem die Surface-app in den Suchergebnissen angezeigt wird, klicken Sie auf das Symbol der app.</span><span class="sxs-lookup"><span data-stu-id="8fc45-150">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="8fc45-151">Sie haben die Wahl ( **Online** oder **Offline**auswählen), wie in Abbildung 2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8fc45-151">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Wählen Sie den Offline Lizenzierungsmodus aus, und fügen Sie die APP Ihrem Inventar hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="8fc45-153">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="8fc45-153">Figure 2.</span></span> <span data-ttu-id="8fc45-154">Wählen Sie den Offline Lizenzierungsmodus aus, und fügen Sie die APP Ihrem Inventar hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fc45-154">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="8fc45-155">Klicken Sie auf **Offline** , um den Offline Lizenzierungsmodus auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-155">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="8fc45-156">Klicken Sie auf **APP herunter** laden, um die APP Ihrem Microsoft Store for Business-Inventar hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-156">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="8fc45-157">Wie in Abbildung 3 zu sehen ist, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mit einem Verwaltungstool bereitgestellt oder von der Inventarseite des Unternehmens im privaten Speicher heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="8fc45-157">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="8fc45-158">Fenster zur Offline lizenzierten App-Bestätigung ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Abbildung 3. Offline lizenzierte App-Bestätigung*</span><span class="sxs-lookup"><span data-stu-id="8fc45-158">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="8fc45-159">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-159">Click **OK**.</span></span>

## <span data-ttu-id="8fc45-160">Herunterladen der Surface-App aus einem Microsoft Store for Business-Konto</span><span class="sxs-lookup"><span data-stu-id="8fc45-160">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="8fc45-161">Nachdem Sie eine APP im Offline Modus zum Microsoft Store for Business-Konto hinzugefügt haben, können Sie die APP als AppxBundle zu einer Bereitstellungsfreigabe herunterladen und hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-161">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="8fc45-162">Melden Sie sich bei dem Microsoft Store for Business-Konto an https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="8fc45-162">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="8fc45-163">Klicken Sie auf **Verwalten->-apps & Software**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-163">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="8fc45-164">Es wird eine Liste aller apps Ihres Unternehmens angezeigt, einschließlich der Surface-APP, die Sie im Abschnitt [Hinzufügen einer Oberfläche-APP zu einem Microsoft Store for Business-Konto](#add-surface-app-to-a-microsoft-store-for-business-account) in diesem Artikel hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="8fc45-164">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="8fc45-165">Klicken Sie unter **Aktionen**auf die Auslassungspunkte (**.**..), und klicken Sie dann auf **herunterladen für die Offlineverwendung** für die Surface-app.</span><span class="sxs-lookup"><span data-stu-id="8fc45-165">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="8fc45-166">Wählen Sie die gewünschten **Platt Form** -und **Architektur** Optionen aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8fc45-166">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="8fc45-168">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="8fc45-168">Figure 4.</span></span> <span data-ttu-id="8fc45-169">Herunterladen des AppxBundle-Pakets für eine APP</span><span class="sxs-lookup"><span data-stu-id="8fc45-169">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="8fc45-170">Klicken Sie auf **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-170">Click **Download**.</span></span> <span data-ttu-id="8fc45-171">Das AppxBundle-Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-171">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="8fc45-172">Stellen Sie sicher, dass Sie den Pfad der heruntergeladenen Datei notieren, da dies später in diesem Artikel erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8fc45-172">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="8fc45-173">Klicken Sie entweder auf die **codierte Lizenz** oder die Option für nicht **codierte Lizenzen** .</span><span class="sxs-lookup"><span data-stu-id="8fc45-173">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="8fc45-174">Verwenden Sie die codierte Lizenzoption mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows-Konfigurations-Designer verwenden, um ein Bereitstellungspaket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-174">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="8fc45-175">Wählen Sie die Option "nicht codierte Lizenz" aus, wenn Sie die Bereitstellung von Bild Wartung und-Verwaltung (DISM) oder Bereitstellungslösungen basierend auf Imaging verwenden, einschließlich des Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="8fc45-175">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="8fc45-176">Klicken Sie auf **generieren** , um die Lizenz für die APP zu generieren und herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-176">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="8fc45-177">Stellen Sie sicher, dass Sie den Pfad der Lizenzdatei notieren, da dies später in diesem Artikel erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8fc45-177">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="8fc45-178">Wenn Sie eine APP für die Offlineverwendung herunterladen, beispielsweise die Surface-APP, sehen Sie möglicherweise einen Abschnitt unten auf der Seite mit der Bezeichnung **erforderliche Frameworks**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-178">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="8fc45-179">Auf Ihren Zielcomputern müssen die Frameworks installiert sein, damit die app ausgeführt werden kann, daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (entweder x86 oder x64) wiederholen und Sie auch im Rahmen ihrer Windows-Bereitstellung, die weiter unten in diesem Artikel erläutert wird, einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-179">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="8fc45-180">Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-app.</span><span class="sxs-lookup"><span data-stu-id="8fc45-180">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="8fc45-182">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="8fc45-182">Figure 5.</span></span> <span data-ttu-id="8fc45-183">Erforderliche Frameworks für die Surface-App</span><span class="sxs-lookup"><span data-stu-id="8fc45-183">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="8fc45-184">Die Versionsnummern der Surface-APP und die erforderlichen Frameworks ändern sich, wenn die Apps aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8fc45-184">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="8fc45-185">Überprüfen Sie, ob die neueste Version der Surface-APP und die einzelnen Frameworks in Microsoft Store for Business erhältlich sind.</span><span class="sxs-lookup"><span data-stu-id="8fc45-185">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="8fc45-186">Verwenden Sie immer die Surface-APP und die empfohlenen Framework-Versionen, wie Sie von Microsoft Store für Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8fc45-186">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="8fc45-187">Das verwenden veralteter Frameworks oder fehlerhafter Versionen kann zu Fehlern oder Anwendungsabstürzen führen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-187">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="8fc45-188">Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-APP herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="8fc45-188">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="8fc45-189">Klicken Sie auf die Schaltfläche **herunterladen** unter **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-189">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="8fc45-190">Dadurch wird der Microsoft. VCLibs. 140.00-_14.0.23816.0-_x64__8wekyb3d8bbwe heruntergeladen. AppX-Datei in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="8fc45-190">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="8fc45-191">Klicken Sie auf die Schaltfläche **herunterladen** unter **Microsoft. net. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-191">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="8fc45-192">Dadurch wird die Datei Microsoft. net. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe. AppX in den angegebenen Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-192">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="8fc45-193">Für Surface-Geräte ist nur die 64-Bit-Version (x64) jedes Frameworks erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8fc45-193">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="8fc45-194">Surface-Geräte sind native 64-Bit-UEFI-Geräte und nicht mit 32-Bit-Versionen von Windows kompatibel, für die 32-Bit-Frameworks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8fc45-194">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="8fc45-195">Installieren der Surface-App auf Ihrem Computer mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fc45-195">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="8fc45-196">Mit dem folgenden Verfahren wird die Surface-App auf Ihrem Computer bereitgestellt und für alle auf dem Computer erstellten Benutzerkonten verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="8fc45-196">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="8fc45-197">Laden Sie die Oberfläche-App-AppxBundle und-Lizenzdatei herunter, und verwenden Sie das Verfahren, das in diesem Artikel im Abschnitt [herunterladen der Surface-App aus einem Microsoft Store for Business-Konto](#download-surface-app-from-a-microsoft-store-for-business-account) beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8fc45-197">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="8fc45-198">Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.</span><span class="sxs-lookup"><span data-stu-id="8fc45-198">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="8fc45-199">Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der app.</span><span class="sxs-lookup"><span data-stu-id="8fc45-199">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="8fc45-200">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="8fc45-200">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="8fc45-201">Wo `<DownloadPath>` befindet sich der Ordner, in den Sie die AppxBundle-und Lizenzdatei aus dem Microsoft Store for Business-Konto heruntergeladen haben?</span><span class="sxs-lookup"><span data-stu-id="8fc45-201">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="8fc45-202">Wenn Sie beispielsweise die Dateien nach c:\temp heruntergeladen haben, lautet der Befehl, den Sie ausführen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8fc45-202">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="8fc45-203">Die Surface-App ist jetzt auf dem aktuellen Windows-Computer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8fc45-203">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="8fc45-204">Bevor die Surface-App auf dem Computer, auf dem Sie bereitgestellt wurde, funktionsfähig ist, müssen Sie auch die oben in diesem Artikel beschriebenen Frameworks bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8fc45-204">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="8fc45-205">Zum Bereitstellen dieser Frameworks verwenden Sie das folgende Verfahren in der erhöhten PowerShell-Sitzung, die Sie für die Bereitstellung der Surface-App verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8fc45-205">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="8fc45-206">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="8fc45-206">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="8fc45-207">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="8fc45-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="8fc45-208">Installieren der Surface-App mit MDT</span><span class="sxs-lookup"><span data-stu-id="8fc45-208">Install Surface app with MDT</span></span>
<span data-ttu-id="8fc45-209">Das folgende Verfahren verwendet MDT, um die Installation der Surface-App zum Zeitpunkt der Bereitstellung zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="8fc45-209">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="8fc45-210">Die App wird automatisch von MDT bereitgestellt, sodass Sie dieses Verfahren mit bereits vorhandenen Images ausführen können.</span><span class="sxs-lookup"><span data-stu-id="8fc45-210">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="8fc45-211">Dies ist die empfohlene Vorgehensweise zum Bereitstellen der Surface-App als Teil einer Windows-Bereitstellung für Surface Devices, da dadurch die plattformübergreifende Kompatibilität des Windows-Abbilds nicht verringert wird.</span><span class="sxs-lookup"><span data-stu-id="8fc45-211">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="8fc45-212">Laden Sie die Oberfläche-App-AppxBundle und-Lizenzdatei mithilfe des [weiter oben in diesem Artikel](#download-surface-app-from-a-microsoft-store-for-business-account)beschriebenen Verfahrens herunter.</span><span class="sxs-lookup"><span data-stu-id="8fc45-212">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="8fc45-213">Importieren Sie die heruntergeladenen Dateien mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench als neue **Anwendung mit Quelldateien**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-213">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="8fc45-214">Geben Sie auf der Seite **Befehls Details** des Assistenten für neue Anwendung das Standard **Arbeitsverzeichnis** an, und geben Sie für den **Befehl** den Dateinamen des AppxBundle wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="8fc45-214">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="8fc45-215">Befehl</span><span class="sxs-lookup"><span data-stu-id="8fc45-215">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="8fc45-216">Arbeitsverzeichnis:%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="8fc45-216">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="8fc45-217">Damit die Surface-App auf dem Zielcomputer funktioniert, müssen auch die oben in diesem Artikel beschriebenen Frameworks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8fc45-217">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="8fc45-218">Gehen Sie wie folgt vor, um die für die Surface-App erforderlichen Frameworks in MDT zu importieren und als Abhängigkeiten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8fc45-218">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="8fc45-219">Laden Sie die Framework-Dateien mithilfe des weiter oben in diesem Artikel beschriebenen Verfahrens herunter.</span><span class="sxs-lookup"><span data-stu-id="8fc45-219">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="8fc45-220">Speichern Sie die einzelnen Frameworks in einem separaten Ordner.</span><span class="sxs-lookup"><span data-stu-id="8fc45-220">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="8fc45-221">Importieren Sie die heruntergeladenen Dateien mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench als neue **Anwendung mit Quelldateien**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-221">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="8fc45-222">Geben Sie auf der Seite **Befehls Details** den Dateinamen jeder Anwendung ein, die Sie im **Befehls** Feld heruntergeladen haben, und das standardmäßige Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8fc45-222">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="8fc45-223">Verwenden Sie diesen Vorgang, um die Frameworks als Abhängigkeiten der Surface-APP zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8fc45-223">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="8fc45-224">Öffnen Sie die Eigenschaften der Surface-app in der MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="8fc45-224">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="8fc45-225">Klicken Sie auf die Registerkarte **Abhängigkeiten** , und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-225">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="8fc45-226">Aktivieren Sie das Kontrollkästchen für jedes Framework unter dem Namen, den Sie im Assistenten für neue Anwendungen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="8fc45-226">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="8fc45-227">Nach dem Importieren steht die Surface-App im Schritt " **Anwendungen** " des Windows-Bereitstellungs-Assistenten zur Auswahl zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8fc45-227">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="8fc45-228">Sie können die Anwendung auch automatisch installieren, indem Sie sie in der Tasksequenz für die Bereitstellung wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="8fc45-228">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="8fc45-229">Öffnen Sie die Tasksequenz für die Bereitstellung in der Deployment Workbench von MDT.</span><span class="sxs-lookup"><span data-stu-id="8fc45-229">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="8fc45-230">Fügen Sie dem Abschnitt **Status wiederherstellen** der Bereitstellung eine neue Aufgabe **Anwendung installieren** hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fc45-230">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="8fc45-231">Wählen Sie **eine einzelne Anwendung installieren** aus, und geben Sie die **Surface-App** als die **Anwendung an, die installiert werden soll**.</span><span class="sxs-lookup"><span data-stu-id="8fc45-231">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="8fc45-232">Weitere Informationen zum Einschließen von apps in Ihre Windows-Bereitstellungen finden Sie unter [Bereitstellen von Windows 10 mit dem Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="8fc45-232">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
