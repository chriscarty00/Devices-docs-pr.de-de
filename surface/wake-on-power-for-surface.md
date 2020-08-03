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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903005"
---
# <span data-ttu-id="07a0c-104">Wake-on-Power für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="07a0c-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="07a0c-105">Surface-Geräte können ausgeschaltet werden, wenn Sie sich nicht am Schreibtisch befinden oder den Ruhemodus einstellen, um Batterie zu sparen.</span><span class="sxs-lookup"><span data-stu-id="07a0c-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="07a0c-106">Um die Verwaltbarkeit dieser Geräte zu verbessern, ermöglicht Wake on Power das automatische Starten von kompatiblen Surface-Geräten, wenn die Verbindung mit dem Stromnetz wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="07a0c-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="07a0c-107">Die Konfiguration von Wake-on-Power erfordert die Verwendung des Surface Enterprise Management Mode (Semm) entweder über den Surface UEFI-Konfigurator oder den UEFI-Manager.</span><span class="sxs-lookup"><span data-stu-id="07a0c-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="07a0c-108">Wake-on-Power ist eine Funktion, die auf den folgenden Geräten zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="07a0c-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="07a0c-109">DGM-Buch 3</span><span class="sxs-lookup"><span data-stu-id="07a0c-109">Surface Book 3</span></span>
- <span data-ttu-id="07a0c-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="07a0c-110">Surface Pro 7</span></span>
- <span data-ttu-id="07a0c-111">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="07a0c-111">Surface Laptop 3</span></span>
- <span data-ttu-id="07a0c-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="07a0c-112">Surface Pro X</span></span> 

## <span data-ttu-id="07a0c-113">Übersicht und Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="07a0c-113">Overview and prerequisites</span></span>

<span data-ttu-id="07a0c-114">Sie können den Surface UEFI-Konfigurator verwenden, um einzelne UEFI-Einstellungen zu konfigurieren, die in einem Windows Installer. MSI-Paket für die Verteilung an Zielgeräte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="07a0c-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="07a0c-115">In diesem Artikel wird davon ausgegangen, dass Sie mit der Verwendung von Semm vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="07a0c-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="07a0c-116">Weitere Informationen finden Sie unter Dokumentation zu [Surface Enterprise Management Mode (Semm)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="07a0c-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="07a0c-117">So aktivieren Sie Wake-on-Power</span><span class="sxs-lookup"><span data-stu-id="07a0c-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="07a0c-118">Laden Sie die neueste Version des [Surface UEFI-Konfigurators](https://www.microsoft.com/download/confirmation.aspx?id=46703)herunter.</span><span class="sxs-lookup"><span data-stu-id="07a0c-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="07a0c-119">Registrieren Sie sich als Administrator bei Ihrem Surface-Gerät, öffnen Sie **Surface UEFI Configurator**, wählen Sie **Surface Devices**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Wählen Sie Surface Devices aus, und wählen Sie weiter aus.":::
3.  <span data-ttu-id="07a0c-121">Wählen Sie **Start** aus, und klicken Sie dann unter **Konfigurationspaket** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="07a0c-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Wählen Sie Konfigurationspaket erstellen aus.":::
4.  <span data-ttu-id="07a0c-123">Wählen Sie **Zertifikatschutz** aus, und fügen Sie die Datei Certificate. pfx hinzu.</span><span class="sxs-lookup"><span data-stu-id="07a0c-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="07a0c-124">Nachdem Sie Ihr Kennwort eingegeben haben, wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="07a0c-125">Fügen Sie nach Bedarf **Kennwortschutz**hinzu, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="07a0c-126">Wählen Sie auf der Seite **Wählen Sie den DGM-Typ aus, den Sie als Ziel auswählen möchten** die gewünschten Zielgeräte aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="07a0c-127">Beispiel: **Surface pro 7**.</span><span class="sxs-lookup"><span data-stu-id="07a0c-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="07a0c-128">Wählen Sie auf der Seite **Erweiterte Features** die Option **bei Stromversorgung** aktivieren und auf **ein**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="07a0c-129">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Wählen Sie bei Stromversorgung aktivieren aus, und legen Sie auf ein."::: 
7.  <span data-ttu-id="07a0c-131">Wählen Sie auf der Seite **erfolgreich** die Option **Ende**aus.</span><span class="sxs-lookup"><span data-stu-id="07a0c-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="07a0c-132">Wenn Sie zum ersten Mal Einstellungen für Ihr Gerät bereitstellen, werden Sie aufgefordert, die letzten beiden Zeichen des Zertifikat Fingerabdrucks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="07a0c-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="07a0c-133">Speichern Sie das MSI-Paket.</span><span class="sxs-lookup"><span data-stu-id="07a0c-133">Save the .msi package.</span></span> 

## <span data-ttu-id="07a0c-134">Anwenden des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="07a0c-134">Apply the MSI package</span></span> 

<span data-ttu-id="07a0c-135">Sie können das MSI-Paket auf Geräte in Ihrem Netzwerk mithilfe von Softwareverteilungstools wie Microsoft Endpoint Configuration Manager anwenden.</span><span class="sxs-lookup"><span data-stu-id="07a0c-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="07a0c-136">Dieses Verfahren enthält die Schritte zum Installieren des Pakets auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="07a0c-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="07a0c-137">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den vollständigen Pfad der MSI-Datei ein, um das MSI-Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="07a0c-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="07a0c-138">Wählen Sie im Dialogfeld **Warnung** die Option **OK** aus, oder deaktivieren Sie BitLocker entsprechend.</span><span class="sxs-lookup"><span data-stu-id="07a0c-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Wählen Sie OK aus, oder deaktivieren Sie BitLocker entsprechend.":::
3.  <span data-ttu-id="07a0c-140">Wählen Sie auf der Seite Willkommen die Option **weiter** aus, um das Paket auszuführen und die neu konfigurierte UEFI-Einstellung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="07a0c-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Klicken Sie auf der Seite Willkommen auf Weiter.":::
4.  <span data-ttu-id="07a0c-142">Starten Sie Ihr Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="07a0c-142">Restart your device.</span></span> 

<span data-ttu-id="07a0c-143">Wake-on-Power ist jetzt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="07a0c-143">Wake on Power is now configured.</span></span> <span data-ttu-id="07a0c-144">Wenn Sie die Einstellung testen möchten, schalten Sie Ihr Gerät aus, trennen Sie die Stromversorgung, und schließen Sie dann die Verbindung wieder an.</span><span class="sxs-lookup"><span data-stu-id="07a0c-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="07a0c-145">Das Gerät wird automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="07a0c-145">The device will start automatically.</span></span> 

## <span data-ttu-id="07a0c-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07a0c-146">More information</span></span>

<span data-ttu-id="07a0c-147">Weitere Informationen finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="07a0c-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="07a0c-148">Surface Enterprise Management-Modus</span><span class="sxs-lookup"><span data-stu-id="07a0c-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="07a0c-149">Wake-on-LAN für Surface-Geräte</span><span class="sxs-lookup"><span data-stu-id="07a0c-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="07a0c-150">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="07a0c-150">Still need help?</span></span> <span data-ttu-id="07a0c-151">Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="07a0c-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>