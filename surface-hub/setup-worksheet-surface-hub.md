---
title: Setup-Arbeitsblatt (Surface Hub)
description: Wenn Sie die Vorab-Einrichtung abgeschlossen haben und bereit für das erste Einrichten von Microsoft Surface Hub sind, stellen Sie sicher, dass Sie alle in diesem Abschnitt aufgeführten Informationen zur Hand haben.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: Setup-Arbeitsblatt, Vorab-Einrichtung, erste Einrichtung
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833853"
---
# Setup-Arbeitsblatt (Surface Hub)


Wenn Sie die Vorab-Einrichtung abgeschlossen haben und bereit für das erste Einrichten von Microsoft Surface Hub sind, stellen Sie sicher, dass Sie alle in diesem Abschnitt aufgeführten Informationen zur Hand haben.

Füllen Sie für jedes zu konfigurierende Surface Hub eine Liste aus. Einige Informationen können für alle Surface Hubs verwendet werden, z.B. die Proxyinformationen oder Domänenanmeldeinformationen. Einige dieser Informationen sind ggf. nicht erforderlich, je nachdem, wie Sie das Gerät konfigurieren möchten oder je nach Konfiguration der Infrastrukturumgebung Ihrer Organisation.

<table>
<tr>
<th>Eigenschaft</th>
<th>Verwendungszweck</th>
<th>Beispiel</th>
<th>Tatsächlicher Wert</th>
</tr>
<tr>
<td>
<p>Proxyinformationen</p>
</td>
<td>
<p>Wenn Sie einen Proxy für Netzwerk- und/oder Internetzugriff verwenden, müssen Sie ein Skript oder Server-/Portinformationen angeben.</p>
</td>
<td>
<p>Proxyskript: <code>http://contoso/proxy.pa</code> </br>
- ODER </br>
Server- und Portinformationen: 10.10.10.100, Port 80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Drahtlosnetzwerk-Anmeldeinformationen (Benutzername und Kennwort)</p>
</td>
<td>
<p>Wenn Sie Ihr Gerät per WLAN verbinden möchten und für Ihr Drahtlosnetzwerk Benutzeranmeldeinformationen erforderlich sind.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Gerätekonto-Benutzerprinzipalname oder Domäne\Benutzername und Gerätekonto-Kennwort</p>
</td>
<td>
<p>Dies sind der Benutzerprinzipalname (UPN) oder Domäne\Benutzername und das Kennwort für das Gerätekonto. E-Mail-, Kalender-Funktionen und Skype for Business erfordern ein kompatibles Gerätekonto.</p>
</td>
<td>
<p> Benutzerprinzipalname: ConfRoom15@contoso.com, #Passw0rd1 </br>
- ODER <br> 
Domäne und Benutzername: CONTOSO\ConfRoom15, #Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Microsoft Exchange Server für Gerätekonto</p>
</td>
<td>
<p>Dies ist der Exchange-Server für das Gerätekonto.
E-Mail-, Kalender-Funktionen und Skype for Business erfordern ein kompatibles Gerätekonto.
Zu Nutzung von E-Mail und Kalender-Funktionen muss das Gerätekonto einen gültigen Exchange-Server aufweisen. Es wird versucht, diesen automatisch zu finden.</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Session Initiation-Protokoll (SIP)-Adresse für Gerätekonto</p>
</td>
<td>
<p>Hierbei handelt es sich um die Skype for Business-SIP-Adresse des Gerätekontos.
E-Mail-, Kalender-Funktionen und Skype for Business erfordern ein kompatibles Gerätekonto.
Zur Nutzung von Skype for Business muss das Gerätekonto eine gültige SIP-Adresse aufweisen. Es wird versucht, diesen automatisch zu finden.</p>
</td>
<td>
<p>sip: ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Anzeigename</p>
</td>
<td>
<p>Der Anzeigename des Geräts ist der Name, der beim Herstellen einer Drahtlosverbindung mit dem Surface-Hub angezeigt wird. Der Name wird gut sichtbar auf dem Bildschirm des Surface Hub angezeigt.
Es wird empfohlen, einen einprägsamen und aussagekräftigen Anzeigename auszuwählen, sodass die Benutzer beim Herstellen einer Verbindung mehrere Surface Hubs voneinander unterscheiden können.</p>
</td>
<td>
<p>Konferenzraum 15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Gerätename</p>
</td>
<td>
<p>Der Gerätename ist der Name, der zum Beitreten zu einer Domäne verwendet wird, und die Kennung für die Registrierung des Geräts bei einem MDM-Anbieter.
Der gewählte Gerätename muss sich von den Namen aller anderen Geräte in der Active Directory-Domäne unterscheiden (wenn Sie das Gerät einer Domäne hinzufügen möchten). Das Gerät kann der Domäne nicht hinzugefügt werden, wenn der Name nicht eindeutig ist.
</p>
</td>
<td>
<p>Konfraum15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>WENN SIE AZURE AD BEITRETEN</b></p>
</td>
</tr>
<tr>
<td>
<p>Azure AD-Mandanten-Anmeldeinformationen (Benutzername und Kennwort)</p>
</td>
<td>
<p>Wenn Sie Personen in Ihrer Azure Active Directory (Azure AD)-Organisation Administratorberechtigungen für das Gerät zuweisen möchten, müssen Sie Azure AD beitreten.
Um Azure AD beizutreten, benötigen Sie gültige Benutzeranmeldeinformationen.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>WENN SIE EINER DOMÄNE BEITRETEN</b></p>
</td>
</tr>
<tr>
<td>
<p>Domäne für den Beitritt</p>
</td>
<td>
<p>Hierbei handelt es sich um die Domäne, der Sie beitreten müssen, damit der Sicherheitsgruppe Ihrer Wahl Administratorberechtigungen für das Gerät zugewiesen werden können.
Möglicherweise ist der vollqualifizierte Domänenname (FQDN) erforderlich.</p>
</td>
<td>
<p>contoso (Kurzname) ODER contoso.corp.com (FQDN)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Domänenkonto-Anmeldeinformationen (Benutzername und Kennwort)</p>
</td>
<td>
<p>Der Beitritt zu einer Domäne kann nur dann erfolgen, wenn die angegebenen Kontoanmeldeinformationen für den Beitritt zur Domäne ausreichen. Nachdem Sie eine Domäne und Anmeldeinformationen für den Beitritt angegeben haben, kann die Sicherheitsgruppe Ihrer Wahl Einstellungen auf dem Gerät ändern.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Alias für Administrator-Sicherheitsgruppe</p>
</td>
<td>
<p>Dies ist eine Sicherheitsgruppe in Active Directory (AD). Alle Mitglieder dieser Sicherheitsgruppe können Einstellungen auf dem Gerät ändern.</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>WENN SIE EINEN LOKALEN ADMINISTRATOR VERWENDEN</b></p>
</td>
</tr>
<tr>
<td>
<p>Kontoanmeldeinformationen für lokalen Administrator (Benutzername und Kennwort)</p>
</td>
<td>
<p>Wenn Sie keiner Active Directory-Domäne oder Azure AD beitreten möchten, können Sie ein lokales Administratorkonto auf dem Gerät erstellen.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>WENN ZERTIFIKATE ODER APPS INSTALLIERT WERDEN MÜSSEN</b></p>
</td>
</tr>
<tr>
<td>
<p>USB-Laufwerk</p>
</td>
<td>
<p>Wenn Sie vor der ersten Ausführung Zertifikate oder universelle Apps installieren möchten, führen Sie die Schritte unter <a href="provisioning-packages-for-certificates-surface-hub.md">Erstellen von Bereitstellungspaketen</a> aus. Die Bereitstellungspakete werden auf einem USB-Laufwerk erstellt.</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





