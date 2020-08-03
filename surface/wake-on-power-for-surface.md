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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903005"
---
# Wake-on-Power für Surface-Geräte

Surface-Geräte können ausgeschaltet werden, wenn Sie sich nicht am Schreibtisch befinden oder den Ruhemodus einstellen, um Batterie zu sparen. Um die Verwaltbarkeit dieser Geräte zu verbessern, ermöglicht Wake on Power das automatische Starten von kompatiblen Surface-Geräten, wenn die Verbindung mit dem Stromnetz wiederhergestellt wird. Die Konfiguration von Wake-on-Power erfordert die Verwendung des Surface Enterprise Management Mode (Semm) entweder über den Surface UEFI-Konfigurator oder den UEFI-Manager.

Wake-on-Power ist eine Funktion, die auf den folgenden Geräten zur Verfügung steht:

- DGM-Buch 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X 

## Übersicht und Voraussetzungen

Sie können den Surface UEFI-Konfigurator verwenden, um einzelne UEFI-Einstellungen zu konfigurieren, die in einem Windows Installer. MSI-Paket für die Verteilung an Zielgeräte gespeichert sind. 

> [!NOTE]
> In diesem Artikel wird davon ausgegangen, dass Sie mit der Verwendung von Semm vertraut sind. Weitere Informationen finden Sie unter Dokumentation zu [Surface Enterprise Management Mode (Semm)](surface-enterprise-management-mode.md) .

## So aktivieren Sie Wake-on-Power

1.  Laden Sie die neueste Version des [Surface UEFI-Konfigurators](https://www.microsoft.com/download/confirmation.aspx?id=46703)herunter.
2.  Registrieren Sie sich als Administrator bei Ihrem Surface-Gerät, öffnen Sie **Surface UEFI Configurator**, wählen Sie **Surface Devices**aus, und wählen Sie dann **weiter**aus.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Wählen Sie Surface Devices aus, und wählen Sie weiter aus.":::
3.  Wählen Sie **Start** aus, und klicken Sie dann unter **Konfigurationspaket** auf **Erstellen**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Wählen Sie Konfigurationspaket erstellen aus.":::
4.  Wählen Sie **Zertifikatschutz** aus, und fügen Sie die Datei Certificate. pfx hinzu. Nachdem Sie Ihr Kennwort eingegeben haben, wählen Sie **weiter**aus. Fügen Sie nach Bedarf **Kennwortschutz**hinzu, und wählen Sie dann **weiter**aus.
5.  Wählen Sie auf der Seite **Wählen Sie den DGM-Typ aus, den Sie als Ziel auswählen möchten** die gewünschten Zielgeräte aus. Beispiel: **Surface pro 7**.
6.  Wählen Sie auf der Seite **Erweiterte Features** die Option **bei Stromversorgung** aktivieren und auf **ein**festlegen aus. Wählen Sie **Weiter** aus.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Wählen Sie bei Stromversorgung aktivieren aus, und legen Sie auf ein."::: 
7.  Wählen Sie auf der Seite **erfolgreich** die Option **Ende**aus. Wenn Sie zum ersten Mal Einstellungen für Ihr Gerät bereitstellen, werden Sie aufgefordert, die letzten beiden Zeichen des Zertifikat Fingerabdrucks anzugeben. 
8.  Speichern Sie das MSI-Paket. 

## Anwenden des MSI-Pakets 

Sie können das MSI-Paket auf Geräte in Ihrem Netzwerk mithilfe von Softwareverteilungstools wie Microsoft Endpoint Configuration Manager anwenden. Dieses Verfahren enthält die Schritte zum Installieren des Pakets auf dem lokalen Computer. 

1.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den vollständigen Pfad der MSI-Datei ein, um das MSI-Paket auszuführen. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Wählen Sie im Dialogfeld **Warnung** die Option **OK** aus, oder deaktivieren Sie BitLocker entsprechend.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Wählen Sie OK aus, oder deaktivieren Sie BitLocker entsprechend.":::
3.  Wählen Sie auf der Seite Willkommen die Option **weiter** aus, um das Paket auszuführen und die neu konfigurierte UEFI-Einstellung anzuwenden.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Klicken Sie auf der Seite Willkommen auf Weiter.":::
4.  Starten Sie Ihr Gerät neu. 

Wake-on-Power ist jetzt konfiguriert. Wenn Sie die Einstellung testen möchten, schalten Sie Ihr Gerät aus, trennen Sie die Stromversorgung, und schließen Sie dann die Verbindung wieder an. Das Gerät wird automatisch gestartet. 

## Weitere Informationen

Weitere Informationen finden Sie in den folgenden Artikeln. 

- [Surface Enterprise Management-Modus](surface-enterprise-management-mode.md)
- [Wake-on-LAN für Surface-Geräte](wake-on-lan-for-surface-devices.md)

Benötigen Sie weitere Hilfe? Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).