---
title: Windows 10 Team 2020 Update installieren
description: Hier erhalten Sie das neueste Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470413"
---
# <a name="install-windows-10-team-2020-update"></a>Windows 10 Team 2020 Update installieren 

Das neue Surface Hub-Betriebssystem, **Windows 10 Team 2020 Update,** basierend auf Windows 10, Version 20H2, ist jetzt für Surface Hub 2S und den ursprünglichen Surface Hub (v1) verfügbar. 

- Siehe auch: [Bekannte Probleme: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>Verteilung

Sie können Windows 2020 Update mit einer der folgenden Methoden abrufen:

- **Windows Update for Business**.
- **Bare Metal Recovery (BMR) Image**. Empfohlene Option für Kunden, die ihre Geräte zu Azure Active Directory hinzufügen oder nicht zulassen, dass ihre Geräte Updates aus dem Internet erhalten. Informationen zu den ersten Schritte finden Sie unter [Herunterladen eines Wiederherstellungsimages für Surface](https://support.microsoft.com/surfacerecoveryimage).
- **WindowsUpdate.** Die Verfügbarkeit variiert je nach Region/Land, wie in der folgenden Tabelle angegeben:

| Phase | Land/Region                         | Starten          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Australien, Kanada, Belgien, Mexiko | Oktober 2020  |
| 2     | Großbritannien, Japan, Schweiz, Italien          | November 2020 |
| 3     | Deutschland, Niederlande                   | Ende Februar 2021 |
| 4     | Global                                 | Anfang März 2021 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Servicing Surface Hubs with Windows 10 Team Edition version 1703 

Die vollständige Wartungsunterstützung [für Windows 10 Team Edition, Version 1703,](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) wird voraussichtlich bis zum 16. März 2021 fortgesetzt.

### <a name="2s-devices"></a>2S-Geräte 

Kunden in allen Regionen können ihre Surface Hub 2S-Geräte auf das Update 2020 über Windows Update, Windows Update for Business oder mithilfe des Bare Metal Recovery (BMR)-Images aktualisieren, wie unter [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)erläutert.

### <a name="v1-devices"></a>V1-Geräte 

Kunden in allen Regionen können ihre Surface Hub v1-Geräte über Windows Update, Windows Update for Business oder mithilfe des Surface Hub-Wiederherstellungstools auf das 2020 Update [aktualisieren.](surface-hub-recovery-tool.md) KB5000749 muss installiert sein, um das Update über die Zeit zu erhalten. Weitere Informationen finden Sie unter [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## <a name="whats-new"></a>Neuigkeiten 

Windows 10 Team 2020 Update bietet neben den neuesten Windows 10-Features wesentliche Verbesserungen bei der Gerätebereitstellung und Verwaltbarkeit. Weitere Informationen finden Sie unter [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).
 
## <a name="before-you-begin"></a>Vorbemerkungen

Stellen Sie vor der Installation von Windows 10 Team 2020 Update sicher, dass Sie den Ihrem Gerät zugeordneten BitLocker-Schlüssel speichern. 

**So speichern Sie den BitLocker-Schlüssel manuell**

1. Fügen Sie ein USB-Laufwerk in Surface Hub ein.
2. Öffnen Sie auf Surface Hub **Einstellungen,** und geben Sie ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
3. Navigieren Sie zu **Update & Security**  >  **Recovery**.
4. Wählen **Sie unter BitLocker**die Option **Speichern aus.** Der BitLocker-Schlüssel wird in einer Textdatei auf dem USB-Laufwerk gespeichert.

Weitere Informationen finden Sie [unter Save your BitLocker key](save-bitlocker-key-surface-hub.md).

## <a name="learn-more"></a>Weitere Informationen

- [Neues in Windows10 Team2020-Update](surface-hub-2020-update-whats-new.md)
- [Aktualisieren auf das Windows 10 Team-Rollout](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
