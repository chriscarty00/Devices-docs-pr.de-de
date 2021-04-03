---
title: Moderne Authentifizierung auf Surface Hub
description: Auf dieser Seite wird die Verwendung der modernen Authentifizierung auf Surface Hub im Gegensatz zur älteren Standardauthentifizierung beschrieben.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 3873d0ac7ffff3fa790f44b474d937772e5a0900
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474762"
---
# <a name="modern-authentication-on-surface-hub"></a>Moderne Authentifizierung auf Surface Hub

Das Windows 10 Team 2020 Update bietet in einigen Szenarien Unterstützung für die moderne Authentifizierung des Hub-Gerätekontos. Nachdem Sie das Update 2020 installiert haben, können Sie von der Standardauthentifizierung der Voreinstellungen migrieren, um die neuesten Sicherheitsverbesserungen zu nutzen, wenn sich das Gerätekonto über Azure Active Directory authentifiziert und das Postfach des Kontos in Exchange Online gehostet wird. Mit dem Update 2020 unterstützt Surface Hub Exchange Web Services (EWS)-Protokolle und die ADAL-basierte Authentifizierung (Active Directory Authentication Library), wenn das Gerätekonto mit Exchange Online synchronisiert wird.

Für neue cloudbasierte Konten verwendet Surface Hub automatisch die moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne dass zusätzliche Konfiguration erforderlich ist, über das einfache Hinzufügen des Gerätekontos zum Surface Hub mit dem Format [alias@contoso.com](mailto:alias@contoso.com). Verwenden Sie nicht das Legacyformat Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird. Weitere Informationen finden Sie unter [Erstellen und Testen eines Gerätekontos](create-and-test-a-device-account-surface-hub.md).

> [!NOTE]
> Die moderne Authentifizierung wird für lokale Surface Hub-Konten nicht unterstützt. Die Konten dürfen nur Azure AD für die Authentifizierung verwenden.
