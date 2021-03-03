---
title: Konfigurieren nicht globaler Administratorkonten auf Surface Hub 2S
description: In diesem Artikel wird beschrieben, wie Sie nicht globale Administratorkonten für die Verwaltung von Surface Hub 2S konfigurieren.
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
ms.openlocfilehash: e16e4f8bd4b2b253233fa9790987287cf17966c7
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385173"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a><span data-ttu-id="4f5eb-104">Konfigurieren nicht globaler Administratorkonten auf Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="4f5eb-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="4f5eb-105">Wenn Sie Surface Hub 2S einer Azure AD-Domäne beitreten, können Sie nicht globale Administratorkonten konfigurieren, die die Berechtigungen auf die Verwaltung der Einstellungen-App auf Surface Hub 2S beschränken.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="4f5eb-106">Auf diese Weise können Sie administratorberechtigungen nur für Surface Hub 2S festlegen und potenziell unerwünschten Administratorzugriff über eine gesamte Azure AD-Domäne hinweg verhindern.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="4f5eb-107">Bevor Sie beginnen, stellen Sie sicher, dass Surface Hub 2S mit Azure AD verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="4f5eb-108">Andern falls nicht, müssen Sie Surface Hub 2S zurücksetzen und das OOBE-Setupprogramm (Out-of-the-Box) abschließen, indem Sie die Option zum Beitritt zu Azure AD auswählen.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="4f5eb-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="4f5eb-109">Summary</span></span> 

<span data-ttu-id="4f5eb-110">Das Erstellen nicht globaler Administratorkonten umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="4f5eb-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="4f5eb-111">Erstellen Sie in Microsoft Intune eine Sicherheitsgruppe mit den Administratoren, die für die Verwaltung von Surface Hub 2S festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="4f5eb-112">Abrufen der Azure AD-Gruppen-SID mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="4f5eb-113">Erstellen Sie eine XML-Datei, die die Azure AD Group SID enthält.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="4f5eb-114">Erstellen Sie eine Sicherheitsgruppe, die die Surface Hub 2S-Geräte enthält, die von der nicht-globalen Gruppe "Administratoren Sicherheit" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="4f5eb-115">Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für die Sicherheitsgruppe, die Ihre Surface Hub 2S-Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="4f5eb-116">Erstellen von Azure AD-Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="4f5eb-116">Create Azure AD security groups</span></span>

<span data-ttu-id="4f5eb-117">Erstellen Sie zunächst eine Sicherheitsgruppe mit den Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="4f5eb-118">Erstellen Sie dann eine weitere Sicherheitsgruppe für Surface Hub-Geräte.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="4f5eb-119">Erstellen einer Sicherheitsgruppe für Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="4f5eb-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="4f5eb-120">Melden Sie sich über das [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)bei Intune an, wählen Sie Gruppen Neue Gruppe > und wählen Sie unter Gruppentyp \*\*\*\*  >  \*\*\*\* die Option **Sicherheit aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="4f5eb-121">Geben Sie einen Gruppennamen ein , z. B. **lokale Surface Hub-Administratoren,** und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Erstellen einer Sicherheitsgruppe für Hubadministratoren](images/sh-create-sec-group.png)

