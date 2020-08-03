---
title: Surface-Diagnosetoolkit für Unternehmen bereitstellen
description: In diesem Thema wird die Verwendung des Surface Diagnostics Toolkit for Business erläutert.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 07/31/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 9c250cef63b760f3faab9172aa950c305e4e47e5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902983"
---
# <span data-ttu-id="a2243-103">Surface-Diagnosetoolkit für Unternehmen bereitstellen</span><span class="sxs-lookup"><span data-stu-id="a2243-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="a2243-104">Mit dem Microsoft Surface Diagnostics Toolkit for Business (Unternehmen) können IT-Administratoren Hardware-, Software-und Firmware-Probleme mit Surface-Geräten schnell untersuchen, beheben und beheben.</span><span class="sxs-lookup"><span data-stu-id="a2243-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="a2243-105">Darüber hinaus können Sie eine Reihe von Diagnosetests und Software Reparaturen durchführen, um Einblicke in die Geräte Integrität und Anleitungen für das Beheben von Problemen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a2243-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="a2243-106">Im speziellen bietet Ihnen das Unternehmen in der folgenden Funktion die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="a2243-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="a2243-107">Passen Sie das Paket an.</span><span class="sxs-lookup"><span data-stu-id="a2243-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="a2243-108">Führen Sie die App mithilfe von Befehlen aus.</span><span class="sxs-lookup"><span data-stu-id="a2243-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="a2243-109">Führen Sie mehrere Hardwaretests aus, um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a2243-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="a2243-110">Generieren von Protokollen zum Analysieren von Problemen</span><span class="sxs-lookup"><span data-stu-id="a2243-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="a2243-111">Ausführlicher Bericht zum Vergleich von Device vs optimaler Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a2243-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="a2243-112">Primäre Szenarien und Ressourcen zum herunterladen</span><span class="sxs-lookup"><span data-stu-id="a2243-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="a2243-113">Laden Sie die in der folgenden Tabelle aufgelisteten Komponenten herunter, um Sie zu Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a2243-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="a2243-114">Modus</span><span class="sxs-lookup"><span data-stu-id="a2243-114">Mode</span></span> |  <span data-ttu-id="a2243-115">Primäre Szenarien</span><span class="sxs-lookup"><span data-stu-id="a2243-115">Primary scenarios</span></span> | <span data-ttu-id="a2243-116">Herunterladen</span><span class="sxs-lookup"><span data-stu-id="a2243-116">Download</span></span> | <span data-ttu-id="a2243-117">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="a2243-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="a2243-118">Desktopmodus</span><span class="sxs-lookup"><span data-stu-id="a2243-118">Desktop mode</span></span> |  <span data-ttu-id="a2243-119">Unterstützen Sie Benutzer beim Ausführen von "auf Ihren Surface Devices", um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a2243-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="a2243-120">Erstellen Sie ein benutzerdefiniertes Paket, das auf einem oder mehreren Oberflächen-Geräten bereitgestellt werden soll, sodass Benutzer bestimmte Protokolle zum Sammeln und analysieren auswählen können.</span><span class="sxs-lookup"><span data-stu-id="a2243-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="a2243-121">Verteilbares MSI-Paket:</span><span class="sxs-lookup"><span data-stu-id="a2243-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="a2243-122">Microsoft Surface Diagnostics Toolkit für Business-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="a2243-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="a2243-123">Surface-Tools für IT</span><span class="sxs-lookup"><span data-stu-id="a2243-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="a2243-124">Verwenden des Surface Diagnostic Toolkit im Desktopmodus</span><span class="sxs-lookup"><span data-stu-id="a2243-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="a2243-125">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="a2243-125">Command line</span></span> |  <span data-ttu-id="a2243-126">Direkte Problembehandlung von Surface Devices Remote ohne Benutzerinteraktion mithilfe von Standardtools wie Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2243-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="a2243-127">Sie umfasst die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="a2243-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="a2243-128">sammelt alle Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="a2243-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="a2243-129">führt die Integritäts Diagnose mithilfe von Best Practice Analyzer aus.</span><span class="sxs-lookup"><span data-stu-id="a2243-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="a2243-130">überprüft Windows Update auf fehlende Firmware-oder Treiberupdates.</span><span class="sxs-lookup"><span data-stu-id="a2243-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="a2243-131">überprüft die Gewährleistungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="a2243-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="a2243-132">App für die APP-Konsole:</span><span class="sxs-lookup"><span data-stu-id="a2243-132">SDT console app:</span></span><br><span data-ttu-id="a2243-133">Microsoft Surface Diagnostics-App-Konsole</span><span class="sxs-lookup"><span data-stu-id="a2243-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="a2243-134">Surface-Tools für IT</span><span class="sxs-lookup"><span data-stu-id="a2243-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="a2243-135">Ausführen des Surface Diagnostic Toolkit mithilfe von Befehlen</span><span class="sxs-lookup"><span data-stu-id="a2243-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="a2243-136">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="a2243-136">Supported devices</span></span> 

