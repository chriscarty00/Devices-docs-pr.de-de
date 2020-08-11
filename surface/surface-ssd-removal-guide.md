---
title: SSD-Entfernung in kompatiblen Surface-Geräten
description: So übertragen Sie eine SSD von einem Surface-Gerät auf ein anderes.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919224"
---
# <span data-ttu-id="dbf7d-103">Bewährte Methoden für die SSD-Entfernung von kompatiblen Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="dbf7d-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbf7d-104">Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="dbf7d-105">Es werden die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beschrieben, wenn Sie SSDs in Surface-Geräten mit wechselbaren SSDs entfernen und ersetzen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-105">It describes the recommended best practices for use by qualified IT technicians when they remove and replace SSDs in Surface devices that have removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="dbf7d-106">Durch das Öffnen von Geräten und das Ersetzen von Gerätekomponenten können elektrische Schocks, Geräteschäden, Brände sowie Risiken für Personenschäden und andere Gefahren auftreten.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="dbf7d-107">Verwenden Sie immer Vorsicht, wenn Sie solche Aktivitäten durchführen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="dbf7d-108">Befolgen Sie die Sicherheitsvorkehrungen und Vorgehensweisen, die im [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="dbf7d-109">Wir empfehlen, dass Sie professionelle Unterstützung erhalten, wenn Sie die Sicherheitsvorkehrungen und Verfahren, die im "rSSD-Entfernungs Leit Faden für Unternehmen" angegeben sind, nicht befolgen können.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="dbf7d-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dbf7d-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbf7d-111">In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheitsvorkehrungen und Sicherheitsrichtlinien und-Verfahren verstehen, die im "rSSD-Entfernungs Leit Faden für Unternehmen" beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="dbf7d-112">Vorbereiten der SSD-Entfernung</span><span class="sxs-lookup"><span data-stu-id="dbf7d-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="dbf7d-113">Installieren der neuesten Updates</span><span class="sxs-lookup"><span data-stu-id="dbf7d-113">Install the latest updates</span></span> 

<span data-ttu-id="dbf7d-114">Bevor Sie beginnen, stellen Sie sicher, dass Ihre Version von Windows über die neuesten Updates verfügt:</span><span class="sxs-lookup"><span data-stu-id="dbf7d-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="dbf7d-115">Wechseln Sie zu **Start**  >  **Settings**  >  **Update & Security**, und wählen Sie auf **Updates überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="dbf7d-116">Installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-116">Install all available updates.</span></span> 
2. <span data-ttu-id="dbf7d-117">Installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-117">Install all available updates.</span></span>
3. <span data-ttu-id="dbf7d-118">Vergewissern Sie sich, dass Sie über alle Kennwörter verfügen, die für den Zugriff auf das Gerät erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="dbf7d-119">„BitLocker verwalten“</span><span class="sxs-lookup"><span data-stu-id="dbf7d-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="dbf7d-120">Dieser Abschnitt enthält Empfehlungen für Organisationen, die die BitLocker-Verschlüsselung für Festplatten aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="dbf7d-121">Weitere Informationen finden Sie im [BitLocker-Wiederherstellungs Handbuch](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="dbf7d-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="dbf7d-122">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="dbf7d-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="dbf7d-123">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt sein kann, führen Sie die folgenden Schritte aus, um BitLocker zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="dbf7d-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="dbf7d-124">Geben **Settings**Sie in Einstellungen **BitLocker**ein, und wählen Sie dann **BitLocker verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="dbf7d-125">Wählen Sie **BitLocker deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="dbf7d-126">Schalten Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-126">Power down the device.</span></span> 

### <span data-ttu-id="dbf7d-127">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="dbf7d-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="dbf7d-128">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker-Wiederherstellungsschlüssel zu generieren und ihn auf einem USB-Speicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="dbf7d-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="dbf7d-129">Geben **Settings**Sie in Einstellungen **BitLocker**ein.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="dbf7d-130">Wählen Sie **BitLocker**  > -**Wiederherstellungsschlüssel generieren BitLocker**verwalten aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="dbf7d-131">Legen Sie ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="dbf7d-132">Speichern Sie den Wiederherstellungsschlüssel in einem USB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="dbf7d-133">Entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="dbf7d-134">Schalten Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-134">Power down the device.</span></span> 