3. <span data-ttu-id="4f5eb-123">Öffnen Sie die Gruppe, wählen \*\*\*\* Sie **Mitglieder**aus, und wählen Sie Dann Mitglieder hinzufügen aus, um die Administratorkonten ein eingeben, die Sie als nicht globale Administratoren auf Surface Hub 2S festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="4f5eb-124">Weitere Informationen zum Erstellen von Gruppen in Intune finden Sie unter Hinzufügen von Gruppen zum [Organisieren von Benutzern und Geräten.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="4f5eb-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-2s-devices"></a><span data-ttu-id="4f5eb-125">Erstellen einer Sicherheitsgruppe für Surface Hub 2S-Geräte</span><span class="sxs-lookup"><span data-stu-id="4f5eb-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="4f5eb-126">Wiederholen Sie das vorherige Verfahren, um eine separate Sicherheitsgruppe für #A0 zu erstellen. Beispiel: **Surface Hub-Geräte**.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Erstellen einer Sicherheitsgruppe für Hubgeräte](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="4f5eb-128">Abrufen der Azure AD-Gruppen-SID mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f5eb-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="4f5eb-129">Starten Sie PowerShell mit erhöhten Kontoberechtigungen (**Als Administrator ausführen**) und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="4f5eb-130">Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="4f5eb-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="4f5eb-131">[Installieren des Azure PowerShell-Moduls](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="4f5eb-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="4f5eb-132">Melden Sie sich bei Ihrem Azure AD-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="4f5eb-133">Wenn Sie bei Ihrem Mandanten angemeldet sind, führen Sie das folgende Commandlet aus.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="4f5eb-134">Sie werden aufgefordert, "Geben Sie die Objekt-ID Ihrer Azure AD-Gruppe ein".</span><span class="sxs-lookup"><span data-stu-id="4f5eb-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="4f5eb-135">Wählen Sie in Intune die Gruppe aus, die Sie zuvor erstellt haben, und kopieren Sie die Objekt-ID, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Kopieren der Objekt-ID der Sicherheitsgruppe](images/sh-objectid.png)

6. <span data-ttu-id="4f5eb-137">Führen Sie das folgende Commandlet aus, um die SID der Sicherheitsgruppe zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="4f5eb-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="4f5eb-138">Fügen Sie die Object-ID in das PowerShell-Commandlet ein, drücken Sie **die EINGABETASTE,** und kopieren Sie dann die **Azure AD-Gruppen-SID** in einen Texteditor.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="4f5eb-139">Erstellen einer XML-Datei mit Azure AD Group SID</span><span class="sxs-lookup"><span data-stu-id="4f5eb-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="4f5eb-140">Kopieren Sie Folgendes in einen Text-Editor:</span><span class="sxs-lookup"><span data-stu-id="4f5eb-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="4f5eb-141">Ersetzen Sie die Platzhalter-SID (beginnend mit S-1-12-1) durch Ihre **Azure AD-Gruppen-SID,** und speichern Sie die Datei dann als XML. Beispiel: **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="4f5eb-142">Erstellen eines benutzerdefinierten Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="4f5eb-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="4f5eb-143">Wählen Sie im \*\*\*\* Endpunkt-Manager  >  **Gerätekonfigurationsprofile**  >  **Erstellen eines Profils aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="4f5eb-144">Wählen Sie unter Plattform **Windows 10 und höher aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="4f5eb-145">Wählen Sie unter Profil **die Option Benutzerdefiniert**aus, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="4f5eb-146">Fügen Sie einen Namen und eine Beschreibung hinzu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="4f5eb-147">Wählen **Sie unter**  >  **Konfigurationseinstellungen OMA-URI-Einstellungen**die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="4f5eb-148">Fügen Sie im Bereich Zeile hinzufügen einen Namen hinzu, und fügen Sie unter     **OMA-URI**die folgende Zeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="4f5eb-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="4f5eb-149">Wählen Sie unter Datentyp die Option **String XML aus,** und navigieren Sie zum Öffnen der IM vorherigen Schritt erstellten XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![Hochladen der lokalen Administrator-XML-Konfigurationsdatei](images/sh-local-admin-config.png)

7. <span data-ttu-id="4f5eb-151">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-151">Click **Save**.</span></span>
8. <span data-ttu-id="4f5eb-152">Klicken **Sie auf Gruppen auswählen, um die** Zuvor erstellte Sicherheitsgruppe **(Surface Hub-Geräte) ein-** und auszuwählen. [](#create-security-group-for-surface-hub-2s-devices)</span><span class="sxs-lookup"><span data-stu-id="4f5eb-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="4f5eb-153">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-153">Click **Next.**</span></span>
9. <span data-ttu-id="4f5eb-154">Fügen Sie unter Anwendbarkeitsregeln bei Bedarf eine Regel hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="4f5eb-155">Wählen Sie andernfalls **Weiter** aus, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="4f5eb-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="4f5eb-156">Weitere Informationen zu benutzerdefinierten Konfigurationsprofilen mithilfe von OMA-URI-Zeichenfolgen finden Sie unter [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="4f5eb-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub-2s"></a><span data-ttu-id="4f5eb-157">Nicht globale Administratoren, die Surface Hub 2S verwalten</span><span class="sxs-lookup"><span data-stu-id="4f5eb-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="4f5eb-158">Mitglieder der **Gruppe Lokale Surface Hub Admins** Security können sich jetzt bei der App "Einstellungen" auf Surface Hub 2S anmelden und Einstellungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="4f5eb-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
