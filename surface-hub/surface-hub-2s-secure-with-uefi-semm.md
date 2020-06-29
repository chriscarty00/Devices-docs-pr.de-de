---
title: Sichern und Verwalten von Surface Hub 2S mit Semm
description: Weitere Informationen zum Sichern des Surface Hub 2S mit Semm.
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832971"
---
# <span data-ttu-id="057a3-104">Sichern und verwalten von Surface Hub 2S mit SEMM und UEFI</span><span class="sxs-lookup"><span data-stu-id="057a3-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="057a3-105">Neu in Surface Hub 2S können Sie Semm verwenden, um die UEFI-Einstellung des Geräts zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="057a3-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="057a3-106">Verwenden Sie den Microsoft Surface UEFI-Konfigurator, um die folgenden Komponenten zu steuern:</span><span class="sxs-lookup"><span data-stu-id="057a3-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="057a3-107">Kabelgebundenes LAN</span><span class="sxs-lookup"><span data-stu-id="057a3-107">Wired LAN</span></span>
- <span data-ttu-id="057a3-108">Kameras</span><span class="sxs-lookup"><span data-stu-id="057a3-108">Cameras</span></span>
- <span data-ttu-id="057a3-109">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="057a3-109">Bluetooth</span></span>
- <span data-ttu-id="057a3-110">WLAN</span><span class="sxs-lookup"><span data-stu-id="057a3-110">Wi-Fi</span></span>
- <span data-ttu-id="057a3-111">Anwesenheitssensor</span><span class="sxs-lookup"><span data-stu-id="057a3-111">Occupancy sensor</span></span>

<span data-ttu-id="057a3-112">Verwenden Sie den Microsoft Surface UEFI-Konfigurator, um die folgenden UEFI-Einstellungen zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="057a3-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="057a3-113">Start</span><span class="sxs-lookup"><span data-stu-id="057a3-113">Boot</span></span>

    - <span data-ttu-id="057a3-114">IPv6 für PXE-Start</span><span class="sxs-lookup"><span data-stu-id="057a3-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="057a3-115">Alternativer Start</span><span class="sxs-lookup"><span data-stu-id="057a3-115">Alternate Boot</span></span>
    - <span data-ttu-id="057a3-116">Sperre дер Startreihenfolge</span><span class="sxs-lookup"><span data-stu-id="057a3-116">Boot Order Lock</span></span>
    - <span data-ttu-id="057a3-117">USB-Start</span><span class="sxs-lookup"><span data-stu-id="057a3-117">USB Boot</span></span>
- <span data-ttu-id="057a3-118">UEFI-Startseite</span><span class="sxs-lookup"><span data-stu-id="057a3-118">UEFI Front Page</span></span>

    - <span data-ttu-id="057a3-119">Geräte</span><span class="sxs-lookup"><span data-stu-id="057a3-119">Devices</span></span>
    - <span data-ttu-id="057a3-120">Start</span><span class="sxs-lookup"><span data-stu-id="057a3-120">Boot</span></span>
    - <span data-ttu-id="057a3-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="057a3-121">Date/Time</span></span>

## <span data-ttu-id="057a3-122">Erstellen eines UEFI-Konfigurations Bilds</span><span class="sxs-lookup"><span data-stu-id="057a3-122">Create UEFI configuration image</span></span>

