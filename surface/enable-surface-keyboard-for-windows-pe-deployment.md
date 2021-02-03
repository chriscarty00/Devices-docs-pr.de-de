---
title: So aktivieren Sie die Surface -Laptop-Tastatur während der MDT-Bereitstellung
description: Wenn Sie MDT zum Bereitstellen von Windows 10 auf Surface Laptops verwenden, müssen Sie Tastaturtreiber für die Verwendung in der Windows PE-Umgebung importieren.
keywords: Windows 10-Oberfläche, automatisieren, anpassen, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312061"
---
# So aktivieren Sie die Surface -Laptop-Tastatur während der MDT-Bereitstellung

In diesem Artikel wird ein Bereitstellungsansatz behandelt, bei dem Das Microsoft Deployment Toolkit (MDT) verwendet wird. Sie können diese Informationen auch auf andere Bereitstellungsmethoden anwenden. Auf den meisten Arten von Surface-Geräten sollte die Tastatur während der Lite Touch Installation (LTI) funktionieren. Surface Laptop erfordert jedoch einige zusätzliche Treiber, um die Tastatur zu aktivieren. Für Surface Laptop (1. Generation) und Surface Laptop 2-Geräte müssen Sie die Ordnerstruktur und Auswahlprofile vorbereiten, mit denen Sie Tastaturtreiber für die Verwendung während der Windows Preinstallation Environment (Windows PE)-Phase von LTI angeben können. Weitere Informationen zu dieser Ordnerstruktur finden Sie unter Bereitstellen eines [Windows 10-Images mithilfe von MDT: Schritt 5: Vorbereiten des Treiberrepositorys.](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)

> [!TIP]    
> Wenn Sie Tastaturtreiber für Surface Laptop 2 und Surface Laptop 3 in derselben Windows PE-Startinstanz verwenden, müssen Sie die Firmware möglicherweise manuell zurücksetzen, wenn die Tastatur oder das Touchpad in Windows PE nicht funktionieren:
>
> - Halten Sie den Netzschalter 30 Sekunden lang gedrückt. Wenn Sie mit einem Netzteil verbunden sind, drücken und halten Sie den Netzschalter gedrückt, bis das Licht am Ende des Netzkabels kurz ausgeschaltet wird, bevor Sie wieder einschalten.

> [!IMPORTANT]
> Wenn Sie ein Windows 10-Image auf einem Surface Laptop bereitstellen, auf dem Windows 10 im S-Modus vorinstalliert ist, finden Sie informationen unter KB [4032347, Probleme](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)bei der Bereitstellung von Windows auf Surface-Geräten mit vorinstalliertem Windows 10 im S-Modus.

Führen Sie die folgenden Schritte aus, um dem Auswahlprofil die Tastaturtreiber hinzuzufügen:

1. Laden Sie die neueste Surface Laptop -MSI-Datei von den entsprechenden Speicherorten herunter:
    - [Surface Laptop (1. Generation) Treiber und Firmware](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 Treiber und Firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 mit Intel -Prozessortreibern und Firmware](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extrahieren Sie den Inhalt der Surface Laptop-MSI-Datei in einen Ordner, den Sie leicht finden können (z. B. c:\surface_laptop_drivers). Öffnen Sie zum Extrahieren des Inhalts ein Eingabeaufforderungsfenster mit erhöhten Rechten, und führen Sie den Befehl aus dem folgenden Beispiel aus:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Öffnen Sie die Deployment Workbench, erweitern Sie den Knoten **"Deployment Shares"** und Ihre Bereitstellungsfreigabe, und navigieren Sie dann zum **Ordner "WindowsPEX64".**

   ![Abbildung des Speicherorts des Ordners WindowsPEX64 in der Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Klicken Sie mit der rechten Maustaste auf den **Ordner WindowsPEX64,** und wählen Sie **"Treiber importieren" aus.**

5. Folgen Sie den Anweisungen im Assistenten zum Importieren von Treibern, um die Treiberordner in den Ordner WindowsPEX64 zu importieren.  

    > [!NOTE]
    >  Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.  Die Verzeichnisstruktur beginnt entweder mit SurfacePlatformInstaller (ältere MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien), je nachdem, wann die MSI veröffentlicht wurde. 

    Um Surface Laptop (1. Generation) zu unterstützen, importieren Sie die folgenden Ordner:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\serialioi2c
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialSERIEART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

     
    Um Surface Laptop 3 mit Intel Processor zu unterstützen, importieren Sie die folgenden Ordner:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialSERIEART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    Beim Importieren der folgenden Ordner werden vollständige Tastatur-, Trackpad- und Touchfunktionen in PE für Surface Laptop 3 aktiviert.

    - SerialIOGPIO
    - SerialIOI2C
    - SerialIOSPI
    - SerialSERIEART
    - itouch
    - Chipsatz
    - ChipsatzLPSS
    - ChipetNorthpeak
    - ManagementEngine
    - SurfaceAcpiNotify
    - SurfaceBattery
    - SurfaceDockIntegration
    - SurfaceHidMini
    - SurfaceHotPlug
    - SurfaceIntegration
    - SurfaceSerialHub
    - SurfaceService
    - SurfaceStorageFwUpdate

     > [!NOTE]
     >  Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.  Die Verzeichnisstruktur beginnt entweder mit SurfacePlatformInstaller (ältere MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien), je nachdem, wann die MSI veröffentlicht wurde. 

     Um Surface Laptop (1. Generation) zu unterstützen, importieren Sie die folgenden Ordner:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Um Surface Laptop 2 zu unterstützen, importieren Sie die folgenden Ordner:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\I2C
    - SurfacePlatformInstaller\Drivers\System\SPI
    - SurfacePlatformInstaller\Drivers\System\UART
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Oder verwenden Sie für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialSERIEART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Um Surface Laptop 3 mit Intel Processor zu unterstützen, importieren Sie die folgenden Ordner:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialSERIEART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3. Die verbleibenden Surface -Laptop-Treiber befinden sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3".

6. Stellen Sie sicher, dass der Ordner WindowsPEX64 jetzt die importierten Treiber enthält. Der Ordner sollte etwa wie folgt aussehen:  

   ![Abbildung der neu importierten Treiber im Ordner "WindowsPEX64" der Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Konfigurieren Sie ein Auswahlprofil, das den Ordner "WindowsPEX64" verwendet. Das Auswahlprofil sollte etwa wie folgt aussehen:  

   ![Abbildung des im Rahmen eines Auswahlprofils ausgewählten WindowsPEX64-Ordners](./images/surface-laptop-keyboard-3.png)

8. Konfigurieren Sie die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe wie folgt für die Verwendung des neuen Auswahlprofils:  

   - Wählen **Sie für die**Plattform **x64 aus.**
   - Wählen **Sie für das**Auswahlprofil das neue Profil aus.
   - Wählen **Sie "Alle Treiber aus dem Auswahlprofil hinzufügen" aus.**
   
   ![Abbildung der Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe](./images/surface-laptop-keyboard-4.png)

9. Stellen Sie sicher, dass Sie die verbleibenden Surface -Laptop-Treiber mithilfe eines Auswahlprofils oder einer **DriverGroup001-Variablen konfiguriert** haben.  
   - Für Surface Laptop (1. Generation) ist das Modell **Surface Laptop.** Die verbleibenden Surface -Laptop-Treiber sollten sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop" befinden, wie in der Abbildung unten in dieser Liste dargestellt.
   - Für Surface Laptop 2 ist surface **Laptop 2 das Modell.** Die verbleibenden Surface -Laptop-Treiber sollten sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2" befinden. 
   - Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3. Die verbleibenden Surface -Laptop-Treiber befinden sich im Ordner "\MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3".

   ![Abbildung der regulären Surface Laptop (1. Generation)-Treiber im Surface Laptop-Ordner der Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Nachdem Sie die MDT-Bereitstellungsfreigabe für die Verwendung des neuen Auswahlprofils und der zugehörigen Einstellungen konfiguriert haben, setzen Sie den Bereitstellungsprozess wie in "Bereitstellen eines [Windows 10-Images mit MDT: Schritt 6:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)Erstellen der Bereitstellungs-Tasksequenz" beschrieben fort.
