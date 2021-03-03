---
title: Vorbereiten Ihrer Umgebung für Surface Hub 2S
description: Erfahren Sie, was Sie tun müssen, um Ihre Umgebung für Surface Hub 2S vorzubereiten.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385143"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a>Vorbereiten Ihrer Umgebung für Surface Hub 2S

## <a name="office-365-readiness"></a>Office 365-Bereitschaft

Wenn Sie Exchange Online, Skype for Business Online, Microsoft Teams oder Microsoft Whiteboard verwenden und Surface Hub 2S mit Intune verwalten möchten, überprüfen Sie zunächst die [Office 365-Anforderungen für Endpunkte.](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)

Office 365-Endpunkte helfen Bei der Optimierung Ihres Netzwerks, indem alle vertrauenswürdigen Office 365-Netzwerkanforderungen direkt über Ihre Firewall gesendet werden und alle zusätzlichen Überprüfungen oder Verarbeitungen auf Paketebene umgangen werden. Mit diesem Feature werden die Wartezeit und die Anforderungen an die Umkreiskapazität reduziert.

Microsoft aktualisiert den Office 365-Dienst regelmäßig mit neuen Features und Funktionen, die erforderliche Ports, URLs und IP-Adressen ändern können. Um Änderungen auszuwerten, zu konfigurieren und auf dem neuesten Stand zu bleiben, abonnieren Sie den [Office 365-IP-Adress- und URL-Webdienst](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

> [!NOTE]
> Surface Hub funktioniert mit Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015 oder Skype for Business Online.
Frühere Plattformen wie Lync Server 2013 werden nicht unterstützt. Surface Hub wird in GCC-High oder DoD-Umgebungen nicht unterstützt.


## <a name="device-affiliation"></a>Gerätezugehörigkeit

Verwenden Sie Gerätezugehörigkeit, um den Benutzerzugriff auf die Einstellungen-App auf Surface Hub 2S zu verwalten.
Mit dem Windows 10 Team-Betriebssystem (das auf Surface Hub 2S ausgeführt wird) können nur autorisierte Benutzer Einstellungen mithilfe der Einstellungs-App anpassen. Da sich die Auswahl der Zuordnung auf die Featureverfügbarkeit auswirken kann, sollten Sie entsprechend planen, um sicherzustellen, dass Benutzer wie beabsichtigt auf Features zugreifen können.

> [!NOTE]
> Sie können die Gerätezugehörigkeit nur während des anfänglichen Setups für die out-of-box-Besens (OOBE) festlegen. Wenn Sie die Gerätezugehörigkeit zurücksetzen müssen, müssen Sie das OOBE-Setup wiederholen.

## <a name="no-affiliation"></a>Keine Zugehörigkeit

Keine Zuordnung ist so, als würde Surface Hub 2S in einer Arbeitsgruppe mit einem anderen lokalen Administratorkonto auf jedem Surface Hub 2S erstellt. Wenn Sie Keine Zugehörigkeit auswählen, müssen Sie den [BitLocker-Schlüssel](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)lokal auf einem USB-Stick speichern. Sie können das Gerät weiterhin bei Intune registrieren. Allerdings kann nur der lokale Administrator mithilfe der Kontoanmeldeinformationen, die während der OOBE konfiguriert wurden, auf die Einstellungs-App zugreifen. Sie können das Administratorkontokennwort über die Einstellungs-App ändern.

## <a name="active-directory-domain-services"></a>Active Directory Domain Services

Wenn Sie Surface Hub 2S mit lokalen Active Directory-Domänendiensten verbinden, müssen Sie den Zugriff auf die Einstellungs-App mithilfe einer Sicherheitsgruppe in Ihrer Domäne verwalten. Dadurch wird sichergestellt, dass alle Mitglieder der Sicherheitsgruppe über Berechtigungen zum Ändern von Einstellungen auf Surface Hub 2S verfügen. Beachten Sie außerdem Folgendes:

- Wenn Surface Hub 2S mit Ihren lokalen Active Directory-Domänendiensten verbunden ist, kann der BitLocker-Schlüssel im Active Directory-Schema gespeichert werden. Weitere Informationen finden Sie unter [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- Die vertrauenswürdigen Stammzertifizierungsstelle Ihrer Organisation werden in Surface Hub 2S an denselben Container geschubst, d. h., Sie müssen sie nicht mithilfe eines Bereitstellungspakets importieren.

- Sie können das Gerät weiterhin bei Intune registrieren, um Einstellungen auf Ihrem Surface Hub 2S zentral zu verwalten.

## <a name="azure-active-directory"></a>Azure Active Directory

Wenn Sie Surface Hub 2S mit Azure Active Directory (Azure AD) verbinden möchten, kann sich jeder Benutzer in der Globalen Sicherheitsgruppe "Administratoren" bei der Einstellungs-App auf Surface Hub 2S anmelden. Sie können auch nicht globale Administratorkonten konfigurieren, die die Berechtigungen auf die Verwaltung der Einstellungen-App auf Surface Hub 2S beschränken. Auf diese Weise können Sie administratorberechtigungen nur für Surface Hub 2S festlegen und potenziell unerwünschten Administratorzugriff über eine gesamte Azure AD-Domäne hinweg verhindern. 

Wenn Sie die automatische Registrierung von Intune für Ihre Organisation aktiviert haben, registriert sich Surface Hub 2S automatisch bei Intune. Der BitLocker-Schlüssel des Geräts wird automatisch in Azure AD gespeichert. 

Weitere Informationen zum Verwalten von Surface Hub mit Azure AD finden Sie unter: 

 - [Administratorgruppenverwaltung](admin-group-management-for-surface-hub.md)
 - [Konfigurieren nicht globaler Administratorkonten auf Surface Hub 2S](surface-hub-2s-nonglobal-admin.md)

