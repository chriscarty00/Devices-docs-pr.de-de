---
title: Verwalten der Kennwort-Rotation für das Gerätekonto
description: Informationen zum Konfigurieren von Surface Hub 2S-lokalen Konten mit PowerShell
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833997"
---
# <span data-ttu-id="09af4-104">Verwalten der Kennwort-Rotation für das Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="09af4-104">Manage device account password rotation</span></span>

<span data-ttu-id="09af4-105">Sie können Surface Hub 2S so konfigurieren, dass ein Geräte Kontokennwort automatisch geändert wird, ohne dass Sie die Geräte Kontoinformationen manuell aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="09af4-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="09af4-106">Wenn Sie die Kenn Wort Rotation aktivieren, ändert Surface Hub 2S das Kennwort alle 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="09af4-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="09af4-107">Die automatisch generierten Kennwörter enthalten 15-32 Zeichen, einschließlich einer Kombination aus Groß-und Kleinbuchstaben, Zahlen und Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="09af4-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="09af4-108">Kennwörter werden während einer Besprechung nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="09af4-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="09af4-109">Wenn Surface Hub 2S deaktiviert ist, wird versucht, das Kennwort beim Einschalten oder alle 10 Minuten bis zum Erfolg sofort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="09af4-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>
