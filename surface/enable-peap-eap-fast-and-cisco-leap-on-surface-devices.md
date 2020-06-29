---
title: Aktivieren von PEAP, EAP-FAST und Cisco LEAP auf Surface-Geräten (Surface)
description: Erfahren Sie, wie Sie Unterstützung für PEAP-, EAP-FAST- oder Cisco LEAP-Protokolle auf Ihrem Surface-Gerät bereitstellen.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: Netzwerk, drahtlos, Gerät, bereitstellen, Authentifizierung, Protokoll
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833496"
---
# <span data-ttu-id="71c50-104">Aktivieren von PEAP, EAP-FAST und Cisco LEAP auf Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="71c50-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="71c50-105">Erfahren Sie, wie Sie Unterstützung für PEAP-, EAP-FAST- oder Cisco LEAP-Protokolle auf Ihrem Surface-Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71c50-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="71c50-106">Wenn Sie in Ihrem Unternehmensnetzwerk PEAP, EAP-FAST oder Cisco LEAP verwenden, wissen Sie wahrscheinlich bereits, dass diese drei Drahtlosauthentifizierungsprotokolle von Surface-Geräten nicht ohne weitere Konfiguration unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="71c50-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="71c50-107">Benutzer stellen dies möglicherweise fest, wenn sie versuchen, eine Verbindung mit Ihrem Drahtlosnetzwerk herzustellen, oder wenn sie nicht auf Ressourcen innerhalb des Netzwerks zugreifen können, wie z.B. Dateifreigaben und interne Websites.</span><span class="sxs-lookup"><span data-stu-id="71c50-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="71c50-108">Weitere Informationen finden Sie unter [Extensible Authentication-Protokoll](https://technet.microsoft.com/network/bb643147).</span><span class="sxs-lookup"><span data-stu-id="71c50-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="71c50-109">Sie können Unterstützung für diese Protokolle bereitstellen, indem Sie ein kleines MSI-Paket von einem USB-Stick oder von einer Dateifreigabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="71c50-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="71c50-110">Für Organisationen, die EAP-Unterstützung auf Ihren Surface-Geräten aktivieren möchten, unterstützt das MSI-Paketformat die Bereitstellung mit zahlreichen Verwaltungs-und Bereitstellungstools wie dem Microsoft Deployment Toolkit (MDT) und dem Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="71c50-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="71c50-111">PEAP-, EAP-FAST- oder Cisco-LEAP-Installationsdateien herunterladen</span><span class="sxs-lookup"><span data-stu-id="71c50-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="71c50-112">Sie können die MSI-Installationsdateien für PEAP, EAP-FAST oder Cisco LEAP in einer einzelnen ZIP-Archivdatei aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="71c50-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="71c50-113">Um diese Datei herunterzuladen, besuchen Sie die Seite [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) (Surface-Tools für IT-Experten) im Microsoft Download Center, klicken Sie auf **Download**, und wählen Sie dann die Datei **Cisco EAP-Supplicant Installer.zip** aus.</span><span class="sxs-lookup"><span data-stu-id="71c50-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="71c50-114">Bereitstellen von PEAP, EAP-FAST oder Cisco LEAP mit MDT</span><span class="sxs-lookup"><span data-stu-id="71c50-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="71c50-115">Wenn Sie in Ihrer Organisation bereits Windows auf Surface-Geräten bereitstellen, können Sie die Installationsdateien für die Protokolle einfach zur Bereitstellungsfreigabe hinzufügen und während der Bereitstellung die automatische Installation konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71c50-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="71c50-116">Sie können sogar eine Tasksequenz konfigurieren, die zuvor bereitgestellte Surface-Geräte aktualisiert, damit für diese Protokolle auf die gleiche Weise Unterstützung bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="71c50-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="71c50-117">Führen Sie die folgenden Schritte aus, um Unterstützung für PEAP, EAP-FAST oder Cisco LEAP auf neu bereitgestellten Surface-Geräten zu bieten:</span><span class="sxs-lookup"><span data-stu-id="71c50-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="71c50-118">Wenn Sie die Installationsdateien für die Protokolle heruntergeladen haben, extrahieren Sie sie in getrennten Ordnern an einem leicht zugänglichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="71c50-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="71c50-119">Öffnen Sie die Deployment Workbench von MDT, und erweitern Sie die Bereitstellungsfreigabe für den Ordner **Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="71c50-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="71c50-120">Wählen Sie im Bereich **Aktion** die Option **Neue Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="71c50-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="71c50-121">Wählen Sie die Option **Anwendung mit Quelldateien** aus, um die MSI-Dateien in die Bereitstellungsfreigabe zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="71c50-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="71c50-122">Wählen Sie den Ordner aus, den Sie in Schritt1 für das gewünschte Protokoll erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="71c50-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="71c50-123">Benennen Sie den Ordner in der Bereitstellungsfreigabe, in dem die Installationsdateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="71c50-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="71c50-124">Geben Sie die Befehlszeile an, um die Anwendung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="71c50-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="71c50-125">Für PEAP: **EAP-PEAP.msi/qn/norestart**.</span><span class="sxs-lookup"><span data-stu-id="71c50-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="71c50-126">Für LEAP: **EAP-LEAP.msi/qn/norestart**.</span><span class="sxs-lookup"><span data-stu-id="71c50-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="71c50-127">Für EAP-FAST: **EAP-FAST.msi/qn/norestart**.</span><span class="sxs-lookup"><span data-stu-id="71c50-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="71c50-128">Verwenden Sie die Standardoptionen, um den Assistenten für neue Anwendungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="71c50-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="71c50-129">Wiederholen Sie die Schritte 3 bis 8 für jedes gewünschte Protokoll.</span><span class="sxs-lookup"><span data-stu-id="71c50-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="71c50-130">Nachdem Sie diese Schritte ausgeführt und die drei MSI-Pakete als Anwendungen in MDT importiert haben, können sie auf der Anwendungsseite des Windows-Bereitstellungs-Assistenten ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="71c50-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="71c50-131">Obwohl es in einfachen Bereitstellungsszenarien u.U. möglich ist, dass Techniker jedes Paket zum Zeitpunkt der Bereitstellung auswählen, ist dies nicht zu empfehlen.</span><span class="sxs-lookup"><span data-stu-id="71c50-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="71c50-132">Da man menschliches Versagen nicht ausschließen kann, besteht die Möglichkeit, dass ein Techniker diese Pakete auf anderen Computern als Surface-Geräten anwendet oder ein Surface-Gerät ohne EAP-Unterstützung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="71c50-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="71c50-133">Wenn Sie diese Anwendungen auf der Seite zum Installieren von Anwendungen ausblenden möchten, aktivieren Sie das Kontrollkästchen \*\*Hide this application in the Deployment Wizard \*\*in den Eigenschaften der einzelnen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="71c50-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="71c50-134">Nachdem die Anwendungen ausgeblendet wurden, werden sie während der Bereitstellung nicht als optionale Anwendungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71c50-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="71c50-135">Um sie in der Tasksequenz für die Bereitstellung eines Surface-Geräts installieren zu können, müssen sie über einen separaten Schritt explizit für die Installation in der Tasksequenz definiert werden.</span><span class="sxs-lookup"><span data-stu-id="71c50-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="71c50-136">Wenn Sie die Protokolle explizit angeben möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="71c50-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="71c50-137">Öffnen Sie über die MDT Deployment Workbench die Eigenschaften der Tasksequenz für die Bereitstellung des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="71c50-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="71c50-138">Wählen Sie auf der Registerkarte **Tasksequenz** unter **Status wiederherstellen** den Schritt **Anwendungen installieren**.</span><span class="sxs-lookup"><span data-stu-id="71c50-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="71c50-139">Dieser Abschnitt befindet sich in der Regel zwischen den Schritten für Windows Update (Pre-Application) und Windows Update (Post-Application).</span><span class="sxs-lookup"><span data-stu-id="71c50-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="71c50-140">Verwenden Sie die Schaltfläche **Hinzufügen**, um einen neuen Schritt **Anwendung installieren** in der Kategorie **Allgemein** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71c50-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="71c50-141">Wählen Sie auf der Registerkarte **Eigenschaften** die Option **Eine einzelne Anwendung installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="71c50-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="71c50-142">Wählen Sie das gewünschte EAP-Protokoll aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="71c50-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="71c50-143">Wiederholen Sie die Schritte 2 bis 5 für jedes gewünschte Protokoll.</span><span class="sxs-lookup"><span data-stu-id="71c50-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="71c50-144">Bereitstellen von PEAP, EAP-FAST oder Cisco LEAP mit Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71c50-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="71c50-145">Für Unternehmen, die Surface-Geräte mit Configuration Manager verwalten, ist es noch einfacher, Unterstützung für PEAP, EAP-FAST oder Cisco LEAP auf Surface-Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="71c50-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="71c50-146">Importieren Sie lediglich jede MSI-Datei als Anwendung aus der Softwarebibliothek, und konfigurieren Sie die Bereitstellung auf Ihren Surface-Geräten.</span><span class="sxs-lookup"><span data-stu-id="71c50-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="71c50-147">Weitere Informationen zum Bereitstellen von Anwendungen mit Configuration Manager finden Sie unter [Erstellen von Anwendungen in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) und [Bereitstellen von Anwendungen in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span><span class="sxs-lookup"><span data-stu-id="71c50-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 





