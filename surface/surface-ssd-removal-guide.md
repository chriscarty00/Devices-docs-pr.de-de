---
title: SSD-Entfernung in kompatiblen Surface-Geräten
description: Dieser Artikel, der für qualifizierte IT-Techniker vorgesehen ist, beschreibt die empfohlenen bewährten Methoden für das Entfernen und Ersetzen von SSDs in Surface Laptop 3, Surface pro X und Surface Laptop go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133170"
---
# <span data-ttu-id="96ceb-103">Bewährte Methoden für die SSD-Entfernung von kompatiblen Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="96ceb-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ceb-104">Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="96ceb-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="96ceb-105">Sie beschreibt die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beim Entfernen und Ersetzen von SSDs auf den folgenden kompatiblen Surface-Geräten:</span><span class="sxs-lookup"><span data-stu-id="96ceb-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="96ceb-106">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="96ceb-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="96ceb-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="96ceb-107">Surface Pro X</span></span> 
- <span data-ttu-id="96ceb-108">Surface Laptop go</span><span class="sxs-lookup"><span data-stu-id="96ceb-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="96ceb-109">Durch das Öffnen von Geräten und das Ersetzen von Gerätekomponenten können elektrische Schocks, Geräteschäden, Brände sowie Risiken für Personenschäden und andere Gefahren auftreten.</span><span class="sxs-lookup"><span data-stu-id="96ceb-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="96ceb-110">Verwenden Sie immer Vorsicht, wenn Sie solche Aktivitäten durchführen.</span><span class="sxs-lookup"><span data-stu-id="96ceb-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="96ceb-111">Befolgen Sie die Sicherheitsvorkehrungen und Vorgehensweisen, die im [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="96ceb-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="96ceb-112">Wir empfehlen, dass Sie professionelle Unterstützung erhalten, wenn Sie die Sicherheitsvorkehrungen und Verfahren, die im "rSSD-Entfernungs Leit Faden für Unternehmen" angegeben sind, nicht befolgen können.</span><span class="sxs-lookup"><span data-stu-id="96ceb-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="96ceb-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="96ceb-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ceb-114">In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheitsvorkehrungen und Sicherheitsrichtlinien und-Verfahren verstehen, die im "rSSD-Entfernungs Leit Faden für Unternehmen" beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="96ceb-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="96ceb-115">Vorbereiten der SSD-Entfernung</span><span class="sxs-lookup"><span data-stu-id="96ceb-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="96ceb-116">Installieren der neuesten Updates</span><span class="sxs-lookup"><span data-stu-id="96ceb-116">Install the latest updates</span></span> 

<span data-ttu-id="96ceb-117">Bevor Sie beginnen, stellen Sie sicher, dass Ihre Version von Windows die neuesten Updates installiert hat:</span><span class="sxs-lookup"><span data-stu-id="96ceb-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="96ceb-118">Wechseln Sie zu **Start**  >  **Settings**  >  **Update & Security**, und wählen Sie auf **Updates überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="96ceb-119">Installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="96ceb-119">Install all available updates.</span></span>
3. <span data-ttu-id="96ceb-120">Überprüfen Sie alle Kennwörter, die für den Zugriff auf das Gerät erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="96ceb-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="96ceb-121">„BitLocker verwalten“</span><span class="sxs-lookup"><span data-stu-id="96ceb-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="96ceb-122">Dieser Abschnitt enthält Empfehlungen für Organisationen, die die BitLocker-Verschlüsselung für Festplatten aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="96ceb-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="96ceb-123">Weitere Informationen finden Sie unter  [BitLocker-Wiederherstellungs Leit Faden](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="96ceb-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="96ceb-124">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="96ceb-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="96ceb-125">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt sein kann, führen Sie die folgenden Schritte aus, um BitLocker zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="96ceb-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="96ceb-126">Geben **Settings**Sie in Einstellungen **BitLocker** ein, und wählen Sie dann **BitLocker verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="96ceb-127">Wählen Sie **BitLocker deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="96ceb-128">Schalten Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-128">Power down the device.</span></span> 

### <span data-ttu-id="96ceb-129">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="96ceb-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="96ceb-130">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker-Wiederherstellungsschlüssel zu generieren und ihn auf einem USB-Speicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="96ceb-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="96ceb-131">Geben **Settings**Sie in Einstellungen **BitLocker**ein.</span><span class="sxs-lookup"><span data-stu-id="96ceb-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="96ceb-132">Wählen Sie **BitLocker**  > -**Wiederherstellungsschlüssel generieren BitLocker**verwalten aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="96ceb-133">Legen Sie ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="96ceb-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="96ceb-134">Speichern Sie den Wiederherstellungsschlüssel in einem USB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="96ceb-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="96ceb-135">Entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="96ceb-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="96ceb-136">Schalten Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-136">Power down the device.</span></span> 

