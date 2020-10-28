---
title: Optimieren der WLAN-Konnektivität für Surface-Geräte
description: In diesem Thema werden empfohlene Wi-Fi Einstellungen beschrieben, um sicherzustellen, dass Oberflächen Geräte in überlasteten Netzwerkumgebungen und mobilen Szenarien in Verbindung bleiben.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.date: 10/26/2020
ms.openlocfilehash: d211ceea20b89824d45e433cf9670abe137130a0
ms.sourcegitcommit: 07ac65bf70c8c6efcda28eecc3013983fc386e0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136144"
---
# Optimieren der WLAN-Konnektivität für Surface-Geräte


Um mit der gesamten Lebensdauer der Batterie in Verbindung zu bleiben, implementieren Surface-Geräte drahtlose Verbindungseinstellungen, die die Leistung und Energieeinsparung abwägen. Außerhalb der anspruchsvollsten Mobilitätsszenarien können Benutzer eine ausreichende drahtlose Verbindung aufrecht erhalten, ohne den standardmäßigen Netzwerkadapter oder Verwandte Einstellungen zu ändern. Auf dieser Seite werden die wichtigsten Überlegungen zur drahtlosen Konnektivität in mobilen Szenarien unter Verwendung der neuesten Surface-Geräte wie Surface pro 7, Surface pro X, Surface Laptop 3, Surface Book 3, Surface Go 2 und Surface Laptop go hervorgehoben.  

## Voraussetzungen

In diesem Dokument wird davon ausgegangen, dass Sie erfolgreich ein Drahtlosnetzwerk bereitgestellt haben, das 802.11 n (Wi-Fi 4) oder höher unterstützt, entsprechend den Empfehlungen der führenden Gerätehersteller.

## Konfigurieren von Zugriffspunkten für optimale Roaming-Funktionen

Wenn Sie ein Drahtlosnetzwerk verwalten, auf das in der Regel viele verschiedene Arten von Clientgeräten zugreifen, wird empfohlen, bestimmte Protokolle auf Zugriffspunkten (APS) in Ihrem WLAN zu aktivieren, wie in [Fast-Roaming mit 802.11 k, 802.11 v und 802.11 r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)beschrieben. Surface-Geräte können die folgenden drahtlos Protokolle nutzen:

- **802.11 r.** "**Fast BSS-Übergang"** beschleunigt die Verbindung zu neuen Drahtloszugriffspunkten, indem die Anzahl der erforderlichen Frames verringert wird, bevor Ihr Gerät auf einen anderen AP zugreifen kann, während Sie sich mit Ihrem Gerät bewegen. In der neuen Generation von Surface-Geräten, die seit 2019 veröffentlicht wurden, erhalten Endbenutzer möglicherweise Zugriff auf Roaming-Aggressivität-Einstellungen auf Ihrem Gerät. Obwohl die Änderung der Standardeinstellungen nicht empfohlen wird, sollten die Benutzer diese Funktion kennen und wissen, wie sich bestimmte Einstellungen auf die Möglichkeit auswirken, verbunden zu bleiben.
- **802.11 k.** **"Nachbar Berichte"** bietet Geräte mit Informationen zu den aktuellen Bedingungen an benachbarten Zugriffspunkten. Sie kann Ihrem Surface-Gerät helfen, den besten AP zu wählen, wobei andere Kriterien als die Signalstärke, wie etwa die AP-Nutzung, verwendet werden.

Bestimmte Oberflächen Geräte können auch 802.11 v "BSS Transition Management Frames" verwenden, die ähnlich wie 802.11 k in der Bereitstellung von Informationen zu den in der Nähe befindlichen Bewerber-APS funktionieren. Dazu gehören Surface go, Surface pro 7, Surface pro X und Surface Laptop 3. 

## Verwalten von Benutzereinstellungen

Sie können optimale Roaming-Funktionen über ein gut konzipiertes Netzwerk erreichen, das 802.11 r und 802.11 k über alle Zugriffspunkte unterstützt. Wenn Sie sicherstellen möchten, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist, um Benutzern optimale WLAN-Funktionalität bereitzustellen, empfiehlt es sich, die Benutzereinstellungen auf einzelnen Geräten zu verwalten. 

### Empfohlene Benutzereinstellungen und bewährte Methoden

