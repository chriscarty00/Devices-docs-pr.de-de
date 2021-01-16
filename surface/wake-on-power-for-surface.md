---
title: Aktivieren von Wake on Power für Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Beschreibt das Aktivieren und Deaktivieren von Wake on Power für Surface-Geräte.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271559"
---
# <span data-ttu-id="5da3e-104">Wake-on-Power für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="5da3e-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="5da3e-105">Surface-Geräte können ausgeschaltet werden, während Sie sich nicht am Schreibtisch befinden, oder sie können in den Ruhezustand versetzt werden, um die Akkulaufzeit zu sparen.</span><span class="sxs-lookup"><span data-stu-id="5da3e-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="5da3e-106">Um die Verwaltbarkeit dieser Geräte zu verbessern, ermöglicht Wake on Power das automatische Starten kompatibler Surface-Geräte, wenn sie wieder mit der Stromversorgung verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="5da3e-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="5da3e-107">Zum Konfigurieren von Wake on Power können Sie den Surface Enterprise Management Mode (SEMM) entweder über den Surface UEFI Configurator oder den UEFI Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="5da3e-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="5da3e-108">Das Aktivierungsfeature ist auf den folgenden Geräten verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5da3e-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="5da3e-109">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="5da3e-109">Surface Pro 7+</span></span>
- <span data-ttu-id="5da3e-110">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="5da3e-110">Surface Book 3</span></span>
- <span data-ttu-id="5da3e-111">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="5da3e-111">Surface Pro 7</span></span>
- <span data-ttu-id="5da3e-112">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="5da3e-112">Surface Laptop 3</span></span>
- <span data-ttu-id="5da3e-113">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="5da3e-113">Surface Laptop Go</span></span>
- <span data-ttu-id="5da3e-114">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="5da3e-114">Surface Pro X</span></span> 


## <span data-ttu-id="5da3e-115">Übersicht und Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5da3e-115">Overview and prerequisites</span></span>

<span data-ttu-id="5da3e-116">Mit dem Surface -UEFI-Konfigurator können Sie einzelne UEFI-Einstellungen in einem Windows Installer-MSI-Paket für die Verteilung auf Zielgeräte speichern.</span><span class="sxs-lookup"><span data-stu-id="5da3e-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="5da3e-117">In diesem Artikel wird davon ausgegangen, dass Sie mit der Verwendung von SEMM wissen.</span><span class="sxs-lookup"><span data-stu-id="5da3e-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="5da3e-118">Weitere Informationen finden Sie in der [Dokumentation zum Surface Enterprise Management Mode (SEMM).](surface-enterprise-management-mode.md)</span><span class="sxs-lookup"><span data-stu-id="5da3e-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="5da3e-119">So aktivieren Sie Wake on Power</span><span class="sxs-lookup"><span data-stu-id="5da3e-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="5da3e-120">Laden Sie die neueste Version von [Surface UEFI Configurator herunter.](https://www.microsoft.com/download/confirmation.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="5da3e-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="5da3e-121">Melden Sie sich als Administrator bei Ihrem Surface-Gerät an, öffnen Sie **den Surface UEFI-Konfigurator,** wählen Sie **"Surface Devices"** aus, und wählen Sie dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="5da3e-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Wählen Sie "Surface-Geräte" und "Weiter" aus.":::
3.  <span data-ttu-id="5da3e-123">Wählen **Sie "Start"** und dann **"Erstellen"** unter **"Konfigurationspaket" aus.**</span><span class="sxs-lookup"><span data-stu-id="5da3e-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Wählen Sie "Konfigurationspaket erstellen" aus.":::
4.  <span data-ttu-id="5da3e-125">Wählen **Sie Zertifikatschutz**aus, und fügen Sie die ZERTIFIKAT-PFX-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5da3e-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="5da3e-126">Geben Sie Ihr Kennwort ein, wählen **Sie "Weiter",** **fügen**Sie gegebenenfalls Den Kennwortschutz hinzu, und wählen Sie dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="5da3e-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="5da3e-127">Wählen Sie **auf der Seite "Wählen Sie aus,** welchen Surface-Typ Sie als Ziel verwenden möchten" ihre Zielgeräte aus.</span><span class="sxs-lookup"><span data-stu-id="5da3e-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="5da3e-128">Wählen Sie beispielsweise Surface Pro **7 aus.**</span><span class="sxs-lookup"><span data-stu-id="5da3e-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="5da3e-129">On the **Advanced Features** page, select Wake **on Power,** set the feature to **On**, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="5da3e-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Wählen Sie "Aktivierung aktivieren" aus, und legen Sie es auf "Ein" festgelegt."::: 
8.  <span data-ttu-id="5da3e-131">Wählen Sie **auf der Seite "Erfolgreich"** die Option **"Ende" aus.**</span><span class="sxs-lookup"><span data-stu-id="5da3e-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5da3e-132">Wenn Sie zum ersten Mal Einstellungen für Ihr Gerät bereitstellen, werden Sie aufgefordert, auch die letzten beiden Zeichen des Zertifikatfingerabdrucks ein.</span><span class="sxs-lookup"><span data-stu-id="5da3e-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="5da3e-133">Speichern Sie das MSI-Paket.</span><span class="sxs-lookup"><span data-stu-id="5da3e-133">Save the .msi package.</span></span> 

## <span data-ttu-id="5da3e-134">Anwenden des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="5da3e-134">Apply the MSI package</span></span> 

<span data-ttu-id="5da3e-135">Sie können das MSI-Paket mithilfe von Softwareverteilungstools wie Microsoft Endpoint Configuration Manager auf Geräte in Ihrem Netzwerk anwenden.</span><span class="sxs-lookup"><span data-stu-id="5da3e-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="5da3e-136">Dieses Verfahren umfasst Schritte zum Installieren des Pakets auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5da3e-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="5da3e-137">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten den vollständigen Pfad der MSI-Datei ein, um das .msi-Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5da3e-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="5da3e-138">Wählen Sie **im Dialogfeld "Warnung"** die Option **"OK"** aus, oder deaktivieren Sie BitLocker.</span><span class="sxs-lookup"><span data-stu-id="5da3e-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Wählen Sie OK aus, oder deaktivieren Sie BitLocker.":::
3.  <span data-ttu-id="5da3e-140">Wählen Sie auf der Willkommensseite **"Weiter"** aus, um das Paket ausführen und die neu konfigurierte Einstellung für UEFI anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="5da3e-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Wählen Sie auf der Willkommensseite "Weiter" aus.":::
4.  <span data-ttu-id="5da3e-142">Starten Sie Das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="5da3e-142">Restart your device.</span></span> 

<span data-ttu-id="5da3e-143">Wake on Power ist jetzt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5da3e-143">Wake on Power is now configured.</span></span> <span data-ttu-id="5da3e-144">Um die Einstellungen zu testen, schalten Sie Ihr Gerät aus, trennen Sie das Netzgerät, und verbinden Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="5da3e-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="5da3e-145">Das Gerät sollte automatisch gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="5da3e-145">The device should start automatically.</span></span> 

## <span data-ttu-id="5da3e-146">Verweise</span><span class="sxs-lookup"><span data-stu-id="5da3e-146">References</span></span>

<span data-ttu-id="5da3e-147">Weitere Informationen finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="5da3e-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="5da3e-148">Surface Enterprise Management-Modus</span><span class="sxs-lookup"><span data-stu-id="5da3e-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="5da3e-149">Wake-on-LAN für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="5da3e-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="5da3e-150">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="5da3e-150">Still need help?</span></span> <span data-ttu-id="5da3e-151">Wechseln Sie zur [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5da3e-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>