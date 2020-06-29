---
title: Vorbereiten der Umgebung für Microsoft Surface Hub
description: Dieser Abschnitt enthält eine Übersicht über die zum Vorbereiten der Umgebung erforderlichen Schritte, damit Sie alle Features von Microsoft Surface Hub verwenden können.
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: Umgebung vorbereiten, Features von Surface Hub, Gerätekonto erstellen und testen, Netzwerkverfügbarkeit überprüfen
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0ee406df6d3022f04a80f4ce253bd76f6473f1c8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834003"
---
# Vorbereiten der Umgebung für Microsoft Surface Hub


Dieser Abschnittenthält eine Übersicht über Setupabhängigkeiten und den Setupprozess. Lesen Sie die Informationen in diesem Abschnitt, um Ihre Umgebung vorzubereiten und die für die Einrichtung von Surface Hub erforderlichen Informationen zu sammeln.


## Überprüfen der Infrastrukturabhängigkeiten
Überprüfen Sie diese Abhängigkeiten, um sicherzustellen, dass die Surface Hub-Features in Ihrer IT-Infrastruktur funktionieren.

| Abhängigkeit        | Zweck           |
|-------------|------------------|
| Active Directory oder Azure Active Directory (Azure AD) | <p>Surface Hub verwendet ein Active Directory- oder Azure AD-Konto (**Gerätekonto** genannt), um auf den Exchange- und den Skype for Business-Dienst zuzugreifen. Surface Hub muss eine Verbindung mit dem Active Directory-Domänencontroller oder dem AzureAD-Mandanten herstellen können, um die Anmeldeinformationen des Gerätekontos zu überprüfen und um auf Informationen wie Anzeigename, Alias, Exchange-Server und Adresse des Session Initiation-Protokolls (SIP) des Gerätekontos zuzugreifen.</p>Sie können Surface Hub auch mit der Domäne oder Azure AD verknüpfen, um einer Gruppe autorisierter Benutzer die Konfiguration von Einstellungen auf Surface Hub zu erlauben. |
| Exchange (Exchange 2013 oder höher oder Exchange Online) und Exchange ActiveSync | <p>Exchange dient zum Aktivieren von E-Mail- und Kalenderfunktionen und ermöglicht außerdem Benutzern des Geräts das Senden von Besprechungsanfragen an das Surface Hub-Gerät, wodurch die One-Touch-Besprechungsteilnahme ermöglicht wird.</p>ActiveSync wird verwendet, um Kalender und E-Mail des Gerätekontos mit dem Surface Hub zu synchronisieren. Wenn das Gerät ActiveSync nicht verwenden kann, werden keine Besprechungen auf der Willkommensseite angezeigt, und die Besprechungsteilnahme und das Senden von Whiteboards per E-Mail sind nicht aktiviert. |
| Skype for Business (Lync Server2013 oder höher oder Skype for Business Online)  | Skype for Business wird für verschiedene Konferenzfeatures wie Videoanrufe, Chats und Bildschirmfreigabe verwendet.|
| Mobile Device Management (MDM)-Lösung (Microsoft InTune, Microsoft Endpoint Configuration Manager oder unterstützter MDM-Anbieter von Drittanbietern) | Wenn Sie per Remoteverbindung auf mehreren Geräten gleichzeitig Einstellungen anwenden und Apps installieren möchten, müssen Sie eine MDM-Lösung einrichten und das Gerät für diese Lösung registrieren. Ausführliche Informationen finden Sie unter [Verwalten von Einstellungen mit einem MDM-Anbieter](manage-settings-with-mdm-for-surface-hub.md). |
| Microsoft Operations Management Suite (OMS)   | OMS wird zum Überwachen der Integrität von Surface Hub-Geräten verwendet. Ausführliche Informationen finden Sie unter [Überwachen von Surface Hub](monitor-surface-hub.md). |
| Netzwerk- und Internetzugriff   | Um korrekt zu funktionieren, muss Surface Hub Zugriff auf ein verkabeltes Netzwerk oder ein Drahtlosnetzwerk haben. Im Allgemeinen wird eine Kabelverbindung bevorzugt. 802.1x-Authentifizierung wird sowohl für kabelgebundene als auch drahtlose Verbindungen unterstützt.</br></br></br>**802.1x-Authentifizierung:** In Windows10, Version 1703 ist die 802. 1 X-Authentifizierung für Kabel- und Drahtlosverbindungen standardmäßig in Surface Hub aktiviert. Wenn Ihre Organisation nicht die 802.1x-Authentifizierung verwendet, ist keine Konfiguration erforderlich, und Surface Hub funktioniert weiterhin wie gewohnt. Wenn Sie die 802.1X-Authentifizierung verwenden, müssen Sie sicherstellen, dass das Authentifizierungszertifikat auf Surface Hub installiert ist. Sie können das Zertifikat an Surface Hub mittels [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) in MDM übermitteln, oder Sie können [ein Bereitstellungspaket erstellen](provisioning-packages-for-surface-hub.md) und es bei der ersten Ausführung oder über die Einstellungs-App installieren. Nachdem das Zertifikat auf Surface Hub angewendet wurde, funktioniert die 802.1x-Authentifizierung automatisch.</br>**Hinweis:** Weitere Informationen zum Aktivieren der kabelgebundenen 802.1x-Authentifizierung auf Surface Hub finden Sie unter [Kabelgebundene 802.1x-Authentifizierung ermöglichen](enable-8021x-wired-authentication.md).</br></br>**Dynamische IP:** Surface Hub kann nicht für die Verwendung einer statischen IP konfiguriert werden. Das Gerät muss DHCP zum Zuweisen einer IP-Adresse verwenden.</br></br>**Proxyserver:** Wenn die Topologie eine Verbindung über einen Proxyserver erfordert, um Internetdienste zu erreichen, kann dieser bei der ersten Ausführung oder in den Einstellungen konfiguriert werden. Proxyanmeldeinformationen werden für alle Surface Hub-Sitzungen gespeichert und müssen nur einmal festgelegt werden. |

