---
title: Überwachen von Microsoft Surface Hub
description: Die Überwachung für Microsoft Surface Hub-Geräte wird über Microsoft Operations Management Suite (OMS) aktiviert.
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub überwachen, Microsoft Operations Management Suite, OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833652"
---
# Überwachen von Microsoft Surface Hub

Die Überwachung für Microsoft Surface Hub-Geräte wird über Microsoft Operations Management Suite (OMS) aktiviert. Die [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138) ist die IT-Verwaltungslösung von Microsoft zur Verwaltung und zum Schutz der gesamten IT-Infrastruktur einschließlich Surface Hubs.


Surface Hub wird in OMS als Log Analytics-Lösung angeboten und ermöglicht das Sammeln und Anzeigen von Nutzungs- und Zuverlässigkeitsdaten für alle Surface Hubs. Verwenden Sie die Surface Hub-Lösung für folgende Zwecke:
- Inventarisieren von Surface Hubs
- Anzeigen einer Momentaufnahme mit Nutzungs- und Zuverlässigkeitsdaten für Skype Besprechungen, kabelgebundene und drahtlose Projektionen und Apps auf Surface Hubs
- Erstellen benutzerdefinierter Warnungen, um schnell zu reagieren, wenn von Surface Hubs Software- oder Hardwareprobleme gemeldet werden

## Hinzufügen von Surface Hub zu Operations Management Suite

1. **Melden Sie sich bei Operations Management Suite (OMS) an**. Sie können entweder ein Microsoft-Konto oder ein Geschäfts-, Schul- oder Unikonto zum Erstellen eines Arbeitsbereichs verwenden. Wenn Ihr Unternehmen bereits Azure Active Directory (Azure AD) nutzt, verwenden Sie zur Anmeldung bei OMS ein Geschäfts-, Schul- oder Unikonto. Bei Verwendung eines Geschäfts-, Schul- oder Unikontos können Sie Azure AD-Identitäten zum Verwalten von Berechtigungen in OMS nutzen.
2. **Erstellen Sie einen neuen OMS-Arbeitsbereich**. Geben Sie einen Namen für den Arbeitsbereich ein, wählen Sie die Arbeitsbereichsregion aus, und geben Sie die E-Mail-Adresse ein, die diesem Arbeitsbereich zugeordnet werden soll. Wählen Sie **Erstellen** aus.
3. **Verknüpfen Sie ein Azure-Abonnement mit Ihrem Arbeitsbereich**. Wenn Ihre Organisation bereits über ein Azure-Abonnement verfügt, können Sie es mit dem Arbeitsbereich verknüpfen. Möglicherweise müssen Sie vom Azure-Administrator Ihrer Organisation eine Zugriffsberechtigung anfordern.

    > [!NOTE] 
    > Wenn Ihre Organisation kein Azure-Abonnement besitzt, erstellen Sie ein neues Abonnement oder wählen das standardmäßige OMS-Azure-Abonnement aus der Liste aus. Der Arbeitsbereich wird geöffnet.

4. **Fügen Sie eine Surface Hub-Lösung hinzu**. Wählen Sie im Lösungskatalog die Kachel **Surface Hub** aus dem Katalog aus, und wählen Sie dann auf der Detailseite der Lösung **Hinzufügen** aus. Die Lösung wird jetzt im Arbeitsbereich angezeigt.

## Verwenden des Surface Hub-Dashboards
Klicken Sie im OMS-Arbeitsbereich auf der Seite **Übersicht** auf die Kachel „Surface Hub“, um das Surface Hub-Dashboard anzuzeigen. Verwenden Sie das Dashboard, um eine Momentaufnahme mit Nutzungs- und Zuverlässigkeitsdaten für alle Surface Hubs abzurufen. Klicken Sie im Dashboard auf die einzelnen Ansichten, um ausführliche Daten anzuzeigen, die Abfrage nach Bedarf zu ändern und Warnungen zu erstellen.

> [!NOTE]
> In den meisten Ansichten werden Daten für die letzten 30Tage angezeigt, die genaue Anzahl richtet sich jedoch nach der Datenaufbewahrungsrichtlinie Ihres Abonnements.

**Aktive Surface Hubs**

Verwenden Sie diese Ansicht, um Ihren gesamten Surface Hub-Bestand anzuzeigen. Nachdem die Verbindung mit OMS hergestellt wurde, sendet jeder Surface Hub regelmäßig ein Taktereignis an den Server. In dieser Ansicht sind Surface Hubs enthalten, die in den letzten 24 Stunden ein Taktereignis gesendet haben.

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**Drahtlose Projektion**