<span data-ttu-id="a2243-137">Für Unternehmens-Devices (Surface 3 und höher) werden die folgenden Geräte unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a2243-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="a2243-138">DGM-Buch 3</span><span class="sxs-lookup"><span data-stu-id="a2243-138">Surface Book 3</span></span>
- <span data-ttu-id="a2243-139">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="a2243-139">Surface Go 2</span></span>
- <span data-ttu-id="a2243-140">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="a2243-140">Surface Pro X</span></span>
- <span data-ttu-id="a2243-141">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a2243-141">Surface Pro 7</span></span>
- <span data-ttu-id="a2243-142">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="a2243-142">Surface Laptop 3</span></span>
- <span data-ttu-id="a2243-143">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="a2243-143">Surface Pro 6</span></span>
- <span data-ttu-id="a2243-144">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="a2243-144">Surface Laptop 2</span></span>
- <span data-ttu-id="a2243-145">Surface Go</span><span class="sxs-lookup"><span data-stu-id="a2243-145">Surface Go</span></span>
- <span data-ttu-id="a2243-146">Surface Go mit LTE</span><span class="sxs-lookup"><span data-stu-id="a2243-146">Surface Go with LTE</span></span>
- <span data-ttu-id="a2243-147">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="a2243-147">Surface Book 2</span></span>
- <span data-ttu-id="a2243-148">Surface Pro mit LTE Advanced (Modell 1807)</span><span class="sxs-lookup"><span data-stu-id="a2243-148">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="a2243-149">Surface Pro (Modell 1796)</span><span class="sxs-lookup"><span data-stu-id="a2243-149">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="a2243-150">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="a2243-150">Surface Laptop</span></span>
- <span data-ttu-id="a2243-151">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="a2243-151">Surface Studio</span></span>
- <span data-ttu-id="a2243-152">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="a2243-152">Surface Studio 2</span></span>
- <span data-ttu-id="a2243-153">Surface Book</span><span class="sxs-lookup"><span data-stu-id="a2243-153">Surface Book</span></span>
- <span data-ttu-id="a2243-154">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a2243-154">Surface Pro 4</span></span>
- <span data-ttu-id="a2243-155">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="a2243-155">Surface 3 LTE</span></span>
- <span data-ttu-id="a2243-156">Surface3</span><span class="sxs-lookup"><span data-stu-id="a2243-156">Surface 3</span></span>
- <span data-ttu-id="a2243-157">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="a2243-157">Surface Pro 3</span></span>

