---
title: Implementieren von Quality of Service auf Surface Hub
ms.reviewer: ''
manager: laurawi
description: Erfahren Sie, wie Sie QoS auf Surface Hub konfigurieren.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832911"
---
# Implementieren von Quality of Service (QoS) auf Surface Hub

Quality of Service (QoS) ist eine Kombination aus Netzwerktechnologien, mit deren Hilfe Administratoren die Erfahrung von Audio/Video-und Anwendungsfreigabe-Kommunikation in Echtzeit optimieren können.
 
Die Konfiguration von [QoS für Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) auf dem Surface Hub kann mithilfe des [MDM-Anbieters (Mobile Device Management)](manage-settings-with-mdm-for-surface-hub.md) oder über ein [Bereitstellungspaket](provisioning-packages-for-surface-hub.md)erfolgen. 
 
 
In diesem Verfahren wird erläutert, wie Sie QoS für Surface Hub mithilfe von Microsoft InTune konfigurieren. 

1. Erstellen Sie in InTune [eine benutzerdefinierte Richtlinie](https://docs.microsoft.com/intune/custom-settings-configure).

    ![Screenshot des Dialogfelds zum Erstellen benutzerdefinierter Richtlinien in InTune](images/qos-create.png)

2. Wählen Sie unter **benutzerdefinierte Oma-URI-Einstellungen**die Option **Hinzufügen**aus. Für jede Einstellung, die Sie hinzufügen, geben Sie einen Namen, eine Beschreibung (optional), einen Datentyp, einen Oma-URI und einen Wert ein.

    ![Screenshot eines leeren Dialogfelds für OMA-URI-Einstellungen](images/qos-setting.png)

3. Fügen Sie die folgenden benutzerdefinierten Oma-URI-Einstellungen hinzu:

    Name | Datentyp | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Wert
    --- | --- | --- | ---
    Audioquellen-Port | Zeichenfolge |  /HubAudio/SourcePortMatchCondition  |   Holen Sie sich die Werte Ihres Skype-Administrators
    Audio DSCP | Ganze Zahl |  /HubAudio/DSCPAction  |   46
    Video Quell Port | Zeichenfolge |  /HubVideo/SourcePortMatchCondition   |  Holen Sie sich die Werte Ihres Skype-Administrators
    Video DSCP | Ganze Zahl |  /HubVideo/DSCPAction   |   34
    Name des Audio-Prozesses | Zeichenfolge |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Name des Video Prozesses | Zeichenfolge |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Jeder **Oma-URI-** Pfad beginnt mit `./Device/Vendor/MSFT/NetworkQoSPolicy` . Der vollständige Pfad für die Audioquellen-Porteinstellung wird beispielsweise sein `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .




4. Wenn die Richtlinie erstellt wurde, [Stellen Sie Sie auf dem Surface Hub bereit.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>Derzeit können Sie die Einstellung **IPProtocolMatchCondition** im [NetworkQoSPolicy-CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)nicht konfigurieren. Wenn diese Einstellung konfiguriert ist, kann die Richtlinie nicht angewendet werden.
 
