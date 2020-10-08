---
title: Erstellen von Bereitstellungspaketen (Surface Hub)
description: Für Windows 10 können Einstellungen, die die Registrierung oder eine Konfigurationsdienstanbieter (configuration service provider, CSP) verwenden, mithilfe von Bereitstellungspaketen konfiguriert werden.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: Zertifikat hinzufügen, Bereitstellungspaket
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: ecbeca9f0910f1fa1ff2721bcf1b745195552ca2
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103799"
---
# Erstellen von Bereitstellungspaketen (Surface Hub)

In diesem Thema wird erläutert, wie Sie mit dem Windows Configuration Designer ein Bereitstellungspaket erstellen und auf Surface Hub-Geräte anwenden. Sie können Bereitstellungspakete für Surface Hub verwenden, um Zertifikate hinzuzufügen, UWP (Universelle Windows-Plattform)-Apps zu installieren und Richtlinien und Einstellungen anzupassen.

Sie können ein Bereitstellungspaket während der Erstausführungseinrichtung per USB-Speicherstick oder über die **Einstellungs-App** anwenden. 


## Vorteile
-   Konfigurieren Sie schnell die Geräte ohne Verwendung eines Mobile Gerätemanagement (MDM)-Anbieters.

-   Keine Netzwerkverbindung erforderlich.

-   Einfache Anwendung

