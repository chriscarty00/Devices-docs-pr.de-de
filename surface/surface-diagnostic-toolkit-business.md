---
title: Surface-Diagnosetoolkit für Unternehmen bereitstellen
description: In diesem Thema wird die Verwendung des Surface Diagnostic Toolkit for Business erläutert.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271579"
---
# <span data-ttu-id="cc21a-103">Surface-Diagnosetoolkit für Unternehmen bereitstellen</span><span class="sxs-lookup"><span data-stu-id="cc21a-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="cc21a-104">Das Microsoft Surface Diagnostic Toolkit for Business (SDT) ermöglicht es IT-Administratoren, Hardware-, Software- und Firmwareprobleme mit Surface-Geräten schnell zu untersuchen, zu beheben und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cc21a-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="cc21a-105">Sie können eine Reihe von Diagnosetests und Softwarereparaturen ausführen, zusätzlich zum Abrufen von Einblicken in die Geräteintegdaten und Anleitungen zur Behebung von Problemen.</span><span class="sxs-lookup"><span data-stu-id="cc21a-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="cc21a-106">SdT for Business ermöglicht Ihnen insbesondere:</span><span class="sxs-lookup"><span data-stu-id="cc21a-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="cc21a-107">Passen Sie das Paket an.</span><span class="sxs-lookup"><span data-stu-id="cc21a-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="cc21a-108">Führen Sie die App mithilfe von Befehlen aus.</span><span class="sxs-lookup"><span data-stu-id="cc21a-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="cc21a-109">Führen Sie mehrere Hardwaretests aus, um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cc21a-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="cc21a-110">Generieren sie Protokolle für die Analyse von Problemen.</span><span class="sxs-lookup"><span data-stu-id="cc21a-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="cc21a-111">Erhalten Sie einen detaillierten Bericht, in dem das Gerät mit der optimalen Konfiguration verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="cc21a-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="cc21a-112">Primäre Szenarien und Downloadressourcen</span><span class="sxs-lookup"><span data-stu-id="cc21a-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="cc21a-113">Laden Sie zum Ausführen von SDT for Business die in der folgenden Tabelle aufgeführten Komponenten herunter.</span><span class="sxs-lookup"><span data-stu-id="cc21a-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="cc21a-114">Modus</span><span class="sxs-lookup"><span data-stu-id="cc21a-114">Mode</span></span> |  <span data-ttu-id="cc21a-115">Primäre Szenarien</span><span class="sxs-lookup"><span data-stu-id="cc21a-115">Primary scenarios</span></span> | <span data-ttu-id="cc21a-116">Herunterladen</span><span class="sxs-lookup"><span data-stu-id="cc21a-116">Download</span></span> | <span data-ttu-id="cc21a-117">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="cc21a-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="cc21a-118">Desktopmodus</span><span class="sxs-lookup"><span data-stu-id="cc21a-118">Desktop mode</span></span> |  <span data-ttu-id="cc21a-119">Unterstützen Sie Benutzer bei der Ausführung von SDT auf ihren Surface-Geräten, um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cc21a-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="cc21a-120">Erstellen Sie ein benutzerdefiniertes Paket für die Bereitstellung auf einem oder mehreren Surface-Geräten, sodass Benutzer bestimmte Protokolle zum Sammeln und Analysieren auswählen können.</span><span class="sxs-lookup"><span data-stu-id="cc21a-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="cc21a-121">Verteilbares SDT-MSI-Paket:</span><span class="sxs-lookup"><span data-stu-id="cc21a-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="cc21a-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span><span class="sxs-lookup"><span data-stu-id="cc21a-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="cc21a-123">Surface-Tools für IT</span><span class="sxs-lookup"><span data-stu-id="cc21a-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="cc21a-124">Verwenden des Surface Diagnostic Toolkits im Desktopmodus</span><span class="sxs-lookup"><span data-stu-id="cc21a-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="cc21a-125">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cc21a-125">Command line</span></span> |  <span data-ttu-id="cc21a-126">Direkte Problembehandlung für Surface-Geräte remote ohne Benutzerinteraktion mithilfe von Standardtools wie Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cc21a-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="cc21a-127">Sie enthält die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="cc21a-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="cc21a-128">sammelt alle Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="cc21a-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="cc21a-129">Führt Integritätsdiagnosen mit Best Practice Analyzer aus.</span><span class="sxs-lookup"><span data-stu-id="cc21a-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="cc21a-130">Überprüft Windows Update auf fehlende Firmware- oder Treiberupdates.</span><span class="sxs-lookup"><span data-stu-id="cc21a-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="cc21a-131">überprüft Garantieinformationen.</span><span class="sxs-lookup"><span data-stu-id="cc21a-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="cc21a-132">SDT-Konsolen-App:</span><span class="sxs-lookup"><span data-stu-id="cc21a-132">SDT console app:</span></span><br><span data-ttu-id="cc21a-133">Microsoft Surface Diagnostics App Console</span><span class="sxs-lookup"><span data-stu-id="cc21a-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="cc21a-134">Surface-Tools für IT</span><span class="sxs-lookup"><span data-stu-id="cc21a-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="cc21a-135">Ausführen des Surface Diagnostic Toolkit mithilfe von Befehlen</span><span class="sxs-lookup"><span data-stu-id="cc21a-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="cc21a-136">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="cc21a-136">Supported devices</span></span> 

