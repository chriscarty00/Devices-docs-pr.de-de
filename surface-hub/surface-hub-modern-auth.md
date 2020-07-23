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
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893138"
---
# <span data-ttu-id="f780b-104">Moderne Authentifizierung auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f780b-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="f780b-105">Die Unterstützung für die moderne Authentifizierung von cloudbasierten Konten ist vollständig in das Windows 10 Team 2020-Update integriert, sodass Sie von der Legacy Standardauthentifizierung migrieren und die neuesten Sicherheitsverbesserungen von Microsoft Azure und Exchange Online verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f780b-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="f780b-106">Mit dem 2020-Update unterstützt Surface Hub Exchange-Webdienste (EWS)-Protokolle und Active Directory Authentication Library (Adal)-basierte Authentifizierung, die die Synchronisierung von Exchange Online für das Device-Konto ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f780b-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="f780b-107">Für neue Cloud-basierte Konten verwendet Surface Hub automatisch eine moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne zusätzliche Konfiguration über die einfache Erstellung von Geräte Konten mit dem Format [Alias@contoso.com](mailto:alias@contoso.com)zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="f780b-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="f780b-108">Verwenden Sie nicht das Legacyformat – Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f780b-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="f780b-109">Weitere Informationen finden Sie unter [Erstellen eines Surface Hub 2S-Geräte Kontos](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="f780b-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="f780b-110">Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten.</span><span class="sxs-lookup"><span data-stu-id="f780b-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="f780b-111">Die Konten müssen in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f780b-111">The accounts must be created in the cloud.</span></span>

