---
title: Surface-Registrierungsunterstützung für Windows-Autopilot
description: In diesem Artikel werden die Anforderungen für die Übermittlung von Registrierungsanforderungen für Autopilot an den Microsoft Support beschrieben.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 4ff3803701ffe71e1c5c0c36200c40e833a7fb25
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271389"
---
# Surface-Registrierungsunterstützung für Windows-Autopilot

Ein vereinfachtes Verfahren zum Registrieren von Surface-Geräten für die Windows -Autopilot-Bereitstellung ist jetzt über den Microsoft Support verfügbar. Ab September 2020 können Kunden und Microsoft Cloud Solution Providers (CSPs) Surface-Geräte registrieren, indem sie Anforderungen an den Microsoft Support senden. Diese Seite beschreibt die Anforderungen für die folgenden unterstützten Autopilot-Registrierungsszenarien:
 

- **Surface Device Autopilot Registration**. Sendet die Anforderung zur Registrierung von Surface-Geräten bei Windows Autopilot.
- **Hardwarehashanforderung für Surface-Geräte.** Sendet eine Anforderung an den Microsoft-Support, um Ihnen Hardwarehashes bereitzustellen, die Kunden oder CSPs verwenden können, um Geräte über Microsoft Intune oder das Microsoft Partner Center selbst zu registrieren.
- **Surface Device Autopilot Deregistration.** Sendet eine Anforderung zum Löschen von Geräten aus Windows Autopilot, die in der Regel in Szenarien verwendet werden, die das Ende der Lebensdauer des Geräts ermöglichen.

In der folgenden Tabelle finden Sie Details zu den Informationen, die Sie sammeln müssen, bevor Sie Registrierungsanforderungen an den Microsoft Support übermitteln.
 
**Tabelle1. Erforderliche Informationen für Registrierungsanforderungen für Autopilot**
 

| Erforderliche Informationen                   | Beschreibung                                                                                                                                                                                                                                                                                    | Registrierung von Autopilot | Hardwarehashanforderung | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory-Mandanten-ID**   | Ihre Azure Active Directory-Mandanten-ID ist eine GUID (Globally Unique Identifier), die sich vom Namen oder der Domäne Ihrer Organisation abh?nt.<br> <br>Um Ihre Mandanten-ID zu finden, melden Sie sich hier im Azure Portal [an.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Azure Active Directory Domain Name** | Ihr Domänenname auf oberster Ebene; Beispiel: contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Nachweis des Besitzes**                 | Überprüfen Sie den Besitznachweis, indem Sie die ursprüngliche Rechnung oder Verkaufsrechnung im PDF-Format hochladen. Screenshots werden nicht akzeptiert.<br> <br>Die Rechnung muss Folgendes enthalten:<br>Seriennummern des Geräts.<br>Firmenname.                                                           | Y                      | Y                     | Y                           |
| **Seriennummern des Geräts**              | Laden Sie die Excel-Datei mit jeder Seriennummer des Geräts in einer neuen Zeile in das CSV-Format hoch.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Übermitteln von Supportanfragen

  [![Get Autopilot Registration Support for Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Mehr erfahren

- [Windows Autopilot und Surface-Geräte](windows-autopilot-and-surface-devices.md)
- [Registrieren von Windows-Geräten in Intune mit Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Übersicht über Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

