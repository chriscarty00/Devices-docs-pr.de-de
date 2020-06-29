---
title: Erweiterte UEFI-Sicherheitsfeatures für Surface Pro 3 (Surface)
description: In diesem Artikel wird beschrieben, wie Sie das UEFI-Update v3.11.760.0 installieren und konfigurieren, um zusätzliche Sicherheitsoptionen für Surface Pro 3-Geräte zu aktivieren.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: Sicherheit, Features, konfigurieren, Hardware, Gerät, benutzerdefiniert, Skript, Update
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 9460b4a5e8b44cbf4b6af57d01aab3b09afb49de
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832581"
---
# <span data-ttu-id="1691d-104">Erweiterte UEFI-Sicherheitsfeatures für Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="1691d-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="1691d-105">In diesem Artikel wird beschrieben, wie Sie das UEFI-Update v3.11.760.0 installieren und konfigurieren, um zusätzliche Sicherheitsoptionen für Surface Pro 3-Geräte zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1691d-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="1691d-106">Das UEFI-Update v3.11.760.0 bietet zusätzliche Optionen zur präziseren Kontrolle über die Sicherheit von Surface-Geräten. So können Sie beispielsweise bestimmte Hardwaregeräte deaktivieren und das Starten von diesen Geräten verhindern.</span><span class="sxs-lookup"><span data-stu-id="1691d-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="1691d-107">Nachdem das UEFI-Update auf einem Gerät installiert wurde, können Sie es manuell oder automatisch durch Ausführung eines Skripts konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1691d-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="1691d-108">Manuelle Installation des UEFI-Updates</span><span class="sxs-lookup"><span data-stu-id="1691d-108">Manually install the UEFI update</span></span>


