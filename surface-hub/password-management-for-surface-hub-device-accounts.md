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
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445581"
---
# <a name="password-management-surface-hub"></a>Kennwortverwaltung (Surface Hub)

Jedes Microsoft Surface Hub-Gerätekonto erfordert ein Kennwort zur Authentifizierung und Aktivierung von Features auf dem Gerät. Aus Sicherheitsgründen sollten Sie das Kennwort regelmäßig ändern (oder „rotieren“). Wenn das Kennwort des Gerätekontos jedoch geändert wird, verliert das zuvor auf dem Surface Hub gespeicherte Kennwort seine Gültigkeit, und alle vom Gerätekonto abhängigen Features werden deaktiviert. Sie müssen das Kennwort des Gerätekontos im Surface Hub in der Einstellungs-App aktualisieren, um die Features erneut zu aktivieren.

Sie haben zwei Möglichkeiten, um die Kennwortverwaltung für Ihre Surface Hub-Gerätekonten zu vereinfachen:

1.  Deaktivieren Sie den Kennwortablauf für das Gerätekonto.
2.  Lassen Sie die automatische Rotation von Gerätekontokennwörtern auf dem Surface Hub zu.


## <a name="turn-off-password-rotation-for-the-device-account"></a>Deaktivieren der Kennwortrotation für das Gerätekonto

Legen Sie die **PasswordNeverExpires**-Eigenschaft des Gerätekontos auf „True“ fest. Überprüfen Sie, ob dies mit den Sicherheitsanforderungen Ihrer Organisation vereinbar ist.


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>Zulassen der automatischen Rotation von Gerätekontokennwörtern auf dem Surface Hub

Der Surface Hub kann das Kennwort eines Gerätekontos automatisch ändern, ohne dass Sie es manuell aktualisieren müssen. Sie können dieses Feature unter **Einstellungen Surface**  >  **Hub Accounts**  >  **aktivieren.** Wenn Sie die Kennwortrotation aktivieren, versucht der Surface Hub, das Kennwort während der Wartungszeiten alle 7 Tage zu ändern. Kennwörter werden während einer Besprechung nicht geändert. Wenn seit der letzten Kennwortrotation 7 Tage vergangen sind, der Surface Hub jedoch deaktiviert war, wird versucht, das Kennwort sofort zu ändern, wenn es aktiviert ist, oder alle 10 Minuten, bis es erfolgreich war.

Die automatisch generierten Kennwörter enthalten 15 bis 32 Zeichen, einschließlich einer Kombination aus Groß- und Kleinbuchstaben, Zahlen und Sonderzeichen. Beachten Sie, dass beim Ändern des Kennworts des Gerätekontos das neue Kennwort nicht angezeigt wird. Wenn Sie sich beim Konto anmelden oder das Kennwort erneut angeben müssen (z. B. wenn Sie die Gerätekontoeinstellungen auf dem Surface Hub ändern möchten), müssen Sie Active Directory oder das Microsoft 365-Verwaltungsportal verwenden, um das Kennwort zurückzusetzen.

> [!IMPORTANT]
> Das Format, das beim Hinzufügen des Gerätekontos [](prepare-your-environment-for-surface-hub.md) zum Surface Hub verwendet wird, hat Auswirkungen darauf, welche Gerätemitgliedschaftsoption verwendet werden muss, damit die Kennwortrotation funktioniert. Wenn Sie das Konto im **Format "Domäne\Benutzername"** hinzufügen, verbinden Sie den Hub während der Ersteinrichtung mit dem lokalen Active Directory. Wenn Sie das Konto im Format hinzufügen, verbinden Sie den Hub bei der Ersteinrichtung `username@domain.com` mit Azure Active Directory. Andernfalls funktioniert die Kennwortrotation nicht.
