---
title: Konfigurieren der Kenn Wort losen Anmeldung auf Surface Hub
description: Hier erfahren Sie, wie Sie die Anmeldung bei Surface Hub vereinfachen.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893047"
---
# <span data-ttu-id="a65d1-104">Konfigurieren der kennwortbasierten Anmeldung auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a65d1-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="a65d1-105">Durch die Kenn Wort lose Anmeldung wird der Zugriff auf Ihre apps, Besprechungen und Dateien vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="a65d1-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="a65d1-106">Surface Hub unterstützt die Anmeldung mit der Microsoft Authenticator-APP und den FIDO2-Sicherheitsschlüsseln, die von Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a65d1-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="a65d1-107">**Wichtig:** Dieser Inhalt ist für Benutzer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a65d1-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="a65d1-108">Wenn Sie die Kenn Wort lose Anmeldung verwenden möchten, muss Ihr IT-Administrator die kennwortgeschützte Authentifizierung für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a65d1-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="a65d1-109">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a65d1-109">For more information, see:</span></span>

- [<span data-ttu-id="a65d1-110">Aktivieren der Anmeldefunktion für das kennwortgeschützte Telefon</span><span class="sxs-lookup"><span data-stu-id="a65d1-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="a65d1-111">Aktivieren der Kennwortsicherheit bei der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="a65d1-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="a65d1-112">Konfigurieren der Anmeldung mit der Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="a65d1-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="a65d1-113">**Hinweis:** Ab Windows 10 Team 2020-Update können Benutzer Ihre bevorzugten e-Mail-Aliase in Azure AD sowie deren Benutzerprinzipalnamen (User Principal Name, UPN) verwenden, um sich mit Microsoft Authenticator zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="a65d1-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="a65d1-114">Beispielsweise kann ein Benutzer entweder seinen bevorzugten Alias (John.Doe@contoso.com) oder seinen UPN (jdoe@contoso.com) für die Anmeldung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a65d1-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="a65d1-115">Die Microsoft Authenticator-App unterstützt Sie bei der Anmeldung bei Surface Hub mithilfe Ihres mobilen Geräts.</span><span class="sxs-lookup"><span data-stu-id="a65d1-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="a65d1-116">So konfigurieren Sie die Anmeldung mit Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="a65d1-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="a65d1-117">Laden Sie die Microsoft Authenticator-App auf Ihrem mobilen Gerät herunter.</span><span class="sxs-lookup"><span data-stu-id="a65d1-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="a65d1-118">Google Android: Wechseln Sie auf Ihrem Android-Gerät zu Google Play, um [die Microsoft Authenticator-APP herunterzuladen und zu installieren](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span><span class="sxs-lookup"><span data-stu-id="a65d1-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="a65d1-119">Apple ios: Wechseln Sie auf Ihrem Apple IOS-Gerät zum App Store, um [die Microsoft Authenticator-APP herunterzuladen und zu installieren](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span><span class="sxs-lookup"><span data-stu-id="a65d1-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="a65d1-120">Richten Sie auf Ihrem PC [die Microsoft Authenticator-App auf der Seite "Sicherheitsinformationen"](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) für Ihr Geschäfts-oder Schulkonto ein.</span><span class="sxs-lookup"><span data-stu-id="a65d1-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="a65d1-121">Aktivieren Sie die Microsoft Authenticator-App auf Ihrem mobilen Gerät, [und verwenden Sie die Telefonanmeldung](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) für Ihr Geschäfts-oder Schulkonto.</span><span class="sxs-lookup"><span data-stu-id="a65d1-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="a65d1-122">Konfigurieren der Anmeldung mithilfe von FIDO2-Sicherheitsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="a65d1-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="a65d1-123">Die Kenn Wort lose Anmeldung auf Surface Hub mithilfe von FIDO2-Sicherheitsschlüsseln erfordert das Windows 10 Team 2020-Update.</span><span class="sxs-lookup"><span data-stu-id="a65d1-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a65d1-124">Surface Hub unterstützt nur USB-Sicherheits Tasten.</span><span class="sxs-lookup"><span data-stu-id="a65d1-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="a65d1-125">Sie können sich auch mit einem von Ihrer Organisation bereitgestellten FIDO2-Sicherheitsschlüssel bei Surface Hub anmelden.</span><span class="sxs-lookup"><span data-stu-id="a65d1-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="a65d1-126">So konfigurieren Sie die Anmeldung mit einem Sicherheitsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="a65d1-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="a65d1-127">Wechseln Sie auf Ihrem PC zu Ihrer [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) Seite, und registrieren Sie sich bei Ihrem Firmen-oder Schulkonto.</span><span class="sxs-lookup"><span data-stu-id="a65d1-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="a65d1-128">Wählen Sie im linken Navigationsbereich oder über den Link im **Sicherheits Informations** Block **Sicherheitsinformationen** aus, und wählen Sie dann auf der Seite **Sicherheitsinformationen** die Option **Methode hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a65d1-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="a65d1-129">Wählen Sie auf der Seite **Methode hinzufügen** in der Dropdownliste den Eintrag **Sicherheitsschlüssel** aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a65d1-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="a65d1-130">Wählen Sie auf der Seite **Sicherheitsschlüssel** die Option **USB-Gerät**aus.</span><span class="sxs-lookup"><span data-stu-id="a65d1-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="a65d1-131">Halten Sie Ihren Sicherheitsschlüssel bereit, und wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a65d1-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="a65d1-132">Befolgen Sie in dem nun angezeigten Dialogfeld die Anweisungen, um den Sicherheitsschlüssel einzufügen, eine PIN zu erstellen oder einzugeben, und führen Sie die erforderliche Geste aus (entweder biometrische oder Fingereingabe).</span><span class="sxs-lookup"><span data-stu-id="a65d1-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="a65d1-133">Geben Sie auf der Seite **Sicherheitsschlüssel** Ihrem Sicherheitsschlüssel einen Namen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a65d1-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="a65d1-134">Wählen Sie **Fertig** aus, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a65d1-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="a65d1-135">Anmelden beim Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a65d1-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="a65d1-136">Nachdem Sie die Kenn Wort lose Anmeldung konfiguriert haben, können Sie Sie verwenden, um den Zugriff auf Ihre apps, Besprechungen und Dateien auf dem Surface Hub zu vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="a65d1-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="a65d1-137">Nehmen Sie schnell an Ihren Besprechungen Teil und öffnen Sie die zuletzt verwendeten Microsoft 365-Dateien.</span><span class="sxs-lookup"><span data-stu-id="a65d1-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="a65d1-138">Weitere Informationen finden Sie unter [**anmelden, um Ihre Besprechungen und Dateien anzuzeigen**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span><span class="sxs-lookup"><span data-stu-id="a65d1-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="a65d1-139">Sie können sich schnell bei Microsoft-apps wie Whiteboard, PowerPoint, Word, Excel, OneDrive und Power BI anmelden.</span><span class="sxs-lookup"><span data-stu-id="a65d1-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="a65d1-140">Sie können sich schnell beim neuen Microsoft Edge anmelden, um auf Ihre Favoriten und Browsereinstellungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a65d1-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="a65d1-141">Weitere Informationen finden Sie unter [Installieren und Konfigurieren des neuen Microsoft Edge](surface-hub-install-chromium-edge.md).</span><span class="sxs-lookup"><span data-stu-id="a65d1-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="a65d1-142">Nachdem Sie sich bei Surface Hub angemeldet haben, können Sie andere apps verwenden, ohne sich erneut anmelden zu müssen, bis Sie **Sitzung beenden**auswählen.</span><span class="sxs-lookup"><span data-stu-id="a65d1-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="a65d1-143">Wenn Sie **Sitzung beenden** auswählen, werden Ihre Anmeldeinformationen, Dateien und persönlichen Daten auf dem Gerät gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a65d1-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="a65d1-144">Weitere Informationen finden Sie unter [Beenden der Sitzung](finishing-your-surface-hub-meeting.md).</span><span class="sxs-lookup"><span data-stu-id="a65d1-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="a65d1-145">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="a65d1-145">Learn more</span></span>

- [<span data-ttu-id="a65d1-146">Kennwortlos-Authentifizierungsoptionen für Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a65d1-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="a65d1-147">Kenn Wort lose Anmeldung mit der Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="a65d1-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="a65d1-148">Kenn Wort lose Anmeldung mithilfe von FIDO2-Sicherheitsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="a65d1-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

