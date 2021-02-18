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
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342975"
---
# <span data-ttu-id="d2880-104">Zurücksetzen und Wiederherstellung für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="d2880-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="d2880-105">Wenn Probleme mit Surface Hub 2S auftreten, können Sie das Gerät auf die Werkseinstellungen zurücksetzen oder mithilfe eines USB-Laufwerks wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d2880-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="d2880-106">Melden Sie sich zunächst bei Surface Hub 2S mit Administratoranmeldeinformationen an, öffnen Sie die **App** "Einstellungen", wählen Sie **"&** Aktualisieren" und dann "Wiederherstellung" **aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="d2880-107">Setzen Sie das Gerät zurück</span><span class="sxs-lookup"><span data-stu-id="d2880-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d2880-108">Stellen Sie sicher, dass Ihr BitLocker-Schlüssel verfügbar ist, bevor Sie das Gerät zurücksetzen, da Sie später dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d2880-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="d2880-109">Weitere Informationen finden Sie unter ["Speichern des BitLocker-Schlüssels".](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="d2880-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="d2880-110">Um das Gerät zurückzusetzen, wählen Sie **"Erste Schritte" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="d2880-111">Wenn das **Fenster "Bereit zum Zurücksetzen" dieses Gerätefensters** angezeigt wird, wählen Sie **"Zurücksetzen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="d2880-112">Wenn der Hub mit der Wiederherstellungspartition neu startet, werden Sie zur Eingabe des BitLocker-Schlüssels aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d2880-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="d2880-113">Wenn Sie diese Eingabeaufforderung überspringen, kann die Zurücksetzung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="d2880-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="d2880-114">Sobald Sie den Schlüssel "BitLocker" eingeben, installiert der Hub das Betriebssystem von der Wiederherstellungspartition neu.</span><span class="sxs-lookup"><span data-stu-id="d2880-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="d2880-115">Dies kann bis zu einer Stunde dauern.</span><span class="sxs-lookup"><span data-stu-id="d2880-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="d2880-116">Führen Sie zum Neukonfigurieren des Geräts das erste Setupprogramm aus.</span><span class="sxs-lookup"><span data-stu-id="d2880-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="d2880-117">Wenn Sie das Gerät mithilfe von Microsoft Intune oder einer anderen Verwaltungslösung für mobile Geräte verwalten, ziehen Sie den vorherigen Eintrag zurück, löschen Sie ihn, und registrieren Sie das neue Gerät erneut.</span><span class="sxs-lookup"><span data-stu-id="d2880-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="d2880-118">Weitere Informationen finden Sie unter ["Entfernen von Geräten mithilfe von Wipe", "Zurückziehen" oder "Manuelles](https://docs.microsoft.com/intune/devices-wipe)Entfernen der Registrierung des Geräts".</span><span class="sxs-lookup"><span data-stu-id="d2880-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Zurücksetzen und Wiederherstellung für Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="d2880-120">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="d2880-120">Figure 1.</span></span> <span data-ttu-id="d2880-121">Zurücksetzen und Wiederherstellung für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="d2880-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="d2880-122">Wiederherstellen von Surface Hub 2S mithilfe eines USB-Wiederherstellungslaufwerks</span><span class="sxs-lookup"><span data-stu-id="d2880-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="d2880-123">Neu in Surface Hub 2S: Sie können das Gerät jetzt mithilfe eines Wiederherstellungsabbilds neu installieren.</span><span class="sxs-lookup"><span data-stu-id="d2880-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="d2880-124">Wiederherstellung von einem USB-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="d2880-124">Recovery from a USB drive</span></span>

<span data-ttu-id="d2880-125">Mit Surface Hub 2S können Sie das Gerät mithilfe eines Wiederherstellungsabbilds neu installieren.</span><span class="sxs-lookup"><span data-stu-id="d2880-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="d2880-126">Dadurch können Sie das Gerät in den Werkseinstellungen neu installieren, wenn Sie den BitLocker-Schlüssel verloren haben oder wenn Sie nicht mehr über Administratoranmeldeinformationen für die Einstellungs-App verfügen.</span><span class="sxs-lookup"><span data-stu-id="d2880-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="d2880-127">Verwenden Sie ein USB 3.0-Laufwerk mit 8 GB oder 16 GB Speicher, formatiert als FAT32.</span><span class="sxs-lookup"><span data-stu-id="d2880-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="d2880-128">Laden Sie von einem separaten PC das Wiederherstellungsimage der ZIP-Datei von der [Surface -Wiederherstellungswebsite](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) herunter, und kehren Sie dann zu diesen Anweisungen zurück.</span><span class="sxs-lookup"><span data-stu-id="d2880-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="d2880-129">Geben Sie in das Suchfeld auf der Taskleiste \*\*\*\* das Wiederherstellungslaufwerk **ein,** und wählen Sie dann in den Ergebnissen ein Wiederherstellungslaufwerk oder Wiederherstellungslaufwerk erstellen aus. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d2880-129">In the search box on the taskbar, enter **recovery drive**, and then select **Create a recovery drive** or **Recovery Drive** from the results.</span></span> <span data-ttu-id="d2880-130">Möglicherweise müssen Sie ein Administratorkennwort eingeben oder Ihre Auswahl bestätigen.</span><span class="sxs-lookup"><span data-stu-id="d2880-130">You may need to enter an admin password or confirm your choice.</span></span>

