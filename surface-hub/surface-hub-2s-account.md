---
title: Erstellen des Gerätekontos für Surface Hub 2S
description: Auf dieser Seite wird das Verfahren zum Erstellen des Surface Hub 2S-Gerätekontos beschrieben.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385223"
---
# <a name="create-surface-hub-2s-device-account"></a>Erstellen des Gerätekontos für Surface Hub 2S

Durch das Erstellen eines Surface Hub-Gerätekontos (auch als Raumpostfach bezeichnet) kann Surface Hub 2S Besprechungsanfragen empfangen, genehmigen oder ablehnen und an Besprechungen teilnehmen. Konfigurieren Sie das Gerätekonto während des Setups der Out-of-Box Experience (OOBE). Bei Bedarf können Sie sie später ändern (ohne das OOBE-Setup zu durchf?nnen).

Sie können das Konto im Microsoft 365 Admin Center in Kombination mit Windows PowerShell: 

- **Konto über Admin Center erstellen.** Um die Mindestanforderungen zu erfüllen, können Sie alles, was Sie für das Konto benötigen, direkt im [Microsoft 365 Admin Center konfigurieren.](https://admin.microsoft.com/AdminPortal) Einige Features wie die direkte Freigabe von Whiteboards über die #A0 erfordern die Verwendung von PowerShell zum Konfigurieren von ActiveSync. Weitere Informationen finden Sie unter Aktivieren von [ActiveSync, wenn die Verwendung der E-Mail-App](#enable-activesync-if-use-of-email-app-is-required) auf dieser Seite erforderlich ist.

- **Erstellen Eines Kontos über PowerShell**. Sie können PowerShell-Skripts verwenden, um das Erstellen mehrerer Gerätekonten zu erleichtern und bestimmte Features schnell zu konfigurieren, z. B.:
    - Kalenderverarbeitung für jedes Surface Hub-Gerätekonto.
    - Benutzerdefinierte automatische Antworten auf Planungsanforderungen.
    - Wenn die standardmäßige ActiveSync-Postfachrichtlinie bereits von einer anderen Person oder einem anderen Prozess geändert wurde, müssen Sie wahrscheinlich eine neue ActiveSync-Postfachrichtlinie erstellen und zuweisen.

> [!TIP]
> Sie können die Kontoeinrichtung überprüfen, indem Sie das unten aufgeführte [Kontoüberprüfungsskript](#account-verification-script) ausführen.

> [!NOTE]  
> Das Surface Hub-Gerätekonto unterstützt keine Verbundidentitätsanbieter (Federated Identity Providers, FIPs) von Drittanbietern und muss ein Standardmäßiges Active Directory- oder Azure Active Directory-Konto sein.

## <a name="create-account-via-admin-center"></a>Erstellen eines Kontos über das Admin Center

1. Wechseln Sie im Microsoft 365 Admin Center zu **Ressourcen,** wählen Sie **Räume & Geräte** aus, und wählen Sie dann + Ressource hinzufügen **aus.**

2. Geben Sie einen Namen und eine E-Mail-Adresse für das Gerätekonto an. Lassen Sie die verbleibenden Einstellungen im Standardzustand unverändert.

   ![Angeben eines Namens und einer E-Mail-Adresse](images/sh2-account2.png)

   ![Verbleibende Einstellungen im Standardzustand unverändert lassen](images/sh2-account3.png)

3. Legen Sie das Kennwort für das Gerätekonto. Zum Festlegen des Kennworts wählen Sie **Benutzer** und dann **Aktive Benutzer aus.** Suchen Sie nun nach dem neu erstellten Benutzer zum Festlegen des Kennworts. Stellen Sie **sicher, dass Sie bei** der ersten Anmeldung nicht die Option Benutzer das Kennwort ändern **auswählen.**

   ![Festlegen des Kennworts für das Gerätekonto](images/sh2-account4.png)

4. Weisen Sie den Raum mit einer Office 365-Lizenz zu. Es wird empfohlen, die Office 365-Besprechungsraumlizenz zuzuordnen, die das Konto für Microsoft Teams und Skype for Business automatisch aktiviert. ****

   ![Zuweisen einer Office 365-Lizenz](images/sh2-account5.png)


> [!NOTE]  
> Wenn Sie Skype for Business verwenden, müssen Sie das Setup über PowerShell abgeschlossen haben – Skype for Business-Kalender: [Festlegen](#set-calendar-auto-processing-skype-for-business-only) der automatischen Kalenderverarbeitung für dieses Konto. 

## <a name="create-account-via-powershell"></a>Erstellen eines Kontos über PowerShell

 Die Verwendung von PowerShell zum schnellen Automatisieren von Aufgaben auf Surface Hub erfordert nicht unbedingt PowerShell-Kenntnisse. Stellen Sie sicher, dass Sie die erforderlichen Setupvoraussetzungen erfüllt haben, bevor Sie die entsprechenden Skripts auf dieser Seite verwenden.

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a>Voraussetzungen für die Verwendung von PowerShell zum Verwalten von Surface Hub 

1. Starten Sie PowerShell mit erhöhten Kontoberechtigungen (**Als Administrator ausführen**) und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist. Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Installieren des Azure PowerShell-Moduls](https://docs.microsoft.com/powershell/azure/install-az-ps).


### <a name="connect-to-exchange-online-powershell"></a>Herstellen einer Verbindung mit Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a>Erstellen eines Postfachs

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a>Festlegen der automatischen Kalenderverarbeitung (nur Skype for Business)

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a>Aktivieren von ActiveSync, wenn die Verwendung der E-Mail-App erforderlich ist

 Die standardmäßige ActiveSync-Richtlinie funktioniert unverändert. Erstellen Sie andernfalls eine neue Richtlinie, und weisen Sie sie zu.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a>Verbindung mit Azure AD herstellen

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a>Zuweisen einer Lizenz

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a>Suchen nach verfügbaren Lizenzen

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a>Kontovalidierungsskript

Nach dem Erstellen des Gerätekontos können Sie das folgende Überprüfungsskript ausführen. Dieses Skript überprüft ein zuvor erstelltes Gerätekonto und erstellt einen Zusammenfassenden Bericht. Zum Beispiel:

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

Details zu bestimmten Einstellungen werden nicht angezeigt.

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## <a name="learn-more"></a>Weitere Informationen

- [Erstellen lokaler Konten für Surface Hub 2S mit PowerShell](surface-hub-2s-onprem-powershell.md)