---
title: Erstellen und Testen eines Gerätekontos (Surface Hub)
description: In diesem Thema wird vorgestellt, wie Sie das Gerätekonto erstellen und testen können, das Microsoft Surface Hub für die Kommunikation mit Microsoft Exchange und Skype verwendet.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: Erstellen und Testen eines Gerätekonto, Gerätekonto, Surface Hub und Microsoft Exchange, Surface Hub und Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 685359f1371a1bef8bd216223a98b934c997a1d8
ms.sourcegitcommit: 879e80200aea26f6705c887fa392db5db35b99ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "11475089"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>Erstellen und Testen eines Gerätekontos (Surface Hub)

Das Erstellen eines Surface Hub-Gerätekontos (auch als Ressourcenkonto/Raumpostfach bezeichnet) ermöglicht dem Surface Hub das Empfangen, Genehmigen oder Ablehnen von Besprechungsanfragen und den Beitritt zu Besprechungen.

Sobald das Gerätekonto auf einem Surface Hub bereitgestellt wurde, können Benutzer dieses Konto einer Besprechungseinladung auf die gleiche Weise hinzufügen, wie sie einen Konferenzraum einladen würden. 

Sie können das Gerätekonto während des [Setups der Out-of-Box Experience (OOBE) konfigurieren.](first-run-program-surface-hub.md) Bei Bedarf können Sie sie auch später unter **Einstellungen Surface**  >  **Hub Accounts**  >  **ändern.**

## <a name="configuration-overview"></a>Konfigurationsübersicht

In der folgenden Tabelle werden die wichtigsten Schritteund Konfigurationsentscheidungen beim Erstellen eines Gerätekontos beschrieben.
 
| Schritt | Beschreibung                     |  Zweck                             |
|------|---------------------------------|--------------------------------------|
| 1    | Erstellen eines anmeldefähigen Raumpostfachs (Exchange Online oder Exchange Server 2016 und höher) | Mit diesem Postfachtyp kann das Gerät einen Besprechungskalender verwalten, Besprechungsanfragen empfangen und E-Mails senden. Sie muss anmeldefähig sein, damit sie mit einem Surface Hub verwendet werden kann. |
| 2    | Konfigurieren der Postfacheigenschaften | Das Postfach muss mit den richtigen Eigenschaften konfiguriert sein, um eine optimale Besprechungserfahrung auf Surface Hub zu ermöglichen. Weitere Informationen zu Postfacheigenschaften finden Sie unter [Postfacheigenschaften](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Stellen Sie sicher, dass Exchange Web Services (EWS) aktiviert ist und die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) deaktiviert ist. | Der Surface Hub verwendet EWS, um seinen Kalender zu synchronisieren. Wenn Sie EWS in Ihrer Umgebung standardmäßig nicht zulassen, muss es für das Hubpostfach explizit aktiviert sein. Da sich surface hub ohne Benutzerinteraktion im Hintergrund bei Exchange anmeldet, kann er nicht auf interaktive Eingabeaufforderungen wie MFA reagieren. Das von Ihnen erstellte Gerätekonto muss von solchen Authentifizierungsanforderungen ausgeschlossen werden. Andernfalls kann Surface Hub E-Mail- und Kalenderinformationen nicht synchronisieren. |
| 4    | Aktivieren des Kontos für Teams oder Skype for Business (Skype for Business Server 2015 und höher) | Skype for Business oder Teams müssen für die Verwendung von Konferenzfunktionen wie Videoanrufen, Chat und Bildschirmfreigabe aktiviert sein. Weitere Informationen zu den Lizenzen, die Teams aktivieren, finden Sie unter [Teams Meeting Room licensing](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing) and Teams service [description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description). |
| 5    | (Optional) Deaktivieren des Kennwortablaufs | Um die Verwaltung zu vereinfachen, können Sie den Kennwortablauf für das Gerätekonto deaktivieren und Surface Hub für das automatische Rotieren des Kennworts für das Gerätekonto aktivieren. Weitere Informationen zur Kennwortverwaltung finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).  |
| 6    | (Optional) Konfigurieren von Exchange-Richtlinien zum Zulassen von ActiveSync | Bei bestimmten lokalen Exchange Server & Active Directory-Bereitstellungen wird ActiveSync zum Synchronisieren der E-Mail- und Kalenderinformationen des Gerätekontos verwendet. Weitere Informationen zu den zu konfigurierende Richtlinien finden Sie unter [ActiveSync-Richtlinien für Surface Hub-Konten](apply-activesync-policies-for-surface-hub-device-accounts.md). |