<span data-ttu-id="cc21a-137">SDT for Business wird auf Surface 3 und höher unterstützt, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="cc21a-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="cc21a-138">Surface Book – alle Generationen</span><span class="sxs-lookup"><span data-stu-id="cc21a-138">Surface Book - all generations</span></span>
- <span data-ttu-id="cc21a-139">Surface Go – alle Generationen</span><span class="sxs-lookup"><span data-stu-id="cc21a-139">Surface Go - all generations</span></span>
- <span data-ttu-id="cc21a-140">Surface Laptop – alle Generationen</span><span class="sxs-lookup"><span data-stu-id="cc21a-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="cc21a-141">Surface Pro 3 und höher</span><span class="sxs-lookup"><span data-stu-id="cc21a-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="cc21a-142">Surface Pro X – alle Generationen</span><span class="sxs-lookup"><span data-stu-id="cc21a-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="cc21a-143">Surface Studio – alle Generationen</span><span class="sxs-lookup"><span data-stu-id="cc21a-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="cc21a-144">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="cc21a-144">Surface 3 LTE</span></span>
- <span data-ttu-id="cc21a-145">Surface3</span><span class="sxs-lookup"><span data-stu-id="cc21a-145">Surface 3</span></span>


## <span data-ttu-id="cc21a-146">Installieren des Surface Diagnostic Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="cc21a-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="cc21a-147">So erstellen Sie ein SDT-Paket, das Sie an Benutzer in Ihrer Organisation verteilen können:</span><span class="sxs-lookup"><span data-stu-id="cc21a-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="cc21a-148">Melden Sie sich mit dem Administratorkonto bei Ihrem Surface-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="cc21a-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="cc21a-149">Laden Sie das SDT Windows Installer Package (MSI) von der Downloadseite der [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) herunter, und kopieren Sie es an einen bevorzugten Speicherort auf Ihrem Surface-Gerät, z. B. Desktop.</span><span class="sxs-lookup"><span data-stu-id="cc21a-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="cc21a-150">Der SDT-Setup-Assistent wird angezeigt, wie in Abbildung 1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc21a-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="cc21a-151">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cc21a-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="cc21a-152">Wenn der Setup-Assistent nicht angezeigt wird, stellen Sie sicher, dass Sie beim Administratorkonto auf Ihrem Computer angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="cc21a-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Willkommen beim Surface Diagnostic Toolkit-Setup-Assistenten](images/sdt-1.png)

    *<span data-ttu-id="cc21a-154">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="cc21a-154">Figure 1.</span></span> <span data-ttu-id="cc21a-155">Surface Diagnostic Toolkit-Setup-Assistent</span><span class="sxs-lookup"><span data-stu-id="cc21a-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="cc21a-156">Wenn der SDT-Setup-Assistent angezeigt wird, klicken Sie auf **"Weiter",** und akzeptieren Sie den Endbenutzer-Lizenzvertrag.</span><span class="sxs-lookup"><span data-stu-id="cc21a-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="cc21a-157">Ändern Sie auf dem Bildschirm "Installationsoptionen" bei Bedarf den Standardinstallationsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="cc21a-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="cc21a-158">Wählen Sie unter "Setuptyp" die Option **"Erweitert" aus.**</span><span class="sxs-lookup"><span data-stu-id="cc21a-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="cc21a-159">Mit der Standardoption können Benutzer das Diagnosetool direkt auf ihrem Surface-Gerät ausführen, sofern sie über ein Administratorkonto bei ihrem Gerät angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="cc21a-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Installationsoptionen: Erweitert](images/sdt-install.png)

