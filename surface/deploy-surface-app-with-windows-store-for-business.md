---
title: Bereitstellen der Surface-App Microsoft Store für Unternehmen oder Microsoft Store für Bildungseinrichtungen (Surface)
description: Erfahren Sie, wie Sie die Surface-App mit Microsoft Store für Unternehmen oder Microsoft Store für Bildungseinrichtungen hinzufügen und herunterladen sowie die Surface-App mit PowerShell und MDT installieren.
keywords: surface app, app, deployment, customize
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
ms.date: 4/16/2021
ms.openlocfilehash: c7a882859339ff3d7feeb685c62672bc57c301ec
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576525"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a><span data-ttu-id="87581-104">Bereitstellen der Surface-App mit Microsoft Store für Unternehmen und Education</span><span class="sxs-lookup"><span data-stu-id="87581-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="87581-105">Betrifft</span><span class="sxs-lookup"><span data-stu-id="87581-105">Applies to</span></span>**

- <span data-ttu-id="87581-106">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="87581-106">Surface Laptop 4</span></span>
- <span data-ttu-id="87581-107">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="87581-107">Surface Pro 7+</span></span>
- <span data-ttu-id="87581-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="87581-108">Surface Laptop Go</span></span>
- <span data-ttu-id="87581-109">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="87581-109">Surface Pro 7</span></span>
- <span data-ttu-id="87581-110">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="87581-110">Surface Laptop 3</span></span>
- <span data-ttu-id="87581-111">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="87581-111">Surface Pro 6</span></span>
- <span data-ttu-id="87581-112">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="87581-112">Surface Laptop 2</span></span>
- <span data-ttu-id="87581-113">Surface Go</span><span class="sxs-lookup"><span data-stu-id="87581-113">Surface Go</span></span>
- <span data-ttu-id="87581-114">Surface Go mit LTE</span><span class="sxs-lookup"><span data-stu-id="87581-114">Surface Go with LTE</span></span>
- <span data-ttu-id="87581-115">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="87581-115">Surface Book 2</span></span>
- <span data-ttu-id="87581-116">Surface Pro mit LTE Advanced (Modell 1807)</span><span class="sxs-lookup"><span data-stu-id="87581-116">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="87581-117">Surface Pro (Modell 1796)</span><span class="sxs-lookup"><span data-stu-id="87581-117">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="87581-118">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="87581-118">Surface Laptop</span></span>
- <span data-ttu-id="87581-119">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="87581-119">Surface Studio</span></span>
- <span data-ttu-id="87581-120">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="87581-120">Surface Studio 2</span></span>
- <span data-ttu-id="87581-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="87581-121">Surface Book</span></span>
- <span data-ttu-id="87581-122">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="87581-122">Surface Pro 4</span></span>
- <span data-ttu-id="87581-123">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="87581-123">Surface 3 LTE</span></span>
- <span data-ttu-id="87581-124">Surface3</span><span class="sxs-lookup"><span data-stu-id="87581-124">Surface 3</span></span>
- <span data-ttu-id="87581-125">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="87581-125">Surface Pro 3</span></span>


