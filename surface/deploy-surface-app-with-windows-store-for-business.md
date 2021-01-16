---
title: Bereitstellen der Surface-App mit dem Microsoft Store für Unternehmen oder dem Microsoft Store für Bildungseinrichtungen (Surface)
description: Erfahren Sie, wie Sie eine Surface-App mit dem Microsoft Store für Unternehmen oder dem Microsoft Store für Bildungseinrichtungen hinzufügen und herunterladen sowie die Surface-App mit PowerShell und MDT installieren.
keywords: Surface-App, App, Bereitstellung, anpassen
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
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271072"
---
# <span data-ttu-id="4ef03-104">Bereitstellen der Surface-App im Microsoft Store für Unternehmen und Bildungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="4ef03-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="4ef03-105">Betrifft</span><span class="sxs-lookup"><span data-stu-id="4ef03-105">Applies to</span></span>**

- <span data-ttu-id="4ef03-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="4ef03-106">Surface Pro 7+</span></span>
- <span data-ttu-id="4ef03-107">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="4ef03-107">Surface Laptop Go</span></span>
- <span data-ttu-id="4ef03-108">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="4ef03-108">Surface Pro 7</span></span>
- <span data-ttu-id="4ef03-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="4ef03-109">Surface Laptop 3</span></span>
- <span data-ttu-id="4ef03-110">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="4ef03-110">Surface Pro 6</span></span>
- <span data-ttu-id="4ef03-111">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="4ef03-111">Surface Laptop 2</span></span>
- <span data-ttu-id="4ef03-112">Surface Go</span><span class="sxs-lookup"><span data-stu-id="4ef03-112">Surface Go</span></span>
- <span data-ttu-id="4ef03-113">Surface Go mit LTE</span><span class="sxs-lookup"><span data-stu-id="4ef03-113">Surface Go with LTE</span></span>
- <span data-ttu-id="4ef03-114">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="4ef03-114">Surface Book 2</span></span>
- <span data-ttu-id="4ef03-115">Surface Pro mit LTE Advanced (Modell 1807)</span><span class="sxs-lookup"><span data-stu-id="4ef03-115">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="4ef03-116">Surface Pro (Modell 1796)</span><span class="sxs-lookup"><span data-stu-id="4ef03-116">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="4ef03-117">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="4ef03-117">Surface Laptop</span></span>
- <span data-ttu-id="4ef03-118">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="4ef03-118">Surface Studio</span></span>
- <span data-ttu-id="4ef03-119">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="4ef03-119">Surface Studio 2</span></span>
- <span data-ttu-id="4ef03-120">Surface Book</span><span class="sxs-lookup"><span data-stu-id="4ef03-120">Surface Book</span></span>
- <span data-ttu-id="4ef03-121">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4ef03-121">Surface Pro 4</span></span>
- <span data-ttu-id="4ef03-122">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="4ef03-122">Surface 3 LTE</span></span>
- <span data-ttu-id="4ef03-123">Surface3</span><span class="sxs-lookup"><span data-stu-id="4ef03-123">Surface 3</span></span>
- <span data-ttu-id="4ef03-124">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="4ef03-124">Surface Pro 3</span></span>


<span data-ttu-id="4ef03-125">Die Surface App ist eine einfache Microsoft Store-App, die die Steuerung vieler Surface-spezifischer Einstellungen und Optionen bietet, darunter:</span><span class="sxs-lookup"><span data-stu-id="4ef03-125">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="4ef03-126">Aktivieren oder Deaktivieren der Windows-Taste auf dem Surface-Gerät 
</span><span class="sxs-lookup"><span data-stu-id="4ef03-126">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="4ef03-127">Anpassen der Empfindlichkeit des Surface-Stifts 
</span><span class="sxs-lookup"><span data-stu-id="4ef03-127">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="4ef03-128">Anpassen der Tastenaktionen des Surface-Stifts 
</span><span class="sxs-lookup"><span data-stu-id="4ef03-128">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="4ef03-129">Aktivieren oder Deaktivieren der Audioerweiterungen des Surface-Geräts 
</span><span class="sxs-lookup"><span data-stu-id="4ef03-129">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="4ef03-130">Schneller Zugriff auf Supportdokumentation und Informationen für Ihr Gerät</span><span class="sxs-lookup"><span data-stu-id="4ef03-130">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="4ef03-131">Kunden, die Windows Update verwenden, erhalten normalerweise die Surface-App als Teil automatischer Updates.</span><span class="sxs-lookup"><span data-stu-id="4ef03-131">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="4ef03-132">Wenn Ihre Organisation jedoch Images für die Bereitstellung auf Ihren Surface-Geräten vorbereitet, sollten Sie die Surface-App (früher Als Surface Hub bezeichnet) in den Imageerstellungs- und Bereitstellungsprozess einplanen, anstatt dass Benutzer jedes einzelnen Geräts die App aus dem Microsoft Store oder aus dem Microsoft Store für Unternehmen herunterladen und installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-132">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="4ef03-133">Dieser Artikel gilt nicht für Surface Pro X. Weitere Informationen finden Sie unter [Bereitstellen, Verwalten](surface-pro-arm-app-management.md) und Warten von Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="4ef03-133">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="4ef03-134">Übersicht über die Surface-App</span><span class="sxs-lookup"><span data-stu-id="4ef03-134">Surface app overview</span></span>

