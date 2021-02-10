---
title: Konfigurieren des Android Enterprise-Arbeitsprofils für Surface Duo
description: In diesem Artikel wird das Einrichten eines Arbeitsprofils auf Surface Duo erläutert.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326175"
---
# <span data-ttu-id="f0a9c-103">Konfigurieren des Android Enterprise-Arbeitsprofils für Surface Duo</span><span class="sxs-lookup"><span data-stu-id="f0a9c-103">Configure Android Enterprise Work Profile for Surface Duo</span></span>

<span data-ttu-id="f0a9c-104">Arbeitsprofile, die auf die Bereitstellung von BYOD ausgerichtet sind, bieten auf Duo einen separaten Platz für Arbeits-Apps und -Daten, damit Organisationen die vollständige Kontrolle über ihre Daten, Apps und Sicherheitsrichtlinien haben, ohne dass Mitarbeiter ihr Gerät für persönliche Apps und Daten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-104">Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.</span></span>

### <span data-ttu-id="f0a9c-105">Einrichten des Android Enterprise-Arbeitsprofils</span><span class="sxs-lookup"><span data-stu-id="f0a9c-105">Set up Android Enterprise Work Profile</span></span>

<span data-ttu-id="f0a9c-106">Verwenden Sie Arbeitsprofile zum Verwalten von Unternehmensdaten und Apps auf Geräten im Besitz des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-106">Use work profiles to manage corporate data and apps on user-owned Android devices.</span></span> <span data-ttu-id="f0a9c-107">Standardmäßig ist die Registrierung von persönlichen Arbeitsprofilgeräten aktiviert und erfordert keine weitere Administratorkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-107">By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.</span></span>  

**<span data-ttu-id="f0a9c-108">So aktivieren Sie das Unternehmensarbeitsprofil:</span><span class="sxs-lookup"><span data-stu-id="f0a9c-108">To enable Enterprise Work Profile:</span></span>**

- <span data-ttu-id="f0a9c-109">Wählen Sie im \*\*\*\* Endpunkt-Manager  >  **"Geräte Android**  >  **Android-Registrierung"** und dann **"Persönliche Geräte mit Arbeitsprofil" aus.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-109">In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.</span></span>
<br><br>
 ![Aktivieren des Unternehmensarbeitsprofils](images/enroll-start.png)

 
**<span data-ttu-id="f0a9c-111">Anmelden bei Surface Duo mit dem Android Enterprise Work Profile</span><span class="sxs-lookup"><span data-stu-id="f0a9c-111">Sign into Surface Duo with Android Enterprise Work Profile</span></span>**

1. <span data-ttu-id="f0a9c-112">Installieren Sie die Unternehmensportal-App aus dem Google Play Store, und melden Sie sich mit Ihrem Microsoft-Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-112">Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.</span></span><br><br>
![Anmelden bei Surface Duo](images/duo-wp-1.png)
 
2. <span data-ttu-id="f0a9c-114">Wählen Sie auf der Seite "Access-Setup" die Option **"Beginnen" aus.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-114">On the Access Setup page, select **Begin**.</span></span><br><br>
![Begin](images/duo-wp-2.png)

3. <span data-ttu-id="f0a9c-116">Überprüfen Sie die Informationen auf der Seite "Datenschutz", und wählen Sie **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="f0a9c-116">Review the information on the privacy page and select **Continue**.</span></span><br><br>
 ![Weiter](images/duo-wp-3.png)
<br><br>
 ![Wählen Sie "Weiter" aus.](images/duo-wp-4.png)
 
4. <span data-ttu-id="f0a9c-119">Wenn das Setup des Arbeitsprofils abgeschlossen ist, wählen **Sie "Weiter** aktivieren" aus, und registrieren Sie das Gerät.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-119">When the work profile setup completes, select **Continue** to activate and register the device.</span></span><br><br>
 ![Wählen Sie "Weiter aktivieren" aus, und registrieren Sie das Gerät.](images/duo-wp-5.png)

5. <span data-ttu-id="f0a9c-121">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-121">Select **Continue**.</span></span><br><br>
 ![Wählen Sie erneut "Weiter" aus.](images/duo-wp-6.png)

6. <span data-ttu-id="f0a9c-123">Wenn Sie das Arbeitsprofil aktiviert haben, wählen **Sie "Weiter** zum Aktualisieren der Geräteeinstellungen" aus.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-123">When you have activated the work profile, select **Continue** to update device settings.</span></span> <span data-ttu-id="f0a9c-124">In diesem Beispiel wendet das Arbeitsprofil eine MDM-Einstellung an, um ein stärkeres alphanumerisches Kennwort mit 6 Ziffern zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-124">In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password.</span></span> <br><br>

     ![Beispiel für ein alphanumerisches Kennwort](images/duo-wp-7.png)<br><br>
7. <span data-ttu-id="f0a9c-126">Wählen **Sie "Auflösen"** aus, um die erforderliche Authentifizierung ein, und wählen Sie dann **"Weiter,** um die Einrichtung des Arbeitsprofils abzuschließen" aus.</span><span class="sxs-lookup"><span data-stu-id="f0a9c-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span></span> <br><br>
     ![Select continue to complete setup](images/duo-wp-8.png)<br><br>
     ![Abschließen des Setups](images/duo-wp-9.png)<br><br>

## <span data-ttu-id="f0a9c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0a9c-129">Learn more</span></span>

- [<span data-ttu-id="f0a9c-130">Einrichten der Registrierung von Android Enterprise-Arbeitsprofilgeräten</span><span class="sxs-lookup"><span data-stu-id="f0a9c-130">Set up enrollment of Android Enterprise work profile devices</span></span>](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

