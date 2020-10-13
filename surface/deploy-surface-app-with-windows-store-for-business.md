---
title: Bereitstelleneiner Surface-App mit Microsoft Store für Unternehmen oder Microsoft Store für Bildung (Surface)
description: Hier erfahren Sie, wie Sie Surface-App mit Microsoft Store for Business oder Microsoft Store für Education hinzufügen und herunterladen sowie Surface-App mit PowerShell und MDT installieren.
keywords: Surface-APP, APP, Bereitstellung, anpassen
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
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114713"
---
# Bereitstelleneiner Surface-App mit Microsoft Store für Unternehmen und Bildungseinrichtungen

**Gilt für:**

- Surface Laptop go
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


Die Surface-APP ist eine einfache Microsoft Store-App, die die Kontrolle über viele oberflächenspezifische Einstellungen und Optionen bietet, einschließlich: 

* Aktivieren oder Deaktivieren der Windows-Taste auf dem Surface-Gerät 
 

* Anpassen der Empfindlichkeit des Surface-Stifts 
 

* Anpassen der Tastenaktionen des Surface-Stifts 
 

* Aktivieren oder Deaktivieren der Audioerweiterungen des Surface-Geräts 
 

* Schneller Zugriff auf Support Dokumentation und-Informationen für Ihr Gerät

Für Kunden, die Windows Update verwenden, wird normalerweise die Surface-App als Teil der automatischen Updates empfangen. Wenn Ihre Organisation jedoch Bilder für die Bereitstellung auf Ihren Surface-Geräten vorbereitet, möchten Sie möglicherweise die Surface-app (vormals Surface Hub genannt) in ihren Imaging-und Bereitstellungsprozess einbeziehen, anstatt die Benutzer jedes einzelnen Geräts zum herunterladen und Installieren der APP aus dem Microsoft Store oder Ihrem Microsoft Store für Unternehmen zu verpflichten. 

> [!NOTE]
> Dieser Artikel gilt nicht für Surface pro X. Weitere Informationen finden Sie unter [bereitstellen, verwalten und warten von Surface pro X](surface-pro-arm-app-management.md)

## Übersicht über DGM-apps

Die Surface-App steht als kostenloser Download aus dem [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)zur Verfügung. Benutzer können Sie aus dem Microsoft Store herunterladen und installieren, doch wenn Ihre Organisation stattdessen Microsoft Store für Unternehmen verwendet, müssen Sie Sie dem Inventar Ihres Shops hinzufügen und die APP möglicherweise als Teil des Windows-Bereitstellungsprozesses einbeziehen. Diese Prozesse werden in diesem Artikel behandelt. Weitere Informationen zu Microsoft Store für Unternehmen finden Sie unter [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) im Windows TechCenter. 

## Hinzufügen einer Surface-APP zu einem Microsoft Store for Business-Konto 

Bevor Benutzer eine APP aus dem Microsoft Store for Business-Konto eines Unternehmens installieren oder bereitstellen können, müssen die gewünschten apps zunächst den Benutzern eines Unternehmens zur Verfügung gestellt und lizenziert werden. 

