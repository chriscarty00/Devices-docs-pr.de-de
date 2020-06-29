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
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 38f02b885a0ac2789ffc82f1ab38dc57fea5e841
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833025"
---
# Vorbereiten Ihrer Umgebung für Surface Hub 2S

## Office 365-Bereitschaft

Wenn Sie Exchange Online, Skype for Business Online, Microsoft Teams oder Microsoft Whiteboard verwenden und Surface Hub 2S mit InTune verwalten möchten, überprüfen Sie zunächst die [Office 365-Anforderungen für Endpunkte](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).

Office 365-Endpunkte helfen, Ihr Netzwerk zu optimieren, indem Sie alle vertrauenswürdigen Office 365-Netzwerkanforderungen direkt über Ihre Firewall senden, wobei alle zusätzlichen Inspektionen oder Verarbeitungsschritte auf Paketebene umgangen werden. Dieses Feature verringert die Latenz und ihre Perimeter-Kapazitätsanforderungen.

Microsoft aktualisiert den Office 365-Dienst regelmäßig mit neuen Features und Funktionen, die erforderliche Ports, URLs und IP-Adressen ändern können. Wenn Sie die Änderungen auswerten, konfigurieren und auf dem neuesten Stand bleiben möchten, abonnieren Sie die [Office 365-IP-Adresse und den URL-Webdienst](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

## Geräte Zugehörigkeit

Verwenden Sie die Geräte Zugehörigkeit, um den Benutzer Zugriff auf die Einstellungs-APP auf Surface Hub 2S zu verwalten.
Mit dem Betriebssystem Windows 10 Team Edition (das auf Surface Hub 2S ausgeführt wird) können nur autorisierte Benutzer die Einstellungen mithilfe der Einstellungs-APP anpassen. Da sich die Auswahl der Zuordnung auf die Verfügbarkeit von Features auswirken kann, sollten Sie entsprechend planen, um sicherzustellen, dass Benutzer auf Funktionen wie beabsichtigt zugreifen können.

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
