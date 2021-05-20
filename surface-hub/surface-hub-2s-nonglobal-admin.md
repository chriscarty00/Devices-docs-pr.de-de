---
title: Konfigurieren nicht globaler Administratorkonten auf Surface Hub
description: In diesem Artikel wird beschrieben, wie Sie nicht globale Administratorkonten zum Verwalten von Surface Hub und Surface Hub 2S konfigurieren.
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
ms.openlocfilehash: 03359a7d8ea028a8094c064c1fcb82cc9a53fe6a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576765"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a><span data-ttu-id="96da3-104">Konfigurieren nicht globaler Administratorkonten auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="96da3-104">Configure non Global admin accounts on Surface Hub</span></span>

<span data-ttu-id="96da3-105">Das Windows 10 Team 2020 Update bietet Unterstützung für die Konfiguration nicht globaler Administratorkonten, die die Berechtigungen für die Verwaltung der Einstellungen-App auf Surface Hub Geräten einschränken, die einer Azure AD-Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="96da3-105">The Windows 10 Team 2020 Update adds support for configuring non Global admin accounts that limit permissions to management of the Settings app on Surface Hub devices joined to an Azure AD domain.</span></span> <span data-ttu-id="96da3-106">Auf diese Weise können Sie Administratorberechtigungen Surface Hub und potenziell unerwünschten Administratorzugriff über eine gesamte Azure AD-Domäne hinweg verhindern.</span><span class="sxs-lookup"><span data-stu-id="96da3-106">This enables you to scope admin permissions for Surface Hub only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="96da3-107">Bevor Sie beginnen, stellen Sie sicher, dass Surface Hub Azure AD und Intune automatisch registriert ist.</span><span class="sxs-lookup"><span data-stu-id="96da3-107">Before you begin, make sure your Surface Hub is joined to Azure AD and Intune auto-enrolled.</span></span> <span data-ttu-id="96da3-108">Wenn dies nicht der Surface Hub, müssen Sie das OOBE-Setupprogramm (Out-of-the-Box) zurücksetzen und die Option zum Beitritt zu Azure AD auswählen.</span><span class="sxs-lookup"><span data-stu-id="96da3-108">If not, you will need to reset Surface Hub and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="96da3-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="96da3-109">Summary</span></span> 

<span data-ttu-id="96da3-110">Das Erstellen nicht globaler Administratorkonten umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="96da3-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="96da3-111">Erstellen Microsoft Intune eine Sicherheitsgruppe mit den Administratoren, die für die Verwaltung von Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="96da3-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub.</span></span>
2. <span data-ttu-id="96da3-112">Abrufen der Azure AD-Gruppen-SID mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96da3-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="96da3-113">Erstellen Sie eine XML-Datei, die die Azure AD Group SID enthält.</span><span class="sxs-lookup"><span data-stu-id="96da3-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="96da3-114">Erstellen Sie eine Sicherheitsgruppe mit Surface Hub Geräte, die von der nicht-globalen Gruppe "Administratoren Sicherheit" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="96da3-114">Create a Security Group containing the Surface Hub devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="96da3-115">Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für die Sicherheitsgruppe, die Ihre Surface Hub enthält.</span><span class="sxs-lookup"><span data-stu-id="96da3-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="96da3-116">Erstellen von Azure AD-Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="96da3-116">Create Azure AD security groups</span></span>

<span data-ttu-id="96da3-117">Erstellen Sie zunächst eine Sicherheitsgruppe mit den Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="96da3-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="96da3-118">Erstellen Sie dann eine weitere Sicherheitsgruppe für Surface Hub Geräte.</span><span class="sxs-lookup"><span data-stu-id="96da3-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="96da3-119">Erstellen einer Sicherheitsgruppe für Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="96da3-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="96da3-120">Melden Sie sich über das [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)bei Intune an, wählen Sie Gruppen Neue Gruppe > und wählen Sie unter Gruppentyp \*\*\*\*  >  \*\*\*\* die Option **Sicherheit aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="96da3-121">Geben Sie einen Gruppennamen ein , z. **B. Surface Hub Lokalen Administratoren,** und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Erstellen einer Sicherheitsgruppe für Hubadministratoren](images/sh-create-sec-group.png)

3. <span data-ttu-id="96da3-123">Öffnen Sie die Gruppe, wählen \*\*\*\* Sie **Mitglieder**aus, und wählen Sie Dann Mitglieder hinzufügen aus, um die Administratorkonten ein eingeben, die Sie als nicht globale Administratoren auf Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="96da3-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub.</span></span> <span data-ttu-id="96da3-124">Weitere Informationen zum Erstellen von Gruppen in Intune finden Sie unter Hinzufügen von Gruppen zum [Organisieren von Benutzern und Geräten.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="96da3-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-devices"></a><span data-ttu-id="96da3-125">Erstellen einer Sicherheitsgruppe für Surface Hub Geräte</span><span class="sxs-lookup"><span data-stu-id="96da3-125">Create security group for Surface Hub devices</span></span>

