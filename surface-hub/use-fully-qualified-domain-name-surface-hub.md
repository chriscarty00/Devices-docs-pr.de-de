---
title: Verwenden eines vollständig qualifizierten Domänennamens mit Surface Hub
description: Behandeln Sie allgemeine Probleme, u.a. Probleme bei der Einrichtung und Exchange ActiveSync-Fehler.
keywords:
- Behandeln von allgemeinen Problemen
- Probleme bei der Einrichtung
- Exchange ActiveSync-Fehler
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832656"
---
# <span data-ttu-id="47dee-106">Konfigurieren des Domänennamens für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="47dee-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="47dee-107">Es gibt einige Szenarien, in denen Sie den Domänennamen Ihres Skype for Business-Servers angeben müssen:</span><span class="sxs-lookup"><span data-stu-id="47dee-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="47dee-108">**Mehrere DNS-Suffixe**: Wenn Ihre Skype for Business-Infrastruktur zusammenhanglose Namespaces enthält, sodass mindestens ein Server ein DNS-Suffix besitzt, das nicht mit dem Suffix der Anmeldeadresse (SIP) für Skype for Business übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="47dee-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="47dee-109">**Unterschiedliche Suffixe für Skype for Business und Exchange**: Wenn das Suffix der Anmeldeadresse für Skype for Business vom Suffix der Exchange-Adresse abweicht, die für das Gerätekonto verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="47dee-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="47dee-110">**Arbeiten mit Zertifikaten** – große Organisationen mit lokalen Skype for Business-Servern verwenden häufig Zertifikate mit ihrer eigenen Stammzertifizierungsstelle (Certification Authority, ca).</span><span class="sxs-lookup"><span data-stu-id="47dee-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="47dee-111">Üblicherweise weicht die Domäne der Zertifizierungsstelle von der Domäne des Skype for Business-Servers ab. Daher wird das Zertifikat als nicht vertrauenswürdig angesehen, und bei der Anmeldung tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="47dee-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="47dee-112">Skype muss den Domänennamen des Zertifikats kennen, um eine Vertrauensstellung einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="47dee-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="47dee-113">Unternehmen verwenden in der Regel Gruppenrichtlinien, um diesen Namen per Push an den Skype-Desktopclient zu senden. Gruppenrichtlinien werden auf Surface Hub jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="47dee-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="47dee-114">So konfigurieren Sie den Domänennamen für Ihren Skype for Business-Server</span><span class="sxs-lookup"><span data-stu-id="47dee-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="47dee-115">Öffnen Sie auf Surface Hub **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="47dee-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="47dee-116">Klicken Sie auf **Surface Hub**, und klicken Sie dann auf **Anrufe und Audio**.</span><span class="sxs-lookup"><span data-stu-id="47dee-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="47dee-117">Klicken Sie unter **Skype for Business-Konfiguration** auf **Domänennamen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="47dee-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="47dee-118">Geben Sie den Domänennamen für Ihren Skype for Business-Server ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="47dee-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="47dee-119">Sie können mehrere Domänennamen durch Kommas getrennt eingeben.</span><span class="sxs-lookup"><span data-stu-id="47dee-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="47dee-120">Beispiel: lync.com, outlook.com, lync.glbdns.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="47dee-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![Hinzufügen von Skype for Business-FQDN zu Einstellungen](images/system-settings-add-fqdn.png)
