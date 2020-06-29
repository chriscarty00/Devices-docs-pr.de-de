---
title: App-Kompatibilität für Surface Pro X
description: Dieser Artikel enthält einführende Informationen zur APP-Kompatibilität für Surface pro X ARM-basierte PCs.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833193"
---
# App-Kompatibilität für Surface Pro X

Anwendungen werden auf ARM-basierten Windows 10-PCs wie Surface pro X. Einschränkungen unterschiedlich ausgeführt:

- **Treiber für Hardware, Spiele und apps funktionieren nur, wenn Sie für einen Windows 10 ARM-basierten PC entwickelt wurden**. Weitere Informationen finden Sie bei dem Hardwarehersteller oder der Organisation, die den Treiber entwickelt hat. Treiber sind Softwareprogramme, die mit Hardwaregeräten kommunizieren – Sie werden häufig für Antivirus-und Antimalwaresoftware, Druck-oder PDF-Software, Hilfstechnologien, CD-und DVD-Utilities sowie Virtualisierungssoftware verwendet. Wenn ein Treiber nicht funktioniert, funktioniert die APP oder Hardware, die davon abhängig ist, nicht (zumindest nicht vollständig). Peripheriegeräte und Geräte funktionieren nur, wenn die von ihnen abhängigen Treiber in Windows 10 integriert sind oder wenn der Hardware Entwickler ARM64-Treiber für das Gerät freigegeben hat.
- **64-Bit (x64)-apps funktionieren nicht**. Sie benötigen 64-Bit-Apps (ARM64), 32-Bit-Apps (ARM32) oder 32-Bit-Apps (x86). Normalerweise finden Sie 32-Bit (x86)-Versionen von apps, aber einige App-Entwickler bieten nur 64-Bit (x64)-apps.
- **Bestimmte Spiele funktionieren nicht**. Spiele und apps funktionieren nicht, wenn Sie eine Version von OpenGL verwenden, die größer als 1,1 ist, oder wenn Sie auf "Anti-Cheat"-Treibern angewiesen sind, die nicht für Windows 10 ARM-basierte PCs erstellt wurden. Erkundigen Sie sich bei Ihrem Spielherausgeber, ob ein Spiel funktioniert.
- **Apps, die die Windows-Umgebung anpassen, haben möglicherweise Probleme**. Dazu gehören einige Eingabemethoden-Editoren (IME), Hilfstechnologien und Cloud-Speicher-apps. Die Organisation, die die APP entwickelt, bestimmt, ob Ihre APP auf einem Windows 10 ARM-basierten PC funktioniert.
- **Einige Antivirus-Software von Drittanbietern kann nicht installiert werden**. Sie können die Antivirensoftware von Drittanbietern nicht auf einem Windows 10-ARM-basierten PC installieren. Die Windows-Sicherheit hilft Ihnen jedoch, die unterstützte Lebensdauer Ihres Windows 10-Geräts zu schützen.
- **Windows-Fax und-Scan steht nicht zur Verfügung**. Dieses Feature ist auf einem Windows 10 ARM-basierten PC nicht verfügbar.

Weitere Informationen zur APP-Kompatibilität finden Sie unter [häufig gestellte Fragen zu Windows 10 ARM-based PCs](https://support.microsoft.com/en-us/help/4521606) .
