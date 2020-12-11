---
title: Moderne Authentifizierung auf Surface Hub
description: Diese Seite beschreibt die Verwendung der modernen Authentifizierung auf Surface Hub im Gegensatz zur Legacy Standardauthentifizierung.
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
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206279"
---
# Moderne Authentifizierung auf Surface Hub

Die Unterstützung für die moderne Authentifizierung von Cloud-basierten Konten ist vollständig in das [Windows 10 Team 2020-Update](surface-hub-2020-update.md)integriert. Nachdem Sie das 2020-Update installiert haben, können Sie von der Legacy Standardauthentifizierung migrieren und die neuesten Sicherheitsverbesserungen von Microsoft Azure und Exchange Online verwenden. Mit dem 2020-Update unterstützt Surface Hub Exchange-Webdienste (EWS)-Protokolle und Active Directory Authentication Library (Adal)-basierte Authentifizierung, die die Synchronisierung von Exchange Online für das Device-Konto ermöglicht.

Für neue Cloud-basierte Konten verwendet Surface Hub automatisch eine moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne zusätzliche Konfiguration über die einfache Erstellung von Geräte Konten mit dem Format [Alias@contoso.com](mailto:alias@contoso.com)zu erfordern. Verwenden Sie nicht das Legacyformat – Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird. Weitere Informationen finden Sie unter [Erstellen eines Surface Hub 2S-Geräte Kontos](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten. Die Konten müssen in der Cloud erstellt werden.