<span data-ttu-id="1691d-109">Bevor Sie die erweiterten Sicherheitsfeatures des Surface-Geräts konfigurieren können, müssen Sie zunächst das UEFI-Update v3.11.760.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="1691d-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="1691d-110">Über Windows Update wird dieses Update automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="1691d-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="1691d-111">Weitere Informationen zum Konfigurieren von Windows zur automatischen Aktualisierung über Windows Update finden Sie unter [Konfigurieren und Verwenden des Features „Automatische Updates“ in Windows](https://support.microsoft.com/kb/306525).</span><span class="sxs-lookup"><span data-stu-id="1691d-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="1691d-112">Zum Aktualisieren der UEFI auf Surface Pro 3 können Sie die Surface UEFI-Updates als Teil der Firmware und des Treiberpakets für Surface Pro 3 herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="1691d-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="1691d-113">Diese Firmware- und Treiberpakete stehen auf der [Surface Pro 3-Seite](https://www.microsoft.com/download/details.aspx?id=38826) im Microsoft Download Center zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1691d-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="1691d-114">Weitere Informationen zu den Firmware- und Treiberpaketen finden Sie unter [Herunterladen der neuesten Firmware und Treiber für Surface-Geräte](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="1691d-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="1691d-115">Die Firmware- und Treiberpakete stehen sowohl als eigenständige Windows Installer-Datei (.msi) als auch als Archivdatei (.zip) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1691d-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="1691d-116">Weitere Informationen zu diesen beiden Formaten sowie zum Aktualisieren ihrer Pakete mithilfe dieser Formate finden Sie unter [Verwalten von Treiber- und Firmwareupdates für Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="1691d-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="1691d-117">Manuelles Konfigurieren zusätzlicher Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1691d-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="1691d-118">Auf einem Surface-Gerät können Sie das Firmwaresetup aufrufen, indem Sie das Gerät zunächst ausschalten, die **Lauter**-Taste gedrückt halten, und dann die **Ein/Aus**-Taste drücken und loslassen. Wenn das Gerät zu starten begonnen hat, lassen Sie die **Lauter**-Taste los.</span><span class="sxs-lookup"><span data-stu-id="1691d-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="1691d-119">Nachdem das UEFI-Update v3.11.760.0 auf einem Surface-Gerät installiert wurde, wird ein zusätzliches UEFI-Menü mit dem Namen **Advanced Device Security** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1691d-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="1691d-120">Wenn Sie auf dieses Menü klicken, werden die folgenden Optionen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1691d-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="1691d-121">Option</span><span class="sxs-lookup"><span data-stu-id="1691d-121">Option</span></span>         | <span data-ttu-id="1691d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1691d-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="1691d-123">Verfügbare Einstellungen (Standardeinstellungen fett formatiert)</span><span class="sxs-lookup"><span data-stu-id="1691d-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="1691d-124">Netzwerkstart</span><span class="sxs-lookup"><span data-stu-id="1691d-124">Network Boot</span></span>   | <span data-ttu-id="1691d-125">Aktiviert oder deaktiviert die Fähigkeit des Surface-Geräts, vom Netzwerk zu starten (PXE-Start).</span><span class="sxs-lookup"><span data-stu-id="1691d-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="1691d-126">**Aktiviert**, nicht startbar</span><span class="sxs-lookup"><span data-stu-id="1691d-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="1691d-127">Side USB</span><span class="sxs-lookup"><span data-stu-id="1691d-127">Side USB</span></span>       | <span data-ttu-id="1691d-128">Aktiviert oder deaktiviert den seitlichen USB-Anschluss am Surface-Gerät.</span><span class="sxs-lookup"><span data-stu-id="1691d-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="1691d-129">Zusätzlich kann der USB-Port aktiviert werden, aber das Starten über USB wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="1691d-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="1691d-130">**Aktiviert**, nicht startbar, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="1691d-131">Docking Port</span><span class="sxs-lookup"><span data-stu-id="1691d-131">Docking Port</span></span>   | <span data-ttu-id="1691d-132">Aktiviert oder deaktiviert die Anschlüsse an der Surface-Dockingstation.</span><span class="sxs-lookup"><span data-stu-id="1691d-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="1691d-133">Zusätzlich kann der Dockinganschluss aktiviert, aber das Starten über einen beliebigen USB- oder Ethernet-Anschluss an der Dockingstation blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="1691d-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="1691d-134">**Aktiviert**, nicht startbar, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="1691d-135">Frontkamera</span><span class="sxs-lookup"><span data-stu-id="1691d-135">Front Camera</span></span>   | <span data-ttu-id="1691d-136">Aktiviert oder deaktiviert die Kamera an der Vorderseite des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="1691d-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="1691d-137">**Aktiviert**, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="1691d-138">Rückwärtige Kamera</span><span class="sxs-lookup"><span data-stu-id="1691d-138">Rear Camera</span></span>    | <span data-ttu-id="1691d-139">Aktiviert oder deaktiviert die Kamera an der Rückseite des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="1691d-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="1691d-140">**Aktiviert**, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="1691d-141">On Board Audio</span><span class="sxs-lookup"><span data-stu-id="1691d-141">On Board Audio</span></span> | <span data-ttu-id="1691d-142">Aktiviert oder deaktiviert die Wiedergabe von Audioinhalten auf dem Surface-Gerät.</span><span class="sxs-lookup"><span data-stu-id="1691d-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="1691d-143">**Aktiviert**, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="1691d-144">microSD</span><span class="sxs-lookup"><span data-stu-id="1691d-144">microSD</span></span>        | <span data-ttu-id="1691d-145">Aktiviert oder deaktiviert den MicroSD-Kartensteckplatz am Surface-Gerät.</span><span class="sxs-lookup"><span data-stu-id="1691d-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="1691d-146">**Aktiviert**, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="1691d-147">WLAN</span><span class="sxs-lookup"><span data-stu-id="1691d-147">WiFi</span></span>           | <span data-ttu-id="1691d-148">Aktiviert oder deaktiviert den integrierten WLAN-Transceiver des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="1691d-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="1691d-149">Dadurch wird auch Bluetooth deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1691d-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="1691d-150">**Aktiviert**, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="1691d-151">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="1691d-151">Bluetooth</span></span>      | <span data-ttu-id="1691d-152">Aktiviert oder deaktiviert den integrierten Bluetooth-Transceiver des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="1691d-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="1691d-153">**Aktiviert**, deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1691d-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="1691d-154">Automatisieren zusätzlicher Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1691d-154">Automate additional security settings</span></span>


<span data-ttu-id="1691d-155">Mithilfe der [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) aus dem Microsoft Download Center können IT-Experten mit Administratorrechten die Konfiguration der UEFI-Einstellungen automatisieren.</span><span class="sxs-lookup"><span data-stu-id="1691d-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="1691d-156">Diese Tools installieren eine .NET-Assembly, die über eine benutzerdefinierte Anwendung oder ein Skript aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1691d-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="1691d-157">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1691d-157">Prerequisites</span></span>**

-   <span data-ttu-id="1691d-158">Die folgenden Beispielskripts nutzen die oben erwähnte Erweiterung und nehmen daher an, dass das Tool auf dem Gerät installiert wurde, das verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="1691d-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="1691d-159">Die Skripts müssen mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1691d-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="1691d-160">Der Windows PowerShell-Befehl [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) muss vor der Ausführung von Beispielskripts aufgerufen werden, wenn diese nicht digital signiert sind.</span><span class="sxs-lookup"><span data-stu-id="1691d-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="1691d-161">Beispielskripts</span><span class="sxs-lookup"><span data-stu-id="1691d-161">Sample scripts</span></span>**

><span data-ttu-id="1691d-162">**Hinweis**:&nbsp;&nbsp;Das in den folgenden Beispielskripts verwendete UEFI-Kennwort wird als Klartext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1691d-162">**Note**:&nbsp;&nbsp;The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="1691d-163">Wir empfehlen dringend, die Skripts an einem geschützten Speicherort abzulegen und sie in einer kontrollierten Umgebung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1691d-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="1691d-164">Alle konfigurierbaren Optionen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="1691d-164">Show all configurable options:</span></span>

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

<span data-ttu-id="1691d-165">UEFI-Kennwort festlegen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="1691d-165">Set or change UEFI password:</span></span>

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="1691d-166">Status der vorgeschlagenen Änderungen prüfen:</span><span class="sxs-lookup"><span data-stu-id="1691d-166">Check status of proposed changes:</span></span>

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

<span data-ttu-id="1691d-167">UEFI-Standardwerte wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="1691d-167">Revert UEFI to default values:</span></span>

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

<span data-ttu-id="1691d-168">Interpretation des Statuscodes</span><span class="sxs-lookup"><span data-stu-id="1691d-168">Status code interpretation</span></span>

-   <span data-ttu-id="1691d-169">00 - Das vorgeschlagene Update war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1691d-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="1691d-170">02 - Einer der vorgeschlagenen Werte besaß einen ungültigen Wert.</span><span class="sxs-lookup"><span data-stu-id="1691d-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="1691d-171">03 - Ein Satz vorgeschlagener Werte wurde nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="1691d-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="1691d-172">0F - Das Kennwort zum Entsperren stimmt nicht mit dem aktuell festgelegten Kennwort überein.</span><span class="sxs-lookup"><span data-stu-id="1691d-172">0F - The unlock password did not match currently set password</span></span>

 

 





