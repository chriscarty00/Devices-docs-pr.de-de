---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator bietet einen schnellen und einfachen Bereitstellungsmechanismus für Organisationen, die ein Reimaging von Surface-Geräten durchführen möchten.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: bereitstellen, installieren, Tool
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832311"
---
# <span data-ttu-id="6b15c-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="6b15c-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="6b15c-105">Microsoft Surface Deployment Accelerator (SDA) automatisiert die Erstellung und Konfiguration einer von Microsoft empfohlenen Bereitstellungsumgebung mithilfe von kostenlosen Microsoft-Bereitstellungstools.</span><span class="sxs-lookup"><span data-stu-id="6b15c-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="6b15c-106">Im April 2020 neu gestaltet, um die Bereitstellung von Surface-Images in einer Unternehmensumgebung zu vereinfachen und zu automatisieren, können Sie mit dem SDA-Tool ein Windows-Abbild erstellen, das Sie an Ihre organisatorischen Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="6b15c-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="6b15c-107">Das Open Source-skriptgesteuerte SDA-Tool nutzt das Windows Assessment and Deployment Kit (ADK) für Windows 10, wodurch die Erstellung von Windows-Images (WIM) in Test-oder Produktionsumgebungen vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="6b15c-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="6b15c-108">Wenn das neueste ADK noch nicht installiert ist, wird es heruntergeladen und installiert, wenn das SDA-Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6b15c-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="6b15c-109">Das resultierende Bild entspricht in engem Zusammenhang mit der Konfiguration von grundlegendem (Bare Metal Recovery)-Bildern ohne vorinstallierte Anwendungen wie Microsoft Office oder die Surface UWP-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6b15c-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="6b15c-110">So führen Sie SDA aus:</span><span class="sxs-lookup"><span data-stu-id="6b15c-110">To run SDA:</span></span>**

1. <span data-ttu-id="6b15c-111">Wechseln Sie zu [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="6b15c-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="6b15c-112">Wählen Sie **Klonen oder herunterladen** aus, und überprüfen Sie die Readme-Datei.</span><span class="sxs-lookup"><span data-stu-id="6b15c-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="6b15c-113">Bearbeiten Sie das Skript mit den entsprechenden Variablen für Ihre Umgebung, wie in der Readme-Datei dokumentiert, und überprüfen Sie Sie, bevor Sie Sie in Ihrer Testumgebung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b15c-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![Tool zum Ausführen des Surface-Bereitstellungs Beschleunigers](images/surface-deployment-accelerator.png)

## <span data-ttu-id="6b15c-115">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="6b15c-115">Related links</span></span>

 - [<span data-ttu-id="6b15c-116">Open-Source-Image-Bereitstellungstool auf GitHub veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="6b15c-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="6b15c-117">Herunterladen und Installieren des Windows ADK</span><span class="sxs-lookup"><span data-stu-id="6b15c-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
