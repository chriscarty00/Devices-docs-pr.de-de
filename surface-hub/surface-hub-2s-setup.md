---
title: Erstmaliges Einrichten von Surface Hub 2S
description: Erfahren Sie, wie Sie das erstmalige Setup für Surface Hub 2S abschließen.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833610"
---
# Erstmaliges Einrichten von Surface Hub 2S

Wenn Sie Surface Hub 2S zum ersten Mal starten, wechselt das Gerät automatisch in den erstmaligen Setup Modus, um Sie durch die Kontokonfiguration und die zugehörigen Einstellungen zu führen.

## Konfigurieren des Surface Hub 2S-Kontos

1. **Konfigurieren Sie Ihr Gebietsschema.** Geben Sie Region, Sprache, Tastaturlayout und Zeitzoneninformationen ein. Wählen Sie **Weiter** aus.

   ![* Konfigurieren Ihres Gebietsschemas *](images/sh2-run1.png) <br>
1. **Herstellen einer Verbindung mit einem Drahtlosnetzwerk** Wählen Sie Ihr bevorzugtes Drahtlosnetzwerk aus, und wählen Sie **weiter aus.**

- Diese Option wird nicht angezeigt, wenn Sie über ein Ethernet-Kabel verbunden sind.
- Sie können keine Verbindung zu einem Drahtlosnetzwerk in Hotspots (Captive Portals) herstellen, die Anmeldeanfragen an die Website eines Anbieters umleiten.

3. **Geben Sie Geräte Kontoinformationen ein.** Verwenden Sie **Domäne \** Benutzer für lokale und Hybrid Umgebungen sowie für **Benutzer \ @example. com** für Online-Umgebungen. Wählen Sie **weiter aus.**

   ![* Geben Sie Geräte Kontoinformationen ein *](images/sh2-run2.png) <br>
1. **Geben Sie zusätzliche Informationen ein.** Geben Sie bei Bedarf Ihre Exchange Server-Adresse ein, und wählen Sie dann **weiter aus.**

    ![* Geben Sie weitere Informationen ein; Beispiel: Exchange Servername *](images/sh2-run3.png) <br>

1. **Benennen Sie dieses Gerät.** Geben Sie einen Namen für Ihr Gerät ein, oder verwenden Sie den vorgeschlagenen Namen basierend auf dem Anzeige Namen und dem Benutzerprinzipalnamen des Kontos. **Wählen Sie weiter aus**.

- Der **Anzeigename** wird in der unteren linken Ecke von Surface Hub 2S angezeigt und beim projizieren auf das Gerät angezeigt.

- Der **Gerätename** identifiziert das Gerät, wenn es mit Active Directory oder Azure Active Directory verbunden ist, und beim Registrieren des Geräts mit InTune.

  ![* Name dieses Geräts *](images/sh2-run4.png) <br>
 
## Konfigurieren von Geräteadministrator Konten

Sie können geräteadministratoren nur während der erstmaligen Einrichtung einrichten. Weitere Informationen finden Sie unter [Surface Hub 2S Device Affiliation](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).

 Wählen Sie im Fenster **Setup-Administratoren für dieses Gerät** eine der folgenden Optionen aus: Active Directory-Domänendienste, Azure Active Directory oder lokaler Administrator.

   ![* Setup-Administratoren für dieses Gerät *](images/sh2-run5.png) <br>

### Active Directory Domain Services

1. Geben Sie die Anmeldeinformationen eines Benutzers ein, der über die Berechtigung zum Beitritt des Geräts zu Active Directory verfügt.

    ![* Setup-Administratoren mithilfe von Domain Join *](images/sh2-run6.png) <br>

2. Wählen Sie die Active Directory-Sicherheitsgruppe aus, die Mitglieder enthält, die sich bei der Einstellungs-APP auf Surface Hub 2S anmelden dürfen.

    ![* Geben Sie eine Sicherheitsgruppe ein *](images/sh2-run7.png) <br>
1. Wählen Sie **Fertig stellen**aus. Das Gerät wird neu gestartet.

### Azure Active Directory

Wenn Sie sich für die Partnereinrichtung Ihres Geräts mit Azure Active Directory entscheiden, wird das Gerät sofort neu gestartet und die folgende Seite angezeigt. Wählen Sie **Weiter** aus.

![* Wenn Ihre Organisation Office 365 oder andere Unternehmensdienste von Microsoft verwendet, werden wir dieses Gerät für Ihre Organisation * registrieren. *](images/sh2-run8.png) <br>

1. Geben Sie die e-Mail-Adresse oder den UPN eines Kontos **bei InTune Plan 1** oder höher ein, und wählen Sie dann **weiter aus.**

    ![* Geben Sie ein Geschäfts-oder Schulkonto ein *](images/sh2-run9.png) <br>

2. Wenn umgeleitet, authentifizieren Sie sich mithilfe der Anmeldeseite Ihrer Organisation, und geben Sie bei Bedarf zusätzliche Anmeldeinformationen an. Das Gerät wird neu gestartet.

## Lokales Administrator Konto

- Geben Sie einen Benutzernamen und ein Kennwort für Ihren lokalen Administrator ein. Das Gerät wird neu gestartet.

     ![* Einrichten eines Administratorkontos *](images/sh2-run10.png) <br>
 
## Verwenden von Bereitstellungspaketen

Wenn Sie ein USB-Daumen Laufwerk mit einem Bereitstellungspaket in einen der USB-Anschlüsse einfügen, wenn Sie Surface Hub 2S starten, zeigt das Gerät die folgende Seite an.

1. Geben Sie die gewünschten Einstellungen ein, und wählen Sie **Einrichten**aus.

    ![* Geben Sie die regionalen Einstellungen für das Bereitstellungspaket ein *](images/sh2-run11.png) <br>

    ![* Bereitstellung dieses Geräts auf Wechselmedien *](images/sh2-run12.png) <br>
2. Wählen Sie das Bereitstellungspaket aus, das Sie verwenden möchten.

   ![* Wählen Sie das zu verwendende Bereitstellungspaket * aus.](images/sh2-run13.png) <br>

3. Wenn Sie eine CSV-Datei mit mehreren Geräten erstellt haben, können Sie eine Gerätekonfiguration auswählen. Weitere Informationen finden Sie unter [Erstellen von Bereitstellungspaketen für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).


    ![* Wählen Sie ein Geräte Konto und einen Anzeigenamen aus Ihrer Konfigurationsdatei * aus.](images/sh2-run14.png) <br>

4. Folgen Sie den Anweisungen, um die erstmalige Einrichtung abzuschließen.