In bestimmten Situationen kann das ändern erweiterter Netzwerkadaptereinstellungen, die in Surface-Geräte integriert sind, zu einer zuverlässigeren Verbindung beitragen. Beachten Sie jedoch, dass die Unfähigkeit, eine Verbindung zu drahtlos Ressourcen herzustellen, häufiger auf ein Problem mit einem Zugriffspunkt, einen Fehler beim Netzwerk Design oder auf ein Problem mit der Umgebungs Website zurückzuführen ist.

> [!NOTE]
> Die Art und Weise, wie Sie die Oberfläche pro oder Surface go halten, kann auch die Signalstärke beeinflussen. Wenn die Bandbreite verloren geht, vergewissern Sie sich, dass Sie nicht den oberen Bildschirmrand, in dem sich der Wi-Fi Funkempfänger befindet, halten. Obwohl der obere Rand der Anzeige keine Funksignale blockiert, kann er den Gerätetreiber auslösen, um Änderungen zu initiieren, die die Konnektivität reduzieren.

### Beibehalten der automatischen Standardeinstellung für die duale Bandbreiten Funktion

Auf den meisten Surface-Geräten können Sie die Einstellungen für den Client-Netzwerkadapter so konfigurieren, dass nur Verbindungen mit WLAN-APS über 5 Gigahertz (GHz) hergestellt werden, nur eine Verbindung über 2,4 GHz hergestellt wird oder das Betriebssystem die beste Option auswählen kann (Standardeinstellung für Auto).

**Um auf die Einstellungen des Netzwerkadapters zuzugreifen, gehen Sie zu:**

- **Anfang**  >  **Systemsteuerung**  >  **Netzwerk-und Freigabe Center**  >  **Ihr Wi-Fi-Adapter**  >  **Eigenschaften**  >  **Konfigurieren**  >  von **Erweitert**.

![* WiFi-Band-Einstellungen *](images/wifi-band.png) <br>

Beachten Sie, dass 2,4 GHz einige Vorteile von mehr als 5 GHz hat: es dehnt sich weiter aus und dringt leichter durch Wände oder andere massive Objekte. Sofern Sie keinen eindeutigen Anwendungsfall haben, der eine Verbindung mit 5 GHz gewährleistet, empfiehlt es sich, die Band Einstellung im Standardzustand zu belassen, um mögliche negative Auswirkungen zu vermeiden. Zum Beispiel:


- Viele Hotspots, die in Hotels, Cafés und Flughäfen zu finden sind, verwenden weiterhin nur 2,4 GHz, wodurch der Zugriff auf Geräte effektiv blockiert wird, wenn Band nur auf 5 GHz festgesetzt ist.
- Da die Miracast-drahtlos Anzeige Verbindungen erfordern, dass der erste Handshake auf 2,4 GHz-Kanälen abgeschlossen wird, können Geräte keine Verbindung mit nur 5 GHz herstellen.

> [!NOTE]
> Standardmäßig wird für Surface Devices die Verbindung zu 5 GHz bevorzugt, falls verfügbar. Um die Stromversorgung jedoch in einem geringen Batteriezustand zu erhalten, sucht Surface zunächst nach einer 2,4 GHz-Verbindung.

Sie können die Bandeinstellung auch so umschalten, wie es für Ihre Umgebung erforderlich ist. Benutzer, die in einem Apartmentgebäude mit hoher Dichte mit mehreren Wi-Fi-Hotspots Leben – unter dem vorhanden sein von Consumer-Geräten, die alle über 2,4 GHz übertragen – können beispielsweise davon profitieren, wenn Sie das Surface-Gerät so einrichten, dass nur 5 GHz verbunden werden, und dann bei Bedarf auf Auto zurückgreifen.

### Einstellungen für Roaming-Aggressivität auf Surface-Geräten mit Intel-Adaptern 

Benutzer möchten möglicherweise einen Schwellenwert für die Signalstärke auswählen, der das Gerät auffordert, nach einem neuen Zugriffspunkt zu suchen, wenn das Signal abfällt (Roaming-Aggressivität). Standardmäßig versuchen Surface-Geräte mit Intel-Adaptern, zu einem neuen Zugriffspunkt zu wechseln, wenn die Signalstärke unter **Mittel** fällt (72 Prozent Signalstärke). Beachten Sie außerdem, dass Organisationen speziell erstellte drahtlos Protokolle über mehrere Netzwerkzugriffspunkte hinweg implementieren können, um Roaming-Netzwerkumgebungen zu vereinfachen, wie weiter oben auf dieser Seite erläutert. 

