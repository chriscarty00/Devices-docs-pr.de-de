---
title: Windows 10 Team 2020 Update installieren
description: Holen Sie sich das neueste Update des Surface Hub-Betriebssystems, Windows 10 Team 2020-Update.
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
ms.openlocfilehash: b3f1f0884273728abc8b4f6e8662190dacdaf2b2
ms.sourcegitcommit: 8c75e57dc32eaf7c11cb9badea74809fd3877ffc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "11253964"
---
# Windows 10 Team 2020 Update installieren 

Das neue Surface Hub-Betriebssystem, **Windows 10 Team 2020-Update**, basierend auf Windows 10-Version 20H2, ist jetzt für alle Surface-Hub-2S-Geräte verfügbar.  

- Siehe auch: [bekannte Probleme: Windows 10 Team 2020-Update](surface-hub-2020-update.md)

## Verteilung

Sie können Windows 2020-Update mithilfe einer der folgenden Methoden abrufen:

- **Windows Update für Unternehmen**.
- **Abbildung des Bare Metal Recovery (GU)**. Empfohlene Option für Kunden, die Ihre Geräte mit Azure Active Directory verbinden oder Ihren Geräten nicht gestatten, Updates aus dem Internet zu erhalten. Informationen zu den ersten Schritten finden Sie unter [Herunterladen eines Wiederherstellungs Bilds für Ihre Oberfläche](https://support.microsoft.com/surfacerecoveryimage).
- **WindowsUpdate.** Die Verfügbarkeit variiert je nach Region/Land, wie in der folgenden Tabelle angegeben:

| Phase | Land/Region                         | Ausgangs          |
| ----- | -------------------------------------- | ----------------- |
| 1     | Neuseeland, Australien, Kanada, Belgien, Mexiko | 27. Oktober 2020  |
| 2     | Großbritannien, Japan, Schweiz, Italien          | 10. November 2020 |
| 3     | USA, Deutschland                            | TBD |
| 4     | Globalen                                 | TBD  |

## Wartungs Oberflächen-Hubs mit Windows 10 Team Edition, Version 1703 

Der vollständige Wartungs Support für Windows 10 Team Edition, Version 1703, soll bis zum 16. März 2021 fortgesetzt werden.

### 2S-Geräte 

Kunden in allen Regionen können Ihre Surface-Hub-2S-Geräte weiterhin auf das 2020-Update unter Verwendung von Windows Update for Business oder mit einem unbaren Metall Wiederherstellungsbild (grundlegendes) aktualisieren, wie unter [Zurücksetzen und Wiederherstellen für Surface Hub 2S](surface-hub-2s-recover-reset.md)erläutert wird.

### V1-Geräte 

Kunden in allen Regionen können nun ihre Surface-Hub-v1-Geräte auf das 2020-Update [mithilfe des Surface Hub-Wiederherstellungstools](surface-hub-recovery-tool.md)aktualisieren. Andere Methoden zum Aktualisieren dieser Geräte auf das Windows 10-Team 2020-Update sind in Kürze verfügbar. Weitere Informationen finden Sie unter [Surface IT pro-Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update/ba-p/2000144).
 
## Neuigkeiten 

Das Windows 10-Team 2020-Update bietet wichtige Verbesserungen bei der Gerätebereitstellung und-Verwaltbarkeit zusammen mit den neuesten Windows 10-Features. Weitere Informationen finden Sie unter [Neuerungen in Windows 10 Team 2020-Update](surface-hub-2020-update-whats-new.md).
 
## Vorbemerkungen

Stellen Sie vor der Installation des Windows 10 Team 2020-Updates sicher, dass Sie den BitLocker-Schlüssel speichern, der Ihrem Gerät zugeordnet ist. 

**So speichern Sie den BitLocker-Schlüssel manuell**

1. Legen Sie ein USB-Laufwerk in Surface Hub ein.
2. Öffnen Sie auf Surface Hub die **Einstellungen** , und geben Sie Ihre Administratoranmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
3. Navigieren Sie zu **Update & Security**  >  **Recovery**.
4. Wählen Sie unter **BitLocker**die Option **Speichern**aus. Der BitLocker-Schlüssel wird in einer Textdatei auf dem USB-Laufwerk gespeichert.

Weitere Informationen finden Sie unter [Speichern des BitLocker-Schlüssels](save-bitlocker-key-surface-hub.md).

## Mehr erfahren

- [Bekannte Probleme: Windows 10 Team 2020-Update](surface-hub-2020-update.md)
- [Wichtige Updates auf dem Surface Hub Windows 10 Team 2020-Update](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/important-updates-on-the-surface-hub-windows-10-team-2020-update/ba-p/1960897)