Verwenden Sie diese Ansicht, um Daten zur Nutzung und Zuverlässigkeit von drahtlosen Projektionen der letzten 30Tage abzurufen. Im Diagramm wird die Gesamtanzahl der für alle Surface Hubs hergestellten Drahtlosverbindungen angezeigt. So erhalten Sie einen Eindruck davon, ob dieses Feature von Personen in Ihrer Organisation genutzt wird. Wenn die Anzahl gering ist, müssen Sie Mitarbeitern Ihrer Organisation möglicherweise in einer Schulung vermitteln, wie Drahtlosverbindungen mit Surface Hubs hergestellt werden.
 
Außerdem enthält das Diagramm eine Aufschlüsselung der erfolgreichen und fehlerhaften Verbindungen. Wenn in zahlreichen Fällen keine Verbindung hergestellt werden konnte, wird die drahtlose Projektion über Miracast von einigen Geräten u. U. nicht richtig unterstützt. Microsoft empfiehlt die Ausführung eines WDI-WLAN-Treibers und WDDM 2.0-Grafiktreibers auf dem Gerät, um optimale Leistung zu erzielen. Anhand der Detailansicht können Sie feststellen, ob Probleme mit der drahtlosen Projektion durch bestimmte Geräte verursacht werden.
 
Benutzer können bei Verwendung eines Windows-Laptops oder -Telefons auch wie folgt vorgehen, wenn ein Verbindungsfehler auftritt:
- Sie können das gekoppelte Gerät unter **Einstellungen** > **Geräte** > **Verbundene Geräte** entfernen und erneut eine Verbindung herstellen.
- Sie können das Gerät neu starten.
 
**Kabelgebundene Projektion**

Verwenden Sie diese Ansicht, um Daten zur Nutzung und Zuverlässigkeit von kabelgebundenen Projektionen der letzten 30Tage abzurufen. Wenn das Diagramm eine hohe Anzahl fehlerhafter Verbindungen enthält, liegt u. U. ein Verbindungsproblem mit der audiovisuellen Pipeline vor. Wenn Sie beispielsweise einen HDMI-Repeater oder eine Bedieneinheit in der Raummitte verwenden, müssen diese u. U. neu gestartet werden.
 
**Anwendungsnutzung**

Verwenden Sie diese Ansicht, um Nutzungsdaten für Apps auf Ihren Surface Hubs aus den letzten 30Tagen abzurufen. Die Daten stammen von App-Starts auf Surface Hubs. Skype for Business ist hiervon ausgenommen. An dieser Ansicht ist erkennbar, welche Surface Hub-Apps Ihrer Organisation den größten Nutzen bieten. Wenn Sie neue Branchen-Apps in Ihrer Umgebung bereitstellen, können Sie auch ermitteln, wie häufig sie verwendet werden.
 
**Application Crashes**

Verwenden Sie diese Ansicht, um Zuverlässigkeitsdaten für Apps auf Ihren Surface Hubs aus den letzten 30Tagen abzurufen. Die Daten stammen von App-Abstürzen auf Surface Hubs. In dieser Ansicht können Sie mitgelieferte Apps und Branchen-Apps erkennen, die nicht optimal funktionieren, und App-Entwickler darüber informieren.
 
**Beispielabfragen**

