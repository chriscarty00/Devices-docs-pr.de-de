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
ms.date: 04/13/2021
ms.openlocfilehash: ea995eda277ecf235eedd92f3af6edb0b60ae68a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576505"
---
# <a name="manage-surface-uefi-settings"></a><span data-ttu-id="451dd-104">Verwalten der Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="451dd-104">Manage Surface UEFI settings</span></span>

 <span data-ttu-id="451dd-105">Surface -PC-Geräte sind für die Verwendung einer eindeutigen Unified Extensible Firmware Interface (UEFI) konzipiert, die von Microsoft speziell für diese Geräte entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="451dd-105">Surface PC devices are designed to utilize a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="451dd-106">Surface UEFI-Einstellungen bieten die Möglichkeit, integrierte Geräte und Komponenten zu aktivieren oder zu deaktivieren, UEFI-Einstellungen vor Änderung zu schützen und die Starteinstellungen für Surface-Geräte anzupassen.</span><span class="sxs-lookup"><span data-stu-id="451dd-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <a name="supported-products"></a><span data-ttu-id="451dd-107">Unterstützte Produkte</span><span class="sxs-lookup"><span data-stu-id="451dd-107">Supported products</span></span>

<span data-ttu-id="451dd-108">Die UEFI-Verwaltung wird wie folgt unterstützt:</span><span class="sxs-lookup"><span data-stu-id="451dd-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="451dd-109">Surface Pro 4, Surface Pro (5. Generation), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="451dd-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="451dd-110">Surface Laptop (1. Generation), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="451dd-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span></span>
- <span data-ttu-id="451dd-111">Surface Studio (1. Generation), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="451dd-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="451dd-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="451dd-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="451dd-113">Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)</span><span class="sxs-lookup"><span data-stu-id="451dd-113">Surface Go, Surface Go 2[<sup>1</sup>](#references)</span></span>

## <a name="support-for-cloud-based-management"></a><span data-ttu-id="451dd-114">Unterstützung für cloudbasierte Verwaltung</span><span class="sxs-lookup"><span data-stu-id="451dd-114">Support for cloud-based management</span></span>

