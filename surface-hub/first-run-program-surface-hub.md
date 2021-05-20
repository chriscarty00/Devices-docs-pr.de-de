---
title: Programm für die Erstausführung (Surface Hub)
description: Der Begriff „Erstausführung“ bezieht sich auf die Schritte, die Sie beim ersten Einschalten von Microsoft Surface Hub durchlaufen, und entspricht der „Windows-Willkommensseite“ (Out-of-the-Box Experience, OOBE). Dieser Abschnitt enthält eine Anleitung für den Prozess.
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: Erste ausführen, Surface Hub, Windows-Willkommensseite, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: af6f6cc71a94d075341637499fe98f8206157e49
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576575"
---
# <a name="first-run-program-surface-hub"></a>Programm für die Erstausführung (Surface Hub)


Der Begriff „Erstausführung“ bezieht sich auf die Schritte, die Sie beim ersten Einschalten von Microsoft Surface Hub durchlaufen, und entspricht der Windows-Willkommensseite. Dieser Abschnitt enthält eine Anleitung für den Prozess.

Zu diesem Zeitpunkt sollten Sie alle vorherigen Schritte abgeschlossen haben:

-   [Vorbereiten der Umgebung für Surface Hub](prepare-your-environment-for-surface-hub.md)
-   [Physische Installation des Surface Hub-Geräts](physically-install-your-surface-hub-device.md) und
-   [Setup-Arbeitsblatt](setup-worksheet-surface-hub.md)

Ist dies der Fall, sollte die Erstausführung einfach und schnell verlaufen.
Das normale Verfahren umfasst sechs Schritte:

