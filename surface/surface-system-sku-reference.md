---
title: System-SKU-Referenz (Surface)
description: Sehen Sie einen Verweis auf Systemmodell-und System-SKU-Namen.
keywords: UEFI, konfigurieren, Firmware, sicher, Semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ec1d53a4bdbcaaf6606dcb0e52fc81de92a2a53b
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114543"
---
# System-SKU-Referenz

Dieses Dokument enthält einen Verweis auf Systemmodell-und System-SKU-Namen, mit denen Sie den Computerzustand eines bestimmten Geräts mithilfe von PowerShell oder WMI schnell ermitteln können.

Systemmodell und System-SKU sind Variablen, die in den SMBIOS-Tabellen (System Management BIOS) auf der UEFI-Ebene von Surface Devices gespeichert werden. Verwenden Sie den System-SKU-Namen, wenn Sie zwischen Geräten mit dem gleichen Systemmodell Namen unterscheiden möchten, beispielsweise Surface pro und Surface pro mit LTE Advanced.

| Gerät   | System Modell | System-SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFi                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE bei&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Nordamerika                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE außerhalb von Nordamerika und Y! Mobile in Japan | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro mit LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| DGM-Buch 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| DGM-Buch 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| DGM-Buch 3 13 "                                        | DGM-Buch 3   | Surface_Book_3_1900                |
| DGM-Buch 3 15 "                                        | DGM-Buch 3   | Surface_Book_3_1899
| Surface go LTE-Werbespot | System Go | Surface_Go_1825_Commercial |
| Surface go-Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface go-Werbespot                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Werbespot                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface pro X mit SQ2-Prozessor                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13 "Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15 "Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15 "AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop go  | Surface Laptop go | Surface_Laptop_Go_1943      | 

## Beispiele 

**Abrufen der SKU mithilfe von PowerShell**  
Verwenden Sie den folgenden PowerShell-Befehl, um die System-SKU-Informationen abzurufen:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Abrufen der SKU mithilfe von System Informationen**  
Sie können auch die System-SKU und das Systemmodell für ein Gerät in **Systeminformationen**finden. Gehen Sie hierzu folgendermaßen vor:

1. Wählen Sie **Start**aus, und geben Sie **msinfo32** in das Suchfeld ein.  
1. Wählen Sie **System Informationen**aus.

**Verwenden der SKU in einer Tasksequenz-WMI-Bedingung**  
Sie können die System-SKU-Informationen im Microsoft Deployment Toolkit (MDT) oder Microsoft Endpoint Configuration Manager als Teil einer Tasksequenz-WMI-Bedingung verwenden.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