7. <span data-ttu-id="cc21a-161">Klicken Sie **auf "Weiter",** und klicken Sie dann auf **"Installieren".**</span><span class="sxs-lookup"><span data-stu-id="cc21a-161">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="cc21a-162">Installieren über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cc21a-162">Installing using the command line</span></span>
<span data-ttu-id="cc21a-163">Bei Bedarf können Sie SDT an einer Eingabeaufforderung installieren und ein benutzerdefiniertes Flag festlegen, um das Tool im Administratormodus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="cc21a-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="cc21a-164">SDT enthält die folgenden Installationsoptionsflags:</span><span class="sxs-lookup"><span data-stu-id="cc21a-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="cc21a-165">sendet Telemetriedaten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc21a-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="cc21a-166">Das Flag akzeptiert `0` "Deaktiviert" oder `1` "Aktiviert".</span><span class="sxs-lookup"><span data-stu-id="cc21a-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="cc21a-167">Der Standardwert ist das `1` Senden von Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="cc21a-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="cc21a-168">konfiguriert das Tool für die Installation im Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="cc21a-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="cc21a-169">Das Flag akzeptiert `0` den Clientmodus oder `1` den IT-Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="cc21a-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="cc21a-170">Der Standardwert lautet `0`.</span><span class="sxs-lookup"><span data-stu-id="cc21a-170">The default value is `0`.</span></span>

### <span data-ttu-id="cc21a-171">So installieren Sie SDT über die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="cc21a-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="cc21a-172">Öffnen Sie eine Eingabeaufforderung, und geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="cc21a-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="cc21a-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cc21a-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="cc21a-174">Suchen von SDT auf Ihrem Surface-Gerät</span><span class="sxs-lookup"><span data-stu-id="cc21a-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="cc21a-175">Sowohl SDT als auch die SDT-App-Konsole werden unter `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` installiert.</span><span class="sxs-lookup"><span data-stu-id="cc21a-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="cc21a-176">Neben der EXE-Datei installiert SDT eine JSON-Datei und eine admin.dll (modules\admin.dll), wie in Abbildung 2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc21a-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![Liste der installierten SDT-Dateien im Datei-Explorer](images/sdt-2.png)

*<span data-ttu-id="cc21a-178">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="cc21a-178">Figure 2.</span></span> <span data-ttu-id="cc21a-179">Von SDT installierte Dateien</span><span class="sxs-lookup"><span data-stu-id="cc21a-179">Files installed by SDT</span></span>*

## <a name="preparing-the-sdt-package-for-distribution"></a><span data-ttu-id="cc21a-180">Vorbereiten des SDT-Pakets für die Verteilung</span><span class="sxs-lookup"><span data-stu-id="cc21a-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="cc21a-181">Durch das Erstellen eines benutzerdefinierten Pakets können Sie das Tool auf bestimmte bekannte Probleme konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="cc21a-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="cc21a-182">Klicken **Sie auf > Ausführen,** geben Sie Surface **ein,** und klicken Sie dann auf **Surface Diagnostic Toolkit for Business**.</span><span class="sxs-lookup"><span data-stu-id="cc21a-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="cc21a-183">Klicken Sie beim Öffnen des Tools auf "Benutzerdefiniertes **Paket erstellen",** wie in Abbildung 3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc21a-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Option "Benutzerdefiniertes Paket erstellen"](images/sdt-3.png)

    *<span data-ttu-id="cc21a-185">Abbildung3.</span><span class="sxs-lookup"><span data-stu-id="cc21a-185">Figure 3.</span></span> <span data-ttu-id="cc21a-186">Erstellen eines benutzerdefinierten Pakets</span><span class="sxs-lookup"><span data-stu-id="cc21a-186">Create custom package</span></span>*

