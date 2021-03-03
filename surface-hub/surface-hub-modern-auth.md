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
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385163"
---
# <a name="modern-authentication-on-surface-hub"></a>Moderne Authentifizierung auf Surface Hub

Das Windows 10 Team 2020 Update bietet in einigen Szenarien Unterstützung für die moderne Authentifizierung des Hub-Gerätekontos. Nachdem Sie das Update 2020 installiert haben, können Sie von der Standardauthentifizierung der Voreinstellungen migrieren, um die neuesten Sicherheitsverbesserungen zu nutzen, wenn sich das Gerätekonto über Azure Active Directory authentifiziert und das Postfach des Kontos in Exchange Online gehostet wird. Mit dem Update 2020 unterstützt Surface Hub Exchange Web Services (EWS)-Protokolle und die ADAL-basierte Authentifizierung (Active Directory Authentication Library), wenn das Gerätekonto mit Exchange Online synchronisiert wird.

Für neue cloudbasierte Konten verwendet Surface Hub automatisch die moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne dass zusätzliche Konfigurationen erforderlich sind, die über das einfache Erstellen von Gerätekonten mit dem Format [alias@contoso.com.](mailto:alias@contoso.com) Verwenden Sie nicht das Legacyformat Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird. Weitere Informationen finden Sie unter [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten. Die Konten müssen in der Cloud erstellt werden.