> [!NOTE]  
> Das Surface Hub-Gerätekonto unterstützt keine Verbundidentitätsanbieter (IdPs) von Drittanbietern und muss sich über Active Directory oder Azure Active Directory authentifizieren.

## <a name="detailed-configuration-steps"></a>Details zu den Konfigurationsschritten 

Es wird empfohlen, Ihre Surface Hub-Gerätekonten mithilfe von Remoteservern Windows PowerShell. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, mit dem Sie neue Ressourcenkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, um sie in kompatible Surface Hub-Gerätekonten zu verwandeln. Wenn es Ihnen lieber ist, können Sie eine Option aus der folgenden Tabelle auswählen und die detaillierten PowerShell-Schritte basierend auf Ihrer Organisationsbereitstellung ausführen.

| Art der Bereitstellung in der Organisation             |  Beschreibung                  |        Format, das während des Surface Hub-Setups verwendet werden soll
|---------------------------------|--------------------------------------|
| [Onlinebereitstellung (Microsoft 365 oder Office 365)](https://docs.microsoft.com/microsoftteams/rooms/with-office-365) |Die Umgebung Ihrer Organisation wird vollständig unter Microsoft 365 oder Office 365 bereitgestellt. | Benutzername@domain.com |
| [Hybridbereitstellung (lokale Exchange-Bereitstellung)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-on-premises) | Ihre Organisation verfügt über eine Mischung aus Diensten, Exchange Server lokal und Microsoft Teams online gehostet wird. | username@domain.com, wenn [die moderne Hybridauthentifizierung](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) in Exchange aktiviert ist, DOMÄNE\Benutzername andernfalls |
| [Hybridbereitstellung (Exchange Online)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-online) | Ihre Organisation verfügt über eine Mischung aus Diensten, bei der Skype for Business Server lokal und Exchange Online gehostet werden. | username@domain.com, wenn [die hybride moderne Authentifizierung](https://docs.microsoft.com/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) in SfB aktiviert ist, DOMAIN\Benutzername andernfalls |
| [Lokale Bereitstellung (einzelne Gesamtstruktur)](https://docs.microsoft.com/microsoftteams/rooms/with-skype-for-business-server-2015) | Ihre Organisation verfügt über Server, die sie steuert, auf denen Active Directory, Exchange und Skype for Business Server in einer Umgebung mit einer einzelnen Gesamtstruktur gehostet werden.  | DOMÄNE\Benutzername |
| [Lokale Bereitstellung (mehrere Gesamtstrukturen)](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Ihre Organisation verfügt über Server, die sie steuert, auf denen Active Directory, Exchange und Skype for Business Server in einer Umgebung mit mehreren Gesamtstrukturen gehostet werden. | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>Kontoüberprüfung und Test

Es stehen zwei Methoden zur Verfügung, die Sie zum Überprüfen und Testen eines Surface Hub-Gerätekontos verwenden [ können: ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1und die [Surface Hub Hardware Diagnostic App](https://www.microsoft.com/store/apps/9nblggh51f2g). Das Kontobereitstellungsskript kann ein zuvor erstelltes Gerätekonto mithilfe von PowerShell auf Ihrem PC überprüfen. Die Hardwarediagnose-App für Surface Hub ist auf dem Surface Hub installiert und übermittelt detailliertes Feedback in puncto Fehler bei der Anmeldung und Kommunikation. Beide Tools sind wertvoll, um neu erstellte Gerätekonten zu testen und sollten verwendet werden, um eine optimale Konto-Verfügbarkeit sicherzustellen.