<span data-ttu-id="451dd-115">Mit in Microsoft Intune integrierten Profilen für die Gerätefirmwarekonfigurationsschnittstelle (Device Firmware Configuration Interface, DFCI) (jetzt in der öffentlichen Vorschau verfügbar) erweitert die Surface UEFI-Verwaltung den modernen Verwaltungsstapel auf die UEFI-Hardwareebene.</span><span class="sxs-lookup"><span data-stu-id="451dd-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="451dd-116">DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Steuerung von Sicherheitseinstellungen, einschließlich Startoptionen und integrierten Peripheriegeräten, und legt die Grundlagen für erweiterte Sicherheitsszenarien in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="451dd-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="451dd-117">DFCI ist derzeit für Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 und Surface Pro X verfügbar.  Weitere Informationen finden Sie unter [Intune Management of Surface UEFI settings](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="451dd-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="open-surface-uefi-menu"></a><span data-ttu-id="451dd-118">Open Surface UEFI menu</span><span class="sxs-lookup"><span data-stu-id="451dd-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="451dd-119">So passen Sie die UEFI-Einstellungen während des Systemstarts an:</span><span class="sxs-lookup"><span data-stu-id="451dd-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="451dd-120">Fahren Sie Ihr Surface herunter, und warten Sie ca. 10 Sekunden, um sicherzustellen, dass es deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="451dd-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="451dd-121">Drücken und halten Sie **die Volume-up-Taste,** und drücken Sie gleichzeitig die Ein-/Aus-Taste. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="451dd-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="451dd-122">Wenn das Microsoft- oder Surface-Logo auf dem Bildschirm angezeigt wird, halten Sie die Schaltfläche **Volume-up** weiterhin gedrückt, bis der UEFI-Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="451dd-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <a name="uefi-pc-information-page"></a><span data-ttu-id="451dd-123">UEFI-PC-Informationsseite</span><span class="sxs-lookup"><span data-stu-id="451dd-123">UEFI PC information page</span></span>

<span data-ttu-id="451dd-124">Die Seite mit den PC-Informationen enthält detaillierte Informationen zu Ihrem Surface-Gerät:</span><span class="sxs-lookup"><span data-stu-id="451dd-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="451dd-125">**Modell** – Das Modell Ihres Surface-Geräts wird hier angezeigt, z. B. Surface Book 2 oder Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="451dd-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="451dd-126">Die genaue Konfiguration Ihres Geräts wird nicht angezeigt (z. B. Prozessor, Größe des Datenträgers oder Arbeitsspeicher).</span><span class="sxs-lookup"><span data-stu-id="451dd-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="451dd-127">**UUID** – Die UUID-Nummer gilt speziell für Ihr Gerät und wird verwendet, um das Gerät während der Bereitstellung oder Verwaltung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="451dd-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="451dd-128">**Seriennummer** – Diese Nummer wird zum Identifizieren dieses speziellen Surface-Geräts für die Bestandskennzeichnung und Supportszenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="451dd-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="451dd-129">**Bestandskennzeichen** – Das Bestandskennzeichen wird dem Surface-Gerät mit dem [Asset Tag Tool](https://docs.microsoft.com/surface/assettag) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="451dd-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="451dd-130">Außerdem finden Sie detaillierte Informationen zur Firmware des Surface-Geräts.</span><span class="sxs-lookup"><span data-stu-id="451dd-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="451dd-131">Surface-Geräte verfügen über mehrere interne Komponenten, die jeweils unterschiedliche Versionen der Firmware ausführen.</span><span class="sxs-lookup"><span data-stu-id="451dd-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="451dd-132">Die Firmwareversion der folgenden Geräte wird auf der Seite **PC-Informationen** angezeigt (siehe Abbildung 1):</span><span class="sxs-lookup"><span data-stu-id="451dd-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="451dd-133">System-UEFI</span><span class="sxs-lookup"><span data-stu-id="451dd-133">System UEFI</span></span> 

- <span data-ttu-id="451dd-134">SAM-Controller</span><span class="sxs-lookup"><span data-stu-id="451dd-134">SAM Controller</span></span> 

- <span data-ttu-id="451dd-135">Intel Management-Modul</span><span class="sxs-lookup"><span data-stu-id="451dd-135">Intel Management Engine</span></span> 

- <span data-ttu-id="451dd-136">System Embedded Controller</span><span class="sxs-lookup"><span data-stu-id="451dd-136">System Embedded Controller</span></span> 

- <span data-ttu-id="451dd-137">Touch-Firmware</span><span class="sxs-lookup"><span data-stu-id="451dd-137">Touch Firmware</span></span> 

![Systeminformationen und Firmwareversionsinformationen](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="451dd-139">Abbildung1.</span><span class="sxs-lookup"><span data-stu-id="451dd-139">Figure 1.</span></span> <span data-ttu-id="451dd-140">Systeminformationen und Firmwareversionsinformationen</span><span class="sxs-lookup"><span data-stu-id="451dd-140">System information and firmware version information</span></span>*

<span data-ttu-id="451dd-141">Aktuelle Informationen zur neuesten Firmware für Ihr Surface-Gerät finden Sie im [Surface-Updateverlauf](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) für Ihr Gerät.</span><span class="sxs-lookup"><span data-stu-id="451dd-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <a name="uefi-security-page"></a><span data-ttu-id="451dd-142">UEFI-Sicherheitsseite</span><span class="sxs-lookup"><span data-stu-id="451dd-142">UEFI Security page</span></span> 

![Konfigurieren von Surface UEFI-Sicherheitseinstellungen](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="451dd-144">Abbildung2.</span><span class="sxs-lookup"><span data-stu-id="451dd-144">Figure 2.</span></span> <span data-ttu-id="451dd-145">Konfigurieren von Surface UEFI-Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="451dd-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="451dd-146">Auf der Seite Sicherheit können Sie ein Kennwort zum Schutz von UEFI-Einstellungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="451dd-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="451dd-147">Dieses Kennwort muss eingegeben werden, wenn Sie das Surface-Gerät mit UEFI starten.</span><span class="sxs-lookup"><span data-stu-id="451dd-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="451dd-148">Das Kennwort kann die folgenden Zeichen enthalten (wie in Abbildung 3 dargestellt):</span><span class="sxs-lookup"><span data-stu-id="451dd-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="451dd-149">Großbuchstaben: A-Z</span><span class="sxs-lookup"><span data-stu-id="451dd-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="451dd-150">Kleinbuchstaben : a-z</span><span class="sxs-lookup"><span data-stu-id="451dd-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="451dd-151">Zahlen: 1-0</span><span class="sxs-lookup"><span data-stu-id="451dd-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="451dd-152">Sonderzeichen: !@#$%^&\*()?<>{} []-_=+|.,;:'"</span><span class="sxs-lookup"><span data-stu-id="451dd-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="451dd-153">Das Kennwort muss mindestens 6 Zeichen lang sein und Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="451dd-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="451dd-155">Abbildung3.</span><span class="sxs-lookup"><span data-stu-id="451dd-155">Figure 3.</span></span> <span data-ttu-id="451dd-156">Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="451dd-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="451dd-157">Auf der Seite Sicherheit können Sie außerdem die Konfiguration für den sicheren Start auf Ihrem Surface-Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="451dd-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="451dd-158">Die Technologie für den sicheren Start verhindert, dass nicht autorisierter Startcode auf Ihrem Surface Gerät gestartet werden kann, und sie schützt Sie vor Schadsoftwareinfektionen durch Bootkits und Rootkits.</span><span class="sxs-lookup"><span data-stu-id="451dd-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="451dd-159">Sie können den sicheren Start deaktivieren, damit Ihr Surface-Gerät Betriebssysteme von Drittanbietern oder startbare Medien starten kann.</span><span class="sxs-lookup"><span data-stu-id="451dd-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="451dd-160">Sie können den sicheren Start auch für die Verwendung mit Zertifikaten von Drittanbietern konfigurieren, wie in Abbildung 4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="451dd-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="451dd-161">Weitere Informationen finden Sie unter [Sicherer Start](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in der TechNet-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="451dd-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Konfigurieren des sicheren Starts](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="451dd-163">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="451dd-163">Figure 4.</span></span> <span data-ttu-id="451dd-164">Konfigurieren des sicheren Starts</span><span class="sxs-lookup"><span data-stu-id="451dd-164">Configure Secure Boot</span></span>*

<span data-ttu-id="451dd-165">Je nach Gerät können Sie auch sehen, ob Ihr TPM aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="451dd-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="451dd-166">Wenn die Einstellung **TPM** aktivieren nicht angezeigt wird, öffnen Sie tpm.msc in Windows, um den Status zu überprüfen, wie in Abbildung 5 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="451dd-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="451dd-167">Das TPM wird zur Authentifizierung der Verschlüsselung Ihrer Gerätedaten mit BitLocker verwendet.</span><span class="sxs-lookup"><span data-stu-id="451dd-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="451dd-168">Weitere Informationen finden Sie unter [BitLocker Übersicht](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="451dd-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM-Konsole](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="451dd-170">Abbildung5.</span><span class="sxs-lookup"><span data-stu-id="451dd-170">Figure 5.</span></span> <span data-ttu-id="451dd-171">TPM-Konsole</span><span class="sxs-lookup"><span data-stu-id="451dd-171">TPM console</span></span>*


## <a name="uefi-menu-devices"></a><span data-ttu-id="451dd-172">UEFI-Menü: Geräte</span><span class="sxs-lookup"><span data-stu-id="451dd-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="451dd-173">Auf der Seite Geräte können Sie bestimmte Geräte und Komponenten aktivieren oder deaktivieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="451dd-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="451dd-174">Docking- und USB-Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="451dd-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="451dd-175">MicroSD oder SD-Kartensteckplatz</span><span class="sxs-lookup"><span data-stu-id="451dd-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="451dd-176">Rückwärtige Kamera</span><span class="sxs-lookup"><span data-stu-id="451dd-176">Rear Camera</span></span> 

- <span data-ttu-id="451dd-177">Frontkamera</span><span class="sxs-lookup"><span data-stu-id="451dd-177">Front Camera</span></span> 

- <span data-ttu-id="451dd-178">Infrarotkamera</span><span class="sxs-lookup"><span data-stu-id="451dd-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="451dd-179">WLAN und Bluetooth</span><span class="sxs-lookup"><span data-stu-id="451dd-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="451dd-180">Integriertes Audio (Lautsprecher und Mikrofon)</span><span class="sxs-lookup"><span data-stu-id="451dd-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="451dd-181">Jedes Gerät wird mit einer Schiebereglerschaltfläche aufgeführt, die Sie zur Position **Ein** (aktiviert) oder **Aus** (deaktiviert) wechseln können, wie in Abbildung 6 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="451dd-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Aktivieren bzw. Deaktivieren bestimmter Geräte](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="451dd-183">Abbildung6.</span><span class="sxs-lookup"><span data-stu-id="451dd-183">Figure 6.</span></span> <span data-ttu-id="451dd-184">Aktivieren bzw. Deaktivieren bestimmter Geräte</span><span class="sxs-lookup"><span data-stu-id="451dd-184">Enable and disable specific devices</span></span>*

## <a name="uefi-menu-boot-configuration"></a><span data-ttu-id="451dd-185">UEFI-Menü: Startkonfiguration</span><span class="sxs-lookup"><span data-stu-id="451dd-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="451dd-186">Auf der Seite Startkonfiguration können Sie die Reihenfolge Ihrer Startgeräte ändern sowie den Start der folgenden Geräte aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="451dd-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="451dd-187">Windows-Start-Manager</span><span class="sxs-lookup"><span data-stu-id="451dd-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="451dd-188">USB-Speicher</span><span class="sxs-lookup"><span data-stu-id="451dd-188">USB Storage</span></span> 

- <span data-ttu-id="451dd-189">PXE-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="451dd-189">PXE Network</span></span> 

- <span data-ttu-id="451dd-190">Interner Speicher</span><span class="sxs-lookup"><span data-stu-id="451dd-190">Internal Storage</span></span> 

<span data-ttu-id="451dd-191">Sie können sofort mit einem bestimmten Gerät starten oder mit dem Touchscreen links neben dem Gerät in der Liste wischen.</span><span class="sxs-lookup"><span data-stu-id="451dd-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="451dd-192">Sie können auch sofort mit einem USB-Gerät oder USB-Ethernet-Adapter starten, wenn das Surface-Gerät durch gleichzeitiges Drücken der **Leiser**-Taste und der **Ein/Aus**-Taste ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="451dd-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="451dd-193">Damit die angegebene Startreihenfolge wirksam wird, müssen Sie die Option Alternative **Startsequenz** aktivieren auf **Ein**(siehe Abbildung 7) festlegen.</span><span class="sxs-lookup"><span data-stu-id="451dd-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Konfigurieren der Startreihenfolge für Ihr Surface-Gerät](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="451dd-195">Abbildung7.</span><span class="sxs-lookup"><span data-stu-id="451dd-195">Figure 7.</span></span> <span data-ttu-id="451dd-196">Konfigurieren der Startreihenfolge für Ihr Surface-Gerät</span><span class="sxs-lookup"><span data-stu-id="451dd-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="451dd-197">Mit der Option **Enable IPv6 for PXE Network Boot** können Sie zudem die IPv6-Unterstützung für PXE aktivieren und deaktivieren, wenn Sie eine Windows-Bereitstellung mit PXE ausführen und der PXE-Server nur für IPv4 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="451dd-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <a name="uefi-menu-management"></a><span data-ttu-id="451dd-198">UEFI-Menü: Verwaltung</span><span class="sxs-lookup"><span data-stu-id="451dd-198">UEFI menu: Management</span></span>
<span data-ttu-id="451dd-199">Auf der Seite Verwaltung können Sie die Verwendung von Zero Touch UEFI Management und anderen Features auf berechtigten Geräten wie Surface Pro 7, Surface Pro X und Surface Laptop 3 verwalten.</span><span class="sxs-lookup"><span data-stu-id="451dd-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="451dd-200">Verwalten des Zugriffs auf die Zero Touch UEFI-Verwaltung und andere Features ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Abbildung 8. Verwalten des Zugriffs auf die Zero Touch UEFI-Verwaltung und andere Features*</span><span class="sxs-lookup"><span data-stu-id="451dd-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="451dd-201">Mit zero Touch UEFI Management können Sie UEFI-Einstellungen remote mithilfe eines Geräteprofils in Intune verwalten, das als Device Firmware Configuration Interface (DFCI) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="451dd-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="451dd-202">Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit zum Verwalten berechtigter Geräte mit DFCI auf **Bereit festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="451dd-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="451dd-203">Wählen Sie **Abmelden**aus, um DFCI zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="451dd-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="451dd-204">Die Seite UEFI-Verwaltungseinstellungen und die Verwendung von DFCI sind derzeit für Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7 und Surface Pro X verfügbar. Weitere Informationen finden Sie unter [Intune-Verwaltung von Surface UEFI-Einstellungen](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="451dd-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="uefi-menu-exit"></a><span data-ttu-id="451dd-205">UEFI-Menü: Beenden</span><span class="sxs-lookup"><span data-stu-id="451dd-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="451dd-206">Verwenden Sie die **Schaltfläche Jetzt** neu starten auf der **Seite Beenden,** um die UEFI-Einstellungen zu beenden, wie in Abbildung 9 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="451dd-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Surface UEFI beenden und Gerät neu starten](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="451dd-208">Abbildung9.</span><span class="sxs-lookup"><span data-stu-id="451dd-208">Figure 9.</span></span> <span data-ttu-id="451dd-209">Klicken Sie auf „Jetzt neu starten“, um Surface UEFI zu beenden und das Gerät neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="451dd-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <a name="surface-uefi-boot-screens"></a><span data-ttu-id="451dd-210">Surface UEFI-Startbildschirme</span><span class="sxs-lookup"><span data-stu-id="451dd-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="451dd-211">Wenn Sie die Firmware für das Surface-Gerät mit Windows Update oder per manueller Installation aktualisieren, werden die Updates nicht sofort auf dem Gerät installiert, sondern erst beim nächsten Neustart.</span><span class="sxs-lookup"><span data-stu-id="451dd-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="451dd-212">Weitere Informationen zum Surface-Firmwareupdate finden Sie unter Verwalten und Bereitstellen [von Surface-Treiber- und Firmwareupdates.](manage-surface-driver-and-firmware-updates.md)</span><span class="sxs-lookup"><span data-stu-id="451dd-212">You can find out more about the Surface firmware update process in [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="451dd-213">Der Fortschritt des Firmwareupdates wird in einem Bildschirm mit Statusanzeigen in verschiedenen Farben angezeigt, um die Firmware für die einzelnen Komponenten zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="451dd-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="451dd-214">Die Statusleiste jeder Komponente wird in Abbildung 9 bis 18 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="451dd-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Surface UEFI-Firmwareupdate mit blauer Statusanzeige](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="451dd-216">Abbildung10.</span><span class="sxs-lookup"><span data-stu-id="451dd-216">Figure 10.</span></span> <span data-ttu-id="451dd-217">Surface-UEFI-Firmwareupdate mit einer blauen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="451dd-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![System Embedded Controller-Firmware mit grüner Statusanzeige](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="451dd-219">Abbildung11.</span><span class="sxs-lookup"><span data-stu-id="451dd-219">Figure 11.</span></span> <span data-ttu-id="451dd-220">System Embedded Controller-Firmwareupdate mit einer grünen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="451dd-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![SAM-Controller-Firmwareupdate mit orangefarbener Statusanzeige](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="451dd-222">Abbildung 12</span><span class="sxs-lookup"><span data-stu-id="451dd-222">Figure 12.</span></span> <span data-ttu-id="451dd-223">SAM-Controller-Firmwareupdate mit einer orangefarbenen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="451dd-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Intel Management Engine-Firmware mit roter Statusanzeige](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="451dd-225">Abbildung 13</span><span class="sxs-lookup"><span data-stu-id="451dd-225">Figure 13.</span></span> <span data-ttu-id="451dd-226">Intel Management Engine-Firmwareupdate mit einer roten Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="451dd-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Surface Touch-Firmware mit grauer Statusanzeige](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="451dd-228">Abbildung 14</span><span class="sxs-lookup"><span data-stu-id="451dd-228">Figure 14.</span></span> <span data-ttu-id="451dd-229">Surface Touch-Firmwareupdate mit einer grauen Statusanzeige</span><span class="sxs-lookup"><span data-stu-id="451dd-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![Surface -KIP-Firmware mit hellgrüner Statusleiste](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="451dd-231">Abbildung15.</span><span class="sxs-lookup"><span data-stu-id="451dd-231">Figure 15.</span></span> <span data-ttu-id="451dd-232">Das Surface KIP-Firmwareupdate zeigt eine hellgrüne Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="451dd-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Surface ISH-Firmware mit rosa Statusleiste](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="451dd-234">Abbildung 16 Das Surface ISH-Firmwareupdate zeigt eine hellrote Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="451dd-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Surface Trackpad-Firmware mit grauer Statusleiste](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="451dd-236">Abbildung17.</span><span class="sxs-lookup"><span data-stu-id="451dd-236">Figure 17.</span></span> <span data-ttu-id="451dd-237">Das Surface Trackpad-Firmwareupdate zeigt eine rosafarbene Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="451dd-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Surface TCON-Firmware mit hellgrauer Statusleiste](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="451dd-239">Abbildung 18.</span><span class="sxs-lookup"><span data-stu-id="451dd-239">Figure 18.</span></span> <span data-ttu-id="451dd-240">Das Surface TCON-Firmwareupdate zeigt eine hellgraue Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="451dd-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Surface -TPM-Firmware mit hellvioletter Statusleiste](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="451dd-242">Abbildung 19.</span><span class="sxs-lookup"><span data-stu-id="451dd-242">Figure 19.</span></span> <span data-ttu-id="451dd-243">Das Surface TPM-Firmwareupdate zeigt eine violette Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="451dd-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="451dd-244">Wie in Abbildung 19 dargestellt, wird eine zusätzliche Warnmeldung angezeigt, die angibt, dass der sichere Start deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="451dd-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" deaktiviert wurde.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="451dd-246">Abbildung 20.</span><span class="sxs-lookup"><span data-stu-id="451dd-246">Figure 20.</span></span> <span data-ttu-id="451dd-247">Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" in den Surface UEFI-Einstellungen deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="451dd-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <a name="references"></a><span data-ttu-id="451dd-248">Verweise</span><span class="sxs-lookup"><span data-stu-id="451dd-248">References</span></span>

1. <span data-ttu-id="451dd-249">Surface Go und Surface Go 2 verwenden UEFI eines Drittanbieters und unterstützen keine DFCI.</span><span class="sxs-lookup"><span data-stu-id="451dd-249">Surface Go and Surface Go 2 use a third-party UEFI and do not support DFCI.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="451dd-250">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="451dd-250">Related topics</span></span>

- [<span data-ttu-id="451dd-251">Intune-Verwaltung von Surface UEFI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="451dd-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="451dd-252">Surface Enterprise Management-Modus</span><span class="sxs-lookup"><span data-stu-id="451dd-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
