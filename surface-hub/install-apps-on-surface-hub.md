---
title: Installieren von Apps auf dem Microsoft Surface Hub
description: Administratoren können Apps entweder aus dem Microsoft Store oder dem Microsoft Store für Unternehmen installieren.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: Apps installieren, Microsoft Store, Microsoft Store für Unternehmen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 462b76451bd12547d1c1560054a51bb88c218f96
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833352"
---
# Installieren von Apps auf dem Microsoft Surface Hub

Sie können weitere Apps auf dem Surface Hub installieren, um Anforderungen Ihres Teams oder Ihrer Organisation zu erfüllen. Es gibt verschiedene Methoden zum Installieren von Apps, je nachdem, ob Sie eine App entwickeln und testen oder eine veröffentlichte App bereitstellen. In diesem Thema werden Methoden für das Installieren von Apps in beiden Szenarien beschrieben.

Einige wichtige Dinge, die Sie über Apps auf Surface Hub wissen müssen:
- Surface Hub führt ausschließlich [Apps für die universelle Windows-Plattform (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp) aus. Apps, die mit [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) erstellt wurden, führen Surface Hub nicht aus.
- Die Apps müssen für die [universelle Gerätefamilie](https://msdn.microsoft.com/library/windows/apps/dn894631) oder die Windows Team-Gerätefamilie entwickelt worden sein.
- Surface Hub unterstützt nur [Offline lizenzierte apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) aus dem [Microsoft Store for Business](https://businessstore.microsoft.com/store).
- Standardmäßig gilt, dass Apps Store-signiert sein müssen, um installiert werden zu können. Während Test und Entwicklung können Sie auch entwicklersignierte UWP-Apps ausführen, indem Sie das Gerät im Entwicklermodus ausführen.
- Wenn Sie eine APP an den Microsoft Store übermitteln, müssen Entwickler die Verfügbarkeit von Gerätefamilien und die Optionen für die Organisations Lizenzierung so einrichten, dass eine APP für die Ausführung auf Surface Hub verfügbar ist.
- Sie benötigen Administratoranmeldeinformationen, um Apps auf dem Surface Hub installieren zu können. Da das Gerät für die Verwendung an gemeinsam genutzten Orten wie Besprechungsräumen entwickelt wurde, können Benutzer nicht auf den Microsoft Store zugreifen, um Apps herunterzuladen und zu installieren.


## Entwickeln und Testen von Apps
Während Sie Ihre eigene App entwickeln, stehen Ihnen einige Optionen für das Testen von Apps auf Surface Hub zur Verfügung.

### Entwicklermodus
Standardmäßig führt Surface Hub ausschließlich UWP-Apps aus, die veröffentlicht und vom Microsoft Store signiert wurden. An den Microsoft Store übermittelte Apps unterliegen im Rahmen des [App-Zertifizierungsprozesses](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process) Sicherheits- und Compliancetests. Dies hilft, den Surface Hub vor schädlichen Apps zu schützen.
 
Durch das Aktivieren des Entwicklermodus können Sie auch entwicklersignierte UWP-Apps installieren.
 
> [!IMPORTANT]
> Nachdem der Entwicklermodus aktiviert wurde, müssen Sie den Surface Hub zurücksetzen, um den Entwicklermodus zu deaktivieren. Durch das Zurücksetzen des Geräts werden alle lokalen Benutzerdateien und Konfigurationen gelöscht. Anschließend wird Windows neu installiert.

**So aktivieren Sie den Entwicklermodus** 
1. Starten Sie auf dem Surface Hub **Einstellungen**.
2. Geben Sie bei Aufforderung die Geräteadministrator-Anmeldeinformationen ein.
3. Navigieren Sie zu **Update und Sicherheit** > **Für Entwickler**.
4. Wählen Sie **Entwicklermodus** aus, und akzeptieren Sie die Warnmeldung.

### Visual Studio
Während der Entwicklung können Sie Ihre App am einfachsten auf einem Surface Hub testen, indem Sie Visual Studio verwenden. Das Visual Studio-Feature für das Remotedebuggen hilft Ihnen, Probleme in Ihrer App zu erkennen, bevor sie umfassend bereitgestellt wird. Weitere Informationen finden Sie unter [Testen von Surface Hub-Apps mit Visual Studio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).

### Bereitstellungspaket
Sie können Visual Studio zum [Erstellen eines App-Pakets](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) für Ihre UWP-App verwenden, das mithilfe eines Testzertifikats signiert wurde. Anschließend verwenden Sie den Windows-Designer für die Imageerstellung und -konfiguration (ICD) zum Erstellen eines Bereitstellungspakets, das das App-Paket enthält. Weitere Informationen finden Sie unter [Erstellen von Bereitstellungspaketen](provisioning-packages-for-certificates-surface-hub.md).


## Übermitteln von Apps an den Microsoft Store
Wenn eine App zur Veröffentlichung bereit ist, müssen Entwickler diese an den Microsoft Store übermitteln und dort veröffentlichen. Weitere Informationen finden Sie unter [Veröffentlichen von Windows-Apps](https://developer.microsoft.com/store/publish-apps).

Während der App-Übermittlung müssen Entwickler die Optionen **Gerätefamilienverfügbarkeit** und **Unternehmenslizenzierung** festlegen, um sicherzustellen, dass die App für die Ausführung auf Surface Hub verfügbar ist.

**So legen Sie die Gerätefamilienverfügbarkeit fest**  
1. Navigieren Sie im [Windows Dev Center](https://developer.microsoft.com) zur Seite für Ihre App-Übermittlung.
2. Wählen Sie **Pakete** aus.
3. Wählen Sie in **Gerätefamilienverfügbarkeit** die folgenden Optionen aus:
    
    - **Windows 10 Team**
    - **Lassen Sie Microsoft entscheiden, ob die App zukünftigen Gerätefamilien zur Verfügung gestellt werden soll.**
  
![Abbildung der Seite für die Gerätefamilienverfügbarkeit – Teil des Vorgangs für die App-Übermittlung an den Microsoft Store.](images/device-family.png)  
    
Weitere Informationen finden Sie unter [Verfügbarkeit von Gerätefamilien](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).

**So legen Sie die Unternehmenslizenzierung fest**
1. Navigieren Sie im [Windows Dev Center](https://developer.microsoft.com) zur Seite für Ihre App-Übermittlung.
2. Wählen Sie **Preise und Verfügbarkeit** aus.
3. Wählen Sie unter Unternehmenslizenzierung **Getrennte (offline) Lizenzierungseinkäufe von Organisationen zulassen** aus.

![Abbildung mit der Seite für die Unternehmenslizenzierung – Teil des Vorgangs für die App-Übermittlung an den Microsoft Store.](images/sh-org-licensing.png)

> [!NOTE]
> **Meine App für Organisationen mit Store-verwalteter (online) Volumenlizenzierung und Verteilung verfügbar machen** ist standardmäßig aktiviert.

> [!NOTE]
> Entwickler können darüber hinaus branchenspezifische Apps direkt für Unternehmen veröffentlichen, ohne sie im Store allgemein zur Verfügung zu stellen. Weitere Informationen finden Sie unter [Verteilen von branchenspezifischen Apps an Unternehmen](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).

Weitere Informationen finden Sie unter [Lizenzierungsoptionen für Unternehmen](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).


## Bereitstellen veröffentlichter Apps

Es gibt verschiedene Optionen zum Installieren von im Microsoft Store veröffentlichten Apps, je nachdem, ob Sie diese auf einigen Geräten evaluieren oder allgemein für Ihre Organisation bereitstellen möchten.

So installieren Sie veröffentlichte Apps
- Laden Sie die App mithilfe der Microsoft Store-App herunter, oder
- Laden Sie das App-Paket aus dem Microsoft Store für Unternehmen herunter, und verteilen Sie es mithilfe eines Bereitstellungspakets oder eines unterstützten MDM-Anbieters.

### Microsoft Store-App
Verwenden Sie die Microsoft Store-App auf dem Surface Hub, um Apps zu suchen und herunterzuladen, wenn Sie im Microsoft Store veröffentlichte Apps evaluieren möchten.

> [!NOTE]
> Das Verwenden der Microsoft Store-App wird nicht empfohlen, um Apps für Ihre Organisation umfassend bereitzustellen:
> - Um Apps herunterzuladen, müssen Sie sich mit einem Microsoft-Konto oder einem Organisationskonto an der Microsoft Store-App anmelden. Sie können ein Konto jedoch nur mit maximal 10Geräten gleichzeitig verknüpfen. Wenn Sie mehr als 10Surface Hubs besitzen, müssen Sie mehrere Konten erstellen oder zwischen App-Installationen Geräte aus dem Konto entfernen.
> - Um Apps zu installieren, müssen Sie sich auf jedem Surface Hub, den Sie besitzen, manuell an der Microsoft Store-App anmelden.

**So durchsuchen Sie den Microsoft Store auf Surface Hub** 
1. Starten Sie auf dem Surface Hub **Einstellungen**.
2. Geben Sie bei Aufforderung die Geräteadministrator-Anmeldeinformationen ein.
3. Navigieren Sie zu **Dieses Gerät** > **Apps und Features**.
4. Wählen Sie **Store öffnen** aus.

### Herunterladen von App-Paketen aus dem Microsoft Store für Unternehmen
Um das zum Installieren von Apps auf dem Surface Hub benötigte App-Paket herunterzuladen, navigieren Sie zum [Microsoft Store für Unternehmen](https://www.microsoft.com/business-store). Im Microsoft Store für Unternehmen können Sie Apps für Windows10-Geräte in Ihrer Organisation, einschließlich Surface Hub, suchen, kaufen und verwalten.
 
> [!NOTE]
> Zurzeit unterstützt Surface Hub nur offline lizenzierte Apps, die im Microsoft Store für Unternehmen verfügbar sind. App-Entwickler legen die Verfügbarkeit von Offlinelizenzen während des Übermittelns von Apps fest.

Suchen und kaufen Sie die gewünschte App, und laden Sie Folgendes herunter:
- Das offline lizenzierte App-Paket (ein AppX- oder Appxbundle-Paket)
- Die *unverschlüsselte* Lizenzdatei (wenn Sie Bereitstellungspakete zum Installieren der App verwenden)
- Die *verschlüsselte* Lizenzdatei (wenn Sie MDM zum Verteilen der App verwenden)
- Alle erforderlichen Abhängigkeitsdateien

Weitere Informationen finden Sie unter [Herunterladen einer offline lizenzierten App](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

### Bereitstellungspaket
Sie können die offline lizenzierten Apps, die Sie aus dem Microsoft Store für Unternehmen heruntergeladen haben, mithilfe von Bereitstellungspaketen manuell installieren, wenn Sie nur einige wenige Surface Hubs besitzen. Sie verwenden den Windows-Designer für die Imageerstellung und -konfiguration (ICD), um ein Bereitstellungspaket mit dem App-Paket und der *unverschlüsselten* Lizenzdatei zu erstellen, die Sie aus dem Microsoft Store für Unternehmen heruntergeladen haben. Weitere Informationen finden Sie unter [Erstellen von Bereitstellungspaketen](provisioning-packages-for-certificates-surface-hub.md).

### Unterstützte MDM-Anbieter
Um Apps für eine große Anzahl von Surface Hubs in Ihrer Organisation bereitzustellen, verwenden Sie einen unterstützten MDM-Anbieter. Die folgende Tabelle enthält die MDM-Anbieter, die das Bereitstellen von offline lizenzierten App-Paketen unterstützen.

| MDM-Anbieter                | Unterstützt offline lizenzierte App-Pakete |
|-----------------------------|----------------------------------------|
| Lokales MDM mit Configuration Manager (ab Version 1602) | Ja |
|
| MDM-Drittanbieter    | Stellen Sie sicher, dass Ihr MDM-Anbieter das Bereitstellen von offline lizenzierten App-Paketen unterstützt. |

**So stellen Sie apps Remote mithilfe von Microsoft Endpoint Configuration Manager bereit**

> [!NOTE]
> Diese Anweisungen basieren auf der aktuellen Verzweigung des Microsoft Endpoint Configuration Manager.

1. Registrieren Sie Ihre Surface Hubs für Configuration Manager. Weitere Informationen finden Sie unter [Registrieren eines Surface Hub bei MDM](manage-settings-with-mdm-for-surface-hub.md#enroll-into-mdm).
2. Laden Sie das offline lizenzierte App-Paket, die *verschlüsselte* Lizenzdatei und alle erforderlichen Abhängigkeitsdateien aus dem Microsoft Store für Unternehmen herunter. Weitere Informationen finden Sie unter [Herunterladen einer offline lizenzierten App](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app). Speichern Sie die heruntergeladenen Dateien im selben Ordner auf einer Netzwerkfreigabe.
3. Klicken Sie im Arbeitsbereich **Softwarebibliothek** der Konfigurations-Manager-Konsole auf **Übersicht** > **Anwendungsverwaltung** > **Anwendungen**.
4. Klicken Sie auf der Registerkarte **Start** in der Gruppe **Erstellen** auf **Anwendung erstellen**.
5. Aktivieren Sie auf der Seite **Allgemein** des **Assistenten zum Erstellen von Anwendungen** das Kontrollkästchen **Informationen zu dieser Anwendung automatisch anhand der Installationsdateien erkennen**.
6. Wählen Sie in der Dropdownliste **Typ** **Windows-App-Paket (*APPX, *APPXBUNDLE)** aus.
7. Geben Sie im Feld **Speicherort** den UNC-Pfad in der Form \\Server\Freigabe\\Dateiname für das offline lizenzierte App-Paket an, das Sie aus dem Microsoft Store für Unternehmen heruntergeladen haben. Alternativ können Sie auf **Durchsuchen** klicken, um das App-Paket zu suchen.
8. Überprüfen Sie auf der Seite **Informationen importieren** die importierten Informationen, und klicken Sie dann auf **Weiter**. Wenn notwendig, können Sie auf **Zurück** klicken, um Fehler zu korrigieren.
9. Geben Sie auf der Seite **Allgemeine Informationen** zusätzliche Details zur App an. Einige dieser Informationen wurden möglicherweise bereits ausgefüllt, wenn sie aus dem App-Paket automatisch abgerufen wurden.
10. Klicken Sie auf **Weiter**, überprüfen Sie die Anwendungsinformationen auf der Zusammenfassungsseite, und führen Sie dann den Assistenten zum Erstellen von Anwendungen aus. 
11. Erstellen Sie einen Bereitstellungstyp für die Anwendung. Weitere Informationen finden Sie unter [Erstellen von Bereitstellungstypen für die Anwendung](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).
12. Stellen Sie die Anwendung für Ihre Surface Hub-Geräte bereit. Weitere Informationen finden Sie unter [Bereitstellen von Anwendungen mit Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).
13. Wenn notwendig, können Sie die App aktualisieren, indem Sie ein neues Paket aus dem Microsoft Store für Unternehmen herunterladen und in Konfigurations-Manager eine Anwendungsrevision veröffentlichen. Weitere Informationen finden Sie unter [aktualisieren und Zurücksetzen von Anwendungen mit Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx). 

> [!NOTE] 
> Wenn Sie den Microsoft Endpoint Configuration Manager (Current Branch) verwenden, können Sie die obigen Schritte umgehen, indem Sie den Store for Business mit Configuration Manager verbinden. Auf diese Weise können Sie die Liste der apps, die Sie mit Configuration Manager gekauft haben, synchronisieren, diese in der Configuration Manager-Konsole anzeigen und wie jede andere APP bereitstellen. Weitere Informationen finden Sie unter [Verwalten von Apps aus dem Microsoft Store für Unternehmen mit Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).


## Zusammenfassung

Es gibt verschiedene Möglichkeiten, Apps auf dem Surface Hub zu installieren, je nachdem, ob Sie apps entwickeln, Apps auf einer kleinen Anzahl von Geräten evaluieren oder apps im Allgemeinen für Ihre Organisation bereitstellen. In der folgenden Tabelle werden die unterstützten Methoden zusammengefasst:

| Installationsmethode             | Entwickeln von Apps | Evaluieren von Apps auf <br> einigen wenigen Geräten | Allgemeine Bereitstellung von Apps <br> in Ihrer Organisation |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| Bereitstellungspaket       | X | X |   |
| Microsoft Store-App          |   | X |   |
| Unterstützte MDM-Anbieter     |   |   | X |

## Weitere Informationen

- [Blogbeitrag: Windows Store-Apps auf Surface Hub mit Intune bereitstellen](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## Verwandte Themen

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub-Administratorhandbuch](surface-hub-administrators-guide.md)

 

 





