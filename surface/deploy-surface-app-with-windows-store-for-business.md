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
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832860"
---
# Bereitstelleneiner Surface-App mit Microsoft Store für Unternehmen und Bildungseinrichtungen

**Betrifft**

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

3. Aktivieren der Offline Lizenzierung: Klicken Sie auf **Verwalten->Store-Einstellungen**, und aktivieren Sie dann das Kontrollkästchen **Offline lizenzierte Apps für Personen, die im Store einkaufen** , wie in Abbildung 1 dargestellt. Weitere Informationen zu den Microsoft Store for Business-App-Lizenzierungsmodellen finden Sie unter [apps im Microsoft Store for Business und Education](https://docs.microsoft.com/microsoft-store/).<br/> <br/>
   ![Kontrollkästchen "Offline-Lizenzen-apps anzeigen"](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Abbildung1. Aktivieren von Apps für die Offlineverwendung*

4. Fügen Sie Surface-APP zu Ihrem Microsoft Store for Business-Konto hinzu, indem Sie die folgenden Schritte ausführen:
    * Klicken Sie auf das Menü **Shop** .
    * Geben Sie im Suchfeld Surface- **App**ein, und klicken Sie dann auf das Symbol suchen.
    * Nachdem die Surface-app in den Suchergebnissen angezeigt wird, klicken Sie auf das Symbol der app.
    * Sie haben die Wahl ( **Online** oder **Offline**auswählen), wie in Abbildung 2 dargestellt.<br/><br/>
    
    ![Wählen Sie den Offline Lizenzierungsmodus aus, und fügen Sie die APP Ihrem Inventar hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *Abbildung2. Wählen Sie den Offline Lizenzierungsmodus aus, und fügen Sie die APP Ihrem Inventar hinzu.*
    
    * Klicken Sie auf **Offline** , um den Offline Lizenzierungsmodus auszuwählen.
    * Klicken Sie auf **APP herunter** laden, um die APP Ihrem Microsoft Store for Business-Inventar hinzuzufügen. Wie in Abbildung 3 zu sehen ist, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mit einem Verwaltungstool bereitgestellt oder von der Inventarseite des Unternehmens im privaten Speicher heruntergeladen werden können.
    
    ![Offline lizenzierte App-Bestätigungsfenster](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *Abbildung3. Offline lizenzierte App-Bestätigung*
    * Klicken Sie auf **OK**.

## Herunterladen der Surface-App aus einem Microsoft Store for Business-Konto
Nachdem Sie eine APP im Offline Modus zum Microsoft Store for Business-Konto hinzugefügt haben, können Sie die APP als AppxBundle zu einer Bereitstellungsfreigabe herunterladen und hinzufügen.
1. Melden Sie sich bei dem Microsoft Store for Business-Konto an https://businessstore.microsoft.com .
2. Klicken Sie auf **Verwalten->-apps & Software**. Es wird eine Liste aller apps Ihres Unternehmens angezeigt, einschließlich der Surface-APP, die Sie im Abschnitt [Hinzufügen einer Oberfläche-APP zu einem Microsoft Store for Business-Konto](#add-surface-app-to-a-microsoft-store-for-business-account) in diesem Artikel hinzugefügt haben.
3. Klicken Sie unter **Aktionen**auf die Auslassungspunkte (**.**..), und klicken Sie dann auf **herunterladen für die Offlineverwendung** für die Surface-app.
4. Wählen Sie die gewünschten **Platt Form** -und **Architektur** Optionen aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.

    ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *Abbildung 4. Herunterladen des AppxBundle-Pakets für eine APP*
5. Klicken Sie auf **herunterladen**. Das AppxBundle-Paket wird heruntergeladen. Stellen Sie sicher, dass Sie den Pfad der heruntergeladenen Datei notieren, da dies später in diesem Artikel erforderlich ist.
6. Klicken Sie entweder auf die **codierte Lizenz** oder die Option für nicht **codierte Lizenzen** . Verwenden Sie die codierte Lizenzoption mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows-Konfigurations-Designer verwenden, um ein Bereitstellungspaket zu erstellen. Wählen Sie die Option "nicht codierte Lizenz" aus, wenn Sie die Bereitstellung von Bild Wartung und-Verwaltung (DISM) oder Bereitstellungslösungen basierend auf Imaging verwenden, einschließlich des Microsoft Deployment Toolkit (MDT).
7. Klicken Sie auf **generieren** , um die Lizenz für die APP zu generieren und herunterzuladen. Stellen Sie sicher, dass Sie den Pfad der Lizenzdatei notieren, da dies später in diesem Artikel erforderlich ist.

>[!NOTE]
>Wenn Sie eine APP für die Offlineverwendung herunterladen, beispielsweise die Surface-APP, sehen Sie möglicherweise einen Abschnitt unten auf der Seite mit der Bezeichnung **erforderliche Frameworks**. Auf Ihren Zielcomputern müssen die Frameworks installiert sein, damit die app ausgeführt werden kann, daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (entweder x86 oder x64) wiederholen und Sie auch im Rahmen ihrer Windows-Bereitstellung, die weiter unten in diesem Artikel erläutert wird, einbeziehen.

Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-app.

![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*Abbildung5. Erforderliche Frameworks für die Surface-App*

>[!NOTE]
>Die Versionsnummern der Surface-APP und die erforderlichen Frameworks ändern sich, wenn die Apps aktualisiert werden. Überprüfen Sie, ob die neueste Version der Surface-APP und die einzelnen Frameworks in Microsoft Store for Business erhältlich sind. Verwenden Sie immer die Surface-APP und die empfohlenen Framework-Versionen, wie Sie von Microsoft Store für Unternehmen bereitgestellt werden. Das verwenden veralteter Frameworks oder fehlerhafter Versionen kann zu Fehlern oder Anwendungsabstürzen führen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-APP herunterzuladen:
1. Klicken Sie auf die Schaltfläche **herunterladen** unter **Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**. Dadurch wird die Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe heruntergeladen. AppX-Datei in den angegebenen Ordner.
2. Klicken Sie auf die Schaltfläche **herunterladen** unter **Microsoft. net. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe**. Dadurch wird die Datei Microsoft. net. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe. AppX in den angegebenen Ordner heruntergeladen.

>[!NOTE]
>Für Surface-Geräte ist nur die 64-Bit-Version (x64) jedes Frameworks erforderlich. Surface-Geräte sind native 64-Bit-UEFI-Geräte und nicht mit 32-Bit-Versionen von Windows kompatibel, für die 32-Bit-Frameworks erforderlich sind. 

## Installieren der Surface-App auf Ihrem Computer mit PowerShell
Mit dem folgenden Verfahren wird die Surface-App auf Ihrem Computer bereitgestellt und für alle auf dem Computer erstellten Benutzerkonten verfügbar gemacht.
1. Laden Sie die Oberfläche-App-AppxBundle und-Lizenzdatei herunter, und verwenden Sie das Verfahren, das in diesem Artikel im Abschnitt [herunterladen der Surface-App aus einem Microsoft Store for Business-Konto](#download-surface-app-from-a-microsoft-store-for-business-account) beschrieben wird. 
2. Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.

    >[!NOTE]
    >Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der app.
    
3. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Wo `<DownloadPath>` befindet sich der Ordner, in den Sie die AppxBundle-und Lizenzdatei aus dem Microsoft Store for Business-Konto heruntergeladen haben?

    Wenn Sie beispielsweise die Dateien nach c:\temp heruntergeladen haben, lautet der Befehl, den Sie ausführen, wie folgt:
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
