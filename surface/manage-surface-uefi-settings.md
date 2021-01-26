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
ms.date: 01/25/2021
ms.openlocfilehash: af9eac171dea5d29ce9776766a2c5842bea9eb8c
ms.sourcegitcommit: 1b12ea363785697ddc705b0a0cc7bb35cad6b327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "11300696"
---
# Verwalten der Surface UEFI-Einstellungen

 Surface -PC-Geräte sind für die Verwendung einer eindeutigen Unified Extensible Firmware Interface (UEFI) ausgelegt, die von Microsoft speziell für diese Geräte entwickelt wurde. Surface -UEFI-Einstellungen bieten die Möglichkeit, integrierte Geräte und Komponenten zu aktivieren oder zu deaktivieren, die Änderung von UEFI-Einstellungen zu schützen und die Starteinstellungen des Surface-Geräts anzupassen. 

## Unterstützte Produkte

Die Verwaltung der UEFI wird in folgenden Themen unterstützt: 

- Surface Pro 4, Surface Pro (5. Generation), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1. Generation), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go
- Surface Studio (1. Generation), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)

## Unterstützung für cloudbasierte Verwaltung

Mit in Microsoft Intune integrierten (jetzt in der öffentlichen Vorschau verfügbaren) Device Firmware Configuration Interface (DFCI)-Profilen erweitert die Surface -UEFI-Verwaltung den modernen Verwaltungsstapel bis auf die UEFI-Hardwareebene. DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, ermöglicht die Steuerung von Sicherheitseinstellungen, einschließlich Startoptionen und integrierter Peripheriegeräte, und bildet die Grundlage für erweiterte Sicherheitsszenarien in der Zukunft. DFCI ist derzeit für Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 und Surface Pro X verfügbar.  Weitere Informationen finden Sie unter [Intune-Verwaltung von Surface UEFI-Einstellungen.](surface-manage-dfci-guide.md)

## Surface -UEFI-Menü öffnen

So passen Sie die UEFI-Einstellungen während des Systemstarts an:

1. Fahren Sie das Surface herunter, und warten Sie etwa 10 Sekunden, um sicherzustellen, dass es deaktiviert ist.
2. Halten Sie die **Ein-/Aus-Taste** gedrückt, und drücken Sie gleichzeitig die **Ein-/Aus-Taste.**
3. Wenn das Microsoft- oder **Surface-Logo** auf dem Bildschirm angezeigt wird, halten Sie die Schaltfläche "Lautstärke" gedrückt, bis der Bildschirm "UEFI" angezeigt wird.

## UEFI-PC-Informationsseite

Die Seite mit den PC-Informationen enthält ausführliche Informationen zu Ihrem Surface-Gerät: 

- **Modell** – Das Modell Ihres Surface-Geräts wird hier angezeigt, z. B. Surface Book 2 oder Surface Pro 7. Die genaue Konfiguration Ihres Geräts wird nicht angezeigt (z. B. Prozessor, Größe des Datenträgers oder Arbeitsspeicher). 
- **UUID** – Die UUID-Nummer gilt speziell für Ihr Gerät und wird verwendet, um das Gerät während der Bereitstellung oder Verwaltung zu identifizieren. 