Beachten Sie darüber hinaus, dass für Surface Hub die folgenden offenen Ports erforderlich sind:
- HTTPS: 443
- HTTP: 80
- NTP: 123

Wenn Sie Surface Hub mit Skype for Business verwenden, müssen Sie zusätzliche Ports öffnen. Bitte folgen Sie den folgenden Anleitungen:
- Wenn Sie Skype for Business Online verwenden, lesen Sie [Office 365-IP-URLs und IP-Adressbereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US).
- Wenn Sie Skype for Business Server verwenden, lesen Sie [Skype for Business Server: Ports und Protokolle für interne Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols). 
- Wenn Sie eine Hybridlösung von Skype for Business Online und Skype for Business Server verwenden, müssen Sie alle dokumentierten Ports aus [Office 365-IP-URLs und IP-Adressbereichen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) sowie [Skype for Business Server: Ports und Protokolle für interne Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)öffnen.

Microsoft sammelt Diagnosedaten zur Verbesserung der Surface Hub-Erfahrung. Fügen Sie die folgenden Websites zur Liste zugelassener Websites hinzu:
- Clientendpunkt der Diagnosedaten: `https://vortex.data.microsoft.com/`
- Endpunkt der Einstellungen für Diagnosedaten: `https://settings.data.microsoft.com/`

### Proxykonfiguration

Wenn Ihre Organisation die Internetverbindungen der Computer im Netzwerk einschränkt, muss für Geräte, die den Microsoft Store für Unternehmen verwenden, ein bestimmter Satz von URLs verfügbar sein. Einige der Features des Microsoft Store für Unternehmen verwenden die Microsoft Store-App und Microsoft Store-Dienste. Geräte, die den Microsoft Store für Unternehmen verwenden, um Apps zu erwerben, zu installieren oder zu aktualisieren, benötigen Zugriff auf diese URLs. Wenn Sie einen Proxyserver verwenden, um Datenverkehr zu blockieren, muss die Konfiguration die folgenden URLs zulassen:

- login.live.com
- login.Windows.net
- account.live.com
- clientconfig.passport.net
- Windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com (vor Windows 10, Version 1607)
- www.msftconnecttest.com/connecttest.txt (ersetzt ab Windows 10, Version 1607, „www.msftncsi.com“)


## Zusammenarbeit mit anderen Administratoren

Surface Hub interagiert mit einigen anderen Produkten und Diensten. Je nach Größe Ihrer Organisation kann es mehrere Personen geben, die Support für verschiedene Produkte in Ihrer Umgebung bereitstellen. Sie möchten Personen, die Exchange, Active Directory (oder Azure Active Directory), MDM (Verwaltung mobiler Geräte) und Netzwerkressourcen verwalten, in die Planung und Vorbereitung von SurfaceHub-Bereitstellungen einschließen. 


