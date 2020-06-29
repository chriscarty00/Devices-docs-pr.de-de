---
title: Verwenden eines vollständig qualifizierten Domänennamens mit Surface Hub
description: Behandeln Sie allgemeine Probleme, u.a. Probleme bei der Einrichtung und Exchange ActiveSync-Fehler.
keywords:
- Behandeln von allgemeinen Problemen
- Probleme bei der Einrichtung
- Exchange ActiveSync-Fehler
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832656"
---
# Konfigurieren des Domänennamens für Skype for Business

Es gibt einige Szenarien, in denen Sie den Domänennamen Ihres Skype for Business-Servers angeben müssen:
- **Mehrere DNS-Suffixe**: Wenn Ihre Skype for Business-Infrastruktur zusammenhanglose Namespaces enthält, sodass mindestens ein Server ein DNS-Suffix besitzt, das nicht mit dem Suffix der Anmeldeadresse (SIP) für Skype for Business übereinstimmt.  
- **Unterschiedliche Suffixe für Skype for Business und Exchange**: Wenn das Suffix der Anmeldeadresse für Skype for Business vom Suffix der Exchange-Adresse abweicht, die für das Gerätekonto verwendet wurde.
- **Arbeiten mit Zertifikaten** – große Organisationen mit lokalen Skype for Business-Servern verwenden häufig Zertifikate mit ihrer eigenen Stammzertifizierungsstelle (Certification Authority, ca). Üblicherweise weicht die Domäne der Zertifizierungsstelle von der Domäne des Skype for Business-Servers ab. Daher wird das Zertifikat als nicht vertrauenswürdig angesehen, und bei der Anmeldung tritt ein Fehler auf.  Skype muss den Domänennamen des Zertifikats kennen, um eine Vertrauensstellung einrichten zu können. Unternehmen verwenden in der Regel Gruppenrichtlinien, um diesen Namen per Push an den Skype-Desktopclient zu senden. Gruppenrichtlinien werden auf Surface Hub jedoch nicht unterstützt.

**So konfigurieren Sie den Domänennamen für Ihren Skype for Business-Server**</br>
1. Öffnen Sie auf Surface Hub **Einstellungen**.
2. Klicken Sie auf **Surface Hub**, und klicken Sie dann auf **Anrufe und Audio**. 
3. Klicken Sie unter **Skype for Business-Konfiguration** auf **Domänennamen konfigurieren**. 
4. Geben Sie den Domänennamen für Ihren Skype for Business-Server ein, und klicken Sie dann auf **OK**. 
   > [!TIP]
   > Sie können mehrere Domänennamen durch Kommas getrennt eingeben. <br> Beispiel: lync.com, outlook.com, lync.glbdns.microsoft.com

    ![Hinzufügen von Skype for Business-FQDN zu Einstellungen](images/system-settings-add-fqdn.png)
