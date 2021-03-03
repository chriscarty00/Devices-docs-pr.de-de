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
# <a name="create-surface-hub-2s-device-account"></a><span data-ttu-id="e5dcd-104">Erstellen des Gerätekontos für Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="e5dcd-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="e5dcd-105">Durch das Erstellen eines Surface Hub-Gerätekontos (auch als Raumpostfach bezeichnet) kann Surface Hub 2S Besprechungsanfragen empfangen, genehmigen oder ablehnen und an Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="e5dcd-106">Konfigurieren Sie das Gerätekonto während des Setups der Out-of-Box Experience (OOBE).</span><span class="sxs-lookup"><span data-stu-id="e5dcd-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="e5dcd-107">Bei Bedarf können Sie sie später ändern (ohne das OOBE-Setup zu durchf?nnen).</span><span class="sxs-lookup"><span data-stu-id="e5dcd-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="e5dcd-108">Sie können das Konto im Microsoft 365 Admin Center in Kombination mit Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e5dcd-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="e5dcd-109">**Konto über Admin Center erstellen.**</span><span class="sxs-lookup"><span data-stu-id="e5dcd-109">**Create account via Admin center**.</span></span> <span data-ttu-id="e5dcd-110">Um die Mindestanforderungen zu erfüllen, können Sie alles, was Sie für das Konto benötigen, direkt im [Microsoft 365 Admin Center konfigurieren.](https://admin.microsoft.com/AdminPortal)</span><span class="sxs-lookup"><span data-stu-id="e5dcd-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="e5dcd-111">Einige Features wie die direkte Freigabe von Whiteboards über die #A0 erfordern die Verwendung von PowerShell zum Konfigurieren von ActiveSync. Weitere Informationen finden Sie unter Aktivieren von [ActiveSync, wenn die Verwendung der E-Mail-App](#enable-activesync-if-use-of-email-app-is-required) auf dieser Seite erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="e5dcd-112">**Erstellen Eines Kontos über PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="e5dcd-113">Sie können PowerShell-Skripts verwenden, um das Erstellen mehrerer Gerätekonten zu erleichtern und bestimmte Features schnell zu konfigurieren, z. B.:</span><span class="sxs-lookup"><span data-stu-id="e5dcd-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="e5dcd-114">Kalenderverarbeitung für jedes Surface Hub-Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="e5dcd-115">Benutzerdefinierte automatische Antworten auf Planungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="e5dcd-116">Wenn die standardmäßige ActiveSync-Postfachrichtlinie bereits von einer anderen Person oder einem anderen Prozess geändert wurde, müssen Sie wahrscheinlich eine neue ActiveSync-Postfachrichtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="e5dcd-117">Sie können die Kontoeinrichtung überprüfen, indem Sie das unten aufgeführte [Kontoüberprüfungsskript](#account-verification-script) ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="e5dcd-118">Das Surface Hub-Gerätekonto unterstützt keine Verbundidentitätsanbieter (Federated Identity Providers, FIPs) von Drittanbietern und muss ein Standardmäßiges Active Directory- oder Azure Active Directory-Konto sein.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <a name="create-account-via-admin-center"></a><span data-ttu-id="e5dcd-119">Erstellen eines Kontos über das Admin Center</span><span class="sxs-lookup"><span data-stu-id="e5dcd-119">Create account via admin center</span></span>

1. <span data-ttu-id="e5dcd-120">Wechseln Sie im Microsoft 365 Admin Center zu **Ressourcen,** wählen Sie **Räume & Geräte** aus, und wählen Sie dann + Ressource hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="e5dcd-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="e5dcd-121">Geben Sie einen Namen und eine E-Mail-Adresse für das Gerätekonto an.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="e5dcd-122">Lassen Sie die verbleibenden Einstellungen im Standardzustand unverändert.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-122">Leave remaining settings unchanged in the default state.</span></span>

   ![Angeben eines Namens und einer E-Mail-Adresse](images/sh2-account2.png)

   ![Verbleibende Einstellungen im Standardzustand unverändert lassen](images/sh2-account3.png)

