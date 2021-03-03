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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="ea0a4-104">Moderne Authentifizierung auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ea0a4-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="ea0a4-105">Das Windows 10 Team 2020 Update bietet in einigen Szenarien Unterstützung für die moderne Authentifizierung des Hub-Gerätekontos.</span><span class="sxs-lookup"><span data-stu-id="ea0a4-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="ea0a4-106">Nachdem Sie das Update 2020 installiert haben, können Sie von der Standardauthentifizierung der Voreinstellungen migrieren, um die neuesten Sicherheitsverbesserungen zu nutzen, wenn sich das Gerätekonto über Azure Active Directory authentifiziert und das Postfach des Kontos in Exchange Online gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ea0a4-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="ea0a4-107">Mit dem Update 2020 unterstützt Surface Hub Exchange Web Services (EWS)-Protokolle und die ADAL-basierte Authentifizierung (Active Directory Authentication Library), wenn das Gerätekonto mit Exchange Online synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="ea0a4-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="ea0a4-108">Für neue cloudbasierte Konten verwendet Surface Hub automatisch die moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne dass zusätzliche Konfigurationen erforderlich sind, die über das einfache Erstellen von Gerätekonten mit dem Format [alias@contoso.com.](mailto:alias@contoso.com)</span><span class="sxs-lookup"><span data-stu-id="ea0a4-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="ea0a4-109">Verwenden Sie nicht das Legacyformat Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ea0a4-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="ea0a4-110">Weitere Informationen finden Sie unter [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="ea0a4-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="ea0a4-111">Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten.</span><span class="sxs-lookup"><span data-stu-id="ea0a4-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="ea0a4-112">Die Konten müssen in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ea0a4-112">The accounts must be created in the cloud.</span></span>

