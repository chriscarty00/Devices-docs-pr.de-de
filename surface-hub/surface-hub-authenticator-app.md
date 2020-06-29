---
title: Anmelden bei Surface Hub mit Microsoft Authenticator
description: Verwenden Sie Microsoft Authenticator zum Anmelden auf Surface Hub auf Ihrem mobilen Gerät.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832959"
---
# <span data-ttu-id="7e821-103">Melden Sie sich bei Surface Hub mit Microsoft Authenticator an</span><span class="sxs-lookup"><span data-stu-id="7e821-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="7e821-104">Personen in Ihrem Unternehmen können sich auf einem Surface Hub ohne Kennwort mithilfe der Microsoft Authenticator-App auf Android und iOS anmelden.</span><span class="sxs-lookup"><span data-stu-id="7e821-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <span data-ttu-id="7e821-105">Voraussetzungen für die Organisation</span><span class="sxs-lookup"><span data-stu-id="7e821-105">Organization prerequisites</span></span>

<span data-ttu-id="7e821-106">Wenn Personen in Ihrer Organisation sich auf Surface Hub mit ihrem Handy und anderen Geräten anstelle eines Kennworts anmelden möchten, müssen Sie sicherstellen, dass Ihre Organisation folgende Voraussetzungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="7e821-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="7e821-107">Bei Ihrer Organisation muss es sich um einen hybride oder Nur-Cloud-Organisation handeln, die über Azure Active Directory (Azure AD) gesichert ist.</span><span class="sxs-lookup"><span data-stu-id="7e821-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7e821-108">Weitere Informationen finden Sie unter [Was ist Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="7e821-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="7e821-109">Stellen Sie sicher, dass Sie mindestens über ein Office365 E3-Abonnement verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e821-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="7e821-110">[Mehrstufige Authentifizierung konfigurieren](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="7e821-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="7e821-111">Stellen Sie sicher, dass **Benachrichtigung über die mobile Anwendung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7e821-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![Multi-Factor Authentication-Optionen](images/mfa-options.png)

- <span data-ttu-id="7e821-113">Aktivieren von Inhalts Hosting auf Azure AD Services wie Office, SharePoint usw.</span><span class="sxs-lookup"><span data-stu-id="7e821-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="7e821-114">Surface Hub muss Windows10, Version 1703 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="7e821-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="7e821-115">Surface Hub ist mit einem lokalen oder mit einer Domäne verbundenen Konto eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="7e821-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

<span data-ttu-id="7e821-116">Derzeit können Sie Microsoft Authenticator nicht verwenden, um sich auf Surface Hubs anzumelden, die mit Azure AD verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="7e821-116">Currently, you cannot use Microsoft Authenticator to sign in to Surface Hubs that are joined to Azure AD.</span></span>

## <span data-ttu-id="7e821-117">Einzelne Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7e821-117">Individual prerequisites</span></span>

- <span data-ttu-id="7e821-118">Eine Android-Telefon mit 6.0 oder höher, oder ein iPhone oder iPad mit iOS9 oder höher</span><span class="sxs-lookup"><span data-stu-id="7e821-118">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="7e821-119">Die neueste Version der Microsoft Authenticator-App aus dem entsprechenden App Store</span><span class="sxs-lookup"><span data-stu-id="7e821-119">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="7e821-120">Unter iOS muss die App-Version 5.4.0 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="7e821-120">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="7e821-121">Die Microsoft Authenticator-App auf Smartphones mit einem Windows-Betriebssystem kann nicht zum Anmelden auf Surface Hub verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e821-121">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="7e821-122">Kennung oder Sperrbildschirm muss auf Ihrem Gerät aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="7e821-122">Passcode or screen lock on your device is enabled</span></span>

- <span data-ttu-id="7e821-123">Eine gültige SMTP-E-Mail-Adresse (Beispiel: joe@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7e821-123">A standard SMTP email address (example: joe@contoso.com).</span></span> <span data-ttu-id="7e821-124">Nicht standardmäßige oder Vanity-SMTP-E-Mail-Adressen (Beispiel: firstname.lastname@contoso.com) funktionieren derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="7e821-124">Non-standard or vanity SMTP email addresses (example: firstname.lastname@contoso.com) currently don’t work.</span></span>

## <span data-ttu-id="7e821-125">So richten Sie die Microsoft Authenticator-App ein</span><span class="sxs-lookup"><span data-stu-id="7e821-125">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="7e821-126">Wenn das Unternehmensportal auf Ihrem Android-Gerät installiert ist, deinstallieren Sie es vor dem Einrichten von Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="7e821-126">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="7e821-127">Nachdem Sie die App eingerichtet haben, können Sie das Unternehmensportal neu installieren.</span><span class="sxs-lookup"><span data-stu-id="7e821-127">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="7e821-128">Wenn Sie Microsoft Authenticator bereits auf Ihrem Telefon eingerichtet und Ihr Gerät registriert haben, fahren Sie mit den Anweisungen zur Anmeldung fort.</span><span class="sxs-lookup"><span data-stu-id="7e821-128">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="7e821-129">Fügen Sie Ihr Geschäfts- oder Schulkonto Microsoft Authenticator für Multi-Factor Authentication hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e821-129">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="7e821-130">Sie benötigen einen QR-Code, der von der IT-Abteilung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7e821-130">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="7e821-131">Hilfe finden Sie unter [Erste Schritte mit der Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span><span class="sxs-lookup"><span data-stu-id="7e821-131">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="7e821-132">Wechseln Sie zu **Einstellungen** und registrieren Sie Ihr Gerät.</span><span class="sxs-lookup"><span data-stu-id="7e821-132">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="7e821-133">Wechseln Sie auf die Seite "Konten" zurück und wählen Sie **Aktivieren der telefonbasierten Anmeldung** aus dem Dropdownmenü des Kontos aus.</span><span class="sxs-lookup"><span data-stu-id="7e821-133">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <span data-ttu-id="7e821-134">Vorgehensweise beim Anmelden auf Surface Hub während einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="7e821-134">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="7e821-135">Nachdem Sie eine Besprechung eingerichtet haben, wechseln Sie zu Surface Hub und wählen Sie **Anmelden, um Ihre Besprechungen und Dateien zu sehen** aus.</span><span class="sxs-lookup"><span data-stu-id="7e821-135">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7e821-136">Wenn Sie nicht wissen, wie Sie eine Besprechung auf einem Surface Hub planen, finden Sie Informationen unter [Planen einer Besprechung auf Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span><span class="sxs-lookup"><span data-stu-id="7e821-136">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![Screenshot der Anmeldeoptionen auf Surface Hub](images/sign-in.png)

2. <span data-ttu-id="7e821-138">Sie sehen eine Liste der Personen, die zu der Besprechung eingeladen sind.</span><span class="sxs-lookup"><span data-stu-id="7e821-138">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="7e821-139">Wählen Sie Ihre eigene Person aus (oder die Person, die sich anmelden möchte – stellen Sie sicher, dass diese Person alle Schritte zum Einrichten des Geräts vor der Besprechung durchgeführt hat), und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e821-139">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![Screenshot der Liste der Teilnehmer einer Besprechung](images/attendees.png)

    <span data-ttu-id="7e821-141">Sie sehen einen Code auf dem Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7e821-141">You'll see a code on the Surface Hub.</span></span>

    ![Screenshot des Codes für die Anmeldegenehmigung](images/approve-signin.png)

3. <span data-ttu-id="7e821-143">Um die Anmeldung zu genehmigen, öffnen Sie die Authenticator-App, geben Sie den vierstelligen Code ein, der auf dem Surface Hub angezeigt wird und wählen Sie **Genehmigen** aus.</span><span class="sxs-lookup"><span data-stu-id="7e821-143">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="7e821-144">Sie werden dann aufgefordert, den PIN oder Fingerabdruck einzugeben, um die Anmeldung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7e821-144">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![Screenshot des Bildschirms für die Anmeldegenehmigung in Microsoft Authenticator](images/approve-signin2.png)

<span data-ttu-id="7e821-146">Sie können jetzt auf alle Dateien über die OneDrive-App zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7e821-146">You can now access all files through the OneDrive app.</span></span>