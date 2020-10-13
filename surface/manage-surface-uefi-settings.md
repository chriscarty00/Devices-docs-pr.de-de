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
ms.reviewer: hachidan
manager: laurawi
ms.date: 10/12/2020
ms.openlocfilehash: 218f98b23adcb7bae2af92655d85144c6e5665e6
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114723"
---
# <span data-ttu-id="44d6d-104">Verwalten der Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="44d6d-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="44d6d-105">Alle aktuellen und zukünftigen Generationen von Surface-Geräten verwenden eine einzigartige Unified Extensible Firmware Interface (UEFI), die von Microsoft speziell für diese Geräte entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="44d6d-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="44d6d-106">Oberflächen UEFI-Einstellungen bieten die Möglichkeit, integrierte Geräte und Komponenten zu aktivieren oder zu deaktivieren, die UEFI-Einstellungen vor Änderungen zu schützen und die Start Einstellungen des Surface-Geräts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="44d6d-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="44d6d-107">Unterstützte Produkte</span><span class="sxs-lookup"><span data-stu-id="44d6d-107">Supported products</span></span>

<span data-ttu-id="44d6d-108">Die UEFI-Verwaltung wird auf der folgenden Grundlage unterstützt:</span><span class="sxs-lookup"><span data-stu-id="44d6d-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="44d6d-109">Surface pro 4, Surface pro (5. Generation), Surface pro 6, Surface pro 7, Surface pro X</span><span class="sxs-lookup"><span data-stu-id="44d6d-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro X</span></span>
- <span data-ttu-id="44d6d-110">Surface Laptop (1st Generation), Surface Laptop 2, Surface Laptop 3, Surface Laptop go</span><span class="sxs-lookup"><span data-stu-id="44d6d-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="44d6d-111">Surface Studio (1st Generation), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="44d6d-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="44d6d-112">DGM-Buch, DGM-Buch 2, DGM-Buch 3</span><span class="sxs-lookup"><span data-stu-id="44d6d-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="44d6d-113">Surface go, Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="44d6d-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="44d6d-114">Unterstützung für Cloud-basiertes Management</span><span class="sxs-lookup"><span data-stu-id="44d6d-114">Support for cloud-based management</span></span>

<span data-ttu-id="44d6d-115">Mit DFCI-Profilen (Device Firmware Configuration Interface), die in Microsoft InTune integriert sind (jetzt in Public Preview verfügbar), erweitert die Oberfläche-UEFI-Verwaltung den modernen Verwaltungs Stapel auf die UEFI-Hardwareebene.</span><span class="sxs-lookup"><span data-stu-id="44d6d-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="44d6d-116">DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Kontrolle über Sicherheitseinstellungen, einschließlich Startoptionen und integrierte Peripheriegeräte, und legt die Grundlagen für fortschrittliche Sicherheitsszenarien in der Zukunft fest.</span><span class="sxs-lookup"><span data-stu-id="44d6d-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="44d6d-117">DFCI steht derzeit für Surface pro 7, Surface pro X und Surface Laptop 3 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="44d6d-117">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="44d6d-118">Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="44d6d-118">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="44d6d-119">Menü "DGM-UEFI öffnen"</span><span class="sxs-lookup"><span data-stu-id="44d6d-119">Open Surface UEFI menu</span></span>

<span data-ttu-id="44d6d-120">So passen Sie die UEFI-Einstellungen während des Systemstarts an:</span><span class="sxs-lookup"><span data-stu-id="44d6d-120">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="44d6d-121">Fahren Sie die Oberfläche herunter, und warten Sie etwa 10 Sekunden, um sicherzustellen, dass Sie deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="44d6d-121">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="44d6d-122">Halten Sie die **Lautstärke** Taste gedrückt, und drücken Sie gleichzeitig die **Power-Taste** , und lassen Sie sie los.</span><span class="sxs-lookup"><span data-stu-id="44d6d-122">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="44d6d-123">Wenn das Microsoft-oder Surface-Logo auf dem Bildschirm angezeigt wird, halten Sie die **Lautstärke** Taste gedrückt, bis der UEFI-Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="44d6d-123">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="44d6d-124">UEFI-PC-Informationsseite</span><span class="sxs-lookup"><span data-stu-id="44d6d-124">UEFI PC information page</span></span>

