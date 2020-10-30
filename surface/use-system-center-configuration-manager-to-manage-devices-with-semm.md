---
title: Verwenden von Microsoft Endpoint Configuration Manager zum Verwalten von Geräten mit Semm (Surface)
description: Erfahren Sie, wie Sie den Microsoft Surface Enterprise Management Mode (Semm) mit Endpoint Configuration Manager verwalten.
keywords: registrieren, aktualisieren, Skripts, Einstellungen
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 2d31f520d8c4da54f47b2b89b58b43e2cb983f1a
ms.sourcegitcommit: 7f5b97275fe301ef700f9c77954a1054e2e8d046
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145616"
---
# <span data-ttu-id="0c1ec-104">Verwenden von Microsoft-Endpunkt-Konfigurations-Manager zum Verwalten von Geräten mit SEMM</span><span class="sxs-lookup"><span data-stu-id="0c1ec-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="0c1ec-105">Mit dem Microsoft Surface Enterprise Management Mode (Semm)-Feature von Surface UEFI-Geräten können Administratoren die Konfiguration von Surface UEFI-Einstellungen verwalten und schützen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="0c1ec-106">Für die meisten Organisationen wird dieser Vorgang durch Erstellen von Windows Installer-Paketen (MSI) mit dem Microsoft Surface UEFI Configurator-Tool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="0c1ec-107">Diese Pakete werden dann auf den Client Oberflächen Geräten ausgeführt oder bereitgestellt, um die Geräte in Semm zu registrieren und die Konfiguration der Oberflächen UEFI-Einstellungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="0c1ec-108">Für Organisationen mit Microsoft Endpoint Configuration Manager gibt es eine Alternative zur Verwendung des Microsoft Surface UEFI Configurator. msi-Prozesses zum Bereitstellen und Verwalten von Semm.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="0c1ec-109">Microsoft Surface UEFI Manager ist ein einfaches Installationsprogramm, mit dem erforderliche Assemblys für die Semm-Verwaltung auf einem Gerät verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="0c1ec-110">Durch Installieren dieser Assemblys mit Microsoft Surface UEFI Manager auf einem verwalteten Client kann Semm vom Configuration Manager mit PowerShell-Skripts verwaltet werden, die als Anwendungen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="0c1ec-111">Bei diesem Verfahren wird die Semm-Verwaltung innerhalb von Configuration Manager durchgeführt, wodurch die Notwendigkeit des externen Microsoft Surface UEFI Configurator-Tools beseitigt wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="0c1ec-112">Obwohl der in diesem Artikel beschriebene Prozess möglicherweise mit früheren Versionen von Endpoint Configuration Manager oder mit anderen Verwaltungslösungen von Drittanbietern funktioniert, wird die Verwaltung von Semm mit Microsoft Surface UEFI Manager und PowerShell nur mit der aktuellen Verzweigung des Endpunkt Konfigurations-Managers unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <span data-ttu-id="0c1ec-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0c1ec-113">Prerequisites</span></span>

