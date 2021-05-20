---
title: Bereitstellen der Surface-App Microsoft Store für Unternehmen oder Microsoft Store für Bildungseinrichtungen (Surface)
description: Erfahren Sie, wie Sie die Surface-App mit Microsoft Store für Unternehmen oder Microsoft Store für Bildungseinrichtungen hinzufügen und herunterladen sowie die Surface-App mit PowerShell und MDT installieren.
keywords: surface app, app, deployment, customize
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
ms.date: 4/16/2021
ms.openlocfilehash: c7a882859339ff3d7feeb685c62672bc57c301ec
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576525"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a>Bereitstellen der Surface-App mit Microsoft Store für Unternehmen und Education

**Betrifft**

- Surface Laptop 4
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


Die Surface-App ist eine Microsoft Store App, die die Steuerung vieler Surface-spezifischer Einstellungen und Optionen bietet, darunter: 

* Aktivieren oder Deaktivieren der Windows-Taste auf dem Surface-Gerät 
 

* Anpassen der Empfindlichkeit des Surface-Stifts 
 

* Anpassen der Tastenaktionen des Surface-Stifts 
 

* Aktivieren oder Deaktivieren der Audioerweiterungen des Surface-Geräts 
 

* Schneller Zugriff auf Supportdokumentation und -informationen für Ihr Gerät

Kunden, die Windows Update verwenden, erhalten normalerweise die Surface-App als Teil automatischer Updates. Wenn Ihre Organisation jedoch Bilder für die Bereitstellung auf Ihren Surface-Geräten vorbereitet, sollten Sie möglicherweise die Surface-App (früher als Surface Hub bezeichnet) in den Imageerstellungs- und Bereitstellungsprozess einbeigen, anstatt die Benutzer jedes einzelnen Geräts zum Herunterladen und Installieren der App aus dem Microsoft Store oder Ihrer Microsoft Store für Unternehmen zu Microsoft Store für Unternehmen. 

> [!NOTE]
> Dieser Artikel gilt nicht für Surface Pro X. Weitere Informationen finden Sie unter [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)

## <a name="surface-app-overview"></a>Übersicht über Surface-App

Die Surface-App ist als kostenloser Download von der [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) Benutzer können sie aus dem Microsoft Store herunterladen und installieren, aber wenn Ihre Organisation stattdessen Microsoft Store für Unternehmen verwendet, müssen Sie sie dem Inventar Ihres Speichers hinzufügen und möglicherweise die App als Teil Ihres Windows-Bereitstellungsprozesses hinzufügen. Diese Prozesse werden in diesem Artikel behandelt. Weitere Informationen zu Microsoft Store für Unternehmen finden Sie [unter Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/) im Windows TechCenter. 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a>Hinzufügen einer Surface-App zu Microsoft Store für Unternehmen Konto 

Bevor Benutzer eine App über das Microsoft Store für Unternehmen-Konto eines Unternehmens installieren oder bereitstellen können, müssen die gewünschten Apps zuerst für die Benutzer eines Unternehmens verfügbar gemacht und lizenziert werden. 

