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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="63321-104">Moderne Authentifizierung auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="63321-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="63321-105">Das Windows 10 Team 2020 Update bietet in einigen Szenarien Unterstützung für die moderne Authentifizierung des Hub-Gerätekontos.</span><span class="sxs-lookup"><span data-stu-id="63321-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="63321-106">Nachdem Sie das Update 2020 installiert haben, können Sie von der Standardauthentifizierung der Voreinstellungen migrieren, um die neuesten Sicherheitsverbesserungen zu nutzen, wenn sich das Gerätekonto über Azure Active Directory authentifiziert und das Postfach des Kontos in Exchange Online gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="63321-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="63321-107">Mit dem Update 2020 unterstützt Surface Hub Exchange Web Services (EWS)-Protokolle und die ADAL-basierte Authentifizierung (Active Directory Authentication Library), wenn das Gerätekonto mit Exchange Online synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="63321-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="63321-108">Für neue cloudbasierte Konten verwendet Surface Hub automatisch die moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne dass zusätzliche Konfiguration erforderlich ist, über das einfache Hinzufügen des Gerätekontos zum Surface Hub mit dem Format [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="63321-108">For new cloud-based accounts, the Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply adding the device account to the Surface Hub using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="63321-109">Verwenden Sie nicht das Legacyformat Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="63321-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="63321-110">Weitere Informationen finden Sie unter [Erstellen und Testen eines Gerätekontos](create-and-test-a-device-account-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="63321-110">For more information, see [create and test a device account](create-and-test-a-device-account-surface-hub.md).</span></span>

> [!NOTE]
> <span data-ttu-id="63321-111">Die moderne Authentifizierung wird für lokale Surface Hub-Konten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63321-111">Modern authentication is not supported for on-premises Surface Hub accounts.</span></span> <span data-ttu-id="63321-112">Die Konten dürfen nur Azure AD für die Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="63321-112">The accounts must use only Azure AD for authentication.</span></span>
