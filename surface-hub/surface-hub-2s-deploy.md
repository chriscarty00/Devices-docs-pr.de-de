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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834187"
---
# <span data-ttu-id="571a4-104">Erstellen von Bereitstellungspaketen für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="571a4-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="571a4-105">Sie können den Windows-Konfigurations-Designer (WCD) verwenden, um Bereitstellungspakete zu erstellen, um den Bereitstellungsprozess von Surface Hub 2S zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="571a4-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="571a4-106">Verwenden Sie Bereitstellungspakete, um Zertifikate hinzuzufügen, Proxys zu konfigurieren, geräteadministratoren und Geräte Konten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="571a4-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="571a4-107">Sie können auch Bereitstellungspakete zusammen mit einer Konfigurationsdatei verwenden, um mehrere Surface-Hubs mit einem einzigen USB-Daumen Laufwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="571a4-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="571a4-108">Installieren von Windows-Konfigurations-Designer</span><span class="sxs-lookup"><span data-stu-id="571a4-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="571a4-109">Installieren Sie den Windows-Konfigurations-Designer aus dem Windows Assessment and Deployment Kit (ADK) für Windows 10.</span><span class="sxs-lookup"><span data-stu-id="571a4-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="571a4-110">Laden Sie das [ADK für Windows 10, Version 1703, herunter,](https://go.microsoft.com/fwlink/p/?LinkId=845542)und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="571a4-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="571a4-111">Weitere Informationen finden Sie unter [herunterladen und Installieren des Windows-ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="571a4-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="571a4-112">Hinzufügen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="571a4-112">Add certificates</span></span>

<span data-ttu-id="571a4-113">Sie können Zertifikat Zertifizierungsstellenzertifikate in Surface Hub 2S importieren.</span><span class="sxs-lookup"><span data-stu-id="571a4-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="571a4-114">Wenn Sie dem Surface Hub 2S Zertifikate hinzufügen möchten, benötigen Sie eine Kopie der einzelnen Zertifikate als X. 509 im CER-Format.</span><span class="sxs-lookup"><span data-stu-id="571a4-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="571a4-115">Sie können CRT-, PFX-oder andere Containerformate nicht importieren.</span><span class="sxs-lookup"><span data-stu-id="571a4-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="571a4-116">Zertifikate müssen in den Windows-Konfigurations-Designer importiert und nach Hierarchie geordnet werden:</span><span class="sxs-lookup"><span data-stu-id="571a4-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![Hinzufügen von Zertifikaten](images/sh2-wcd.png)

### <span data-ttu-id="571a4-118">Konfigurieren des Proxys während OOBE</span><span class="sxs-lookup"><span data-stu-id="571a4-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="571a4-119">Wechseln Sie im Windows-Konfigurations-Designer zur Registerkarte Proxyeinstellungen konfigurieren, und geben Sie die entsprechenden Einstellungen wie unten dargestellt ein.</span><span class="sxs-lookup"><span data-stu-id="571a4-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![Proxyeinstellungen konfigurieren](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="571a4-121">Wenn Sie Proxyeinstellungen konfigurieren, deaktivieren Sie die Option zum **automatischen Erkennen von Einstellungen** , wenn Sie beabsichtigen, ein Setupskript oder einen Proxy Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="571a4-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="571a4-122">Sie können ein Setupskript *oder* einen Proxy Server verwenden, nicht beide.</span><span class="sxs-lookup"><span data-stu-id="571a4-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="571a4-123">Affiliate Surface Hub 2S mit Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="571a4-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="571a4-124">Sie können Surface Hub 2S mit Azure Active Directory mit einem Bereitstellungspaket verknüpfen: als globaler Azure Active Directory-Administrator können Sie mit einem Massen Token eine große Anzahl von neuen Windows-Geräten an Azure Active Directory und InTune teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="571a4-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="571a4-125">Wenn Sie ein Massen Token erstellen möchten, geben Sie ihm einen Anzeigenamen, konfigurieren Sie das Ablaufdatum (maximal 30 Tage), und verwenden Sie Ihre Administratoranmeldeinformationen zum Abrufen des Tokens, wie unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="571a4-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![Einrichten von geräteadministratoren](images/sh2-token.png) <br><br>
 ![Einrichten von geräteadministratoren](images/sh2-token2.png) <br><br>
 ![Einrichten von geräteadministratoren](images/sh2-token3.png) <br><br>

### <span data-ttu-id="571a4-129">Bereitstellen mehrerer Geräte (CSV-Datei)</span><span class="sxs-lookup"><span data-stu-id="571a4-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="571a4-130">Zusätzlich zum Bereitstellungspaket können Sie eine Surface Hub-Konfigurationsdatei verwenden, um die Einrichtung Ihrer Geräte noch einfacher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="571a4-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="571a4-131">Eine Surface Hub-Konfigurationsdatei enthält eine Liste der Geräte Konten und Anzeigenamen für die drahtlose Projektion.</span><span class="sxs-lookup"><span data-stu-id="571a4-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="571a4-132">Während der ersten Ausführung erhalten Sie eine Option, mit der Sie ein Geräte Konto und einen Anzeigenamen aus einer Konfigurationsdatei auswählen können.</span><span class="sxs-lookup"><span data-stu-id="571a4-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="571a4-133">So erstellen Sie eine Surface Hub-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="571a4-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="571a4-134">Erstellen Sie mithilfe von Microsoft Excel oder einem anderen CSV-Editor eine CSV-Datei mit dem Namen: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="571a4-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="571a4-135">Geben Sie eine Liste der Geräte Konten und Anzeige Namen in diesem Format ein:</span><span class="sxs-lookup"><span data-stu-id="571a4-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="571a4-136">Speichern Sie die Datei im Stammverzeichnis des USB-Thumb-Laufwerks, auf dem Sie die PPKG-Datei kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="571a4-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![Beispiel für eine Konfigurationsdatei](images/sh2-config-file.png)
