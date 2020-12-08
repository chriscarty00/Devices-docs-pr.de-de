---
title: Konfigurieren nicht globaler Administratorkonten auf Surface Hub 2S
description: In diesem Artikel wird beschrieben, wie Sie nicht globale Administratorkonten konfigurieren, um Surface Hub 2S zu verwalten.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196804"
---
# Konfigurieren nicht globaler Administratorkonten auf Surface Hub 2S

Wenn Sie Surface Hub 2S zu einer Azure AD-Domäne hinzufügen, können Sie nicht globale Administratorkonten konfigurieren, die die Berechtigungen für die Verwaltung der Einstellungs-APP auf Surface Hub 2S einschränken. Auf diese Weise können Sie die Administratorberechtigungen für Surface Hub 2S nur bereichern und verhindern, dass potenziell unerwünschter Administrator auf eine gesamte Azure AD-Domäne zugreifen kann. Bevor Sie beginnen, stellen Sie sicher, dass Ihr Surface Hub 2S mit Azure AD verbunden ist. Wenn dies nicht der Fall ist, müssen Sie Surface Hub 2S zurücksetzen und das Setupprogramm für das erstmalige out-of-the-Box (OOBE) durchführen, indem Sie die Option zum beitreten zu Azure AD auswählen.

## Zusammenfassung 

Der Vorgang zum Erstellen nicht globaler Administratorkonten umfasst die folgenden Schritte: 

1. Erstellen Sie in Microsoft InTune eine Sicherheitsgruppe mit den Administratoren, die für die Verwaltung von Surface Hub 2S vorgesehen sind.
2. Besorgen Sie sich eine Azure Ad Group-sid mithilfe von PowerShell.
3. Erstellen einer XML-Datei mit Azure Ad Group-sid
4. Erstellen Sie eine Sicherheitsgruppe mit den Surface Hub 2S-Geräten, die von der Sicherheitsgruppe nicht-globale Administratoren verwaltet werden.
5. Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil, das für die Sicherheitsgruppe mit ihren Surface Hub 2S-Geräten ausgerichtet ist. 


## Erstellen von Azure AD-Sicherheitsgruppen

Erstellen Sie zunächst eine Sicherheitsgruppe mit den Administratorkonten. Erstellen Sie dann eine weitere Sicherheitsgruppe für Surface-Hub-Geräte.  

### Erstellen einer Sicherheitsgruppe für Administratorkonten

1. Registrieren Sie sich über das [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)bei InTune, wählen Sie **Gruppen**  >  **neu gruppieren** > aus, und wählen Sie unter Gruppentyp die Option **Sicherheit aus.** 
2. Geben Sie einen Gruppennamen ein, beispielsweise **Surface Hub local-Administratoren** , und wählen Sie dann **erstellen aus.** 

     ![Erstellen einer Sicherheitsgruppe für Hub-Administratoren](images/sh-create-sec-group.png)

3. Öffnen Sie die Gruppe, wählen Sie **Mitglieder**aus, und wählen Sie dann **Mitglieder hinzufügen** aus, um die Administrator Konten einzugeben, die Sie als nicht globale Administratoren auf Surface Hub 2S festlegen möchten. Weitere Informationen zum Erstellen von Gruppen in InTune finden Sie unter  [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

### Erstellen einer Sicherheitsgruppe für Surface Hub 2S-Geräte

1. Wiederholen Sie das vorherige Verfahren zum Erstellen einer separaten Sicherheitsgruppe für Hub-Geräte. beispielsweise **Surface-Hub-Geräte**. 

     ![Erstellen einer Sicherheitsgruppe für Hub-Geräte](images/sh-create-sec-group-devices.png) 

## Abrufen einer Azure Ad Group-sid mithilfe von PowerShell

1. Starten Sie PowerShell mit erhöhten Konto Privilegien (**als Administrator ausführen**), und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist. Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Installieren Sie das Azure PowerShell-Modul](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Registrieren Sie sich bei Ihrem Azure AD-Mandanten.

    ```powershell
    Connect-AzureAD
    ```

4. Wenn Sie bei Ihrem Mandanten angemeldet sind, führen Sie die folgende Unifiedgroup aus. Sie werden aufgefordert, "geben Sie die Objekt-ID Ihrer Azure Ad-Gruppe ein."

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. Wählen Sie in InTune die Gruppe aus, die Sie zuvor erstellt haben, und kopieren Sie die Objekt-ID, wie in der folgenden Abbildung dargestellt. 

     ![Objekt-ID der Sicherheitsgruppe kopieren](images/sh-objectid.png)

6. Führen Sie die folgende Unifiedgroup aus, um die SID der Sicherheitsgruppe abzurufen:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Fügen Sie die Objekt-ID in das PowerShell-Unifiedgroup ein, drücken **Sie die EINGABETASTE**, und kopieren Sie dann die **Azure Ad Group-sid** in einen Text-Editor. 

## Erstellen einer XML-Datei mit Azure Ad Group-sid

1. Kopieren Sie Folgendes in einen Text-Editor: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. Ersetzen Sie die Platzhalter-sid (beginnend mit S-1-12-1) durch ihre **Azure Ad Group-sid** , und speichern Sie die Datei dann als XML. Beispiel: **aad-local-admin.xml**. 

## Erstellen eines benutzerdefinierten Konfigurationsprofils

1. Wählen Sie in Endpunkt-Manager die Option **Geräte**-  >  **Konfigurationsprofile**  >  **Profil erstellen**aus. 
2. Wählen Sie unter Plattform **Windows 10 und höher aus.** Wählen Sie unter Profil die Option **Benutzerdefiniert**aus, und wählen Sie dann **erstellen aus.**
3. Fügen Sie einen Namen und eine Beschreibung hinzu, und wählen Sie dann **weiter aus.**
4. Wählen Sie unter **Konfigurationseinstellungen**  >  **Oma-URI-Einstellungen**die Option **Hinzufügen**aus.
5. Fügen Sie im Bereich Zeile hinzufügen einen Namen hinzu, und fügen Sie unter     **Oma-URI**die folgende Zeichenfolge hinzu: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. Wählen Sie unter Datentyp die Option **Zeichenfolge XML** aus, und navigieren Sie zu der XML-Datei, die Sie im vorherigen Schritt erstellt haben. 

     ![Upload der XML-Konfigurationsdatei des lokalen Administrators](images/sh-local-admin-config.png)

7. Klicken Sie auf **Speichern**.
8. Klicken Sie auf **Gruppen zum einbeziehen auswählen,** und wählen Sie die Sicherheitsgruppe aus, die [Sie zuvor erstellt haben](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub Devices**). Klicken Sie auf **Weiter**.
9. Fügen Sie unter Anwendungsregeln auf Wunsch eine Regel hinzu. Wählen Sie andernfalls **weiter** aus, und wählen Sie dann **Erstellen**aus.

Weitere Informationen zu benutzerdefinierten Konfigurationsprofilen mithilfe von Oma-URI-Zeichenfolgen finden Sie unter [Verwenden von benutzerdefinierten Einstellungen für Windows 10-Geräte in InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## Nicht globale Administratoren, die Surface Hub 2S verwalten

Mitglieder der Sicherheitsgruppe **Surface Hub Local Administrators** können sich jetzt bei der Einstellungs-APP auf Surface Hub 2S anmelden und Einstellungen verwalten.
