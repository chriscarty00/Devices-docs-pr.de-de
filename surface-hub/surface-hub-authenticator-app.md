---
title: Melden Sie sich bei Surface Hub mit Microsoft Authenticator an
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
ms.openlocfilehash: f8a2bf8ddb75ca6dd3ff89e16fe0d37e099be29d
ms.sourcegitcommit: 85f5a2e67b34fe073ec588ed441ebee239ab0ac6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400736"
---
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a><span data-ttu-id="20d6f-103">Melden Sie sich bei Surface Hub mit Microsoft Authenticator an</span><span class="sxs-lookup"><span data-stu-id="20d6f-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="20d6f-104">Personen in Ihrem Unternehmen können sich auf einem Surface Hub ohne Kennwort mithilfe der Microsoft Authenticator-App auf Android und iOS anmelden.</span><span class="sxs-lookup"><span data-stu-id="20d6f-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <a name="organization-prerequisites"></a><span data-ttu-id="20d6f-105">Voraussetzungen für die Organisation</span><span class="sxs-lookup"><span data-stu-id="20d6f-105">Organization prerequisites</span></span>

<span data-ttu-id="20d6f-106">Wenn Personen in Ihrer Organisation sich auf Surface Hub mit ihrem Handy und anderen Geräten anstelle eines Kennworts anmelden möchten, müssen Sie sicherstellen, dass Ihre Organisation folgende Voraussetzungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="20d6f-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="20d6f-107">Bei Ihrer Organisation muss es sich um einen hybride oder Nur-Cloud-Organisation handeln, die über Azure Active Directory (Azure AD) gesichert ist.</span><span class="sxs-lookup"><span data-stu-id="20d6f-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="20d6f-108">Weitere Informationen finden Sie unter [Was ist Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="20d6f-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="20d6f-109">Stellen Sie sicher, dass Sie mindestens über ein Office365 E3-Abonnement verfügen.</span><span class="sxs-lookup"><span data-stu-id="20d6f-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="20d6f-110">[Mehrstufige Authentifizierung konfigurieren](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="20d6f-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="20d6f-111">Stellen Sie sicher, dass **Benachrichtigung über die mobile Anwendung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="20d6f-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![Multi-Factor Authentication-Optionen](images/mfa-options.png)

- <span data-ttu-id="20d6f-113">Aktivieren des Inhaltshostings auf Azure AD-Diensten wie Office, SharePoint usw.</span><span class="sxs-lookup"><span data-stu-id="20d6f-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="20d6f-114">Surface Hub muss Windows10, Version 1703 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="20d6f-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="20d6f-115">Surface Hub ist mit einem lokalen oder mit einer Domäne verbundenen Konto eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="20d6f-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

## <a name="individual-prerequisites"></a><span data-ttu-id="20d6f-116">Einzelne Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="20d6f-116">Individual prerequisites</span></span>

- <span data-ttu-id="20d6f-117">Eine Android-Telefon mit 6.0 oder höher, oder ein iPhone oder iPad mit iOS9 oder höher</span><span class="sxs-lookup"><span data-stu-id="20d6f-117">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="20d6f-118">Die neueste Version der Microsoft Authenticator-App aus dem entsprechenden App Store</span><span class="sxs-lookup"><span data-stu-id="20d6f-118">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="20d6f-119">Unter iOS muss die App-Version 5.4.0 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="20d6f-119">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="20d6f-120">Die Microsoft Authenticator-App auf Smartphones mit einem Windows-Betriebssystem kann nicht zum Anmelden auf Surface Hub verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20d6f-120">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="20d6f-121">Kennung oder Sperrbildschirm muss auf Ihrem Gerät aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="20d6f-121">Passcode or screen lock on your device is enabled</span></span>

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a><span data-ttu-id="20d6f-122">So richten Sie die Microsoft Authenticator-App ein</span><span class="sxs-lookup"><span data-stu-id="20d6f-122">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="20d6f-123">Wenn das Unternehmensportal auf Ihrem Android-Gerät installiert ist, deinstallieren Sie es vor dem Einrichten von Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="20d6f-123">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="20d6f-124">Nachdem Sie die App eingerichtet haben, können Sie das Unternehmensportal neu installieren.</span><span class="sxs-lookup"><span data-stu-id="20d6f-124">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="20d6f-125">Wenn Sie Microsoft Authenticator bereits auf Ihrem Telefon eingerichtet und Ihr Gerät registriert haben, fahren Sie mit den Anweisungen zur Anmeldung fort.</span><span class="sxs-lookup"><span data-stu-id="20d6f-125">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="20d6f-126">Fügen Sie Ihr Geschäfts- oder Schulkonto Microsoft Authenticator für Multi-Factor Authentication hinzu.</span><span class="sxs-lookup"><span data-stu-id="20d6f-126">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="20d6f-127">Sie benötigen einen QR-Code, der von der IT-Abteilung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="20d6f-127">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="20d6f-128">Hilfe finden Sie unter [Erste Schritte mit der Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span><span class="sxs-lookup"><span data-stu-id="20d6f-128">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="20d6f-129">Wechseln Sie zu **Einstellungen** und registrieren Sie Ihr Gerät.</span><span class="sxs-lookup"><span data-stu-id="20d6f-129">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="20d6f-130">Wechseln Sie auf die Seite "Konten" zurück und wählen Sie **Aktivieren der telefonbasierten Anmeldung** aus dem Dropdownmenü des Kontos aus.</span><span class="sxs-lookup"><span data-stu-id="20d6f-130">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a><span data-ttu-id="20d6f-131">Vorgehensweise beim Anmelden auf Surface Hub während einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="20d6f-131">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="20d6f-132">Nachdem Sie eine Besprechung eingerichtet haben, wechseln Sie zu Surface Hub und wählen Sie **Anmelden, um Ihre Besprechungen und Dateien zu sehen** aus.</span><span class="sxs-lookup"><span data-stu-id="20d6f-132">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="20d6f-133">Wenn Sie nicht wissen, wie Sie eine Besprechung auf einem Surface Hub planen, finden Sie Informationen unter [Planen einer Besprechung auf Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span><span class="sxs-lookup"><span data-stu-id="20d6f-133">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![Screenshot der Anmeldeoptionen auf Surface Hub](images/sign-in.png)

2. <span data-ttu-id="20d6f-135">Sie sehen eine Liste der Personen, die zu der Besprechung eingeladen sind.</span><span class="sxs-lookup"><span data-stu-id="20d6f-135">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="20d6f-136">Wählen Sie Ihre eigene Person aus (oder die Person, die sich anmelden möchte – stellen Sie sicher, dass diese Person alle Schritte zum Einrichten des Geräts vor der Besprechung durchgeführt hat), und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="20d6f-136">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![Screenshot der Liste der Teilnehmer einer Besprechung](images/attendees.png)

    <span data-ttu-id="20d6f-138">Sie sehen einen Code auf dem Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="20d6f-138">You'll see a code on the Surface Hub.</span></span>

    ![Screenshot des Codes für die Anmeldegenehmigung](images/approve-signin.png)

3. <span data-ttu-id="20d6f-140">Um die Anmeldung zu genehmigen, öffnen Sie die Authenticator-App, geben Sie den vierstelligen Code ein, der auf dem Surface Hub angezeigt wird und wählen Sie **Genehmigen** aus.</span><span class="sxs-lookup"><span data-stu-id="20d6f-140">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="20d6f-141">Sie werden dann aufgefordert, den PIN oder Fingerabdruck einzugeben, um die Anmeldung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="20d6f-141">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![Screenshot des Bildschirms für die Anmeldegenehmigung in Microsoft Authenticator](images/approve-signin2.png)

<span data-ttu-id="20d6f-143">Sie können jetzt auf alle Dateien über die OneDrive-App zugreifen.</span><span class="sxs-lookup"><span data-stu-id="20d6f-143">You can now access all files through the OneDrive app.</span></span>