## <span data-ttu-id="a2243-158">Installieren des Surface Diagnostics Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="a2243-158">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="a2243-159">So erstellen Sie ein unstrukturiertes Paket, das Sie an Benutzer in Ihrer Organisation verteilen können:</span><span class="sxs-lookup"><span data-stu-id="a2243-159">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="a2243-160">Mit dem Administrator Konto können Sie sich bei Ihrem Surface-Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="a2243-160">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="a2243-161">Laden Sie das Windows Installer-Paket (. msi) auf der [Seite Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) herunter, und kopieren Sie es an eine bevorzugte Position auf dem Surface-Gerät, beispielsweise Desktop.</span><span class="sxs-lookup"><span data-stu-id="a2243-161">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="a2243-162">Der Assistent für die strukturierte Einrichtung wird angezeigt, wie in Abbildung 1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a2243-162">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="a2243-163">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a2243-163">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="a2243-164">Wenn der Setup-Assistent nicht angezeigt wird, stellen Sie sicher, dass Sie beim Administrator Konto auf Ihrem Computer angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="a2243-164">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Willkommen beim Setup-Assistenten für Surface Diagnostics Toolkit](images/sdt-1.png)

    *<span data-ttu-id="a2243-166">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="a2243-166">Figure 1.</span></span> <span data-ttu-id="a2243-167">Setup-Assistent für Surface Diagnostics Toolkit</span><span class="sxs-lookup"><span data-stu-id="a2243-167">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="a2243-168">Klicken Sie auf **weiter**, um den Endbenutzer-Lizenzvertrag (EULA) zu akzeptieren, wenn der Assistent für die strukturierte Installation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a2243-168">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="a2243-169">Ändern Sie auf dem Bildschirm Installationsoptionen den Standard Installationsspeicherort, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="a2243-169">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="a2243-170">Wählen Sie unter Setuptyp die Option **erweitert**aus.</span><span class="sxs-lookup"><span data-stu-id="a2243-170">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="a2243-171">Die Standardoption ermöglicht es Benutzern, das Diagnosetool direkt auf dem Surface-Gerät auszuführen, vorausgesetzt, dass Sie mit einem Administrator Konto bei Ihrem Gerät angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="a2243-171">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Installationsoptionen: erweitert](images/sdt-install.png)

7. <span data-ttu-id="a2243-173">Klicken Sie auf **weiter** , und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="a2243-173">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="a2243-174">Installieren über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="a2243-174">Installing using the command line</span></span>
<span data-ttu-id="a2243-175">Wenn Sie möchten, können Sie an einer Eingabeaufforderung die Option "unstrukturierte" installieren und ein benutzerdefiniertes Flag einrichten, um das Tool im Administratormodus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a2243-175">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="a2243-176">In der folgenden Option werden die Flags für die Installation angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a2243-176">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="a2243-177">sendet Telemetrie-Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2243-177">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="a2243-178">Das Flag akzeptiert `0` für deaktiviert oder `1` für aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a2243-178">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="a2243-179">Der Standardwert lautet " `1` Telemetrie senden".</span><span class="sxs-lookup"><span data-stu-id="a2243-179">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="a2243-180">konfiguriert das Tool, das im Administratormodus installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2243-180">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="a2243-181">Das Flag akzeptiert den `0` Client Modus oder den `1` IT-Administrator Modus.</span><span class="sxs-lookup"><span data-stu-id="a2243-181">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="a2243-182">Der Standardwert lautet `0`.</span><span class="sxs-lookup"><span data-stu-id="a2243-182">The default value is `0`.</span></span>

### <span data-ttu-id="a2243-183">So installieren Sie "von" in der Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="a2243-183">To install SDT from the command line:</span></span>

1. <span data-ttu-id="a2243-184">Öffnen Sie eine Eingabeaufforderung, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a2243-184">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="a2243-185">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2243-185">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="a2243-186">Suchen von "nach" auf Ihrem Surface-Gerät</span><span class="sxs-lookup"><span data-stu-id="a2243-186">Locating SDT on your Surface device</span></span>

