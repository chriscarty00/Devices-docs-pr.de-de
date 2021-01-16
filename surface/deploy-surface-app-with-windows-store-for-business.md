---
title: Bereitstellen der Surface-App mit dem Microsoft Store für Unternehmen oder dem Microsoft Store für Bildungseinrichtungen (Surface)
description: Erfahren Sie, wie Sie eine Surface-App mit dem Microsoft Store für Unternehmen oder dem Microsoft Store für Bildungseinrichtungen hinzufügen und herunterladen sowie die Surface-App mit PowerShell und MDT installieren.
keywords: Surface-App, App, Bereitstellung, anpassen
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271072"
---
# Bereitstellen der Surface-App im Microsoft Store für Unternehmen und Bildungseinrichtungen

**Betrifft**

- Surface Pro 7+
- Surface Laptop Go
- Surface Pro 7
- Surface Laptop 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Surface Go mit LTE
- Surface Book 2
- Surface Pro mit LTE Advanced (Modell 1807)
- Surface Pro (Modell 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface3
- Surface Pro 3


Die Surface App ist eine einfache Microsoft Store-App, die die Steuerung vieler Surface-spezifischer Einstellungen und Optionen bietet, darunter: 

* Aktivieren oder Deaktivieren der Windows-Taste auf dem Surface-Gerät 
 

* Anpassen der Empfindlichkeit des Surface-Stifts 
 

* Anpassen der Tastenaktionen des Surface-Stifts 
 

* Aktivieren oder Deaktivieren der Audioerweiterungen des Surface-Geräts 
 

* Schneller Zugriff auf Supportdokumentation und Informationen für Ihr Gerät

Kunden, die Windows Update verwenden, erhalten normalerweise die Surface-App als Teil automatischer Updates. Wenn Ihre Organisation jedoch Images für die Bereitstellung auf Ihren Surface-Geräten vorbereitet, sollten Sie die Surface-App (früher Als Surface Hub bezeichnet) in den Imageerstellungs- und Bereitstellungsprozess einplanen, anstatt dass Benutzer jedes einzelnen Geräts die App aus dem Microsoft Store oder aus dem Microsoft Store für Unternehmen herunterladen und installieren müssen. 

> [!NOTE]
> Dieser Artikel gilt nicht für Surface Pro X. Weitere Informationen finden Sie unter [Bereitstellen, Verwalten](surface-pro-arm-app-management.md) und Warten von Surface Pro X

## Übersicht über die Surface-App

Die Surface App steht als kostenloser Download aus dem [Microsoft Store zur Verfügung.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) Benutzer können sie aus dem Microsoft Store herunterladen und installieren. Wenn Ihre Organisation stattdessen den Microsoft Store für Unternehmen verwendet, müssen Sie sie dem Inventar Ihres Store hinzufügen und die App möglicherweise in Ihren Windows-Bereitstellungsprozess mit einplanen. Diese Prozesse werden in diesem Artikel behandelt. Weitere Informationen zum Microsoft Store für Unternehmen finden Sie im [Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/) im Windows TechCenter. 

## Hinzufügen einer Surface-App zu einem Microsoft Store für Unternehmen-Konto 

Bevor Benutzer eine App aus dem Microsoft Store für Unternehmen eines Unternehmens installieren oder bereitstellen können, müssen die gewünschten Apps zuerst für die Benutzer eines Unternehmens verfügbar gemacht und lizenziert werden. 

1. Falls noch nicht geschehen, erstellen Sie ein [Microsoft Store für Unternehmen-Konto.](https://www.microsoft.com/business-store) 

2. Melden Sie sich beim Portal an. 

3. Aktivieren Sie die Offlinelizenzierung: Klicken Sie auf "Manage->**Store settings",** und aktivieren Sie dann das Kontrollkästchen "Offline lizenzierte Apps für Personen anzeigen, die im Store kaufen", wie in Abbildung 1 dargestellt. **** Weitere Informationen zu Lizenzierungsmodellen für Microsoft Store für Unternehmen-Apps finden Sie unter ["Apps" im Microsoft Store für Unternehmen und Bildungseinrichtungen.](https://docs.microsoft.com/microsoft-store/)

   > [!div class="mx-imgBorder"]
   > ![Kontrollkästchen "Apps für Offlinelizenzen anzeigen"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Abbildung1. Aktivieren von Apps für die Offlineverwendung*

4. Fügen Sie Ihrem Microsoft Store für Unternehmen-Konto eine Surface-App hinzu, indem Sie dieses Verfahren verwenden:

    * Klicken Sie auf das **Menü "Shop".**
    
    * Geben Sie im Suchfeld die **Surface-App ein,** und klicken Sie dann auf das Suchsymbol.
    
    * Nachdem die Surface-App in den Suchergebnissen angezeigt wurde, klicken Sie auf das Symbol der App.
    
    * Ihnen wird eine Auswahl angezeigt (Wählen **Sie "Online"** oder **"Offline"** aus), wie in Abbildung 2 dargestellt.
    
      > [!div class="mx-imgBorder"]
      > ![Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App ihrem Bestand hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Abbildung2. Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App ihrem Bestand hinzu.*
    
    * Klicken Sie **auf "Offline",** um den Offlinelizenzierungsmodus auszuwählen.
    
    * Klicken **Sie auf "App herunterladen",** um die App ihrem Microsoft Store für Unternehmen hinzuzufügen. Wie in Abbildung 3 dargestellt, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mithilfe eines Verwaltungstools bereitgestellt oder von der Bestandsseite des Unternehmens in ihrem privaten Store heruntergeladen werden können.
    
      > [!div class="mx-imgBorder"]
      > ![Fenster "Offline lizenzierte App-Bestätigung", ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Abbildung 3. Offline lizenzierte App-Bestätigung*
      
    * Klicken Sie auf **OK**.

## Herunterladen der Surface-App aus einem Microsoft Store für Unternehmen-Konto
Nachdem Sie eine App zum Microsoft Store für Unternehmen-Konto im Offlinemodus hinzugefügt haben, können Sie die App herunterladen und als AppxBundle zu einer Bereitstellungsfreigabe hinzufügen.

1. Melden Sie sich beim Microsoft Store für Unternehmen-Konto unter https://businessstore.microsoft.com an.

2. Klicken **Sie auf ">Apps & Software verwalten".** Es wird eine Liste aller Apps Ihres Unternehmens angezeigt, einschließlich der Surface-App, die Sie in der Add Surface App zu einem [Microsoft Store für](#add-surface-app-to-a-microsoft-store-for-business-account) Business-Kontoabschnitt in diesem Artikel hinzugefügt haben.

3. Klicken **Sie**unter "Aktionen" auf die Auslassungspunkte (**...**), und klicken Sie dann auf **"Zur Offlineverwendung für** die Surface-App herunterladen".

4. Wählen Sie die **** gewünschten **Plattform-** und Architekturoptionen aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.

    > [!div class="mx-imgBorder"]
    > ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Abbildung 4. Herunterladen des AppxBundle-Pakets für eine App*
    
5. Klicken Sie **auf "Herunterladen".** Das AppxBundle-Paket wird heruntergeladen. Notieren Sie sich den Pfad der heruntergeladenen Datei, da Sie dies später in diesem Artikel benötigen.

6. Klicken Sie entweder **auf die Option "Codierte Lizenz"** oder **auf die Option "Nicht codierte Lizenz".** Verwenden Sie die codierte Lizenzoption mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows-Konfigurations-Designer zum Erstellen eines Bereitstellungspakets verwenden. Wählen Sie die Option "Nicht codierte Lizenz" aus, wenn Sie deployment Image Servicing and Management (DISM) oder Bereitstellungslösungen basierend auf der Imageerstellung verwenden, einschließlich des Microsoft Deployment Toolkits (MDT).

7. Klicken **Sie auf "Generieren",** um die Lizenz für die App zu generieren und herunterzuladen. Notieren Sie sich den Pfad der Lizenzdatei, da Sie dies später in diesem Artikel benötigen.

>[!NOTE]
>Wenn Sie eine App für die Offlineverwendung herunterladen, z. B. die Surface-App, sehen Sie möglicherweise einen Abschnitt am unteren Rand der Seite mit der Bezeichnung **"Erforderliche Frameworks".** Auf den Zielcomputern müssen die Frameworks installiert sein, damit die App ausgeführt werden kann. Daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (x86 oder x64) wiederholen und sie auch als Teil der weiter später in diesem Artikel erläuterten Windows-Bereitstellung verwenden.

Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-App.

> [!div class="mx-imgBorder"]
> ![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Abbildung5. Erforderliche Frameworks für die Surface-App*

>[!NOTE]
>Die Versionsnummern der Surface-App und die erforderlichen Frameworks ändern sich, wenn die Apps aktualisiert werden. Suchen Sie nach der neuesten Version der Surface-App und den einzelnen Frameworks im Microsoft Store für Unternehmen. Verwenden Sie immer die Surface-App und die empfohlenen Frameworkversionen, wie sie vom Microsoft Store für Unternehmen bereitgestellt werden. Die Verwendung veralteter Frameworks oder der falschen Versionen kann zu Fehlern oder Anwendungsabstürzen führen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-App herunterzuladen:

1. Klicken Sie auf die Schaltfläche **"Herunterladen"** **unter Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. Dadurch wird Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe heruntergeladen. Die Datei "Appx" in den angegebenen Ordner.

2. Klicken Sie auf die Schaltfläche **"Herunterladen"** **unter Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. Dadurch wird die Datei Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx in den angegebenen Ordner heruntergeladen.

>[!NOTE]
>Nur die 64-Bit-Version (x64) jedes Frameworks ist für Surface-Geräte erforderlich. Surface Geräte sind systemeigene 64-Bit-UEFI-Geräte und nicht kompatibel mit 32-Bit-Versionen (x86) von Windows, die 32-Bit-Frameworks erfordern würden. 

## Installieren der Surface-App auf Ihrem Computer mit PowerShell
Das folgende Verfahren stellt die Surface-App auf Ihrem Computer bereit und stellt sie für alle Benutzerkonten zur Verfügung, die anschließend auf dem Computer erstellt wurden.

1. Laden Sie mithilfe des im Abschnitt "Herunterladen der Surface-App aus einem [Microsoft Store für Business-Konto"](#download-surface-app-from-a-microsoft-store-for-business-account) dieses Artikels beschriebenen Verfahrens die Surface-AppxBundle und die Lizenzdatei herunter. 

2. Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.

    >[!NOTE]
    >Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der App.
    
3. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Wo befindet sich der Ordner, in den Sie die AppxBundle und die Lizenzdatei aus dem Microsoft Store für Unternehmen `<DownloadPath>` heruntergeladen haben.

    Wenn Sie beispielsweise die Dateien in "c:\Temp" heruntergeladen haben, führen Sie den folgenden Befehl aus:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. Die Surface-App ist jetzt auf dem aktuellen Windows-Computer verfügbar. 

   Bevor die Surface-App auf dem Computer funktionsfähig ist, auf dem sie bereitgestellt wurde, müssen Sie auch die weiter oben in diesem Artikel beschriebenen Frameworks bereitstellen. Verwenden Sie zum Bereitstellen dieser Frameworks das folgende Verfahren in der PowerShell-Sitzung mit erhöhten Rechten, die Sie zum Bereitstellen der Surface-App verwendet haben.

5. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Installieren der Surface-App mit MDT
Im folgenden Verfahren wird MDT verwendet, um die Installation der Surface-App zum Zeitpunkt der Bereitstellung zu automatisieren. Die App wird automatisch von MDT bereitgestellt, sodass Sie dieses Verfahren mit bereits vorhandenen Images ausführen können. Dies ist der empfohlene Prozess für die Bereitstellung der Surface-App als Teil einer Windows-Bereitstellung auf Surface-Geräten, da dadurch die plattformübergreifende Kompatibilität des Windows-Images nicht reduziert wird.

1. Laden Sie mithilfe des [weiter oben in diesem](#download-surface-app-from-a-microsoft-store-for-business-account)Artikel beschriebenen Verfahrens die Surface-App-App -AppxBundle und die Lizenzdatei herunter. 

2. Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**

3. Geben Sie **auf der Seite** "Befehlsdetails" des Assistenten **** für neue Anwendungen das Standardarbeitsverzeichnis und für den Befehl den Dateinamen von "AppxBundle" wie folgt an: ****

   * Befehl:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Arbeitsverzeichnis: %DEPLOYROOT%\Applications\SurfaceApp

Damit die Surface-App auf dem Zielcomputer funktioniert, sind auch die weiter oben in diesem Artikel beschriebenen Frameworks erforderlich. Verwenden Sie das folgende Verfahren, um die für die Surface-App erforderlichen Frameworks in MDT zu importieren und als Abhängigkeiten zu konfigurieren.

1. Laden Sie mithilfe des weiter oben in diesem Artikel beschriebenen Verfahrens die Frameworkdateien herunter. Speichern Sie jedes Framework in einem separaten Ordner.

2. Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**

3. Geben Sie **auf der Seite "Befehlsdetails"** im **** Befehlsfeld und im Standardarbeitsverzeichnis den Dateinamen jeder Anwendung ein, die Sie heruntergeladen haben.

Verwenden Sie diesen Prozess, um die Frameworks als Abhängigkeiten der Surface-App zu konfigurieren:

1. Öffnen Sie die Eigenschaften der Surface-App in der MDT Deployment Workbench.

2. Klicken Sie **auf die** Registerkarte Abhängigkeiten, und klicken Sie dann auf **Hinzufügen**.

3. Aktivieren Sie das Kontrollkästchen für jedes Framework mit dem Namen, den Sie im Assistenten für neue Anwendungen angegeben haben.

Nach dem Import steht die Surface-App **** zur Auswahl im Schritt "Anwendungen" des Windows-Bereitstellungs-Assistenten zur Verfügung. Sie können die Anwendung auch automatisch installieren, indem Sie sie in der Tasksequenz für die Bereitstellung wie folgt angeben:

1. Öffnen Sie die Tasksequenz für die Bereitstellung in der Deployment Workbench von MDT.

2. Fügen Sie dem Abschnitt **Status wiederherstellen** der Bereitstellung eine neue Aufgabe **Anwendung installieren** hinzu.

3. Wählen **Sie "Einzelne Anwendung installieren"** aus, und geben Sie die **Surface App** als zu **installierende Anwendung an.**

Weitere Informationen zum Hinzufügen von Apps in Ihre Windows-Bereitstellungen finden Sie unter Bereitstellen von [Windows 10 mit dem Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