Mithilfe von Beispielabfragen können Sie benutzerdefinierte Warnungen anhand einer Reihe empfohlener Abfragen erstellen. Mit Warnungen können Sie schnell reagieren, wenn von den Surface Hubs Software- oder Hardwareprobleme gemeldet werden. Weitere Informationen finden Sie unter [Einrichten von Warnungen mithilfe von Beispielabfragen](#set-up-alerts-with-sample-queries).

## Einrichten von Warnungen mithilfe von Beispielabfragen

Verwenden Sie Warnungen, um schnell zu reagieren, wenn von den Surface Hubs Software- oder Hardwareprobleme gemeldet werden. Mithilfe von Warnungsregeln werden automatisch Protokollsuchen nach einem Zeitplan ausgeführt und mindestens eine Aktion ausgeführt, wenn die Ergebnisse bestimmte Kriterien erfüllen. Weitere Informationen finden Sie unter [Warnungen in Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/).
 
Die Log Analytics-Lösung von Surface Hub umfasst eine Reihe von Beispielabfragen. Sie helfen beim Einrichten der geeigneten Warnungen und veranschaulichen, wie Sie mögliche Probleme beheben können. Verwenden Sie die Abfragen bei der Planung Ihrer Überwachungs- und Unterstützungsstrategie als Ausgangspunkt.

In der folgenden Tabelle werden die Beispielabfragen in der Surface Hub-Lösung beschrieben:

| Warnungstyp | Auswirkungen | Empfohlene Maßnahmen | Details |
| ---------- | ------ | ----------------------- | ------- |
| Software   | Fehler  | **Starten Sie das Gerät neu**. <br> Führen Sie den Neustart manuell oder mit dem [Konfigurationsdienstanbieter (CSP) für Neustarts](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx) aus. <br> Der Neustart sollte zwischen Besprechungen stattfinden, um die Mitarbeiter in Ihrer Organisation möglichst wenig zu beeinträchtigen. | Auslöserbedingungen: <br> – Ein kritischer Vorfall im Surface Hub-Betriebssystem, beispielsweise, wenn die Shell, die Projektion oder Skype abstürzt oder nicht mehr reagiert. <br> – Das Gerät hat in den letzten 24 Stunden kein Taktereignis gemeldet. Dies kann auf ein Problem mit der Netzwerkkonnektivität, auf fehlerhafte Netzwerkhardware oder auf einen Fehler im Diagnosedatenberichtssystem zurückzuführen sein. |
| Software   | Fehler  | **Überprüfen Sie Ihren Exchange-Dienst**. <br> Achten Sie auf Folgendes: <br> – Der Dienst ist verfügbar. <br> – Das Kennwort des Gerätekontos ist auf dem neuesten Stand. Ausführliche Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).| Wird ausgelöst, wenn beim Synchronisieren des Gerätekalenders mit Exchange ein Fehler auftritt. |
| Software   | Fehler  | **Überprüfen Sie Ihren Skype for Business-Dienst**. <br> Achten Sie auf Folgendes: <br> – Der Dienst ist verfügbar. <br> – Das Kennwort des Gerätekontos ist auf dem neuesten Stand. Ausführliche Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md). <br> – Der Domänenname für Skype for Business ist ordnungsgemäß konfiguriert. Ausführliche Informationen finden Sie unter [Konfigurieren eines Domänennamens](use-fully-qualified-domain-name-surface-hub.md). | Wird bei einem Skype-Anmeldefehler ausgelöst. |
| Software   | Fehler  | **Setzen Sie das Gerät zurück**. <br> Da dieser Vorgang etwas dauern kann, sollten Sie das Gerät offline schalten. <br> Weitere Informationen finden Sie unter [Zurücksetzen des Geräts](device-reset-surface-hub.md).| Wird ausgelöst, wenn beim Bereinigen von Benutzer- und App-Daten am Ende einer Sitzung ein Fehler auftritt. Wenn dieser Vorgang wiederholt einen Fehler verursacht, wird das Gerät zum Schutz von Benutzerdaten gesperrt. Sie müssen das Gerät zurücksetzen, um den Vorgang fortzusetzen. |
| Hardware   | Warnung | **Keine**. Hat praktisch keine Auswirkungen auf die Funktionalität.| Wird ausgelöst, wenn bei einer der folgenden Hardwarekomponenten ein Fehler auftritt: <br> – Steckplätze für virtuelle Stifte <br> – NFC-Treiber <br> – USB-Hubtreiber <br> – Bluetooth-Treiber <br> – Näherungssensor <br> – Grafikleistung (Grafikkartentreiber) <br> – Falsche Festplatte <br> – Keine Tastatur/Maus erkannt |
| Hardware   | Fehler | **Wenden Sie sich an den Microsoft-Support**. <br> Deutet auf Auswirkungen auf Kernfunktionen hin (z.B. Skype, Projektion, Toucheingabe und Internetkonnektivität). <br> **Hinweis** In einigen Ereignissen, einschließlich Taktereignissen, ist die Seriennummer des Geräts enthalten, die Sie angeben können, wenn Sie sich an den Support wenden.| Wird ausgelöst, wenn bei einer der folgenden Hardwarekomponenten ein Fehler auftritt: <br> **Komponenten, die Skype beeinflussen**: <br> – Lautsprechertreiber <br> – Mikrofontreiber <br> – Kameratreiber <br> **Komponenten, die die kabelgebundene und drahtlose Projektion beeinflussen**: <br> – Touchback-Treiber für verkabelte Geräte <br> – Treiber für kabelgebundene Erfassung <br> – Treiber für Drahtlosadapter <br> – Wi-Fi Direct-Fehler <br> **Weitere Komponenten**: <br> – Treiber für Touchdigitalisierer <br> – Netzwerkkartenfehler (nicht in OMS gemeldet)|

