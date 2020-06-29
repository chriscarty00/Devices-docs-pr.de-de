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
# Microsoft Surface Deployment Accelerator

Microsoft Surface Deployment Accelerator (SDA) automatisiert die Erstellung und Konfiguration einer von Microsoft empfohlenen Bereitstellungsumgebung mithilfe von kostenlosen Microsoft-Bereitstellungstools.

Im April 2020 neu gestaltet, um die Bereitstellung von Surface-Images in einer Unternehmensumgebung zu vereinfachen und zu automatisieren, können Sie mit dem SDA-Tool ein Windows-Abbild erstellen, das Sie an Ihre organisatorischen Anforderungen anpassen können.

Das Open Source-skriptgesteuerte SDA-Tool nutzt das Windows Assessment and Deployment Kit (ADK) für Windows 10, wodurch die Erstellung von Windows-Images (WIM) in Test-oder Produktionsumgebungen vereinfacht wird. Wenn das neueste ADK noch nicht installiert ist, wird es heruntergeladen und installiert, wenn das SDA-Tool ausgeführt wird.

Das resultierende Bild entspricht in engem Zusammenhang mit der Konfiguration von grundlegendem (Bare Metal Recovery)-Bildern ohne vorinstallierte Anwendungen wie Microsoft Office oder die Surface UWP-Anwendung.

**So führen Sie SDA aus:**

1. Wechseln Sie zu [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) auf GitHub. 
2. Wählen Sie **Klonen oder herunterladen** aus, und überprüfen Sie die Readme-Datei.
3. Bearbeiten Sie das Skript mit den entsprechenden Variablen für Ihre Umgebung, wie in der Readme-Datei dokumentiert, und überprüfen Sie Sie, bevor Sie Sie in Ihrer Testumgebung ausführen. 

   ![Tool zum Ausführen des Surface-Bereitstellungs Beschleunigers](images/surface-deployment-accelerator.png)

## Verwandte Links

 - [Open-Source-Image-Bereitstellungstool auf GitHub veröffentlicht](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Herunterladen und Installieren des Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