## Erstellen und Überprüfen eines Gerätekontos

Ein Gerätekonto ist ein Exchange-Ressourcenkonto, das Surface Hub verwendet, um den Besprechungskalender anzuzeigen, an Skype for Business-Anrufen teilzunehmen und (optional) die Authentifizierung bei Exchange durchzuführen. Ausführliche Informationen finden Sie unter [Erstellen und Testen eines Gerätekontos](create-and-test-a-device-account-surface-hub.md).

Führen Sie nach der Erstellung Ihres Gerätekontos PowerShell-Skripts zur Surface Hub-Gerätekontoüberprüfung aus, um sicherzustellen, dass es ordnungsgemäß eingerichtet ist. Weitere Informationen finden Sie unter [PowerShell-Skripts für Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md) weiter unten in diesem Handbuch. 

 

## Vorbereiten des Programms für die Erstausführung 
Es gibt einige weitere Aspekte, die vor dem Starten des [Programms für die Erstausführung](first-run-program-surface-hub.md) berücksichtigt werden sollten.  

### Erstellen von Bereitstellungspaketen (optional)
Sie können Bereitstellungspakete verwenden, um Zertifikate hinzuzufügen, Einstellungen anzupassen und Apps zu installieren. Ausführliche Informationen finden Sie unter [Erstellen von Bereitstellungspaketen](provisioning-packages-for-certificates-surface-hub.md). Sie können [Bereitstellungspakete bei der ersten Ausführung installieren](first-run-program-surface-hub.md#first-page).

### Einrichten von Administratorgruppen
Jedes Surface Hub-Gerät kann mithilfe der Einstellungs-App auf dem Gerät lokal konfiguriert werden. Um die Änderung der Einstellungen durch nicht autorisierte Benutzer zu verhindern, sind zum Öffnen der Einstellungs-App Administratoranmeldeinformationen erforderlich. Ausführliche Informationen zum Einrichten und Verwalten von Administratorgruppen finden Sie unter [Administratorgruppenverwaltung](admin-group-management-for-surface-hub.md) . Sie [richten Administratoren für das Gerät bei der Erstausführung ein](first-run-program-surface-hub.md#setup-admins).

### Lesen und Abschließen des Surface Hub-Setup-Arbeitsblatts (optional)
Im Programm für die Erstausführung für Surface Hub müssen Sie einige Informationen bereitstellen. Im Setup-Arbeitsblatt sind diese Informationen zusammengefasst. Darüber hinaus enthält es Listen mit umgebungsspezifischen Infos, die Sie beim Durchlaufen des Programms für die Erstausführung benötigen. Weitere Informationen finden Sie unter [Setup-Arbeitsblatt](setup-worksheet-surface-hub.md).


## Inhalt dieses Abschnitts

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Thema</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">Erstellen und Testen eines Gerätekontos</a></p></td>
<td align="left"><p>In diesem Thema wird erläutert, wie Sie das Gerätekonto, das Surface Hub für die Kommunikation mit Skype verwendet, erstellen und testen.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">Erstellen von Bereitstellungspaketen</a></p></td>
<td align="left"><p>Für Windows 10 können Einstellungen, die die Registrierung oder eine Content Services-Plattform (CSP) verwenden, mithilfe von Bereitstellungspaketen konfiguriert werden. Sie können bei der ersten Ausführung auch Zertifikate mit der Bereitstellung hinzufügen.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">Administratorgruppenverwaltung</a></p></td>
<td align="left"><p>Jeder Surface Hub kann durch Öffnen der Einstellungs-App auf dem Gerät einzeln konfiguriert werden. Um jedoch zu verhindern, dass Benutzer, die keine Administratoren sind, die Einstellungen ändern, erfordert die Einstellungs-App Administratoranmeldeinformationen zum Öffnen der App und Ändern der Einstellungen.</p>
<p>Die Einstellungs-App erfordert lokale Administratoranmeldeinformationen zum Öffnen der App.</p></td>
</tr>
</tbody>
</table>

## Weitere Informationen

- [Blogbeitrag: Surface Hub and the Skype for Business Trusted Domain List (in englischer Sprache)](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [Blogbeitrag: Surface Hub in a Multi-Domain Environment (in englischer Sprache)](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [Blogbeitrag: Configuring a proxy for your Surface Hub (in englischer Sprache)](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 





