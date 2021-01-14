---
title: Entfernen von SSD auf kompatiblen Surface-Geräten
description: Dieser Artikel richtet sich an qualifizierte IT-Techniker und beschreibt die empfohlenen bewährten Methoden zum Entfernen und Ersetzen von SSDs in Surface Laptop 3, Surface Pro X und Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: b65feb24803311aba809819cd6da273ed6934c75
ms.sourcegitcommit: 41124d496abaa38a0d989159f2afec3542d562ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269106"
---
# <span data-ttu-id="3950c-103">Bewährte Methoden für das Entfernen von SSD von kompatiblen Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="3950c-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3950c-104">Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3950c-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="3950c-105">Es beschreibt die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beim Entfernen und Ersetzen von SSDs auf den folgenden kompatiblen Surface-Geräten:</span><span class="sxs-lookup"><span data-stu-id="3950c-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="3950c-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="3950c-106">Surface Pro 7+</span></span>
- <span data-ttu-id="3950c-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="3950c-107">Surface Pro X</span></span>
- <span data-ttu-id="3950c-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="3950c-108">Surface Laptop Go</span></span>
- <span data-ttu-id="3950c-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="3950c-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="3950c-110">Das Öffnen von Geräten und das Ersetzen von Gerätekomponenten kann stromauflösend, Geräteschäden, Löschrisiken und persönliche Schäden sowie andere Gefahren darstellen.</span><span class="sxs-lookup"><span data-stu-id="3950c-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="3950c-111">Verwenden Sie bei solchen Aktivitäten stets Vorsicht.</span><span class="sxs-lookup"><span data-stu-id="3950c-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="3950c-112">Befolgen Sie die Sicherheitsvorkehrungen und -verfahren, die im [rSSD Removal Guide for Enterprise identifiziert sind.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="3950c-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="3950c-113">Es wird empfohlen, professionelle Unterstützung zu erhalten, wenn Sie die im "rSSD Removal Guide for Enterprise" angegebenen Sicherheitsvorkehrungen und Verfahren nicht befolgen können.</span><span class="sxs-lookup"><span data-stu-id="3950c-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="3950c-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3950c-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3950c-115">In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheitsvorkehrungen und Sicherheitsrichtlinien und -verfahren verstehen, die im "rSSD Removal Guide for Enterprise" beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="3950c-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="3950c-116">Vorbereiten der Entfernung von SSD</span><span class="sxs-lookup"><span data-stu-id="3950c-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="3950c-117">Installieren der neuesten Updates</span><span class="sxs-lookup"><span data-stu-id="3950c-117">Install the latest updates</span></span> 

<span data-ttu-id="3950c-118">Bevor Sie beginnen, stellen Sie sicher, dass in Ihrer Version von Windows die neuesten Updates installiert sind:</span><span class="sxs-lookup"><span data-stu-id="3950c-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="3950c-119">Go to **Start**  >  **Settings**  >  **Update & Security,** and select **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="3950c-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="3950c-120">Installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="3950c-120">Install all available updates.</span></span>
3. <span data-ttu-id="3950c-121">Überprüfen Sie alle Kennwörter, die für den Zugriff auf das Gerät erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3950c-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="3950c-122">„BitLocker verwalten“</span><span class="sxs-lookup"><span data-stu-id="3950c-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="3950c-123">Dieser Abschnitt enthält Empfehlungen für Organisationen, die die BitLocker-Verschlüsselung für Festplatten aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3950c-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="3950c-124">Weitere Informationen finden Sie im [BitLocker-Wiederherstellungshandbuch.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="3950c-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="3950c-125">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="3950c-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="3950c-126">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt werden kann, führen Sie die folgenden Schritte aus, um BitLocker zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3950c-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="3950c-127">Geben **Sie in**den Einstellungen **BitLocker ein,** und wählen Sie dann **"BitLocker verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="3950c-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="3950c-128">Wählen **Sie BitLocker deaktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="3950c-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="3950c-129">Schalten Sie das Gerät herunter.</span><span class="sxs-lookup"><span data-stu-id="3950c-129">Power down the device.</span></span> 

### <span data-ttu-id="3950c-130">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="3950c-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="3950c-131">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker-Wiederherstellungsschlüssel zu generieren und ihn im USB-Speicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="3950c-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="3950c-132">Geben **Sie in**den Einstellungen **BitLocker ein.**</span><span class="sxs-lookup"><span data-stu-id="3950c-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="3950c-133">Wählen **Sie "BitLocker**  > **verwalten" aus, um den BitLocker-Wiederherstellungsschlüssel zu generieren.**</span><span class="sxs-lookup"><span data-stu-id="3950c-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="3950c-134">Fügen Sie ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="3950c-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="3950c-135">Speichern Sie den Wiederherstellungsschlüssel im USB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="3950c-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="3950c-136">Entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="3950c-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="3950c-137">Schalten Sie das Gerät herunter.</span><span class="sxs-lookup"><span data-stu-id="3950c-137">Power down the device.</span></span> 

## <span data-ttu-id="3950c-138">Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="3950c-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="3950c-139">Entfernen Sie das SSD mithilfe der entsprechenden Anweisungen für Ihr Gerät, das im [rSSD Removal Guide for Enterprise enthalten ist.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="3950c-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="3950c-140">Stellen Sie das ursprüngliche SSD in ein neues Gerät ein, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="3950c-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="3950c-141">Schalten Sie das neue Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="3950c-141">Power on the new device.</span></span> <span data-ttu-id="3950c-142">Das Gerät kann während des Starts ein Firmwareupdate durchgehen.</span><span class="sxs-lookup"><span data-stu-id="3950c-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="3950c-143">Nach dem Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="3950c-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="3950c-144">Verwalten unverschlüsselter SSDs</span><span class="sxs-lookup"><span data-stu-id="3950c-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="3950c-145">Wenn das SSD während der Übertragung unverschlüsselt ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3950c-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="3950c-146">Wechseln Sie **zu "Kennwort für Anmeldeoptionen"**  >  \*\*\*\* (dargestellt durch das Schlüsselsymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="3950c-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="3950c-147">Geben Sie das Kennwort ein, und melden Sie sich an, bis die zweistufige Authentifizierung abgeschlossen ist (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="3950c-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="3950c-148">Nachdem Sie vollständig angemeldet sind, wechseln Sie zu **"Konto**  >  \*\*\*\*  >  **abmelden starten".**</span><span class="sxs-lookup"><span data-stu-id="3950c-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="3950c-149">Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3950c-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="3950c-150">Wenn das Gerät bitLocker-deaktiviert war, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **BitLocker**  >  **Verwalten BitLocker**  >  **Fortsetzen BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3950c-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="3950c-151">Führen Sie [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) aus, um die vollständige Gerätefunktionalität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3950c-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="3950c-152">Suchen Sie nach der Windows-Aktivierung, indem Sie zur **Einstellungsaktivierung**  >  **navigieren.**</span><span class="sxs-lookup"><span data-stu-id="3950c-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="3950c-153">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.**</span><span class="sxs-lookup"><span data-stu-id="3950c-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="3950c-154">Überprüfen Sie das Office-Konto, indem Sie die **Office-App**öffnen, zu **"Dateikonto"** navigieren und dann nach  >  \*\*\*\* Fehlermeldungen suchen.</span><span class="sxs-lookup"><span data-stu-id="3950c-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="3950c-155">Verwalten verschlüsselter SSDs</span><span class="sxs-lookup"><span data-stu-id="3950c-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="3950c-156">Sie müssen über ein zweites Gerät verfügen, um den BitLocker-Wiederherstellungsschlüssel zu lesen, der auf dem USB-Laufwerk gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="3950c-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="3950c-157">Wenn das SSD während der Übertragung verschlüsselt ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3950c-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="3950c-158">Fügen Sie das USB-Laufwerk, das den BitLocker-Wiederherstellungsschlüssel enthält, in das zweite Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="3950c-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="3950c-159">Öffnen Sie die TXT-Datei, die den Bitlocker-Wiederherstellungsschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="3950c-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="3950c-160">Geben Sie den BitLocker-Wiederherstellungsschlüssel manuell auf dem neuen Gerät ein, das das ursprüngliche SSD enthält.</span><span class="sxs-lookup"><span data-stu-id="3950c-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="3950c-161">Nachdem Sie den BitLocker-Wiederherstellungsschlüssel erfolgreich eingegeben haben, wechseln Sie zu **"Kennwort**für Anmeldeoptionen" (dargestellt durch das Schlüsselsymbol  >  \*\*\*\* auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="3950c-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="3950c-162">Geben Sie das Kennwort ein, und melden Sie sich an, bis die zweistufige Authentifizierung abgeschlossen ist (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="3950c-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="3950c-163">Nachdem Sie vollständig angemeldet sind, wechseln Sie zu **"Konto**  >  \*\*\*\*  >  **abmelden starten".**</span><span class="sxs-lookup"><span data-stu-id="3950c-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="3950c-164">Melden Sie sich mit dem Kennwort wieder an, richten Sie Windows Hello ein, und fügen Sie eine PIN hinzu.</span><span class="sxs-lookup"><span data-stu-id="3950c-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="3950c-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings**  >  **BitLocker**  >  **Manage BitLocker**Resume  >  **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="3950c-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="3950c-166">Führen Sie **[SDT aus,](surface-diagnostic-toolkit-for-business-intro.md)** um die vollständige Gerätefunktionalität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3950c-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="3950c-167">Um die Aktivierung von Windows zu überprüfen, wählen **Sie "Einstellungsaktivierung"**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="3950c-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="3950c-168">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.**</span><span class="sxs-lookup"><span data-stu-id="3950c-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="3950c-169">Um den Status des Office-Kontos zu überprüfen, \*\*\*\* öffnen Sie die **Office-App,** und wechseln Sie dann zu "Dateikonto", um nach  >  \*\*\*\* Fehlermeldungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="3950c-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="3950c-170">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="3950c-170">Learn more</span></span>

- [<span data-ttu-id="3950c-171">rSSD Removal Guide for Enterprise</span><span class="sxs-lookup"><span data-stu-id="3950c-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="3950c-172">BitLocker-Wiederherstellungsleitfaden</span><span class="sxs-lookup"><span data-stu-id="3950c-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="3950c-173">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="3950c-173">Still need help?</span></span> <span data-ttu-id="3950c-174">Wechseln Sie zur [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3950c-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>