<span data-ttu-id="0c1ec-114">Bevor Sie mit dem in diesem Artikel beschriebenen Verfahren beginnen, sollten Sie sich mit den folgenden Technologien und Tools vertraut machen:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="0c1ec-115">DGM-UEFI</span><span class="sxs-lookup"><span data-stu-id="0c1ec-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="0c1ec-116">Surface Enterprise Management Mode (SEMM)</span><span class="sxs-lookup"><span data-stu-id="0c1ec-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="0c1ec-117">PowerShell-Skripting</span><span class="sxs-lookup"><span data-stu-id="0c1ec-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="0c1ec-118">System Center Configuration Manager-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="0c1ec-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="0c1ec-119">Zertifikatverwaltung</span><span class="sxs-lookup"><span data-stu-id="0c1ec-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="0c1ec-120">Außerdem benötigen Sie Zugriff auf das Zertifikat, das Sie zum Sichern von Semm verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="0c1ec-121">Details zu den Anforderungen für dieses Zertifikat finden Sie unter [Anforderungen für das Surface Enterprise Management Mode-Zertifikat](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="0c1ec-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="0c1ec-122">Es ist sehr wichtig, dass dieses Zertifikat an einem sicheren Ort aufbewahrt und ordnungsgemäß gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="0c1ec-123">Wenn dieses Zertifikat verloren geht oder nicht verwendet werden kann, ist es nicht möglich, die UEFI-Oberfläche zurückzusetzen, die UEFI-Einstellungen für verwaltete Oberflächen zu ändern oder Semm aus einem eingeschriebenen Surface-Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="0c1ec-124">Herunterladen des Microsoft Surface UEFI-Managers</span><span class="sxs-lookup"><span data-stu-id="0c1ec-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="0c1ec-125">Die Verwaltung von Semm mit Configuration Manager setzt die Installation von Microsoft Surface UEFI Manager auf jedem Client Oberflächengerät voraus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="0c1ec-126">Sie können den Microsoft Surface UEFI-Manager (SurfaceUEFIManager.msi) über die Seite [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="0c1ec-127">Herunterladen von Semm-Skripts für Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0c1ec-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="0c1ec-128">Nachdem Microsoft Surface UEFI Manager auf dem Client Oberflächengerät installiert wurde, wird Semm mit PowerShell-Skripts bereitgestellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="0c1ec-129">Sie können Beispiele der Semm- [Verwaltungsskripts](https://www.microsoft.com/download/details.aspx?id=46703) aus dem Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <span data-ttu-id="0c1ec-130">Bereitstellen des Microsoft Surface UEFI-Managers</span><span class="sxs-lookup"><span data-stu-id="0c1ec-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="0c1ec-131">Die Bereitstellung des Microsoft Surface UEFI-Managers ist eine typische Anwendungsbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="0c1ec-132">Die Microsoft Surface UEFI Manager-Installationsdatei ist eine standardmäßige Windows Installer-Datei, die Sie mit der [standardmäßigen Option quiet](https://msdn.microsoft.com/library/windows/desktop/aa367988)installieren können.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="0c1ec-133">Der Befehl zum Installieren des Microsoft Surface UEFI-Managers lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="0c1ec-134">Der Befehl zum Deinstallieren des Microsoft Surface UEFI-Managers lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="0c1ec-135">Führen Sie die folgenden Schritte aus, um eine neue Anwendung zu erstellen und diese in einer Sammlung bereitzustellen, die ihre Surface-Geräte enthält:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="0c1ec-136">Öffnen Sie die Configuration Manager-Konsole auf dem **Start** Bildschirm oder im **Startmenü** .</span><span class="sxs-lookup"><span data-stu-id="0c1ec-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="0c1ec-137">Wählen Sie in der unteren linken Ecke des Fensters **Software Bibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="0c1ec-138">Erweitern Sie den Knoten **Anwendungsverwaltung** der Software Bibliothek, und wählen Sie dann **Anwendungen**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="0c1ec-139">Wählen Sie die Schaltfläche " **Anwendung erstellen** " unter der Registerkarte " **Start** " oben im Fenster aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="0c1ec-140">Damit wird der Assistent zum Erstellen von Anwendungen gestartet.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="0c1ec-141">Der Assistent zum Erstellen von Anwendungen enthält eine Reihe von Schritten:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="0c1ec-142">**Allgemein** – standardmäßig ist die Option **Informationen über diese Anwendung aus Installationsdateien automatisch erkennen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="0c1ec-143">Im Feld **Typ** ist **Windows Installer (MSI-Datei)** ebenfalls standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="0c1ec-144">Wählen Sie **Durchsuchen** aus, um zu navigieren, und wählen Sie **SurfaceUEFIManagerSetup.msi**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="0c1ec-145">Der Speicherort von SurfaceUEFIManagerSetup.msi muss sich auf einer Netzwerkfreigabe befinden und sich in einem Ordner befinden, der keine anderen Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="0c1ec-146">Ein lokaler Dateispeicherort kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="0c1ec-147">**Importieren von Informationen** – der Assistent zum Erstellen von Anwendungen analysiert die MSI-Datei und liest den **Anwendungsnamen** und den **Produkt Code**.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="0c1ec-148">SurfaceUEFIManagerSetup.msi sollten als einzige Datei unter den Linien **Inhaltsdateien**aufgeführt werden, wie in Abbildung 1 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="0c1ec-149">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-149">Select **Next** to proceed.</span></span>

      ![Informationen aus dem Surface UEFI Manager-Setup werden automatisch analysiert](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="0c1ec-151">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-151">Figure 1.</span></span> <span data-ttu-id="0c1ec-152">Informationen aus dem Microsoft Surface UEFI Manager-Setup werden automatisch analysiert</span><span class="sxs-lookup"><span data-stu-id="0c1ec-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="0c1ec-153">**Allgemeine Informationen** : Sie können den Namen der Anwendung sowie Informationen zu Publisher und Version ändern oder Kommentare auf dieser Seite hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="0c1ec-154">Der Installationsbefehl für Microsoft Surface UEFI Manager wird im Feld Installationsprogramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="0c1ec-155">Das Standard Installationsverhalten von installieren für System ermöglicht es dem Microsoft Surface UEFI-Manager, die erforderlichen Assemblys für Semm zu installieren, auch wenn ein Benutzer nicht am Surface-Gerät angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="0c1ec-156">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="0c1ec-157">**Zusammenfassung** – die Informationen, die im Schritt " **Import Informationen** " analysiert wurden, und Ihre Auswahl aus dem Schritt " **Allgemeine Informationen** " werden auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="0c1ec-158">Wählen Sie **weiter** aus, um Ihre Auswahl zu bestätigen und die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="0c1ec-159">**Status – zeigt** eine Statusleiste und den Status an, während die Anwendung importiert und der Software Bibliothek hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="0c1ec-160">**Fertigstellung** – die Bestätigung der erfolgreichen Anwendungserstellung wird angezeigt, wenn der Anwendungs Erstellungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="0c1ec-161">Wählen Sie **Schließen** aus, um den Assistenten zum Erstellen von Anwendungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="0c1ec-162">Nachdem die Anwendung in Configuration Manager erstellt wurde, können Sie Sie an Ihre Verteilungspunkte verteilen und Sie auf die Sammlungen einschließlich ihrer Surface-Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="0c1ec-163">Diese Anwendung kann Semm auf dem Surface-Gerät nicht installieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="0c1ec-164">Es werden nur die Assemblys bereitgestellt, die für die Aktivierung von Semm mit dem PowerShell-Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="0c1ec-165">Wenn Sie die Microsoft Surface UEFI Manager-Assemblys nicht auf Geräten installieren möchten, die nicht mit Semm verwaltet werden, können Sie den Microsoft Surface UEFI Manager als eine Abhängigkeit der Semm-Konfigurations-Manager-Skripts konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="0c1ec-166">Dieses Szenario wird im Abschnitt [Deploy Semm Configuration Manager-Skripts](#deploy-semm-configuration-manager-scripts) weiter unten in diesem Artikel behandelt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <span data-ttu-id="0c1ec-167">Erstellen oder Ändern der Semm-Konfigurations-Manager-Skripts</span><span class="sxs-lookup"><span data-stu-id="0c1ec-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="0c1ec-168">Nachdem die erforderlichen Assemblys auf den Geräten installiert wurden, erfolgt der Registriervorgang für die Geräte in Semm und das Konfigurieren des Oberflächen UEFI mit PowerShell-Skripts, die als Skriptanwendung mit Configuration Manager bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="0c1ec-169">Diese Skripts können an die Anforderungen Ihrer Organisation und Umgebung angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="0c1ec-170">So können Sie beispielsweise mehrere Konfigurationen für verwaltete Surface-Geräte in verschiedenen Abteilungen oder Rollen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="0c1ec-171">Sie können Beispiele der Skripts für Semm und Configuration Manager über den Link im Abschnitt [Voraussetzungen](#prerequisites) am Anfang dieses Artikels herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="0c1ec-172">Es gibt zwei primäre Skripts, die Sie benötigen, um eine Semm-Bereitstellung mit Configuration Manager durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="0c1ec-173">**ConfigureSEMM.ps1** – mit diesem Skript können Sie Konfigurationspakete für Ihre Surface-Geräte mit den gewünschten Oberflächen UEFI-Einstellungen erstellen, um die angegebenen Einstellungen auf ein Surface-Gerät anzuwenden, um das Gerät in Semm zu registrieren und einen Registrierungsschlüssel festzulegen, der zur Identifizierung der Registrierung des Geräts in Semm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="0c1ec-174">**ResetSEMM.ps1** – verwenden Sie dieses Skript zum Zurücksetzen von Semm auf einem Surface-Gerät, das die Registrierung von Semm aufhebt und das Steuerelement über die UEFI-Oberflächeneinstellungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="0c1ec-175">Die Beispielskripts umfassen Beispiele für das Festlegen von UEFI-Einstellungen für die Oberfläche und das Steuern von Berechtigungen für diese Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="0c1ec-176">Diese Einstellungen können geändert werden, um die UEFI-Oberfläche zu sichern und die UEFI-Einstellungen entsprechend den Anforderungen Ihrer Umgebung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="0c1ec-177">In den folgenden Abschnitten dieses Artikels wird das ConfigureSEMM.ps1-Skript erläutert, und es werden die Änderungen erläutert, die Sie an dem Skript vornehmen müssen, damit Sie Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="0c1ec-178">Die Semm-Konfigurations-Manager-Skripts und die exportierte Semm-Zertifikatsdatei (. pfx) sollten sich im gleichen Ordner wie keine anderen Dateien befinden, bevor Sie dem Configuration Manager hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <span data-ttu-id="0c1ec-179">Angeben von Zertifikats-und Paketnamen</span><span class="sxs-lookup"><span data-stu-id="0c1ec-179">Specify certificate and package names</span></span>

<span data-ttu-id="0c1ec-180">Der erste Bereich des Skripts, den Sie ändern müssen, ist der Teil, der das Semm-Zertifikat angibt und lädt, und auch die SurfaceUEFIManager-Version sowie die Namen für das Semm-Konfigurationspaket und das Semm-Zurücksetzungs Paket.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="0c1ec-181">Der Zertifikatname und die SurfaceUEFIManager-Version werden in Zeilen 56 bis 73 im ConfigureSEMM.ps1-Skript angegeben.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="0c1ec-182">Ersetzen Sie den Wert **FabrikamSEMMSample. pfx** für die **$certName** -Variable durch den Namen Ihrer Semm-Zertifikatsdatei in Zeile 58.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="0c1ec-183">Das Skript erstellt ein Arbeitsverzeichnis (mit dem Namen config) in dem Ordner, in dem sich Ihre Skripts befinden, und kopiert dann die Zertifikatdatei in dieses Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="0c1ec-184">Das Paket "Besitzer Paket und-Zurücksetzen" wird auch im Verzeichnis "config" erstellt und die Konfiguration für Oberflächen UEFI-Einstellungen und-Berechtigungen enthalten, die vom Skript generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="0c1ec-185">Ersetzen Sie in Zeile 73 den Wert der **$Password** -Variablen von **1234** in das Kennwort für Ihre Zertifikatsdatei.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="0c1ec-186">Wenn kein Kennwort erforderlich ist, löschen Sie den **1234** -Text.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="0c1ec-187">Die letzten beiden Zeichen des Zertifikat Fingerabdrucks sind zum Registrieren eines Geräts in Semm erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="0c1ec-188">Dieses Skript zeigt diese Ziffern dem Benutzer an, sodass der Benutzer oder Techniker diese Ziffern aufzeichnen kann, bevor das System neu gestartet wird, um das Gerät in Semm zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="0c1ec-189">Das Skript verwendet den folgenden Code, der in Zeilen 150-155 zu finden ist, um dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Administratoren mit Zugriff auf die Zertifikatsdatei (. pfx) können den Fingerabdruck jederzeit lesen, indem Sie die PFX-Datei in certmgr öffnen. <span data-ttu-id="0c1ec-191">Gehen Sie folgendermaßen vor, um den Fingerabdruck mit certmgr anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="0c1ec-192">Klicken Sie mit der rechten Maustaste auf die PFX-Datei, und wählen Sie dann **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="0c1ec-193">Erweitern Sie den Ordner im Navigationsbereich.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="0c1ec-194">Wählen Sie **Zertifikate**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="0c1ec-195">Klicken Sie im Hauptfenster mit der rechten Maustaste auf das Zertifikat, und wählen Sie dann **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="0c1ec-196">Wählen Sie die Registerkarte **Details** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="0c1ec-197">Im Dropdownmenü **anzeigen** muss nur **alle** oder **nur Eigenschaften** ausgewählt sein.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="0c1ec-198">Wählen Sie das Feld **Daumenabdruck**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c1ec-199">Der Semm-Zertifikatname und das Kennwort müssen ebenfalls in diesem Abschnitt des ResetSEMM.ps1 Skripts eingegeben werden, damit Configuration Manager Semm vom Gerät mit der Deinstallations Aktion Entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <span data-ttu-id="0c1ec-200">Konfigurieren von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0c1ec-200">Configure permissions</span></span>

<span data-ttu-id="0c1ec-201">Der erste Bereich des Skripts, in dem Sie die Konfiguration für Surface UEFI angeben, ist der Bereich " **Berechtigungen konfigurieren** ".</span><span class="sxs-lookup"><span data-stu-id="0c1ec-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="0c1ec-202">Dieser Bereich beginnt bei Zeile 210 im Beispielskript mit dem Kommentar **# configure-Berechtigungen** und fährt mit Zeile 247 fort.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="0c1ec-203">Das folgende Codefragment legt zunächst Berechtigungen für alle DGM-UEFI-Einstellungen fest, sodass Sie nur von Semm geändert werden können, und fügt dann explizite Berechtigungen hinzu, um dem lokalen Benutzer das Ändern des UEFI-Kennworts, des TPM und der Front-und rückkamera zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="0c1ec-204">Jede **$uefiV 2** -Variable kennzeichnet eine DGM-UEFI-Einstellung durch Festlegen von Name oder ID und konfiguriert dann die Berechtigungen auf einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="0c1ec-205">**$ownerOnly** – die Berechtigung zum Ändern dieser Einstellung wird nur Semm gewährt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="0c1ec-206">**$ownerAndLocalUser** – die Berechtigung zum Ändern dieser Einstellung wird einem lokalen Benutzer gewährt, der auf Surface UEFI und Semm.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="0c1ec-207">Informationen zu den verfügbaren Einstellungsnamen und IDs für Surface UEFI finden Sie im Abschnitt [Settings Names and IDs](#settings-names-and-ids) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <span data-ttu-id="0c1ec-208">Konfigurieren von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="0c1ec-208">Configure settings</span></span>

<span data-ttu-id="0c1ec-209">Der zweite Bereich des Skripts, in dem Sie die Konfiguration für Surface UEFI angeben, ist der Bereich " **Einstellungen konfigurieren** " des ConfigureSEMM.ps1 Skripts, mit dem konfiguriert wird, ob jede Einstellung aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="0c1ec-210">Das Beispielskript enthält Anweisungen zum Festlegen aller Einstellungen auf die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="0c1ec-211">Das Skript enthält dann explizite Anweisungen, um IPv6 für PXE-Start zu deaktivieren und das Surface UEFI-Administrator Kennwort unverändert zu lassen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="0c1ec-212">Sie finden diese Region beginnend mit dem Kommentar **# Configure Settings** in Zeile 291 bis Zeile 335 im Beispielskript.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="0c1ec-213">Der Bereich wird wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="0c1ec-214">Wie die Berechtigungen, die im Abschnitt " **Berechtigungen konfigurieren** " des Skripts festgelegt sind, wird die Konfiguration der einzelnen DGM-UEFI-Einstellungen durch Definieren der **$uefiV 2** -Variablen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="0c1ec-215">Für jede Zeile, die die Variable **$uefiV 2** definiert, wird eine DGM-UEFI-Einstellung durch Festlegen des Namens oder der ID identifiziert, und der konfigurierte Wert ist auf **Enabled** oder **disabled**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="0c1ec-216">Wenn Sie die Konfiguration einer Oberflächen UEFI-Einstellung nicht ändern möchten, beispielsweise um sicherzustellen, dass das Kennwort des Surface UEFI-Administrators nicht durch die Aktion zurückgesetzt wird, die alle DGM-UEFI-Einstellungen auf Ihren Standard zurücksetzen, können Sie **ClearConfiguredValue ()** verwenden, um zu erzwingen, dass diese Einstellung nicht geändert wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="0c1ec-217">Im Beispielskript wird dies in Zeile 323 verwendet, um das Löschen des Oberflächen-UEFI-Administrator Kennworts zu verhindern, das im Beispielskript anhand der Einstellungs-ID **501**identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="0c1ec-218">Informationen zu den verfügbaren Einstellungsnamen und IDs für Surface UEFI finden Sie im Abschnitt [Einstellungsnamen und IDs](#settings-names-and-ids) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <span data-ttu-id="0c1ec-219">Registrierungsschlüssel "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="0c1ec-219">Settings registry key</span></span>

<span data-ttu-id="0c1ec-220">Zum Identifizieren von eingeschriebenen Systemen für Configuration Manager schreibt das ConfigureSEMM.ps1-Skriptregistrierungsschlüssel, die zum Identifizieren von eingeschriebenen Systemen verwendet werden können, wenn Sie mit dem Semm-Konfigurationsskript installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="0c1ec-221">Diese Schlüssel finden Sie am folgenden Standort.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="0c1ec-222">Das folgende Codefragment, das in Zeilen 380-477 zu finden ist, wird zum Schreiben dieser Registrierungsschlüssel verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <span data-ttu-id="0c1ec-223">Einstellungsnamen und IDs</span><span class="sxs-lookup"><span data-stu-id="0c1ec-223">Settings names and IDs</span></span>

<span data-ttu-id="0c1ec-224">Wenn Sie die Oberflächen-UEFI-Einstellungen oder-Berechtigungen für die Oberflächen-UEFI-Einstellungen konfigurieren möchten, müssen Sie entweder den Einstellungsnamen oder die Einstellungs-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="0c1ec-225">Bei jedem neuen Update für Surface UEFI können neue Einstellungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="0c1ec-226">Die beste Methode, um eine vollständige Liste der auf einem Surface-Gerät verfügbaren Einstellungen zusammen mit dem Einstellungsnamen und den Einstellungen-IDs abzurufen, besteht darin, das ShowSettingsOptions.ps1-Skript aus SEMM_Powershell.zip in [Surface Tools für IT-Downloads](https://www.microsoft.com/download/details.aspx?id=46703) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="0c1ec-227">Auf dem Computer, auf dem ShowSettingsOptions.ps1 ausgeführt wird, muss Microsoft Surface UEFI Manager installiert sein, das Skript erfordert jedoch kein Surface-Gerät.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>


## <span data-ttu-id="0c1ec-228">Bereitstellen von Semm-Konfigurations-Manager-Skripts</span><span class="sxs-lookup"><span data-stu-id="0c1ec-228">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="0c1ec-229">Nachdem Ihre Skripts bereit sind, Semm auf dem Clientgerät zu konfigurieren und zu aktivieren, besteht der nächste Schritt darin, diese Skripts als Anwendung in Configuration Manager hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-229">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="0c1ec-230">Bevor Sie Configuration Manager öffnen, stellen Sie sicher, dass sich die folgenden Dateien in einem freigegebenen Ordner befinden, in dem keine anderen Dateien enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-230">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="0c1ec-231">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="0c1ec-231">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="0c1ec-232">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="0c1ec-232">ResetSEMM.ps1</span></span>
* <span data-ttu-id="0c1ec-233">Ihr Semm-Zertifikat (beispielsweise SEMMCertificate. pfx)</span><span class="sxs-lookup"><span data-stu-id="0c1ec-233">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="0c1ec-234">Die Semm-Konfigurations-Manager-Skripts werden dem Configuration Manager als Skriptanwendung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-234">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="0c1ec-235">Der Befehl zum Installieren von Semm mit ConfigureSEMM.ps1 lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-235">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="0c1ec-236">Der Befehl zum Deinstallieren von Semm mit ResetSEMM.ps1 lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-236">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="0c1ec-237">Verwenden Sie zum Hinzufügen der Semm-Konfigurations-Manager-Skripts zu Configuration Manager als Anwendung den folgenden Prozess:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-237">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="0c1ec-238">Starten Sie den Assistenten zum Erstellen von Anwendungen mit Schritt 1 bis Schritt 5 aus dem Abschnitt [Microsoft Surface UEFI Manager bereitstellen](#deploy-microsoft-surface-uefi-manager) weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-238">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="0c1ec-239">Gehen Sie mit dem Assistenten zum Erstellen von Anwendungen wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-239">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="0c1ec-240">**Allgemein** – wählen Sie **die Anwendungsinformationen manuell angeben**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-240">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="0c1ec-241">**Allgemeine Informationen** : Geben Sie einen Namen für die Anwendung (beispielsweise Semm) und alle weiteren gewünschten Informationen wie Publisher, Version oder Kommentare auf dieser Seite ein.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-241">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="0c1ec-242">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-242">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="0c1ec-243">**Anwendungskatalog** – die Felder auf dieser Seite können mit ihren Standardwerten verbleibt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-243">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="0c1ec-244">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-244">Select **Next**.</span></span>

   - <span data-ttu-id="0c1ec-245">**Bereitstellungstypen** – wählen Sie **Hinzufügen** aus, um den Assistenten zum Erstellen von Bereitstellungstypen zu starten.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-245">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="0c1ec-246">Führen Sie die Schritte des Assistenten zum Erstellen von Bereitstellungstypen wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-246">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="0c1ec-247">**Allgemein** – wählen Sie im Dropdownmenü **Typ** den Eintrag **Skript Installationsprogramm** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-247">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="0c1ec-248">Die Option " **Bereitstellungsinformationen manuell angeben** " wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-248">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="0c1ec-249">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-249">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="0c1ec-250">**Allgemeine Informationen** : Geben Sie einen Namen für den Bereitstellungs ein (beispielsweise Semm-Konfigurationsskripts), und wählen Sie dann **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-250">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="0c1ec-251">**Inhalt** – wählen Sie neben dem Feld **Inhaltsspeicherort** die Option **Durchsuchen** aus, und wählen Sie dann den Ordner aus, in dem sich die Semm-Konfigurations-Manager-Skripts befinden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-251">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="0c1ec-252">Geben Sie im Feld **Installationsprogramm** den oben in diesem Artikel gefundenen [Installationsbefehl](#deploy-semm-configuration-manager-scripts) ein.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-252">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="0c1ec-253">Geben Sie im Feld **Programm deinstallieren** den zuvor in diesem Artikel gefundenen [Deinstallationsbefehl](#deploy-semm-configuration-manager-scripts) ein (siehe Abbildung 2).</span><span class="sxs-lookup"><span data-stu-id="0c1ec-253">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="0c1ec-254">Wählen Sie **weiter** aus, um zur nächsten Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-254">Select **Next** to move to the next page.</span></span>
    
     ![Einrichten der Semm-Konfigurations-Manager-Skripts als Befehle zum Installieren und deinstallieren](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="0c1ec-256">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-256">Figure 2.</span></span> <span data-ttu-id="0c1ec-257">Einrichten der Semm-Konfigurations-Manager-Skripts als Befehle zum Installieren und deinstallieren</span><span class="sxs-lookup"><span data-stu-id="0c1ec-257">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="0c1ec-258">**Detection-Methode** – wählen Sie **Add-Klausel** aus, um die Erkennungsregel des Semm-Konfigurations-Manager-Skript Registrierungsschlüssels hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-258">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="0c1ec-259">Das Fenster **Erkennungsregel** wird angezeigt, wie in Abbildung 3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-259">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="0c1ec-260">Verwenden Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0c1ec-260">Use the following settings:</span></span>

       - <span data-ttu-id="0c1ec-261">Wählen Sie im Dropdownmenü **Einstellungstyp** die Option **Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-261">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="0c1ec-262">Wählen Sie im Dropdownmenü **Hive** den Eintrag **HKEY_LOCAL_MACHINE** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-262">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="0c1ec-263">Geben Sie **SOFTWARE\Microsoft\Surface\SEMM** in das **Schlüssel** Feld ein.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-263">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="0c1ec-264">Geben Sie im Feld **Wert den Wert** **CertName** ein.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-264">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="0c1ec-265">Wählen Sie im Dropdownmenü **Datentyp** die Option **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-265">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="0c1ec-266">Wählen Sie die **Registrierungseinstellung muss die folgende Regel erfüllen, um das vorhanden sein dieser Anwendungsschaltfläche anzugeben** .</span><span class="sxs-lookup"><span data-stu-id="0c1ec-266">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="0c1ec-267">Geben Sie den Namen des Zertifikats ein, das Sie in Zeile 58 des Skripts im Feld **Wert** eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-267">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="0c1ec-268">Wählen Sie **OK** aus, um das Fenster **Erkennungsregel** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-268">Select **OK** to close the **Detection Rule** window.</span></span>

     ![Verwenden eines Registrierungsschlüssels zum Identifizieren von in Semm registrierten Geräten](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="0c1ec-270">Abbildung3.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-270">Figure 3.</span></span> <span data-ttu-id="0c1ec-271">Verwenden eines Registrierungsschlüssels zum Identifizieren von in Semm registrierten Geräten</span><span class="sxs-lookup"><span data-stu-id="0c1ec-271">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="0c1ec-272">Wählen Sie **weiter** aus, um zur nächsten Seite zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-272">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="0c1ec-273">**Benutzererfahrung** : Wählen Sie im Dropdownmenü **Installationsverhalten** die Option **für System installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-273">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="0c1ec-274">Wenn Sie möchten, dass die Benutzer den Fingerabdruck des Zertifikats selbst aufzeichnen und eingeben können, lassen Sie die Anmeldeanforderung **nur dann fest, wenn ein Benutzer angemeldet ist**.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-274">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="0c1ec-275">Wenn Sie möchten, dass Ihre Administratoren den Fingerabdruck für Benutzer eingeben und die Benutzer den Fingerabdruck nicht sehen müssen, wählen Sie aus dem Dropdownmenü **Anmeldeanforderung** aus, **ob ein Benutzer angemeldet ist** .</span><span class="sxs-lookup"><span data-stu-id="0c1ec-275">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="0c1ec-276">**Anforderungen** – das ConfigureSEMM.ps1-Skript überprüft automatisch, ob es sich bei dem Gerät um ein Surface-Device handelt, bevor Sie versuchen, Semm zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-276">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="0c1ec-277">Wenn Sie jedoch beabsichtigen, diese Skriptanwendung für eine Sammlung mit anderen Geräten als denjenigen bereitzustellen, die mit Semm verwaltet werden sollen, können Sie hier Anforderungen hinzufügen, um sicherzustellen, dass diese Anwendung nur auf Surface-Geräten oder-Geräten ausgeführt wird, die Sie mit Semm verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-277">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="0c1ec-278">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-278">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="0c1ec-279">**Abhängigkeiten** – wählen Sie **Hinzufügen** aus, um das Fenster **Abhängigkeit hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-279">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="0c1ec-280">Wählen Sie **Hinzufügen** aus, um das Fenster **erforderliche Anwendung angeben** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-280">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="0c1ec-281">Geben Sie im Feld **Name der Abhängigkeitsgruppe** einen Namen für die Semm-Abhängigkeiten ein (beispielsweise *Semm-Assemblys*).</span><span class="sxs-lookup"><span data-stu-id="0c1ec-281">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="0c1ec-282">Wählen Sie **Microsoft Surface UEFI Manager** aus der Liste der **verfügbaren Anwendungen** und dem MSI-Bereitstellungs aus, und wählen Sie dann **OK** aus, um das Fenster **erforderliche Anwendung angeben** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-282">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="0c1ec-283">Aktivieren Sie das Kontrollkästchen **Automatische Installation** , wenn Microsoft Surface UEFI Manager automatisch auf Geräten installiert werden soll, wenn Sie versuchen, Semm mit den Configuration Manager-Skripts zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-283">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="0c1ec-284">Wählen Sie **OK** aus, um das Fenster **Abhängigkeit hinzufügen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-284">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="0c1ec-285">Wählen Sie **weiter** aus, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-285">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="0c1ec-286">**Zusammenfassung** – die Informationen, die Sie im Assistenten zum Erstellen von Bereitstellungstypen eingegeben haben, werden auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-286">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="0c1ec-287">Wählen Sie **weiter** aus, um Ihre Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-287">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="0c1ec-288">**Fortschritt** – auf dieser Seite wird eine Statusanzeige und ein Status angezeigt, während der Bereitstellungs für die Semm-Skriptanwendung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-288">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="0c1ec-289">**Fertigstellung** – Bestätigung der Erstellung des Bereitstellungstyps wird angezeigt, wenn der Prozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-289">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="0c1ec-290">Wählen Sie **Schließen** aus, um den Assistenten zum Erstellen von Bereitstellungstypen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-290">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="0c1ec-291">**Zusammenfassung** – die Informationen, die Sie im Assistenten zum Erstellen von Anwendungen eingegeben haben, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-291">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="0c1ec-292">Wählen Sie **weiter** aus, um die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-292">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="0c1ec-293">**Fortschritt** – auf dieser Seite wird eine Statusanzeige und ein Status angezeigt, während die Anwendung zur Software Bibliothek hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-293">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="0c1ec-294">**Fertigstellung** – die Bestätigung der erfolgreichen Anwendungserstellung wird angezeigt, wenn der Anwendungs Erstellungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-294">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="0c1ec-295">Wählen Sie **Schließen** aus, um den Assistenten zum Erstellen von Anwendungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-295">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="0c1ec-296">Nachdem die Skriptanwendung in der Software Bibliothek von Configuration Manager verfügbar ist, können Sie Semm mithilfe der Skripts, die Sie auf Geräte oder Sammlungen vorbereitet haben, verteilen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-296">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="0c1ec-297">Wenn Sie die Microsoft Surface UEFI Manager-Assemblys als eine Abhängigkeit konfiguriert haben, die automatisch installiert wird, können Sie Semm in einem einzigen Schritt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-297">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="0c1ec-298">Wenn Sie die Assemblys nicht als Abhängigkeit konfiguriert haben, müssen Sie auf den Geräten installiert werden, die Sie verwalten möchten, bevor Sie Semm aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-298">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="0c1ec-299">Wenn Sie Semm mithilfe dieser Skriptanwendung und einer für den Endbenutzer sichtbaren Konfiguration bereitstellen, wird das PowerShell-Skript gestartet, und der Fingerabdruck für das Zertifikat wird vom PowerShell-Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-299">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="0c1ec-300">Sie können feststellen, dass Ihre Benutzer diesen Fingerabdruck aufzeichnen und beim erneuten Booten des Geräts nach der Eingabeaufforderung von Surface UEFI eingeben.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-300">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="0c1ec-301">Alternativ können Sie die Anwendungsinstallation so konfigurieren, dass Sie automatisch neu gestartet und für den Benutzer unsichtbar installiert wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-301">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="0c1ec-302">In diesem Szenario muss ein Techniker den Fingerabdruck auf jedem Gerät eingeben, während er neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-302">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="0c1ec-303">Jeder Techniker, der Zugriff auf die Zertifikatsdatei hat, kann den Fingerabdruck lesen, indem Sie das Zertifikat mit CertMgr anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-303">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="0c1ec-304">Anweisungen zum Anzeigen des Fingerabdrucks mit certmgr finden Sie im Abschnitt [erstellen oder Ändern der Semm-Konfigurations-Manager-Skripts](#create-or-modify-the-semm-configuration-manager-scripts) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-304">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="0c1ec-305">Das Entfernen von Semm von einem Gerät, das mit Configuration Manager mithilfe dieser Skripts bereitgestellt wird, ist so einfach wie das Deinstallieren der Anwendung mit Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-305">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="0c1ec-306">Mit dieser Aktion wird das ResetSEMM.ps1 Skript gestartet, und die Registrierung des Geräts mit der gleichen Zertifikatdatei, die während der Bereitstellung von Semm verwendet wurde, wird ordnungsgemäß abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-306">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="0c1ec-307">Microsoft Surface empfiehlt, dass Sie Pakete nur zurücksetzen erstellen, wenn Sie die Registrierung eines Geräts aufheben müssen.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-307">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="0c1ec-308">Diese Reset-Pakete gelten in der Regel nur für ein Gerät, das durch seine Seriennummer gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-308">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="0c1ec-309">Sie können jedoch ein universelles Reset-Paket erstellen, das für jedes Gerät, das mit diesem Zertifikat in Semm registriert ist, funktionieren würde.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-309">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="0c1ec-310">Wir empfehlen dringend, das universelle Reset-Paket so sorgfältig wie das Zertifikat zu schützen, das Sie für die Registrierung von Geräten in Semm verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-310">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="0c1ec-311">Beachten Sie bitte, dass dieses universelle Reset-Paket genauso wie das Zertifikat selbst verwendet werden kann, um die Registrierung von Surface-Geräten Ihrer Organisation von Semm zu entbinden.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-311">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="0c1ec-312">Wenn Sie ein Reset-Paket installieren, wird der niedrigste unterstützte Wert (LSV) auf den Wert 1 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-312">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="0c1ec-313">Sie können ein Gerät mithilfe eines vorhandenen Konfigurationspakets erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-313">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="0c1ec-314">Das Gerät fordert den Fingerabdruck des Zertifikats auf, bevor der Besitz übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-314">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="0c1ec-315">Aus diesem Grund würde die erneute Registrierung eines Geräts in Semm erfordern, dass ein neues Paket auf dem Gerät erstellt und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-315">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="0c1ec-316">Da es sich bei dieser Aktion um eine neue Registrierung und nicht um eine Änderung der Konfiguration auf einem Gerät handelt, das bereits in Semm registriert ist, wird das Gerät zum Fingerabdruck des Zertifikats aufgefordert, bevor der Besitz übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="0c1ec-316">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>