<span data-ttu-id="057a3-123">Im Gegensatz zu anderen Surface-Geräten können Sie keine MSI-Datei oder ein Win PE-Bild verwenden, um diese Einstellungen auf Surface Hub 2S anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="057a3-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="057a3-124">Stattdessen müssen Sie ein USB-Bild erstellen, das in das Gerät geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="057a3-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="057a3-125">Laden Sie die neueste Version des Microsoft Surface UEFI-Konfigurators auf der Seite [Surface Tools für IT](https://www.microsoft.com/download/details.aspx?id=46703) im Microsoft Download Center herunter, und installieren Sie die aktuelle Version des Microsoft Surface UEFI-Konfigurators, um ein DGM-UEFI-Konfigurationsbild zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="057a3-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="057a3-126">Weitere Informationen zur Verwendung von UEFI und Semm finden Sie unter [Microsoft Surface Enterprise-Verwaltungsmodus](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span><span class="sxs-lookup"><span data-stu-id="057a3-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="057a3-127">So konfigurieren Sie UEFI auf Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="057a3-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="057a3-128">Starten Sie den UEFI-Konfigurator, und wählen Sie auf dem ersten Bildschirm **Konfigurationspaket**aus.</span><span class="sxs-lookup"><span data-stu-id="057a3-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* Starten Sie den UEFI-Konfigurator und wählen Sie das Konfigurationspaket \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="057a3-130">Um das Zertifikat zu Ihrem Paket hinzuzufügen, müssen Sie über ein gültiges Zertifikat mit dem privaten Schlüssel in einem PFX-Dateiformat verfügen, um das Paket zu signieren und zu schützen.</span><span class="sxs-lookup"><span data-stu-id="057a3-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="057a3-131">Wählen Sie **+ Zertifikatschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="057a3-131">Select **+ Certificate Protection.**</span></span> <br>
![\* Wählen Sie + Zertifikatschutz \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="057a3-133">Geben Sie das Kennwort für den privaten Schlüssel des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="057a3-133">Enter the certificate’s private key’s password.</span></span><br>
![\* Geben Sie das Kennwort des privaten Schlüssels des Zertifikats ein \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="057a3-135">Nachdem Sie den privaten Schlüssel importiert haben, fahren Sie mit dem Erstellen des Pakets fort.</span><span class="sxs-lookup"><span data-stu-id="057a3-135">After importing the private key, continue creating the package.</span></span><br>
![\* Fortsetzen des Erstellens des Pakets \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="057a3-137">Wählen Sie **Hub** und **Surface Hub 2S** als Ziel für das UEFI-Konfigurationspaket aus.</span><span class="sxs-lookup"><span data-stu-id="057a3-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* Wählen Sie Hub und Surface Hub 2S als Ziel für das UEFI-Konfigurationspaket \* aus.](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="057a3-139">Wählen Sie die Komponenten und Einstellungen aus, die Sie auf Surface Hub 2S aktivieren oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="057a3-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* Wählen Sie die Komponenten und Einstellungen aus, die Sie aktivieren oder deaktivieren möchten \*](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="057a3-141">Verwenden Sie die USB-Option, um die Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="057a3-141">Use the USB option to export the file.</span></span><br>
![\* Verwenden Sie die USB-Option, um die Datei zu exportieren \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="057a3-143">Legen Sie das USB-Laufwerk ein, das Sie für dieses Paket verwenden möchten, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="057a3-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="057a3-144">Das USB-Laufwerk wird formatiert, und Sie verlieren alle Informationen, die Sie dazu haben.</span><span class="sxs-lookup"><span data-stu-id="057a3-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* Einfügen und auswählen des USB-Laufwerks für Ihr Paket \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="057a3-146">Nach erfolgreicher Erstellung des Pakets werden im Konfigurator die letzten beiden Zeichen des Fingerabdrucks des Zertifikats angezeigt.</span><span class="sxs-lookup"><span data-stu-id="057a3-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="057a3-147">Sie benötigen diese Zeichen beim Importieren in die Konfiguration in Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="057a3-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* Erfolgreiche Konfiguration des Pakets \*](images/sh2-uefi10.png) <br>

## <span data-ttu-id="057a3-149">So starten Sie in UEFI</span><span class="sxs-lookup"><span data-stu-id="057a3-149">To boot into UEFI</span></span>

<span data-ttu-id="057a3-150">Deaktivieren Sie Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="057a3-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="057a3-151">Drücken Sie die **Lautstärke** Taste und halten Sie sie gedrückt, und drücken Sie die **Power** -Taste.</span><span class="sxs-lookup"><span data-stu-id="057a3-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="057a3-152">Halten Sie die Lautstärketaste gedrückt, bis das UEFI-Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="057a3-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>
