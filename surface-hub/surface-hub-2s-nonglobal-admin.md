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
# <span data-ttu-id="d338c-104">Konfigurieren nicht globaler Administratorkonten auf Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="d338c-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="d338c-105">Wenn Sie Surface Hub 2S zu einer Azure AD-Domäne hinzufügen, können Sie nicht globale Administratorkonten konfigurieren, die die Berechtigungen für die Verwaltung der Einstellungs-APP auf Surface Hub 2S einschränken.</span><span class="sxs-lookup"><span data-stu-id="d338c-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="d338c-106">Auf diese Weise können Sie die Administratorberechtigungen für Surface Hub 2S nur bereichern und verhindern, dass potenziell unerwünschter Administrator auf eine gesamte Azure AD-Domäne zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d338c-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="d338c-107">Bevor Sie beginnen, stellen Sie sicher, dass Ihr Surface Hub 2S mit Azure AD verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d338c-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="d338c-108">Wenn dies nicht der Fall ist, müssen Sie Surface Hub 2S zurücksetzen und das Setupprogramm für das erstmalige out-of-the-Box (OOBE) durchführen, indem Sie die Option zum beitreten zu Azure AD auswählen.</span><span class="sxs-lookup"><span data-stu-id="d338c-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="d338c-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d338c-109">Summary</span></span> 

<span data-ttu-id="d338c-110">Der Vorgang zum Erstellen nicht globaler Administratorkonten umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="d338c-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="d338c-111">Erstellen Sie in Microsoft InTune eine Sicherheitsgruppe mit den Administratoren, die für die Verwaltung von Surface Hub 2S vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="d338c-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="d338c-112">Besorgen Sie sich eine Azure Ad Group-sid mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d338c-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="d338c-113">Erstellen einer XML-Datei mit Azure Ad Group-sid</span><span class="sxs-lookup"><span data-stu-id="d338c-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="d338c-114">Erstellen Sie eine Sicherheitsgruppe mit den Surface Hub 2S-Geräten, die von der Sicherheitsgruppe nicht-globale Administratoren verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d338c-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="d338c-115">Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil, das für die Sicherheitsgruppe mit ihren Surface Hub 2S-Geräten ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="d338c-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="d338c-116">Erstellen von Azure AD-Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="d338c-116">Create Azure AD security groups</span></span>

<span data-ttu-id="d338c-117">Erstellen Sie zunächst eine Sicherheitsgruppe mit den Administratorkonten.</span><span class="sxs-lookup"><span data-stu-id="d338c-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="d338c-118">Erstellen Sie dann eine weitere Sicherheitsgruppe für Surface-Hub-Geräte.</span><span class="sxs-lookup"><span data-stu-id="d338c-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="d338c-119">Erstellen einer Sicherheitsgruppe für Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="d338c-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="d338c-120">Registrieren Sie sich über das [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)bei InTune, wählen Sie **Gruppen**  >  **neu gruppieren** > aus, und wählen Sie unter Gruppentyp die Option **Sicherheit aus.**</span><span class="sxs-lookup"><span data-stu-id="d338c-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="d338c-121">Geben Sie einen Gruppennamen ein, beispielsweise **Surface Hub local-Administratoren** , und wählen Sie dann **erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="d338c-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Erstellen einer Sicherheitsgruppe für Hub-Administratoren](images/sh-create-sec-group.png)

