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
# <span data-ttu-id="ccbda-104">Moderne Authentifizierung auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ccbda-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="ccbda-105">Die Unterstützung für die moderne Authentifizierung von Cloud-basierten Konten ist vollständig in das [Windows 10 Team 2020-Update](surface-hub-2020-update.md)integriert.</span><span class="sxs-lookup"><span data-stu-id="ccbda-105">Support for modern authentication of cloud-based accounts is fully integrated in [Windows 10 Team 2020 Update](surface-hub-2020-update.md).</span></span> <span data-ttu-id="ccbda-106">Nachdem Sie das 2020-Update installiert haben, können Sie von der Legacy Standardauthentifizierung migrieren und die neuesten Sicherheitsverbesserungen von Microsoft Azure und Exchange Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccbda-106">Once you install the 2020 update, you can migrate from legacy basic authentication and use the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="ccbda-107">Mit dem 2020-Update unterstützt Surface Hub Exchange-Webdienste (EWS)-Protokolle und Active Directory Authentication Library (Adal)-basierte Authentifizierung, die die Synchronisierung von Exchange Online für das Device-Konto ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ccbda-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="ccbda-108">Für neue Cloud-basierte Konten verwendet Surface Hub automatisch eine moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne zusätzliche Konfiguration über die einfache Erstellung von Geräte Konten mit dem Format [Alias@contoso.com](mailto:alias@contoso.com)zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="ccbda-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="ccbda-109">Verwenden Sie nicht das Legacyformat – Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ccbda-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="ccbda-110">Weitere Informationen finden Sie unter [Erstellen eines Surface Hub 2S-Geräte Kontos](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="ccbda-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="ccbda-111">Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten.</span><span class="sxs-lookup"><span data-stu-id="ccbda-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="ccbda-112">Die Konten müssen in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ccbda-112">The accounts must be created in the cloud.</span></span>