1. <span data-ttu-id="96da3-126">Wiederholen Sie das vorherige Verfahren, um eine separate Sicherheitsgruppe für #A0 zu erstellen. Verwenden Sie **beispielsweise Surface Hub Geräte**.</span><span class="sxs-lookup"><span data-stu-id="96da3-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Erstellen einer Sicherheitsgruppe für Hubgeräte](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="96da3-128">Abrufen der Azure AD-Gruppen-SID mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="96da3-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="96da3-129">Starten Sie PowerShell mit erhöhten Kontoberechtigungen (**Als Administrator ausführen**) und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="96da3-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="96da3-130">Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="96da3-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="96da3-131">[Installieren Azure PowerShell Modul .](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="96da3-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="96da3-132">Melden Sie sich bei Ihrem Azure AD-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="96da3-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="96da3-133">Wenn Sie bei Ihrem Mandanten angemeldet sind, führen Sie das folgende Commandlet aus.</span><span class="sxs-lookup"><span data-stu-id="96da3-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="96da3-134">Sie werden aufgefordert, "Geben Sie die Objekt-ID Ihrer Azure AD-Gruppe ein".</span><span class="sxs-lookup"><span data-stu-id="96da3-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="96da3-135">Wählen Sie in Intune die Gruppe aus, die Sie zuvor erstellt haben, und kopieren Sie die Objekt-ID, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="96da3-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Kopieren der Objekt-ID der Sicherheitsgruppe](images/sh-objectid.png)

6. <span data-ttu-id="96da3-137">Führen Sie das folgende Commandlet aus, um die SID der Sicherheitsgruppe zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="96da3-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="96da3-138">Fügen Sie die Object-ID in das PowerShell-Commandlet ein, drücken Sie **die EINGABETASTE,** und kopieren Sie dann die **Azure AD-Gruppen-SID** in einen Texteditor.</span><span class="sxs-lookup"><span data-stu-id="96da3-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="96da3-139">Erstellen einer XML-Datei mit Azure AD Group SID</span><span class="sxs-lookup"><span data-stu-id="96da3-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="96da3-140">Kopieren Sie Folgendes in einen Text-Editor:</span><span class="sxs-lookup"><span data-stu-id="96da3-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > <span data-ttu-id="96da3-141">Entfernen Sie das Standardmäßige Administratormitglied nicht aus der XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="96da3-141">Do not remove the default Administrator member from the XML file.</span></span>

2. <span data-ttu-id="96da3-142">Ersetzen Sie die Platzhalter-SID (beginnend mit S-1-12-1) durch Ihre **Azure AD-Gruppen-SID,** und speichern Sie die Datei dann als XML. Beispiel: **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="96da3-142">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="96da3-143">Erstellen eines benutzerdefinierten Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="96da3-143">Create Custom configuration profile</span></span>

1. <span data-ttu-id="96da3-144">Wählen sie Endpoint Manager \*\*\*\*  >  **Gerätekonfigurationsprofile**  >  **Erstellen eines Profils aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-144">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="96da3-145">Wählen Sie unter Plattform **Windows 10 und höher aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-145">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="96da3-146">Wählen Sie unter Profil **die Option Benutzerdefiniert**aus, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-146">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="96da3-147">Fügen Sie einen Namen und eine Beschreibung hinzu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-147">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="96da3-148">Wählen **Sie unter Konfigurationseinstellungen**  >  **OMA-URI Einstellungen**die Option Hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-148">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="96da3-149">Fügen Sie im Bereich Zeile hinzufügen einen Namen hinzu, und fügen Sie unter     **OMA-URI**die folgende Zeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="96da3-149">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="96da3-150">Wählen Sie unter Datentyp die Option **String XML aus,** und navigieren Sie zum Öffnen der IM vorherigen Schritt erstellten XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="96da3-150">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![Hochladen der lokalen Administrator-XML-Konfigurationsdatei](images/sh-local-admin-config.png)

7. <span data-ttu-id="96da3-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="96da3-152">Click **Save**.</span></span>
8. <span data-ttu-id="96da3-153">Klicken **Sie auf Gruppen auswählen, um** die Zuvor erstellte Sicherheitsgruppe (Surface Hub) [](#create-security-group-for-surface-hub-devices) **ein- und auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="96da3-153">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="96da3-154">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96da3-154">Click **Next.**</span></span>
9. <span data-ttu-id="96da3-155">Fügen Sie unter Anwendbarkeitsregeln bei Bedarf eine Regel hinzu.</span><span class="sxs-lookup"><span data-stu-id="96da3-155">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="96da3-156">Wählen Sie andernfalls **Weiter** aus, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="96da3-156">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="96da3-157">Weitere Informationen zu benutzerdefinierten Konfigurationsprofilen mithilfe von OMA-URI-Zeichenfolgen finden Sie unter [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="96da3-157">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub"></a><span data-ttu-id="96da3-158">Nicht globale Administratoren, die Surface Hub</span><span class="sxs-lookup"><span data-stu-id="96da3-158">Non Global admins managing Surface Hub</span></span>

<span data-ttu-id="96da3-159">Mitglieder der gruppe **Surface Hub Lokale Administratoren** können sich jetzt bei der Einstellungen-App unter Surface Hub anmelden und Einstellungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="96da3-159">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub and manage settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96da3-160">Der Standardzugriff globaler Administratoren auf die Einstellungen-App wird entfernt (es sei denn, sie sind auch Mitglieder dieser neuen Sicherheitsgruppe).</span><span class="sxs-lookup"><span data-stu-id="96da3-160">The default access of global admins to the Settings app is removed (unless they are also members of this new security group).</span></span>