<span data-ttu-id="44d6d-125">Auf der Seite PC-Informationen finden Sie detaillierte Informationen zu Ihrem Surface-Gerät:</span><span class="sxs-lookup"><span data-stu-id="44d6d-125">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="44d6d-126">**Modell** – das Modell Ihres Surface-Geräts wird hier angezeigt, beispielsweise Surface Book 2 oder Surface pro 7.</span><span class="sxs-lookup"><span data-stu-id="44d6d-126">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="44d6d-127">Die genaue Konfiguration Ihres Geräts wird nicht angezeigt (z. B. Prozessor, Größe des Datenträgers oder Arbeitsspeicher).</span><span class="sxs-lookup"><span data-stu-id="44d6d-127">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="44d6d-128">**UUID** – Die UUID-Nummer gilt speziell für Ihr Gerät und wird verwendet, um das Gerät während der Bereitstellung oder Verwaltung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="44d6d-128">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="44d6d-129">**Seriennummer** – Diese Nummer wird zum Identifizieren dieses speziellen Surface-Geräts für die Bestandskennzeichnung und Supportszenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="44d6d-129">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="44d6d-130">**Bestandskennzeichen** – Das Bestandskennzeichen wird dem Surface-Gerät mit dem [Asset Tag Tool](https://docs.microsoft.com/surface/assettag) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="44d6d-130">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="44d6d-131">Außerdem finden Sie detaillierte Informationen zur Firmware des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="44d6d-131">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="44d6d-132">Surface-Geräte verfügen über mehrere interne Komponenten, die jeweils unterschiedliche Versionen der Firmware ausführen.</span><span class="sxs-lookup"><span data-stu-id="44d6d-132">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="44d6d-133">Die Firmwareversion der folgenden Geräte wird auf der Seite **PC-Informationen** angezeigt (siehe Abbildung 1):</span><span class="sxs-lookup"><span data-stu-id="44d6d-133">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="44d6d-134">System-UEFI</span><span class="sxs-lookup"><span data-stu-id="44d6d-134">System UEFI</span></span> 

- <span data-ttu-id="44d6d-135">SAM-Controller</span><span class="sxs-lookup"><span data-stu-id="44d6d-135">SAM Controller</span></span> 

- <span data-ttu-id="44d6d-136">Intel Management-Modul</span><span class="sxs-lookup"><span data-stu-id="44d6d-136">Intel Management Engine</span></span> 

- <span data-ttu-id="44d6d-137">System Embedded Controller</span><span class="sxs-lookup"><span data-stu-id="44d6d-137">System Embedded Controller</span></span> 

- <span data-ttu-id="44d6d-138">Touch-Firmware</span><span class="sxs-lookup"><span data-stu-id="44d6d-138">Touch Firmware</span></span> 

![Systeminformationen und Firmwareversionsinformationen](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="44d6d-140">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="44d6d-140">Figure 1.</span></span> <span data-ttu-id="44d6d-141">Systeminformationen und Firmwareversionsinformationen</span><span class="sxs-lookup"><span data-stu-id="44d6d-141">System information and firmware version information</span></span>*

<span data-ttu-id="44d6d-142">Aktuelle Informationen zur neuesten Firmware für Ihr Surface-Gerät finden Sie im [Surface-Updateverlauf](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) für Ihr Gerät.</span><span class="sxs-lookup"><span data-stu-id="44d6d-142">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="44d6d-143">UEFI-Sicherheitsseite</span><span class="sxs-lookup"><span data-stu-id="44d6d-143">UEFI Security page</span></span> 

![Konfigurieren von Surface UEFI-Sicherheitseinstellungen](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="44d6d-145">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="44d6d-145">Figure 2.</span></span> <span data-ttu-id="44d6d-146">Konfigurieren von Surface UEFI-Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="44d6d-146">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="44d6d-147">Auf der Seite "Sicherheit" können Sie ein Kennwort zum Schützen von UEFI-Einstellungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="44d6d-147">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="44d6d-148">Dieses Kennwort muss eingegeben werden, wenn Sie das Surface-Gerät mit UEFI starten.</span><span class="sxs-lookup"><span data-stu-id="44d6d-148">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="44d6d-149">Das Kennwort kann die folgenden Zeichen enthalten (siehe Abbildung 3):</span><span class="sxs-lookup"><span data-stu-id="44d6d-149">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="44d6d-150">Großbuchstaben: A-Z</span><span class="sxs-lookup"><span data-stu-id="44d6d-150">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="44d6d-151">Kleinbuchstaben : a-z</span><span class="sxs-lookup"><span data-stu-id="44d6d-151">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="44d6d-152">Zahlen: 1-0</span><span class="sxs-lookup"><span data-stu-id="44d6d-152">Numbers: 1-0</span></span> 

- <span data-ttu-id="44d6d-153">Sonderzeichen:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: "'"</span><span class="sxs-lookup"><span data-stu-id="44d6d-153">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="44d6d-154">Das Kennwort muss mindestens 6 Zeichen lang sein und Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="44d6d-154">The password must be at least 6 characters and is case sensitive.</span></span> 

![Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="44d6d-156">Abbildung3.</span><span class="sxs-lookup"><span data-stu-id="44d6d-156">Figure 3.</span></span> <span data-ttu-id="44d6d-157">Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="44d6d-157">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="44d6d-158">Auf der Seite Sicherheit können Sie außerdem die Konfiguration für den sicheren Start auf Ihrem Surface-Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="44d6d-158">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="44d6d-159">Die Technologie für den sicheren Start verhindert, dass nicht autorisierter Startcode auf Ihrem Surface Gerät gestartet werden kann, und sie schützt Sie vor Schadsoftwareinfektionen durch Bootkits und Rootkits.</span><span class="sxs-lookup"><span data-stu-id="44d6d-159">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="44d6d-160">Sie können den sicheren Start deaktivieren, damit Ihr Surface-Gerät Betriebssysteme von Drittanbietern oder startbare Medien starten kann.</span><span class="sxs-lookup"><span data-stu-id="44d6d-160">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="44d6d-161">Sie können auch den sicheren Start für die Verwendung von Zertifikaten von Drittanbietern konfigurieren, wie in Abbildung 4 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="44d6d-161">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="44d6d-162">Weitere Informationen finden Sie unter [Sicherer Start](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in der TechNet-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="44d6d-162">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Konfigurieren des sicheren Starts](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="44d6d-164">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="44d6d-164">Figure 4.</span></span> <span data-ttu-id="44d6d-165">Konfigurieren des sicheren Starts</span><span class="sxs-lookup"><span data-stu-id="44d6d-165">Configure Secure Boot</span></span>*

<span data-ttu-id="44d6d-166">Je nach Gerät können Sie möglicherweise auch feststellen, ob Ihr TPM aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="44d6d-166">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="44d6d-167">Wenn die Einstellung **TPM aktivieren**  nicht angezeigt wird, öffnen Sie TPM. msc in Windows, um den Status zu überprüfen, wie in Abbildung 5 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="44d6d-167">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="44d6d-168">Das TPM wird zur Authentifizierung der Verschlüsselung Ihrer Gerätedaten mit BitLocker verwendet.</span><span class="sxs-lookup"><span data-stu-id="44d6d-168">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="44d6d-169">Weitere Informationen finden Sie unter [Übersicht über BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="44d6d-169">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM-Konsole](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="44d6d-171">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="44d6d-171">Figure 5.</span></span> <span data-ttu-id="44d6d-172">TPM-Konsole</span><span class="sxs-lookup"><span data-stu-id="44d6d-172">TPM console</span></span>*


## <span data-ttu-id="44d6d-173">UEFI-Menü: Geräte</span><span class="sxs-lookup"><span data-stu-id="44d6d-173">UEFI menu: Devices</span></span> 

<span data-ttu-id="44d6d-174">Auf der Seite "Geräte" können Sie bestimmte Geräte und Komponenten aktivieren oder deaktivieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="44d6d-174">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="44d6d-175">Docking- und USB-Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="44d6d-175">Docking and USB Ports</span></span> 

- <span data-ttu-id="44d6d-176">MicroSD oder SD-Kartensteckplatz</span><span class="sxs-lookup"><span data-stu-id="44d6d-176">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="44d6d-177">Rückwärtige Kamera</span><span class="sxs-lookup"><span data-stu-id="44d6d-177">Rear Camera</span></span> 

- <span data-ttu-id="44d6d-178">Frontkamera</span><span class="sxs-lookup"><span data-stu-id="44d6d-178">Front Camera</span></span> 

- <span data-ttu-id="44d6d-179">Infrarotkamera</span><span class="sxs-lookup"><span data-stu-id="44d6d-179">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="44d6d-180">WLAN und Bluetooth</span><span class="sxs-lookup"><span data-stu-id="44d6d-180">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="44d6d-181">Integriertes Audio (Lautsprecher und Mikrofon)</span><span class="sxs-lookup"><span data-stu-id="44d6d-181">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="44d6d-182">Jedes Gerät ist mit einer Schieberegler-Schaltfläche aufgeführt, die Sie **in die Position ein (aktiviert** ) oder **aus** (deaktiviert) verschieben können, wie in Abbildung 6 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="44d6d-182">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Aktivieren bzw. Deaktivieren bestimmter Geräte](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="44d6d-184">Abbildung6.</span><span class="sxs-lookup"><span data-stu-id="44d6d-184">Figure 6.</span></span> <span data-ttu-id="44d6d-185">Aktivieren bzw. Deaktivieren bestimmter Geräte</span><span class="sxs-lookup"><span data-stu-id="44d6d-185">Enable and disable specific devices</span></span>*

## <span data-ttu-id="44d6d-186">UEFI-Menü: Startkonfiguration</span><span class="sxs-lookup"><span data-stu-id="44d6d-186">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="44d6d-187">Auf der Start Konfigurationsseite können Sie die Reihenfolge ihrer Startgeräte ändern sowie den Start der folgenden Geräte aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="44d6d-187">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="44d6d-188">Windows-Start-Manager</span><span class="sxs-lookup"><span data-stu-id="44d6d-188">Windows Boot Manager</span></span> 

- <span data-ttu-id="44d6d-189">USB-Speicher</span><span class="sxs-lookup"><span data-stu-id="44d6d-189">USB Storage</span></span> 

- <span data-ttu-id="44d6d-190">PXE-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="44d6d-190">PXE Network</span></span> 

- <span data-ttu-id="44d6d-191">Interner Speicher</span><span class="sxs-lookup"><span data-stu-id="44d6d-191">Internal Storage</span></span> 

<span data-ttu-id="44d6d-192">Sie können sofort mit einem bestimmten Gerät starten oder mit dem Touchscreen links neben dem Gerät in der Liste wischen.</span><span class="sxs-lookup"><span data-stu-id="44d6d-192">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="44d6d-193">Sie können auch sofort mit einem USB-Gerät oder USB-Ethernet-Adapter starten, wenn das Surface-Gerät durch gleichzeitiges Drücken der **Leiser**-Taste und der **Ein/Aus**-Taste ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="44d6d-193">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="44d6d-194">Damit die angegebene Startreihenfolge wirksam wird, müssen Sie die Option **Alternative Startsequenz aktivieren** auf **ein**festlegen, wie in Abbildung 7 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="44d6d-194">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Konfigurieren der Startreihenfolge für Ihr Surface-Gerät](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="44d6d-196">Abbildung7.</span><span class="sxs-lookup"><span data-stu-id="44d6d-196">Figure 7.</span></span> <span data-ttu-id="44d6d-197">Konfigurieren der Startreihenfolge für Ihr Surface-Gerät</span><span class="sxs-lookup"><span data-stu-id="44d6d-197">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="44d6d-198">Mit der Option **Enable IPv6 for PXE Network Boot** können Sie zudem die IPv6-Unterstützung für PXE aktivieren und deaktivieren, wenn Sie eine Windows-Bereitstellung mit PXE ausführen und der PXE-Server nur für IPv4 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="44d6d-198">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="44d6d-199">UEFI-Menü: Verwaltung</span><span class="sxs-lookup"><span data-stu-id="44d6d-199">UEFI menu: Management</span></span>
<span data-ttu-id="44d6d-200">Auf der Seite "Verwaltung" können Sie die Verwendung der NULL-Touch-UEFI-Verwaltung und anderer Features auf geeigneten Geräten wie Surface pro 7, Surface pro X und Surface Laptop 3 verwalten.</span><span class="sxs-lookup"><span data-stu-id="44d6d-200">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="44d6d-201">Verwalten des Zugriffs auf die UEFI-Verwaltung und andere Features in ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Abbildung 8. Verwalten des Zugriffs auf die UEFI-Verwaltung und andere Features von Zero Touch*</span><span class="sxs-lookup"><span data-stu-id="44d6d-201">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="44d6d-202">Mit der UEFI-Verwaltung mit Zero Touch können Sie die UEFI-Einstellungen mithilfe eines Geräteprofils in InTune, der so genannten Device Firmware Configuration Interface (DFCI), remote verwalten.</span><span class="sxs-lookup"><span data-stu-id="44d6d-202">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="44d6d-203">Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit, berechtigte Geräte mit DFCI zu verwalten, auf **Ready**eingestellt.</span><span class="sxs-lookup"><span data-stu-id="44d6d-203">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="44d6d-204">Um DFCI zu verhindern, wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="44d6d-204">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="44d6d-205">Die Seite "UEFI-Verwaltungseinstellungen" und die Verwendung von DFCI steht nur auf Surface pro 7, Surface pro X und Surface Laptop 3 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="44d6d-205">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="44d6d-206">Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="44d6d-206">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="44d6d-207">UEFI-Menü: beenden</span><span class="sxs-lookup"><span data-stu-id="44d6d-207">UEFI menu: Exit</span></span> 

<span data-ttu-id="44d6d-208">Verwenden Sie die Schaltfläche **jetzt neu starten** auf der Seite **Beenden** , um die UEFI-Einstellungen zu beenden, wie in Abbildung 9 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="44d6d-208">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Surface UEFI beenden und Gerät neu starten](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="44d6d-210">Abbildung9.</span><span class="sxs-lookup"><span data-stu-id="44d6d-210">Figure 9.</span></span> <span data-ttu-id="44d6d-211">Klicken Sie auf „Jetzt neu starten“, um Surface UEFI zu beenden und das Gerät neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="44d6d-211">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="44d6d-212">Surface UEFI-Startbildschirme</span><span class="sxs-lookup"><span data-stu-id="44d6d-212">Surface UEFI boot screens</span></span>

<span data-ttu-id="44d6d-213">Wenn Sie die Firmware für das Surface-Gerät mit Windows Update oder per manueller Installation aktualisieren, werden die Updates nicht sofort auf dem Gerät installiert, sondern erst beim nächsten Neustart.</span><span class="sxs-lookup"><span data-stu-id="44d6d-213">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="44d6d-214">Weitere Informationen zum Updateprozess für die Surface-Firmware finden Sie unter [Verwalten von Treiber- und Firmwareupdates für Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="44d6d-214">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="44d6d-215">Der Fortschritt des Firmwareupdates wird in einem Bildschirm mit Statusanzeigen in verschiedenen Farben angezeigt, um die Firmware für die einzelnen Komponenten zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="44d6d-215">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="44d6d-216">Die Statusanzeige jeder Komponente wird in den Abbildungen 9 bis 18 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44d6d-216">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Surface UEFI-Firmwareupdate mit blauer Statusanzeige](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="44d6d-218">Abbildung10.</span><span class="sxs-lookup"><span data-stu-id="44d6d-218">Figure 10.</span></span> <span data-ttu-id="44d6d-219">Surface-UEFI-Firmwareupdate mit einer blauen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="44d6d-219">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![System Embedded Controller-Firmware mit grüner Statusanzeige](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="44d6d-221">Abbildung11.</span><span class="sxs-lookup"><span data-stu-id="44d6d-221">Figure 11.</span></span> <span data-ttu-id="44d6d-222">System Embedded Controller-Firmwareupdate mit einer grünen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="44d6d-222">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![SAM-Controller-Firmwareupdate mit orangefarbener Statusanzeige](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="44d6d-224">Abbildung 12</span><span class="sxs-lookup"><span data-stu-id="44d6d-224">Figure 12.</span></span> <span data-ttu-id="44d6d-225">SAM-Controller-Firmwareupdate mit einer orangefarbenen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="44d6d-225">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Intel Management Engine-Firmware mit roter Statusanzeige](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="44d6d-227">Abbildung 13</span><span class="sxs-lookup"><span data-stu-id="44d6d-227">Figure 13.</span></span> <span data-ttu-id="44d6d-228">Intel Management Engine-Firmwareupdate mit einer roten Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="44d6d-228">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Surface Touch-Firmware mit grauer Statusanzeige](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="44d6d-230">Abbildung 14</span><span class="sxs-lookup"><span data-stu-id="44d6d-230">Figure 14.</span></span> <span data-ttu-id="44d6d-231">Surface Touch-Firmwareupdate mit einer grauen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="44d6d-231">The Surface touch firmware update displays a gray progress bar</span></span>*

![Surface Kip-Firmware mit hellgrün-Statusleiste](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="44d6d-233">Abbildung15.</span><span class="sxs-lookup"><span data-stu-id="44d6d-233">Figure 15.</span></span> <span data-ttu-id="44d6d-234">Das Firmware-Update für Surface Kip zeigt eine hell grüne Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="44d6d-234">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Surface ish-Firmware mit rosa Statusleiste](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="44d6d-236">Abbildung 16 die Firmware-Aktualisierung der Surface ish zeigt eine hell Rosa Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="44d6d-236">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Surface-Trackpad-Firmware mit grauer Statusleiste](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="44d6d-238">Abbildung17.</span><span class="sxs-lookup"><span data-stu-id="44d6d-238">Figure 17.</span></span> <span data-ttu-id="44d6d-239">Das Surface Trackpad-Firmware-Update zeigt eine rosafarbene Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="44d6d-239">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Surface TCON-Firmware mit hellgrauer Statusleiste](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="44d6d-241">Abbildung 18.</span><span class="sxs-lookup"><span data-stu-id="44d6d-241">Figure 18.</span></span> <span data-ttu-id="44d6d-242">Die Oberfläche-TCON-Firmware-Aktualisierung zeigt eine hell graue Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="44d6d-242">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Surface TPM-Firmware mit hell violetter Statusleiste](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="44d6d-244">Abbildung 19.</span><span class="sxs-lookup"><span data-stu-id="44d6d-244">Figure 19.</span></span> <span data-ttu-id="44d6d-245">Das TPM-Firmware-Update für Surface zeigt eine violette Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="44d6d-245">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="44d6d-246">Eine zusätzliche Warnmeldung, die besagt, dass der sichere Start deaktiviert ist, wird angezeigt, wie in Abbildung 19 zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="44d6d-246">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" deaktiviert wurde.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="44d6d-248">Abbildung 20.</span><span class="sxs-lookup"><span data-stu-id="44d6d-248">Figure 20.</span></span> <span data-ttu-id="44d6d-249">Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" in den Surface UEFI-Einstellungen deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="44d6d-249">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="44d6d-250">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="44d6d-250">Related topics</span></span>

- [<span data-ttu-id="44d6d-251">Intune-Verwaltung von Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="44d6d-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="44d6d-252">Surface Enterprise Management-Modus</span><span class="sxs-lookup"><span data-stu-id="44d6d-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
