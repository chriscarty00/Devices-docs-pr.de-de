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
# Verwalten der Surface UEFI-Einstellungen

Alle aktuellen und zukünftigen Generationen von Surface-Geräten verwenden eine einzigartige Unified Extensible Firmware Interface (UEFI), die von Microsoft speziell für diese Geräte entwickelt wurde. Oberflächen UEFI-Einstellungen bieten die Möglichkeit, integrierte Geräte und Komponenten zu aktivieren oder zu deaktivieren, die UEFI-Einstellungen vor Änderungen zu schützen und die Start Einstellungen des Surface-Geräts anzupassen. 

## Unterstützte Produkte

Die UEFI-Verwaltung wird auf der folgenden Grundlage unterstützt: 

- Surface pro 4, Surface pro (5. Generation), Surface pro 6, Surface pro 7, Surface pro X
- Surface Laptop (1st Generation), Surface Laptop 2, Surface Laptop 3, Surface Laptop go
- Surface Studio (1st Generation), Surface Studio 2
- DGM-Buch, DGM-Buch 2, DGM-Buch 3
- Surface go, Surface Go 2

## Unterstützung für Cloud-basiertes Management

Mit DFCI-Profilen (Device Firmware Configuration Interface), die in Microsoft InTune integriert sind (jetzt in Public Preview verfügbar), erweitert die Oberfläche-UEFI-Verwaltung den modernen Verwaltungs Stapel auf die UEFI-Hardwareebene. DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Kontrolle über Sicherheitseinstellungen, einschließlich Startoptionen und integrierte Peripheriegeräte, und legt die Grundlagen für fortschrittliche Sicherheitsszenarien in der Zukunft fest. DFCI steht derzeit für Surface pro 7, Surface pro X und Surface Laptop 3 zur Verfügung. Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).

## Menü "DGM-UEFI öffnen"

So passen Sie die UEFI-Einstellungen während des Systemstarts an:

1. Fahren Sie die Oberfläche herunter, und warten Sie etwa 10 Sekunden, um sicherzustellen, dass Sie deaktiviert ist.
2. Halten Sie die **Lautstärke** Taste gedrückt, und drücken Sie gleichzeitig die **Power-Taste** , und lassen Sie sie los.
3. Wenn das Microsoft-oder Surface-Logo auf dem Bildschirm angezeigt wird, halten Sie die **Lautstärke** Taste gedrückt, bis der UEFI-Bildschirm angezeigt wird.

## UEFI-PC-Informationsseite

Auf der Seite PC-Informationen finden Sie detaillierte Informationen zu Ihrem Surface-Gerät: 

- **Modell** – das Modell Ihres Surface-Geräts wird hier angezeigt, beispielsweise Surface Book 2 oder Surface pro 7. Die genaue Konfiguration Ihres Geräts wird nicht angezeigt (z. B. Prozessor, Größe des Datenträgers oder Arbeitsspeicher). 
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

## UEFI-Sicherheitsseite 

