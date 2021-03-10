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
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a>Melden Sie sich bei Surface Hub mit Microsoft Authenticator an

Personen in Ihrem Unternehmen können sich auf einem Surface Hub ohne Kennwort mithilfe der Microsoft Authenticator-App auf Android und iOS anmelden.

## <a name="organization-prerequisites"></a>Voraussetzungen für die Organisation

Wenn Personen in Ihrer Organisation sich auf Surface Hub mit ihrem Handy und anderen Geräten anstelle eines Kennworts anmelden möchten, müssen Sie sicherstellen, dass Ihre Organisation folgende Voraussetzungen erfüllt: 

- Bei Ihrer Organisation muss es sich um einen hybride oder Nur-Cloud-Organisation handeln, die über Azure Active Directory (Azure AD) gesichert ist. Weitere Informationen finden Sie unter [Was ist Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)

- Stellen Sie sicher, dass Sie mindestens über ein Office365 E3-Abonnement verfügen. 

- [Mehrstufige Authentifizierung konfigurieren](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings). Stellen Sie sicher, dass **Benachrichtigung über die mobile Anwendung** ausgewählt ist. 

    ![Multi-Factor Authentication-Optionen](images/mfa-options.png)

- Aktivieren des Inhaltshostings auf Azure AD-Diensten wie Office, SharePoint usw. 

- Surface Hub muss Windows10, Version 1703 oder höher ausführen.

- Surface Hub ist mit einem lokalen oder mit einer Domäne verbundenen Konto eingerichtet.

## <a name="individual-prerequisites"></a>Einzelne Voraussetzungen

- Eine Android-Telefon mit 6.0 oder höher, oder ein iPhone oder iPad mit iOS9 oder höher 

- Die neueste Version der Microsoft Authenticator-App aus dem entsprechenden App Store

    >[!NOTE]
    >Unter iOS muss die App-Version 5.4.0 oder höher sein.
    >
    >Die Microsoft Authenticator-App auf Smartphones mit einem Windows-Betriebssystem kann nicht zum Anmelden auf Surface Hub verwendet werden.

- Kennung oder Sperrbildschirm muss auf Ihrem Gerät aktiviert sein

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a>So richten Sie die Microsoft Authenticator-App ein

>[!NOTE]
>Wenn das Unternehmensportal auf Ihrem Android-Gerät installiert ist, deinstallieren Sie es vor dem Einrichten von Microsoft Authenticator. Nachdem Sie die App eingerichtet haben, können Sie das Unternehmensportal neu installieren.
>
>Wenn Sie Microsoft Authenticator bereits auf Ihrem Telefon eingerichtet und Ihr Gerät registriert haben, fahren Sie mit den Anweisungen zur Anmeldung fort.

1. Fügen Sie Ihr Geschäfts- oder Schulkonto Microsoft Authenticator für Multi-Factor Authentication hinzu. Sie benötigen einen QR-Code, der von der IT-Abteilung bereitgestellt wird. Hilfe finden Sie unter [Erste Schritte mit der Microsoft Authenticator-App](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).
2. Wechseln Sie zu **Einstellungen** und registrieren Sie Ihr Gerät.
3. Wechseln Sie auf die Seite "Konten" zurück und wählen Sie **Aktivieren der telefonbasierten Anmeldung** aus dem Dropdownmenü des Kontos aus.

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a>Vorgehensweise beim Anmelden auf Surface Hub während einer Besprechung

1. Nachdem Sie eine Besprechung eingerichtet haben, wechseln Sie zu Surface Hub und wählen Sie **Anmelden, um Ihre Besprechungen und Dateien zu sehen** aus.

    >[!NOTE]
    >Wenn Sie nicht wissen, wie Sie eine Besprechung auf einem Surface Hub planen, finden Sie Informationen unter [Planen einer Besprechung auf Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).

    ![Screenshot der Anmeldeoptionen auf Surface Hub](images/sign-in.png)

2. Sie sehen eine Liste der Personen, die zu der Besprechung eingeladen sind. Wählen Sie Ihre eigene Person aus (oder die Person, die sich anmelden möchte – stellen Sie sicher, dass diese Person alle Schritte zum Einrichten des Geräts vor der Besprechung durchgeführt hat), und wählen Sie dann **Weiter**.

    ![Screenshot der Liste der Teilnehmer einer Besprechung](images/attendees.png)

    Sie sehen einen Code auf dem Surface Hub.

    ![Screenshot des Codes für die Anmeldegenehmigung](images/approve-signin.png)

3. Um die Anmeldung zu genehmigen, öffnen Sie die Authenticator-App, geben Sie den vierstelligen Code ein, der auf dem Surface Hub angezeigt wird und wählen Sie **Genehmigen** aus. Sie werden dann aufgefordert, den PIN oder Fingerabdruck einzugeben, um die Anmeldung abzuschließen. 

    ![Screenshot des Bildschirms für die Anmeldegenehmigung in Microsoft Authenticator](images/approve-signin2.png)

Sie können jetzt auf alle Dateien über die OneDrive-App zugreifen.