**So richten Sie eine Warnung ein**
1. Wählen Sie in der Surface Hub-Lösung eine Beispielabfrage aus.
2. Ändern Sie die Abfrage nach Bedarf. Weitere Informationen finden Sie in der Suchreferenz zu Log Analytics.
3. Klicken Sie am oberen Seitenrand auf **Warnung**, um den Bildschirm **Warnungsregel hinzufügen** zu öffnen. Ausführliche Informationen zu den für die Warnung verfügbaren Konfigurationsoptionen finden Sie unter [Warnungen in Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/).
4. Klicken Sie auf **Speichern**, um die Warnungsregel abzuschließen. Ihre Ausführung wird sofort gestartet.

## Registrieren von Surface Hub

Damit Surface Hub eine Verbindung mit dem OMS-Dienst herstellen und sich registrieren kann, benötigt er Zugriff auf die Portnummer Ihrer Domänen und die URLs. In der folgenden Tabelle sind die von OMS benötigten Ports aufgelistet. Weitere Informationen finden Sie unter [Konfigurieren von Proxy- und Firewalleinstellungen in Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/).

>[!NOTE]
>Surface Hub unterstützt derzeit nicht die Verwendung eines Proxyservers für die Kommunikation mit dem OMS-Dienst.

| Agent-Ressource              | Anschlüsse | HTTPS-Überprüfung umgehen? |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | Ja |
| *.oms.opinsights.azure.com  | 443   | Ja |
| *.blob.core.windows.net     | 443   | Ja |
| ods.systemcenteradvisor.com | 443   | Nein  |

Der Microsoft Monitoring Agent dient zum Verbinden von Geräten mit OMS und ist in das Surface Hub-Betriebssystem integriert. Daher ist es nicht erforderlich, zusätzliche Clients zu installieren, um den Surface Hub mit OMS zu verbinden.
 
Nachdem der OMS-Arbeitsbereich eingerichtet wurde, gibt es verschiedene Möglichkeiten zum Registrieren Ihrer Surface Hub-Geräte:
- [Einstellungs-App](#enroll-using-the-settings-app)
- [Bereitstellungspaket](#enroll-using-a-provisioning-package)
- [MDM-Anbieter](#enroll-using-a-mdm-provider), z. B. Microsoft Intune und Konfigurations-Manager
 
Sie benötigen die Arbeitsbereichs-ID und den Primärschlüssel Ihres OMS-Arbeitsbereichs. Sie können diese aus dem OMS-Portal abrufen.
 
### Registrieren mithilfe der Einstellungs-App

**So führen Sie die Registrierung mit der Einstellungs-App durch**

1. Starten Sie auf dem Surface Hub **Einstellungen**.
2. Geben Sie die Geräteadministrator-Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden.
3. Wählen Sie **Dieses Gerät** aus, und navigieren Sie zu **Geräteverwaltung**.
4. Wählen Sie unter **Überwachung** die Option **OMS-Einstellungen konfigurieren** aus.
5. Wählen Sie im Dialogfeld für die OMS-Einstellungen **Überwachung aktivieren** aus.
6. Geben Sie die Arbeitsbereichs-ID und den Primärschlüssel des OMS-Arbeitsbereichs ein. Sie können diese aus dem OMS-Portal abrufen.
7. Klicken Sie auf **OK**, um die Konfiguration abzuschließen.
 
Ein Bestätigungsdialogfeld informiert Sie darüber, ob die OMS-Konfiguration erfolgreich auf das Gerät angewendet wurde. In diesem Fall beginnt das Gerät mit dem Senden von Daten an OMS.

### Registrieren mithilfe eines Bereitstellungspakets
Sie können den Surface Hub mit einem Bereitstellungspaket registrieren. Weitere Informationen finden Sie unter [Erstellen von Bereitstellungspaketen](provisioning-packages-for-certificates-surface-hub.md).
 
### Registrieren mithilfe eines MDM-Anbieters
Surface Hub kann mit dem SurfaceHub-CSP bei OMS registriert werden. Intune und Konfigurations-Manager bieten integrierte Funktionen, die Sie beim Erstellen von Richtlinienvorlagen für Surface Hub unterstützen. Weitere Informationen finden Sie unter [Verwalten von Surface Hub-Einstellungen mit einem MDM-Anbieter](manage-settings-with-mdm-for-surface-hub.md).

## Verwandte Themen

[Verwalten von Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub-Administratorhandbuch](surface-hub-administrators-guide.md)

 

 





