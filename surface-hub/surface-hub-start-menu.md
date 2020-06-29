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
ms.openlocfilehash: c5b6a083d543649eab899d2fea36327d08f8bc29
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832404"
---
# Konfigurieren des Surface Hub-Startmenüs

Das [Update vom 17. Januar2018 für Windows10](https://support.microsoft.com/help/4057144) (Build 15063.877) ermöglicht angepasste Startmenüs auf Surface Hub-Geräten. Sie können das angepasste Startmenü-Layout mit der Verwaltung mobiler Geräte (MDM) verwenden.

Wenn Sie ein benutzerdefiniertes Startmenü-Layout auf Surface Hub verwenden, können Benutzer auf dem Startbildschirm keine Apps anheften, lösen oder deinstallieren. 

## So verwenden Sie ein angepasstes Startmenü auf Surface Hub

Das angepasste Startmenü ist in einer XML-Startlayoutdatei definiert. Zum Erstellen Ihrer XML-Startlayoutdatei verfügen Sie über zwei Optionen:

- Bearbeiten der [Surface Hub XML-Standard-Startdatei](#default)

    -oder-

- Konfigurieren Sie das gewünschte Startmenü auf dem Desktop (nur Apps anheften, die auf Surface Hub verfügbar sind), und klicken Sie dann auf [Layout exportieren](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).

>[!TIP]
>Um eine Kachel mit einem Weblink an das Startmenü auf dem Desktop hinzuzufügen, wechseln Sie auf den Link in Microsoft Edge, wählen Sie `...`in der oberen rechten Ecke, und wählen Sie **auf dieser Seite an die Startseite anheften**. Ein Beispiel, wie Links im XML-Code angezeigt werden, finden Sie unter [a Start layout that includes a Microsoft Edge link](#edge).

Um die standardmäßige XML-Datei oder das exportierte Layout zu bearbeiten, machen Sie sich mit der [Startlayout-XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop) vertraut. Es gibt einige wenige [Unterschiede zwischen einem Startlayout auf einem Desktop und auf einem Surface Hub.](#differences)

Wenn Sie das Startmenü in einem Startlayout-XML-Code definiert haben [erstellen Sie eine MDM-Richtlinie, um das Layout zu übernehmen.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)

<span id="differences" />
## Unterschiede zwischen dem Startmenü auf Surface Hub und dem Desktop

Es gibt einige wichtige Unterschiede zwischen der Anpassung der Startseite im Menü für Surface Hub und einem Windows10-Desktop:

- Sie können **DesktopApplicationTile** ( https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in Ihrem Start Layout-XML nicht verwenden, da Windows-Desktopanwendungen (Win32) nicht auf Surface Hub unterstützt werden.
- Sie können das Startlayout-XML nicht zur Konfiguration der Taskleiste oder der Willkommensseite für Surface Hub verwenden.  
- Surface Hub unterstützt bis zu 6 Spalten (6 1x1-Kacheln), Sie **müssen** allerdings `GroupCellWidth=8` definieren, obwohl Surface Hub nur die Kacheln 0 bis 5 in Spalten anzeigt, und nicht die Spalten 6 und 7.
- Surface Hub unterstützt maximal 6 Zeilen (6 Kacheln 1x1)
- `SecondaryTile`, die für Links verwendet werden und den Link in Microsoft Edge öffnet.


<span id="default" />
## Beispiel: Surface Hub XML-Standardlayout

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
## Beispiel: Startseitenlayout, das einen Link zu Microsoft Edge enthält

Dieses Beispiel zeigt einen Link zu einer Website und einen Link zu einer PDF-Datei. Die sekundäre Kachel für Microsoft Edge verwendet ein 150 x 150 Pixel-Symbol.

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
>Der Standardwert für `ForegroundText` ist Light; Sie müssen `ForegroundText` Ihre XML-Datei nur dann einbeziehen, wenn Sie den Wert in "dunkel" ändern.