<span data-ttu-id="87581-126">Die Surface-App ist eine Microsoft Store App, die die Steuerung vieler Surface-spezifischer Einstellungen und Optionen bietet, darunter:</span><span class="sxs-lookup"><span data-stu-id="87581-126">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="87581-127">Aktivieren oder Deaktivieren der Windows-Taste auf dem Surface-Gerät 
</span><span class="sxs-lookup"><span data-stu-id="87581-127">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="87581-128">Anpassen der Empfindlichkeit des Surface-Stifts 
</span><span class="sxs-lookup"><span data-stu-id="87581-128">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="87581-129">Anpassen der Tastenaktionen des Surface-Stifts 
</span><span class="sxs-lookup"><span data-stu-id="87581-129">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="87581-130">Aktivieren oder Deaktivieren der Audioerweiterungen des Surface-Geräts 
</span><span class="sxs-lookup"><span data-stu-id="87581-130">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="87581-131">Schneller Zugriff auf Supportdokumentation und -informationen für Ihr Gerät</span><span class="sxs-lookup"><span data-stu-id="87581-131">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="87581-132">Kunden, die Windows Update verwenden, erhalten normalerweise die Surface-App als Teil automatischer Updates.</span><span class="sxs-lookup"><span data-stu-id="87581-132">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="87581-133">Wenn Ihre Organisation jedoch Bilder für die Bereitstellung auf Ihren Surface-Geräten vorbereitet, sollten Sie möglicherweise die Surface-App (früher als Surface Hub bezeichnet) in den Imageerstellungs- und Bereitstellungsprozess einbeigen, anstatt die Benutzer jedes einzelnen Geräts zum Herunterladen und Installieren der App aus dem Microsoft Store oder Ihrer Microsoft Store für Unternehmen zu Microsoft Store für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="87581-133">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="87581-134">Dieser Artikel gilt nicht für Surface Pro X. Weitere Informationen finden Sie unter [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="87581-134">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <a name="surface-app-overview"></a><span data-ttu-id="87581-135">Übersicht über Surface-App</span><span class="sxs-lookup"><span data-stu-id="87581-135">Surface app overview</span></span>

<span data-ttu-id="87581-136">Die Surface-App ist als kostenloser Download von der [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="87581-136">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="87581-137">Benutzer können sie aus dem Microsoft Store herunterladen und installieren, aber wenn Ihre Organisation stattdessen Microsoft Store für Unternehmen verwendet, müssen Sie sie dem Inventar Ihres Speichers hinzufügen und möglicherweise die App als Teil Ihres Windows-Bereitstellungsprozesses hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="87581-137">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="87581-138">Diese Prozesse werden in diesem Artikel behandelt.</span><span class="sxs-lookup"><span data-stu-id="87581-138">These processes are discussed throughout this article.</span></span> <span data-ttu-id="87581-139">Weitere Informationen zu Microsoft Store für Unternehmen finden Sie [unter Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/) im Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="87581-139">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a><span data-ttu-id="87581-140">Hinzufügen einer Surface-App zu Microsoft Store für Unternehmen Konto</span><span class="sxs-lookup"><span data-stu-id="87581-140">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="87581-141">Bevor Benutzer eine App über das Microsoft Store für Unternehmen-Konto eines Unternehmens installieren oder bereitstellen können, müssen die gewünschten Apps zuerst für die Benutzer eines Unternehmens verfügbar gemacht und lizenziert werden.</span><span class="sxs-lookup"><span data-stu-id="87581-141">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="87581-142">Wenn Sie dies noch nicht getan haben, erstellen Sie [ein Microsoft Store für Unternehmen Konto.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="87581-142">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="87581-143">Melden Sie sich am Portal an.</span><span class="sxs-lookup"><span data-stu-id="87581-143">Log on to the portal.</span></span> 

3. <span data-ttu-id="87581-144">Offlinelizenzierung aktivieren: Klicken Sie auf >Store **verwalten,** und aktivieren Sie dann das Kontrollkästchen Offline lizenzierte Apps für Personen anzeigen, die im Store einkaufen, wie in Abbildung 1 dargestellt. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87581-144">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="87581-145">Weitere Informationen zu Microsoft Store für Unternehmen App-Lizenzierungsmodellen finden Sie unter [Apps in Microsoft Store für Unternehmen und Education](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="87581-145">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Kontrollkästchen Offlinelizenzen-Apps anzeigen](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="87581-147">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="87581-147">Figure 1.</span></span> <span data-ttu-id="87581-148">Aktivieren von Apps für die Offlineverwendung</span><span class="sxs-lookup"><span data-stu-id="87581-148">Enable apps for offline use</span></span>*

4. <span data-ttu-id="87581-149">Fügen Sie Ihrem konto Microsoft Store für Unternehmen Surface-App hinzu, indem Sie folgendes Verfahren verwenden:</span><span class="sxs-lookup"><span data-stu-id="87581-149">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="87581-150">Klicken Sie auf **das Menü Geschäft.**</span><span class="sxs-lookup"><span data-stu-id="87581-150">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="87581-151">Geben Sie im Suchfeld **Surface-App**ein, und klicken Sie dann auf das Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="87581-151">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="87581-152">Nachdem die Surface-App in den Suchergebnissen angezeigt wurde, klicken Sie auf das Symbol der App.</span><span class="sxs-lookup"><span data-stu-id="87581-152">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="87581-153">Ihnen wird eine Auswahl angezeigt (wählen **Sie Online** oder **Offline**aus), wie in Abbildung 2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="87581-153">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App zu Ihrem Inventar hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="87581-155">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="87581-155">Figure 2.</span></span> <span data-ttu-id="87581-156">Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App zu Ihrem Inventar hinzu.</span><span class="sxs-lookup"><span data-stu-id="87581-156">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="87581-157">Klicken **Sie auf Offline,** um den Offlinelizenzierungsmodus auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="87581-157">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="87581-158">Klicken **Sie auf App herunterladen,** um die App zu Ihrem Microsoft Store für Unternehmen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="87581-158">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="87581-159">Wie in Abbildung 3 dargestellt, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mithilfe eines Verwaltungstools bereitgestellt oder von der Inventarseite des Unternehmens in ihrem privaten Store heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="87581-159">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="87581-160">Offline lizenziertes App-Bestätigungsfenster ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Abbildung 3. Offline lizenzierte App-Bestätigung*</span><span class="sxs-lookup"><span data-stu-id="87581-160">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="87581-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87581-161">Click **OK**.</span></span>

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a><span data-ttu-id="87581-162">Herunterladen der Surface-App aus Microsoft Store für Unternehmen Konto</span><span class="sxs-lookup"><span data-stu-id="87581-162">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="87581-163">Nachdem Sie dem Microsoft Store für Unternehmen im Offlinemodus eine App hinzugefügt haben, können Sie die App als AppxBundle zu einer Bereitstellungsfreigabe herunterladen und hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="87581-163">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="87581-164">Melden Sie sich beim Microsoft Store für Unternehmen unter https://businessstore.microsoft.com an.</span><span class="sxs-lookup"><span data-stu-id="87581-164">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="87581-165">Klicken **Sie auf >Apps & verwalten.**</span><span class="sxs-lookup"><span data-stu-id="87581-165">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="87581-166">Eine Liste aller Apps Ihres Unternehmens wird angezeigt, einschließlich der Surface-App, die Sie im Abschnitt [Add Surface app to a Microsoft Store für Unternehmen account](#add-surface-app-to-a-microsoft-store-for-business-account) dieses Artikels hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="87581-166">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="87581-167">Klicken **Sie unter Aktionen**auf die Auslassungspunkte (**...**), und klicken Sie dann auf Für **die Offlineverwendung** für die Surface-App herunterladen.</span><span class="sxs-lookup"><span data-stu-id="87581-167">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="87581-168">Wählen Sie die gewünschten **Plattform-** und **Architekturoptionen** aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="87581-168">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="87581-170">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="87581-170">Figure 4.</span></span> <span data-ttu-id="87581-171">Herunterladen des AppxBundle-Pakets für eine App</span><span class="sxs-lookup"><span data-stu-id="87581-171">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="87581-172">Klicken Sie **auf Herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="87581-172">Click **Download**.</span></span> <span data-ttu-id="87581-173">Das AppxBundle-Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="87581-173">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="87581-174">Achten Sie darauf, den Pfad der heruntergeladenen Datei zu notieren, da Sie dies später in diesem Artikel benötigen.</span><span class="sxs-lookup"><span data-stu-id="87581-174">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="87581-175">Klicken Sie entweder auf **die Option Codierte Lizenz** oder auf Nicht **codierte** Lizenz.</span><span class="sxs-lookup"><span data-stu-id="87581-175">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="87581-176">Verwenden Sie die Option Codierte Lizenz mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows Configuration Designer zum Erstellen eines Bereitstellungspakets verwenden.</span><span class="sxs-lookup"><span data-stu-id="87581-176">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="87581-177">Wählen Sie die Option Nicht codierte Lizenz aus, wenn Sie Bereitstellungsimagewartung und -verwaltung (Deployment Image Servicing and Management, DISM) oder Bereitstellungslösungen basierend auf der Imageerstellung verwenden, einschließlich des Microsoft Deployment Toolkits (MDT).</span><span class="sxs-lookup"><span data-stu-id="87581-177">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="87581-178">Klicken **Sie auf Generieren,** um die Lizenz für die App zu generieren und herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="87581-178">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="87581-179">Achten Sie darauf, den Pfad der Lizenzdatei zu notieren, da Sie dies später in diesem Artikel benötigen.</span><span class="sxs-lookup"><span data-stu-id="87581-179">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="87581-180">Wenn Sie eine App für die Offlineverwendung herunterladen, z. B. die Surface-App, wird möglicherweise ein Abschnitt unten auf der Seite mit der Bezeichnung **Erforderliche Frameworks angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="87581-180">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="87581-181">Auf Ihren Zielcomputern müssen die Frameworks installiert sein, damit die App ausgeführt werden kann. Daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (x86 oder x64) wiederholen und sie auch als Teil Ihrer Windows-Bereitstellung, die weiter später in diesem Artikel behandelt wird, enthalten.</span><span class="sxs-lookup"><span data-stu-id="87581-181">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="87581-182">Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-App.</span><span class="sxs-lookup"><span data-stu-id="87581-182">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="87581-184">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="87581-184">Figure 5.</span></span> <span data-ttu-id="87581-185">Erforderliche Frameworks für die Surface-App</span><span class="sxs-lookup"><span data-stu-id="87581-185">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="87581-186">Die Versionsnummern der Surface-App und die erforderlichen Frameworks ändern sich, sobald die Apps aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="87581-186">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="87581-187">Überprüfen Sie die neueste Version der Surface-App und jedes Framework in Microsoft Store für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="87581-187">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="87581-188">Verwenden Sie immer die Surface-App und die empfohlenen Frameworkversionen, wie von Microsoft Store für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="87581-188">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="87581-189">Die Verwendung veralteter Frameworks oder falscher Versionen kann zu Fehlern oder Anwendungsabstürzen führen.</span><span class="sxs-lookup"><span data-stu-id="87581-189">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="87581-190">Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-App herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="87581-190">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="87581-191">Klicken Sie **unter** **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**auf die Schaltfläche Herunterladen.</span><span class="sxs-lookup"><span data-stu-id="87581-191">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="87581-192">Dadurch wird Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe heruntergeladen. Appx-Datei in Den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="87581-192">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="87581-193">Klicken Sie **unter** **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**auf die Schaltfläche Herunterladen.</span><span class="sxs-lookup"><span data-stu-id="87581-193">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="87581-194">Dadurch wird die datei Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx in den angegebenen Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="87581-194">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="87581-195">Nur die 64-Bit-Version (x64) jedes Frameworks ist für Surface-Geräte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="87581-195">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="87581-196">Surface-Geräte sind systemeigene 64-Bit-UEFI-Geräte und nicht kompatibel mit 32-Bit-Versionen (x86) von Windows die 32-Bit-Frameworks erfordern würden.</span><span class="sxs-lookup"><span data-stu-id="87581-196">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <a name="install-surface-app-on-your-computer-with-powershell"></a><span data-ttu-id="87581-197">Installieren der Surface-App auf Ihrem Computer mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="87581-197">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="87581-198">Das folgende Verfahren stellt die Surface-App auf Ihrem Computer bereit und stellt sie für alle Benutzerkonten zur Verfügung, die anschließend auf dem Computer erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="87581-198">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="87581-199">Laden Sie mithilfe des verfahrens, das im Abschnitt Herunterladen der [Surface-App](#download-surface-app-from-a-microsoft-store-for-business-account) aus einem Microsoft Store für Unternehmen-Konto dieses Artikels beschrieben wird, die Surface-App App AppxBundle und die Lizenzdatei herunter.</span><span class="sxs-lookup"><span data-stu-id="87581-199">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="87581-200">Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.</span><span class="sxs-lookup"><span data-stu-id="87581-200">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="87581-201">Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der App.</span><span class="sxs-lookup"><span data-stu-id="87581-201">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="87581-202">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="87581-202">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="87581-203">Wo `<DownloadPath>` befindet sich der Ordner, in dem Sie die AppxBundle- und Lizenzdatei aus dem Microsoft Store für Unternehmen heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="87581-203">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="87581-204">Wenn Sie die Dateien beispielsweise in c:\Temp heruntergeladen haben, wird der folgende Befehl ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="87581-204">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="87581-205">Die Surface-App ist jetzt auf dem aktuellen Windows-Computer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87581-205">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="87581-206">Bevor die Surface-App auf dem Computer funktionsfähig ist, auf dem sie bereitgestellt wurde, müssen Sie auch die weiter oben in diesem Artikel beschriebenen Frameworks bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="87581-206">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="87581-207">Verwenden Sie zum Bereitstellen dieser Frameworks das folgende Verfahren in der PowerShell-Sitzung mit erhöhten Rechten, die Sie zum Bereitstellen der Surface-App verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="87581-207">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="87581-208">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="87581-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="87581-209">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="87581-209">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a><span data-ttu-id="87581-210">Installieren der Surface-App mit MDT</span><span class="sxs-lookup"><span data-stu-id="87581-210">Install Surface app with MDT</span></span>
<span data-ttu-id="87581-211">Im folgenden Verfahren wird MDT verwendet, um die Installation der Surface-App zum Zeitpunkt der Bereitstellung zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="87581-211">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="87581-212">Die App wird automatisch von MDT bereitgestellt, sodass Sie dieses Verfahren mit bereits vorhandenen Images ausführen können.</span><span class="sxs-lookup"><span data-stu-id="87581-212">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="87581-213">Dies ist der empfohlene Prozess für die Bereitstellung der Surface-App als Teil einer Windows-Bereitstellung auf Surface-Geräten, da dadurch die plattformübergreifende Kompatibilität des Windows wird.</span><span class="sxs-lookup"><span data-stu-id="87581-213">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="87581-214">Laden Sie mithilfe des [weiter oben in diesem Artikel beschriebenen](#download-surface-app-from-a-microsoft-store-for-business-account)Verfahrens die Surface-App App AppxBundle und die Lizenzdatei herunter.</span><span class="sxs-lookup"><span data-stu-id="87581-214">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="87581-215">Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**</span><span class="sxs-lookup"><span data-stu-id="87581-215">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="87581-216">Geben Sie **auf** der Seite Befehlsdetails \*\*\*\* des Assistenten für \*\*\*\* neue Anwendungen das Standardarbeitsverzeichnis an, und geben Sie für den Befehl den Dateinamen des AppxBundle wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="87581-216">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="87581-217">Befehl:</span><span class="sxs-lookup"><span data-stu-id="87581-217">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="87581-218">Arbeitsverzeichnis: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="87581-218">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="87581-219">Damit die Surface-App auf dem Zielcomputer funktioniert, sind auch die weiter oben in diesem Artikel beschriebenen Frameworks erforderlich.</span><span class="sxs-lookup"><span data-stu-id="87581-219">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="87581-220">Verwenden Sie das folgende Verfahren, um die für die Surface-App erforderlichen Frameworks in MDT zu importieren und als Abhängigkeiten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="87581-220">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="87581-221">Laden Sie mithilfe des weiter oben in diesem Artikel beschriebenen Verfahrens die Frameworkdateien herunter.</span><span class="sxs-lookup"><span data-stu-id="87581-221">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="87581-222">Store framework in einem separaten Ordner.</span><span class="sxs-lookup"><span data-stu-id="87581-222">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="87581-223">Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**</span><span class="sxs-lookup"><span data-stu-id="87581-223">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="87581-224">Geben Sie auf der Seite **Befehlsdetails** den Dateinamen der einzelnen heruntergeladenen Anwendungen in das **Feld Befehl** und das Standardarbeitsverzeichnis ein.</span><span class="sxs-lookup"><span data-stu-id="87581-224">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="87581-225">Verwenden Sie diesen Prozess, um die Frameworks als Abhängigkeiten der Surface-App zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="87581-225">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="87581-226">Öffnen Sie die Eigenschaften der Surface-App in der MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="87581-226">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="87581-227">Klicken Sie **auf die** Registerkarte Abhängigkeiten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="87581-227">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="87581-228">Aktivieren Sie das Kontrollkästchen für jedes Framework mit dem Namen, den Sie im Assistenten für neue Anwendungen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="87581-228">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="87581-229">Nach dem Import steht die Surface-App \*\*\*\* im Schritt Anwendungen des Assistenten für die Windows zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="87581-229">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="87581-230">Sie können die Anwendung auch automatisch installieren, indem Sie sie in der Tasksequenz für die Bereitstellung wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="87581-230">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="87581-231">Öffnen Sie die Tasksequenz für die Bereitstellung in der Deployment Workbench von MDT.</span><span class="sxs-lookup"><span data-stu-id="87581-231">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="87581-232">Fügen Sie dem Abschnitt **Status wiederherstellen** der Bereitstellung eine neue Aufgabe **Anwendung installieren** hinzu.</span><span class="sxs-lookup"><span data-stu-id="87581-232">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="87581-233">Wählen **Sie Installieren einer einzelnen Anwendung** aus, und geben Sie die Surface **App** als **zu installierende Anwendung an.**</span><span class="sxs-lookup"><span data-stu-id="87581-233">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="87581-234">Weitere Informationen zum Hinzufügen von Apps in Ihre Windows finden Sie unter [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="87581-234">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
