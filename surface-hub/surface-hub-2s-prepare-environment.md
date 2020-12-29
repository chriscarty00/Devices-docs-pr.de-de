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
ms.date: 12/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: af66449806c9aa525fa3f5df84012d3daeed96ba
ms.sourcegitcommit: dbd14649442ad039aeb265cd60ed029d483a4bb0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2020
ms.locfileid: "11251452"
---
# Vorbereiten Ihrer Umgebung für Surface Hub 2S

## Office 365-Bereitschaft

Wenn Sie Exchange Online, Skype for Business Online, Microsoft Teams oder Microsoft Whiteboard verwenden und Surface Hub 2S mit InTune verwalten möchten, überprüfen Sie zunächst die [Office 365-Anforderungen für Endpunkte](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).

Office 365-Endpunkte helfen, Ihr Netzwerk zu optimieren, indem Sie alle vertrauenswürdigen Office 365-Netzwerkanforderungen direkt über Ihre Firewall senden, wobei alle zusätzlichen Inspektionen oder Verarbeitungsschritte auf Paketebene umgangen werden. Dieses Feature verringert die Latenz und ihre Perimeter-Kapazitätsanforderungen.

Microsoft aktualisiert den Office 365-Dienst regelmäßig mit neuen Features und Funktionen, die erforderliche Ports, URLs und IP-Adressen ändern können. Wenn Sie die Änderungen auswerten, konfigurieren und auf dem neuesten Stand bleiben möchten, abonnieren Sie die [Office 365-IP-Adresse und den URL-Webdienst](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

> [!NOTE]
> Surface Hub kann mit Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015 oder Skype for Business Online verwendet werden.
Frühere Plattformen wie lync Server 2013 werden nicht unterstützt. Surface Hub wird in GCC-High-oder DoD-Umgebungen nicht unterstützt.


## Geräte Zugehörigkeit

Verwenden Sie die Geräte Zugehörigkeit, um den Benutzer Zugriff auf die Einstellungs-APP auf Surface Hub 2S zu verwalten.
Mit dem Windows 10-Team Betriebssystem (das auf Surface Hub 2S ausgeführt wird) können nur autorisierte Benutzer die Einstellungen mithilfe der Einstellungs-APP anpassen. Da sich die Auswahl der Zuordnung auf die Verfügbarkeit von Features auswirken kann, sollten Sie entsprechend planen, um sicherzustellen, dass Benutzer auf Funktionen wie beabsichtigt zugreifen können.

> [!NOTE]
> Sie können die Geräte Zugehörigkeit nur während des anfänglichen out-of-Box Experience (OOBE)-Setups festzulegen. Wenn Sie die Geräte Zugehörigkeit zurücksetzen müssen, müssen Sie das OOBE-Setup wiederholen.

## Keine Zugehörigkeit

Keine Zugehörigkeit ist vergleichbar mit dem Surface Hub 2S in einer Arbeitsgruppe mit einem anderen lokalen Administrator Konto auf jeder Surface Hub 2S. Wenn Sie keine Zuordnung auswählen, müssen Sie den [BitLocker-Schlüssel lokal auf einem USB-Daumen Laufwerk](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)speichern. Sie können das Gerät weiterhin mit InTune registrieren; Allerdings kann nur der lokale Administrator auf die Einstellungs-APP mit den Kontoanmeldeinformationen zugreifen, die während OOBE konfiguriert sind. Sie können das Kennwort für das Administrator Konto aus der Einstellungs-APP ändern.

## Active Directory Domain Services

Wenn Sie Surface Hub 2S mit lokalen Active Directory-Domänendiensten verknüpfen, müssen Sie den Zugriff auf die Einstellungs-APP mithilfe einer Sicherheitsgruppe in Ihrer Domäne verwalten. Dadurch wird sichergestellt, dass alle Mitglieder der Sicherheitsgruppe über die Berechtigungen zum Ändern der Einstellungen für Surface Hub 2S verfügen. Beachten Sie außerdem Folgendes:

- Wenn die Surface Hub 2S-Partner mit Ihren lokalen Active Directory-Domänendiensten verbunden sind, kann der BitLocker-Schlüssel im Active Directory-Schema gespeichert werden. Weitere Informationen finden Sie unter [Vorbereiten Ihrer Organisation für BitLocker: Planung und Richtlinien](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- Die vertrauenswürdigen Stammzertifizierungsstellen Ihrer Organisation werden in Surface Hub 2S an denselben Container übertragen, was bedeutet, dass Sie Sie nicht mit einem Bereitstellungspaket importieren müssen.

- Sie können das Gerät weiterhin mit InTune registrieren, um die Einstellungen auf dem Surface Hub 2S zentral zu verwalten.

## Azure Active Directory

Wenn Sie sich entscheiden, ihre Surface Hub 2S mit Azure Active Directory (Azure AD) zu verknüpfen, kann sich jeder Benutzer in der Sicherheitsgruppe globale Administratoren bei der Einstellungs-APP auf Surface Hub 2S anmelden. Derzeit kann keine andere Gruppe delegiert werden, um sich bei der Einstellungs-APP auf Surface Hub 2S anzumelden.

Wenn Sie die automatische Registrierung von InTune für Ihre Organisation aktiviert haben, wird Surface Hub 2S automatisch bei InTune registriert. Der BitLocker-Schlüssel des Geräts wird in Azure AD automatisch gespeichert. Bei der Zuordnung von Surface Hub 2S mit Azure AD können einmaliges Anmelden und einfache Authentifizierung nicht funktionieren.