- **Seriennummer** – Diese Nummer wird zum Identifizieren dieses speziellen Surface-Geräts für die Bestandskennzeichnung und Supportszenarien verwendet.
- **Bestandskennzeichen** – Das Bestandskennzeichen wird dem Surface-Gerät mit dem [Asset Tag Tool](https://docs.microsoft.com/surface/assettag) zugewiesen. 

Außerdem finden Sie detaillierte Informationen zur Firmware des Surface-Geräts. Surface-Geräte verfügen über mehrere interne Komponenten, die jeweils unterschiedliche Versionen der Firmware ausführen. Die Firmwareversion der folgenden Geräte wird auf der Seite **PC-Informationen** angezeigt (siehe Abbildung 1): 

- System-UEFI 

- SAM-Controller 

- Intel Management-Modul 

- System Embedded Controller 

- Touch-Firmware 

![Systeminformationen und Firmwareversionsinformationen](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*Abbildung1. Systeminformationen und Firmwareversionsinformationen*

Aktuelle Informationen zur neuesten Firmware für Ihr Surface-Gerät finden Sie im [Surface-Updateverlauf](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) für Ihr Gerät. 

## Seite "UEFI-Sicherheit" 

![Konfigurieren von Surface UEFI-Sicherheitseinstellungen](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Abbildung2. Konfigurieren von Surface UEFI-Sicherheitseinstellungen*

Auf der Seite "Sicherheit" können Sie ein Kennwort zum Schutz von UEFI-Einstellungen festlegen. Dieses Kennwort muss eingegeben werden, wenn Sie das Surface-Gerät mit UEFI starten. Das Kennwort kann die folgenden Zeichen enthalten (siehe Abbildung 3): 

- Großbuchstaben: A-Z 

- Kleinbuchstaben : a-z 

- Zahlen: 1-0 

- Sonderzeichen: !@#$%^&*()?<>{} []-_=+|.,;:''" 

Das Kennwort muss mindestens 6 Zeichen lang sein und Groß-/Kleinschreibung beachten. 

![Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Abbildung3. Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen*

Auf der Seite Sicherheit können Sie außerdem die Konfiguration für den sicheren Start auf Ihrem Surface-Gerät ändern. Die Technologie für den sicheren Start verhindert, dass nicht autorisierter Startcode auf Ihrem Surface Gerät gestartet werden kann, und sie schützt Sie vor Schadsoftwareinfektionen durch Bootkits und Rootkits. Sie können den sicheren Start deaktivieren, damit Ihr Surface-Gerät Betriebssysteme von Drittanbietern oder startbare Medien starten kann. Sie können den sicheren Start auch für die Verwendung mit Zertifikaten von Drittanbietern konfigurieren, wie in Abbildung 4 dargestellt. Weitere Informationen finden Sie unter [Sicherer Start](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in der TechNet-Bibliothek.

![Konfigurieren des sicheren Starts](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Abbildung 4. Konfigurieren des sicheren Starts*

Je nach Gerät können Sie auch sehen, ob Ihr TPM aktiviert oder deaktiviert ist. If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5. Das TPM wird zur Authentifizierung der Verschlüsselung Ihrer Gerätedaten mit BitLocker verwendet. Weitere Informationen finden Sie in der [BitLocker-Übersicht.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) 

![TPM Console](images/manage-surface-uefi-fig5-a.png "TPM console")

*Abbildung5. TPM Console*


## UEFI-Menü: Geräte 

Auf der Seite "Geräte" können Sie bestimmte Geräte und Komponenten aktivieren oder deaktivieren, einschließlich:

- Docking- und USB-Anschlüsse 

- MicroSD oder SD-Kartensteckplatz 

- Rückwärtige Kamera 

- Frontkamera 

- Infrarotkamera 

- WLAN und Bluetooth 

- Integriertes Audio (Lautsprecher und Mikrofon) 

Jedes Gerät wird mit einer Schiebereglerschaltfläche **** aufgelistet, mit der Sie zur Position "Ein" (aktiviert) oder "Aus" **(deaktiviert)** wechseln können, wie in Abbildung 6 dargestellt. 

![Aktivieren bzw. Deaktivieren bestimmter Geräte](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Abbildung6. Aktivieren bzw. Deaktivieren bestimmter Geräte*

## UEFI-Menü: Startkonfiguration 

Auf der Seite "Startkonfiguration" können Sie die Reihenfolge Ihrer Startgeräte ändern sowie den Start der folgenden Geräte aktivieren oder deaktivieren: 

- Windows-Start-Manager 

- USB-Speicher 

- PXE-Netzwerk 

- Interner Speicher 

Sie können sofort mit einem bestimmten Gerät starten oder mit dem Touchscreen links neben dem Gerät in der Liste wischen. Sie können auch sofort mit einem USB-Gerät oder USB-Ethernet-Adapter starten, wenn das Surface-Gerät durch gleichzeitiges Drücken der **Leiser**-Taste und der **Ein/Aus**-Taste ausgeschaltet wird. 

Damit die angegebene Startreihenfolge wirksam wird, müssen Sie die Option "Alternative **Startsequenz** aktivieren" auf **"Ein"** festlegen , wie in Abbildung 7 dargestellt. 

![Konfigurieren der Startreihenfolge für Ihr Surface-Gerät](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Abbildung7. Konfigurieren der Startreihenfolge für Ihr Surface-Gerät* 

Mit der Option **Enable IPv6 for PXE Network Boot** können Sie zudem die IPv6-Unterstützung für PXE aktivieren und deaktivieren, wenn Sie eine Windows-Bereitstellung mit PXE ausführen und der PXE-Server nur für IPv4 konfiguriert ist.  

## UEFI-Menü: Verwaltung
Auf der Verwaltungsseite können Sie die Verwendung von Zero Touch UEFI Management und anderer Features auf berechtigten Geräten wie Surface Pro 7, Surface Pro X und Surface Laptop 3 verwalten.  

![Verwalten des Zugriffs auf zero Touch UEFI Management und andere Features Abbildung ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *8. Verwalten des Zugriffs auf zero Touch UEFI Management und andere Features* 


Mit zero Touch UEFI Management können Sie die UEFI-Einstellungen remote mithilfe eines Geräteprofils in Intune verwalten, das als Device Firmware Configuration Interface (DFCI) bezeichnet wird. Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit, berechtigte Geräte mit DFCI zu verwalten, auf **"Bereit" festgelegt.** Um DFCI zu verhindern, wählen **Sie "Abmelden" aus.** 

> [!NOTE]
> Die Seite mit den Einstellungen für die UEFI-Verwaltung und die Verwendung von DFCI ist derzeit für Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 und Surface Pro X verfügbar. Weitere Informationen finden Sie unter [Intune-Verwaltung von Surface UEFI-Einstellungen.](surface-manage-dfci-guide.md)

## UEFI-Menü: Beenden 

Verwenden Sie **die Schaltfläche "Jetzt** neu starten" auf der Seite **"Beenden",** um die UEFI-Einstellungen zu beenden, wie in Abbildung 9 dargestellt. 

![Surface UEFI beenden und Gerät neu starten](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Abbildung9. Klicken Sie auf „Jetzt neu starten“, um Surface UEFI zu beenden und das Gerät neu zu starten.*

## Surface UEFI-Startbildschirme

Wenn Sie die Firmware für das Surface-Gerät mit Windows Update oder per manueller Installation aktualisieren, werden die Updates nicht sofort auf dem Gerät installiert, sondern erst beim nächsten Neustart. Weitere Informationen zum Updateprozess für die Surface-Firmware finden Sie unter [Verwalten von Treiber- und Firmwareupdates für Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). Der Fortschritt des Firmwareupdates wird in einem Bildschirm mit Statusanzeigen in verschiedenen Farben angezeigt, um die Firmware für die einzelnen Komponenten zu unterscheiden. Die Statusleiste jeder Komponente ist in den Abbildungen 9 bis 18 dargestellt.

![Surface UEFI-Firmwareupdate mit blauer Statusanzeige](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Abbildung10. Surface-UEFI-Firmwareupdate mit einer blauen Statusanzeige*

![System Embedded Controller-Firmware mit grüner Statusanzeige](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Abbildung11. System Embedded Controller-Firmwareupdate mit einer grünen Statusanzeige*

![SAM-Controller-Firmwareupdate mit orangefarbener Statusanzeige](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Abbildung 12 SAM-Controller-Firmwareupdate mit einer orangefarbenen Statusanzeige*

![Intel Management Engine-Firmware mit roter Statusanzeige](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Abbildung 13 Intel Management Engine-Firmwareupdate mit einer roten Statusanzeige*

![Surface Touch-Firmware mit grauer Statusanzeige](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Abbildung 14 Surface Touch-Firmwareupdate mit einer grauen Statusanzeige*

![Surface -KIP-Firmware mit hellgrüner Statusleiste](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Abbildung15. Das Surface -KIP-Firmwareupdate zeigt eine hellgrüne Statusanzeige an.*

![Surface -ISH-Firmware mit rosa Statusleiste](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Abbildung 16 Das Surface ISH-Firmwareupdate zeigt eine hellrote Statusanzeige an.*

![Surface Trackpad-Firmware mit grauer Statusleiste](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Abbildung17. Das Surface Trackpad-Firmwareupdate zeigt eine pinke Statusanzeige an.*

![Surface -TCON-Firmware mit hellgrauer Statusleiste](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Abbildung 18. Das Surface TCON-Firmwareupdate zeigt eine hellgraue Statusanzeige an.*


![Surface -TPM-Firmware mit hellvioletter Statusleiste](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Abbildung 19. Das Surface TPM-Firmwareupdate zeigt eine lila Statusanzeige an.*


>[!NOTE]
>Eine zusätzliche Warnmeldung, die darauf hinweist, dass der sichere Start deaktiviert ist, wird wie in Abbildung 19 dargestellt angezeigt.

![Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" deaktiviert wurde.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Abbildung 20. Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" in den Surface UEFI-Einstellungen deaktiviert wurde.*

## Verweise

1. Surface Go und Surface Go 2 verwenden UEFI eines Drittanbieters und unterstützen dfCI nicht. 

## Verwandte Themen

- [Intune-Verwaltung von Surface UEFI-Einstellungen](surface-manage-dfci-guide.md)

-  [Surface Enterprise Management-Modus](surface-enterprise-management-mode.md)
