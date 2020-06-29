---
title: Setup-Arbeitsblatt (Surface Hub)
description: Wenn Sie die Vorab-Einrichtung abgeschlossen haben und bereit für das erste Einrichten von Microsoft Surface Hub sind, stellen Sie sicher, dass Sie alle in diesem Abschnitt aufgeführten Informationen zur Hand haben.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: Setup-Arbeitsblatt, Vorab-Einrichtung, erste Einrichtung
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833853"
---
# <span data-ttu-id="132d0-104">Setup-Arbeitsblatt (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="132d0-104">Setup worksheet (Surface Hub)</span></span>


<span data-ttu-id="132d0-105">Wenn Sie die Vorab-Einrichtung abgeschlossen haben und bereit für das erste Einrichten von Microsoft Surface Hub sind, stellen Sie sicher, dass Sie alle in diesem Abschnitt aufgeführten Informationen zur Hand haben.</span><span class="sxs-lookup"><span data-stu-id="132d0-105">When you've finished pre-setup and are ready to start first-time setup for your Microsoft Surface Hub, make sure you have all the information listed in this section.</span></span>

<span data-ttu-id="132d0-106">Füllen Sie für jedes zu konfigurierende Surface Hub eine Liste aus. Einige Informationen können für alle Surface Hubs verwendet werden, z.B. die Proxyinformationen oder Domänenanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="132d0-106">You should fill out one list for each Surface Hub you need to configure, although some information can be used on all Surface Hubs, like the proxy information or domain credentials.</span></span> <span data-ttu-id="132d0-107">Einige dieser Informationen sind ggf. nicht erforderlich, je nachdem, wie Sie das Gerät konfigurieren möchten oder je nach Konfiguration der Infrastrukturumgebung Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="132d0-107">Some of this information may not be needed, depending on how you've decided to configure your device, or depending on how the environment is configured for your organization's infrastructure.</span></span>

