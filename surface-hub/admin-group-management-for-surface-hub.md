---
title: Administratorgruppenverwaltung
description: Jeder Microsoft Surface Hub kann durch Öffnen der Einstellungs-App auf dem Gerät einzeln konfiguriert werden.
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: Administratorgruppenverwaltung, Einstellungs-App, Surface Hub konfigurieren
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 217567ef310c4288a5073edd1313ce02a633568c
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442849"
---
# <a name="admin-group-management-for-surface-hub"></a>Verwaltung von Administratorgruppen für Surface Hub


Jedes Surface Hub-Gerät kann mithilfe der Einstellungs-App auf dem Gerät lokal konfiguriert werden. Um die Änderung der Einstellungen durch nicht autorisierte Benutzer zu verhindern, sind zum Öffnen der Einstellungs-App Administratoranmeldeinformationen erforderlich.


## <a name="admin-group-management"></a>Administratorgruppenverwaltung

Sie können Administratorkonten für das Gerät auf folgende Weise einrichten:

- [Erstellen eines lokalen Administratorkontos](#create-a-local-admin-account)
- [Domäne wird dem Gerät zu Active Directory beitreten](#domain-join-the-device-to-active-directory)
- [Azure AD wird dem Gerät beitreten](#azure-ad-join-the-device)
- [Konfigurieren nicht globaler Administratorkonten auf Azure AD-geräten (Surface Hub 2S)](#configure-non-global-admin-accounts-on-azure-ad-joined-devices)


### <a name="create-a-local-admin-account"></a>Erstellen eines lokalen Administratorkontos

Verwenden Sie zum Erstellen eines lokalen Administrators [bei der ersten Ausführung einen lokalen Administrator](first-run-program-surface-hub.md#use-a-local-admin). Dadurch wird auf dem Surface Hub ein einzelnes lokales Administratorkonto mit einem Benutzernamen und Kennwort Ihrer Wahl erstellt. Verwenden Sie diese Anmeldeinformationen, um die Einstellungs-App zu öffnen.

Beachten Sie, dass die Informationen des lokalen Administratorkontos nicht von einem Verzeichnisdienst unterstützt werden. Es wird empfohlen, dass Sie nur dann einen lokalen Administrator auswählen, wenn das Gerät nicht auf Active Directory (AD) oder Azure Active Directory (Azure AD) zugreifen kann. Wenn Sie das Kennwort des lokalen Administrators ändern möchten, können Sie dies in den Einstellungen tun. Wenn Sie jedoch von der Verwendung des lokalen Administratorkontos zur Verwendung einer Gruppe aus Ihrer Domäne oder Ihrem Azure AD-Mandanten wechseln möchten, müssen Sie [das Gerät zurückzusetzen](device-reset-surface-hub.md) und das Programm für die erste Ausführung erneut ausführen.

### <a name="domain-join-the-device-to-active-directory"></a>Domäne wird dem Gerät zu Active Directory beitreten

Sie können für den Surface Hub einen Beitritt zu Ihrer AD-Domäne ausführen, um Benutzern aus einer angegebenen Sicherheitsgruppe das Konfigurieren von Einstellungen zu ermöglichen. Wählen Sie bei der ersten Ausführung die Verwendung von [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services) aus. Sie müssen Anmeldeinformationen angeben, die einen Beitritt zur Domäne Ihrer Wahl ermöglichen, sowie den Namen einer vorhandenen Sicherheitsgruppe. Jedes Mitglied dieser Sicherheitsgruppe kann seine Anmeldeinformationen eingeben und die Einstellungen entsperren.

#### <a name="what-happens-when-you-domain-join-your-surface-hub"></a>Was geschieht, wenn Sie einen Domänenbeitritt für den Surface Hub ausführen?
Surface Hubs verwenden Domänenbeitritte zu folgenden Zwecken:
- Gewähren von Administratorrechten für Mitglieder einer angegebenen Sicherheitsgruppe in Active Directory
- Sichern des BitLocker-Wiederherstellungsschlüssels des Geräts durch dessen Speicherung unter dem Computerobjekt in Active Directory Details hierzu finden Sie unter [Speichern des BitLocker-Schlüssels](save-bitlocker-key-surface-hub.md).
- Synchronisieren der Systemuhr mit dem Domänencontroller für verschlüsselte Kommunikation

Surface Hub unterstützt das Anwenden von Gruppenrichtlinien oder Zertifikaten vom Domänencontroller nicht.

> [!NOTE]
> Wenn der Surface Hub die Vertrauensstellung mit der Domäne verliert (wenn Sie z.B. den Surface Hub nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht beim Gerät authentifizieren und keine Einstellungen öffnen. Wenn Sie die Vertrauensstellung des Surface Hub mit Ihrer Domäne entfernen möchten, [müssen Sie zuerst das Gerät zurücksetzen](device-reset-surface-hub.md).


### <a name="azure-ad-join-the-device"></a>Azure AD wird dem Gerät beitreten

Sie können Azure Active Directory (Azure AD) zum Surface Hub hinzufügen, damit IT-Profis aus Ihrem Azure AD-Mandanten Einstellungen konfigurieren können. Wählen Sie bei der ersten Ausführung die Verwendung von [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory) aus. Sie müssen Anmeldeinformationen angeben, die einen Beitritt zum Azure AD-Mandanten Ihrer Wahl ausführen können. Nach dem erfolgreichen Beitritt zu Azure AD werden den entsprechenden Benutzern Administratorrechte auf dem Gerät gewährt.

Standardmäßig erhalten alle **globalen Administratoren** Administratorrechte auf einem Surface Hub, das Azure AD beigetreten ist. Mithilfe von **Azure AD Premium** oder **Enterprise Mobility Suite (EMS)** können Sie weitere Administratoren hinzufügen:
1.  Klicken Sie im [klassischen Azure-Portal](https://manage.windowsazure.com/) auf **Active Directory** und anschließend auf den Namen des Verzeichnisses Ihrer Organisation.
2.  Klicken Sie auf der Seite **Konfigurieren** unter **Geräte** > **Weitere Administratoren für in Azure AD eingebundene Geräte** auf **Ausgewählt**.
3.  Klicken Sie auf **Hinzufügen**, und wählen Sie die Benutzer aus, die Sie als Administratoren auf dem Surface Hub und anderen Geräten hinzufügen möchten, die Azure AD beigetreten sind.
4.  Wenn Sie fertig sind, klicken Sie auf das Kontrollkästchen, um die Änderung zu speichern.

#### <a name="what-happens-when-you-azure-ad-join-your-surface-hub"></a>Was geschieht, wenn Sie einen Beitritt zu Azure AD für den Surface Hub ausführen?
Surface Hubs verwenden Beitritte zu Azure AD zu folgenden Zwecken:
- Gewähren von Administratorrechten für die entsprechenden Benutzer in Ihrem Azure AD-Mandanten
- Sichern des BitLocker-Wiederherstellungsschlüssels des Geräts durch dessen Speicherung unter dem Konto, das für den Beitritt des Geräts zu Azure AD verwendet wurde Details hierzu finden Sie unter [Speichern des BitLocker-Schlüssels](save-bitlocker-key-surface-hub.md).

#### <a name="automatic-enrollment-via-azure-active-directory-join"></a>Automatische Registrierung über Azure Active Directory-Beitritt

Surface Hub unterstützt jetzt die Möglichkeit, sich automatisch in Intune zu registrieren, indem das Gerät azure Active Directory hinzugefügt wird. 

Weitere Informationen finden Sie unter [Aktivieren der automatischen Registrierung von Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

#### <a name="which-should-i-choose"></a>Welche Option sollte ausgewählt werden?

Wenn Ihre Organisation AD oder Azure AD verwendet, empfehlen wir entweder einen Domänenbeitritt oder einen Beitritt zu Azure AD, vor allem aus Sicherheitsgründen. Benutzer können Einstellungen mit ihren eigenen Anmeldeinformationen authentifizieren und entsperren und in die oder aus den der Domäne zugeordneten Sicherheitsgruppen verschoben werden.

| Option                                            | Anforderungen                            | Welche Anmeldeinformationen können für den Zugriff auf die Einstellungs-App verwendet werden?  |
|---------------------------------------------------|-----------------------------------------|-------|
| Erstellen eines lokalen Administratorkontos                      | Keine                                    | Der Benutzername und das Kennwort, die bei der ersten Ausführung angegeben wurden |
| Domänenbeitritt zu Active Directory (AD)              | Ihre Organisation verwendet AD               | Jeder AD-Benutzer aus einer angegebenen Sicherheitsgruppe in Ihrer Domäne |
| Beitritt des Geräts zu Azure Active Directory (Azure AD) | Ihre Organisation verwendet Azure AD Basic.   | Nur globale Administratoren |
| &nbsp;                                            | Ihre Organisation verwendet Azure AD Premium oder Enterprise Mobility Suite (EMS). | Globale Administratoren und zusätzliche Administratoren |


### <a name="configure-non-global-admin-accounts-on-azure-ad-joined-devices"></a>Konfigurieren nicht globaler Administratorkonten auf Azure AD-beigetretenen Geräten

Für Surface Hub v1- und Surface Hub 2S-Geräte, die Azure AD beigetreten sind, können Sie mit Windows 10 Team 2020 Update die Administratorberechtigungen auf die Verwaltung der Einstellungs-App auf Surface Hub beschränken. Auf diese Weise können Sie administratorberechtigungen nur für Surface Hub festlegen und potenziell unerwünschten Administratorzugriff auf eine gesamte Azure AD-Domäne verhindern. Weitere Informationen finden Sie unter [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).