<span data-ttu-id="a2243-187">Sowohl die Sonderanwendungen als auch die APP-Konsole sind unter installiert `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="a2243-187">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="a2243-188">Zusätzlich zu der exe-Datei installiert die Datei eine JSON-Datei und eine admin.dll-Datei (modules\admin.dll), wie in Abbildung 2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a2243-188">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![Liste der im Datei-Explorer installierten Dateien](images/sdt-2.png)

*<span data-ttu-id="a2243-190">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="a2243-190">Figure 2.</span></span> <span data-ttu-id="a2243-191">Dateien, die von "unstrukturierte" installiert wurden</span><span class="sxs-lookup"><span data-stu-id="a2243-191">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="a2243-192">Vorbereiten des unstrukturierten Pakets für die Verteilung</span><span class="sxs-lookup"><span data-stu-id="a2243-192">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="a2243-193">Durch das Erstellen eines benutzerdefinierten Pakets können Sie das Tool auf bestimmte bekannte Probleme ausrichten.</span><span class="sxs-lookup"><span data-stu-id="a2243-193">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="a2243-194">Klicken Sie auf **Start > ausführen**, geben Sie **Surface** ein, und klicken Sie dann auf **Surface Diagnostics Toolkit for Business**.</span><span class="sxs-lookup"><span data-stu-id="a2243-194">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="a2243-195">Wenn das Tool geöffnet wird, klicken Sie auf **benutzerdefiniertes Paket erstellen**, wie in Abbildung 3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a2243-195">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Option ' benutzerdefiniertes Paket erstellen '](images/sdt-3.png)

    *<span data-ttu-id="a2243-197">Abbildung3.</span><span class="sxs-lookup"><span data-stu-id="a2243-197">Figure 3.</span></span> <span data-ttu-id="a2243-198">Erstellen eines benutzerdefinierten Pakets</span><span class="sxs-lookup"><span data-stu-id="a2243-198">Create custom package</span></span>*

### <span data-ttu-id="a2243-199">Einstellungen für Sprache und Telemetrie</span><span class="sxs-lookup"><span data-stu-id="a2243-199">Language and telemetry settings</span></span>

  <span data-ttu-id="a2243-200">Beim Erstellen eines Pakets können Sie Spracheinstellungen auswählen oder das Senden von Telemetrie-Informationen an Microsoft deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2243-200">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="a2243-201">Standardmäßig sendet die datentelemetrie an Microsoft, die zur Verbesserung der Anwendung in Übereinstimmung mit den [Datenschutzbestimmungen von Microsoft](https://privacy.microsoft.com/privacystatement)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2243-201">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="a2243-202">Wenn Sie ablehnen möchten, deaktivieren Sie das Kontrollkästchen beim Erstellen eines benutzerdefinierten Pakets, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a2243-202">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="a2243-203">Oder deaktivieren Sie das Kontrollkästchen **Telemetrie an Microsoft senden** auf der Seite " **Installationsoptionen** " während der Einrichtung des Programms.</span><span class="sxs-lookup"><span data-stu-id="a2243-203">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="a2243-204">Diese Einstellung hat keinen Einfluss auf die minimale Telemetrie, die auf Microsoft-Servern automatisch gespeichert wird, wenn Tests und Reparaturen ausgeführt werden, bei denen eine Internet Verbindung erforderlich ist, beispielsweise Windows Update und Software Reparatur, oder Feedback über die Schaltflächen Lächeln oder missbilligen in der APP-Symbolleiste bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a2243-204">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Auswählen von Sprach-und Telemetrie-Einstellungen](images/sdt-4.png)

*<span data-ttu-id="a2243-206">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="a2243-206">Figure 4.</span></span> <span data-ttu-id="a2243-207">Auswählen von Sprach-und Telemetrie-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a2243-207">Select language and telemetry settings</span></span>*


### <span data-ttu-id="a2243-208">Windows Update-Seite</span><span class="sxs-lookup"><span data-stu-id="a2243-208">Windows Update page</span></span>

<span data-ttu-id="a2243-209">Wählen Sie die für Ihre Organisation geeignete Option aus.</span><span class="sxs-lookup"><span data-stu-id="a2243-209">Select the option appropriate for your organization.</span></span> <span data-ttu-id="a2243-210">Die meisten Organisationen mit mehreren Benutzern wählen in der Regel aus, um Updates über Windows Server Update Services (WSUS) zu erhalten, wie in Abbildung 5 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="a2243-210">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="a2243-211">Wenn Sie lokale Windows Update-Pakete oder WSUS verwenden, geben Sie den Pfad entsprechend ein.</span><span class="sxs-lookup"><span data-stu-id="a2243-211">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Windows Update-Option auswählen](images/sdt-5.png)

*<span data-ttu-id="a2243-213">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="a2243-213">Figure 5.</span></span> <span data-ttu-id="a2243-214">Windows Update-Option</span><span class="sxs-lookup"><span data-stu-id="a2243-214">Windows Update option</span></span>*

### <span data-ttu-id="a2243-215">Seite "Software Reparatur"</span><span class="sxs-lookup"><span data-stu-id="a2243-215">Software repair page</span></span>

<span data-ttu-id="a2243-216">Auf diese Weise können Sie die Option zum Ausführen von Software Reparatur Updates auswählen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="a2243-216">This allows you to select or remove the option to run software repair updates.</span></span> 

![Option "Software Reparatur" auswählen](images/sdt-6.png)

*<span data-ttu-id="a2243-218">Abbildung6.</span><span class="sxs-lookup"><span data-stu-id="a2243-218">Figure 6.</span></span> <span data-ttu-id="a2243-219">Option für Software Reparatur</span><span class="sxs-lookup"><span data-stu-id="a2243-219">Software repair option</span></span>*

### <span data-ttu-id="a2243-220">Sammeln von Protokollen und Speichern der Paketseite</span><span class="sxs-lookup"><span data-stu-id="a2243-220">Collecting logs and saving package page</span></span>

<span data-ttu-id="a2243-221">Sie können auswählen, dass eine große Auswahl von Protokollen für Anwendungen, Treiber, Hardware und das Betriebssystem ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2243-221">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="a2243-222">Klicken Sie auf den entsprechenden Bereich, und wählen Sie im Menü verfügbare Protokolle aus.</span><span class="sxs-lookup"><span data-stu-id="a2243-222">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="a2243-223">Anschließend können Sie das Paket auf einem Softwareverteilungspunkt oder einem entsprechenden Speicherort speichern, auf den Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a2243-223">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Auswählen von Protokolloptionen](images/sdt-7.png)

*<span data-ttu-id="a2243-225">Abbildung7.</span><span class="sxs-lookup"><span data-stu-id="a2243-225">Figure 7.</span></span> <span data-ttu-id="a2243-226">Protokolloption und Paket speichern</span><span class="sxs-lookup"><span data-stu-id="a2243-226">Log option and save package</span></span>*

## <span data-ttu-id="a2243-227">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a2243-227">Next steps</span></span>

- [<span data-ttu-id="a2243-228">Surface-Diagnosetoolkit für Unternehmen im Desktopmodus verwenden</span><span class="sxs-lookup"><span data-stu-id="a2243-228">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="a2243-229">Verwenden von Surface Diagnostics Toolkit for Business mithilfe von Befehlen</span><span class="sxs-lookup"><span data-stu-id="a2243-229">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="a2243-230">Änderungen und Updates</span><span class="sxs-lookup"><span data-stu-id="a2243-230">Changes and updates</span></span>


### <span data-ttu-id="a2243-231">Version 2.121.139</span><span class="sxs-lookup"><span data-stu-id="a2243-231">Version 2.121.139</span></span>
*<span data-ttu-id="a2243-232">Veröffentlichungsdatum: Juli 31 2020</span><span class="sxs-lookup"><span data-stu-id="a2243-232">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="a2243-233">Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a2243-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a2243-234">Nahtlose Unterstützung</span><span class="sxs-lookup"><span data-stu-id="a2243-234">Seamless support experience</span></span>
- <span data-ttu-id="a2243-235">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a2243-235">Bug fixes</span></span>

### <span data-ttu-id="a2243-236">Version 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="a2243-236">Version 2.94.139.0</span></span>
*<span data-ttu-id="a2243-237">Veröffentlichungsdatum: 11. Mai 2020</span><span class="sxs-lookup"><span data-stu-id="a2243-237">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="a2243-238">Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a2243-238">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a2243-239">Möglichkeit, Windows Update zu überspringen, um eine Hardwareüberprüfung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a2243-239">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="a2243-240">Möglichkeit zum Empfang von Benachrichtigungen über die neueste Version des Updates</span><span class="sxs-lookup"><span data-stu-id="a2243-240">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="a2243-241">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="a2243-241">Surface Go 2</span></span>
- <span data-ttu-id="a2243-242">DGM-Buch 3</span><span class="sxs-lookup"><span data-stu-id="a2243-242">Surface Book 3</span></span>
- <span data-ttu-id="a2243-243">Statusanzeige anzeigen</span><span class="sxs-lookup"><span data-stu-id="a2243-243">Show progress indicator</span></span>


### <span data-ttu-id="a2243-244">Version 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="a2243-244">Version 2.43.139.0</span></span>
*<span data-ttu-id="a2243-245">Veröffentlichungsdatum: 21. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="a2243-245">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="a2243-246">Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a2243-246">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a2243-247">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a2243-247">Surface Pro 7</span></span>
- <span data-ttu-id="a2243-248">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="a2243-248">Surface Laptop 3</span></span>

### <span data-ttu-id="a2243-249">Version 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="a2243-249">Version 2.42.139.0</span></span>
*<span data-ttu-id="a2243-250">Veröffentlichungsdatum: 24. September 2019</span><span class="sxs-lookup"><span data-stu-id="a2243-250">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="a2243-251">Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a2243-251">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="a2243-252">Möglichkeit zum Herunterladen von Hardwareberichten</span><span class="sxs-lookup"><span data-stu-id="a2243-252">Ability to download hardware reports.</span></span>
- <span data-ttu-id="a2243-253">Möglichkeit, den Microsoft-Support direkt über das Tool zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="a2243-253">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="a2243-254">Version 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="a2243-254">Version 2.41.139.0</span></span>
*<span data-ttu-id="a2243-255">Veröffentlichungsdatum: Juni 24, 2019</span><span class="sxs-lookup"><span data-stu-id="a2243-255">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="a2243-256">Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a2243-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="a2243-257">Informationen zu Treiberversionen, die in Protokollen und Berichten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a2243-257">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="a2243-258">Möglichkeit, Feedback zur APP bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a2243-258">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="a2243-259">Version 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="a2243-259">Version 2.36.139.0</span></span>
*<span data-ttu-id="a2243-260">Veröffentlichungsdatum: April 26, 2019</span><span class="sxs-lookup"><span data-stu-id="a2243-260">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="a2243-261">Diese Version des Surface Diagnostics Toolkit for Business bietet Unterstützung für die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a2243-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="a2243-262">Erweiterte Setup Option zum Entsperren von Administratorfunktionen über die Benutzeroberfläche des Installationsprogramms, ohne dass die Befehlszeilenkonfiguration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a2243-262">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="a2243-263">Verbesserungen bei der Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="a2243-263">Accessibility improvements.</span></span>
- <span data-ttu-id="a2243-264">Einstellungen für die Oberflächen Helligkeitssteuerung, die in Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a2243-264">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="a2243-265">Link zum Kompatibilitäts Support für externe Monitore im Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="a2243-265">External monitor compatibility support link in report generator.</span></span>
