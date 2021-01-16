---
title: System-SKU-Referenz (Surface)
description: Siehe eine Referenz zu Systemmodell- und System-SKU-Namen.
keywords: uefi, configure, firmware, secure, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 2140faf346229842bffc4f9348041f4667b94686
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271369"
---
# Referenz zur System-SKU

Dieses Dokument enthält eine Referenz zu Systemmodell- und System-SKU-Namen, mit deren Hilfe Sie den Computerstatus eines bestimmten Geräts mithilfe von PowerShell oder WMI schnell ermitteln können.

Systemmodell und System-SKU sind Variablen, die in den System management BIOS (SMBIOS)-Tabellen auf der UEFI-Ebene von Surface-Geräten gespeichert werden. Verwenden Sie den System-SKU-Namen, wenn Sie zwischen Geräten mit demselben Systemmodellnamen unterscheiden müssen, z. B. Surface Pro und Surface Pro LTE Advanced.

| Gerät   | Systemmodell | System-SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Nordamerika                                  | Surface 3        | Surface_3_NAG                    |
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
| Surface Pro X mit EINEM SQ2-Prozessor                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 

## Beispiele 

**Abrufen der SKU mithilfe von PowerShell**  
Verwenden Sie den folgenden PowerShell-Befehl, um die System-SKU-Informationen zu erhalten:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Abrufen der SKU mithilfe von Systeminformationen**  
Die System-SKU und das Systemmodell für ein Gerät finden Sie auch in **den Systeminformationen.** Gehen Sie hierzu folgendermaßen vor:

1. Wählen **Sie "Start"** aus, und geben Sie **dann "MSInfo32"** in das Suchfeld ein.  
1. Wählen Sie **Systeminformationen aus.**

**Verwenden der SKU in einer Tasksequenz-WMI-Bedingung**  
Sie können die System-SKU-Informationen im Microsoft Deployment Toolkit (MDT) oder Microsoft Endpoint Configuration Manager als Teil einer Tasksequenz-WMI-Bedingung verwenden.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
