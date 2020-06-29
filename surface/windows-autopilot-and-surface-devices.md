---
title: Windows Autopilot und Surface-Geräte
ms.reviewer: ''
manager: laurawi
description: Informieren Sie sich über die Windows Autopilot-Bereitstellungsoptionen für Surface Devices.
keywords: Autopilot, Windows 10, DGM, Bereitstellung
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832482"
---
# Windows Autopilot und Surface-Geräte

Windows Autopilot ist eine Cloud-basierte Bereitstellungstechnologie in Windows 10. Sie können Windows Autopilot verwenden, um Geräte in einem Zero-Touch-Prozess Remote bereitzustellen und zu konfigurieren.

Windows Autopilot-registrierte Geräte werden beim ersten Start über das Internet identifiziert, und zwar über eine eindeutige Geräte Signatur, die als *Hardwarehash*bezeichnet wird. Sie werden automatisch registriert und mit modernen Verwaltungslösungen wie Azure Active Directory (Azure AD) und Verwaltung mobiler Geräte konfiguriert.

Sie können Surface-Geräte zum Zeitpunkt des Kaufs von einem Surface-Partner registrieren, der für Windows Autopilot aktiviert ist. Diese Partner können neue Geräte direkt an Ihre Benutzer senden. Die Geräte werden automatisch registriert und konfiguriert, wenn Sie zum ersten Mal aktiviert werden. Dieser Prozess beseitigt die rebildung während der Bereitstellung, mit der Sie neue Agile Methoden für die Geräteverwaltung und-Verteilung implementieren können.

## Moderne Verwaltung

Autopilot ist die empfohlene Bereitstellungsoption für Surface-Geräte, einschließlich Surface pro 7, Surface Laptop 3 und Surface pro X, das speziell für die Bereitstellung über Autopilot entwickelt wurde.

 Am besten registrieren Sie Ihre Surface-Geräte mithilfe eines Microsoft-Cloud-Lösungsanbieters. In diesem Schritt können Sie die UEFI-Firmwareeinstellungen direkt aus InTune auf Surface verwalten. Dadurch ist es nicht mehr notwendig, Geräte für die Zertifikatverwaltung physisch zu berühren. Details finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md) .

## Überlegungen zur Windows-Version

Die Breite Bereitstellung von Surface-Geräten über Windows Autopilot, einschließlich der Registrierung von Surface-Partnern zum Zeitpunkt des Kaufs, erfordert Windows 10 Version 1709 (Fall Creators Update) oder höher.

Diese Windows-Versionen unterstützen einen 4.000-Byte (4K)-Hashwert, der Geräte für Windows Autopilot eindeutig identifiziert, was für Bereitstellungen im Maßstab notwendig ist. Alle neuen Surface-Geräte, einschließlich Surface pro 7, Surface pro X und Surface Laptop 3, werden mit Windows 10, Version 1903 oder höher, ausgeliefert.

## Erfahrungsaustausch auf Oberflächen Geräten, die repariert oder ersetzt werden müssen

Microsoft überprüft automatisch alle Oberflächen auf die Autopilot-Registrierung und hebt die Registrierung des Geräts vom Mandanten des Kunden auf.  Microsoft stellt sicher, dass das Ersatzgerät für Windows Autopilot registriert ist, sobald ein Ersatz an den Kunden zurückgeliefert wurde. Dieser Dienst ist für alle Geräte-Exchange-Service Bestellungen direkt mit Microsoft verfügbar.

> [!NOTE]
> Wenn Kunden einen Partner für die Rückgabe von Geräten verwenden, ist der Partner für die Verwaltung des Exchange-Prozesses verantwortlich, einschließlich der Deregistrierung und Anmeldung von Geräten in Windows Autopilot.

## Für Windows Autopilot aktivierte Surface-Partner

Wählen Sie Surface Partners kann Surface Devices in Windows Autopilot für Sie zum Zeitpunkt des Kaufs registrieren. Sie können auch registrierte Geräte direkt an Ihre Benutzer senden. Die Geräte können mithilfe von Windows Autopilot, Azure AD und der Verwaltung mobiler Geräte vollständig über einen Zero-Touch-Prozess konfiguriert werden.

Surface-Partner, die für Windows Autopilot aktiviert sind, umfassen Folgendes:

| US-Partner | Globale Partner | US-Distributoren |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [Auch](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Verbindung](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [Atea](https://www.atea.com/) | * [TechData](https://www.techdata.com/)  |
| * [Einblick](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [Shi](https://www.shi.com/Surface) | * [CANCOM](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Geschützte Vertrauensstellung](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## Mehr erfahren

Weitere Informationen zu Windows Autopilot finden Sie unter:
- [Übersicht über Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Anforderungen für Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)