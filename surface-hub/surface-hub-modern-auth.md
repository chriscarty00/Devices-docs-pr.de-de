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
# <span data-ttu-id="8c3f1-104">Moderne Authentifizierung auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="8c3f1-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="8c3f1-105">Die Unterstützung für die moderne Authentifizierung von cloudbasierten Konten ist vollständig in das bevorstehende Windows 10 Team 2020-Update integriert, wobei Preview-Builds im [Windows-Insider-Programm](https://insider.windows.com/)zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="8c3f1-106">Nachdem Sie [den Preview-Build installiert](surface-hub-install-2020preview.md)haben, können Sie von der Legacy Standardauthentifizierung migrieren und die neuesten Sicherheitsverbesserungen von Microsoft Azure und Exchange Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="8c3f1-107">Mit dem 2020-Update unterstützt Surface Hub Exchange-Webdienste (EWS)-Protokolle und Active Directory Authentication Library (Adal)-basierte Authentifizierung, die die Synchronisierung von Exchange Online für das Device-Konto ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="8c3f1-108">Für neue Cloud-basierte Konten verwendet Surface Hub automatisch eine moderne Authentifizierung, um eine Verbindung mit Exchange Online herzustellen, ohne zusätzliche Konfiguration über die einfache Erstellung von Geräte Konten mit dem Format [Alias@contoso.com](mailto:alias@contoso.com)zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="8c3f1-109">Verwenden Sie nicht das Legacyformat – Contoso\alias, das für die moderne Authentifizierung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="8c3f1-110">Weitere Informationen finden Sie unter [Erstellen eines Surface Hub 2S-Geräte Kontos](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="8c3f1-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="8c3f1-111">Surface Hub unterstützt keine moderne Authentifizierung für lokale Konten.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="8c3f1-112">Die Konten müssen in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8c3f1-112">The accounts must be created in the cloud.</span></span>