Während die zunehmende Roaming-Aggressivität über **Medium** zu einer verbesserten Konnektivität in stark überlasteten Office-oder Residential-Umgebungen führen kann, kann dies zu einer beeinträchtigten Konnektivität führen, wenn Sie außerhalb dieser Umgebungen treten. 

Es wird empfohlen, die Einstellung Roaming-Aggressivität im Standardzustand zu belassen, es sei denn, es treten Verbindungsprobleme in bestimmten mobilen Szenarien auf, beispielsweise das Durchführen von Umgebungs Inspektionen bei der Website und die Beibehaltung der Sprach-und Video Konnektivität während einer Konferenz Besprechung. Wenn Sie keine Verbesserung bemerken, kehren Sie zum standardmäßigen mittleren Zustand zurück. Beachten Sie, dass Sie beim Erhöhen der Aggressivität des Roamings auch den Energieverbrauch der Batterie verkürzen. 

**So aktivieren Sie Roaming-Aggressivität auf der Oberfläche:**

1. Wechseln Sie **Start**zu  >  **Geräte-Manager**starten.
2. Wählen Sie unter **Netzwerkadapter** die Option **Intel Wi-Fi 6** und dann mit der rechten Maustaste auf **Eigenschaften**.
3. Wählen Sie die Registerkarte **erweitert** aus.
4. Wählen Sie **Roaming-Aggressivität** aus, und wählen Sie den gewünschten Wert aus dem Dropdown-Menü aus.

![* Roaming-Aggressivität-Einstellungen – Intel *](images/wifi-roaming-int.png) <br>

### Einstellungen für Roaming-Aggressivität auf Surface Go und Surface pro X

Front-Work-Mitarbeiter mit Surface go möchten möglicherweise einen Schwellenwert für die Signalstärke auswählen, der das Gerät auffordert, nach einem neuen Zugriffspunkt zu suchen, wenn die Signalstärke sinkt (Roaming-Aggressivität). Standardmäßig versuchen Surface-Geräte, zu einem neuen Zugriffspunkt zu wechseln, wenn die Signalstärke unter **Mittel** fällt (50 Prozent Signalstärke). Beachten Sie, dass Sie bei jeder Erhöhung der Aggressivität des Roamings den Akkuverbrauch beschleunigen.

Belassen Sie die Einstellung Roaming-Aggressivität im Standardzustand, es sei denn, Sie stoßen auf Verbindungsprobleme in bestimmten mobilen Szenarien, wie beispielsweise die Durchführung von Umgebungs Inspektionen und gleichzeitig die Sprach-und Video Konnektivität während einer Konferenz Besprechung. Wenn Sie keine Verbesserung bemerken, kehren Sie zum standardmäßigen **Mittel** Zustand zurück.

**So aktivieren Sie Roaming-Aggressivität auf Surface go:**

1. Wechseln Sie zu **Start > Control Panel**-  >  **Netzwerk und Internet**  >  **-Netzwerk-und Freigabe Center.**
2. Wählen Sie unter **Verbindungen** die Option **WLAN** und dann **Eigenschaften aus.**
3. Wählen Sie **Client für Microsoft Networks** und dann **Konfigurieren** aus.
4. Wählen Sie **Erweiterte**  >  **Roaming-Aggressivität** aus, und wählen Sie den gewünschten Wert aus dem Dropdownmenü aus.

![* Roaming-Aggressivität-Einstellungen-Qualcomm *](images/wifi-roaming.png) <br>


## Fazit

Surface-Geräte sind mit Standardeinstellungen für optimale drahtlose Konnektivität sowie mit der Notwendigkeit, die Akkulaufzeit zu gewährleisten, abgestimmt. Die effektivste Methode, um zuverlässige Konnektivität für Surface-Geräte zu ermöglichen, besteht in einem gut durchdachten Netzwerk, das 802.11 r und 802.11 k unterstützt. Benutzer können die Einstellungen des Netzwerkadapters oder die Roaming-Aggressivität anpassen, sollten dies aber nur als Reaktion auf bestimmte Umgebungsfaktoren tun und den Standardzustand wiederherstellen, wenn keine nennenswerten Verbesserungen bestehen.