[Erfahren Sie mehr über die Vorteile und Verwendungsmöglichkeiten von Bereitstellungspaketen.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## Anforderungen 

Sie benötigen Folgendes, um ein Bereitstellungspaket zu erstellen und auf einen Surface Hub anzuwenden:

-   Der Windows-Konfigurations-Designer, der aus dem Microsoft Store oder aus dem Windows 10 Assessment and Deployment Kit (ADK) installiert werden kann. [Erfahren Sie, wie Sie Windows-Konfigurations-Designer installieren.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   Ein USB-Stick.
-   Wenn Sie das Paket mithilfe der **Einstellungs-App** anwenden, benötigen Sie Geräteadministrator-Anmeldeinformationen.

Sie erstellen das Bereitstellungspaket auf einem PC mit Windows10, speichern das Paket auf einem USB-Laufwerk und stellen es dann für den Surface Hub bereit.


## Unterstützte Elemente für Surface Hub-Bereitstellungspakete

Mit dem **Bereitstellen von Surface Hub-Geräte** -Assistenten können Sie:

- In Active Directory, Azure Active Directory oder MDM registrieren. 
- Ein Geräteadministratorkonto erstellen 
- Anwendungen und Zertifikate hinzufügen
- Proxyeinstellungen konfigurieren
- Eine Konfigurationsdatei für Surface Hub hinzufügen

>[!WARNING]
>Sie müssen Windows-Konfigurations-Designer unter Windows10 ausführen, um die Azure Active Directory-Registrierung mit dem Assistenten zu konfigurieren.

Mit dem erweiterten Bereitstellungseditor können Sie diese Elemente zu den Bereitstellungspaketen für Surface Hub hinzufügen:

- **Richtlinien**: Surface Hub unterstützt eine Teilmenge der Richtlinien im [Konfigurationsdienstanbieter (CSP) für Richtlinien](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies). 
- **Einstellungen** – Sie können alle Einstellungen im [SurfaceHub-Konfigurationsdienstanbieter](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) konfigurieren.

>[!TIP]
> Verwenden Sie den Assistenten, um ein Paket mit allgemeinen Einstellungen zu erstellen, und wechseln Sie dann zum erweiterten Editor, um weitere Einstellungen hinzuzufügen.
>
>![Öffnen des erweiterten Editors](images/icd-simple-edit.png)

## Verwendung des Surface Hub-Bereitstellungsassistenten

Nachdem Sie den [Windows-Konfigurations-Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) installiert haben, können Sie ein Bereitstellungspaket erstellen.

### Erstellen des Bereitstellungspakets 

1. Öffnen Sie Windows-Konfigurations-Designer:
   - Geben Sie auf dem Startbildschirm oder im Suchbereich des Startmenüs „Windows-Konfigurations-Designer“ ein, und klicken Sie auf die Windows-Konfigurations-Designer-Verknüpfung, 
    
     oder
    
   - Wenn Sie Windows-Konfigurations-Designer aus dem ADK installiert haben, navigieren Sie zu `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (auf einem x64-Computer) oder `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (auf einem x86-Computer), und doppelklicken Sie anschließend auf **ICD.exe**.

2. Klicken Sie auf **Bereitstellen von Surface Hub-Geräten**.

3. Benennen Sie Ihr Projekt, und klicken Sie auf **Weiter**.

### Configure settings

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>To provision the device with a certificate, click <strong>Add a certificate</strong>. Enter a name for the certificate, and then browse to and select the certificate to be used.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings. Die Standardkonfiguration für Surface Hub ist es, Proxyeinstellungen automatisch zuerkennen, damit Sie <strong>Nein</strong> auswählen können, wenn Sie möchten. Wenn Ihre Infrastruktur jedoch zuvor die Verwendung eines Proxyservers erfordert hat und diese Anforderung beseitigt hat, können Sie ein Bereitstellungspaket verwenden, um Ihre Surface Hub-Geräte auf die Standardeinstellungen wiederherzustellen, indem Sie <strong>Ja</strong> und <strong>Einstellungen automatisch erkennen</strong> auswählen. </br></br>Wenn Sie auf <strong>Ja</strong> umschalten, können Sie auswählen, dass die Proxyeinstellungen automatisch erkannt werden, oder Sie können die Einstellungen manuell konfigurieren, indem Sie eine URL oder eine statische Proxyserveradresse in ein Setup-Skript eingeben. Sie können auch angeben, ob der Proxyserver für lokale Adressen verwendet werden soll, und Ausnahmen (Adressen, die Surface Hub eine Verbindung herstellen soll direkt und ohne Verwendung des Proxyservers) festlegen.  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Sie können das Gerät in Active Directory registrieren und eine Sicherheitsgruppe angeben, um die Einstellungs-App zu verwenden und in der Azure Active Directory zu registrieren, sodass globale Administratoren die Einstellungs-App verwenden oder ein lokales Administratorkonto auf dem Gerät erstellen können.</br></br>Um das Gerät in Active Directory zu registrieren, geben Sie die Anmeldeinformationen für ein Konto mit den geringsten Rechten an, um das Gerät mit der Domäne zu verknüpfen, und geben Sie die Sicherheitsgruppe an, um über die Administratoranmeldeinformationen für Surface Hub zu verfügen. Wenn ein Bereitstellungspaket, das ein Gerät in der Active Directory registriert, auf ein Surface Hub angewendet werden soll, das zurückgesetzt wurde, kann nur das gleiche Domänenkonto verwendet werden, wenn das aufgeführte Konto ein Domänenadministrator oder das gleiche Konto ist, das Surface Hub ursprünglich eingerichtet hatte. Otherwise, a different domain account must be used in the provisioning package.</br></br>Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>. Die Einstellung <strong>Maximale Anzahl von Geräten pro Benutzer</strong> in Ihrem Azure AD-Mandanten bestimmt, wie oft das Massen-Token im Assistenten verwendet werden kann. Um das Gerät in Azure AD zu registrieren, wählen Sie diese Option aus, und geben Sie einen aussagekräftigen Namen für das Massen-Token ein, das Sie vom Assistenten erhalten. Set an expiration date for the token (maximum is 30 days from the date you get the token). Click <strong>Get bulk token</strong>. In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password. Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</br></br>To create a local administrator account, select that option and enter a user name and password. </br></br><strong>Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days. If the password is not changed during that period, the account might be locked out and unable to sign in.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM. </br></br>Wenn Sie auf <strong>Ja</strong> umschalten, müssen Sie ein Servicekonto und das Kennwort oder den Fingerabdruck des Zertifikats, das berechtigt ist, das Gerät zu registrieren und auch die Art der Authentifizierung angeben. If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">Learn more about managing Surface Hub with MDM.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>You can install multiple Universal Windows Platform (UWP) apps in a provisioning package. For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>. </br></br><strong>Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub. If you include a Classic Win32 app, provisioning will fail. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>You don&#39;t configure any settings in this step. It provides instructions for including a configuration file that contains a list of device accounts. Die Konfigurationsdatei darf keine Spaltenüberschriften enthalten. Wenn eine Surface Hub-Konfigurationsdatei bei der Anwendung eines Bereitstellungspakets auf Surface-Hub auf dem USB-Laufwerk enthalten ist, können Sie das Konto und den Anzeigenamen für das Gerät aus der Datei auswählen. See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</br></br><strong>Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>You can set a password to protect your provisioning package. You must enter this password when you apply the provisioning package to a device.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

After you're done, click **Create**. Es dauert nur wenige Sekunden. Wenn das Paket erstellt wurde, wird der Speicherort des Pakets als Hyperlink am unteren Rand der Seite angezeigt.

## Konfigurationsdatei-Beispiel

Eine Konfigurationsdatei für Surface Hub enthält eine Liste der Gerätekonten, die Ihr Gerät verwenden kann, um mit Exchange und Skype for Business zu verbinden. Wenn Sie ein Bereitstellungspaket auf Surface Hub anwenden, können Sie eine Konfigurationsdatei an das Stammverzeichnis des USB-Speichersticks hinzufügen, und dann das gewünschte Konto für das Gerät auswählen. Die Konfigurationsdatei kann nur während der Einrichtung der Out-of-Box-Experience (OOBE) angewendet werden, und kann nur mithilfe von Bereitstellungspaketen erstellt, mit dem Windows-Konfigurations-Designer mit Windows10, Version 1703 veröffentlicht verwendet werden.

Verwenden Sie Microsoft Excel oder einen anderen CSV-Editor zum Erstellen einer CSV-Datei mit dem Namen `SurfaceHubConfiguration.csv`. Geben Sie in der Datei eine Liste von Gerätekonten und Namen im folgenden Format ein:

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>Da die Konfigurationsdatei die Kontokennwörter für Geräte im Nur-Text speichert, wird es empfohlen, die Kennwörter zu aktualisieren, nachdem Sie das Bereitstellungspaket auf Ihren Geräten angewendet haben. Sie können die [DeviceAccount Knoten](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) in der [Surface Hub-Konfigurationsdienstanbieter (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) verwenden, um die Kennwörter per MDM zu aktualisieren.


Im Folgenden finden Sie ein Beispiel von `SurfaceHubConfiguration.csv`. 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## Verwenden Sie erweiterte Bereitstellung.

Nachdem Sie den [Windows-Konfigurations-Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) installiert haben, können Sie ein Bereitstellungspaket erstellen.

### Erstellen des Bereitstellungspakets (erweitert)

1. Öffnen Sie Windows-Konfigurations-Designer:
   - Geben Sie auf dem Startbildschirm oder im Suchbereich des Startmenüs „Windows-Konfigurations-Designer“ ein, und klicken Sie auf die Windows-Konfigurations-Designer-Verknüpfung, 
    
     oder
    
   - Wenn Sie Windows-Konfigurations-Designer aus dem ADK installiert haben, navigieren Sie zu `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (auf einem x64-Computer) oder `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (auf einem x86-Computer), und doppelklicken Sie anschließend auf **ICD.exe**.

2. Klicken Sie auf **Erweiterte Bereitstellung**.
   
3. Name your project and click **Next**.

4. Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.

    ![ICD new project](images/icd-new-project.png)

5. In the project, under **Available customizations**, select **Common Team settings**.

    ![ICD common settings](images/icd-common-settings.png)


### Hinzufügen eines Zertifikats zum Paket
Sie können Bereitstellungspakete zum Installieren von Zertifikaten verwenden, mit denen sich das Gerät bei Microsoft Exchange authentifizieren kann.

> [!NOTE]
> Mit Bereitstellungspaketen können Zertifikate nur im Speicher des Geräts (lokaler Computer) und nicht im Benutzerspeicher installiert werden. Wenn es für Ihre Organisation erforderlich ist, dass Zertifikate im Benutzerspeicher installiert werden, verwenden Sie die mobile Geräteverwaltung (MDM) zum Bereitstellen dieser Zertifikate. Ausführliche Informationen finden Sie in der Dokumentation zur MDM-Lösung.

1. Wechseln Sie im Bereich **Verfügbare Anpassungen** zu **Laufzeiteinstellungen** > **Certificates** > **ClientCertificates**. 

2. Geben Sie einen **CertificateName** ein, und klicken Sie dann auf **Hinzufügen**. 

2. Geben Sie das **CertificatePassword** ein. 

3. Suchen Sie für **CertificatePath** das Zertifikat, und wählen Sie es aus. 

4. Legen Sie **ExportCertificate** auf **False** fest.

5. Wählen Sie für **KeyLocation** die Option **Software only** aus.


### Hinzufügen einer UWP (Universelle Windows-Plattform)-App zu Ihrem Paket
Vor dem Hinzufügen einer UWP-App zu einem Bereitstellungspaket benötigen Sie das App-Paket (entweder „.appx“ oder „.appxbundle“) und alle Abhängigkeitsdateien. Wenn Sie die App im Microsoft Store für Unternehmen erworben haben, benötigen Sie auch die *nicht codierte* App-Lizenz. Unter [Verteilen von Offline-Apps](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) erfahren Sie, wie Sie diese Elemente aus dem Microsoft Store für Unternehmen herunterladen.

1. Wechseln Sie im Bereich **Verfügbare Anpassungen** zu **Laufzeiteinstellungen** > **UniversalAppInstall** > **DeviceContextApp**.

2. Geben Sie einen **PackageFamilyName** für die App ein, und klicken Sie dann auf **Hinzufügen**. Verwenden Sie aus Gründen der Konsistenz den Paketfamiliennamen der App. If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license. Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.

3. For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).

4. Klicken Sie für **DependencyAppxFiles** auf **Durchsuchen**, um Abhängigkeiten für die App zu suchen und hinzuzufügen. Für den Surface Hub benötigen Sie nur die x64-Versionen dieser Abhängigkeiten.

Wenn Sie die App im Microsoft Store für Unternehmen erworben haben, müssen Sie dem Bereitstellungspaket auch die App-Lizenz hinzufügen.

1. Erstellen Sie eine Kopie der App-Lizenz, und benennen Sie sie unter Verwendung der Erweiterung **.ms-windows-store-license** um. So wird „Beispiel.xml“ beispielsweise zu „Beispiel.ms-windows-store-license“.

2. Wechseln Sie im ICD im Bereich **Verfügbare Anpassungen** zu **Laufzeiteinstellungen** > **UniversalAppInstall** > **DeviceContextAppLicense**.

3. Geben Sie eine **LicenseProductId** ein, und klicken Sie dann auf **Hinzufügen**. Verwenden Sie aus Gründen der Konsistenz die Lizenz-ID der App aus der App-Lizenz. Open the license file using a text editor. Then, in the \<License\> tag, use the value in the **LicenseID** attribute.

4. Select the new **LicenseProductId** node. Klicken Sie für **LicenseInstall** auf **Durchsuchen**, um die in Schritt1 umbenannte Lizenzdatei zu suchen und auszuwählen.


### Hinzufügen einer Richtlinie zum Paket
Surface Hub unterstützt eine Teilmenge der Richtlinien im [Konfigurationsdienstanbieter (CSP) für Richtlinien](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). Einige dieser Richtlinien können mit dem ICD konfiguriert werden.

1. Wechseln Sie im Bereich **Verfügbare Anpassungen** zu **Laufzeiteinstellungen** > **Policies**.

2. Wählen Sie einen der verfügbaren Richtlinienbereiche aus.

3. Wählen Sie die Richtlinie aus, die Sie dem Bereitstellungspaket hinzufügen möchten, und legen Sie sie fest.


### Hinzufügen von Surface Hub-Einstellungen zum Paket 

You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package. 

1. In the **Available customizations** pane, go to **Runtime settings** > **SurfaceHub**.

2. Select one of the available setting areas.

3. Wählen Sie die Einstellung aus, die Sie dem Bereitstellungspaket hinzufügen möchten, und legen Sie sie fest. 


## Erstellen des Pakets

1. Nachdem Sie das Bereitstellungspaket konfiguriert haben, klicken Sie im Menü **Datei** auf **Speichern**.

2. Lesen Sie den Warnhinweis, dass die Projektdateien möglicherweise vertrauliche Informationen enthalten, und klicken Sie auf **OK**.

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und das Bereitstellungspaket (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und löschen, wenn sie nicht mehr benötigt werden.

3. Klicken Sie im Menü **Exportieren** auf **Bereitstellungspaket**.

4. Ändern Sie den **Besitzer** in **IT-Administrator**, sodass die Priorität dieses Bereitstellungspakets höher eingestuft wird als die von Bereitstellungspaketen, die von anderen Quellen auf dieses Gerät angewendet wurden.

5. Legen Sie einen Wert für **Paketversion** fest, und wählen Sie dann **Weiter** aus.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

6. Optional: Sie können das Paket auch verschlüsseln und die Paketsignierung aktivieren.

    -   **Paketverschlüsselung aktivieren** – Wenn Sie diese Option auswählen, wird ein automatisch generiertes Kennwort auf dem Bildschirm angezeigt.

    -   **Paketsignierung aktivieren** – Wenn Sie diese Option auswählen, müssen Sie ein gültiges Zertifikat zum Signieren des Pakets auswählen. Sie können das Zertifikat angeben, indem Sie auf **Durchsuchen…** klicken und das Zertifikat zum Signieren des Pakets auswählen.

        > [!IMPORTANT]
        > Es wird empfohlen, ein vertrauenswürdiges Bereitstellungszertifikat in das Bereitstellungspaket einzuschließen. Wird das Paket für ein Gerät übernommen, wird das Zertifikat dem Systemspeicher hinzugefügt, und alle mit diesem Zertifikat signierten Pakete werden anschließend automatisch im Hintergrund übernommen. 

7. Klicken Sie auf **Weiter** , um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Erstellen gespeichert werden soll. Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.<p>
Klicken Sie optional auf **Durchsuchen** , um den Standardausgabespeicherort zu ändern.

8. Klicken Sie auf **Weiter**.

9. Klicken Sie auf **Erstellen** , um mit der Paketerstellung zu beginnen. Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.<p>
Wenn Sie den Build abbrechen müssen, klicken Sie auf **Abbrechen**. Dadurch wird der aktuelle Buildprozess abgebrochen, der Assistent geschlossen und wieder die **Customizations Page**angezeigt.

10. Falls der Build nicht erfolgreich verläuft, wird eine Fehlermeldung mit einem Link zum Projektordner angezeigt. Sie können die Fehlerursache anhand der Protokolle ermitteln. Nachdem Sie das Problem behoben haben, versuchen Sie, das Paket erneut zu erstellen.<p>
Wenn der Build erfolgreich ist, werden der Name des Bereitstellungspakets sowie das Ausgabeverzeichnis und Projektverzeichnis angezeigt.

    -   Sie können das Bereitstellungspaket ggf. erneut erstellen und einen anderen Pfad für das Ausgabepaket auswählen. Klicken Sie dazu auf **Zurück** , um den Namen und Pfad des Ausgabepakets zu ändern, und klicken Sie dann auf **Weiter** , um einen weiteren Build zu starten.
    
    -   Wenn Sie fertig sind, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen und zur **Customizations Page**zurückzukehren.

11. Wählen Sie den Link zum **Ausgabespeicherort** aus, um zum Speicherort des Pakets zu navigieren. Kopieren Sie die PPKG-Datei auf einen leeren USB-Speicherstick.


## Anwenden eines Bereitstellungspakets auf den Surface Hub

There are two options for deploying provisioning packages to a Surface Hub. [During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings). 


### Apply a provisioning package during first run

> [!IMPORTANT]
> During the first-run program, you can only use provisioning packages to install certificates. Use the **Settings** app to install apps and apply other settings.

1. Wenn Sie den Surface Hub zum ersten Mal aktivieren, zeigt das Programm für die Erstausführung die [**Seite „Hallo“**](first-run-program-surface-hub.md#first-page) an. Stellen Sie sicher, dass die Einstellungen richtig festgelegt sind, bevor Sie fortfahren.

2. Schließen Sie den USB-Speicherstick, auf dem die PPKG-Datei enthalten ist, an den Surface Hub an. Wenn das Paket im Stammverzeichnis des Laufwerks enthalten ist, wird es vom Programm für die Erstausführung erkannt, und Sie werden gefragt, ob Sie das Gerät einrichten möchten. Wählen Sie **Einrichten** aus.

    ![Gerät einrichten?](images/provisioningpackageoobe-01.png)

3. Im nächsten Bildschirm werden Sie aufgefordert, eine Bereitstellungsquelle auszuwählen. Wählen Sie **Wechselmedien** aus, und tippen Sie auf **Weiter**.

    ![Dieses Gerät bereitstellen](images/provisioningpackageoobe-02.png)
    
4. Wählen Sie das anzuwendende Bereitstellungspaket („\*.ppkg“) aus, und tippen Sie auf **Weiter**. Beachten Sie, dass Sie bei der ersten Ausführung nur ein Paket installieren können.

    ![Paket auswählen](images/provisioningpackageoobe-03.png)

5. Im Programm für die Erstausführung wird eine Zusammenfassung der Änderungen angezeigt, die vom Bereitstellungspaket angewendet werden. Wählen Sie **Ja, hinzufügen** aus.  

    ![Vertrauen Sie diesem Paket?](images/provisioningpackageoobe-04.png)
    
6. Wenn eine Konfigurationsdatei im Stammverzeichnis des USB-Speichersticks enthalten ist, sehen Sie **Auswählen einer Konfiguration**. Das erste Gerätekonto in der Konfigurationsdatei wird mit einer Zusammenfassung der Kontoinformationen angezeigt, die mit dem Surface Hub angewendet werden.

    ![Konfiguration auswählen](images/ppkg-config.png)    

7. In **Auswählen einer Konfiguration**, wählen Sie den anzuwendenden Gerätenamen aus und klicken Sie dann auf **Weiter**.

    ![Wählen Sie einen Gerätenamen aus](images/ppkg-csv.png)
    
Die Einstellungen im Bereitstellungspaket werden auf das Gerät angewendet, und die Windows-Willkommensseite wird abgeschlossen. Nach dem Neustart des Geräts können Sie das USB-Flash-Laufwerk entfernen.

### Anwenden eines Pakets mithilfe von Einstellungen

1. Schließen Sie den USB-Speicherstick, auf dem die PPKG-Datei enthalten ist, an den Surface Hub an.

2. Starten Sie über den Surface Hub **Einstellungen**, und geben Sie die Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.

3. Navigieren Sie zu **Surface Hub** > **Geräteverwaltung**. Wählen Sie unter **Bereitstellungspakete** die Option **Bereitstellungspaket hinzufügen oder entfernen** aus.

4. Wählen Sie **Paket hinzufügen** aus.

5. Wählen Sie das Bereitstellungspaket und dann **Hinzufügen** aus. Sie müssen die Administratoranmeldeinformationen u. U. erneut eingeben, falls Sie dazu aufgefordert werden.

6. Eine Zusammenfassung der Änderungen wird angezeigt, die vom Bereitstellungspaket angewendet werden. Wählen Sie **Ja, hinzufügen** aus.


