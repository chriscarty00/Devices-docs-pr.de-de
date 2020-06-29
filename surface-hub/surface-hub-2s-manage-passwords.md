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
# Verwalten der Kennwort-Rotation für das Gerätekonto

Sie können Surface Hub 2S so konfigurieren, dass ein Geräte Kontokennwort automatisch geändert wird, ohne dass Sie die Geräte Kontoinformationen manuell aktualisieren müssen.

Wenn Sie die Kenn Wort Rotation aktivieren, ändert Surface Hub 2S das Kennwort alle 7 Tage. Die automatisch generierten Kennwörter enthalten 15-32 Zeichen, einschließlich einer Kombination aus Groß-und Kleinbuchstaben, Zahlen und Sonderzeichen.

Kennwörter werden während einer Besprechung nicht geändert. Wenn Surface Hub 2S deaktiviert ist, wird versucht, das Kennwort beim Einschalten oder alle 10 Minuten bis zum Erfolg sofort zu ändern.
