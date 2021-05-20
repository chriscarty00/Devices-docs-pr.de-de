---
title: Konfigurieren des Surface Hub-Startmenüs
description: Verwenden Sie MDM, um das Startmenü auf Surface Hub benutzerdefiniert anzupassen.
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: cf9649b8d1f747722064793fbbde70116bc7f424
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576845"
---
# <a name="configure-surface-hub-start-menu"></a><span data-ttu-id="6a42d-103">Konfigurieren des Surface Hub-Startmenüs</span><span class="sxs-lookup"><span data-stu-id="6a42d-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="6a42d-104">Das [Update vom 17. Januar2018 für Windows10](https://support.microsoft.com/help/4057144) (Build 15063.877) ermöglicht angepasste Startmenüs auf Surface Hub-Geräten.</span><span class="sxs-lookup"><span data-stu-id="6a42d-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="6a42d-105">Sie können das angepasste Startmenü-Layout mit der Verwaltung mobiler Geräte (MDM) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a42d-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="6a42d-106">Wenn Sie ein benutzerdefiniertes Startmenü-Layout auf Surface Hub verwenden, können Benutzer auf dem Startbildschirm keine Apps anheften, lösen oder deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="6a42d-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a><span data-ttu-id="6a42d-107">So verwenden Sie ein angepasstes Startmenü auf Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6a42d-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="6a42d-108">Das angepasste Startmenü ist in einer XML-Startlayoutdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="6a42d-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="6a42d-109">Zum Erstellen Ihrer XML-Startlayoutdatei verfügen Sie über zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="6a42d-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="6a42d-110">Bearbeiten der [Surface Hub XML-Standard-Startdatei](#default)</span><span class="sxs-lookup"><span data-stu-id="6a42d-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="6a42d-111">-oder-</span><span class="sxs-lookup"><span data-stu-id="6a42d-111">-or-</span></span>

- <span data-ttu-id="6a42d-112">Konfigurieren Sie das gewünschte Startmenü auf dem Desktop (nur Apps anheften, die auf Surface Hub verfügbar sind), und klicken Sie dann auf [Layout exportieren](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span><span class="sxs-lookup"><span data-stu-id="6a42d-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="6a42d-113">Um eine Kachel mit einem Weblink an das Startmenü auf dem Desktop hinzuzufügen, wechseln Sie auf den Link in Microsoft Edge, wählen Sie `...`in der oberen rechten Ecke, und wählen Sie **auf dieser Seite an die Startseite anheften**.</span><span class="sxs-lookup"><span data-stu-id="6a42d-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="6a42d-114">Ein Beispiel, wie Links im XML-Code angezeigt werden, finden Sie unter [a Start layout that includes a Microsoft Edge link](#edge).</span><span class="sxs-lookup"><span data-stu-id="6a42d-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="6a42d-115">Um die standardmäßige XML-Datei oder das exportierte Layout zu bearbeiten, machen Sie sich mit der [Startlayout-XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop) vertraut.</span><span class="sxs-lookup"><span data-stu-id="6a42d-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="6a42d-116">Es gibt einige wenige [Unterschiede zwischen einem Startlayout auf einem Desktop und auf einem Surface Hub.](#differences)</span><span class="sxs-lookup"><span data-stu-id="6a42d-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="6a42d-117">Wenn Sie das Startmenü in einem Startlayout-XML-Code definiert haben [erstellen Sie eine MDM-Richtlinie, um das Layout zu übernehmen.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="6a42d-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a><span data-ttu-id="6a42d-118">Unterschiede zwischen dem Startmenü auf Surface Hub und dem Desktop</span><span class="sxs-lookup"><span data-stu-id="6a42d-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="6a42d-119">Es gibt einige wichtige Unterschiede zwischen der Anpassung der Startseite im Menü für Surface Hub und einem Windows10-Desktop:</span><span class="sxs-lookup"><span data-stu-id="6a42d-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="6a42d-120">Sie können **DesktopApplicationTile** ( in Ihrem Startlayout-XML nicht verwenden, da Windows Desktopanwendungen (Win32) nicht auf der https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6a42d-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="6a42d-121">Sie können das Startlayout-XML nicht zur Konfiguration der Taskleiste oder der Willkommensseite für Surface Hub verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a42d-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="6a42d-122">Die Startlayoutrichtlinie sollte nur Geräten und nicht Benutzern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6a42d-122">The Start layout policy should be assigned only to devices, not users.</span></span>
- <span data-ttu-id="6a42d-123">Die in der Richtlinie zu verwendende OMA-URI-Einstellung ist</span><span class="sxs-lookup"><span data-stu-id="6a42d-123">The OMA-URI setting to use in the policy is</span></span> `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- <span data-ttu-id="6a42d-124">Surface Hub unterstützt bis zu 6 Spalten (6 1x1-Kacheln), Sie **müssen** allerdings `GroupCellWidth=8` definieren, obwohl Surface Hub nur die Kacheln 0 bis 5 in Spalten anzeigt, und nicht die Spalten 6 und 7.</span><span class="sxs-lookup"><span data-stu-id="6a42d-124">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="6a42d-125">Surface Hub unterstützt maximal 6 Zeilen (6 Kacheln 1x1)</span><span class="sxs-lookup"><span data-stu-id="6a42d-125">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="6a42d-126">, die für Links verwendet werden und den Link in Microsoft Edge öffnet.</span><span class="sxs-lookup"><span data-stu-id="6a42d-126">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a><span data-ttu-id="6a42d-127">Beispiel: Surface Hub XML-Standardlayout</span><span class="sxs-lookup"><span data-stu-id="6a42d-127">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a><span data-ttu-id="6a42d-128">Beispiel: Startseitenlayout, das einen Link zu Microsoft Edge enthält</span><span class="sxs-lookup"><span data-stu-id="6a42d-128">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="6a42d-129">Dieses Beispiel zeigt einen Link zu einer Website und einen Link zu einer PDF-Datei.</span><span class="sxs-lookup"><span data-stu-id="6a42d-129">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="6a42d-130">Die sekundäre Kachel für Microsoft Edge verwendet ein 150 x 150 Pixel-Symbol.</span><span class="sxs-lookup"><span data-stu-id="6a42d-130">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
><span data-ttu-id="6a42d-131">Der Standardwert für ist hell. Sie müssen ihre #A0 nur dann in die #A1 ein- und ausdunklieren, wenn Sie `ForegroundText` den Wert in Dunkel `ForegroundText` ändern.</span><span class="sxs-lookup"><span data-stu-id="6a42d-131">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>
