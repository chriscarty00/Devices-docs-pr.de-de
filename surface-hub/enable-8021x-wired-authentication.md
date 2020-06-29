---
title: Aktivieren der kabelgebundenen 802.1x-Authentifizierung
description: Die MDM-Richtlinien für die 802.1x kabelgebundene Authentifizierung wurde auf Surface Hub-Geräten aktiviert.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833706"
---
# <span data-ttu-id="83a35-103">Aktivieren Sie 802.1x kabelgebundene Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="83a35-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="83a35-104">Das [Update vom 14 November2017 auf Windows10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (Build 15063.726) ermöglicht die MDM-Richtlinien für die 802.1x kabelgebundene Authentifizierung auf Surface Hub-Geräten.</span><span class="sxs-lookup"><span data-stu-id="83a35-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="83a35-105">Das Feature ermöglicht Organisationen, standardisierte Kabelnetzwerkauthentifizierungen mithilfe des [IEEE 802.1x-Authentifizierungsprotokolls](http://www.ieee802.org/1/pages/802.1x-2010.html) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="83a35-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="83a35-106">Diese Option besteht bereits für die drahtlose Authentifizierung mithilfe von WLAN-Profilen per MDM.</span><span class="sxs-lookup"><span data-stu-id="83a35-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="83a35-107">In diesem Thema wird erläutert, wie Sie einen Surface Hub für die Verwendung mit kabelgebundenen Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="83a35-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="83a35-108">Die Erzwingung und Aktivierung der 802.1x kabelgebundenen Authentifizierung auf Surface Hub kann über die MDM [OMA-URI-Definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings) durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="83a35-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="83a35-109">Die primäre Konfiguration ist auf die Richtlinie **LanProfile** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83a35-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="83a35-110">Je nach ausgewählter Authentifizierungsmethode sind andere Richtlinien möglicherweise erforderlich, entweder die **EapUserData**-Richtlinie oder die MDM-Richtlinien für das Hinzufügen von Benutzer- oder Computerzertifikaten (z.B. [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) für Benutzer/Gerätezertifikate oder [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) für Gerätezertifikate).</span><span class="sxs-lookup"><span data-stu-id="83a35-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="83a35-111">LanProfile-Richtlinienelement</span><span class="sxs-lookup"><span data-stu-id="83a35-111">LanProfile policy element</span></span>

<span data-ttu-id="83a35-112">Um Surface Hub zum Verwenden der unterstützten 802.1 x-Authentifizierungsmethoden zu konfigurieren, verwenden Sie die folgende OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="83a35-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="83a35-113">Dieser OMA-URI-Knoten verwendet eine XML-Textzeichenfolge als Parameter.</span><span class="sxs-lookup"><span data-stu-id="83a35-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="83a35-114">Der als Parameter bereitgestellte XML-Code sollte dem [verkabelten LAN-Profilschema](https://msdn.microsoft.com/library/cc233002.aspx) einschließlich der Elemente des [802.1X-Schemas](https://msdn.microsoft.com/library/cc233003.aspx) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="83a35-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="83a35-115">In den meisten Fällen kann ein Administrator oder Benutzer die LanProfile XML von einem vorhandenen PC exportieren, der bereits im Netzwerk für 802.1X mit dem folgenden NETSH-Befehl konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="83a35-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="83a35-116">Das Ausführung dieses Befehls ergibt die folgende Ausgabe und platziert eine Datei mit dem Titel **Ethernet.xml** in das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="83a35-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="83a35-117">EapUserData-Richtlinienelement</span><span class="sxs-lookup"><span data-stu-id="83a35-117">EapUserData policy element</span></span>

<span data-ttu-id="83a35-118">Wenn die ausgewählte Authentifizierungsmethode einen Benutzernamen und Kennwort im Gegensatz zu einem Zertifikat erfordert, können Sie das **EapUserData**-Elements zur Angabe der Anmeldeinformationen für das Gerät verwenden, um sich beim Netzwerk zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="83a35-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="83a35-119">Dieser OMA-URI-Knoten verwendet eine XML-Textzeichenfolge als Parameter.</span><span class="sxs-lookup"><span data-stu-id="83a35-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="83a35-120">Der als Parameter bereitgestellte XML-Code sollte dem [Beispiel der Benutzereigenschaften für PEAP-MS-CHAPv2](https://msdn.microsoft.com/library/windows/desktop/bb891979) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="83a35-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="83a35-121">In diesem Beispiel müssen Sie alle Instanzen von *test* und *ias-domain* durch Ihre Informationen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="83a35-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="83a35-122">Hinzufügen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="83a35-122">Adding certificates</span></span>

<span data-ttu-id="83a35-123">Wenn die ausgewählte Authentifizierungsmethode Zertifikat basiert ist, müssen Sie [ein Bereitstellungspaket erstellen](provisioning-packages-for-surface-hub.md), [MDM verwenden](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)oder ein Zertifikat aus den Einstellungen (**Einstellungen**  >  **aktualisieren und Sicherheits**  >  **Zertifikate**) importieren, um diese Zertifikate auf dem Surface Hub-Gerät im entsprechenden Zertifikatspeicher bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="83a35-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="83a35-124">Wenn Sie ein Zertifikat hinzufügen möchten, muss jeder PFX nur ein Zertifikat enthalten (PFX kann nicht mehrere Zertifikate enthalten).</span><span class="sxs-lookup"><span data-stu-id="83a35-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>

