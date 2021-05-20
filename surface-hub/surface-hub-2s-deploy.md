---
title: Erstellen von Bereitstellungspaketen für Surface Hub 2S
description: Auf dieser Seite wird beschrieben, wie Surface Hub 2S mithilfe von Bereitstellungspaketen und anderen Tools bereitgestellt wird.
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576865"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="2b6f3-104">Erstellen von Bereitstellungspaketen für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="2b6f3-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="2b6f3-105">Sie können Windows Configuration Designer (WCD) verwenden, um Bereitstellungspakete zum Automatisieren der Bereitstellung von Surface Hub 2S zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="2b6f3-106">Verwenden Sie Bereitstellungspakete, um Zertifikate hinzuzufügen, Proxys zu konfigurieren, Geräteadministratoren und Gerätekonten einrichten.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="2b6f3-107">Sie können auch Bereitstellungspakete zusammen mit einer Konfigurationsdatei verwenden, um mehrere Surface Hubs mit einem einzigen USB-Stick zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="2b6f3-108">Installieren von Windows-Konfigurations-Designer</span><span class="sxs-lookup"><span data-stu-id="2b6f3-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="2b6f3-109">Installieren Windows Configuration Designer aus dem Windows Assessment and Deployment Kit (ADK) für Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="2b6f3-110">Laden Sie [adK für Windows 10, Version 1703, herunter, und installieren Sie es.](https://go.microsoft.com/fwlink/p/?LinkId=845542)</span><span class="sxs-lookup"><span data-stu-id="2b6f3-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="2b6f3-111">Weitere Informationen finden Sie unter [Herunterladen und Installieren von Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="2b6f3-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="2b6f3-112">Hinzufügen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2b6f3-112">Add certificates</span></span>

<span data-ttu-id="2b6f3-113">Sie können Zertifikate der Zertifizierungsstelle in Surface Hub 2S importieren.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="2b6f3-114">Zum Hinzufügen von Zertifikaten zu Surface Hub 2S benötigen Sie eine Kopie jedes Zertifikats als X.509 im CER-Format.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="2b6f3-115">Sie können keine .crt-, PFX- oder andere Containerformate importieren.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="2b6f3-116">Zertifikate müssen in den Windows importiert und nach Hierarchie angeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="2b6f3-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![Hinzufügen von Zertifikaten](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="2b6f3-118">Konfigurieren des Proxys während der OOBE</span><span class="sxs-lookup"><span data-stu-id="2b6f3-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="2b6f3-119">Wechseln Windows Konfigurations-Designer zur Registerkarte Proxyeinstellungen konfigurieren, und geben Sie die entsprechenden Einstellungen wie unten gezeigt ein.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![Proxyeinstellungen konfigurieren](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="2b6f3-121">Wenn Sie Proxyeinstellungen konfigurieren, deaktivieren Sie Einstellungen automatisch **erkennen,** wenn Sie ein Setupskript oder einen Proxyserver verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="2b6f3-122">Sie können ein Setupskript *oder einen* Proxyserver verwenden, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="2b6f3-123">Partner Surface Hub 2S mit Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2b6f3-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="2b6f3-124">Sie können Surface Hub 2S mit Azure Active Directory mithilfe eines Bereitstellungspakets verbinden: Als globaler Azure Active Directory-Administrator können Sie eine große Anzahl neuer Windows-Geräte mit Azure Active Directory und Intune mithilfe eines Massentokens verbinden.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="2b6f3-125">Um ein Massentoken zu erstellen, geben Sie ihm einen Anzeigenamen, konfigurieren Sie das Ablaufdatum (maximal 30 Tage) und verwenden Sie Ihre Administratoranmeldeinformationen, um das Token wie unten gezeigt zu erwerben:</span><span class="sxs-lookup"><span data-stu-id="2b6f3-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![Einrichten von Geräteadministratoren (Beispiel 1)](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Einrichten von Geräteadministratoren (Beispiel 2)](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Einrichten von Geräteadministratoren (Beispiel 3)](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="2b6f3-129">Bereitstellen mehrerer Geräte (.csv Datei)</span><span class="sxs-lookup"><span data-stu-id="2b6f3-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="2b6f3-130">Zusätzlich zum Bereitstellungspaket können Sie eine Surface Hub konfigurationsdatei verwenden, um das Einrichten Ihrer Geräte noch einfacher zu machen.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="2b6f3-131">Eine Surface Hub enthält eine Liste der Gerätekonten und Anzeigenamen für die drahtlose Projektion.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="2b6f3-132">Während der ersten Ausführung erhalten Sie eine Option zum Auswählen eines Gerätekontos und eines Anzeigenamens aus einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="2b6f3-133">So erstellen Sie Surface Hub Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2b6f3-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="2b6f3-134">Erstellen Microsoft Excel oder einem anderen CSV-Editor eine CSV-Datei mit dem Namen: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="2b6f3-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="2b6f3-135">Geben Sie eine Liste der Gerätekonten und Anzeigenamen in diesem Format ein:</span><span class="sxs-lookup"><span data-stu-id="2b6f3-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="2b6f3-136">Speichern Sie die Datei im Stammverzeichnis des USB-Sticks, auf dem Sie die PPKG-Datei kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="2b6f3-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Beispiel für Konfigurationsdatei](images/sh2-config-file.png)