### <span data-ttu-id="cc21a-187">Sprach- und Telemetrieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="cc21a-187">Language and telemetry settings</span></span>

  <span data-ttu-id="cc21a-188">Beim Erstellen eines Pakets können Sie Spracheinstellungen auswählen oder das Senden von Telemetrieinformationen an Microsoft deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc21a-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="cc21a-189">Standardmäßig sendet SDT Telemetrie an Microsoft, die verwendet wird, um die Anwendung in Übereinstimmung mit den Datenschutzbestimmungen von [Microsoft zu verbessern.](https://privacy.microsoft.com/privacystatement)</span><span class="sxs-lookup"><span data-stu-id="cc21a-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="cc21a-190">Wenn Sie dies ablehnen möchten, müssen Sie das Kontrollkästchen beim Erstellen eines benutzerdefinierten Pakets wie unten dargestellt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc21a-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="cc21a-191">Oder aktivieren Sie das **Kontrollkästchen "Telemetrie** an Microsoft senden" auf der Seite **"Installationsoptionen"** während des SDT-Setups.</span><span class="sxs-lookup"><span data-stu-id="cc21a-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="cc21a-192">Diese Einstellung wirkt sich nicht auf die minimale Telemetrie aus, die automatisch auf den Servern von Microsoft gespeichert wird, wenn Tests und Reparaturen ausgeführt werden, die eine Internetverbindung erfordern, z. B. Windows Update und Softwarereparatur, oder geben Feedback über die Schaltflächen "Smile" oder "Stirnrunzeln" in der Symbolleiste der App.</span><span class="sxs-lookup"><span data-stu-id="cc21a-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Auswählen von Sprach- und Telemetrieeinstellungen](images/sdt-4.png)

*<span data-ttu-id="cc21a-194">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="cc21a-194">Figure 4.</span></span> <span data-ttu-id="cc21a-195">Auswählen von Sprach- und Telemetrieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="cc21a-195">Select language and telemetry settings</span></span>*


### <span data-ttu-id="cc21a-196">Windows Update-Seite</span><span class="sxs-lookup"><span data-stu-id="cc21a-196">Windows Update page</span></span>

<span data-ttu-id="cc21a-197">Wählen Sie die für Ihre Organisation geeignete Option aus.</span><span class="sxs-lookup"><span data-stu-id="cc21a-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="cc21a-198">Die meisten Organisationen mit mehreren Benutzern wählen in der Regel updates über Windows Server Update Services (WSUS) aus, wie in Abbildung 5 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc21a-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="cc21a-199">Wenn Sie lokale Windows Update-Pakete oder WSUS verwenden, geben Sie den Pfad entsprechend ein.</span><span class="sxs-lookup"><span data-stu-id="cc21a-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Option "Windows Update auswählen"](images/sdt-5.png)

*<span data-ttu-id="cc21a-201">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="cc21a-201">Figure 5.</span></span> <span data-ttu-id="cc21a-202">Windows Update-Option</span><span class="sxs-lookup"><span data-stu-id="cc21a-202">Windows Update option</span></span>*

### <span data-ttu-id="cc21a-203">Seite "Softwarereparatur"</span><span class="sxs-lookup"><span data-stu-id="cc21a-203">Software repair page</span></span>

<span data-ttu-id="cc21a-204">Auf diese Weise können Sie die Option zum Ausführen von Softwarereparaturupdates auswählen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="cc21a-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![Softwarereparaturoption auswählen](images/sdt-6.png)