1. Wenn Sie dies noch nicht getan haben, erstellen Sie ein [Microsoft Store for Business-Konto](https://www.microsoft.com/business-store). 

2. Melden Sie sich beim Portal an. 

3. Aktivieren der Offline Lizenzierung: Klicken Sie auf **Verwalten->Store-Einstellungen**, und aktivieren Sie dann das Kontrollkästchen **Offline lizenzierte Apps für Personen, die im Store einkaufen** , wie in Abbildung 1 dargestellt. Weitere Informationen zu den Microsoft Store for Business-App-Lizenzierungsmodellen finden Sie unter [apps im Microsoft Store for Business und Education](https://docs.microsoft.com/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![Kontrollkästchen "Offline-Lizenzen-apps anzeigen"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Abbildung1. Aktivieren von Apps für die Offlineverwendung*

4. Fügen Sie Surface-APP zu Ihrem Microsoft Store for Business-Konto hinzu, indem Sie die folgenden Schritte ausführen:

    * Klicken Sie auf das Menü **Shop** .
    
    * Geben Sie im Suchfeld Surface- **App**ein, und klicken Sie dann auf das Symbol suchen.
    
    * Nachdem die Surface-app in den Suchergebnissen angezeigt wird, klicken Sie auf das Symbol der app.
    
    * Sie haben die Wahl ( **Online** oder **Offline**auswählen), wie in Abbildung 2 dargestellt.
    
      > [!div class="mx-imgBorder"]
      > ![Wählen Sie den Offline Lizenzierungsmodus aus, und fügen Sie die APP Ihrem Inventar hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Abbildung2. Wählen Sie den Offline Lizenzierungsmodus aus, und fügen Sie die APP Ihrem Inventar hinzu.*
    
    * Klicken Sie auf **Offline** , um den Offline Lizenzierungsmodus auszuwählen.
    
    * Klicken Sie auf **APP herunter** laden, um die APP Ihrem Microsoft Store for Business-Inventar hinzuzufügen. Wie in Abbildung 3 zu sehen ist, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mit einem Verwaltungstool bereitgestellt oder von der Inventarseite des Unternehmens im privaten Speicher heruntergeladen werden können.
    
      > [!div class="mx-imgBorder"]
      > ![Fenster zur Offline lizenzierten App-Bestätigung ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Abbildung 3. Offline lizenzierte App-Bestätigung*
      
    * Klicken Sie auf **OK**.

## Herunterladen der Surface-App aus einem Microsoft Store for Business-Konto
Nachdem Sie eine APP im Offline Modus zum Microsoft Store for Business-Konto hinzugefügt haben, können Sie die APP als AppxBundle zu einer Bereitstellungsfreigabe herunterladen und hinzufügen.

1. Melden Sie sich bei dem Microsoft Store for Business-Konto an https://businessstore.microsoft.com .

2. Klicken Sie auf **Verwalten->-apps & Software**. Es wird eine Liste aller apps Ihres Unternehmens angezeigt, einschließlich der Surface-APP, die Sie im Abschnitt [Hinzufügen einer Oberfläche-APP zu einem Microsoft Store for Business-Konto](#add-surface-app-to-a-microsoft-store-for-business-account) in diesem Artikel hinzugefügt haben.

3. Klicken Sie unter **Aktionen**auf die Auslassungspunkte (**.**..), und klicken Sie dann auf **herunterladen für die Offlineverwendung** für die Surface-app.

4. Wählen Sie die gewünschten **Platt Form** -und **Architektur** Optionen aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.

    > [!div class="mx-imgBorder"]
    > ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Abbildung 4. Herunterladen des AppxBundle-Pakets für eine APP*
    
5. Klicken Sie auf **herunterladen**. Das AppxBundle-Paket wird heruntergeladen. Stellen Sie sicher, dass Sie den Pfad der heruntergeladenen Datei notieren, da dies später in diesem Artikel erforderlich ist.

6. Klicken Sie entweder auf die **codierte Lizenz** oder die Option für nicht **codierte Lizenzen** . Verwenden Sie die codierte Lizenzoption mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows-Konfigurations-Designer verwenden, um ein Bereitstellungspaket zu erstellen. Wählen Sie die Option "nicht codierte Lizenz" aus, wenn Sie die Bereitstellung von Bild Wartung und-Verwaltung (DISM) oder Bereitstellungslösungen basierend auf Imaging verwenden, einschließlich des Microsoft Deployment Toolkit (MDT).

7. Klicken Sie auf **generieren** , um die Lizenz für die APP zu generieren und herunterzuladen. Stellen Sie sicher, dass Sie den Pfad der Lizenzdatei notieren, da dies später in diesem Artikel erforderlich ist.

>[!NOTE]
>Wenn Sie eine APP für die Offlineverwendung herunterladen, beispielsweise die Surface-APP, sehen Sie möglicherweise einen Abschnitt unten auf der Seite mit der Bezeichnung **erforderliche Frameworks**. Auf Ihren Zielcomputern müssen die Frameworks installiert sein, damit die app ausgeführt werden kann, daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (entweder x86 oder x64) wiederholen und Sie auch im Rahmen ihrer Windows-Bereitstellung, die weiter unten in diesem Artikel erläutert wird, einbeziehen.

Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-app.

> [!div class="mx-imgBorder"]
> ![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Abbildung5. Erforderliche Frameworks für die Surface-App*

>[!NOTE]
>Die Versionsnummern der Surface-APP und die erforderlichen Frameworks ändern sich, wenn die Apps aktualisiert werden. Überprüfen Sie, ob die neueste Version der Surface-APP und die einzelnen Frameworks in Microsoft Store for Business erhältlich sind. Verwenden Sie immer die Surface-APP und die empfohlenen Framework-Versionen, wie Sie von Microsoft Store für Unternehmen bereitgestellt werden. Das verwenden veralteter Frameworks oder fehlerhafter Versionen kann zu Fehlern oder Anwendungsabstürzen führen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-APP herunterzuladen:

1. Klicken Sie auf die Schaltfläche **herunterladen** unter **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**. Dadurch wird der Microsoft. VCLibs. 140.00-_14.0.23816.0-_x64__8wekyb3d8bbwe heruntergeladen. AppX-Datei in den angegebenen Ordner.

2. Klicken Sie auf die Schaltfläche **herunterladen** unter **Microsoft. net. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe**. Dadurch wird die Datei Microsoft. net. Native. Runtime. 1.1 _1.1.23406.0 _x64__8wekyb3d8bbwe. AppX in den angegebenen Ordner heruntergeladen.

>[!NOTE]
>Für Surface-Geräte ist nur die 64-Bit-Version (x64) jedes Frameworks erforderlich. Surface-Geräte sind native 64-Bit-UEFI-Geräte und nicht mit 32-Bit-Versionen von Windows kompatibel, für die 32-Bit-Frameworks erforderlich sind. 

## Installieren der Surface-App auf Ihrem Computer mit PowerShell
Mit dem folgenden Verfahren wird die Surface-App auf Ihrem Computer bereitgestellt und für alle auf dem Computer erstellten Benutzerkonten verfügbar gemacht.

1. Laden Sie die Oberfläche-App-AppxBundle und-Lizenzdatei herunter, und verwenden Sie das Verfahren, das in diesem Artikel im Abschnitt [herunterladen der Surface-App aus einem Microsoft Store for Business-Konto](#download-surface-app-from-a-microsoft-store-for-business-account) beschrieben wird. 

2. Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.

    >[!NOTE]
    >Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der app.
    
3. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Wo `<DownloadPath>` befindet sich der Ordner, in den Sie die AppxBundle-und Lizenzdatei aus dem Microsoft Store for Business-Konto heruntergeladen haben?

    Wenn Sie beispielsweise die Dateien nach c:\temp heruntergeladen haben, lautet der Befehl, den Sie ausführen, wie folgt:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. Die Surface-App ist jetzt auf dem aktuellen Windows-Computer verfügbar. 

   Bevor die Surface-App auf dem Computer, auf dem Sie bereitgestellt wurde, funktionsfähig ist, müssen Sie auch die oben in diesem Artikel beschriebenen Frameworks bereitstellen. Zum Bereitstellen dieser Frameworks verwenden Sie das folgende Verfahren in der erhöhten PowerShell-Sitzung, die Sie für die Bereitstellung der Surface-App verwendet haben.

5. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Installieren der Surface-App mit MDT
Das folgende Verfahren verwendet MDT, um die Installation der Surface-App zum Zeitpunkt der Bereitstellung zu automatisieren. Die App wird automatisch von MDT bereitgestellt, sodass Sie dieses Verfahren mit bereits vorhandenen Images ausführen können. Dies ist die empfohlene Vorgehensweise zum Bereitstellen der Surface-App als Teil einer Windows-Bereitstellung für Surface Devices, da dadurch die plattformübergreifende Kompatibilität des Windows-Abbilds nicht verringert wird.

1. Laden Sie die Oberfläche-App-AppxBundle und-Lizenzdatei mithilfe des [weiter oben in diesem Artikel](#download-surface-app-from-a-microsoft-store-for-business-account)beschriebenen Verfahrens herunter. 

2. Importieren Sie die heruntergeladenen Dateien mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench als neue **Anwendung mit Quelldateien**.

3. Geben Sie auf der Seite **Befehls Details** des Assistenten für neue Anwendung das Standard **Arbeitsverzeichnis** an, und geben Sie für den **Befehl** den Dateinamen des AppxBundle wie folgt an:

   * Befehl
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Arbeitsverzeichnis:%DEPLOYROOT%\Applications\SurfaceApp

Damit die Surface-App auf dem Zielcomputer funktioniert, müssen auch die oben in diesem Artikel beschriebenen Frameworks verwendet werden. Gehen Sie wie folgt vor, um die für die Surface-App erforderlichen Frameworks in MDT zu importieren und als Abhängigkeiten zu konfigurieren.

1. Laden Sie die Framework-Dateien mithilfe des weiter oben in diesem Artikel beschriebenen Verfahrens herunter. Speichern Sie die einzelnen Frameworks in einem separaten Ordner.

2. Importieren Sie die heruntergeladenen Dateien mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench als neue **Anwendung mit Quelldateien**.

3. Geben Sie auf der Seite **Befehls Details** den Dateinamen jeder Anwendung ein, die Sie im **Befehls** Feld heruntergeladen haben, und das standardmäßige Arbeitsverzeichnis.

Verwenden Sie diesen Vorgang, um die Frameworks als Abhängigkeiten der Surface-APP zu konfigurieren:

1. Öffnen Sie die Eigenschaften der Surface-app in der MDT Deployment Workbench.

2. Klicken Sie auf die Registerkarte **Abhängigkeiten** , und klicken Sie dann auf **Hinzufügen**.

3. Aktivieren Sie das Kontrollkästchen für jedes Framework unter dem Namen, den Sie im Assistenten für neue Anwendungen angegeben haben.

Nach dem Importieren steht die Surface-App im Schritt " **Anwendungen** " des Windows-Bereitstellungs-Assistenten zur Auswahl zur Verfügung. Sie können die Anwendung auch automatisch installieren, indem Sie sie in der Tasksequenz für die Bereitstellung wie folgt angeben:

1. Öffnen Sie die Tasksequenz für die Bereitstellung in der Deployment Workbench von MDT.

2. Fügen Sie dem Abschnitt **Status wiederherstellen** der Bereitstellung eine neue Aufgabe **Anwendung installieren** hinzu.

3. Wählen Sie **eine einzelne Anwendung installieren** aus, und geben Sie die **Surface-App** als die **Anwendung an, die installiert werden soll**.

Weitere Informationen zum Einschließen von apps in Ihre Windows-Bereitstellungen finden Sie unter [Bereitstellen von Windows 10 mit dem Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
