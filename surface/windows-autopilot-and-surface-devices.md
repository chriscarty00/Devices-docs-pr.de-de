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
ms.date: 9/14/2020
ms.openlocfilehash: d2a948d236ffa286192937cc5ca71099b6eeeafb
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016424"
---
# Windows Autopilot und Surface-Geräte

Windows Autopilot ist eine Cloud-basierte Bereitstellungstechnologie in Windows 10. Sie können Windows Autopilot verwenden, um Geräte in einem Zero-Touch-Prozess Remote bereitzustellen und zu konfigurieren.

In der Regel verbringen IT-Experten viel Zeit mit dem Erstellen und Anpassen von Bildern, die später auf Geräten bereitgestellt werden, die bereits über ein perfekt geeignetes Betriebssystem verfügen, das bereits auf Ihnen installiert ist. Mithilfe einer Sammlung von Technologien zum Einrichten und Konfigurieren von Windows-Geräten führt Windows Autopilot einen neuen Zero-Touch-Bereitstellungsansatz ein. Auf diese Weise kann eine IT-Abteilung Bilder mit wenig zu keiner Infrastruktur konfigurieren/anpassen, um Sie zu verwalten, und ein einfaches und einfaches Verfahren. Aus Sicht des Benutzers sind nur einige einfache Schritte erforderlich, um die Oberfläche in einen produktiven Zustand zu bringen. Tatsächlich besteht die einzige vom Endbenutzer benötigte Interaktion darin, eine Verbindung mit einem Netzwerk herzustellen und deren Anmeldeinformationen zu überprüfen. Alles nach diesem ist vollständig automatisiert.

Mit Windows Autopilot können Sie Folgendes ausführen:

- Automatisches beitreten von Geräten zu Azure Active Directory (Azure AD).
- Automatisches Registrieren von Geräten in MDM-Dienste wie Microsoft InTune (erfordert ein Azure AD Premium-Abonnement)
- Einschränkung der Administratorkontoerstellung. Autopilot ist die einzige Möglichkeit, die erste Person, die sich bei Windows anmeldet, als Standardbenutzer einzugeben.
- Erstellen und automatisches Zuweisen von Geräten zu Konfigurationsgruppen auf der Grundlage von Geräteprofilen.
- Passen Sie die Inhalte und das Branding von OOBE (außerhalb des Felds) an, um die organisatorischen Anforderungen zu erfüllen.
- Aktivieren Sie die vollständige Gerätekonfiguration mit InTune.
- Geräte remote zurücksetzen oder neu starten

## Funktionsweise

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

## Microsoft-Support-Registrierung

Kunden und Microsoft Cloud Solution Provider (LSP) haben die Möglichkeit, Surface Devices zu registrieren, indem Sie Anfragen an den Microsoft-Support senden. Weitere Informationen finden Sie unter [Surface-Registrierungsunterstützung für Windows Autopilot](surface-autopilot-registration-support.md).

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
- [Surface-Registrierungsunterstützung für Windows Autopilot](surface-autopilot-registration-support.md)