---
title: Windows 10 Team 2020 Update installieren
description: Erhalten Sie das neueste Update des Surface Hub-Betriebssystems, Windows 10 Team 2020 Update.
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
ms.openlocfilehash: 291a2eda0c1fa6e5e2fd2240861c8570d00054df
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319179"
---
# Windows 10 Team 2020 Update installieren 

Das neue Surface Hub-Betriebssystem, **Windows 10 Team 2020 Update,** basierend auf Windows 10, Version 20H2, ist jetzt für Surface Hub 2S und den ursprünglichen Surface Hub (v1) verfügbar. 

- Siehe auch: [Bekannte Probleme: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)

## Verteilung

Sie können Windows 2020 Update mit einer der folgenden Methoden abrufen:

- **Windows Update for Business**.
- **Bare-Metal-Wiederherstellungsabbild (Bare Metal Recovery, BMR).** Empfohlene Option für Kunden, die ihre Geräte mit Azure Active Directory verbinden oder nicht zulassen, dass ihre Geräte Updates aus dem Internet erhalten. Informationen zu den ersten Schritte finden Sie unter ["Herunterladen eines Wiederherstellungsimages für Ihr Surface".](https://support.microsoft.com/surfacerecoveryimage)
- **WindowsUpdate.** Die Verfügbarkeit variiert je nach Region/Land, wie in der folgenden Tabelle angegeben:

| Phase | Land/Region                         | Starten          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Australien, Kanada, Belgien, Mexiko | Oktober 2020  |
| 2     | Vereinigtes Königreich, Japan, Schweiz, Italien          | November 2020 |
| 3     | USA, Deutschland                            | Ende Februar 2021 |
| 4     | Global                                 | Ende Februar 2021 |

## Wartung von Surface Hubs mit Windows 10 Team Edition, Version 1703 

Der vollständige Wartungssupport [für Windows 10 Team Edition, Version 1703,](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) soll bis zum 16. März 2021 fortgesetzt werden.

### 2S-Geräte 

Kunden in allen Regionen können ihre Surface Hub 2S-Geräte mithilfe von Windows Update for Business oder mithilfe eines Bare-Metal-Wiederherstellungsimages (Bare Metal Recovery, BMR) weiterhin auf das 2020 Update aktualisieren, wie unter Zurücksetzen und Wiederherstellung für [Surface Hub 2S](surface-hub-2s-recover-reset.md)erläutert.

### V1-Geräte 

Kunden in allen Regionen können jetzt ihre Surface Hub v1-Geräte mithilfe des [Surface Hub-Wiederherstellungstools](surface-hub-recovery-tool.md)auf das 2020-Update aktualisieren. Andere Methoden zum Aktualisieren dieser Geräte auf das Windows 10 Team 2020 Update werden in Kürze verfügbar sein. Weitere Informationen finden Sie im [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655).
 
## Neuigkeiten 

Windows 10 Team 2020 Update bietet wesentliche Verbesserungen bei der Gerätebereitstellung und Verwaltbarkeit zusammen mit den neuesten Windows 10-Features. Weitere Informationen finden Sie unter ["Neues" in Windows 10 Team 2020 Update.](surface-hub-2020-update-whats-new.md)
 
## Vorbemerkungen

Stellen Sie vor der Installation von Windows 10 Team 2020 Update sicher, dass Sie den ihrem Gerät zugeordneten BitLocker-Schlüssel speichern. 

**So speichern Sie den BitLocker-Schlüssel manuell**

1. Fügen Sie ein USB-Laufwerk in Surface Hub ein.
2. Öffnen Sie auf Surface Hub **"Einstellungen",** und geben Sie ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
3. Navigieren Sie zu **Update & Security**  >  **Recovery**.
4. Wählen **Sie unter BitLocker**"Speichern" **aus.** Der BitLocker-Schlüssel wird in einer Textdatei auf dem USB-Laufwerk gespeichert.

Weitere Informationen finden Sie unter ["Speichern des BitLocker-Schlüssels".](save-bitlocker-key-surface-hub.md)

## Weitere Informationen

- [Neues in Windows10 Team2020-Update](surface-hub-2020-update-whats-new.md)
- [Aktualisieren auf das Windows 10 Team-Rollout](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
