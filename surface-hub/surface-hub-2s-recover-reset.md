---
title: Zurücksetzen und Wiederherstellen für Surface Hub 2S
description: Hier erfahren Sie, wie Sie Surface Hub 2S wiederherstellen und zurücksetzen.
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
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833004"
---
# <span data-ttu-id="9e0bf-104">Zurücksetzen und Wiederherstellen für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="9e0bf-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="9e0bf-105">Wenn Probleme mit Surface Hub 2S auftreten, können Sie das Gerät auf die Werkseinstellungen zurücksetzen oder mithilfe eines USB-Laufwerks wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="9e0bf-106">Melden Sie sich zunächst bei Surface Hub 2S mit Administratoranmeldeinformationen an, öffnen Sie die **Einstellungs** -APP, wählen Sie **Update & Security**aus, und wählen Sie dann **Wiederherstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="9e0bf-107">Zurücksetzen des Geräts</span><span class="sxs-lookup"><span data-stu-id="9e0bf-107">Reset the device</span></span>

1. <span data-ttu-id="9e0bf-108">Wenn Sie das Gerät zurücksetzen möchten, wählen Sie **Erste Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-108">To reset the device, select **Get Started**.</span></span>
2. <span data-ttu-id="9e0bf-109">Wenn das Fenster **bereit zum Zurücksetzen dieses Geräts** angezeigt wird, wählen Sie **Zurücksetzen**aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
  >[!NOTE]
  ><span data-ttu-id="9e0bf-110">Surface Hub 2S installiert das Betriebssystem von der Wiederherstellungspartition erneut.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="9e0bf-111">Dieser Vorgang kann bis zu einer Stunde dauern.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="9e0bf-112">Um das Gerät neu zu konfigurieren, führen Sie das erstmalige Setup-Programm aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-112">To reconfigure the device, run the first-time Setup program.</span></span>
4. <span data-ttu-id="9e0bf-113">Wenn Sie das Gerät mithilfe von Microsoft InTune oder einer anderen Lösung für die Verwaltung mobiler Geräte verwalten, ziehen Sie den vorherigen Eintrag zurück, löschen Sie ihn, und registrieren Sie das neue Gerät dann erneut.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="9e0bf-114">Weitere Informationen finden Sie unter [Entfernen von Geräten mithilfe von wischen, zurückziehen oder manuelles Aufheben der Registrierung des Geräts](https://docs.microsoft.com/intune/devices-wipe).</span><span class="sxs-lookup"><span data-stu-id="9e0bf-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

![\* Reset und Recovery für Surface Hub 2S \*](images/sh2-reset.png)<br>
*<span data-ttu-id="9e0bf-116">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-116">Figure 1.</span></span> <span data-ttu-id="9e0bf-117">Zurücksetzen und Wiederherstellen für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="9e0bf-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="9e0bf-118">Wiederherstellen des Surface Hub 2S mithilfe eines USB-Wiederherstellungs Laufwerks</span><span class="sxs-lookup"><span data-stu-id="9e0bf-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="9e0bf-119">Neu in Surface Hub 2S können Sie das Gerät jetzt mithilfe eines Wiederherstellungs Bilds erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="9e0bf-120">Wiederherstellung von einem USB-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="9e0bf-120">Recovery from a USB drive</span></span>

<span data-ttu-id="9e0bf-121">Mithilfe von Surface Hub 2S können Sie das Gerät mithilfe eines Wiederherstellungs Bilds erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="9e0bf-122">Auf diese Weise können Sie das Gerät erneut auf die Werkseinstellungen installieren, wenn Sie den BitLocker-Schlüssel verloren haben oder wenn Sie nicht mehr über Administratoranmeldeinformationen für die Einstellungs-APP verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="9e0bf-123">Verwenden Sie ein USB-3,0-Laufwerk mit 8 GB oder 16 GB Speicher, das als FAT32 formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="9e0bf-124">Laden Sie das ZIP-Datei Wiederherstellungsabbild von einem separaten PC von der [Surface Recovery-Website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) herunter, und kehren Sie dann zu diesen Anweisungen zurück.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 
1. <span data-ttu-id="9e0bf-125">Entzippen Sie die heruntergeladene Datei auf das Stammverzeichnis des USB-Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  
1. <span data-ttu-id="9e0bf-126">Schließen Sie das USB-Laufwerk an einen beliebigen USB-C-oder USB-Anschluss an Surface Hub 2S an.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>
1. <span data-ttu-id="9e0bf-127">Gerät ausschalten:</span><span class="sxs-lookup"><span data-stu-id="9e0bf-127">Turn off the device:</span></span>
   1. <span data-ttu-id="9e0bf-128">Drücken Sie die Einschalttaste, während Sie die Lautstärketaste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-128">While holding down the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="9e0bf-129">Halten Sie beide Schaltflächen gedrückt, bis Sie das Windows-Logo sehen.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-129">Keep holding both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="9e0bf-130">Lassen Sie die Power-Taste los, aber halten Sie die Lautstärke so lange gedrückt, bis die Benutzeroberfläche für die Installation beginnt.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-130">Release the Power button but continue to hold the Volume until the Install UI begins.</span></span>

    ![\* Verwenden Sie die Lautstärke-und Netztasten, um die Wiederherstellung zu initiieren \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="9e0bf-132">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-132">Figure 2.</span></span> <span data-ttu-id="9e0bf-133">Lautstärke-und Power-Tasten</span><span class="sxs-lookup"><span data-stu-id="9e0bf-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="9e0bf-134">Wählen Sie auf dem Bildschirm Sprachauswahl die Anzeigesprache für den Surface Hub 2S aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>
1. <span data-ttu-id="9e0bf-135">Wählen Sie **auf einem Laufwerk wiederherstellen aus** , und **reinigen Sie das Laufwerk vollständig**, und wählen Sie dann **Wiederherstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="9e0bf-136">Wenn Sie zur Eingabe eines BitLocker-Schlüssels aufgefordert werden, wählen Sie **dieses Laufwerk überspringen**aus.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="9e0bf-137">Surface Hub 2S wird mehrmals neu gestartet, und es dauert ungefähr 30 Minuten, bis der Wiederherstellungsvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="9e0bf-138">Wenn der Bildschirm für die erstmalige Einrichtung angezeigt wird, entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="9e0bf-138">When the first-time setup screen appears,remove the USB drive.</span></span>

## <span data-ttu-id="9e0bf-139">Support kontaktieren</span><span class="sxs-lookup"><span data-stu-id="9e0bf-139">Contact Support</span></span>

<span data-ttu-id="9e0bf-140">Wenn Sie Fragen haben oder Hilfe benötigen, können Sie [eine Supportanfrage erstellen](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="9e0bf-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