## <span data-ttu-id="96ceb-137">Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="96ceb-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="96ceb-138">Entfernen Sie die SSD, indem Sie die Anweisungen im [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440)verwenden.</span><span class="sxs-lookup"><span data-stu-id="96ceb-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="96ceb-139">Setzen Sie die ursprüngliche SSD auf ein neues Gerät, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="96ceb-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="96ceb-140">Schalten Sie das neue Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="96ceb-140">Power on the new device.</span></span> <span data-ttu-id="96ceb-141">Das Gerät kann während des Starts eine Firmware-Aktualisierung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="96ceb-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="96ceb-142">Nach dem Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="96ceb-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="96ceb-143">Verwalten von unverschlüsselten SSDs</span><span class="sxs-lookup"><span data-stu-id="96ceb-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="96ceb-144">Wenn die SSD während der Übertragung unverschlüsselt ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="96ceb-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="96ceb-145">Wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (dargestellt durch das Schlüsselsymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="96ceb-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="96ceb-146">Geben Sie das Kennwort ein, und melden Sie sich bis zum Abschluss der zweistufigen Authentifizierung an (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="96ceb-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="96ceb-147">Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zu Konto **Start**  >  **Account**  >  **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="96ceb-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="96ceb-148">Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="96ceb-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="96ceb-149">Wenn das Gerät BitLocker-deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Ersatz aktivieren möchten, wechseln Sie zu **BitLocker**BitLocker-BitLocker-  >  **Manage BitLocker**  >  **Lebenslauf**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="96ceb-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="96ceb-150">Führen Sie das [Microsoft Surface Diagnostics Toolkit for Business (Unternehmen) aus](surface-diagnostic-toolkit-for-business-intro.md) , um die vollständige Gerätefunktionalität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="96ceb-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="96ceb-151">Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="96ceb-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="96ceb-152">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="96ceb-153">Überprüfen Sie das Office-Konto, indem Sie die **Office-App**öffnen, zu **Datei**  >  **Konto** navigieren und dann auf Fehlermeldungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="96ceb-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="96ceb-154">Verwalten von verschlüsselten SSDs</span><span class="sxs-lookup"><span data-stu-id="96ceb-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="96ceb-155">Sie benötigen ein zweites Gerät zum Lesen des BitLocker-Wiederherstellungsschlüssels, der auf dem USB-Laufwerk gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="96ceb-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="96ceb-156">Wenn die SSD während der Übertragung verschlüsselt ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="96ceb-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="96ceb-157">Legen Sie das USB-Laufwerk mit dem BitLocker-Wiederherstellungsschlüssel in das zweite Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="96ceb-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="96ceb-158">Öffnen Sie die txt-Datei, die den BitLocker-Wiederherstellungsschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="96ceb-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="96ceb-159">Geben Sie den BitLocker-Wiederherstellungsschlüssel auf dem neuen Gerät, das die ursprüngliche SSD enthält, manuell ein.</span><span class="sxs-lookup"><span data-stu-id="96ceb-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="96ceb-160">Nachdem Sie den BitLocker-Wiederherstellungsschlüssel erfolgreich eingegeben haben, wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (dargestellt durch das Schlüsselsymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="96ceb-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="96ceb-161">Geben Sie das Kennwort ein, und melden Sie sich an, bis zum Abschluss der zweistufigen Authentifizierung (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="96ceb-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="96ceb-162">Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zu Konto **Start**  >  **Account**  >  **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="96ceb-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="96ceb-163">Melden Sie sich mit dem Kennwort wieder an, und richten Sie dann Windows Hello ein, und fügen Sie eine PIN hinzu.</span><span class="sxs-lookup"><span data-stu-id="96ceb-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="96ceb-164">Wenn das Gerät BitLocker-deaktiviert war, um das Entfernen und Ersetzen von SSD zu vereinfachen, und wenn Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **Einstellungen**BitLocker-BitLocker-BitLocker-Status  >  **BitLocker**  >  **Manage BitLocker**  >  **wieder aufnehmen**.</span><span class="sxs-lookup"><span data-stu-id="96ceb-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="96ceb-165">Führen Sie die Funktion **[zum Überprüfen](surface-diagnostic-toolkit-for-business-intro.md)** der vollständigen Gerätefunktionalität aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="96ceb-166">Zum Überprüfen der Windows-Aktivierung wählen Sie **Einstellungen**  >  **aktivieren aus**.</span><span class="sxs-lookup"><span data-stu-id="96ceb-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="96ceb-167">Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="96ceb-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="96ceb-168">Um den Status des Office-Kontos zu überprüfen, öffnen Sie die **Office-App**, und wechseln Sie dann zu **Datei**  >  **Konto** , um auf Fehlermeldungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="96ceb-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="96ceb-169">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="96ceb-169">Learn more</span></span>

- [<span data-ttu-id="96ceb-170">rSSD-Entfernungs Leit Faden für Enterprise</span><span class="sxs-lookup"><span data-stu-id="96ceb-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="96ceb-171">BitLocker-Wiederherstellungsleitfaden</span><span class="sxs-lookup"><span data-stu-id="96ceb-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="96ceb-172">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="96ceb-172">Still need help?</span></span> <span data-ttu-id="96ceb-173">Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="96ceb-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>