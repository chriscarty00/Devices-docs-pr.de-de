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
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004467"
---
# Moderne Authentifizierung auf Surface Hub

Die Unterstützung für die moderne Authentifizierung von cloudbasierten Konten ist vollständig in das bevorstehende Windows 10 Team 2020-Update integriert, wobei Preview-Builds im [Windows-Insider-Programm](https://insider.windows.com/)zur Verfügung stehen. Nachdem Sie [den Preview-Build installiert](surface-hub-install-2020preview.md)haben, können Sie von der Legacy Standardauthentifizierung migrieren und die neuesten Sicherheitsverbesserungen von Microsoft Azure und Exchange Online verwenden. Mit dem 2020-Update unterstützt Surface Hub Exchange-Webdienste (EWS)-Protokolle und Active Directory Authentication Library (Adal)-basierte Authentifizierung, die die Synchronisierung von Exchange Online für das Device-Konto ermöglicht.

Für neue Cloud-basierte Konten verwendet Surface Hub automatisch eine moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne zusätzliche Konfiguration über die einfache Erstellung von Geräte Konten mit dem Format [Alias@contoso.com](mailto:alias@contoso.com)zu erfordern. Verwenden Sie nicht das Legacyformat – Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird. Weitere Informationen finden Sie unter [Erstellen eines Surface Hub 2S-Geräte Kontos](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten. Die Konten müssen in der Cloud erstellt werden.

