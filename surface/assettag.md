---
title: DGM-Inventar-Tag-Tool
description: In diesem Thema wird die Verwendung des Surface-Asset-Tag-Tools erläutert.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832578"
---
# <span data-ttu-id="9cadc-103">DGM-Inventar-Tag-Tool</span><span class="sxs-lookup"><span data-stu-id="9cadc-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="9cadc-104">Surface-Ressourcen-Tag ist ein Befehlszeilen-Interface-Dienstprogramm, mit dem Sie einen zugewiesenen Ressourcen-Tag-Wert für Surface-Geräte anzeigen, zuweisen und ändern können.</span><span class="sxs-lookup"><span data-stu-id="9cadc-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="9cadc-105">Es funktioniert auf Surface pro 3 und auf allen neueren Surface-Geräten.</span><span class="sxs-lookup"><span data-stu-id="9cadc-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="9cadc-106">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="9cadc-106">System requirements</span></span>

- <span data-ttu-id="9cadc-107">Surface pro 3 oder höher</span><span class="sxs-lookup"><span data-stu-id="9cadc-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="9cadc-108">UEFI-Firmwareversion 3.9.150.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="9cadc-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="9cadc-109">Verwenden der Surface-Ressourcenkategorie</span><span class="sxs-lookup"><span data-stu-id="9cadc-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="9cadc-110">So führen Sie eine DGM-Anlagen Kategorie aus:</span><span class="sxs-lookup"><span data-stu-id="9cadc-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="9cadc-111">Laden Sie auf dem Surface-Gerät **Surface Asset Tag.zip** aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703)herunter, extrahieren Sie die ZIP-Datei, und speichern Sie AssetTag.exe im gewünschten Ordner (in diesem Beispiel C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="9cadc-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9cadc-112">Verwenden Sie für Surface pro X die Anwendung mit dem Namen **AssetTag_x86** in der ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="9cadc-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="9cadc-113">Öffnen Sie eine Befehlskonsole als Administrator, und führen Sie AssetTag.exe aus, und geben Sie den vollständigen Pfad zum Tool ein.</span><span class="sxs-lookup"><span data-stu-id="9cadc-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="9cadc-114">Oberfläche neu starten</span><span class="sxs-lookup"><span data-stu-id="9cadc-114">Restart Surface.</span></span>

### <span data-ttu-id="9cadc-115">Befehle für das Element-Tag-Tool</span><span class="sxs-lookup"><span data-stu-id="9cadc-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="9cadc-116">In den folgenden Beispielen wird AssetTag.exe in einem Verzeichnis auf einem lokalen Computer (C:\assets) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9cadc-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="9cadc-117">Führen Sie AssetTag-g aus, um die vorgeschlagene Inventar Kategorie zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9cadc-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="9cadc-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cadc-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="9cadc-119">Führen Sie AssetTag-s aus, um die vorgeschlagene Ressourcenkategorie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9cadc-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="9cadc-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cadc-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="9cadc-121">Führen Sie AssetTag-s testassettag12 aus, um die vorgeschlagene Ressourcenkategorie einzurichten.</span><span class="sxs-lookup"><span data-stu-id="9cadc-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="9cadc-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cadc-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="9cadc-123">Der Wert für das Elementtag muss zwischen 1 und 36 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9cadc-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="9cadc-124">Gültige Zeichen sind a-z, a-z, 0-9, Punkt (.) und Bindestrich (-).</span><span class="sxs-lookup"><span data-stu-id="9cadc-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="9cadc-125">Verwalten von Inventar Kategorien</span><span class="sxs-lookup"><span data-stu-id="9cadc-125">Managing asset tags</span></span>

<span data-ttu-id="9cadc-126">Sie können die vorhandene Objektkategorie in den UEFI-Einstellungen unter Geräteinformationen anzeigen (**Systemsteuerung > Wiederherstellung > Advanced Startup > jetzt neu starten**.)</span><span class="sxs-lookup"><span data-stu-id="9cadc-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="9cadc-127">Die folgende Abbildung zeigt die Ergebnisse der Ausführung des Asset-Tag-Tools auf Surface go.</span><span class="sxs-lookup"><span data-stu-id="9cadc-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="9cadc-128">Ergebnisse des laufenden Surface-Asset-Tag-Tools auf Surface go.</span><span class="sxs-lookup"><span data-stu-id="9cadc-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="9cadc-129">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="9cadc-129">Figure 1.</span></span>** <span data-ttu-id="9cadc-130">Ergebnisse des laufenden Surface-Asset-Tag-Tools auf Surface go</span><span class="sxs-lookup"><span data-stu-id="9cadc-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="9cadc-131">Alternativ können Sie mithilfe von WMI die vorhandene Objektkategorie auf einem Gerät Abfragen:</span><span class="sxs-lookup"><span data-stu-id="9cadc-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="9cadc-132">(Get-WMIObject-Query "Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="9cadc-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="9cadc-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cadc-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="9cadc-134">Mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cadc-134">Using PowerShell</span></span>

<span data-ttu-id="9cadc-135">Mit dem folgenden Skript können Sie den vorgeschlagenen Wert abrufen und Fehler interpretieren.</span><span class="sxs-lookup"><span data-stu-id="9cadc-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