1.  [Seite „Hallo“](#first-page)
2.  [Seite „Bereits für Sie eingerichtet“](#set-up-for-you)
3.  [Seite „Gerätekonto“](#device-account)
4.  [Seite „Gerät benennen“](#name-this-device)
5.  [Seite „Administratoren für dieses Gerät einrichten“](#setup-admins)
6.  [Aktualisieren des Surface Hub](#update-surface-hub)

Jeder dieser Abschnitte enthält auch Informationen zur Vorgehensweise bei möglichen Abweichungen. Beispielsweise werden die meisten Surface Hubs per Kabel mit dem Netzwerk verbunden, einige jedoch per WLAN. Die Details werden gegebenenfalls beschrieben.

>[!NOTE]
>Die separate mit dem Surface Hub gelieferte Tastatur sollte eingerichtet und einsatzbereit sein. Im Installationshandbuch für das Surface Hub wird dies detailliert beschrieben.

 

## <a name="hi-there-page"></a><a href="" id="first-page"></a>Seite „Hallo“


Dies ist der Bildschirm, der beim ersten Einschalten des Surface Hub angezeigt wird. Hier geben Sie Informationen zur Lokalisierung des Geräts ein.

>[!NOTE]
>Außerdem können hier optional Bereitstellungspakete eingebunden werden. Bei Bedarf finden Sie unter [Erstellen von Bereitstellungspaketen](provisioning-packages-for-certificates-surface-hub.md) weitere Informationen hierzu.

 Wählen Sie eine Sprache aus, und die anfänglichen Setupoptionen werden angezeigt.

![Abbildung der Prüfliste mit den ICD-Optionen.](images/setuplocale.png)

### <a name="details"></a>Details

Wenn die angezeigten Standardwerte richtig sind, klicken Sie auf **Weiter** , um den Vorgang fortzusetzen. Andernfalls müssen Sie die Daten in die entsprechenden Felder eingeben.

-   **Land/Region:** Wählen Sie das Land/die Region aus, in dem/der der Surface Hub verwendet werden wird.
-   **App-Sprache:** Apps und Features werden in dieser Sprache und diesem Sprachformat angezeigt.
-   **Tastaturlayout:** Wählen Sie das Tastaturlayout für die Bildschirmtastatur und die physischen Tastaturen aus, die mit dem Gerät verwendet werden.
-   **Zeitzone:** Wählen Sie die Zeitzone aus, in der der Surface Hub verwendet werden wird.

### <a name="what-happens"></a>Folgendes passiert:

>[!NOTE]
> Nachdem die Einstellungen auf dieser Seite festgelegt wurden, können Sie den Bildschirm erst dann wieder aufrufen, wenn Sie das Gerät zurücksetzen (weitere Informationen unter [Zurücksetzen des Geräts](device-reset-surface-hub.md)). Stellen Sie sicher, dass die Einstellungen richtig festgelegt sind, bevor Sie fortfahren.

 

Nach dem Übernehmen der Einstellungen wird geprüft, ob eine drahtgebundene Netzwerkverbindung besteht. Ist die Verbindung in Ordnung, wird die Seite [Bereits für Sie eingerichtet](#set-up-for-you)angezeigt. Liegt ein Problem mit der drahtgebundenen Verbindung vor, wird die Seite [Netzwerkinstallation](#network-setup)angezeigt.

Wenn keine drahtgebundene Verbindung gefunden wird, wird zur Einrichtung der Verbindung die Seite [Netzwerkinstallation](#network-setup).

## <a name="network-setup-page"></a><a href="" id="network-setup"></a>Netzwerkinstallation


Kann keine drahtgebundene Verbindung zu einem Netzwerk oder dem Internet gefunden werden, wird diese Seite angezeigt. Hier können Sie entweder eine Verbindung mit einem Drahtlosnetzwerk herstellen oder das Herstellen der Netzwerkverbindung überspringen.

![Abbildung der Netzwerkeinrichtungsseite.](images/setupnetworksetup-1.png)

### <a name="details"></a>Details

Dieser Bildschirm wird nur angezeigt, wenn kein drahtgebundenes Netzwerk erkannt wird. Wenn dieser Bildschirm angezeigt wird, haben Sie drei Optionen:

-   Sie können eines der angezeigten Drahtlosnetzwerke auswählen. Wenn es sich um ein gesichertes Netzwerk handelt, werden Sie zu einer Anmeldeseite weitergeleitet. Unter [Drahtlosnetzwerkinstallation](#wireless) finden Sie weitere Informationen.
-   Klicken Sie auf **Diesen Schritt überspringen** , um die Herstellung der Netzwerkverbindung zu überspringen. Die Seite [Bereits für Sie eingerichtet](#set-up-for-you) wird angezeigt.
    >[!NOTE]
    >Wenn Sie diesen Schritt überspringen, wird keine Netzwerkverbindung hergestellt, und es können keine Dienste auf dem Surface Hub genutzt werden, die eine Netzwerkverbindung erfordern, u.a. System-Updates sowie E-Mail- und Kalender-Synchronisierung. Sie können eine Verbindung mit einem Drahtlosnetzwerk zu einem späteren Zeitpunkt mithilfe Einstellungen (siehe [Drahtlosnetzwerkverwaltung](wireless-network-management-for-surface-hub.md)).

     

-   Während dieser Bildschirm angezeigt wird, können Sie ein Netzwerkkabel anschließen. Nach der Erkennung wird auf dem Bildschirm **Weiter** angezeigt. Klicken Sie auf **Weiter** , um die Herstellung der drahtgebundenen Verbindung fortzusetzen.

### <a name="what-happens"></a>Folgendes passiert:

Wenn beim Einschalten des Geräts eine kabelgebundene Netzwerkverbindung besteht und eine Verbindung mit einem Netzwerk oder dem Internet hergestellt werden kann, wird diese Seite nicht angezeigt. Wenn Sie eine Verbindung mit einem Drahtlosnetzwerk herstellen möchten, darf bei der ersten Ausführung kein Ethernet-Kabel angeschlossen sein, da sonst dieser Bildschirm angezeigt wird. Unabhängig davon, was Sie direkt einrichten möchten, können Sie zu einem späteren Zeitpunkt in den [Einstellungen](wireless-network-management-for-surface-hub.md) weitere Verbindungen einrichten.

Wenn Sie auf dieser Seite eine Verbindung mit einem gesicherten Drahtlosnetzwerk herstellen möchten, klicken Sie auf das gewünschte Netzwerk, und geben Sie dann die erforderlichen Informationen (Kennwort oder Konto-Anmeldeinformationen) ein. Weitere Informationen finden Sie unter [Drahtlosnetzwerkinstallation](#wireless).

## <a name="wireless-network-setup"></a><a href="" id="wireless"></a>Drahtlosnetzwerkinstallation


Diese Seite wird angezeigt, wenn ein gesichertes Drahtlosnetzwerk ausgewählt ist.

![Abbildung der Drahtlosnetzwerk-Einrichtungsseite.](images/setupnetworksetup-3.png)

### <a name="details"></a>Details

-   **Benutzername:** Geben Sie den Benutzernamen für das ausgewählte Drahtlosnetzwerk ein.
-   **Kennwort:** Dies ist das Kennwort für das Netzwerk.

### <a name="what-happens"></a>Folgendes passiert:

Es wird versucht, eine Verbindung mit dem angegebenen Netzwerk herzustellen. Ist dies erfolgreich, werden Sie zur Seite [Bereits für Sie eingerichtet](#set-up-for-you) weitergeleitet.

## <a name="network-proxy-setup"></a><a href="" id="proxy"></a>Netzwerkproxy-Installation


Wird eine eingeschränkte drahtgebundene Verbindung erkannt, wird diese Seite angezeigt. Es stehen drei Optionen zur Auswahl:

-   Sie können ein Drahtlosnetzwerk anstelle der eingeschränkten drahtgebundenen Verbindung auswählen.

-   Sie können das Herstellen einer Verbindung mit einem Netzwerk überspringen, indem Sie auf **Diesen Schritt überspringen**klicken. Die Seite [Bereits für Sie eingerichtet](#set-up-for-you) wird angezeigt.

    > [!NOTE]
    > Wenn Sie diesen Schritt überspringen, wird keine Netzwerkverbindung hergestellt, und es können keine Dienste auf dem Surface Hub genutzt werden, die eine Netzwerkverbindung erfordern, u.a. E-Mail- und Kalender-Synchronisierung. Sie können eine Verbindung mit einem Drahtlosnetzwerk zu einem späteren Zeitpunkt mithilfe Einstellungen (siehe [Drahtlosnetzwerkverwaltung](wireless-network-management-for-surface-hub.md)).

-   Sie können **Proxyeinstellungen eingeben** auswählen, um die Nutzung des Netzwerkproxys anzugeben. Sie werden zum nächsten Bildschirm weitergeleitet.

    ![Abbildung der Netzwerk-Proxy-Seite.](images/setupnetworksetup-2.png)

    Dieser Bildschirm wird angezeigt, wenn Sie im vorherigen Bildschirm auf **Proxyeinstellungen eingeben** klicken.

    ![Abbildung der Proxyserver-Einstellungsdetails.](images/setupnetworksetup-4.png)

### <a name="details"></a>Details

Um eine Netzwerkverbindung herzustellen, müssen Sie einen Skriptnamen oder den Proxyserver und die Portinformationen eingeben.

-   **Proxyskript:** Geben Sie die Adresse für ein Proxyskript an.
-   **Proxyserver und -port:** Hier können Sie Proxyserveradresse und -port angeben.

### <a name="what-happens"></a>Folgendes passiert:

Nach dem Klicken auf **Weiter** wird versucht, eine Verbindung mit dem Proxyserver herzustellen. Wenn erfolgreich, werden Sie zur Seite [Bereits für Sie eingerichtet](#set-up-for-you) weitergeleitet.

Sie können das Herstellen einer Verbindung mit einem Netzwerk überspringen, indem Sie auf **Diesen Schritt überspringen**klicken. Die Seite [Bereits für Sie eingerichtet](#set-up-for-you) wird angezeigt.

>[!NOTE]
>Wenn Sie diesen Schritt überspringen, wird keine Netzwerkverbindung hergestellt, und es können keine Dienste auf dem Surface Hub genutzt werden, die eine Netzwerkverbindung erfordern, u.a. E-Mail- und Kalender-Synchronisierung. Sie können eine Verbindung mit einem Drahtlosnetzwerk zu einem späteren Zeitpunkt mithilfe Einstellungen (siehe [Drahtlosnetzwerkverwaltung](wireless-network-management-for-surface-hub.md)).

 

## <a name="set-up-for-you-page"></a><a href="" id="set-up-for-you"></a>Seite „Bereits für Sie eingerichtet“


Dieser Bildschirm dient nur Informationszwecken und zeigt die empfohlenen standardmäßig aktivierten Einstellungen.

![Abbildung der Einrichtung Ihrer Seite.](images/setupsetupforyou.png)

### <a name="details"></a>Details

Lesen Sie auf dem Bildschirm ab, welche Dienste standardmäßig aktiviert wurden. Sie können in der Einstellungs-App ggf. Änderungen vornehmen, aber beachten Sie, welche Auswirkungen dies haben kann. Unter [Einführung in Microsoft Surface Hub](intro-to-surface-hub.md) finden Sie weitere Informationen.

Wenn Sie die Einstellungen überprüft haben, klicken Sie auf **Weiter** , um den Vorgang fortzusetzen.

### <a name="what-happens"></a>Folgendes passiert:

Die auf der Seite angezeigten Einstellungen wurden bereits festgelegt und können erst nach der ersten Ausführung geändert werden.

## <a name="device-account-page"></a><a href="" id="device-account"></a>Seite „Gerätekonto“


Auf dieser Seite werden Sie zur Eingabe von Anmeldeinformationen für das zuvor konfigurierte Gerätekonto aufgefordert. (Siehe [Erstellen und Testen eines Gerätekontos](create-and-test-a-device-account-surface-hub.md).) Es wird versucht, diverse Eigenschaften des Kontos zu erkennen. Ist dies nicht erfolgreich, werden Sie ggf. zur Eingabe weiterer Informationen auf einer anderen Seite aufgefordert.

>[!NOTE]
>In diesem Abschnitt werden keine spezifischen Fehler behandelt, die bei der ersten Ausführung auftreten können. Unter [Problembehandlung bei Microsoft Surface Hub](troubleshoot-surface-hub.md) finden Sie weitere Informationen zu Fehlern.


![Abbildung der Seite zur Eingabe der Gerätekontoinformationen.](images/setupdeviceacct.png)

### <a name="details"></a>Details

Geben Sie im ersten Eingabefeld entweder einen **Benutzerprinzipalnamen (UPN)** oder **Domäne\\Benutzername** als Konto-ID an. Verwenden Sie das Format, das Ihrer Umgebung entspricht, und geben Sie das Kennwort ein.


|                      Umgebung                      | Erforderliches Format für Gerätekonto |
|-------------------------------------------------------|------------------------------------|
|         Das Gerätekonto wird nur online gehostet.         |        Benutzername@domain.com         |
|        Das Gerätekonto wird nur lokal gehostet.         |          DOMÄNE\Benutzername           |
| Das Gerätekonto wird online und lokal gehostet (hybrid). |          DOMÄNE\Benutzername           |

Klicken Sie auf **Einrichtung eines Gerätekontos überspringen**, um diesen Schritt zu überspringen. Wenn Sie allerdings kein Gerätekonto festlegen, wird das Gerät nicht vollständig in die Infrastruktur integriert. Beispielsweise ist Folgendes nicht möglich:

-   Anzeigen eines Besprechungskalenders auf der Willkommensseite
-   Starten einer Besprechung von der Willkommensseite aus
-   Senden von Whiteboards von OneNote per E-Mail
-   Verwenden von Skype for Business für Besprechungen

Wenn Sie die Einstellung jetzt überspringen, können Sie auch später in der Einstellungs-App ein Gerätekonto hinzufügen.

Wenn Sie auf **Einrichtung eines Gerätekontos überspringen**klicken, wird ein Dialogfeld mit Informationen zu den Folgen angezeigt, die mit dem Überspringen des Schritts einhergehen. Wenn Sie auf **Ja, diesen Schritt überspringen**klicken, werden Sie auf die Seite [Gerät benennen](#name-this-device)weitergeleitet.

![Abbildung der Meldung, die angezeigt wird, um zu bestätigen, dass Sie das Erstellen eines Gerätekontos überspringen möchten.](images/setupskipdeviceacct.png)

### <a name="what-happens"></a>Folgendes passiert:

Der Benutzerprinzipalname bzw. Domäne\\Benutzername und Kennwort für das Gerätekonto werden für Folgendes verwendet:

-   Überprüfen, ob das Konto in Active Directory (AD) oder Azure Active Directory (Azure AD) vorhanden ist:

    -   Wenn ein UPN eingegeben wurde, wird in Azure AD nach dem Konto gesucht.
    -   Wenn Domäne\\Benutzername eingegeben wurden, wird das Konto in AD gesucht.
-   Suchen nach dem Microsoft Exchange-Server für das Postfach des Kontos
-   Suchen nach der Session Initiation-Protokoll (SIP)-Adresse für das Konto
-   Abrufen des Anzeigenamens des Kontos und der alias-Attribute

## <a name="exchange-server-page"></a><a href="" id="exchange-server"></a>Seite „Exchange Server“


Diese wird nur angezeigt, wenn ein Problem vorliegt. In der Regel bedeutet dies, dass das angegebene Gerätekonto in Active Directory (AD) oder Azure Active Directory (Azure AD) zwar gefunden wurde, aber der Exchange-Server für das Konto nicht erkannt wurde.

![Abbildung der Exchange-Server-Seite.](images/setupexchangeserver-01.png)

### <a name="details"></a>Details

Geben Sie den Namen des Exchange-Servers ein, auf dem das Postfach des Gerätekontos gehostet wird.

Klicken Sie auf **Einrichtung von Exchange-Diensten überspringen** , um diesen Schritt zu überspringen. Wenn Sie dies tun, ist Folgendes nicht möglich:

-   Anzeigen eines Besprechungskalenders auf der Willkommensseite
-   Starten einer Besprechung von der Willkommensseite aus
-   Senden von Whiteboards von OneNote per E-Mail

Unter [Einführung in Microsoft Surface Hub](intro-to-surface-hub.md) finden Sie ausführliche Informationen zur Einrichtung von Abhängigkeiten.

Sie können Exchange-Dienste für ein Gerätekonto später mithilfe der Einstellungs-App aktivieren.

Wenn Sie auf **Einrichtung von Exchange-Diensten überspringen**klicken, wird ein Dialogfeld mit Informationen zu den Folgen hiervon angezeigt. Wenn Sie auf **Ja, diesen Schritt überspringen**klicken, werden die Exchange-Dienste nicht eingerichtet.

![Abbildung der Bestätigungsmeldung, die angezeigt wird, wenn Sie die Einrichtung von Exchange-Diensten überspringen.](images/setupexchangeserver-02.png)

### <a name="what-happens"></a>Folgendes passiert:

Das Surface Hub versucht, das Gerätekonto auf dem angegebenen Exchange-Server zu überprüfen. Wenn der Exchange-Server erreicht werden kann und die Überprüfung erfolgreich ist, wird die erste Ausführung fortgesetzt.

Wenn Sie die Einrichtung der Exchange-Dienste überspringen, wird nicht weiter nach dem Exchange-Server gesucht, und es werden keine Exchange-Dienste (E-Mail und Kalender) aktiviert.

## <a name="exchange-policies-page"></a><a href="" id="exchange-policies"></a>Seite „Exchange-Richtlinien“


Diese Seite wird angezeigt, wenn Folgendes zutrifft:

-   Das Gerätekonto verwendet eine Exchange Active Sync (EAS)-Richtlinie, wobei die Richtlinie „PasswordEnabled“ auf den Wert 1 festgelegt ist.
-   Es besteht keine Verbindung mit Exchange.
-   Exchange gibt einen Statuscode zurück, der auf einen Fehler hinweist. (Beispiel: Das Konto wurde für zu viele Geräte bereitgestellt.)
-   Unterstützte Exchange-Protokolle werden vom Surface Hub nicht unterstützt.
-   Exchange gibt eine ungültige XML zurück.

![Abbildung der Seite mit den Exchange-Richtlinien.](images/setupexchangepolicies.png)

### <a name="details"></a>Details

Diese Seite dient ausschließlich Informationszwecken. Es ist also keine Eingabe erforderlich. Sie können jedoch auf zwei unterschiedliche Arten fortfahren: Entweder Sie fahren mit dem nächsten Schritt fort, oder Sie wiederholen die Überprüfung, die den Fehler verursacht hat. Bevor Sie entscheiden, welche Option am besten geeignet ist, lesen Sie den Abschnitt **Folgendes passiert** . Sie können das Problem möglicherweise an anderer Stelle beheben, bevor Sie auf eine der Optionen klicken.

-   **Klicken Sie hier, um den Vorgang unter Verwendung nicht unterstützter Richtlinien fortzusetzen**: Klicken Sie auf diese Option, um mit der Erstausführung fortzufahren. Das Surface Hub kann dann keine Exchange-Dienste oder Synchronisierung verwenden.
-   **Wiederholen**: Überprüfen Sie erneut die Richtlinie auf dem Exchange-Server.

### <a name="what-happens"></a>Folgendes passiert:

Das Surface Hub überprüft, ob in der EAS-Richtlinie des Gerätekontos die Richtlinie „PasswordEnabled“ auf 0 (False) festgelegt ist. Wenn dies nicht der Fall ist, können E-Mails und Kalender nicht synchronisiert werden, und das Surface Hub kann keine Exchange-Dienste verwenden. Sie können mit den Exchange-Verwaltungstools auf einem PC überprüfen, ob im Gerätekonto die Richtlinie „PasswordEnabled“ auf 0 festgelegt ist. Wenn dies nicht der Fall ist, können Sie das Konto erneut konfigurieren und anschließend auf **Wiederholen** klicken.

Wurde die Richtlinie bereits richtig konfiguriert, überprüfen Sie, ob das Gerät ordnungsgemäß mit dem Netzwerk oder Internet verbunden ist und der Exchange-Server erreicht werden kann, da diese Seite auch angezeigt wird, wenn das Surface Hub den Exchange-Server nicht erreichen kann.

Ein weiterer möglicher Grund dafür, dass Exchange nicht erreicht werden kann, ist zertifikatbasierte Authentifizierung. Diese Seite wird möglicherweise aufgrund von Zertifikatproblemen angezeigt. Wenn das Gerät die Fehlercodes 0x80072F0D oder 0X800C0019 ausgibt, ist ein Zertifikat erforderlich. Da die Bereitstellung auf der ersten Seite des Erstausführungsprozesses erfolgt, müssen Sie Exchange-Dienste deaktivieren. Klicken Sie hierzu auf **Klicken Sie hier, um den Vorgang unter Verwendung nicht unterstützter Richtlinien fortzusetzen**, und installieren Sie anschließend die richtigen Zertifikate in der Einstellungs-App.

Wenn Sie diese Überprüfung überspringen, wird nicht mehr weiter nach dem Exchange-Server gesucht, die EAS-Richtlinien werden nicht überprüft, und es werden keine Exchange-Dienste aktiviert. Unter [Einführung in Microsoft Surface Hub](intro-to-surface-hub.md) finden Sie ausführliche Informationen zur Einrichtung von Abhängigkeiten.

## <a name="name-this-device-page"></a><a href="" id="name-this-device"></a>Seite „Gerät benennen“


Auf dieser Seite werden Sie aufgefordert, zwei Namen zum Identifizieren des Surface Hub anzugeben.

![Abbildungder Seite zum Benennen dieses Geräts.](images/setupnamedevice.png)

### <a name="details"></a>Details

Wenn die angezeigten Standardwerte richtig sind, klicken Sie auf **Weiter** , um den Vorgang fortzusetzen. Andernfalls geben Sie Daten in mindestens eines der beiden Textfelder ein.

-   **Anzeigename:** Dies ist der Name, der bei der Herstellung einer Drahtlosverbindung mit dem Surface Hub angezeigt wird.
-   **Gerätename:** Es kann ein beliebiger eindeutiger Name festgelegt werden wie auf dem Bildschirm beschrieben.

Sofern beide Namen die Längenanforderungen erfüllen und keine eingeschränkten Zeichen enthalten, klicken Sie auf **Weiter** , um die nächste Seite [Administratoren für dieses Gerät einrichten](#setup-admins)aufzurufen.

### <a name="what-happens"></a>Folgendes passiert:

Das Surface Hub erfordert zwei Namen für das Gerät, die standardmäßig folgendermaßen verwendet werden:

-   **Anzeigename:** Hierfür wird standardmäßig der Anzeigename des Gerätekontos verwendet.
-   **Gerätename:** Hierfür wird standardmäßig das Alias des Gerätekontos verwendet.

Zwar können die Namen später geändert werden, beachten Sie aber Folgendes:

-   Der Anzeigename sollte aussagekräftig und eindeutig sein, damit beim Herstellen einer Drahtlosverbindung mehrere Surface Hubs voneinander unterschieden werden können.
-   Wenn Sie mit dem Gerät einer Domäne beitreten möchten, darf der Gerätename von keinem anderen Gerät in der Active Directory-Domäne für das Konto verwendet werden. Das Gerät kann der Domäne nicht beitreten, wenn ein anderes Gerät mit demselben Namen in der Domäne vorhanden ist.

>[!NOTE]
>Wenn Sie [Miracast über die Infrastruktur](miracast-over-infrastructure.md) aktivieren möchten, muss der Namen des Geräts über DNS erkannt werden. Sie können dies erreichen, indem Sie entweder den Surface Hub automatisch über die dynamische DNS registrieren oder manuell einen A oder AAAA-Eintrag für den Surface Hub-Gerätenamen erstellen.

## <a name="set-up-admins-for-this-device-page"></a><a href="" id="setup-admins"></a>Seite „Administratoren für dieses Gerät einrichten“


Auf dieser Seite können Sie aus mehreren Möglichkeiten zur Einrichtung von Administratorkonten auswählen, um das Gerät lokal zu verwalten.

Da jedes Surface Hub von einer beliebigen Anzahl von authentifizierten Mitarbeitern verwendet werden kann, werden die Einstellungen gesperrt, damit sie von Sitzung zu Sitzung nicht geändert werden können. Nur Administratoren können die Einstellungen auf dem Gerät konfigurieren, und auf dieser Seite wählen Sie aus, welche Administratoren über diese Berechtigung verfügen.

>[!NOTE]
>Der Zweck dieser Seite besteht in erster Linie in der Bestimmung, wer das Gerät via die Benutzeroberfläche des Geräts konfigurieren darf, d.h., wer sich auf dem Gerät anmelden, die Einstellungs-App öffnen und die Einstellungen ändern darf.

 

![Abbildung der Seite „Administratoren für dieses Gerät einrichten“.](images/setupsetupadmins.png)

### <a name="details"></a>Details

Wählen Sie eine der drei verfügbaren Optionen aus:

-   **Microsoft Azure Active Directory verwenden**
-   **Active Directory-Domänendienste verwenden**
-   **Lokalen Administrator verwenden**

### <a name="what-happens"></a>Folgendes passiert:

Bei Auswahl einer der Optionen passiert Folgendes.

-   **Microsoft Azure Active Directory verwenden**

    Mit dieser Option können Sie das Gerät mit Azure AD verknüpfen. Wenn Sie auf **Weiter**klicken, wird das Gerät neu gestartet, um bestimmte Einstellungen zu übernehmen. Anschließend werden Sie zur Seite [Microsoft Azure Active Directory verwenden](#use-microsoft-azure) weitergeleitet und zur Eingabe der Anmeldeinformationen für Azure AD aufgefordert. Mitglieder der Azure Global Admins-Rolle aus der beigetretenen Organisation können die Einstellungen verwenden. Welche Personen zugelassen werden, hängt von Ihrem Azure AD-Abonnement und davon ab, wie Sie die Einstellungen für Ihre Azure AD-Organisation konfiguriert haben.
    
    > [!IMPORTANT]
    > Um zu konfigurieren, wer die Einstellungen-App verwenden kann, um Surface Hubs zu verwalten, stellen Sie sicher, dass die automatische [Intune-Registrierung](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) in Ihrem Mandanten aktiviert ist, bevor Sie dem Gerät azure AD beitreten. Intune-Richtlinien können dann verwendet werden, um nicht globale Administratoren auf Surface [Hubs](surface-hub-2s-nonglobal-admin.md) zu konfigurieren.

-   **Active Directory Domain Services verwenden**

    Klicken Sie auf diese Option, um das Gerät mit AD zu verknüpfen. Wenn Sie auf **Weiter**klicken, werden Sie zur Seite [Active Directory-Domänendienste verwenden](#use-active-directory) weitergeleitet und zur Eingabe der Anmeldeinformationen für die angegebene Domäne aufgefordert. Nach dem Beitritt können Sie eine Sicherheitsgruppe aus der Domäne auswählen und Personen aus der Sicherheitsgruppe können die Einstellungs-App verwenden.

-   **Lokalen Administrator verwenden**

    Mit dieser Option können Sie einen einzelnen lokalen Administrator erstellen. Dieser Administrator wird von keinem Verzeichnisdienst unterstützt. Wählen Sie diese Option daher nur dann, wenn das Gerät nicht auf Azure AD oder AD zugreifen kann. Nach dem Erstellen von Benutzername und Kennwort eines Administrators auf der Seite [Lokalen Administrator verwenden](#use-a-local-admin) müssen Sie dieselben Anmeldeinformationen erneut eingeben, wenn Sie die Einstellungs-App öffnen.

    Das Surface Hub muss für einen Administrator physisch zugänglich sein, damit sich dieser anmelden kann.

>[!NOTE]
>Nach Abschluss dieses Prozesses kann die Administratoroption des Geräts nur nach dem Zurücksetzen geändert werden.

 

### <a name="use-microsoft-azure-active-directory"></a><a href="" id="use-microsoft-azure"></a>Microsoft Azure Active Directory verwenden

Wenn Sie das Surface Hub mit einem Azure Active Directory (Azure AD) verknüpfen möchten, wird die Seite **Folgendes passiert** angezeigt. Lesen Sie die Informationen, und klicken Sie auf **Weiter** , um zur **Anmeldeseite**zu wechseln.

Das Verknüpfen mit Azure AD bietet zwei wesentliche Vorteile:

1.  Bestimmte Mitarbeiter Ihrer Organisation können als Administratoren auf das Gerät zugreifen, die Einstellungs-App starten und das Gerät konfigurieren. Personen mit Administratorberechtigungen werden in Ihrem Azure AD-Abonnement definiert.

2.  Wenn eine Verbindung zwischen Azure AD und einer Lösung für die mobile Geräteverwaltung (MDM) hergestellt wird, wird diese MDM-Lösung für das Gerät verwendet, und Sie können Richtlinien und Konfiguration übernehmen.

    ![Abbildung der Meldung, die angezeigt wird, wenn Sie Ihr Surface Hub mit Azure Active Directory verbinden.](images/setupjoiningazuread-1.png)

### <a name="details"></a>Details

Die folgende Eingabe ist erforderlich:

-   **UPN des Benutzers:** Der Benutzerprinzipalname (UPN) für ein Konto, das Azure AD beitreten kann.
-   **Kennwort:** Das Kennwort des Kontos, das verwendet wird, um Azure AD beizutreten.

![Abbildung der Informationen für die Kontoanmeldung.](images/setupjoiningazuread-2.png)

Wenn Sie über keine gültigen Anmeldeinformationen für ein Azure AD-Konto verfügen, können Sie fortfahren, indem Sie ein lokales Administratorkonto erstellen. Klicken Sie auf **Windows stattdessen mit einem lokalen Konto einrichten**.

![Abbildungder Seite zur Einrichtung eines Administratorkontos.](images/setupjoiningazuread-3.png)

### <a name="what-happens"></a>Folgendes passiert:

Nach der Eingabe gültiger Azure AD-Kontoanmeldeinformationen wird versucht, das Gerät mit der zugeordneten Azure AD-Organisation zu verknüpfen. Ist dies erfolgreich, stellt das Gerät Mitarbeiter in der Organisation als lokale Administratoren auf dem Gerät bereit. Wenn der Azure AD-Mandant entsprechend konfiguriert wurde, erfolgt ebenfalls eine Registrierung des Gerät in MDM.

### <a name="use-active-directory-domain-services"></a><a href="" id="use-active-directory"></a>Active Directory-Domänendienste verwenden

Auf dieser Seite wird zur Eingabe von Anmeldeinformationen zum Beitritt zu einer Domäne aufgefordert, sodass das Surface Hub eine Sicherheitsgruppe als Administratoren des Geräts bereitstellen kann.

Nach dem Beitritt des Geräts zu einer Domäne müssen Sie eine Sicherheitsgruppe aus der entsprechenden Domäne angeben. Diese Sicherheitsgruppe wird als Administratoren im Surface Hub bereitgestellt, und alle Mitglieder der Sicherheitsgruppe können ihre Anmeldeinformationen für die Domäne eingeben, um auf die Einstellungen zuzugreifen.

![Abbildungder Seite zur Einrichtung von Administratoren mithilfe des Domänenbeitritts.](images/setupdomainjoin.png)

### <a name="details"></a>Details

Die folgende Eingabe ist erforderlich:

-   **Domäne:** Dies ist der vollqualifizierte Domänenname (FQDN) der Domäne, der Sie beitreten möchten. Eine Sicherheitsgruppe aus dieser Domäne kann zum Verwalten des Geräts verwendet werden.
-   **Benutzername:** Der Benutzername eines Kontos, das über ausreichende Berechtigungen für den Beitritt zur angegebenen Domäne verfügt. 
-   **Kennwort:** Das Kennwort für das Konto.

Nachdem die Anmeldeinformationen überprüft wurden, werden Sie zur Eingabe eines Sicherheitsgruppennamens aufgefordert. Diese ist eine Pflichteingabe.

![Abbildung der Seite zur Eingabe einer Sicherheitsgruppe.](images/setupsecuritygroup-1.png)

### <a name="what-happens"></a>Folgendes passiert:

Anhand der angegebenen Domäne, der Kontoanmeldeinformationen auf der Seite [Active Directory-Domänendienste verwenden](#use-active-directory) und des Gerätenamens auf der Seite [Gerät benennen](#name-this-device) versucht das Surface Hub, der Domäne beizutreten. War der Beitritt erfolgreich, wird die Erstausführung fortgesetzt, und es wird nach einer Sicherheitsgruppe gefragt. War der Beitritt nicht erfolgreich, wird die Erstausführung angehalten, und Sie werden zur Änderung der angegebenen Informationen aufgefordert.

War der Beitritt erfolgreich, wird die Seite **Sicherheitsgruppe eingeben** angezeigt. Wenn Sie auf die Schaltfläche **Auswählen** auf dieser Seite klicken, wird nach der angegebenen Sicherheitsgruppe in der Domäne gesucht. Wenn gefunden, wird die Gruppe überprüft. Klicken Sie auf **Fertig stellen**, um den Erstausführungsprozess abzuschließen.

>[!NOTE]
>Wenn Sie einer Domäne beitreten, kann der Beitritt nur durch Zurücksetzen des Geräts aufgehoben werden.

 

### <a name="use-a-local-admin"></a>Lokalen Administrator verwenden

Wenn Sie Azure Active Directory (Azure AD) oder Active Directory (AD) nicht zum Verwalten des Surface Hub verwenden möchten, müssen Sie ein lokales Administratorkonto erstellen.

![Abbildungder Seite zur Einrichtung eines Administratorkontos für den lokalen Administrator.](images/setuplocaladmin.png)

### <a name="details"></a>Details

Die folgende Eingabe ist erforderlich:

-   **Benutzername:** Dies ist der Benutzername des lokalen Administratorkontos, das für diesen Surface Hub erstellt werden wird.
-   **Kennwort:** Dies ist das Kennwort für das Gerätekonto.
-   **Kennwort erneut eingeben:** Bestätigen Sie das zuvor eingegebene Kennwort.

### <a name="what-happens"></a>Folgendes passiert:

Nach dem Eingeben der Anmeldeinformationen wird versucht, ein neues Administratorkonto zu erstellen. Wenn dies erfolgreich ist, wird die Erstausführung beendet. Wenn dies nicht erfolgreich ist, werden Sie zur Eingabe anderer Anmeldeinformationen aufgefordert.

## <a name="update-the-surface-hub"></a><a href="" id="update-surface-hub"></a>Aktualisieren des Surface Hub


>[!IMPORTANT]
>Bevor Sie Updates installieren, lesen Sie unbedingt die Informationen unter [Speichern des BitLocker-Schlüssels](save-bitlocker-key-surface-hub.md), und stellen Sie sicher, dass Sie über eine Sicherungskopie des Schlüssels verfügen.

 

Um die neuesten Features und Updates zu erhalten, aktualisieren Sie das Surface Hub direkt im Anschluss an die Erstausführung.

1.  Stellen Sie sicher, dass das Gerät Zugriff auf die Windows hat. 
2.  Öffnen Sie die Einstellungen, klicken Sie auf **Update und Sicherheit**, **Windows Update** und anschließend auf **Nach Updates suchen**.
3.  Wenn Updates verfügbar sind, werden sie heruntergeladen. Nach dem Download klicken Sie auf die Schaltfläche **Jetzt aktualisieren**, um die Updates zu installieren.
4.  Befolgen Sie die Anweisungen auf dem Bildschirm, nachdem die Updates installiert wurden. Gegebenenfalls muss das Gerät neu gestartet werden.

 

 