1. <span data-ttu-id="d2880-131">Wählen Sie **im Feld Benutzerkontensteuerung** **"Ja" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-131">In the **User Account Control** box, select **Yes**.</span></span>

1. <span data-ttu-id="d2880-132">Stellen Sie sicher, dass Sie das **Kontrollkästchen "Systemdateien auf dem** Wiederherstellungslaufwerk sichern" aktivieren und dann **"Weiter" auswählen.**</span><span class="sxs-lookup"><span data-stu-id="d2880-132">Make sure to clear the **Back up system files to the recovery drive** check box and then select **Next**.</span></span>

1. <span data-ttu-id="d2880-133">Wählen Sie Ihr USB-Laufwerk aus, und wählen Sie dann **"Weiter > Erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-133">Select your USB drive, and then select **Next > Create**.</span></span>  <span data-ttu-id="d2880-134">Einige Hilfsprogramme müssen auf das Wiederherstellungslaufwerk kopiert werden, sodass dies einige Minuten dauern kann.</span><span class="sxs-lookup"><span data-stu-id="d2880-134">Some utilities need to be copied to the recovery drive, so this might take a few minutes.</span></span>

1. <span data-ttu-id="d2880-135">Wenn das Wiederherstellungslaufwerk bereit ist, wählen Sie **"Fertig stellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-135">When the recovery drive is ready, select **Finish**.</span></span>

1. <span data-ttu-id="d2880-136">Doppelklicken Sie auf die ZIP-Wiederherstellungsabbilddatei, die Sie zuvor heruntergeladen haben, um sie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d2880-136">Double-click the recovery image .zip file that you previously downloaded to open it.</span></span>

1. <span data-ttu-id="d2880-137">Wählen Sie alle Dateien aus dem Wiederherstellungsimageordner aus, kopieren Sie sie in das Stammverzeichnis Ihres USB-Laufwerks, und wählen Sie dann "Auswählen, um die Dateien im Ziel **zu ersetzen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-137">Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.</span></span>

1. <span data-ttu-id="d2880-138">Sobald die Dateien kopiert wurden, wählen Sie auf der Taskleiste das Symbol "Hardware sicher entfernen" und **"Eject Media"** aus, und entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="d2880-138">Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar, and remove your USB drive.</span></span>

1. <span data-ttu-id="d2880-139">Schließen Sie das #A0 an einen beliebigen USB-C- oder #A1 auf dem Surface Hub 2S an.</span><span class="sxs-lookup"><span data-stu-id="d2880-139">Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S.</span></span>

1. <span data-ttu-id="d2880-140">Deaktivieren Sie den Hub, und gehen Sie dann wie im Folgenden vor, um vom USB-Laufwerk zu starten:</span><span class="sxs-lookup"><span data-stu-id="d2880-140">Turn off the Hub and then take these steps to boot from the USB drive:</span></span>

   1. <span data-ttu-id="d2880-141">Drücken Sie beim Drücken der Taste "Lautstärke nach unten" die Ein-/Aus-Taste.</span><span class="sxs-lookup"><span data-stu-id="d2880-141">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="d2880-142">Drücken Sie weiterhin beide Tasten, bis das Windows-Logo angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d2880-142">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="d2880-143">Lassen Sie die Ein/Aus-Taste los, halten Sie jedoch die Schaltfläche "Volume down" gedrückt, bis die Installation der Benutzeroberfläche beginnt.</span><span class="sxs-lookup"><span data-stu-id="d2880-143">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Verwenden der Tasten "Volume down" und "Power", um die Wiederherstellung zu initiieren*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="d2880-145">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="d2880-145">Figure 2.</span></span> <span data-ttu-id="d2880-146">Lautstärke- und Netztasten</span><span class="sxs-lookup"><span data-stu-id="d2880-146">Volume and Power buttons</span></span>*

1. <span data-ttu-id="d2880-147">Wählen Sie auf dem Sprachauswahlbildschirm die Anzeigesprache für Surface Hub 2S aus.</span><span class="sxs-lookup"><span data-stu-id="d2880-147">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="d2880-148">Wählen **Sie "Von einem Laufwerk wiederherstellen"** aus, und **bereinigen**Sie das Laufwerk vollständig, und wählen Sie dann "Wiederherstellen" **aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-148">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="d2880-149">Wenn Sie zur Eingabe eines BitLocker-Schlüssels aufgefordert werden, wählen Sie **"Dieses Laufwerk überspringen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2880-149">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="d2880-150">Surface Hub 2S wird mehrmals neu gestartet und benötigt ca. 30 Minuten, um den Wiederherstellungsvorgang abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="d2880-150">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="d2880-151">Wenn der Bildschirm zum ersten Einrichten angezeigt wird, entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="d2880-151">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="d2880-152">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="d2880-152">Contact Support</span></span>

<span data-ttu-id="d2880-153">Wenn Sie Fragen haben oder Hilfe benötigen, können [Sie eine Supportanfrage erstellen.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="d2880-153">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
