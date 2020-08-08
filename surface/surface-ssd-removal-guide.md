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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918962"
---
# <span data-ttu-id="27902-103">Bewährte Methoden für die SSD-Entfernung in kompatiblen Surface-Geräten</span><span class="sxs-lookup"><span data-stu-id="27902-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27902-104">Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="27902-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="27902-105">In diesem Abschnitt werden die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beschrieben, wenn Sie SSDs auf Surface-Geräten mit wechselbaren SSDs entfernen und ersetzen.</span><span class="sxs-lookup"><span data-stu-id="27902-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="27902-106">Durch das Öffnen von Geräten und das Ersetzen von Gerätekomponenten können elektrische Schocks, Geräteschäden, Brände sowie Risiken für Personenschäden und andere Gefahren auftreten.</span><span class="sxs-lookup"><span data-stu-id="27902-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="27902-107">Achten Sie bei derartigen Aktivitäten immer auf Vorsicht.</span><span class="sxs-lookup"><span data-stu-id="27902-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="27902-108">Befolgen Sie die Sicherheitsvorkehrungen und Verfahren, die im rSSD-Entfernungs Leit Faden für Enterprise angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="27902-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="27902-109">Microsoft empfiehlt, dass Sie professionelle Unterstützung suchen, wenn Sie die im rSSD-Entfernungs Leit Faden für Enterprise angegebenen Sicherheitsvorkehrungen und Verfahren nicht befolgen können.</span><span class="sxs-lookup"><span data-stu-id="27902-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="27902-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="27902-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27902-111">In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheits-und Sicherheitsrichtlinien und-Verfahren verstehen, die im [rSSD-Entfernungs Leit Faden für Unternehmen](https://www.microsoft.com/download/100440)beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="27902-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="27902-112">Vorbereiten der SSD-Entfernung</span><span class="sxs-lookup"><span data-stu-id="27902-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="27902-113">Installieren der neuesten Updates</span><span class="sxs-lookup"><span data-stu-id="27902-113">Install the latest updates</span></span> 

