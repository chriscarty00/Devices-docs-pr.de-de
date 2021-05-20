---
title: Referenz für Surface-System-SKU
description: Siehe einen Verweis auf Systemmodell- und System-SKU-Namen für alle Surface-Geräte.
keywords: uefi, configure, firmware, secure, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/19/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: bf3fb926c5e66f5f02f921f1c0d4fbe5f016f02d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577045"
---
# <a name="surface-system-sku-reference"></a>Referenz für Surface-System-SKU

Dieses Dokument enthält einen Verweis, der für verschiedene IT-Aufgaben verwendet werden kann, z. B. das Registrieren von Surface-Geräten bei Windows Autopilot oder das Überprüfen des Computerstatus eines bestimmten Geräts mit PowerShell oder WMI.

Systemmodell und System-SKU sind Variablen, die in den Tabellen des Systemverwaltungs-BIOS (System Management BIOS, SMBIOS) in der UEFI-Ebene von Surface-Geräten gespeichert sind. Verwenden Sie den System-SKU-Namen, wenn Sie zwischen Geräten mit demselben Systemmodellnamen unterscheiden müssen, z. B. Surface Pro und Surface Pro LTE Advanced.

| Gerät   | Systemmodell | System-SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE North America                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE außerhalb von Nordamerika und Y!mobile in Japan | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro mit LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Commercial | System Go | Surface_Go_1825_Commercial |
| Surface Go Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X mit SQ2-Prozessor                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 
| Surface Laptop 4 13" Intel | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop 4 15" Intel | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop 4 15" AMD   | Surface Laptop 4 | Surface_Laptop_4_1952:1953     | 
| Surface Laptop 4 13" AMD   | Surface Laptop 4 | Surface_Laptop_4_1958:1959    | 
| Surface Hub 2S 50"  | Surface Hub 2S | Surface Hub 2S   | 
| Surface Hub 2S 85"  | Surface Hub 2S | Surface Hub 2S 85   | 

## <a name="examples"></a>Beispiele 

**Abrufen der SKU mithilfe von PowerShell**  
Verwenden Sie den folgenden PowerShell-Befehl, um die System-SKU-Informationen zu ziehen:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Abrufen der SKU mithilfe von Systeminformationen**  
Sie finden auch die System-SKU und das Systemmodell für ein Gerät in **Systeminformationen.** Gehen Sie hierzu folgendermaßen vor:

1. Wählen **Sie Start**aus, und geben Sie **msInfo32** in das Suchfeld ein.  
1. Wählen **Sie Systeminformationen**aus.

**Verwenden der SKU in einer Tasksequenz-WMI-Bedingung**  
Sie können die System-SKU-Informationen im Microsoft Deployment Toolkit (MDT) oder Microsoft Endpoint Configuration Manager als Teil einer Tasksequenz-WMI-Bedingung verwenden.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

## <a name="learn-more"></a>Mehr erfahren

- [WMI-Referenz](https://docs.microsoft.com/windows/win32/wmisdk/wmi-reference)
- [Surface-Registrierungsunterstützung für Windows-Autopilot](surface-autopilot-registration-support.md)
