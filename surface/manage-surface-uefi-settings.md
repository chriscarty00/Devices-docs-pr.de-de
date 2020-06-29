---
title: Verwalten von Surface UEFI-Einstellungen
description: Mit den Surface UEFI-Einstellungen können Sie Geräte und Komponenten aktivieren oder deaktivieren, Sicherheitseinstellungen konfigurieren und Surface-Gerätestarteinstellungen anpassen.
keywords: Firmware, Sicherheit, Features, konfigurieren, Hardware
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833409"
---
# <span data-ttu-id="e50bd-104">Verwalten der Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e50bd-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="e50bd-105">Alle aktuellen und zukünftigen Generationen von Surface-Geräten verwenden eine einzigartige Unified Extensible Firmware Interface (UEFI), die von Microsoft speziell für diese Geräte entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="e50bd-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="e50bd-106">Oberflächen UEFI-Einstellungen bieten die Möglichkeit, integrierte Geräte und Komponenten zu aktivieren oder zu deaktivieren, die UEFI-Einstellungen vor Änderungen zu schützen und die Start Einstellungen des Surface-Geräts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="e50bd-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="e50bd-107">Unterstützung für Cloud-basiertes Management</span><span class="sxs-lookup"><span data-stu-id="e50bd-107">Support for cloud-based management</span></span>

<span data-ttu-id="e50bd-108">Mit DFCI-Profilen (Device Firmware Configuration Interface), die in Microsoft InTune integriert sind (jetzt in Public Preview verfügbar), erweitert die Oberfläche-UEFI-Verwaltung den modernen Verwaltungs Stapel auf die UEFI-Hardwareebene.</span><span class="sxs-lookup"><span data-stu-id="e50bd-108">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="e50bd-109">DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Kontrolle über Sicherheitseinstellungen, einschließlich Startoptionen und integrierte Peripheriegeräte, und legt die Grundlagen für fortschrittliche Sicherheitsszenarien in der Zukunft fest.</span><span class="sxs-lookup"><span data-stu-id="e50bd-109">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="e50bd-110">DFCI steht derzeit für Surface pro 7, Surface pro X und Surface Laptop 3 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e50bd-110">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="e50bd-111">Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="e50bd-111">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="e50bd-112">Menü "DGM-UEFI öffnen"</span><span class="sxs-lookup"><span data-stu-id="e50bd-112">Open Surface UEFI menu</span></span>

<span data-ttu-id="e50bd-113">So passen Sie die UEFI-Einstellungen während des Systemstarts an:</span><span class="sxs-lookup"><span data-stu-id="e50bd-113">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="e50bd-114">Fahren Sie die Oberfläche herunter, und warten Sie etwa 10 Sekunden, um sicherzustellen, dass Sie deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e50bd-114">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="e50bd-115">Halten Sie die **Lautstärke** Taste gedrückt, und drücken Sie gleichzeitig die **Power-Taste** , und lassen Sie sie los.</span><span class="sxs-lookup"><span data-stu-id="e50bd-115">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="e50bd-116">Wenn das Microsoft-oder Surface-Logo auf dem Bildschirm angezeigt wird, halten Sie die **Lautstärke** Taste gedrückt, bis der UEFI-Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e50bd-116">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="e50bd-117">UEFI-PC-Informationsseite</span><span class="sxs-lookup"><span data-stu-id="e50bd-117">UEFI PC information page</span></span>

<span data-ttu-id="e50bd-118">Auf der Seite PC-Informationen finden Sie detaillierte Informationen zu Ihrem Surface-Gerät:</span><span class="sxs-lookup"><span data-stu-id="e50bd-118">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="e50bd-119">**Modell** – das Modell Ihres Surface-Geräts wird hier angezeigt, beispielsweise Surface Book 2 oder Surface pro 7.</span><span class="sxs-lookup"><span data-stu-id="e50bd-119">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="e50bd-120">Die genaue Konfiguration Ihres Geräts wird nicht angezeigt (z. B. Prozessor, Größe des Datenträgers oder Arbeitsspeicher).</span><span class="sxs-lookup"><span data-stu-id="e50bd-120">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="e50bd-121">**UUID** – Die UUID-Nummer gilt speziell für Ihr Gerät und wird verwendet, um das Gerät während der Bereitstellung oder Verwaltung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e50bd-121">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="e50bd-122">**Seriennummer** – Diese Nummer wird zum Identifizieren dieses speziellen Surface-Geräts für die Bestandskennzeichnung und Supportszenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="e50bd-122">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="e50bd-123">**Bestandskennzeichen** – Das Bestandskennzeichen wird dem Surface-Gerät mit dem [Asset Tag Tool](https://docs.microsoft.com/surface/assettag) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e50bd-123">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="e50bd-124">Außerdem finden Sie detaillierte Informationen zur Firmware des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="e50bd-124">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="e50bd-125">Surface-Geräte verfügen über mehrere interne Komponenten, die jeweils unterschiedliche Versionen der Firmware ausführen.</span><span class="sxs-lookup"><span data-stu-id="e50bd-125">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="e50bd-126">Die Firmwareversion der folgenden Geräte wird auf der Seite **PC-Informationen** angezeigt (siehe Abbildung 1):</span><span class="sxs-lookup"><span data-stu-id="e50bd-126">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="e50bd-127">System-UEFI</span><span class="sxs-lookup"><span data-stu-id="e50bd-127">System UEFI</span></span> 