<span data-ttu-id="27902-114">Bevor Sie beginnen, stellen Sie sicher, dass Ihre Version von Windows über die neuesten Updates verfügt.</span><span class="sxs-lookup"><span data-stu-id="27902-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="27902-115">Wechseln Sie zu **Start**  >  **Settings**  >  **Update & Security** , und wählen Sie auf **Updates überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="27902-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="27902-116">Installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="27902-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="27902-117">Vergewissern Sie sich, dass für den Zugriff auf das Gerät Kennwörter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="27902-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="27902-118">Verwalten von BitLocker</span><span class="sxs-lookup"><span data-stu-id="27902-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="27902-119">Dieser Abschnitt enthält Empfehlungen für Organisationen, die die BitLocker-Verschlüsselung für Festplatten aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="27902-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="27902-120">Weitere Informationen finden Sie im [BitLocker-Wiederherstellungs Handbuch](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="27902-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="27902-121">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="27902-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="27902-122">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt sein kann, führen Sie die folgenden Schritte aus, um BitLocker zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="27902-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="27902-123">Geben **Settings**Sie in Einstellungen **BitLocker** ein, und wählen Sie **BitLocker verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="27902-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="27902-124">Wählen Sie **BitLocker deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="27902-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="27902-125">Schalten Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="27902-125">Power down the device.</span></span> 

### <span data-ttu-id="27902-126">Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="27902-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="27902-127">Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker-Wiederherstellungsschlüssel zu generieren und ihn auf einem USB-Speicher zu speichern:</span><span class="sxs-lookup"><span data-stu-id="27902-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="27902-128">Wechseln Sie zu **Einstellungen** , und geben Sie **BitLocker**ein.</span><span class="sxs-lookup"><span data-stu-id="27902-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="27902-129">Wählen Sie **BitLocker**  > -**Wiederherstellungsschlüssel generieren BitLocker**verwalten aus.</span><span class="sxs-lookup"><span data-stu-id="27902-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="27902-130">Legen Sie ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="27902-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="27902-131">Speichern Sie den Wiederherstellungsschlüssel in einem USB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="27902-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="27902-132">Entfernen Sie das USB-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="27902-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="27902-133">Schalten Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="27902-133">Power down the device.</span></span> 

## <span data-ttu-id="27902-134">Entfernen und Ersetzen der SSD</span><span class="sxs-lookup"><span data-stu-id="27902-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="27902-135">Entfernen Sie die SSD mithilfe der Anweisungen im [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="27902-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="27902-136">Legen Sie die ursprüngliche SSD auf einem neuen Gerät ab, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="27902-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="27902-137">Schalten Sie das neue Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="27902-137">Power on the new device.</span></span> <span data-ttu-id="27902-138">Das Gerät kann während des Starts eine Firmware-Aktualisierung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="27902-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="27902-139">Nach dem Entfernen und Ersetzen von SSD</span><span class="sxs-lookup"><span data-stu-id="27902-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="27902-140">Verwalten von unverschlüsselten SSDs</span><span class="sxs-lookup"><span data-stu-id="27902-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="27902-141">Wenn die SSD während der Übertragung unverschlüsselt bleibt, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="27902-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="27902-142">Wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (als Schlüsselsymbol auf der linken Seite dargestellt).</span><span class="sxs-lookup"><span data-stu-id="27902-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="27902-143">Geben Sie das Kennwort ein, und melden Sie sich bis zum Abschluss der zweistufigen Authentifizierung an (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="27902-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="27902-144">Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zum Konto **Start**  >  **Account**  >  **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="27902-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="27902-145">Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="27902-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="27902-146">Wenn das Gerät BitLocker-deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Ersatz aktivieren möchten, wechseln Sie zu **BitLocker**BitLocker-BitLocker-  >  **Manage Bitlocker**  >  **Lebenslauf**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="27902-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="27902-147">Führen **Sie** "mit", um die vollständige Gerätefunktionalität zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="27902-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="27902-148">Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="27902-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="27902-149">Wenn Fehlermeldungen auftreten, wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="27902-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="27902-150">Überprüfen Sie das Office-Konto, indem Sie die **Office-App**öffnen, dann zu **Datei**  >  **Konto** navigieren und auf Fehlermeldungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="27902-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="27902-151">Verwalten von verschlüsselten SSDs</span><span class="sxs-lookup"><span data-stu-id="27902-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="27902-152">Sie benötigen ein zweites Gerät zum Lesen des BitLocker-Wiederherstellungsschlüssels, der auf dem USB-Laufwerk gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="27902-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="27902-153">Wenn die SSD während der Übertragung verschlüsselt blieb, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="27902-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="27902-154">Legen Sie das USB-Laufwerk mit dem BitLocker-Wiederherstellungsschlüssel in das zweite Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="27902-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="27902-155">Öffnen Sie die txt-Datei, die den BitLocker-Wiederherstellungsschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="27902-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="27902-156">Geben Sie den BitLocker-Wiederherstellungsschlüssel manuell in das neue Gerät ein, das die ursprüngliche SSD enthält.</span><span class="sxs-lookup"><span data-stu-id="27902-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="27902-157">Nachdem Sie den BitLocker-Wiederherstellungsschlüssel erfolgreich eingegeben haben, wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (dargestellt durch das Schlüsselsymbol auf der linken Seite).</span><span class="sxs-lookup"><span data-stu-id="27902-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="27902-158">Geben Sie das Kennwort ein, und melden Sie sich an, bis zum Abschluss der zweistufigen Authentifizierung (falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="27902-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="27902-159">Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zum Konto **Start**  >  **Account**  >  **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="27902-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="27902-160">Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello ein, und fügen Sie eine PIN hinzu.</span><span class="sxs-lookup"><span data-stu-id="27902-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="27902-161">Wenn das Gerät BitLocker-deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Ersatz aktivieren möchten, wechseln Sie zu **Einstellungen**BitLocker-BitLocker-BitLocker-  >  **Bitlocker**  >  **Manage Bitlocker**  >  **Lebenslauf**-BitLocker.</span><span class="sxs-lookup"><span data-stu-id="27902-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="27902-162">Führen **Sie** "mit", um die vollständige Gerätefunktionalität zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="27902-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="27902-163">Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="27902-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="27902-164">Wenn Fehlermeldungen auftreten, wählen Sie **Problembehandlung**aus.</span><span class="sxs-lookup"><span data-stu-id="27902-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="27902-165">Um das Office-Konto zu überprüfen, öffnen Sie die **Office-App**, wechseln Sie dann zu **Datei**  >  **Konto** , und überprüfen Sie, ob Fehlermeldungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="27902-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="27902-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27902-166">More information</span></span> 

<span data-ttu-id="27902-167">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="27902-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="27902-168">rSSD-Entfernungs Leit Faden für Enterprise</span><span class="sxs-lookup"><span data-stu-id="27902-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="27902-169">BitLocker-Wiederherstellungsleitfaden</span><span class="sxs-lookup"><span data-stu-id="27902-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="27902-170">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="27902-170">Still need help?</span></span> <span data-ttu-id="27902-171">Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="27902-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>