---
title: Surface-Registrierungsunterstützung für Windows Autopilot
description: In diesem Artikel werden die Voraussetzungen für die Übermittlung von Autopilot-Registrierungsanforderungen an den Microsoft-Support beschrieben.
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
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016473"
---
# Surface-Registrierungsunterstützung für Windows Autopilot

Ein vereinfachtes Verfahren zum Registrieren von Surface-Geräten für die Windows Autopilot-Bereitstellung steht nun über den Microsoft-Support zur Verfügung. Ab September 2020 können Kunden und Microsoft Cloud Solution Provider (LSP) Surface Devices registrieren, indem Sie Anfragen an den Microsoft-Support senden. Auf dieser Seite werden die Anforderungen für die folgenden unterstützten Autopilot-Registrierungs Szenarien erläutert:
 

- **Autopilot-Registrierung für Surface-Geräte**. Sendet eine Anforderung zum Registrieren von Surface-Geräten in Windows Autopilot.
- **Hardware-Hash Anforderung für Surface-Geräte.** Sendet eine Anfrage an den Microsoft-Support, um Ihnen Hardware-Hashes zur Verfügung zu stellen, die Kunden oder LSP für die Selbstregistrierung von Geräten über Microsoft InTune oder das Microsoft Partner Center verwenden können.
- **Autopilot-Deregistrierung für Oberflächen Geräte.** Sendet eine Anforderung zum Löschen von Geräten von Windows Autopilot, die normalerweise in Szenarien für das Lebenszyklusende des Geräts verwendet wird.

In der folgenden Tabelle finden Sie Informationen zu den Informationen, die Sie sammeln müssen, bevor Sie Registrierungsanforderungen an den Microsoft-Support übermitteln.
 
**Tabelle1. Erforderliche Informationen für Autopilot-Registrierungsanforderungen**
 

| Erforderliche Informationen                   | Beschreibung                                                                                                                                                                                                                                                                                    | Autopilot-Registrierung | Hardware-Hash Anforderung | Autopilot<br>Abmeldung |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory-Mandanten-ID**   | Ihre Azure Active Directory-Mandanten-ID ist eine GUID (Globally Unique Identifier), die sich von Ihrem Organisationsnamen oder Ihrer Domäne unterscheidet.<br> <br>Um Ihre Mandanten-ID-Signatur im Azure-Portal zu finden, lesen Sie [hier](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | Y                      | N                     | Y                           |
| **Azure Active Directory-Domänen Name** | Ihr Domänenname auf oberster Ebene; Beispiel: contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Nachweis des Besitzes**                 | Überprüfen Sie den Beweis des Besitzes, indem Sie den ursprünglichen Kauf-oder Rechnungs Schein im PDF-Format hochladen. Screenshots werden nicht akzeptiert.<br> <br>Der Kaufvertrag oder die Rechnung muss Folgendes umfassen:<br>Geräteseriennummern.<br>Name des Unternehmens.                                                           | Y                      | Y                     | Y                           |
| **Geräteseriennummern**              | Hochladen einer Excel-Datei im CSV-Format mit jeder Geräteseriennummer in einer neuen Zeile                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Supportanfragen senden

  [![Get Autopilot-Registrierungsunterstützung für Surface](images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Mehr erfahren

- [Windows Autopilot und Surface-Geräte](windows-autopilot-and-surface-devices.md)
- [Registrieren von Windows-Geräten in Intune mit Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Übersicht über Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

