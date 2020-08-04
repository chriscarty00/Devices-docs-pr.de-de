---
title: Aktivieren von Wake-on-Power für Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Beschreibt, wie Sie Wake-on-Power für Surface-Geräte aktivieren und deaktivieren.
keywords: Update, bereitstellen, Treiber, wol, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903394"
---
# Wake-on-Power für Surface-Geräte

Surface-Geräte können ausgeschaltet werden, wenn Sie nicht an Ihrem Schreibtisch sind, oder Sie können den Ruhemodus aktivieren, um die Akkulaufzeit zu sparen. Um die Verwaltbarkeit dieser Geräte zu verbessern, ermöglicht Wake on Power das automatische Starten von kompatiblen Surface-Geräten, wenn Sie wieder an die Stromversorgung angeschlossen werden. Um Wake-on-Power zu konfigurieren, können Sie den Surface Enterprise Management Mode (Semm) entweder über den Surface UEFI-Konfigurator oder den UEFI-Manager verwenden.

Das Feature Wake-on-Power steht auf den folgenden Geräten zur Verfügung:

- DGM-Buch 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X 

## Übersicht und Voraussetzungen

Mit dem Surface UEFI Configurator können Sie einzelne UEFI-Einstellungen in einem Windows Installer. MSI-Paket für die Verteilung an Zielgeräte speichern. 

> [!NOTE]
> In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie Semm verwenden. Weitere Informationen finden Sie unter Dokumentation zu [Surface Enterprise Management Mode (Semm)](surface-enterprise-management-mode.md) .

## So aktivieren Sie Wake-on-Power

1.  Laden Sie die neueste Version des [Surface UEFI-Konfigurators](https://www.microsoft.com/download/confirmation.aspx?id=46703)herunter.
2.  Registrieren Sie sich als Administrator bei Ihrem Surface-Gerät, öffnen Sie **Surface UEFI Configurator**, wählen Sie **Surface Devices**aus, und wählen Sie dann **weiter**aus.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Wählen Sie Surface Devices aus, und wählen Sie weiter aus.":::
3.  Wählen Sie **Start**aus, und wählen Sie dann unter **Konfigurationspaket** **Erstellen** aus.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Wählen Sie Konfigurationspaket erstellen aus.":::
4.  Wählen Sie **Zertifikatschutz**aus, und fügen Sie die Datei Certificate. pfx hinzu. 
5. Geben Sie Ihr Kennwort ein, wählen Sie **weiter**aus, fügen Sie nach Bedarf **Kennwortschutz**hinzu, und wählen Sie dann **weiter**aus.
6.  Wählen Sie auf der Seite **Wählen Sie den DGM-Typ aus, den Sie als Ziel auswählen möchten** die gewünschten Zielgeräte aus. Wählen Sie beispielsweise **Surface pro 7**aus.
7.  Wählen Sie auf der Seite **Advanced Features** die Option **Wake on Power**aus, legen Sie das Feature auf **ein**, und wählen Sie dann **weiter**aus.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Wählen Sie bei Stromversorgung aktivieren aus, und legen Sie auf ein."::: 
8.  Wählen Sie auf der Seite **erfolgreich** die Option **Ende**aus.

    > [!NOTE]
    > Wenn Sie zum ersten Mal Einstellungen für Ihr Gerät bereitstellen, werden Sie aufgefordert, auch die letzten beiden Zeichen des Zertifikat Fingerabdrucks anzugeben. 
9.  Speichern Sie das MSI-Paket. 

## Anwenden des MSI-Pakets 

Sie können das MSI-Paket auf Geräte im gesamten Netzwerk anwenden, indem Sie Softwareverteilungstools wie Microsoft Endpoint Configuration Manager verwenden. Dieses Verfahren umfasst Schritte zum Installieren des Pakets auf dem lokalen Computer. 

1.  Geben Sie an einer Eingabeaufforderung mit erhöhten Rechten den vollständigen Pfad der MSI-Datei ein, um das MSI-Paket auszuführen. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Wählen Sie im Dialogfeld **Warnung** die Option **OK** aus, oder deaktivieren Sie BitLocker, je nach Bedarf.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Wählen Sie OK aus, oder deaktivieren Sie BitLocker entsprechend.":::
3.  Wählen Sie auf der Seite Willkommen die Option **weiter** aus, um das Paket auszuführen und die neu konfigurierte UEFI-Einstellung anzuwenden.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Klicken Sie auf der Seite Willkommen auf Weiter.":::
4.  Starten Sie Ihr Gerät neu. 

Wake-on-Power ist jetzt konfiguriert. Wenn Sie die Einstellungen testen möchten, schalten Sie Ihr Gerät aus, trennen Sie die Stromversorgung, und schließen Sie dann die Verbindung wieder an. Das Gerät sollte automatisch gestartet werden. 

## Verweise

Weitere Informationen finden Sie in den folgenden Artikeln. 

- [Surface Enterprise Management-Modus](surface-enterprise-management-mode.md)
- [Wake-on-LAN für Surface-Geräte](wake-on-lan-for-surface-devices.md)

Benötigen Sie weitere Hilfe? Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).