3. <span data-ttu-id="e5dcd-125">Legen Sie das Kennwort für das Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-125">Set the password for the device account.</span></span> <span data-ttu-id="e5dcd-126">Zum Festlegen des Kennworts wählen Sie **Benutzer** und dann **Aktive Benutzer aus.**</span><span class="sxs-lookup"><span data-stu-id="e5dcd-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="e5dcd-127">Suchen Sie nun nach dem neu erstellten Benutzer zum Festlegen des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="e5dcd-128">Stellen Sie **sicher, dass Sie bei** der ersten Anmeldung nicht die Option Benutzer das Kennwort ändern **auswählen.**</span><span class="sxs-lookup"><span data-stu-id="e5dcd-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Festlegen des Kennworts für das Gerätekonto](images/sh2-account4.png)

4. <span data-ttu-id="e5dcd-130">Weisen Sie den Raum mit einer Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="e5dcd-131">Es wird empfohlen, die Office 365-Besprechungsraumlizenz zuzuordnen, die das Konto für Microsoft Teams und Skype for Business automatisch aktiviert. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e5dcd-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![Zuweisen einer Office 365-Lizenz](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="e5dcd-133">Wenn Sie Skype for Business verwenden, müssen Sie das Setup über PowerShell abgeschlossen haben – Skype for Business-Kalender: [Festlegen](#set-calendar-auto-processing-skype-for-business-only) der automatischen Kalenderverarbeitung für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <a name="create-account-via-powershell"></a><span data-ttu-id="e5dcd-134">Erstellen eines Kontos über PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5dcd-134">Create account via PowerShell</span></span>

 <span data-ttu-id="e5dcd-135">Die Verwendung von PowerShell zum schnellen Automatisieren von Aufgaben auf Surface Hub erfordert nicht unbedingt PowerShell-Kenntnisse.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="e5dcd-136">Stellen Sie sicher, dass Sie die erforderlichen Setupvoraussetzungen erfüllt haben, bevor Sie die entsprechenden Skripts auf dieser Seite verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a><span data-ttu-id="e5dcd-137">Voraussetzungen für die Verwendung von PowerShell zum Verwalten von Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e5dcd-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="e5dcd-138">Starten Sie PowerShell mit erhöhten Kontoberechtigungen (**Als Administrator ausführen**) und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="e5dcd-139">Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="e5dcd-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="e5dcd-140">[Installieren des Azure PowerShell-Moduls](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="e5dcd-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <a name="connect-to-exchange-online-powershell"></a><span data-ttu-id="e5dcd-141">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5dcd-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a><span data-ttu-id="e5dcd-142">Erstellen eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="e5dcd-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a><span data-ttu-id="e5dcd-143">Festlegen der automatischen Kalenderverarbeitung (nur Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e5dcd-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a><span data-ttu-id="e5dcd-144">Aktivieren von ActiveSync, wenn die Verwendung der E-Mail-App erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="e5dcd-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="e5dcd-145">Die standardmäßige ActiveSync-Richtlinie funktioniert unverändert.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="e5dcd-146">Erstellen Sie andernfalls eine neue Richtlinie, und weisen Sie sie zu.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-146">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a><span data-ttu-id="e5dcd-147">Verbindung mit Azure AD herstellen</span><span class="sxs-lookup"><span data-stu-id="e5dcd-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a><span data-ttu-id="e5dcd-148">Zuweisen einer Lizenz</span><span class="sxs-lookup"><span data-stu-id="e5dcd-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a><span data-ttu-id="e5dcd-149">Suchen nach verfügbaren Lizenzen</span><span class="sxs-lookup"><span data-stu-id="e5dcd-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a><span data-ttu-id="e5dcd-150">Kontovalidierungsskript</span><span class="sxs-lookup"><span data-stu-id="e5dcd-150">Account verification script</span></span>

<span data-ttu-id="e5dcd-151">Nach dem Erstellen des Gerätekontos können Sie das folgende Überprüfungsskript ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="e5dcd-152">Dieses Skript überprüft ein zuvor erstelltes Gerätekonto und erstellt einen Zusammenfassenden Bericht.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="e5dcd-153">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5dcd-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="e5dcd-154">Details zu bestimmten Einstellungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5dcd-154">Details of specific settings will not be shown.</span></span>

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

## <a name="learn-more"></a><span data-ttu-id="e5dcd-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5dcd-155">Learn more</span></span>

- [<span data-ttu-id="e5dcd-156">Erstellen lokaler Konten für Surface Hub 2S mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5dcd-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)