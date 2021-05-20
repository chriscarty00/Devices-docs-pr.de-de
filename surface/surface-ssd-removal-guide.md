---
title: Entfernen von SSD auf kompatiblen Surface-Geräten
description: In diesem Artikel für qualifizierte IT-Techniker werden die empfohlenen bewährten Methoden für das Entfernen und Ersetzen von SSDs in Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X und Surface Laptop Go beschrieben.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576905"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="9e70e-103">Bewährte Methoden für das Entfernen von SSD von kompatiblen Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="9e70e-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e70e-104">Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="9e70e-105">Es werden die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beim Entfernen und Ersetzen von SSDs auf den folgenden kompatiblen Surface-Geräten beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9e70e-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="9e70e-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="9e70e-106">Surface Pro 7+</span></span>
- <span data-ttu-id="9e70e-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="9e70e-107">Surface Pro X</span></span>
- <span data-ttu-id="9e70e-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="9e70e-108">Surface Laptop Go</span></span>
- <span data-ttu-id="9e70e-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="9e70e-109">Surface Laptop 3</span></span>
- <span data-ttu-id="9e70e-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="9e70e-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="9e70e-111">Das Öffnen von Geräten und das Ersetzen von Gerätekomponenten kann zu Elektrischen Schlägen, Geräteschäden, Brand- und Verletzungsrisiken und anderen Gefahren führen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="9e70e-112">Verwenden Sie immer Vorsicht, wenn Sie solche Aktivitäten unternehmen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="9e70e-113">Befolgen Sie die Sicherheitsvorkehrungen und -verfahren, die im [rSSD Removal Guide für](https://www.microsoft.com/download/100440)Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9e70e-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="9e70e-114">Es wird empfohlen, professionelle Unterstützung zu erhalten, wenn Sie die im "rSSD Removal Guide for Enterprise" angegebenen Sicherheitsvorkehrungen und Verfahren nicht befolgen Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9e70e-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e70e-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9e70e-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e70e-116">In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheits- und Sicherheitsrichtlinien und -verfahren verstehen, die im "rSSD Removal Guide for Enterprise" beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9e70e-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="9e70e-117">Vorbereiten der SSD-Entfernung</span><span class="sxs-lookup"><span data-stu-id="9e70e-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="9e70e-118">Installieren der neuesten Updates</span><span class="sxs-lookup"><span data-stu-id="9e70e-118">Install the latest updates</span></span> 

<span data-ttu-id="9e70e-119">Bevor Sie beginnen, stellen Sie sicher, dass Windows die neuesten Updates installiert sind:</span><span class="sxs-lookup"><span data-stu-id="9e70e-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="9e70e-120">Wechseln Sie **zu Start**  >  **Einstellungen**  >  **Update & Security**, und wählen Sie Nach Updates suchen **aus.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="9e70e-121">Installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="9e70e-121">Install all available updates.</span></span>
3. <span data-ttu-id="9e70e-122">Überprüfen Sie alle Kennwörter, die für den Zugriff auf das Gerät erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9e70e-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="9e70e-123">„BitLocker verwalten“</span><span class="sxs-lookup"><span data-stu-id="9e70e-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="9e70e-124">Dieser Abschnitt enthält Empfehlungen für Organisationen, die BitLocker für Festplatten aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="9e70e-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="9e70e-125">Weitere Informationen finden Sie unter [BitLocker Wiederherstellungshandbuch](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="9e70e-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="9e70e-126">Wenn BitLocker während des Entfernens und Ersetzens von SSD deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="9e70e-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="9e70e-127">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt sein kann, führen Sie die folgenden Schritte aus, um die BitLocker:</span><span class="sxs-lookup"><span data-stu-id="9e70e-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="9e70e-128">Geben **Einstellungen**in **BitLocker** ein, und wählen Sie dann Verwalten **BitLocker**aus.</span><span class="sxs-lookup"><span data-stu-id="9e70e-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="9e70e-129">Wählen **Sie Deaktivieren BitLocker**aus.</span><span class="sxs-lookup"><span data-stu-id="9e70e-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="9e70e-130">Schalten Sie das Gerät herunter.</span><span class="sxs-lookup"><span data-stu-id="9e70e-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="9e70e-131">Wenn BitLocker während des Entfernens und Ersetzens von SSD aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="9e70e-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="9e70e-132">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker zu generieren und im USB-Speicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="9e70e-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="9e70e-133">Geben **Einstellungen**geben Sie **BitLocker ein.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="9e70e-134">Wählen **Sie Manage BitLocker**Generate BitLocker Recovery Key  > **aus.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="9e70e-135">Fügen Sie ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="9e70e-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="9e70e-136">Speichern Sie den Wiederherstellungsschlüssel im USB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="9e70e-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="9e70e-137">Entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="9e70e-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="9e70e-138">Schalten Sie das Gerät herunter.</span><span class="sxs-lookup"><span data-stu-id="9e70e-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="9e70e-139">Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="9e70e-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="9e70e-140">Entfernen Sie die SSD mithilfe der entsprechenden Anweisungen für Ihr Gerät, die in [rSSD Removal Guide for Enterprise.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="9e70e-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="9e70e-141">Legen Sie die ursprüngliche SSD in ein neues Gerät ein, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="9e70e-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="9e70e-142">Schalten Sie das neue Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="9e70e-142">Power on the new device.</span></span> <span data-ttu-id="9e70e-143">Das Gerät kann während des Startvorgangs ein Firmwareupdate durchgehen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="9e70e-144">Nach dem Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="9e70e-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="9e70e-145">Verwalten unverschlüsselter SSDs</span><span class="sxs-lookup"><span data-stu-id="9e70e-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="9e70e-146">Wenn die SSD während der Übertragung unverschlüsselt ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9e70e-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="9e70e-147">Wechseln Sie **zu Anmeldeoptionen**  >  **Kennwort** (dargestellt durch das Tastensymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="9e70e-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="9e70e-148">Geben Sie das Kennwort ein, und melden Sie sich bis zum Abschluss der zweistufigen Authentifizierung an (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="9e70e-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="9e70e-149">Wechseln Sie nach der vollständigen Anmeldung zu **Konto**  >  **abmelden**  >  **starten.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="9e70e-150">Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="9e70e-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="9e70e-151">Wenn das Gerät BitLocker deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu erleichtern, und Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **BitLocker**Verwalten BitLocker  >  \*\*\*\*  >  **Fortsetzen BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="9e70e-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="9e70e-152">Führen Sie [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) aus, um die vollständige Gerätefunktionalität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="9e70e-153">Überprüfen Sie Windows Aktivierung, indem Sie zu **Einstellungen**  >  **navigieren.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="9e70e-154">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="9e70e-155">Überprüfen Sie das Office, indem Sie **die Office-App**öffnen, zu Dateikonto navigieren und dann \*\*\*\*  >  \*\*\*\* nach Fehlermeldungen suchen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="9e70e-156">Verwalten verschlüsselter SSDs</span><span class="sxs-lookup"><span data-stu-id="9e70e-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="9e70e-157">Sie müssen über ein zweites Gerät verfügen, um den BitLocker wiederherstellungsschlüssel zu lesen, der auf dem USB-Laufwerk gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="9e70e-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="9e70e-158">Wenn die SSD während der Übertragung verschlüsselt ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9e70e-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="9e70e-159">Fügen Sie das USB-Laufwerk, das den BitLocker wiederherstellungsschlüssel enthält, in das zweite Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="9e70e-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="9e70e-160">Öffnen Sie .txt Datei, die den Bitlocker-Wiederherstellungsschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="9e70e-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="9e70e-161">Geben Sie manuell BitLocker wiederherstellungsschlüssel auf dem neuen Gerät ein, das die ursprüngliche SSD enthält.</span><span class="sxs-lookup"><span data-stu-id="9e70e-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="9e70e-162">Nachdem Sie den Wiederherstellungsschlüssel BitLocker eingegeben haben, wechseln Sie zu **Kennwort**für Anmeldeoptionen (dargestellt durch das Tastensymbol  >  \*\*\*\* auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="9e70e-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="9e70e-163">Geben Sie das Kennwort ein, und melden Sie sich an, bis die zweistufige Authentifizierung abgeschlossen ist (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="9e70e-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="9e70e-164">Wechseln Sie nach der vollständigen Anmeldung zu **Konto**  >  **abmelden**  >  **starten.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="9e70e-165">Melden Sie sich mit dem Kennwort wieder an, und richten Sie dann Windows Hello ein, und fügen Sie eine PIN hinzu.</span><span class="sxs-lookup"><span data-stu-id="9e70e-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="9e70e-166">Wenn das Gerät BitLocker deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu erleichtern, und wenn Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **Einstellungen**  >  **BitLocker**  >  **Verwalten**BitLocker  >  **Fortsetzen BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="9e70e-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="9e70e-167">Führen **[Sie SDT aus,](surface-diagnostic-toolkit-for-business-intro.md)** um die vollständige Gerätefunktionalität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="9e70e-168">Um die Windows zu überprüfen, wählen Sie **Einstellungen**  >  **Aktivierung aus.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="9e70e-169">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.**</span><span class="sxs-lookup"><span data-stu-id="9e70e-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="9e70e-170">Um den Status des Office zu überprüfen, öffnen Sie die **Office-App,** und wechseln Sie dann zu Dateikonto, um nach \*\*\*\*  >  \*\*\*\* Fehlermeldungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9e70e-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="9e70e-171">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="9e70e-171">Learn more</span></span>

- [<span data-ttu-id="9e70e-172">rSSD Removal Guide for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e70e-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="9e70e-173">BitLocker-Wiederherstellungsleitfaden</span><span class="sxs-lookup"><span data-stu-id="9e70e-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="9e70e-174">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="9e70e-174">Still need help?</span></span> <span data-ttu-id="9e70e-175">Wechseln Sie [zu Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9e70e-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>