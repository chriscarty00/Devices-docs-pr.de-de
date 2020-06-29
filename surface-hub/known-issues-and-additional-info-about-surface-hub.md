---
title: Bekannte Probleme und weitere Informationen zu Microsoft Surface Hub
description: Beschreibt bekannte Probleme mit Microsoft Surface Hub.
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: Surface, Hub, Issues
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833091"
---
# Bekannte Probleme und weitere Informationen zu Microsoft Surface Hub

Wir hören zu. Qualität hat oberste Priorität, und wir möchten Sie über Probleme informieren, die sich auf Kunden auswirken. Im folgenden sind einige bekannte Probleme mit Microsoft Surface Hub zu finden:

- **Skype for Business verwendet keinen Proxy für Mediendatenverkehr mit RS2**
<br/>Für einige Surface Hub-Benutzer, die sich hinter einem Proxy befinden, verwendet Skype for Business nicht den Proxy Server für Medien. Der Surface-Hub kann sich jedoch bei dem Konto anmelden. Wir haben Ihr Feedback erhalten und sind uns des Problems des Medien Verkehrs bewusst, wenn Sie einen Proxy verwenden. Wir untersuchen dieses Problem aktiv und beheben Updates, sobald eine Lösung identifiziert und getestet wird. 

- **Wenn ein Benutzer versucht, sich bei Aad-verbundenen Geräten bei "meine Besprechungen & Dateien" anzumeldet, meldet Surface Hub, dass keine Internet Verbindung besteht.**
<br/>Wir sind uns einer Reihe von Problemen bewusst, die sich auf die Anmeldung und den Dokumentenzugriff auf Surface Hub auswirken. Wir untersuchen diese Probleme aktiv. Als Problemumgehung, bis eine Lösung freigegeben wurde, können Kunden ihre Geräte zurücksetzen und ihren Hub so einrichten, dass ein lokales Administratorkonto verwendet wird. Nach der Neukonfiguration zur Verwendung des lokalen Administratorkontos funktionieren "meine Besprechungen und Dateien" wie erwartet.
- **Einmaliges Anmelden, wenn Azure AD beigetreten ist**
<br/>Surface Hub wurde für kommunale Räume entwickelt, was Auswirkungen auf die Speicherung von Benutzeranmeldeinformationen hat. Aus diesem Grund gibt es derzeit Einschränkungen bei der Funktionsweise der einmaligen Anmeldung, wenn die Geräte Azure AD beigetreten sind. Microsoft ist sich dieser Einschränkung bewusst und untersucht aktiv die Optionen für eine Lösung.
- **Miracast über Infrastruktur Projektion auf Surface Hub schlägt fehl, wenn der DGM-Hub ein Punkt Zeichen (.) im Anzeigenamen aufweist.**
<br/>Benutzer von Surface Hub können Probleme beim projizieren auf Ihr Gerät auftreten, wenn der Anzeigename einen Punkt oder Punkt im Namen (.) enthält (.)--beispielsweise "conf. Room42". Um das Problem zu umgehen, ändern Sie den Anzeigenamen des Hubs unter **Einstellungen**  >  **Surface Hub**  >  **About**, und starten Sie dann das Gerät neu. Microsoft arbeitet an einer Lösung für dieses Problem.