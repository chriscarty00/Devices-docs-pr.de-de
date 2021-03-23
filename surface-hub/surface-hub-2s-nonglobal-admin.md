---
title: Konfigurieren nicht globaler Administratorkonten auf Surface Hub
description: In diesem Artikel wird beschrieben, wie Sie nicht globale Administratorkonten für die Verwaltung von Surface Hub und Surface Hub 2S konfigurieren.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/22/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: ceac8fc1b0e168b206d937197ef404990b8e40ae
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442899"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Konfigurieren nicht globaler Administratorkonten auf Surface Hub

Wenn Sie Surface Hub v1 oder Surface Hub 2S zu einer Azure AD-Domäne hinzufügen, können Sie nicht globale Administratorkonten konfigurieren, die Berechtigungen auf die Verwaltung der Einstellungen-App auf Surface Hub beschränken. Auf diese Weise können Sie administratorberechtigungen nur für Surface Hub festlegen und potenziell unerwünschten Administratorzugriff über eine gesamte Azure AD-Domäne hinweg verhindern. Bevor Sie beginnen, stellen Sie sicher, dass Ihr Surface Hub mit Azure AD verbunden ist. Andern falls nicht, müssen Sie Surface Hub zurücksetzen und das OOBE-Setupprogramm (Out-of-the-Box) abschließen, indem Sie die Option zum Beitritt zu Azure AD auswählen.

## <a name="summary"></a>Zusammenfassung 

Das Erstellen nicht globaler Administratorkonten umfasst die folgenden Schritte: 

1. Erstellen Sie in Microsoft Intune eine Sicherheitsgruppe mit den Administratoren, die für die Verwaltung von Surface Hub bestimmt sind.
2. Abrufen der Azure AD-Gruppen-SID mithilfe von PowerShell.
3. Erstellen Sie eine XML-Datei, die die Azure AD Group SID enthält.
4. Erstellen Sie eine Sicherheitsgruppe, die die Surface Hub-Geräte enthält, die von der nicht-globalen Gruppe "Administratoren Sicherheit" verwaltet werden.
5. Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für die Sicherheitsgruppe, die Ihre Surface Hub-Geräte enthält. 


## <a name="create-azure-ad-security-groups"></a>Erstellen von Azure AD-Sicherheitsgruppen

Erstellen Sie zunächst eine Sicherheitsgruppe mit den Administratorkonten. Erstellen Sie dann eine weitere Sicherheitsgruppe für Surface Hub-Geräte.  

### <a name="create-security-group-for-admin-accounts"></a>Erstellen einer Sicherheitsgruppe für Administratorkonten

1. Melden Sie sich über das [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)bei Intune an, wählen Sie Gruppen Neue Gruppe > und wählen Sie unter Gruppentyp ****  >  **** die Option **Sicherheit aus.** 
2. Geben Sie einen Gruppennamen ein , z. B. **lokale Surface Hub-Administratoren,** und wählen Sie dann **Erstellen aus.** 

     ![Erstellen einer Sicherheitsgruppe für Hubadministratoren](images/sh-create-sec-group.png)

3. Öffnen Sie die Gruppe, wählen **** Sie **Mitglieder**aus, und wählen Sie Dann Mitglieder hinzufügen aus, um die Administratorkonten ein eingeben, die Sie als nicht globale Administratoren auf Surface Hub festlegen möchten. Weitere Informationen zum Erstellen von Gruppen in Intune finden Sie unter Hinzufügen von Gruppen zum [Organisieren von Benutzern und Geräten.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-security-group-for-surface-hub-devices"></a>Erstellen einer Sicherheitsgruppe für Surface Hub-Geräte

1. Wiederholen Sie das vorherige Verfahren, um eine separate Sicherheitsgruppe für #A0 zu erstellen. Beispiel: **Surface Hub-Geräte**. 

     ![Erstellen einer Sicherheitsgruppe für Hubgeräte](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Abrufen der Azure AD-Gruppen-SID mithilfe von PowerShell

1. Starten Sie PowerShell mit erhöhten Kontoberechtigungen (**Als Administrator ausführen**) und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist. Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Installieren des Azure PowerShell-Moduls](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Melden Sie sich bei Ihrem Azure AD-Mandanten an.

    ```powershell
    Connect-AzureAD
    ```

4. Wenn Sie bei Ihrem Mandanten angemeldet sind, führen Sie das folgende Commandlet aus. Sie werden aufgefordert, "Geben Sie die Objekt-ID Ihrer Azure AD-Gruppe ein".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. Wählen Sie in Intune die Gruppe aus, die Sie zuvor erstellt haben, und kopieren Sie die Objekt-ID, wie in der folgenden Abbildung dargestellt. 

     ![Kopieren der Objekt-ID der Sicherheitsgruppe](images/sh-objectid.png)

6. Führen Sie das folgende Commandlet aus, um die SID der Sicherheitsgruppe zu erhalten:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Fügen Sie die Object-ID in das PowerShell-Commandlet ein, drücken Sie **die EINGABETASTE,** und kopieren Sie dann die **Azure AD-Gruppen-SID** in einen Texteditor. 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Erstellen einer XML-Datei mit Azure AD Group SID

1. Kopieren Sie Folgendes in einen Text-Editor: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. Ersetzen Sie die Platzhalter-SID (beginnend mit S-1-12-1) durch Ihre **Azure AD-Gruppen-SID,** und speichern Sie die Datei dann als XML. Beispiel: **aad-local-admin.xml**. 

## <a name="create-custom-configuration-profile"></a>Erstellen eines benutzerdefinierten Konfigurationsprofils

1. Wählen Sie im **** Endpunkt-Manager  >  **Gerätekonfigurationsprofile**  >  **Erstellen eines Profils aus.** 
2. Wählen Sie unter Plattform **Windows 10 und höher aus.** Wählen Sie unter Profil **die Option Benutzerdefiniert**aus, und wählen Sie dann **Erstellen aus.**
3. Fügen Sie einen Namen und eine Beschreibung hinzu, und wählen Sie dann **Weiter aus.**
4. Wählen **Sie unter**  >  **Konfigurationseinstellungen OMA-URI-Einstellungen**die Option **Hinzufügen aus.**
5. Fügen Sie im Bereich Zeile hinzufügen einen Namen hinzu, und fügen Sie unter     **OMA-URI**die folgende Zeichenfolge hinzu: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. Wählen Sie unter Datentyp die Option **String XML aus,** und navigieren Sie zum Öffnen der IM vorherigen Schritt erstellten XML-Datei. 

     ![Hochladen der lokalen Administrator-XML-Konfigurationsdatei](images/sh-local-admin-config.png)

7. Klicken Sie auf **Speichern**.
8. Klicken **Sie auf Gruppen auswählen, um die** Zuvor erstellte Sicherheitsgruppe **(Surface Hub-Geräte) ein-** und auszuwählen. [](#create-security-group-for-surface-hub-devices) Klicken Sie auf **Weiter**.
9. Fügen Sie unter Anwendbarkeitsregeln bei Bedarf eine Regel hinzu. Wählen Sie andernfalls **Weiter** aus, und wählen Sie dann **Erstellen aus.**

Weitere Informationen zu benutzerdefinierten Konfigurationsprofilen mithilfe von OMA-URI-Zeichenfolgen finden Sie unter [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## <a name="non-global-admins-managing-surface-hub"></a>Nicht globale Administratoren, die Surface Hub verwalten

Mitglieder der **Gruppe Lokale Surface Hub Admins** Security können sich jetzt bei der App "Einstellungen" auf Surface Hub anmelden und Einstellungen verwalten.
