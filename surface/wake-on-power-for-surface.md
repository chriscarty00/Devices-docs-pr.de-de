---
title: Aktivieren von Wake-on-Power für Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Beschreibt, wie Sie Wake-on-Power für Surface-Geräte aktivieren und deaktivieren.
keywords: Update, bereitstellen, Treiber, wol, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903394"
---
# <span data-ttu-id="6662d-104">Wake-on-Power für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="6662d-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="6662d-105">Surface-Geräte können ausgeschaltet werden, wenn Sie nicht an Ihrem Schreibtisch sind, oder Sie können den Ruhemodus aktivieren, um die Akkulaufzeit zu sparen.</span><span class="sxs-lookup"><span data-stu-id="6662d-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="6662d-106">Um die Verwaltbarkeit dieser Geräte zu verbessern, ermöglicht Wake on Power das automatische Starten von kompatiblen Surface-Geräten, wenn Sie wieder an die Stromversorgung angeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6662d-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="6662d-107">Um Wake-on-Power zu konfigurieren, können Sie den Surface Enterprise Management Mode (Semm) entweder über den Surface UEFI-Konfigurator oder den UEFI-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="6662d-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="6662d-108">Das Feature Wake-on-Power steht auf den folgenden Geräten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6662d-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="6662d-109">DGM-Buch 3</span><span class="sxs-lookup"><span data-stu-id="6662d-109">Surface Book 3</span></span>
- <span data-ttu-id="6662d-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="6662d-110">Surface Pro 7</span></span>
- <span data-ttu-id="6662d-111">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="6662d-111">Surface Laptop 3</span></span>
- <span data-ttu-id="6662d-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="6662d-112">Surface Pro X</span></span> 

## <span data-ttu-id="6662d-113">Übersicht und Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6662d-113">Overview and prerequisites</span></span>

<span data-ttu-id="6662d-114">Mit dem Surface UEFI Configurator können Sie einzelne UEFI-Einstellungen in einem Windows Installer. MSI-Paket für die Verteilung an Zielgeräte speichern.</span><span class="sxs-lookup"><span data-stu-id="6662d-114">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="6662d-115">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie Semm verwenden.</span><span class="sxs-lookup"><span data-stu-id="6662d-115">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="6662d-116">Weitere Informationen finden Sie unter Dokumentation zu [Surface Enterprise Management Mode (Semm)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="6662d-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="6662d-117">So aktivieren Sie Wake-on-Power</span><span class="sxs-lookup"><span data-stu-id="6662d-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="6662d-118">Laden Sie die neueste Version des [Surface UEFI-Konfigurators](https://www.microsoft.com/download/confirmation.aspx?id=46703)herunter.</span><span class="sxs-lookup"><span data-stu-id="6662d-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="6662d-119">Registrieren Sie sich als Administrator bei Ihrem Surface-Gerät, öffnen Sie **Surface UEFI Configurator**, wählen Sie **Surface Devices**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-119">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Wählen Sie Surface Devices aus, und wählen Sie weiter aus.":::
3.  <span data-ttu-id="6662d-121">Wählen Sie **Start**aus, und wählen Sie dann unter **Konfigurationspaket** **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-121">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Wählen Sie Konfigurationspaket erstellen aus.":::
4.  <span data-ttu-id="6662d-123">Wählen Sie **Zertifikatschutz**aus, und fügen Sie die Datei Certificate. pfx hinzu.</span><span class="sxs-lookup"><span data-stu-id="6662d-123">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="6662d-124">Geben Sie Ihr Kennwort ein, wählen Sie **weiter**aus, fügen Sie nach Bedarf **Kennwortschutz**hinzu, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-124">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="6662d-125">Wählen Sie auf der Seite **Wählen Sie den DGM-Typ aus, den Sie als Ziel auswählen möchten** die gewünschten Zielgeräte aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-125">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="6662d-126">Wählen Sie beispielsweise **Surface pro 7**aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-126">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="6662d-127">Wählen Sie auf der Seite **Advanced Features** die Option **Wake on Power**aus, legen Sie das Feature auf **ein**, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-127">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Wählen Sie bei Stromversorgung aktivieren aus, und legen Sie auf ein."::: 
8.  <span data-ttu-id="6662d-129">Wählen Sie auf der Seite **erfolgreich** die Option **Ende**aus.</span><span class="sxs-lookup"><span data-stu-id="6662d-129">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6662d-130">Wenn Sie zum ersten Mal Einstellungen für Ihr Gerät bereitstellen, werden Sie aufgefordert, auch die letzten beiden Zeichen des Zertifikat Fingerabdrucks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6662d-130">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="6662d-131">Speichern Sie das MSI-Paket.</span><span class="sxs-lookup"><span data-stu-id="6662d-131">Save the .msi package.</span></span> 

## <span data-ttu-id="6662d-132">Anwenden des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="6662d-132">Apply the MSI package</span></span> 

<span data-ttu-id="6662d-133">Sie können das MSI-Paket auf Geräte im gesamten Netzwerk anwenden, indem Sie Softwareverteilungstools wie Microsoft Endpoint Configuration Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="6662d-133">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="6662d-134">Dieses Verfahren umfasst Schritte zum Installieren des Pakets auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="6662d-134">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="6662d-135">Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten den vollständigen Pfad der MSI-Datei ein, um das MSI-Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6662d-135">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="6662d-136">Wählen Sie im Dialogfeld **Warnung** die Option **OK** aus, oder deaktivieren Sie BitLocker, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="6662d-136">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Wählen Sie OK aus, oder deaktivieren Sie BitLocker entsprechend.":::
3.  <span data-ttu-id="6662d-138">Wählen Sie auf der Seite Willkommen die Option **weiter** aus, um das Paket auszuführen und die neu konfigurierte UEFI-Einstellung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6662d-138">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Klicken Sie auf der Seite Willkommen auf Weiter.":::
4.  <span data-ttu-id="6662d-140">Starten Sie Ihr Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="6662d-140">Restart your device.</span></span> 

<span data-ttu-id="6662d-141">Wake-on-Power ist jetzt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6662d-141">Wake on Power is now configured.</span></span> <span data-ttu-id="6662d-142">Wenn Sie die Einstellungen testen möchten, schalten Sie Ihr Gerät aus, trennen Sie die Stromversorgung, und schließen Sie dann die Verbindung wieder an.</span><span class="sxs-lookup"><span data-stu-id="6662d-142">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="6662d-143">Das Gerät sollte automatisch gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="6662d-143">The device should start automatically.</span></span> 

## <span data-ttu-id="6662d-144">Verweise</span><span class="sxs-lookup"><span data-stu-id="6662d-144">References</span></span>

<span data-ttu-id="6662d-145">Weitere Informationen finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="6662d-145">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="6662d-146">Surface Enterprise Management-Modus</span><span class="sxs-lookup"><span data-stu-id="6662d-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="6662d-147">Wake-on-LAN für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="6662d-147">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="6662d-148">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="6662d-148">Still need help?</span></span> <span data-ttu-id="6662d-149">Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6662d-149">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>