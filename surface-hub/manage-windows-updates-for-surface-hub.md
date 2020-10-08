---
title: Manage Windows updates on Surface Hub
description: You can manage Windows updates on your Microsoft Surface Hub or Surface Hub 2S by setting the maintenance window, deferring updates, or using Windows Server Update Services (WSUS).
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: manage Windows updates, Surface Hub, Windows Server Update Services, WSUS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 72214ec9436e6ea106d9e42c957664631ee88a0a
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103789"
---
# Manage Windows updates on Surface Hub

New releases of the Surface Hub operating system are published through Windows Update, just like releases of Windows 10. Es gibt verschiedene Möglichkeiten, zu steuern, welche Updates auf den Surface Hub-Geräten installiert werden und wann Updates angewendet werden sollen.
- **Windows Update for Business** – Windows Update for Business ist neu in Windows10 und stellt einen Satz von Features bereit, mit denen Unternehmen besser steuern können, wie und wann Versionen von Windows Update installiert werden. Gleichzeitig werden die Kosten für die Geräteverwaltung reduziert. Bei Verwendung dieser Methode werden Surface Hub-Geräte direkt mit dem Windows Update-Dienst von Microsoft verbunden.
- **Windows Server Update Services (WSUS)** – Dies ist ein Satz von Diensten, mit denen IT-Administratoren die Updates abrufen können, von denen Windows Update annimmt, dass sie auf die Geräte im jeweiligen Unternehmen anwendbar sind; zusätzliche Tests und Evaluierungen der Updates ausführen können; und die zu installierenden Updates auswählen können. Bei Verwendung dieser Methode empfangen Surface Hub-Geräte Updates von WSUS und nicht von Windows Update.