*<span data-ttu-id="cc21a-206">Abbildung6.</span><span class="sxs-lookup"><span data-stu-id="cc21a-206">Figure 6.</span></span> <span data-ttu-id="cc21a-207">Softwarereparaturoption</span><span class="sxs-lookup"><span data-stu-id="cc21a-207">Software repair option</span></span>*

### <span data-ttu-id="cc21a-208">Sammeln von Protokollen und Speichern der Paketseite</span><span class="sxs-lookup"><span data-stu-id="cc21a-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="cc21a-209">Sie können eine Vielzahl von Protokollen für Anwendungen, Treiber, Hardware und das Betriebssystem ausführen.</span><span class="sxs-lookup"><span data-stu-id="cc21a-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="cc21a-210">Klicken Sie auf den entsprechenden Bereich, und wählen Sie im Menü der verfügbaren Protokolle aus.</span><span class="sxs-lookup"><span data-stu-id="cc21a-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="cc21a-211">Anschließend können Sie das Paket an einem Softwareverteilungspunkt oder einem gleichwertigen Speicherort speichern, auf den Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="cc21a-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Auswählen von Protokolloptionen](images/sdt-7.png)

*<span data-ttu-id="cc21a-213">Abbildung7.</span><span class="sxs-lookup"><span data-stu-id="cc21a-213">Figure 7.</span></span> <span data-ttu-id="cc21a-214">Protokollierungsoption und Paket speichern</span><span class="sxs-lookup"><span data-stu-id="cc21a-214">Log option and save package</span></span>*

## <span data-ttu-id="cc21a-215">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cc21a-215">Next steps</span></span>