![Konfigurieren von Surface UEFI-Sicherheitseinstellungen](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Abbildung2. Konfigurieren von Surface UEFI-Sicherheitseinstellungen*

Auf der Seite "Sicherheit" können Sie ein Kennwort zum Schützen von UEFI-Einstellungen festlegen. Dieses Kennwort muss eingegeben werden, wenn Sie das Surface-Gerät mit UEFI starten. Das Kennwort kann die folgenden Zeichen enthalten (siehe Abbildung 3): 

- Großbuchstaben: A-Z 

- Kleinbuchstaben : a-z 

- Zahlen: 1-0 

- Sonderzeichen:! @ # $% ^& * ()? <>{} []-_ = + |.,;: "'" 

Das Kennwort muss mindestens 6 Zeichen lang sein und Groß-/Kleinschreibung beachten. 

![Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Abbildung3. Hinzufügen eines Kennworts zum Schutz der Surface UEFI-Einstellungen*

Auf der Seite Sicherheit können Sie außerdem die Konfiguration für den sicheren Start auf Ihrem Surface-Gerät ändern. Die Technologie für den sicheren Start verhindert, dass nicht autorisierter Startcode auf Ihrem Surface Gerät gestartet werden kann, und sie schützt Sie vor Schadsoftwareinfektionen durch Bootkits und Rootkits. Sie können den sicheren Start deaktivieren, damit Ihr Surface-Gerät Betriebssysteme von Drittanbietern oder startbare Medien starten kann. Sie können auch den sicheren Start für die Verwendung von Zertifikaten von Drittanbietern konfigurieren, wie in Abbildung 4 zu sehen ist. Weitere Informationen finden Sie unter [Sicherer Start](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in der TechNet-Bibliothek.

![Konfigurieren des sicheren Starts](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Abbildung 4. Konfigurieren des sicheren Starts*

Je nach Gerät können Sie möglicherweise auch feststellen, ob Ihr TPM aktiviert oder deaktiviert ist. Wenn die Einstellung **TPM aktivieren**  nicht angezeigt wird, öffnen Sie TPM. msc in Windows, um den Status zu überprüfen, wie in Abbildung 5 dargestellt. Das TPM wird zur Authentifizierung der Verschlüsselung Ihrer Gerätedaten mit BitLocker verwendet. Weitere Informationen finden Sie unter [Übersicht über BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview). 

![TPM-Konsole](images/manage-surface-uefi-fig5-a.png "TPM console")

*Abbildung5. TPM-Konsole*


## UEFI-Menü: Geräte 

Auf der Seite "Geräte" können Sie bestimmte Geräte und Komponenten aktivieren oder deaktivieren, einschließlich:

- Docking- und USB-Anschlüsse 

- MicroSD oder SD-Kartensteckplatz 

- Rückwärtige Kamera 

- Frontkamera 

- Infrarotkamera 

- WLAN und Bluetooth 

- Integriertes Audio (Lautsprecher und Mikrofon) 

Jedes Gerät ist mit einer Schieberegler-Schaltfläche aufgeführt, die Sie **in die Position ein (aktiviert** ) oder **aus** (deaktiviert) verschieben können, wie in Abbildung 6 dargestellt. 

![Aktivieren bzw. Deaktivieren bestimmter Geräte](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Abbildung6. Aktivieren bzw. Deaktivieren bestimmter Geräte*

## UEFI-Menü: Startkonfiguration 

Auf der Start Konfigurationsseite können Sie die Reihenfolge ihrer Startgeräte ändern sowie den Start der folgenden Geräte aktivieren oder deaktivieren: 

- Windows-Start-Manager 

- USB-Speicher 

- PXE-Netzwerk 

- Interner Speicher 

Sie können sofort mit einem bestimmten Gerät starten oder mit dem Touchscreen links neben dem Gerät in der Liste wischen. Sie können auch sofort mit einem USB-Gerät oder USB-Ethernet-Adapter starten, wenn das Surface-Gerät durch gleichzeitiges Drücken der **Leiser**-Taste und der **Ein/Aus**-Taste ausgeschaltet wird. 

Damit die angegebene Startreihenfolge wirksam wird, müssen Sie die Option **Alternative Startsequenz aktivieren** auf **ein**festlegen, wie in Abbildung 7 dargestellt. 

![Konfigurieren der Startreihenfolge für Ihr Surface-Gerät](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Abbildung7. Konfigurieren der Startreihenfolge für Ihr Surface-Gerät* 

Mit der Option **Enable IPv6 for PXE Network Boot** können Sie zudem die IPv6-Unterstützung für PXE aktivieren und deaktivieren, wenn Sie eine Windows-Bereitstellung mit PXE ausführen und der PXE-Server nur für IPv4 konfiguriert ist.  

## UEFI-Menü: Verwaltung
Auf der Seite "Verwaltung" können Sie die Verwendung der NULL-Touch-UEFI-Verwaltung und anderer Features auf geeigneten Geräten wie Surface pro 7, Surface pro X und Surface Laptop 3 verwalten.  

![Verwalten des Zugriffs auf die UEFI-Verwaltung und andere Features in ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *Abbildung 8. Verwalten des Zugriffs auf die UEFI-Verwaltung und andere Features von Zero Touch* 


Mit der UEFI-Verwaltung mit Zero Touch können Sie die UEFI-Einstellungen mithilfe eines Geräteprofils in InTune, der so genannten Device Firmware Configuration Interface (DFCI), remote verwalten. Wenn Sie diese Einstellung nicht konfigurieren, ist die Möglichkeit, berechtigte Geräte mit DFCI zu verwalten, auf **Ready**eingestellt. Um DFCI zu verhindern, wählen Sie **Abmelden aus**. 

> [!NOTE]
> Die Seite "UEFI-Verwaltungseinstellungen" und die Verwendung von DFCI steht nur auf Surface pro 7, Surface pro X und Surface Laptop 3 zur Verfügung.  

Weitere Informationen finden Sie unter [InTune-Verwaltung von Oberflächen UEFI-Einstellungen](surface-manage-dfci-guide.md).

## UEFI-Menü: beenden 

Verwenden Sie die Schaltfläche **jetzt neu starten** auf der Seite **Beenden** , um die UEFI-Einstellungen zu beenden, wie in Abbildung 9 zu sehen ist. 

![Surface UEFI beenden und Gerät neu starten](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Abbildung9. Klicken Sie auf „Jetzt neu starten“, um Surface UEFI zu beenden und das Gerät neu zu starten.*

## Surface UEFI-Startbildschirme

Wenn Sie die Firmware für das Surface-Gerät mit Windows Update oder per manueller Installation aktualisieren, werden die Updates nicht sofort auf dem Gerät installiert, sondern erst beim nächsten Neustart. Weitere Informationen zum Updateprozess für die Surface-Firmware finden Sie unter [Verwalten von Treiber- und Firmwareupdates für Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). Der Fortschritt des Firmwareupdates wird in einem Bildschirm mit Statusanzeigen in verschiedenen Farben angezeigt, um die Firmware für die einzelnen Komponenten zu unterscheiden. Die Statusanzeige jeder Komponente wird in den Abbildungen 9 bis 18 angezeigt.

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

![Surface Kip-Firmware mit hellgrün-Statusleiste](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Abbildung15. Das Firmware-Update für Surface Kip zeigt eine hell grüne Statusleiste an.*

![Surface ish-Firmware mit rosa Statusleiste](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Abbildung 16 die Firmware-Aktualisierung der Surface ish zeigt eine hell Rosa Statusleiste an.*

![Surface-Trackpad-Firmware mit grauer Statusleiste](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Abbildung17. Das Surface Trackpad-Firmware-Update zeigt eine rosafarbene Statusleiste an.*

![Surface TCON-Firmware mit hellgrauer Statusleiste](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Abbildung 18. Die Oberfläche-TCON-Firmware-Aktualisierung zeigt eine hell graue Statusleiste an.*


![Surface TPM-Firmware mit hell violetter Statusleiste](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Abbildung 19. Das TPM-Firmware-Update für Surface zeigt eine violette Statusleiste an.*


>[!NOTE]
>Eine zusätzliche Warnmeldung, die besagt, dass der sichere Start deaktiviert ist, wird angezeigt, wie in Abbildung 19 zu sehen ist.

![Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" deaktiviert wurde.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Abbildung 20. Surface-Startbildschirm mit dem Hinweis, dass die Option "Sicherer Start" in den Surface UEFI-Einstellungen deaktiviert wurde.*

## Verwandte Themen

- [Intune-Verwaltung von Surface UEFI-Einstellungen](surface-manage-dfci-guide.md)

-  [Surface Enterprise Management-Modus](surface-enterprise-management-mode.md)
