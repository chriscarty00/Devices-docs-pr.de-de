---
title: Kennwortverwaltung (Surface Hub)
description: Jedes Microsoft Surface Hub-Gerätekonto erfordert ein Kennwort zur Authentifizierung und Aktivierung von Features auf dem Gerät.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: Kennwort, Kennwortverwaltung, Kennwortrotation, Gerätekonto
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834027"
---
# Kennwortverwaltung (Surface Hub)

Jedes Microsoft Surface Hub-Gerätekonto erfordert ein Kennwort zur Authentifizierung und Aktivierung von Features auf dem Gerät. Aus Sicherheitsgründen sollten Sie das Kennwort regelmäßig ändern (oder „rotieren“). Wenn das Kennwort des Gerätekontos jedoch geändert wird, verliert das zuvor auf dem Surface Hub gespeicherte Kennwort seine Gültigkeit, und alle vom Gerätekonto abhängigen Features werden deaktiviert. Sie müssen das Kennwort des Gerätekontos im Surface Hub in der Einstellungs-App aktualisieren, um die Features erneut zu aktivieren.

Sie haben zwei Möglichkeiten, um die Kennwortverwaltung für Ihre Surface Hub-Gerätekonten zu vereinfachen:

1.  Deaktivieren Sie den Kennwortablauf für das Gerätekonto.
2.  Lassen Sie die automatische Rotation von Gerätekontokennwörtern auf dem Surface Hub zu.


## Deaktivieren der Kennwortrotation für das Gerätekonto

Legen Sie die **PasswordNeverExpires**-Eigenschaft des Gerätekontos auf „True“ fest. Überprüfen Sie, ob dies mit den Sicherheitsanforderungen Ihrer Organisation vereinbar ist.


## Zulassen der automatischen Rotation von Gerätekontokennwörtern auf dem Surface Hub

Der Surface Hub kann das Kennwort eines Gerätekontos verwalten, d. h. häufig ändern, ohne dass Sie die Informationen des Gerätekontos manuell aktualisieren müssen. Sie können dieses Feature in den **Einstellungen** aktivieren. Nach der Aktivierung wird das Kennwort des Gerätekontos jede Woche während der Wartungszeiten geändert.

Wenn das Kennwort des Gerätekontos geändert wird, wird Ihnen das neue Kennwort allerdings nicht angezeigt. Wenn Sie sich beim Konto anmelden oder das Kennwort erneut angeben möchten (z.B. zur Änderung der Einstellungen des Gerätekontos im Surface Hub), müssen Sie das Kennwort über Active Directory oder das Verwaltungsportal von Office 365 zurücksetzen.

> [!IMPORTANT]
> Wenn Ihre Organisation eine hybride Topologie verwendet (einige Dienste werden lokal und einige online über Office365 gehostet), müssen Sie das Gerätekonto im Format **Domäne\Benutzername** einrichten. Andernfalls funktioniert die Kennwortrotation nicht.