- <span data-ttu-id="e50bd-128">SAM-Controller</span><span class="sxs-lookup"><span data-stu-id="e50bd-128">SAM Controller</span></span> 

- <span data-ttu-id="e50bd-129">Intel Management-Modul</span><span class="sxs-lookup"><span data-stu-id="e50bd-129">Intel Management Engine</span></span> 

- <span data-ttu-id="e50bd-130">System Embedded Controller</span><span class="sxs-lookup"><span data-stu-id="e50bd-130">System Embedded Controller</span></span> 

- <span data-ttu-id="e50bd-131">Touch-Firmware</span><span class="sxs-lookup"><span data-stu-id="e50bd-131">Touch Firmware</span></span> 

![Systeminformationen und Firmwareversionsinformationen](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="e50bd-133">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="e50bd-133">Figure 1.</span></span> <span data-ttu-id="e50bd-134">Systeminformationen und Firmwareversionsinformationen</span><span class="sxs-lookup"><span data-stu-id="e50bd-134">System information and firmware version information</span></span>*

<span data-ttu-id="e50bd-135">Aktuelle Informationen zur neuesten Firmware für Ihr Surface-Gerät finden Sie im [Surface-Updateverlauf](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) für Ihr Gerät.</span><span class="sxs-lookup"><span data-stu-id="e50bd-135">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="e50bd-136">UEFI-Sicherheitsseite</span><span class="sxs-lookup"><span data-stu-id="e50bd-136">UEFI Security page</span></span> 

![Konfigurieren von Surface UEFI-Sicherheitseinstellungen](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="e50bd-138">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="e50bd-138">Figure 2.</span></span> <span data-ttu-id="e50bd-139">Konfigurieren von Surface UEFI-Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e50bd-139">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="e50bd-140">Auf der Seite "Sicherheit" können Sie ein Kennwort zum Schützen von UEFI-Einstellungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="e50bd-140">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="e50bd-141">Dieses Kennwort muss eingegeben werden, wenn Sie das Surface-Gerät mit UEFI starten.</span><span class="sxs-lookup"><span data-stu-id="e50bd-141">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="e50bd-142">Das Kennwort kann die folgenden Zeichen enthalten (siehe Abbildung 3):</span><span class="sxs-lookup"><span data-stu-id="e50bd-142">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="e50bd-143">Großbuchstaben: A-Z</span><span class="sxs-lookup"><span data-stu-id="e50bd-143">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="e50bd-144">Kleinbuchstaben : a-z</span><span class="sxs-lookup"><span data-stu-id="e50bd-144">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="e50bd-145">Zahlen: 1-0</span><span class="sxs-lookup"><span data-stu-id="e50bd-145">Numbers: 1-0</span></span> 

- <span data-ttu-id="e50bd-146">Sonderzeichen:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: "'"</span><span class="sxs-lookup"><span data-stu-id="e50bd-146">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="e50bd-147">Das Kennwort muss mindestens 6 Zeichen lang sein und Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="e50bd-147">The password must be at least 6 characters and is case sensitive.</span></span> 

![Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="e50bd-149">Abbildung3.</span><span class="sxs-lookup"><span data-stu-id="e50bd-149">Figure 3.</span></span> <span data-ttu-id="e50bd-150">Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e50bd-150">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="e50bd-151">Auf der Seite Sicherheit können Sie außerdem die Konfiguration für den sicheren Start auf Ihrem Surface-Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="e50bd-151">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="e50bd-152">Die Technologie für den sicheren Start verhindert, dass nicht autorisierter Startcode auf Ihrem Surface Gerät gestartet werden kann, und sie schützt Sie vor Schadsoftwareinfektionen durch Bootkits und Rootkits.</span><span class="sxs-lookup"><span data-stu-id="e50bd-152">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="e50bd-153">Sie können den sicheren Start deaktivieren, damit Ihr Surface-Gerät Betriebssysteme von Drittanbietern oder startbare Medien starten kann.</span><span class="sxs-lookup"><span data-stu-id="e50bd-153">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="e50bd-154">Sie können auch den sicheren Start für die Verwendung von Zertifikaten von Drittanbietern konfigurieren, wie in Abbildung 4 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="e50bd-154">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="e50bd-155">Weitere Informationen finden Sie unter [Sicherer Start](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in der TechNet-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="e50bd-155">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Konfigurieren des sicheren Starts](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="e50bd-157">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="e50bd-157">Figure 4.</span></span> <span data-ttu-id="e50bd-158">Konfigurieren des sicheren Starts</span><span class="sxs-lookup"><span data-stu-id="e50bd-158">Configure Secure Boot</span></span>*

<span data-ttu-id="e50bd-159">Je nach Gerät können Sie möglicherweise auch feststellen, ob Ihr TPM aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e50bd-159">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="e50bd-160">Wenn die Einstellung **TPM aktivieren** nicht angezeigt wird, öffnen Sie TPM. msc in Windows, um den Status zu überprüfen, wie in Abbildung 5 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e50bd-160">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="e50bd-161">Das TPM wird zur Authentifizierung der Verschlüsselung Ihrer Gerätedaten mit BitLocker verwendet.</span><span class="sxs-lookup"><span data-stu-id="e50bd-161">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="e50bd-162">Weitere Informationen finden Sie unter [Übersicht über BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="e50bd-162">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM-Konsole](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="e50bd-164">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="e50bd-164">Figure 5.</span></span> <span data-ttu-id="e50bd-165">TPM-Konsole</span><span class="sxs-lookup"><span data-stu-id="e50bd-165">TPM console</span></span>*


## <span data-ttu-id="e50bd-166">UEFI-Menü: Geräte</span><span class="sxs-lookup"><span data-stu-id="e50bd-166">UEFI menu: Devices</span></span> 

<span data-ttu-id="e50bd-167">Auf der Seite "Geräte" können Sie bestimmte Geräte und Komponenten aktivieren oder deaktivieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="e50bd-167">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="e50bd-168">Docking- und USB-Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="e50bd-168">Docking and USB Ports</span></span> 

- <span data-ttu-id="e50bd-169">MicroSD oder SD-Kartensteckplatz</span><span class="sxs-lookup"><span data-stu-id="e50bd-169">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="e50bd-170">Rückwärtige Kamera</span><span class="sxs-lookup"><span data-stu-id="e50bd-170">Rear Camera</span></span> 

- <span data-ttu-id="e50bd-171">Frontkamera</span><span class="sxs-lookup"><span data-stu-id="e50bd-171">Front Camera</span></span> 

- <span data-ttu-id="e50bd-172">Infrarotkamera</span><span class="sxs-lookup"><span data-stu-id="e50bd-172">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="e50bd-173">WLAN und Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e50bd-173">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="e50bd-174">Integriertes Audio (Lautsprecher und Mikrofon)</span><span class="sxs-lookup"><span data-stu-id="e50bd-174">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="e50bd-175">Jedes Gerät ist mit einer Schieberegler-Schaltfläche aufgeführt, die Sie **in die Position ein (aktiviert** ) oder **aus** (deaktiviert) verschieben können, wie in Abbildung 6 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e50bd-175">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Aktivieren bzw. Deaktivieren bestimmter Geräte](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="e50bd-177">Abbildung6.</span><span class="sxs-lookup"><span data-stu-id="e50bd-177">Figure 6.</span></span> <span data-ttu-id="e50bd-178">Aktivieren bzw. Deaktivieren bestimmter Geräte</span><span class="sxs-lookup"><span data-stu-id="e50bd-178">Enable and disable specific devices</span></span>*

## <span data-ttu-id="e50bd-179">UEFI-Menü: Startkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e50bd-179">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="e50bd-180">Auf der Start Konfigurationsseite können Sie die Reihenfolge ihrer Startgeräte ändern sowie den Start der folgenden Geräte aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="e50bd-180">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="e50bd-181">Windows-Start-Manager</span><span class="sxs-lookup"><span data-stu-id="e50bd-181">Windows Boot Manager</span></span> 

- <span data-ttu-id="e50bd-182">USB-Speicher</span><span class="sxs-lookup"><span data-stu-id="e50bd-182">USB Storage</span></span> 

- <span data-ttu-id="e50bd-183">PXE-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="e50bd-183">PXE Network</span></span> 

- <span data-ttu-id="e50bd-184">Interner Speicher</span><span class="sxs-lookup"><span data-stu-id="e50bd-184">Internal Storage</span></span> 

<span data-ttu-id="e50bd-185">Sie können sofort mit einem bestimmten Gerät starten oder mit dem Touchscreen links neben dem Gerät in der Liste wischen.</span><span class="sxs-lookup"><span data-stu-id="e50bd-185">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="e50bd-186">Sie können auch sofort mit einem USB-Gerät oder USB-Ethernet-Adapter starten, wenn das Surface-Gerät durch gleichzeitiges Drücken der **Leiser**-Taste und der **Ein/Aus**-Taste ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e50bd-186">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="e50bd-187">Damit die angegebene Startreihenfolge wirksam wird, müssen Sie die Option **Alternative Startsequenz aktivieren** auf **ein**festlegen, wie in Abbildung 7 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e50bd-187">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Konfigurieren der Startreihenfolge für Ihr Surface-Gerät](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="e50bd-189">Abbildung7.</span><span class="sxs-lookup"><span data-stu-id="e50bd-189">Figure 7.</span></span> <span data-ttu-id="e50bd-190">Konfigurieren der Startreihenfolge für Ihr Surface-Gerät</span><span class="sxs-lookup"><span data-stu-id="e50bd-190">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="e50bd-191">Mit der Option **Enable IPv6 for PXE Network Boot** können Sie zudem die IPv6-Unterstützung für PXE aktivieren und deaktivieren, wenn Sie eine Windows-Bereitstellung mit PXE ausführen und der PXE-Server nur für IPv4 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e50bd-191">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="e50bd-192">UEFI-Menü: Verwaltung</span><span class="sxs-lookup"><span data-stu-id="e50bd-192">UEFI menu: Management</span></span>
<span data-ttu-id="e50bd-193">Auf der Seite "Verwaltung" können Sie die Verwendung der NULL-Touch-UEFI-Verwaltung und anderer Features auf geeigneten Geräten wie Surface pro 7, Surface pro X und Surface Laptop 3 verwalten.</span><span class="sxs-lookup"><span data-stu-id="e50bd-193">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="e50bd-194">Verwalten des Zugriffs auf die UEFI-Verwaltung und andere Features in ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Abbildung 8. Verwalten des Zugriffs auf die UEFI-Verwaltung und andere Features von Zero Touch*</span><span class="sxs-lookup"><span data-stu-id="e50bd-194">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="e50bd-195">Mit der UEFI-Verwaltung mit Zero Touch können Sie die UEFI-Einstellungen mithilfe eines Geräteprofils in InTune, der so genannten Device Firmware Configuration Interface (DFCI), remote verwalten.</span><span class="sxs-lookup"><span data-stu-id="e50bd-195">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="e50bd-196">Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit, berechtigte Geräte mit DFCI zu verwalten, auf **Ready**eingestellt.</span><span class="sxs-lookup"><span data-stu-id="e50bd-196">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="e50bd-197">Um DFCI zu verhindern, wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="e50bd-197">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e50bd-198">Die Seite "UEFI-Verwaltungseinstellungen" und die Verwendung von DFCI steht nur auf Surface pro 7, Surface pro X und Surface Laptop 3 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e50bd-198">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="e50bd-199">Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="e50bd-199">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="e50bd-200">UEFI-Menü: beenden</span><span class="sxs-lookup"><span data-stu-id="e50bd-200">UEFI menu: Exit</span></span> 

<span data-ttu-id="e50bd-201">Verwenden Sie die Schaltfläche **jetzt neu starten** auf der Seite **Beenden** , um die UEFI-Einstellungen zu beenden, wie in Abbildung 9 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="e50bd-201">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Surface UEFI beenden und Gerät neu starten](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="e50bd-203">Abbildung9.</span><span class="sxs-lookup"><span data-stu-id="e50bd-203">Figure 9.</span></span> <span data-ttu-id="e50bd-204">Klicken Sie auf „Jetzt neu starten“, um Surface UEFI zu beenden und das Gerät neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="e50bd-204">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="e50bd-205">Surface UEFI-Startbildschirme</span><span class="sxs-lookup"><span data-stu-id="e50bd-205">Surface UEFI boot screens</span></span>

<span data-ttu-id="e50bd-206">Wenn Sie die Firmware für das Surface-Gerät mit Windows Update oder per manueller Installation aktualisieren, werden die Updates nicht sofort auf dem Gerät installiert, sondern erst beim nächsten Neustart.</span><span class="sxs-lookup"><span data-stu-id="e50bd-206">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="e50bd-207">Weitere Informationen zum Updateprozess für die Surface-Firmware finden Sie unter [Verwalten von Treiber- und Firmwareupdates für Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="e50bd-207">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="e50bd-208">Der Fortschritt des Firmwareupdates wird in einem Bildschirm mit Statusanzeigen in verschiedenen Farben angezeigt, um die Firmware für die einzelnen Komponenten zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e50bd-208">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="e50bd-209">Die Statusanzeige jeder Komponente wird in den Abbildungen 9 bis 18 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e50bd-209">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Surface UEFI-Firmwareupdate mit blauer Statusanzeige](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="e50bd-211">Abbildung10.</span><span class="sxs-lookup"><span data-stu-id="e50bd-211">Figure 10.</span></span> <span data-ttu-id="e50bd-212">Surface-UEFI-Firmwareupdate mit einer blauen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="e50bd-212">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![System Embedded Controller-Firmware mit grüner Statusanzeige](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="e50bd-214">Abbildung11.</span><span class="sxs-lookup"><span data-stu-id="e50bd-214">Figure 11.</span></span> <span data-ttu-id="e50bd-215">System Embedded Controller-Firmwareupdate mit einer grünen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="e50bd-215">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![SAM-Controller-Firmwareupdate mit orangefarbener Statusanzeige](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="e50bd-217">Abbildung 12</span><span class="sxs-lookup"><span data-stu-id="e50bd-217">Figure 12.</span></span> <span data-ttu-id="e50bd-218">SAM-Controller-Firmwareupdate mit einer orangefarbenen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="e50bd-218">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Intel Management Engine-Firmware mit roter Statusanzeige](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="e50bd-220">Abbildung 13</span><span class="sxs-lookup"><span data-stu-id="e50bd-220">Figure 13.</span></span> <span data-ttu-id="e50bd-221">Intel Management Engine-Firmwareupdate mit einer roten Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="e50bd-221">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Surface Touch-Firmware mit grauer Statusanzeige](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="e50bd-223">Abbildung 14</span><span class="sxs-lookup"><span data-stu-id="e50bd-223">Figure 14.</span></span> <span data-ttu-id="e50bd-224">Surface Touch-Firmwareupdate mit einer grauen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="e50bd-224">The Surface touch firmware update displays a gray progress bar</span></span>*

![Surface Kip-Firmware mit hellgrün-Statusleiste](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="e50bd-226">Abbildung15.</span><span class="sxs-lookup"><span data-stu-id="e50bd-226">Figure 15.</span></span> <span data-ttu-id="e50bd-227">Das Firmware-Update für Surface Kip zeigt eine hell grüne Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="e50bd-227">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Surface ish-Firmware mit rosa Statusleiste](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="e50bd-229">Abbildung 16 die Firmware-Aktualisierung der Surface ish zeigt eine hell Rosa Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="e50bd-229">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Surface-Trackpad-Firmware mit grauer Statusleiste](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="e50bd-231">Abbildung17.</span><span class="sxs-lookup"><span data-stu-id="e50bd-231">Figure 17.</span></span> <span data-ttu-id="e50bd-232">Das Surface Trackpad-Firmware-Update zeigt eine rosafarbene Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="e50bd-232">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Surface TCON-Firmware mit hellgrauer Statusleiste](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="e50bd-234">Abbildung 18.</span><span class="sxs-lookup"><span data-stu-id="e50bd-234">Figure 18.</span></span> <span data-ttu-id="e50bd-235">Die Oberfläche-TCON-Firmware-Aktualisierung zeigt eine hell graue Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="e50bd-235">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Surface TPM-Firmware mit hell violetter Statusleiste](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="e50bd-237">Abbildung 19.</span><span class="sxs-lookup"><span data-stu-id="e50bd-237">Figure 19.</span></span> <span data-ttu-id="e50bd-238">Das TPM-Firmware-Update für Surface zeigt eine violette Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="e50bd-238">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="e50bd-239">Eine zusätzliche Warnmeldung, die besagt, dass der sichere Start deaktiviert ist, wird angezeigt, wie in Abbildung 19 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="e50bd-239">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" deaktiviert wurde.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="e50bd-241">Abbildung 20.</span><span class="sxs-lookup"><span data-stu-id="e50bd-241">Figure 20.</span></span> <span data-ttu-id="e50bd-242">Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" in den Surface UEFI-Einstellungen deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="e50bd-242">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="e50bd-243">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e50bd-243">Related topics</span></span>

- [<span data-ttu-id="e50bd-244">Intune-Verwaltung von Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e50bd-244">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="e50bd-245">Surface Enterprise Management-Modus</span><span class="sxs-lookup"><span data-stu-id="e50bd-245">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