<span data-ttu-id="4ef03-135">Die Surface App steht als kostenloser Download aus dem [Microsoft Store zur Verfügung.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="4ef03-135">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="4ef03-136">Benutzer können sie aus dem Microsoft Store herunterladen und installieren. Wenn Ihre Organisation stattdessen den Microsoft Store für Unternehmen verwendet, müssen Sie sie dem Inventar Ihres Store hinzufügen und die App möglicherweise in Ihren Windows-Bereitstellungsprozess mit einplanen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-136">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="4ef03-137">Diese Prozesse werden in diesem Artikel behandelt.</span><span class="sxs-lookup"><span data-stu-id="4ef03-137">These processes are discussed throughout this article.</span></span> <span data-ttu-id="4ef03-138">Weitere Informationen zum Microsoft Store für Unternehmen finden Sie im [Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/) im Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="4ef03-138">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="4ef03-139">Hinzufügen einer Surface-App zu einem Microsoft Store für Unternehmen-Konto</span><span class="sxs-lookup"><span data-stu-id="4ef03-139">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="4ef03-140">Bevor Benutzer eine App aus dem Microsoft Store für Unternehmen eines Unternehmens installieren oder bereitstellen können, müssen die gewünschten Apps zuerst für die Benutzer eines Unternehmens verfügbar gemacht und lizenziert werden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-140">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="4ef03-141">Falls noch nicht geschehen, erstellen Sie ein [Microsoft Store für Unternehmen-Konto.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="4ef03-141">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="4ef03-142">Melden Sie sich beim Portal an.</span><span class="sxs-lookup"><span data-stu-id="4ef03-142">Log on to the portal.</span></span> 

3. <span data-ttu-id="4ef03-143">Aktivieren Sie die Offlinelizenzierung: Klicken Sie auf "Manage->**Store settings",** und aktivieren Sie dann das Kontrollkästchen "Offline lizenzierte Apps für Personen anzeigen, die im Store kaufen", wie in Abbildung 1 dargestellt. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4ef03-143">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="4ef03-144">Weitere Informationen zu Lizenzierungsmodellen für Microsoft Store für Unternehmen-Apps finden Sie unter ["Apps" im Microsoft Store für Unternehmen und Bildungseinrichtungen.](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="4ef03-144">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Kontrollkästchen "Apps für Offlinelizenzen anzeigen"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="4ef03-146">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="4ef03-146">Figure 1.</span></span> <span data-ttu-id="4ef03-147">Aktivieren von Apps für die Offlineverwendung</span><span class="sxs-lookup"><span data-stu-id="4ef03-147">Enable apps for offline use</span></span>*

4. <span data-ttu-id="4ef03-148">Fügen Sie Ihrem Microsoft Store für Unternehmen-Konto eine Surface-App hinzu, indem Sie dieses Verfahren verwenden:</span><span class="sxs-lookup"><span data-stu-id="4ef03-148">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="4ef03-149">Klicken Sie auf das **Menü "Shop".**</span><span class="sxs-lookup"><span data-stu-id="4ef03-149">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="4ef03-150">Geben Sie im Suchfeld die **Surface-App ein,** und klicken Sie dann auf das Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="4ef03-150">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="4ef03-151">Nachdem die Surface-App in den Suchergebnissen angezeigt wurde, klicken Sie auf das Symbol der App.</span><span class="sxs-lookup"><span data-stu-id="4ef03-151">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="4ef03-152">Ihnen wird eine Auswahl angezeigt (Wählen **Sie "Online"** oder **"Offline"** aus), wie in Abbildung 2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4ef03-152">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App ihrem Bestand hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="4ef03-154">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="4ef03-154">Figure 2.</span></span> <span data-ttu-id="4ef03-155">Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App ihrem Bestand hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ef03-155">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="4ef03-156">Klicken Sie **auf "Offline",** um den Offlinelizenzierungsmodus auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-156">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="4ef03-157">Klicken **Sie auf "App herunterladen",** um die App ihrem Microsoft Store für Unternehmen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-157">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="4ef03-158">Wie in Abbildung 3 dargestellt, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mithilfe eines Verwaltungstools bereitgestellt oder von der Bestandsseite des Unternehmens in ihrem privaten Store heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="4ef03-158">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="4ef03-159">Fenster "Offline lizenzierte App-Bestätigung", ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Abbildung 3. Offline lizenzierte App-Bestätigung*</span><span class="sxs-lookup"><span data-stu-id="4ef03-159">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="4ef03-160">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ef03-160">Click **OK**.</span></span>

## <span data-ttu-id="4ef03-161">Herunterladen der Surface-App aus einem Microsoft Store für Unternehmen-Konto</span><span class="sxs-lookup"><span data-stu-id="4ef03-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="4ef03-162">Nachdem Sie eine App zum Microsoft Store für Unternehmen-Konto im Offlinemodus hinzugefügt haben, können Sie die App herunterladen und als AppxBundle zu einer Bereitstellungsfreigabe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="4ef03-163">Melden Sie sich beim Microsoft Store für Unternehmen-Konto unter https://businessstore.microsoft.com an.</span><span class="sxs-lookup"><span data-stu-id="4ef03-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="4ef03-164">Klicken **Sie auf ">Apps & Software verwalten".**</span><span class="sxs-lookup"><span data-stu-id="4ef03-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="4ef03-165">Es wird eine Liste aller Apps Ihres Unternehmens angezeigt, einschließlich der Surface-App, die Sie in der Add Surface App zu einem [Microsoft Store für](#add-surface-app-to-a-microsoft-store-for-business-account) Business-Kontoabschnitt in diesem Artikel hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="4ef03-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="4ef03-166">Klicken **Sie**unter "Aktionen" auf die Auslassungspunkte (**...**), und klicken Sie dann auf **"Zur Offlineverwendung für** die Surface-App herunterladen".</span><span class="sxs-lookup"><span data-stu-id="4ef03-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="4ef03-167">Wählen Sie die \*\*\*\* gewünschten **Plattform-** und Architekturoptionen aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4ef03-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="4ef03-169">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="4ef03-169">Figure 4.</span></span> <span data-ttu-id="4ef03-170">Herunterladen des AppxBundle-Pakets für eine App</span><span class="sxs-lookup"><span data-stu-id="4ef03-170">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="4ef03-171">Klicken Sie **auf "Herunterladen".**</span><span class="sxs-lookup"><span data-stu-id="4ef03-171">Click **Download**.</span></span> <span data-ttu-id="4ef03-172">Das AppxBundle-Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="4ef03-173">Notieren Sie sich den Pfad der heruntergeladenen Datei, da Sie dies später in diesem Artikel benötigen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="4ef03-174">Klicken Sie entweder **auf die Option "Codierte Lizenz"** oder **auf die Option "Nicht codierte Lizenz".**</span><span class="sxs-lookup"><span data-stu-id="4ef03-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="4ef03-175">Verwenden Sie die codierte Lizenzoption mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows-Konfigurations-Designer zum Erstellen eines Bereitstellungspakets verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="4ef03-176">Wählen Sie die Option "Nicht codierte Lizenz" aus, wenn Sie deployment Image Servicing and Management (DISM) oder Bereitstellungslösungen basierend auf der Imageerstellung verwenden, einschließlich des Microsoft Deployment Toolkits (MDT).</span><span class="sxs-lookup"><span data-stu-id="4ef03-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="4ef03-177">Klicken **Sie auf "Generieren",** um die Lizenz für die App zu generieren und herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="4ef03-178">Notieren Sie sich den Pfad der Lizenzdatei, da Sie dies später in diesem Artikel benötigen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="4ef03-179">Wenn Sie eine App für die Offlineverwendung herunterladen, z. B. die Surface-App, sehen Sie möglicherweise einen Abschnitt am unteren Rand der Seite mit der Bezeichnung **"Erforderliche Frameworks".**</span><span class="sxs-lookup"><span data-stu-id="4ef03-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="4ef03-180">Auf den Zielcomputern müssen die Frameworks installiert sein, damit die App ausgeführt werden kann. Daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (x86 oder x64) wiederholen und sie auch als Teil der weiter später in diesem Artikel erläuterten Windows-Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="4ef03-181">Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-App.</span><span class="sxs-lookup"><span data-stu-id="4ef03-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="4ef03-183">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="4ef03-183">Figure 5.</span></span> <span data-ttu-id="4ef03-184">Erforderliche Frameworks für die Surface-App</span><span class="sxs-lookup"><span data-stu-id="4ef03-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="4ef03-185">Die Versionsnummern der Surface-App und die erforderlichen Frameworks ändern sich, wenn die Apps aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="4ef03-186">Suchen Sie nach der neuesten Version der Surface-App und den einzelnen Frameworks im Microsoft Store für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="4ef03-187">Verwenden Sie immer die Surface-App und die empfohlenen Frameworkversionen, wie sie vom Microsoft Store für Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="4ef03-188">Die Verwendung veralteter Frameworks oder der falschen Versionen kann zu Fehlern oder Anwendungsabstürzen führen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="4ef03-189">Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-App herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="4ef03-189">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="4ef03-190">Klicken Sie auf die Schaltfläche **"Herunterladen"** **unter Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="4ef03-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="4ef03-191">Dadurch wird Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe heruntergeladen. Die Datei "Appx" in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="4ef03-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="4ef03-192">Klicken Sie auf die Schaltfläche **"Herunterladen"** **unter Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="4ef03-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="4ef03-193">Dadurch wird die Datei Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx in den angegebenen Ordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="4ef03-194">Nur die 64-Bit-Version (x64) jedes Frameworks ist für Surface-Geräte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4ef03-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="4ef03-195">Surface Geräte sind systemeigene 64-Bit-UEFI-Geräte und nicht kompatibel mit 32-Bit-Versionen (x86) von Windows, die 32-Bit-Frameworks erfordern würden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="4ef03-196">Installieren der Surface-App auf Ihrem Computer mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ef03-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="4ef03-197">Das folgende Verfahren stellt die Surface-App auf Ihrem Computer bereit und stellt sie für alle Benutzerkonten zur Verfügung, die anschließend auf dem Computer erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4ef03-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="4ef03-198">Laden Sie mithilfe des im Abschnitt "Herunterladen der Surface-App aus einem [Microsoft Store für Business-Konto"](#download-surface-app-from-a-microsoft-store-for-business-account) dieses Artikels beschriebenen Verfahrens die Surface-AppxBundle und die Lizenzdatei herunter.</span><span class="sxs-lookup"><span data-stu-id="4ef03-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="4ef03-199">Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.</span><span class="sxs-lookup"><span data-stu-id="4ef03-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="4ef03-200">Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der App.</span><span class="sxs-lookup"><span data-stu-id="4ef03-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="4ef03-201">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="4ef03-201">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="4ef03-202">Wo befindet sich der Ordner, in den Sie die AppxBundle und die Lizenzdatei aus dem Microsoft Store für Unternehmen `<DownloadPath>` heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="4ef03-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="4ef03-203">Wenn Sie beispielsweise die Dateien in "c:\Temp" heruntergeladen haben, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4ef03-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="4ef03-204">Die Surface-App ist jetzt auf dem aktuellen Windows-Computer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ef03-204">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="4ef03-205">Bevor die Surface-App auf dem Computer funktionsfähig ist, auf dem sie bereitgestellt wurde, müssen Sie auch die weiter oben in diesem Artikel beschriebenen Frameworks bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ef03-205">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="4ef03-206">Verwenden Sie zum Bereitstellen dieser Frameworks das folgende Verfahren in der PowerShell-Sitzung mit erhöhten Rechten, die Sie zum Bereitstellen der Surface-App verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="4ef03-206">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="4ef03-207">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="4ef03-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="4ef03-208">Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: </span><span class="sxs-lookup"><span data-stu-id="4ef03-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="4ef03-209">Installieren der Surface-App mit MDT</span><span class="sxs-lookup"><span data-stu-id="4ef03-209">Install Surface app with MDT</span></span>
<span data-ttu-id="4ef03-210">Im folgenden Verfahren wird MDT verwendet, um die Installation der Surface-App zum Zeitpunkt der Bereitstellung zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="4ef03-210">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="4ef03-211">Die App wird automatisch von MDT bereitgestellt, sodass Sie dieses Verfahren mit bereits vorhandenen Images ausführen können.</span><span class="sxs-lookup"><span data-stu-id="4ef03-211">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="4ef03-212">Dies ist der empfohlene Prozess für die Bereitstellung der Surface-App als Teil einer Windows-Bereitstellung auf Surface-Geräten, da dadurch die plattformübergreifende Kompatibilität des Windows-Images nicht reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="4ef03-212">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="4ef03-213">Laden Sie mithilfe des [weiter oben in diesem](#download-surface-app-from-a-microsoft-store-for-business-account)Artikel beschriebenen Verfahrens die Surface-App-App -AppxBundle und die Lizenzdatei herunter.</span><span class="sxs-lookup"><span data-stu-id="4ef03-213">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="4ef03-214">Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**</span><span class="sxs-lookup"><span data-stu-id="4ef03-214">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="4ef03-215">Geben Sie **auf der Seite** "Befehlsdetails" des Assistenten \*\*\*\* für neue Anwendungen das Standardarbeitsverzeichnis und für den Befehl den Dateinamen von "AppxBundle" wie folgt an: \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4ef03-215">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="4ef03-216">Befehl:</span><span class="sxs-lookup"><span data-stu-id="4ef03-216">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="4ef03-217">Arbeitsverzeichnis: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="4ef03-217">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="4ef03-218">Damit die Surface-App auf dem Zielcomputer funktioniert, sind auch die weiter oben in diesem Artikel beschriebenen Frameworks erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4ef03-218">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="4ef03-219">Verwenden Sie das folgende Verfahren, um die für die Surface-App erforderlichen Frameworks in MDT zu importieren und als Abhängigkeiten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4ef03-219">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="4ef03-220">Laden Sie mithilfe des weiter oben in diesem Artikel beschriebenen Verfahrens die Frameworkdateien herunter.</span><span class="sxs-lookup"><span data-stu-id="4ef03-220">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="4ef03-221">Speichern Sie jedes Framework in einem separaten Ordner.</span><span class="sxs-lookup"><span data-stu-id="4ef03-221">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="4ef03-222">Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**</span><span class="sxs-lookup"><span data-stu-id="4ef03-222">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="4ef03-223">Geben Sie **auf der Seite "Befehlsdetails"** im \*\*\*\* Befehlsfeld und im Standardarbeitsverzeichnis den Dateinamen jeder Anwendung ein, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="4ef03-223">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="4ef03-224">Verwenden Sie diesen Prozess, um die Frameworks als Abhängigkeiten der Surface-App zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4ef03-224">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="4ef03-225">Öffnen Sie die Eigenschaften der Surface-App in der MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="4ef03-225">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="4ef03-226">Klicken Sie **auf die** Registerkarte Abhängigkeiten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4ef03-226">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="4ef03-227">Aktivieren Sie das Kontrollkästchen für jedes Framework mit dem Namen, den Sie im Assistenten für neue Anwendungen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4ef03-227">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="4ef03-228">Nach dem Import steht die Surface-App \*\*\*\* zur Auswahl im Schritt "Anwendungen" des Windows-Bereitstellungs-Assistenten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4ef03-228">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="4ef03-229">Sie können die Anwendung auch automatisch installieren, indem Sie sie in der Tasksequenz für die Bereitstellung wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="4ef03-229">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="4ef03-230">Öffnen Sie die Tasksequenz für die Bereitstellung in der Deployment Workbench von MDT.</span><span class="sxs-lookup"><span data-stu-id="4ef03-230">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="4ef03-231">Fügen Sie dem Abschnitt **Status wiederherstellen** der Bereitstellung eine neue Aufgabe **Anwendung installieren** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ef03-231">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="4ef03-232">Wählen **Sie "Einzelne Anwendung installieren"** aus, und geben Sie die **Surface App** als zu **installierende Anwendung an.**</span><span class="sxs-lookup"><span data-stu-id="4ef03-232">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="4ef03-233">Weitere Informationen zum Hinzufügen von Apps in Ihre Windows-Bereitstellungen finden Sie unter Bereitstellen von [Windows 10 mit dem Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="4ef03-233">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