## <span data-ttu-id="dbf7d-135">Entfernen und Ersetzen der SSD</span><span class="sxs-lookup"><span data-stu-id="dbf7d-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="dbf7d-136">Entfernen Sie die SSD, indem Sie die Anweisungen im [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440)verwenden.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="dbf7d-137">Setzen Sie die ursprüngliche SSD auf ein neues Gerät, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="dbf7d-138">Schalten Sie das neue Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-138">Power on the new device.</span></span> <span data-ttu-id="dbf7d-139">Das Gerät kann während des Starts eine Firmware-Aktualisierung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="dbf7d-140">Nach dem Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="dbf7d-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="dbf7d-141">Verwalten von unverschlüsselten SSDs</span><span class="sxs-lookup"><span data-stu-id="dbf7d-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="dbf7d-142">Wenn die SSD während der Übertragung unverschlüsselt bleibt, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dbf7d-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="dbf7d-143">Wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (dargestellt durch das Schlüsselsymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="dbf7d-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="dbf7d-144">Geben Sie das Kennwort ein, und melden Sie sich bis zum Abschluss der zweistufigen Authentifizierung an (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="dbf7d-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="dbf7d-145">Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zu Konto **Start**  >  **Account**  >  **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="dbf7d-146">Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="dbf7d-147">Wenn das Gerät BitLocker-deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Ersatz aktivieren möchten, wechseln Sie zu **BitLocker**BitLocker-BitLocker-  >  **Manage Bitlocker**  >  **Lebenslauf**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="dbf7d-148">Führen Sie das Microsoft Surface Diagnostics Toolkit for Business (Unternehmen) aus, um die vollständige Gerätefunktionalität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="dbf7d-149">Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="dbf7d-150">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="dbf7d-151">Überprüfen Sie das Office-Konto, indem Sie die **Office-App**öffnen, zu **Datei**  >  **Konto** navigieren und dann auf Fehlermeldungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="dbf7d-152">Verwalten von verschlüsselten SSDs</span><span class="sxs-lookup"><span data-stu-id="dbf7d-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="dbf7d-153">Sie benötigen ein zweites Gerät zum Lesen des BitLocker-Wiederherstellungsschlüssels, der auf dem USB-Laufwerk gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="dbf7d-154">Wenn die SSD während der Übertragung verschlüsselt blieb, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dbf7d-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="dbf7d-155">Legen Sie das USB-Laufwerk mit dem BitLocker-Wiederherstellungsschlüssel in das zweite Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="dbf7d-156">Öffnen Sie die txt-Datei, die den BitLocker-Wiederherstellungsschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="dbf7d-157">Geben Sie den BitLocker-Wiederherstellungsschlüssel auf dem neuen Gerät, das die ursprüngliche SSD enthält, manuell ein.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="dbf7d-158">Nachdem Sie den BitLocker-Wiederherstellungsschlüssel erfolgreich eingegeben haben, wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (dargestellt durch das Schlüsselsymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="dbf7d-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="dbf7d-159">Geben Sie das Kennwort ein, und melden Sie sich an, bis zum Abschluss der zweistufigen Authentifizierung (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="dbf7d-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="dbf7d-160">Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zu Konto **Start**  >  **Account**  >  **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="dbf7d-161">Melden Sie sich mit dem Kennwort wieder an, und richten Sie dann Windows Hello ein, und fügen Sie eine PIN hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="dbf7d-162">Wenn das Gerät BitLocker-deaktiviert war, um das Entfernen und Ersetzen von SSD zu vereinfachen, und wenn Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **Einstellungen**BitLocker-BitLocker-BitLocker-Status  >  **Bitlocker**  >  **Manage Bitlocker**  >  **wieder aufnehmen**.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="dbf7d-163">Führen Sie die Funktion **zum Überprüfen** der vollständigen Gerätefunktionalität aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="dbf7d-164">Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="dbf7d-165">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="dbf7d-166">Um den Status des Office-Kontos zu überprüfen, öffnen Sie die **Office-App**, und wechseln Sie dann zu **Datei**  >  **Konto** , um auf Fehlermeldungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dbf7d-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="dbf7d-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbf7d-167">More information</span></span> 

<span data-ttu-id="dbf7d-168">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="dbf7d-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="dbf7d-169">rSSD-Entfernungs Leit Faden für Enterprise</span><span class="sxs-lookup"><span data-stu-id="dbf7d-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="dbf7d-170">BitLocker-Wiederherstellungsleitfaden</span><span class="sxs-lookup"><span data-stu-id="dbf7d-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="dbf7d-171">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="dbf7d-171">Still need help?</span></span> <span data-ttu-id="dbf7d-172">Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="dbf7d-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>