3. <span data-ttu-id="d338c-123">Öffnen Sie die Gruppe, wählen Sie **Mitglieder**aus, und wählen Sie dann **Mitglieder hinzufügen** aus, um die Administrator Konten einzugeben, die Sie als nicht globale Administratoren auf Surface Hub 2S festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="d338c-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="d338c-124">Weitere Informationen zum Erstellen von Gruppen in InTune finden Sie unter  [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="d338c-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="d338c-125">Erstellen einer Sicherheitsgruppe für Surface Hub 2S-Geräte</span><span class="sxs-lookup"><span data-stu-id="d338c-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="d338c-126">Wiederholen Sie das vorherige Verfahren zum Erstellen einer separaten Sicherheitsgruppe für Hub-Geräte. beispielsweise **Surface-Hub-Geräte**.</span><span class="sxs-lookup"><span data-stu-id="d338c-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Erstellen einer Sicherheitsgruppe für Hub-Geräte](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="d338c-128">Abrufen einer Azure Ad Group-sid mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="d338c-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="d338c-129">Starten Sie PowerShell mit erhöhten Konto Privilegien (**als Administrator ausführen**), und stellen Sie sicher, dass Ihr System für die Ausführung von PowerShell-Skripts konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d338c-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="d338c-130">Weitere Informationen finden Sie unter [Informationen zu Ausführungsrichtlinien](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="d338c-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="d338c-131">[Installieren Sie das Azure PowerShell-Modul](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="d338c-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="d338c-132">Registrieren Sie sich bei Ihrem Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="d338c-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="d338c-133">Wenn Sie bei Ihrem Mandanten angemeldet sind, führen Sie die folgende Unifiedgroup aus.</span><span class="sxs-lookup"><span data-stu-id="d338c-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="d338c-134">Sie werden aufgefordert, "geben Sie die Objekt-ID Ihrer Azure Ad-Gruppe ein."</span><span class="sxs-lookup"><span data-stu-id="d338c-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="d338c-135">Wählen Sie in InTune die Gruppe aus, die Sie zuvor erstellt haben, und kopieren Sie die Objekt-ID, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d338c-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Objekt-ID der Sicherheitsgruppe kopieren](images/sh-objectid.png)

6. <span data-ttu-id="d338c-137">Führen Sie die folgende Unifiedgroup aus, um die SID der Sicherheitsgruppe abzurufen:</span><span class="sxs-lookup"><span data-stu-id="d338c-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="d338c-138">Fügen Sie die Objekt-ID in das PowerShell-Unifiedgroup ein, drücken **Sie die EINGABETASTE**, und kopieren Sie dann die **Azure Ad Group-sid** in einen Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="d338c-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="d338c-139">Erstellen einer XML-Datei mit Azure Ad Group-sid</span><span class="sxs-lookup"><span data-stu-id="d338c-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="d338c-140">Kopieren Sie Folgendes in einen Text-Editor:</span><span class="sxs-lookup"><span data-stu-id="d338c-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="d338c-141">Ersetzen Sie die Platzhalter-sid (beginnend mit S-1-12-1) durch ihre **Azure Ad Group-sid** , und speichern Sie die Datei dann als XML. Beispiel: **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="d338c-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="d338c-142">Erstellen eines benutzerdefinierten Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="d338c-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="d338c-143">Wählen Sie in Endpunkt-Manager die Option **Geräte**-  >  **Konfigurationsprofile**  >  **Profil erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="d338c-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="d338c-144">Wählen Sie unter Plattform **Windows 10 und höher aus.**</span><span class="sxs-lookup"><span data-stu-id="d338c-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="d338c-145">Wählen Sie unter Profil die Option **Benutzerdefiniert**aus, und wählen Sie dann **erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="d338c-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="d338c-146">Fügen Sie einen Namen und eine Beschreibung hinzu, und wählen Sie dann **weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d338c-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="d338c-147">Wählen Sie unter **Konfigurationseinstellungen**  >  **Oma-URI-Einstellungen**die Option **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="d338c-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="d338c-148">Fügen Sie im Bereich Zeile hinzufügen einen Namen hinzu, und fügen Sie unter     **Oma-URI**die folgende Zeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="d338c-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="d338c-149">Wählen Sie unter Datentyp die Option **Zeichenfolge XML** aus, und navigieren Sie zu der XML-Datei, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d338c-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![Upload der XML-Konfigurationsdatei des lokalen Administrators](images/sh-local-admin-config.png)

7. <span data-ttu-id="d338c-151">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d338c-151">Click **Save**.</span></span>
8. <span data-ttu-id="d338c-152">Klicken Sie auf **Gruppen zum einbeziehen auswählen,** und wählen Sie die Sicherheitsgruppe aus, die [Sie zuvor erstellt haben](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub Devices**).</span><span class="sxs-lookup"><span data-stu-id="d338c-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="d338c-153">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d338c-153">Click **Next.**</span></span>
9. <span data-ttu-id="d338c-154">Fügen Sie unter Anwendungsregeln auf Wunsch eine Regel hinzu.</span><span class="sxs-lookup"><span data-stu-id="d338c-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="d338c-155">Wählen Sie andernfalls **weiter** aus, und wählen Sie dann **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="d338c-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="d338c-156">Weitere Informationen zu benutzerdefinierten Konfigurationsprofilen mithilfe von Oma-URI-Zeichenfolgen finden Sie unter [Verwenden von benutzerdefinierten Einstellungen für Windows 10-Geräte in InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="d338c-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="d338c-157">Nicht globale Administratoren, die Surface Hub 2S verwalten</span><span class="sxs-lookup"><span data-stu-id="d338c-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="d338c-158">Mitglieder der Sicherheitsgruppe **Surface Hub Local Administrators** können sich jetzt bei der Einstellungs-APP auf Surface Hub 2S anmelden und Einstellungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="d338c-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
