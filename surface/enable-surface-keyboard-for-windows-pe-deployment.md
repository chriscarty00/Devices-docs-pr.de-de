---
title: Aktivieren der Surface-Laptop Tastatur während der MDT-Bereitstellung
description: Wenn Sie das MDT für die Bereitstellung von Windows 10 auf Surface-Laptops verwenden, müssen Sie die Tastaturtreiber importieren, um Sie in der Windows PE-Umgebung verwenden zu können.
keywords: Windows 10 Surface, automatisieren, anpassen, MDT
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
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247307"
---
# Aktivieren der Surface-Laptop Tastatur während der MDT-Bereitstellung

In diesem Artikel wird ein Bereitstellungsansatz behandelt, in dem Microsoft Deployment Toolkit (MDT) verwendet wird. Sie können diese Informationen auch auf andere Bereitstellungsmethoden anwenden. Bei den meisten Arten von Surface-Geräten sollte die Tastatur während der Lite Touch-Installation (LTI) funktionieren. Surface Laptop erfordert jedoch einige zusätzliche Treiber, um die Tastatur zu aktivieren. Für Surface Laptop (1st Generation) und Surface Laptop 2-Geräte müssen Sie die Ordnerstruktur und die Auswahlprofile vorbereiten, mit deren Hilfe Sie während der Windows PE-Phase (Windows Preinstallation Environment) von LTI Tastaturtreiber angeben können. Weitere Informationen zu dieser Ordnerstruktur finden Sie unter [Bereitstellen eines Windows 10-Images mithilfe von MDT: Schritt 5: Vorbereiten des Treiber-Repositorys](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).


> [!IMPORTANT]
> Wenn Sie ein Windows 10-Abbild auf einem Surface-Laptop bereitstellen, auf dem Windows 10 im s-Modus vorinstalliert ist, lesen Sie KB [4032347, Probleme beim Bereitstellen von Windows auf Surface-Geräten mit vorinstalliertem Windows 10 im s-Modus](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

Führen Sie die folgenden Schritte aus, um die Tastaturtreiber zum Auswahlprofil hinzuzufügen:

1. Laden Sie die neueste msi-Datei für Surface Laptop von den entsprechenden Speicherorten herunter:
    - [Surface Laptop (1st Gen)-Treiber und-Firmware](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2-Treiber und-Firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 mit Intel-Prozessor Treibern und-Firmware](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extrahieren Sie den Inhalt der MSI-Datei des Surface-Laptops in einen Ordner, den Sie problemlos finden können (beispielsweise "c-surface_laptop_drivers"). Um den Inhalt zu extrahieren, öffnen Sie ein Eingabeaufforderungsfenster mit erhöhten Rechten, und führen Sie den Befehl aus dem folgenden Beispiel aus:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Öffnen Sie die Deployment Workbench, und erweitern Sie den Knoten **Bereitstellung Freigaben** und ihre Bereitstellungsfreigabe, und navigieren Sie dann zum Ordner **WindowsPEX64** .

   ![Bild, das den Speicherort des Ordners "WindowsPEX64" in der Deployment Workbench zeigt](./images/surface-laptop-keyboard-1.png)

4. Klicken Sie mit der rechten Maustaste auf den Ordner **WindowsPEX64** , und wählen Sie **Treiber importieren**aus.
5. Folgen Sie den Anweisungen im Assistenten zum Importieren des Treibers, um die Treiberordner in den Ordner WindowsPEX64 zu importieren.  

> [!NOTE]
>  Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.  Die Verzeichnisstruktur wird entweder mit SurfacePlatformInstaller (älteren MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien) gestartet, je nachdem, wann die MSI-Datei veröffentlicht wurde. 

Um Surface Laptop (1st Generation) zu unterstützen, importieren Sie die folgenden Ordner:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:

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

Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Wenn Sie Surface Laptop 3 mit Intel-Prozessor unterstützen möchten, importieren Sie die folgenden Ordner:

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

Beim Importieren der folgenden Ordner werden die vollständige Tastatur-, Trackpad-und Touchfunktionen in PE für Surface Laptop 3 aktiviert.

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- iTouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
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
    >  Überprüfen Sie das heruntergeladene MSI-Paket, um das Format und die Verzeichnisstruktur zu ermitteln.  Die Verzeichnisstruktur wird entweder mit SurfacePlatformInstaller (älteren MSI-Dateien) oder SurfaceUpdate (neuere MSI-Dateien) gestartet, je nachdem, wann die MSI-Datei veröffentlicht wurde. 

    Um Surface Laptop (1st Generation) zu unterstützen, importieren Sie die folgenden Ordner:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:

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

    Oder für neuere MSI-Dateien, die mit "SurfaceUpdate" beginnen, verwenden Sie:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Wenn Sie Surface Laptop 3 mit Intel-Prozessor unterstützen möchten, importieren Sie die folgenden Ordner:

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3. Die restlichen Surface-Laptop Treiber befinden sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3-Ordner.

6. Überprüfen Sie, ob der WindowsPEX64-Ordner nun die importierten Treiber enthält. Der Ordner sollte wie folgt aussehen:  

   ![Bild, in dem die neu importierten Treiber im Ordner "WindowsPEX64" der Deployment Workbench angezeigt werden](./images/surface-laptop-keyboard-2.png)

7. Konfigurieren Sie ein Auswahlprofil, das den Ordner "WindowsPEX64" verwendet. Das Auswahlprofil sollte wie folgt aussehen:  

   ![Bild, in dem der WindowsPEX64-Ordner angezeigt wird, der als Teil eines Auswahl Profils ausgewählt ist](./images/surface-laptop-keyboard-3.png)

8. Konfigurieren Sie die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe, um das neue Auswahlprofil wie folgt zu verwenden:  

   - Wählen Sie unter **Plattform**die Option **x64**aus.
   - Wählen Sie im **Auswahlprofil**das neue Profil aus.
   - Wählen Sie **alle Treiber aus dem Auswahlprofil einbeziehen aus**.
   
   ![Bild, in dem die Windows PE-Eigenschaften der MDT-Bereitstellungsfreigabe angezeigt werden](./images/surface-laptop-keyboard-4.png)

9. Überprüfen Sie, ob Sie die restlichen Surface-Laptop Treiber mithilfe eines Auswahl Profils oder einer **DriverGroup001** -Variablen konfiguriert haben.  
   - Für Surface Laptop (1st Generation) ist das Modell **Surface Laptop**. Die restlichen Surface-Laptop Treiber sollten sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop-Ordner befinden, wie in der Abbildung dargestellt, die dieser Liste folgt.
   - Für Surface Laptop 2 ist das Modell **Surface Laptop 2**. Die restlichen Surface-Laptop Treiber sollten sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2-Ordner befinden. 
   - Für Surface Laptop 3 mit Intel-Prozessor ist das Modell Surface Laptop 3. Die restlichen Surface-Laptop Treiber befinden sich im \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3-Ordner.

   ![Abbildung der normalen Surface Laptop-Treiber (1st Gen) im Surface Laptop-Ordner der Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Nachdem Sie die MDT-Bereitstellungsfreigabe für die Verwendung des neuen Auswahl Profils und der zugehörigen Einstellungen konfiguriert haben, fahren Sie mit dem Bereitstellungsprozess fort, wie unter [Bereitstellen eines Windows 10-Abbilds mit MDT: Schritt 6: Erstellen der Bereitstellungstasksequenz](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)beschrieben.