- [<span data-ttu-id="cc21a-216">Surface-Diagnosetoolkit für Unternehmen im Desktopmodus verwenden</span><span class="sxs-lookup"><span data-stu-id="cc21a-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="cc21a-217">Verwenden des Surface Diagnostic Toolkit for Business mithilfe von Befehlen</span><span class="sxs-lookup"><span data-stu-id="cc21a-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="cc21a-218">Änderungen und Updates</span><span class="sxs-lookup"><span data-stu-id="cc21a-218">Changes and updates</span></span>

### <span data-ttu-id="cc21a-219">Version 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-219">Version 2.131.139.0</span></span>

<span data-ttu-id="cc21a-220">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cc21a-221">Unterstützung für Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="cc21a-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="cc21a-222">Nahtlose Supporterfahrung auf Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="cc21a-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="cc21a-223">Sicherheitsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="cc21a-223">Security improvements</span></span>
- <span data-ttu-id="cc21a-224">Verbesserungen der inklusiven Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="cc21a-224">Inclusive user experience improvements</span></span>

### <span data-ttu-id="cc21a-225">Version 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-225">Version 2.124.139.0</span></span>

<span data-ttu-id="cc21a-226">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cc21a-227">Nahtlose integrierte Unterstützung</span><span class="sxs-lookup"><span data-stu-id="cc21a-227">Seamless integrated support</span></span>
- <span data-ttu-id="cc21a-228">Speichern aller Testergebnisse</span><span class="sxs-lookup"><span data-stu-id="cc21a-228">Save all test results</span></span>
- <span data-ttu-id="cc21a-229">Überprüfen, ob das Bild benutzerdefinierte erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="cc21a-229">Check if the image is custom created</span></span>
- <span data-ttu-id="cc21a-230">Schließen Sie Warnungen vom Gerätemanager ein</span><span class="sxs-lookup"><span data-stu-id="cc21a-230">Include warnings from device manager</span></span>
- <span data-ttu-id="cc21a-231">Dock Firmware version</span><span class="sxs-lookup"><span data-stu-id="cc21a-231">Dock firmware version</span></span>
- <span data-ttu-id="cc21a-232">Kennzeichnen von Laufwerken als potenzielle Fehler beim Speichertest</span><span class="sxs-lookup"><span data-stu-id="cc21a-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="cc21a-233">Entfernen eines Informationsspeicherlinks</span><span class="sxs-lookup"><span data-stu-id="cc21a-233">Remove store link</span></span> 

### <span data-ttu-id="cc21a-234">Version 2.121.139</span><span class="sxs-lookup"><span data-stu-id="cc21a-234">Version 2.121.139</span></span>
*<span data-ttu-id="cc21a-235">Veröffentlichungsdatum: 31. Juli 2020</span><span class="sxs-lookup"><span data-stu-id="cc21a-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="cc21a-236">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cc21a-237">Nahtlose Supporterfahrung</span><span class="sxs-lookup"><span data-stu-id="cc21a-237">Seamless support experience</span></span>
- <span data-ttu-id="cc21a-238">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cc21a-238">Bug fixes</span></span>

### <span data-ttu-id="cc21a-239">Version 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="cc21a-240">Veröffentlichungsdatum: 11. Mai 2020</span><span class="sxs-lookup"><span data-stu-id="cc21a-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="cc21a-241">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cc21a-242">Möglichkeit, Windows Update zu überspringen, um eine Hardwareprüfung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cc21a-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="cc21a-243">Möglichkeit zum Empfangen von Benachrichtigungen über das neueste Versionsupdate</span><span class="sxs-lookup"><span data-stu-id="cc21a-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="cc21a-244">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="cc21a-244">Surface Go 2</span></span>
- <span data-ttu-id="cc21a-245">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="cc21a-245">Surface Book 3</span></span>
- <span data-ttu-id="cc21a-246">Statusanzeige anzeigen</span><span class="sxs-lookup"><span data-stu-id="cc21a-246">Show progress indicator</span></span>


### <span data-ttu-id="cc21a-247">Version 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="cc21a-248">Veröffentlichungsdatum: 21. Oktober 2019</span><span class="sxs-lookup"><span data-stu-id="cc21a-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="cc21a-249">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cc21a-250">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="cc21a-250">Surface Pro 7</span></span>
- <span data-ttu-id="cc21a-251">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="cc21a-251">Surface Laptop 3</span></span>

### <span data-ttu-id="cc21a-252">Version 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="cc21a-253">Veröffentlichungsdatum: 24. September 2019</span><span class="sxs-lookup"><span data-stu-id="cc21a-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="cc21a-254">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="cc21a-255">Möglichkeit zum Herunterladen von Hardwareberichten.</span><span class="sxs-lookup"><span data-stu-id="cc21a-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="cc21a-256">Möglichkeit, den Microsoft Support direkt über das Tool zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="cc21a-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="cc21a-257">Version 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="cc21a-258">Veröffentlichungsdatum: 24. Juni 2019</span><span class="sxs-lookup"><span data-stu-id="cc21a-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="cc21a-259">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="cc21a-260">Informationen zur Treiberversion, die in Protokollen und Berichten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cc21a-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="cc21a-261">Möglichkeit, Feedback zur App zu geben.</span><span class="sxs-lookup"><span data-stu-id="cc21a-261">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="cc21a-262">Version 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="cc21a-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="cc21a-263">Veröffentlichungsdatum: 26. April 2019</span><span class="sxs-lookup"><span data-stu-id="cc21a-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="cc21a-264">Diese Version des Surface Diagnostic Toolkit for Business bietet Unterstützung für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc21a-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="cc21a-265">Erweiterte Setupoption zum Entsperren von Administratorfunktionen über die Installer-Benutzeroberfläche, ohne dass eine Befehlszeilenkonfiguration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cc21a-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="cc21a-266">Verbesserte Barrierefreiheit.</span><span class="sxs-lookup"><span data-stu-id="cc21a-266">Accessibility improvements.</span></span>
- <span data-ttu-id="cc21a-267">Einstellungen für die Oberflächenhelligkeitssteuerung, die in Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cc21a-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="cc21a-268">Link zur Unterstützung der externen Monitorkompatibilität im Berichtsgenerator.</span><span class="sxs-lookup"><span data-stu-id="cc21a-268">External monitor compatibility support link in report generator.</span></span>
