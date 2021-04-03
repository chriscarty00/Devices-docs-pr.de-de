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
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470483"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>Implementieren der Dienstqualität (Quality of Service, QoS) auf Surface Hub

Quality of Service (QoS) ist eine Kombination aus Netzwerktechnologien, mit der administratoren die Nutzung von Audio-/Video- und Anwendungsfreigabekommunikation in Echtzeit optimieren können.
 
Das Konfigurieren [von QoS für Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) auf dem Surface Hub kann über Ihren Mobile Device Management [(MDM)-Anbieter](manage-settings-with-mdm-for-surface-hub.md) oder über ein [Bereitstellungspaket durchgeführt werden.](provisioning-packages-for-surface-hub.md) 
 
 
In diesem Verfahren wird erläutert, wie Sie QoS für Surface Hub mithilfe von Microsoft Intune konfigurieren. 

1. Erstellen Sie in Intune [eine benutzerdefinierte Richtlinie](https://docs.microsoft.com/intune/custom-settings-configure).

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Dialogfelds zum Erstellen benutzerdefinierter Richtlinien in Intune](images/qos-create.png)

2. Wählen **Sie unter Benutzerdefinierte OMA-URI-Einstellungen**die Option **Hinzufügen aus.** Für jede hinzugefügte Einstellung geben Sie einen Namen, eine Beschreibung (optional), einen Datentyp, einen OMA-URI und einen Wert ein.

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines leeren OMA-URI-Einstellungsdialogfelds](images/qos-setting.png)

3. Fügen Sie die folgenden benutzerdefinierten OMA-URI-Einstellungen hinzu:<br/><br/>

    Name | Datentyp | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Wert
    --- | --- | --- | ---
    Audioquellenport | Zeichenfolge |  /HubAudio/SourcePortMatchCondition  |   Die Werte von Ihrem Skype-Administrator erhalten
    Audio DSCP | Ganze Zahl |  /HubAudio/DSCPAction  |   46
    Video Source Port | Zeichenfolge |  /HubVideo/SourcePortMatchCondition   |  Die Werte von Ihrem Skype-Administrator erhalten
    Video DSCP | Ganze Zahl |  /HubVideo/DSCPAction   |   34
    Name des Audioprozesses | Zeichenfolge |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Name des Videoprozesses | Zeichenfolge |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Jeder **OMA-URI-Pfad** beginnt mit `./Device/Vendor/MSFT/NetworkQoSPolicy` . Der vollständige Pfad für die Einstellung des Audioquellenports ist beispielsweise `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .

4. Wenn die Richtlinie erstellt wurde, stellen Sie sie auf Surface Hub aus.


>[!WARNING]
>Derzeit können Sie die Einstellung **IPProtocolMatchCondition** im [NetworkQoSPolicy CSP nicht konfigurieren.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) Wenn diese Einstellung konfiguriert ist, kann die Richtlinie nicht angewendet werden.
 