1. Wenn Sie dies noch nicht getan haben, erstellen Sie [ein Microsoft Store für Unternehmen Konto.](https://www.microsoft.com/business-store) 

2. Melden Sie sich am Portal an. 

3. Offlinelizenzierung aktivieren: Klicken Sie auf >Store **verwalten,** und aktivieren Sie dann das Kontrollkästchen Offline lizenzierte Apps für Personen anzeigen, die im Store einkaufen, wie in Abbildung 1 dargestellt. **** Weitere Informationen zu Microsoft Store für Unternehmen App-Lizenzierungsmodellen finden Sie unter [Apps in Microsoft Store für Unternehmen und Education](https://docs.microsoft.com/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![Kontrollkästchen Offlinelizenzen-Apps anzeigen](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Abbildung1. Aktivieren von Apps für die Offlineverwendung*

4. Fügen Sie Ihrem konto Microsoft Store für Unternehmen Surface-App hinzu, indem Sie folgendes Verfahren verwenden:

    * Klicken Sie auf **das Menü Geschäft.**
    
    * Geben Sie im Suchfeld **Surface-App**ein, und klicken Sie dann auf das Suchsymbol.
    
    * Nachdem die Surface-App in den Suchergebnissen angezeigt wurde, klicken Sie auf das Symbol der App.
    
    * Ihnen wird eine Auswahl angezeigt (wählen **Sie Online** oder **Offline**aus), wie in Abbildung 2 dargestellt.
    
      > [!div class="mx-imgBorder"]
      > ![Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App zu Ihrem Inventar hinzu.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Abbildung2. Wählen Sie den Offlinelizenzierungsmodus aus, und fügen Sie die App zu Ihrem Inventar hinzu.*
    
    * Klicken **Sie auf Offline,** um den Offlinelizenzierungsmodus auszuwählen.
    
    * Klicken **Sie auf App herunterladen,** um die App zu Ihrem Microsoft Store für Unternehmen hinzuzufügen. Wie in Abbildung 3 dargestellt, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Offline-Apps mithilfe eines Verwaltungstools bereitgestellt oder von der Inventarseite des Unternehmens in ihrem privaten Store heruntergeladen werden können.
    
      > [!div class="mx-imgBorder"]
      > ![Offline lizenziertes App-Bestätigungsfenster ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Abbildung 3. Offline lizenzierte App-Bestätigung*
      
    * Klicken Sie auf **OK**.

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a>Herunterladen der Surface-App aus Microsoft Store für Unternehmen Konto
Nachdem Sie dem Microsoft Store für Unternehmen im Offlinemodus eine App hinzugefügt haben, können Sie die App als AppxBundle zu einer Bereitstellungsfreigabe herunterladen und hinzufügen.

1. Melden Sie sich beim Microsoft Store für Unternehmen unter https://businessstore.microsoft.com an.

2. Klicken **Sie auf >Apps & verwalten.** Eine Liste aller Apps Ihres Unternehmens wird angezeigt, einschließlich der Surface-App, die Sie im Abschnitt [Add Surface app to a Microsoft Store für Unternehmen account](#add-surface-app-to-a-microsoft-store-for-business-account) dieses Artikels hinzugefügt haben.

3. Klicken **Sie unter Aktionen**auf die Auslassungspunkte (**...**), und klicken Sie dann auf Für **die Offlineverwendung** für die Surface-App herunterladen.

4. Wählen Sie die gewünschten **Plattform-** und **Architekturoptionen** aus der verfügbaren Auswahl für die ausgewählte App aus, wie in Abbildung 4 dargestellt.

    > [!div class="mx-imgBorder"]
    > ![Beispiel für das AppxBundle-Paket](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Abbildung 4. Herunterladen des AppxBundle-Pakets für eine App*
    
5. Klicken Sie **auf Herunterladen**. Das AppxBundle-Paket wird heruntergeladen. Achten Sie darauf, den Pfad der heruntergeladenen Datei zu notieren, da Sie dies später in diesem Artikel benötigen.

6. Klicken Sie entweder auf **die Option Codierte Lizenz** oder auf Nicht **codierte** Lizenz. Verwenden Sie die Option Codierte Lizenz mit Verwaltungstools wie Microsoft Endpoint Configuration Manager oder wenn Sie Windows Configuration Designer zum Erstellen eines Bereitstellungspakets verwenden. Wählen Sie die Option Nicht codierte Lizenz aus, wenn Sie Bereitstellungsimagewartung und -verwaltung (Deployment Image Servicing and Management, DISM) oder Bereitstellungslösungen basierend auf der Imageerstellung verwenden, einschließlich des Microsoft Deployment Toolkits (MDT).

7. Klicken **Sie auf Generieren,** um die Lizenz für die App zu generieren und herunterzuladen. Achten Sie darauf, den Pfad der Lizenzdatei zu notieren, da Sie dies später in diesem Artikel benötigen.

>[!NOTE]
>Wenn Sie eine App für die Offlineverwendung herunterladen, z. B. die Surface-App, wird möglicherweise ein Abschnitt unten auf der Seite mit der Bezeichnung **Erforderliche Frameworks angezeigt.** Auf Ihren Zielcomputern müssen die Frameworks installiert sein, damit die App ausgeführt werden kann. Daher müssen Sie möglicherweise den Downloadvorgang für jedes der erforderlichen Frameworks für Ihre Architektur (x86 oder x64) wiederholen und sie auch als Teil Ihrer Windows-Bereitstellung, die weiter später in diesem Artikel behandelt wird, enthalten.

Abbildung 5 zeigt die erforderlichen Frameworks für die Surface-App.

> [!div class="mx-imgBorder"]
> ![Erforderliche Frameworks für die Surface-App](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Abbildung5. Erforderliche Frameworks für die Surface-App*

>[!NOTE]
>Die Versionsnummern der Surface-App und die erforderlichen Frameworks ändern sich, sobald die Apps aktualisiert werden. Überprüfen Sie die neueste Version der Surface-App und jedes Framework in Microsoft Store für Unternehmen. Verwenden Sie immer die Surface-App und die empfohlenen Frameworkversionen, wie von Microsoft Store für Unternehmen. Die Verwendung veralteter Frameworks oder falscher Versionen kann zu Fehlern oder Anwendungsabstürzen führen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Frameworks für die Surface-App herunterzuladen:

1. Klicken Sie **unter** **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**auf die Schaltfläche Herunterladen. Dadurch wird Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe heruntergeladen. Appx-Datei in Den angegebenen Ordner.

2. Klicken Sie **unter** **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**auf die Schaltfläche Herunterladen. Dadurch wird die datei Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx in den angegebenen Ordner heruntergeladen.

>[!NOTE]
>Nur die 64-Bit-Version (x64) jedes Frameworks ist für Surface-Geräte erforderlich. Surface-Geräte sind systemeigene 64-Bit-UEFI-Geräte und nicht kompatibel mit 32-Bit-Versionen (x86) von Windows die 32-Bit-Frameworks erfordern würden. 

## <a name="install-surface-app-on-your-computer-with-powershell"></a>Installieren der Surface-App auf Ihrem Computer mit PowerShell
Das folgende Verfahren stellt die Surface-App auf Ihrem Computer bereit und stellt sie für alle Benutzerkonten zur Verfügung, die anschließend auf dem Computer erstellt wurden.

1. Laden Sie mithilfe des verfahrens, das im Abschnitt Herunterladen der [Surface-App](#download-surface-app-from-a-microsoft-store-for-business-account) aus einem Microsoft Store für Unternehmen-Konto dieses Artikels beschrieben wird, die Surface-App App AppxBundle und die Lizenzdatei herunter. 

2. Führen Sie eine PowerShell-Sitzung mit erhöhten Rechten aus.

    >[!NOTE]
    >Wenn Sie PowerShell nicht als Administrator ausführen, verfügt die Sitzung nicht über die erforderlichen Berechtigungen zum Installieren der App.
    
3. Kopieren Sie in der PowerShell-Sitzung mit erhöhten Rechten den folgenden Befehl, und fügen Sie ihn ein: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Wo `<DownloadPath>` befindet sich der Ordner, in dem Sie die AppxBundle- und Lizenzdatei aus dem Microsoft Store für Unternehmen heruntergeladen haben.

    Wenn Sie die Dateien beispielsweise in c:\Temp heruntergeladen haben, wird der folgende Befehl ausgeführt:
    
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

## <a name="install-surface-app-with-mdt"></a>Installieren der Surface-App mit MDT
Im folgenden Verfahren wird MDT verwendet, um die Installation der Surface-App zum Zeitpunkt der Bereitstellung zu automatisieren. Die App wird automatisch von MDT bereitgestellt, sodass Sie dieses Verfahren mit bereits vorhandenen Images ausführen können. Dies ist der empfohlene Prozess für die Bereitstellung der Surface-App als Teil einer Windows-Bereitstellung auf Surface-Geräten, da dadurch die plattformübergreifende Kompatibilität des Windows wird.

1. Laden Sie mithilfe des [weiter oben in diesem Artikel beschriebenen](#download-surface-app-from-a-microsoft-store-for-business-account)Verfahrens die Surface-App App AppxBundle und die Lizenzdatei herunter. 

2. Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**

3. Geben Sie **auf** der Seite Befehlsdetails **** des Assistenten für **** neue Anwendungen das Standardarbeitsverzeichnis an, und geben Sie für den Befehl den Dateinamen des AppxBundle wie folgt an:

   * Befehl:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Arbeitsverzeichnis: %DEPLOYROOT%\Applications\SurfaceApp

Damit die Surface-App auf dem Zielcomputer funktioniert, sind auch die weiter oben in diesem Artikel beschriebenen Frameworks erforderlich. Verwenden Sie das folgende Verfahren, um die für die Surface-App erforderlichen Frameworks in MDT zu importieren und als Abhängigkeiten zu konfigurieren.

1. Laden Sie mithilfe des weiter oben in diesem Artikel beschriebenen Verfahrens die Frameworkdateien herunter. Store framework in einem separaten Ordner.

2. Importieren Sie mithilfe des Assistenten für neue Anwendungen in der MDT Deployment Workbench die heruntergeladenen Dateien als neue **Anwendung mit Quelldateien.**

3. Geben Sie auf der Seite **Befehlsdetails** den Dateinamen der einzelnen heruntergeladenen Anwendungen in das **Feld Befehl** und das Standardarbeitsverzeichnis ein.

Verwenden Sie diesen Prozess, um die Frameworks als Abhängigkeiten der Surface-App zu konfigurieren:

1. Öffnen Sie die Eigenschaften der Surface-App in der MDT Deployment Workbench.

2. Klicken Sie **auf die** Registerkarte Abhängigkeiten, und klicken Sie dann auf **Hinzufügen**.

3. Aktivieren Sie das Kontrollkästchen für jedes Framework mit dem Namen, den Sie im Assistenten für neue Anwendungen angegeben haben.

Nach dem Import steht die Surface-App **** im Schritt Anwendungen des Assistenten für die Windows zur Auswahl. Sie können die Anwendung auch automatisch installieren, indem Sie sie in der Tasksequenz für die Bereitstellung wie folgt angeben:

1. Öffnen Sie die Tasksequenz für die Bereitstellung in der Deployment Workbench von MDT.

2. Fügen Sie dem Abschnitt **Status wiederherstellen** der Bereitstellung eine neue Aufgabe **Anwendung installieren** hinzu.

3. Wählen **Sie Installieren einer einzelnen Anwendung** aus, und geben Sie die Surface **App** als **zu installierende Anwendung an.**

Weitere Informationen zum Hinzufügen von Apps in Ihre Windows finden Sie unter [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