Sie können Surface Hub auch für den Empfang von Updates sowohl von Windows Update for Business als auch von WSUS konfigurieren. Details hierzu finden Sie unter [Integrieren von Windows Update for Business mit Windows Server Update Services](https://technet.microsoft.com/itpro/windows/manage/waas-integrate-wufb#integrate-windows-update-for-business-with-windows-server-update-services).

| Funktionen | Windows Update for Business | Windows Server Update Services (WSUS) |
| ------------ | --------------------------- | ------------------------------------- |
| Empfangen von Updates direkt vom Windows Update-Dienst von Microsoft, ohne dass zusätzliche Infrastruktur erforderlich ist.  | Ja  | Nein  |
| Rückstellung von Updates, um zusätzliche Zeit für Tests und Evaluierung bereitzustellen. | Ja  | Ja  |
| Bereitstellen von Updates für bestimmte Gruppen von Geräten. | Ja | Ja |
| Definieren von Wartungsfenstern für die Installation von Updates. | Ja  | Ja  |

> [!TIP]
> Verwenden Sie die Peer-to-Peer-Inhaltsfreigabe, um Bandbreitenprobleme während Aktualisierungen zu reduzieren. Details hierzu finden Sie unter [Optimieren der Updatebereitstellung für Windows10-Updates](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates).

> [!NOTE]
> Surface Hub unterstützt zurzeit das Zurücksetzen von Updates nicht.


## Surface Hub-Wartungsmodell

Surface Hub verwendet das Windows10-Wartungsmodell, das als [Windows as a Service (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview) bezeichnet wird. Herkömmlicherweise werden neue Features nur in neuen Versionen von Windows hinzugefügt, die in Abständen von einigen Jahren veröffentlicht werden. Jede neue Version erforderte langwierige und kostspielige Bereitstellungsvorgänge in Unternehmen. Dies führte dazu, dass Endbenutzer und Unternehmen die Vorteile von Innovationen häufig nicht nutzten. Das Ziel von Windows as a Service besteht darin, kontinuierlich neue Funktionen bereitzustellen und gleichzeitig eine hohe Qualität zu wahren.

Microsoft veröffentlicht allgemein kontinuierlich zwei Arten von Surface Hub-Versionen:
- **Feature updates** - Updates that install the latest new features, experiences, and capabilities. Microsoft expects to publish two new feature updates per year.
- **Quality updates** - Updates that focus on the installation of security fixes, drivers, and other servicing updates. Microsoft geht davon aus, ein kumulatives Qualitätsupdate pro Monat zu veröffentlichen.

Um die Versionsqualität zu verbessern und die Bereitstellung zu vereinfachen, werden alle neuen Versionen kumulativ sein, die Microsoft für Windows10 einschließlich Surface Hub veröffentlicht. Dies bedeutet, dass Feature- und Qualitätsupdates die Nutzlast aller vorherigen Versionen enthalten (in optimierter Form, um Speicherplatz zu sparen und Netzwerkanforderungen zu berücksichtigen) und die Installation der Version auf einem Gerät dieses vollständig aktualisiert. Anders als bei früheren Versionen von Windows ist es nicht möglich, lediglich einen Teil eines Qualitätsupdates für Windows10 zu installieren. Wenn zum Beispiel ein Qualitätsupdate Patches für drei Sicherheitsrisiken und ein Zuverlässigkeitsproblem enthält, führt die Bereitstellung der Aktualisierung zur Installation von allen vier Patches.

The Surface Hub operating system receives updates on the [Semi-Annual Channel](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Like other editions of Windows 10, the servicing lifetime is finite. You must install new feature updates on machines running these branches in order to continue receiving quality updates.

Weitere Informationen zu Windows as a Service finden Sie unter [Übersicht über Windows as a Service](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Verwenden von Windows Update for Business
Surface Hub-Geräte enthalten, wie alle Windows10-Geräte, **Windows Update for Business (WUfB)**, damit Sie steuern können, wie Ihre Geräte aktualisiert werden. Windows Update for Business hilft, die Kosten für die Geräteverwaltung zu reduzieren, die Kontrolle über die Bereitstellung von Updates zu wahren, einen schnelleren Zugriff auf Sicherheitsupdates zu erhalten und kontinuierlich die neuesten Innovationen von Microsoft bereitzustellen. Weitere Informationen finden Sie unter [Verwalten von Updates mit Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

**So richten Sie Windows Update for Business ein**
1. [Gruppieren von Surface Hub in Bereitstellungsringe](#group-surface-hub-into-deployment-rings)
2. [Configure when Surface Hub receives updates](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> You can use Microsoft Intune, Microsoft Endpoint Configuration Manager, or a supported third-party MDM provider to set up WUfB. [Walkthrough: use Microsoft Intune to configure Windows Update for Business.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Gruppieren von Surface Hub in Bereitstellungsringe
Verwenden Sie Bereitstellungsringe, um zu steuern, wann Updates auf Surface Hub-Geräten installiert werden, damit Sie Zeit für deren Prüfung haben. Beispielsweise können Sie einen kleinen Pool von Geräten zuerst aktualisieren, um die Qualität zu überprüfen, bevor Sie das Update umfassender für Ihr Unternehmen bereitstellen. Abhängig davon, wer die Surface Hub-Geräte in Ihrer Organisation verwaltet, sollten Sie die Integration von Surface Hub in die Bereitstellungsringe in Betracht ziehen, die Sie für andere Windows10-Geräten erstellt haben. Weitere Informationen zu Bereitstellungsringen finden Sie unter [Erstellen von Bereitstellungsringen für Windows10-Updates](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

Diese Tabelle enthält Beispiele für Bereitstellungsringe.

| Bereitstellungsring | Ringgröße | Wartungszweig | Rückstellung für Featureupdates | Rückstellung für Qualitätsupdates (Sicherheitsupdates, Treiber und andere Updates) | Überprüfungsschritt |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Vorschau (z.B. nicht kritisch oder Testgeräte) | Small | Windows Insider Preview | None.  | Keine  | Manuelles Testen und Evaluieren neuer Funktionen. Unterbrechen von Updates bei Problemen. |
| Version (z.B. Geräte, die von bestimmten Teams verwendet werden) | Mittel | Semi-Annual Channel  | Keine | Keine  | Überwachen von Gerätenutzung und Benutzerfeedback. Unterbrechen von Updates bei Problemen. |
| Umfassende Bereitstellung (z.B. auf der Mehrzahl der Geräte in Ihrer Organisation) | Groß | Semi-Annual Channel |  120Tage nach Veröffentlichung. | 7-14Tage nach Veröffentlichung. | Überwachen von Gerätenutzung und Benutzerfeedback. Unterbrechen von Updates bei Problemen. |
| Unternehmenskritisch (z.B. Geräte Besprechungsräumen von Führungskräften) | Klein | Semi-Annual Channel |  180Tage nach der Veröffentlichung (maximale Rückstellung für Featureupdates). | 30Tage nach der Veröffentlichung (maximale Rückstellung für Qualitätsupdates). | Überwachen von Gerätenutzung und Benutzerfeedback. |





### Konfigurieren des Zeitpunkts, an dem Surface Hub Updates empfängt
Nachdem Sie Bereitstellungsringe für die Surface Hub-Geräte festgelegt haben, konfigurieren Sie für die einzelnen Ringe Rückstellungsrichtlinien für Updates:
- Um Featureupdates zurückzustellen, legen Sie eine entsprechende [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)-Richtlinie für jeden Ring fest.
- Um Qualitätsupdates zurückzustellen, legen Sie eine entsprechende [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)-Richtlinie für jeden Ring fest.

> [!NOTE]
> Bei Problemen während des Updaterollouts können Sie Updates mit [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) und [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates) unterbrechen.


## Verwenden von Windows Server Update Services

Sie können Surface Hub mit Ihrem WSUS(Windows Server Update Services)-Server verbinden, um Updates zu verwalten. Die Updates werden über Genehmigungen oder automatische Bereitstellungsregeln gesteuert, die auf dem WSUS-Server konfiguriert sind. Auf diese Weise werden neue Upgrades erst bereitgestellt, wenn Sie dies möchten.

**So verbinden Sie einen Surface Hub manuell mit einem WSUS-Server**
1. Öffnen Sie auf dem Surface Hub **Einstellungen**.
2. Geben Sie die Geräteadministrator-Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
3. Navigieren Sie zu **Update und Sicherheit** > **Windows Update** > **Erweiterte Optionen** > **Windows Server Update Services (WSUS)-Server konfigurieren**.
4. Klicken Sie auf **WSUS-Server zum Herunterladen von Updates verwenden**, und geben Sie die URL des WSUS-Servers ein.

Um Surface Hub mit einem WSUS-Server mithilfe von MDM zu verbinden, legen Sie eine entsprechende [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)-Richtlinie fest.

**Wenn Sie über einen Proxyserver oder mit einer anderen Methode URLs blockieren**

Wenn Sie eine andere Methode als WSUS zum Blockieren bestimmter URLs und zum Verhindern von Updates verwenden, müssen Sie die folgenden vertrauenswürdigen Windows Update-Website-URLs den „zugelassenen Kontakten“ hinzufügen:
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Sobald das Windows10 Team Anniversary Update installiert ist, können Sie diese Adressen entfernen, um den vorherigen Zustand Ihres Surface Hub wiederherzustellen.

## Wartungsfenster

To ensure the device is always available for use during business hours, Surface Hub performs its administrative functions during a specified maintenance window. During the maintenance window, the Surface Hub automatically installs updates through Windows Update or WSUS, and reboots the device 20 minutes before the end of the window.

Surface Hub follows these guidelines to apply updates:
- Das Update wird während des nächsten Wartungsfensters installiert. Wenn der Start einer Besprechung während eines Wartungsfensters geplant ist, oder die Surface Hub-Sensoren erkennen, dass das Gerät verwendet wird, wird das ausstehende Update zum folgenden Wartungsfenster verschoben.
- Wenn das nächste Wartungsfenster nach dem zulässigen Zeitraum für die Installation des Updates liegt, berechnet das Gerät den nächsten verfügbaren freien Zeitraum während der Geschäftszeiten mithilfe der anhand der Updatemetadaten geschätzten Installationszeit. Das Update wird erneut verschoben, wenn eine Besprechung geplant ist oder die Surface Hub-Sensoren erkennen, dass das Gerät verwendet wird.
- If the next maintenance window is **not** past the update's grace period, the Surface Hub will continue to postpone the update.
- If a reboot is needed, the Surface Hub will automatically reboot during the next maintenance window.

> [!NOTE]
> Lassen Sie bei der Ersteinrichtung des Surface Hub genügend Zeit für Updates. Möglicherweise sind neue Virusdefinitionen verfügbar, die sofort installiert werden sollten.

A default maintenance window is set for all new Surface Hubs:
-   **Start time:** 2:00 AM
-   **Duration:** 2 hours

**To manually change the maintenance window:**
1.  Öffnen Sie auf dem Surface Hub **Einstellungen**.
2.  Navigieren Sie zu **Update und Sicherheit** > **Windows Update** > **Erweiterte Optionen**.
3.  Wählen Sie unter **Wartungsstunden** **Ändern** aus.

Um das Wartungsfenster mit MDM zu ändern, legen Sie den Knoten **MOMAgent** im [SurfaceHub-Konfigurationsdienstanbieter](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) fest See [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md) for more details.


## More information

- [Blog post: Servicing, Flighting, and Managing updates for Surface Hub (With Intune, of course!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Related topics

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub-Administratorhandbuch](surface-hub-administrators-guide.md)

