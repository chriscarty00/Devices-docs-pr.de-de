---
title: Zurücksetzen und Wiederherstellung für Surface Hub 2S
description: Erfahren Sie, wie Sie Surface Hub 2S wiederherstellen und zurücksetzen.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304808"
---
# <span data-ttu-id="ade67-104">Zurücksetzen und Wiederherstellung für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="ade67-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="ade67-105">Wenn Probleme mit Surface Hub 2S auftreten, können Sie das Gerät auf die Werkseinstellungen zurücksetzen oder mithilfe eines USB-Laufwerks wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="ade67-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="ade67-106">Melden Sie sich zunächst bei Surface Hub 2S mit Administratoranmeldeinformationen an, öffnen Sie die **App** "Einstellungen", wählen Sie **"&** Aktualisieren" und dann "Wiederherstellung" **aus.**</span><span class="sxs-lookup"><span data-stu-id="ade67-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="ade67-107">Setzen Sie das Gerät zurück</span><span class="sxs-lookup"><span data-stu-id="ade67-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ade67-108">Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, da Sie später dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="ade67-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="ade67-109">Weitere Informationen finden Sie unter ["Speichern des BitLocker-Schlüssels".](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="ade67-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="ade67-110">Um das Gerät zurückzusetzen, wählen Sie **"Erste Schritte" aus.**</span><span class="sxs-lookup"><span data-stu-id="ade67-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="ade67-111">Wenn das **Fenster "Bereit zum Zurücksetzen" dieses Gerätefensters** angezeigt wird, wählen Sie **"Zurücksetzen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ade67-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="ade67-112">Wenn der Hub mit der Wiederherstellungspartition neu startet, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ade67-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="ade67-113">Wenn Sie diese Eingabeaufforderung überspringen, kann die Zurücksetzung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="ade67-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="ade67-114">Sobald Sie den Schlüssel "BitLocker" eingeben, installiert der Hub das Betriebssystem von der Wiederherstellungspartition neu.</span><span class="sxs-lookup"><span data-stu-id="ade67-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="ade67-115">Dies kann bis zu einer Stunde dauern.</span><span class="sxs-lookup"><span data-stu-id="ade67-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="ade67-116">Führen Sie zum Neukonfigurieren des Geräts das erste Setupprogramm aus.</span><span class="sxs-lookup"><span data-stu-id="ade67-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="ade67-117">Wenn Sie das Gerät mithilfe von Microsoft Intune oder einer anderen Lösung für die Verwaltung mobiler Geräte verwalten, ziehen Sie den vorherigen Eintrag zurück, löschen Sie ihn, und registrieren Sie das neue Gerät erneut.</span><span class="sxs-lookup"><span data-stu-id="ade67-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="ade67-118">Weitere Informationen finden Sie unter [Entfernen von Geräten mithilfe von Zurückziehen,](https://docs.microsoft.com/intune/devices-wipe)Zurückziehen oder manuellen Entfernen der Registrierung des Geräts.</span><span class="sxs-lookup"><span data-stu-id="ade67-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Zurücksetzen und Wiederherstellung für Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="ade67-120">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="ade67-120">Figure 1.</span></span> <span data-ttu-id="ade67-121">Zurücksetzen und Wiederherstellung für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="ade67-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="ade67-122">Wiederherstellen von Surface Hub 2S mithilfe eines USB-Wiederherstellungslaufwerks</span><span class="sxs-lookup"><span data-stu-id="ade67-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="ade67-123">Neu in Surface Hub 2S: Sie können das Gerät jetzt mithilfe eines Wiederherstellungsabbilds neu installieren.</span><span class="sxs-lookup"><span data-stu-id="ade67-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="ade67-124">Wiederherstellung von einem USB-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="ade67-124">Recovery from a USB drive</span></span>

<span data-ttu-id="ade67-125">Mit Surface Hub 2S können Sie das Gerät mithilfe eines Wiederherstellungsabbilds neu installieren.</span><span class="sxs-lookup"><span data-stu-id="ade67-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="ade67-126">Dadurch können Sie das Gerät in den Werkseinstellungen neu installieren, wenn Sie den BitLocker-Schlüssel verloren haben oder wenn Sie nicht mehr über Administratoranmeldeinformationen für die Einstellungs-App verfügen.</span><span class="sxs-lookup"><span data-stu-id="ade67-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="ade67-127">Verwenden Sie ein USB 3.0-Laufwerk mit 8 GB oder 16 GB Speicher, formatiert als FAT32.</span><span class="sxs-lookup"><span data-stu-id="ade67-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="ade67-128">Laden Sie von einem separaten PC das Wiederherstellungsimage der ZIP-Datei von der [Surface -Wiederherstellungswebsite](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) herunter, und kehren Sie dann zu diesen Anweisungen zurück.</span><span class="sxs-lookup"><span data-stu-id="ade67-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="ade67-129">Entpacken Sie die heruntergeladene Datei im Stammverzeichnis des USB-Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="ade67-129">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="ade67-130">Schließen Sie das #A0 an einen beliebigen USB-C- oder #A1 auf Surface Hub 2S an.</span><span class="sxs-lookup"><span data-stu-id="ade67-130">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="ade67-131">Deaktivieren Sie das Gerät:</span><span class="sxs-lookup"><span data-stu-id="ade67-131">Turn off the device:</span></span>

   1. <span data-ttu-id="ade67-132">Drücken Sie beim Drücken der Taste "Lautstärke nach unten" die Ein-/Aus-Taste.</span><span class="sxs-lookup"><span data-stu-id="ade67-132">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="ade67-133">Drücken Sie weiterhin beide Tasten, bis das Windows-Logo angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ade67-133">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="ade67-134">Lassen Sie die Ein/Aus-Taste los, halten Sie jedoch die Schaltfläche "Volume down" gedrückt, bis die Installation der Benutzeroberfläche beginnt.</span><span class="sxs-lookup"><span data-stu-id="ade67-134">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Verwenden der Tasten "Volume down" und "Power", um die Wiederherstellung zu initiieren*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="ade67-136">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="ade67-136">Figure 2.</span></span> <span data-ttu-id="ade67-137">Lautstärke- und Netztasten</span><span class="sxs-lookup"><span data-stu-id="ade67-137">Volume and Power buttons</span></span>*

1. <span data-ttu-id="ade67-138">Wählen Sie auf dem Sprachauswahlbildschirm die Anzeigesprache für Surface Hub 2S aus.</span><span class="sxs-lookup"><span data-stu-id="ade67-138">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="ade67-139">Wählen **Sie "Von einem Laufwerk wiederherstellen"** aus, und **bereinigen**Sie das Laufwerk vollständig, und wählen Sie dann **"Wiederherstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ade67-139">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="ade67-140">Wenn Sie zur Eingabe eines BitLocker-Schlüssels aufgefordert werden, wählen Sie **"Dieses Laufwerk überspringen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ade67-140">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="ade67-141">Surface Hub 2S wird mehrmals neu gestartet und benötigt ca. 30 Minuten, um den Wiederherstellungsvorgang abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="ade67-141">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="ade67-142">Entfernen Sie beim ersten Einrichten des Bildschirms das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="ade67-142">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="ade67-143">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="ade67-143">Contact Support</span></span>

<span data-ttu-id="ade67-144">Wenn Sie Fragen haben oder Hilfe benötigen, können [Sie eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="ade67-144">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