<table>
<tr>
<th><span data-ttu-id="132d0-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="132d0-108">Property</span></span></th>
<th><span data-ttu-id="132d0-109">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="132d0-109">What this is used for</span></span></th>
<th><span data-ttu-id="132d0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="132d0-110">Example</span></span></th>
<th><span data-ttu-id="132d0-111">Tatsächlicher Wert</span><span class="sxs-lookup"><span data-stu-id="132d0-111">Actual value</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-112">Proxyinformationen</span><span class="sxs-lookup"><span data-stu-id="132d0-112">Proxy information</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-113">Wenn Sie einen Proxy für Netzwerk- und/oder Internetzugriff verwenden, müssen Sie ein Skript oder Server-/Portinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="132d0-113">If your network uses a proxy for network and/or Internet access, you must provide a script or server/port information.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-114">Proxyskript:</span><span class="sxs-lookup"><span data-stu-id="132d0-114">Proxy script:</span></span> <code>http://contoso/proxy.pa</code> </br>
- <span data-ttu-id="132d0-115">ODER</span><span class="sxs-lookup"><span data-stu-id="132d0-115">OR -</span></span> </br>
<span data-ttu-id="132d0-116">Server- und Portinformationen: 10.10.10.100, Port 80</span><span class="sxs-lookup"><span data-stu-id="132d0-116">Server and port info: 10.10.10.100, port 80</span></span>
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-117">Drahtlosnetzwerk-Anmeldeinformationen (Benutzername und Kennwort)</span><span class="sxs-lookup"><span data-stu-id="132d0-117">Wireless network credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-118">Wenn Sie Ihr Gerät per WLAN verbinden möchten und für Ihr Drahtlosnetzwerk Benutzeranmeldeinformationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="132d0-118">If you decide to connect your device to Wi-Fi, and your wireless network requires user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-119">admin1@contoso.com, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="132d0-119">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-120">Gerätekonto-Benutzerprinzipalname oder Domäne\Benutzername und Gerätekonto-Kennwort</span><span class="sxs-lookup"><span data-stu-id="132d0-120">Device account UPN or Domain\username and device account password</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-121">Dies sind der Benutzerprinzipalname (UPN) oder Domäne\Benutzername und das Kennwort für das Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="132d0-121">This is the User Principal Name (UPN) or the domain\username, and the password of the device account.</span></span> <span data-ttu-id="132d0-122">E-Mail-, Kalender-Funktionen und Skype for Business erfordern ein kompatibles Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="132d0-122">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span></p>
</td>
<td>
<p> <span data-ttu-id="132d0-123">Benutzerprinzipalname: ConfRoom15@contoso.com, #Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="132d0-123">UPN: ConfRoom15@contoso.com, #Passw0rd1</span></span> </br>
- <span data-ttu-id="132d0-124">ODER</span><span class="sxs-lookup"><span data-stu-id="132d0-124">OR -</span></span> <br> 
<span data-ttu-id="132d0-125">Domäne und Benutzername: CONTOSO\ConfRoom15, #Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="132d0-125">Domain and username: CONTOSO\ConfRoom15, #Passw0rd1</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-126">Microsoft Exchange Server für Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="132d0-126">Device account Microsoft Exchange server</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-127">Dies ist der Exchange-Server für das Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="132d0-127">This is the device account's Exchange server.</span></span>
<span data-ttu-id="132d0-128">E-Mail-, Kalender-Funktionen und Skype for Business erfordern ein kompatibles Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="132d0-128">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="132d0-129">Zu Nutzung von E-Mail und Kalender-Funktionen muss das Gerätekonto einen gültigen Exchange-Server aufweisen.</span><span class="sxs-lookup"><span data-stu-id="132d0-129">For mail and calendar to work, the device account must have a valid Exchange server.</span></span> <span data-ttu-id="132d0-130">Es wird versucht, diesen automatisch zu finden.</span><span class="sxs-lookup"><span data-stu-id="132d0-130">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-131">outlook.office365.com</span><span class="sxs-lookup"><span data-stu-id="132d0-131">outlook.office365.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-132">Session Initiation-Protokoll (SIP)-Adresse für Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="132d0-132">Device account Session Initiation Protocol (SIP) address</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-133">Hierbei handelt es sich um die Skype for Business-SIP-Adresse des Gerätekontos.</span><span class="sxs-lookup"><span data-stu-id="132d0-133">This is the device account's Skype for Business SIP address.</span></span>
<span data-ttu-id="132d0-134">E-Mail-, Kalender-Funktionen und Skype for Business erfordern ein kompatibles Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="132d0-134">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="132d0-135">Zur Nutzung von Skype for Business muss das Gerätekonto eine gültige SIP-Adresse aufweisen.</span><span class="sxs-lookup"><span data-stu-id="132d0-135">For Skype for Business to work, the device account must have a valid SIP address.</span></span> <span data-ttu-id="132d0-136">Es wird versucht, diesen automatisch zu finden.</span><span class="sxs-lookup"><span data-stu-id="132d0-136">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-137">sip: ConfRoom15@contoso.com</span><span class="sxs-lookup"><span data-stu-id="132d0-137">sip: ConfRoom15@contoso.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-138">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="132d0-138">Friendly name</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-139">Der Anzeigename des Geräts ist der Name, der beim Herstellen einer Drahtlosverbindung mit dem Surface-Hub angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="132d0-139">The friendly name of the device is the broadcast name that people will see when they try to wirelessly connect to the Surface Hub.</span></span> <span data-ttu-id="132d0-140">Der Name wird gut sichtbar auf dem Bildschirm des Surface Hub angezeigt.</span><span class="sxs-lookup"><span data-stu-id="132d0-140">This name will be displayed prominently on the Surface Hub's screen.</span></span>
<span data-ttu-id="132d0-141">Es wird empfohlen, einen einprägsamen und aussagekräftigen Anzeigename auszuwählen, sodass die Benutzer beim Herstellen einer Verbindung mehrere Surface Hubs voneinander unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="132d0-141">We suggest that the friendly name you choose is recognizable and unique so that people can distinguish one Surface Hub from another when trying to connect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-142">Konferenzraum 15</span><span class="sxs-lookup"><span data-stu-id="132d0-142">Conference Room 15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-143">Gerätename</span><span class="sxs-lookup"><span data-stu-id="132d0-143">Device name</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-144">Der Gerätename ist der Name, der zum Beitreten zu einer Domäne verwendet wird, und die Kennung für die Registrierung des Geräts bei einem MDM-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="132d0-144">The device name is the name that will be used for domain join, and is the identity you will see in your MDM provider if the device is enrolled into MDM.</span></span>
<span data-ttu-id="132d0-145">Der gewählte Gerätename muss sich von den Namen aller anderen Geräte in der Active Directory-Domäne unterscheiden (wenn Sie das Gerät einer Domäne hinzufügen möchten).</span><span class="sxs-lookup"><span data-stu-id="132d0-145">The device name you choose must not be the same name as any other device on the user’s Active Directory domain (if you decide to domain join the device).</span></span> <span data-ttu-id="132d0-146">Das Gerät kann der Domäne nicht hinzugefügt werden, wenn der Name nicht eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="132d0-146">The device cannot join the domain if its name is not unique.</span></span>
</p>
</td>
<td>
<p><span data-ttu-id="132d0-147">Konfraum15</span><span class="sxs-lookup"><span data-stu-id="132d0-147">confroom15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="132d0-148">WENN SIE AZURE AD BEITRETEN</span><span class="sxs-lookup"><span data-stu-id="132d0-148">IF YOU'RE JOINING AZURE AD</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-149">Azure AD-Mandanten-Anmeldeinformationen (Benutzername und Kennwort)</span><span class="sxs-lookup"><span data-stu-id="132d0-149">Azure AD tenant user credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-150">Wenn Sie Personen in Ihrer Azure Active Directory (Azure AD)-Organisation Administratorberechtigungen für das Gerät zuweisen möchten, müssen Sie Azure AD beitreten.</span><span class="sxs-lookup"><span data-stu-id="132d0-150">If you decide to have people in your Azure Active Directory (Azure AD) organization become admins on the device, then you'll need to join Azure AD.</span></span>
<span data-ttu-id="132d0-151">Um Azure AD beizutreten, benötigen Sie gültige Benutzeranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="132d0-151">To join Azure AD, you will need valid user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-152">admin1@contoso.com, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="132d0-152">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="132d0-153">WENN SIE EINER DOMÄNE BEITRETEN</span><span class="sxs-lookup"><span data-stu-id="132d0-153">IF YOU'RE JOINING A DOMAIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-154">Domäne für den Beitritt</span><span class="sxs-lookup"><span data-stu-id="132d0-154">Domain to join</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-155">Hierbei handelt es sich um die Domäne, der Sie beitreten müssen, damit der Sicherheitsgruppe Ihrer Wahl Administratorberechtigungen für das Gerät zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="132d0-155">This is the domain you will need to join so that a security group of your choice can be admins for the device.</span></span>
<span data-ttu-id="132d0-156">Möglicherweise ist der vollqualifizierte Domänenname (FQDN) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="132d0-156">You may need the fully qualified domain name (FQDN).</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-157">contoso (Kurzname) ODER contoso.corp.com (FQDN)</span><span class="sxs-lookup"><span data-stu-id="132d0-157">contoso (short name) OR contoso.corp.com (FQDN)</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-158">Domänenkonto-Anmeldeinformationen (Benutzername und Kennwort)</span><span class="sxs-lookup"><span data-stu-id="132d0-158">Domain account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-159">Der Beitritt zu einer Domäne kann nur dann erfolgen, wenn die angegebenen Kontoanmeldeinformationen für den Beitritt zur Domäne ausreichen.</span><span class="sxs-lookup"><span data-stu-id="132d0-159">A domain can't be joined unless you provide sufficient account credentials to join the domain.</span></span> <span data-ttu-id="132d0-160">Nachdem Sie eine Domäne und Anmeldeinformationen für den Beitritt angegeben haben, kann die Sicherheitsgruppe Ihrer Wahl Einstellungen auf dem Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="132d0-160">Once you provide a domain to join and credentials to join the domain, then a security group of your choice can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-161">admin1, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="132d0-161">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-162">Alias für Administrator-Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="132d0-162">Admin security group alias</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-163">Dies ist eine Sicherheitsgruppe in Active Directory (AD). Alle Mitglieder dieser Sicherheitsgruppe können Einstellungen auf dem Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="132d0-163">This is a security group in your Active Directory (AD); any members of this security group can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-164">SurfaceHubAdmins</span><span class="sxs-lookup"><span data-stu-id="132d0-164">SurfaceHubAdmins</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="132d0-165">WENN SIE EINEN LOKALEN ADMINISTRATOR VERWENDEN</span><span class="sxs-lookup"><span data-stu-id="132d0-165">IF YOU'RE USING A LOCAL ADMIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-166">Kontoanmeldeinformationen für lokalen Administrator (Benutzername und Kennwort)</span><span class="sxs-lookup"><span data-stu-id="132d0-166">Local admin account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-167">Wenn Sie keiner Active Directory-Domäne oder Azure AD beitreten möchten, können Sie ein lokales Administratorkonto auf dem Gerät erstellen.</span><span class="sxs-lookup"><span data-stu-id="132d0-167">If you decide not to join an AD domain or Azure AD, you can create a local admin account on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-168">admin1, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="132d0-168">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="132d0-169">WENN ZERTIFIKATE ODER APPS INSTALLIERT WERDEN MÜSSEN</span><span class="sxs-lookup"><span data-stu-id="132d0-169">IF YOU NEED TO INSTALL CERTIFICATES OR APPS</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="132d0-170">USB-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="132d0-170">USB drive</span></span></p>
</td>
<td>
<p><span data-ttu-id="132d0-171">Wenn Sie vor der ersten Ausführung Zertifikate oder universelle Apps installieren möchten, führen Sie die Schritte unter <a href="provisioning-packages-for-certificates-surface-hub.md">Erstellen von Bereitstellungspaketen</a> aus.</span><span class="sxs-lookup"><span data-stu-id="132d0-171">If you know before first run that you want to install certificates or universal apps, follow the steps in <a href="provisioning-packages-for-certificates-surface-hub.md">Create provisioning packages</a>.</span></span> <span data-ttu-id="132d0-172">Die Bereitstellungspakete werden auf einem USB-Laufwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="132d0-172">Your provisioning packages will be created on a USB drive.</span></span></p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





