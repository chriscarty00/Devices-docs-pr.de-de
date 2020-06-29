---
title: Referenz für Surface-System-SKU
description: Dieses Thema enthält einen Verweis auf System-SKU-Namen, mit denen Sie schnell den Computerzustand eines bestimmten Geräts ermitteln können.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832845"
---
# DGM-System-SKU-Referenz
Dieses Dokument enthält einen Verweis auf System-SKU-Namen, mit denen Sie den Computerzustand eines bestimmten Geräts mithilfe von PowerShell, WMI und verwandten Tools schnell ermitteln können. 

System-SKU ist eine Variable (zusammen mit dem Systemmodell und anderen), die in SMBIOS-Tabellen (System Management BIOS) auf der UEFI-Ebene von Surface Devices gespeichert ist.  Verwenden Sie den System-SKU-Namen, wenn Sie zwischen Geräten mit dem gleichen Systemmodell Namen unterscheiden möchten, beispielsweise Surface pro und Surface pro mit LTE Advanced. 

| **Gerät**| **System Modell** | **System-SKU**|
| --- | ---| --- |
| Surface 3 WiFi                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE bei&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Nordamerika                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE außerhalb von Nordamerika und T-Mobile in Japan | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro mit LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| DGM-Buch 2-18cm                                        | Surface Book 2   | Surface_Book_1832                |
| DGM-Buch 2 15cm                                        | Surface Book 2   | Surface_Book_1793                |
| Surface go-Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface go-Werbespot                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Werbespot                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## Verwenden von System-SKU-Variablen 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### Systeminformationen
Sie können auch die System-SKU und das Systemmodell für ein Gerät in Systeminformationen finden. 
- Klicken Sie auf **Start**  >   **msinfo32**.  

### WMI
Sie können System-SKU-Variablen in einer Task Sequenz-WMI-Bedingung im Microsoft Deployment Toolkit (MDT) oder Microsoft Endpoint Configuration Manager verwenden. Beispiel: 

    - WMI-Namespace – Root\WMI
    - WQL-Abfrage – wählen Sie * aus MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796" aus.

 
 
 


