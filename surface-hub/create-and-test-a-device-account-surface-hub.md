---
title: Erstellen und Testen eines Gerätekontos (Surface Hub)
description: In diesem Thema wird vorgestellt, wie Sie das Gerätekonto erstellen und testen können, das Microsoft Surface Hub für die Kommunikation mit Microsoft Exchange und Skype verwendet.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: Erstellen und Testen eines Gerätekonto, Gerätekonto, Surface Hub und Microsoft Exchange, Surface Hub und Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833772"
---
# Erstellen und Testen eines Gerätekontos (Surface Hub)


In diesem Thema wird vorgestellt, wie Sie das Gerätekonto erstellen und testen können, das Microsoft Surface Hub für die Kommunikation mit Microsoft Exchange und Skype verwendet.

Ein **Gerätekonto** ist ein Exchange-Ressourcenkonto, das Surface Hub zu folgenden Zwecken verwendet:

-   Anzeigen des Besprechungskalenders
-   Teilnahme an Teams oder Skype for Business-anrufen
-   Senden von E-Mails (z.B. mit Whiteboard-Inhalten aus einer Besprechung)

Nachdem das Gerätekonto für einen Surface Hub bereitgestellt wurde, können Benutzer dieses Konto einer Besprechungseinladung auf die gleiche Weise hinzufügen, wie sie einen Besprechungsraum hinzufügen würden. 

## Konfigurationsübersicht

In der folgenden Tabelle werden die wichtigsten Schritteund Konfigurationsentscheidungen beim Erstellen eines Gerätekontos beschrieben. 
 
| Schritt | Beschreibung                     |  Zweck                             |
|------|---------------------------------|--------------------------------------|
| 1    | Erstellen eines für Anmeldungen aktivierten Exchange-Ressourcenpostfachs (Exchange2013 oder höher oder Exchange Online) | Dieses Ressourcenpostfach ermöglicht dem Gerät das Warten eines Besprechungskalenders, das Empfangen von Besprechungsanfragen und das Senden von E-Mails. Es muss für Anmeldungen aktiviert sein, um für einen Surface Hub bereitgestellt werden zu können. |
| 2    | Konfigurieren der Postfacheigenschaften | Das Postfach muss mit den richtigen Eigenschaften konfiguriert sein, um eine optimale Besprechungserfahrung auf Surface Hub zu ermöglichen. Weitere Informationen zu Postfacheigenschaften finden Sie unter [Postfacheigenschaften](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Anwenden einer Postfachrichtlinie für kompatible mobile Geräte für das Postfach | Surface Hub wird mithilfe der mobilen Geräteverwaltung (Mobile Device Management, MDM) verwaltet und nicht über Postfachrichtlinien für mobile Geräte. Um die Kompatibilität zu gewährleisten, muss das Gerätekonto über eine Postfachrichtlinie für mobile Geräte verfügen, in der die Einstellung **PasswordEnabled** auf „false“ festgelegt ist. Andernfalls kann Surface Hub E-Mail- und Kalenderinformationen nicht synchronisieren. |
| 4    | Aktivieren des Postfachs mit Skype for Business (Lync Server2013 oder höher oder Skype for Business Online) | Skype for Business muss aktiviert sein, um Konferenzfeatures wie Videoanrufe, Sofortnachrichten und Bildschirmfreigabe zu verwenden.  |
| 5    | (Optional) Eintragen der ActiveSync-Geräte-ID in die Whitelist | Ihre Organisation verfügt möglicherweise über eine globale Richtlinie, die das Synchronisieren von E-Mails und Kalenderinformationen durch Gerätekonten verhindert. In diesem Fall müssen Sie die ActiveSync-Geräte-ID Ihres Surface-Hubs zulassen. |
| 6    | (Optional) Deaktivieren des Kennwortablaufs | Um die Verwaltung zu vereinfachen, können Sie den Kennwortablauf für das Gerätekonto deaktivieren und Surface Hub für das automatische Rotieren des Kennworts für das Gerätekonto aktivieren. Weitere Informationen zur Kennwortverwaltung finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).  |

## Details zu den Konfigurationsschritten 

Wir empfehlen, Gerätekonten mithilfe von Remote-PowerShell einzurichten. Es sind PowerShell-Skripts verfügbar, die das Erstellen und Überprüfen von Gerätekonten unterstützen. Weitere Informationen zu PowerShell-Skripts und -Anweisungen finden Sie in [AnhangA: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md). 

Weitere Details zur Bereitstellung von Gerätekonten mithilfe von PowerShell erhalten Sie, indem Sie entsprechend der Art der Bereitstellung in Ihrer Organisation eine Option aus der Tabelle auswählen. 

| Art der Bereitstellung in der Organisation             |  Beschreibung                  |
|---------------------------------|--------------------------------------|
| [Onlinebereitstellung (Office365)](online-deployment-surface-hub-device-accounts.md) | Die Umgebung Ihrer Organisation wird vollständig auf Office365 bereitgestellt. |
| [Lokale Bereitstellung (einzelne Gesamtstruktur)](on-premises-deployment-surface-hub-device-accounts.md) | Ihre Organisation verfügt über Server, die von ihr gesteuert werden, und verwendet diese, um Active Directory, Exchange und Skype for Business (oder Lync) in einer einzelnen Gesamtstruktur zu hosten. |
| [Lokale Bereitstellung (mehrere Gesamtstrukturen)](on-premises-deployment-surface-hub-multi-forest.md) | Ihre Organisation verfügt über Server, die von ihr gesteuert werden, und verwendet diese, um Active Directory, Exchange und Skype for Business (oder Lync) in einer mehreren Gesamtstruktur zu hosten. |
| [Hybridbereitstellung](hybrid-deployment-surface-hub-device-accounts.md) | Ihre Organisation verfügt über verschiedene Dienste, von denen einige lokal und einige online über Office365 gehostet werden. |
| [Online- oder Hybridbereitstellung mithilfe von Skype-Hybrid-Voice-Umgebung](skype-hybrid-voice.md) | Ihre Organisation hat Skype for Business-Home-Pools und Exchange-Server in der Cloud und verwendet einen lokalen Pool von Skype for Business 2015 oder Cloud Connector Edition, der über PSTN (Public Switched Telephone Network) verbunden ist. |


Wenn Sie eine grafische Benutzeroberfläche (UI) bevorzugen, können einige Schritte in der UI statt mithilfe von PowerShell ausgeführt werden. Weitere Informationen finden Sie unter [Erstellen eines Gerätekontos mithilfe der UI](create-a-device-account-using-office-365.md).

## Kontoüberprüfung und Test

Es gibt zwei Methoden, um ein Gerätekonto für Surface Hub zu überprüfen und zu testen: [Kontovalidierungsskripts](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) und [Hardwarediagnose-App für Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g). Das Kontovalidierungsskript überprüft ein zuvor erstelltes Gerätekonto mithilfe von PowerShell vom Desktop aus. Die Hardwarediagnose-App für Surface Hub ist auf dem Surface Hub installiert und übermittelt detailliertes Feedback in puncto Fehler bei der Anmeldung und Kommunikation. Beide Tools sind wertvoll, um neu erstellte Gerätekonten zu testen und sollten verwendet werden, um eine optimale Konto-Verfügbarkeit sicherzustellen.

 

 

 





