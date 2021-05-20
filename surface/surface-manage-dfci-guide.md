---
title: Intune-Verwaltung von Surface UEFI-Einstellungen
description: In diesem Artikel wird erläutert, wie Sie eine DFCI-Umgebung in Microsoft Intune konfigurieren und Firmwareeinstellungen für bestimmte Surface-Geräte verwalten.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4
ms.openlocfilehash: b74aeab45dd2354550f0dff712af5b37b853111c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576515"
---
# <a name="intune-management-of-surface-uefi-settings"></a>Intune-Verwaltung von Surface UEFI-Einstellungen

## <a name="introduction"></a>Einführung

Die Möglichkeit, Geräte aus der Cloud zu verwalten, hat die BEREITSTELLUNG und Bereitstellung von IT über den gesamten Lebenszyklus hinweg erheblich vereinfacht. Mit in Microsoft Intune integrierten Profilen [für](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)die Gerätefirmwarekonfigurationsschnittstelle (Device Firmware Configuration Interface, DFCI) erweitert die Surface UEFI-Verwaltung den modernen Verwaltungsstapel auf die UEFI-Hardwareebene. DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Steuerung von Sicherheitseinstellungen, einschließlich Startoptionen und integrierten Peripheriegeräten, und legt die Grundlagen für erweiterte Sicherheitsszenarien in der Zukunft. Antworten auf häufig gestellte Fragen finden Sie unter [Ignite 2019: Ankündigung](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)der Remoteverwaltung von Surface UEFI-Einstellungen von Intune .

### <a name="background"></a>Hintergrund

Wie alle Computer, auf Windows 10, verwenden Surface-Geräte code, der in der SoC gespeichert ist, mit dem die CPU eine Schnittstelle mit Festplatten, Anzeigegeräten, USB-Ports und anderen Geräten verwenden kann. Die in diesem schreibgeschützten Speicher (ROM) gespeicherten Programme werden als Firmware (während programme, die in dynamischen Medien gespeichert sind, als Software bekannt) bekannt.

Im Gegensatz zu anderen Windows 10, die heute auf dem Markt verfügbar sind, bietet Surface IT-Administratoren die Möglichkeit, Firmware über eine reihe von UEFI-Konfigurationseinstellungen zu konfigurieren und zu verwalten. Dies bietet eine Ebene der Hardwaresteuerung neben der softwarebasierten Richtlinienverwaltung, die über Mobile Device Management (MDM)-Richtlinien, Configuration Manager oder Gruppenrichtlinien implementiert wird. Beispielsweise können Organisationen, die Geräte in hochsicheren Bereichen mit vertraulichen Informationen bereitstellen, die Kameranutzung verhindern, indem sie die Funktionalität auf Hardwareebene entfernen. Aus Geräte sicht ist das Deaktivieren der Kamera über eine Firmwareeinstellung gleichbedeutend mit dem physischen Entfernen der Kamera. Vergleichen Sie die zusätzliche Sicherheit der Verwaltung auf Firmwareebene mit der ausschließlichen Nsung von Betriebssystemsoftwareeinstellungen. Wenn Sie beispielsweise den Windows über eine Richtlinieneinstellung in einer Domänenumgebung deaktivieren, kann ein lokaler Administrator den Dienst weiterhin erneut aktivieren.

### <a name="dfci-versus-semm"></a>DFCI im Vergleich zu SEMM

Zuvor war für die Verwaltung der Firmware die Registrierung von Geräten im Surface Enterprise Management Mode (SEMM) mit dem Aufwand für laufende manuelle IT-intensive Aufgaben erforderlich. Semm erfordert beispielsweise, dass IT-Mitarbeiter physisch auf jeden PC zugreifen, um im Rahmen des Zertifikatverwaltungsprozesses einen zweistelligen Pin ein eingeben zu können. Obwohl SEMM weiterhin eine gute Lösung für Organisationen in einer rein lokalen Umgebung ist, ist die Verwendung durch die Komplexität und die IT-intensiven Anforderungen kostspielig.

 Mit integrierten UEFI-Firmwareverwaltungsfunktionen in Microsoft Intune ist die Möglichkeit, Hardware zu sperren, vereinfacht und einfacher mit neuen Features für bereitstellung, Sicherheit und optimierte Aktualisierung in einer einzigen Konsole, die jetzt als Microsoft Endpoint Manager [vereinheitlicht](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)ist. Die folgende Abbildung zeigt UEFI-Einstellungen, die direkt auf dem Gerät (links) und in der Endpoint Manager (rechts) angezeigt werden.

![UEFI-Einstellungen, die auf dem Gerät (links) und in der Endpoint Manager (rechts) angezeigt werden](images/uefidfci.png)

DfCI ermöglicht eine Verwaltung ohne Touch-Touch, sodass keine manuelle Interaktion durch IT-Administratoren erforderlich ist. DFCI wird über Windows Autopilot mithilfe der Geräteprofilfunktion in Intune bereitgestellt. Mit einem Geräteprofil können Sie Einstellungen hinzufügen und konfigurieren, die dann auf Geräten bereitgestellt werden können, die in Ihrer Organisation für die Verwaltung registriert sind. Sobald das Gerät das Geräteprofil empfängt, werden die Features und Einstellungen automatisch angewendet. Beispiele für häufige Geräteprofile sind E-Mail, Geräteeinschränkungen, VPN, WLAN und administrative Vorlagen. DFCI ist einfach ein zusätzliches Geräteprofil, mit dem Sie UEFI-Konfigurationseinstellungen aus der Cloud verwalten können, ohne die lokale Infrastruktur verwalten zu müssen.  

## <a name="supported-devices"></a>Unterstützte Geräte

DFCI wird auf den folgenden Geräten unterstützt:

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4

> [!NOTE]
> Surface Pro X unterstützt keine Verwaltung von DFCI-Einstellungen für integrierte Kamera, Audio und WLAN/Bluetooth.

## <a name="prerequisites"></a>Voraussetzungen

- Geräte müssen bei Windows autopilot von einem [#A0 (CSP Microsoft Cloud Solution Provider oder](https://partner.microsoft.com/membership/cloud-solution-provider) OEM-Händler registriert werden.

- Bevor Sie DFCI für Surface konfigurieren, sollten Sie mit den Konfigurationsanforderungen für Autopilot [in](https://docs.microsoft.com/intune/) Microsoft Intune und [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD) vertraut sein.

## <a name="before-you-begin"></a>Vorbemerkungen

Fügen Sie Ihre Ziel-Surface-Geräte einer Azure AD-Sicherheitsgruppe hinzu. Weitere Informationen zum Erstellen und Verwalten von Sicherheitsgruppen finden Sie in der [Intune-Dokumentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

## <a name="configure-dfci-management-for-surface-devices"></a>Konfigurieren der DFCI-Verwaltung für Surface-Geräte

Eine DFCI-Umgebung erfordert das Einrichten eines DFCI-Profils, das die Einstellungen enthält, und ein Autopilot-Profil, um die Einstellungen auf registrierte Geräte anzuwenden. Es wird auch empfohlen, ein Registrierungsstatusprofil zu verwenden, um sicherzustellen, dass die Einstellungen während der OOBE-Einrichtung nach unten geschubsert werden, wenn Benutzer das Gerät zum ersten Mal starten. In diesem Handbuch wird erläutert, wie Sie die DFCI-Umgebung konfigurieren und UEFI-Konfigurationseinstellungen für zielorientierte Surface-Geräte verwalten.

## <a name="create-dfci-profile"></a>Erstellen eines DFCI-Profils

Erstellen Sie vor dem Konfigurieren der DFCI-Richtlinieneinstellungen zunächst ein DFCI-Profil, und weisen Sie es der Azure AD-Sicherheitsgruppe zu, die Ihre Zielgeräte enthält.

1. Melden Sie sich bei Ihrem Mandanten unter devicemanagement.microsoft.com.
2. Wählen Sie Microsoft Endpoint Manager Admin Center Geräte **> Konfigurationsprofile aus,** > Profil erstellen und einen Namen eingeben. z. **B. DFCI-Konfigurationsrichtlinie.**
3. Wählen **Windows 10 und höher für den** Plattformtyp aus.
4. Wählen Sie in der Dropdownliste Profiltyp die Option **Gerätefirmwarekonfigurationsschnittstelle** aus, um das BLATT DFCI zu öffnen, das alle verfügbaren Richtlinieneinstellungen enthält. Informationen zu DEN DFCI-Einstellungen finden Sie in Tabelle 1 auf dieser Seite oder in der [Intune-Dokumentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows). Sie können DFCI-Einstellungen während des anfänglichen Setupvorgangs oder höher konfigurieren, indem Sie das DFCI-Profil bearbeiten.

    ![Erstellen eines DFCI-Profils](images/df1.png)

5. Klicken Sie **auf OK,** und wählen Sie **dann Erstellen aus.**
6. Wählen Sie **** **Zuordnungen** aus, und wählen Sie unter Gruppen auswählen aus, um die Azure AD-Sicherheitsgruppe auszuwählen, die Ihre Zielgeräte enthält, wie in der folgenden Abbildung dargestellt. Klicken Sie auf **Speichern**.

    ![Zuweisen einer Sicherheitsgruppe](images/df2a.png)

## <a name="create-autopilot-profile"></a>Erstellen eines Autopilot-Profils

1. Wählen Endpoint Manager unter devicemanagement.microsoft.com Geräte aus, **> Windows** registrieren möchten, und führen Sie einen Bildlauf nach unten zu **Bereitstellungsprofile aus.**
2. Wählen **Sie Profil erstellen** aus, und geben Sie einen Namen ein. Beispiel: **Mein Autopilot-Profil,** und wählen Sie **Weiter aus.**
3. Wählen Sie die folgenden Einstellungen aus:

    - Bereitstellungsmodus: **Benutzergesteuert**.
    - Join-Typ: Azure **AD ist beigetreten.**

4. Lassen Sie die verbleibenden Standardeinstellungen unverändert, und wählen Sie **Weiter**aus, wie in der folgenden Abbildung dargestellt.

    ![Erstellen eines Autopilot-Profils](images/df3b.png)

5. Wählen Sie auf der Seite Zuordnungen Gruppen auswählen aus, **die sie enthalten sollen,** und klicken Sie auf Ihre Azure AD-Sicherheitsgruppe. Wählen Sie **Weiter** aus.
6. Akzeptieren Sie die Zusammenfassung, und wählen Sie **dann Erstellen aus.** Das Autopilot-Profil wird nun erstellt und der Gruppe zugewiesen.

## <a name="configure-enrollment-status-page"></a>Konfigurieren der Registrierungsstatusseite

Um sicherzustellen, dass Geräte die DFCI-Konfiguration während der OOBE anwenden, bevor sich Benutzer anmelden, müssen Sie den Registrierungsstatus konfigurieren.

Weitere Informationen finden Sie unter [Einrichten einer Registrierungsstatusseite](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).


## <a name="configure-dfci-settings-on-surface-devices"></a>Konfigurieren von DFCI-Einstellungen auf Surface-Geräten

DFCI enthält einen optimierten Satz von UEFI-Konfigurationsrichtlinien, die ein zusätzliches Maß an Sicherheit bieten, indem Geräte auf Hardwareebene gesperrt werden. DFCI ist für die Verwendung in Verbindung mit Einstellungen für die Verwaltung mobiler Geräte auf Softwareebene konzipiert. Beachten Sie, dass die DFCI-Einstellungen nur auf Hardwarekomponenten in Surface-Geräten und nicht auf angeschlossene Peripheriegeräte wie USB-Webcams erweitert werden. (Sie können jedoch Geräteeinschränkungsrichtlinien in Intune verwenden, um den Zugriff auf angeschlossene Peripheriegeräte auf Softwareebene zu deaktivieren).

Sie konfigurieren DFCI-Richtlinieneinstellungen, indem Sie das DFCI-Profil aus Endpoint Manager bearbeiten, wie in der folgenden Abbildung dargestellt. 

- Wählen Endpoint Manager unter devicemanagement.microsoft.com die Option Geräte **> Windows > Konfigurationsprofile > "DFCI-Profilname" > Eigenschaften > Einstellungen**.

    ![Konfigurieren von DFCI-Einstellungen](images/dfciconfig.png)

### <a name="block-user-access-to-uefi-settings"></a>Blockieren des Benutzerzugriffs auf UEFI-Einstellungen

Für viele Kunden ist die Möglichkeit, Benutzer am Ändern von UEFI-Einstellungen zu blockieren, von entscheidender Bedeutung und ein Hauptgrund für die Verwendung von DFCI. Wie in Tabelle 1 aufgeführt, wird dies über die Einstellung Lokale Benutzer zum Ändern von **UEFI-Einstellungen zulassen verwaltet.** Wenn Sie diese Einstellung nicht bearbeiten oder konfigurieren, können lokale Benutzer alle UEFI-Einstellungen ändern, die nicht von Intune verwaltet werden. Daher wird dringend empfohlen, lokale Benutzer das Ändern von **UEFI-Einstellungen zulassen zu deaktivieren.**
Mit den restlichen DFCI-Einstellungen können Sie Funktionen deaktivieren, die benutzern ansonsten zur Verfügung stehen würden. Wenn Sie z. B. vertrauliche Informationen in hochsicheren Bereichen schützen müssen, können Sie die Kamera deaktivieren, und wenn Sie nicht möchten, dass Benutzer von USB-Laufwerken starten, können Sie dies auch deaktivieren.

### <a name="table-1-dfci-scenarios"></a>Tabelle 1: DFCI-Szenarien

| Ziel der Geräteverwaltung                        | Konfigurationsschritte                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Blockieren, dass lokale Benutzer UEFI-Einstellungen ändern | Wählen **Sie unter Sicherheitsfeatures > Lokalen Benutzer das Ändern von UEFI-Einstellungen erlauben**die Option Keine **aus.**              |
| Deaktivieren von Kameras                               | Wählen Sie unter Built **in Hardware > Cameras**die Option Deaktiviert **aus.**                                       |
| Deaktivieren von Mikrofonen und Lautsprechern              | Wählen Sie unter Integrierte **Hardware > Mikrofone und Lautsprecher**die Option Deaktiviert **aus.**                      |
| Deaktivieren von Radios (Bluetooth, WLAN)             | Wählen Sie unter Built **in Hardware > Radios (Bluetooth, WI-Fi usw.)** die Option **Deaktiviert aus.**                   |
| Deaktivieren des Startens von externen Medien (USB, SD)    | Wählen Sie unter Built **in Hardware > Boot Options > Boot from external media (USB, SD)** die Option **Deaktiviert aus.** |

> [!CAUTION]
> Die **Einstellung Funkgeräte deaktivieren (Bluetooth, WLAN)** sollte nur auf Geräten verwendet werden, die über eine verkabelte Ethernetverbindung verfügen.
 
> [!NOTE]
>  DFCI in Intune umfasst zwei Einstellungen, die derzeit nicht für Surface-Geräte gelten: (1) CPU- und IO-Virtualisierung und (2) Starten von Netzwerkadaptern deaktivieren.
 
Intune bietet Scope-Tags zum Delegieren von Administratorrechten und Anwendbarkeitsregeln zum Verwalten von Gerätetypen. Weitere Informationen zur Richtlinienverwaltungsunterstützung und vollständige Details zu allen DFCI-Einstellungen finden Sie [in Microsoft Intune Dokumentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).

## <a name="register-devices-in-autopilot"></a>Registrieren von Geräten in Autopilot

Wie oben erwähnt, kann DFCI nur auf Geräten angewendet werden, die von Ihrem Händler oder Händler in Windows Autopilot registriert sind und nur auf Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X und Surface Laptop 3 unterstützt werden. Aus Sicherheitsgründen ist es nicht möglich, Ihre Geräte in Autopilot "selbstzuliefern". Weitere Informationen finden Sie unter Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md). 

## <a name="manually-sync-autopilot-devices"></a>Manuelles Synchronisieren von Autopilot-Geräten

Obwohl Intune-Richtlinieneinstellungen in der Regel fast sofort angewendet werden, kann es zu einer Verzögerung von 10 Minuten kommen, bevor die Einstellungen auf zielgerichteten Geräten wirksam werden. In seltenen Fällen sind Verzögerungen von bis zu 8 Stunden möglich. Um sicherzustellen, dass Einstellungen so bald wie möglich angewendet werden (z. B. in Testszenarien), können Sie die Zielgeräte manuell synchronisieren.

- Wechseln Endpoint Manager unter devicemanagement.microsoft.com zu Geräte **> Geräteregistrierung > Windows Registrierung > Windows Autopilot-Geräten,** und wählen Sie **Synchronisieren aus.**

 Weitere Informationen finden Sie unter [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

> [!NOTE]
> Wenn Sie Einstellungen direkt in UEFI anpassen, müssen Sie sicherstellen, dass das Gerät vollständig auf die Standardeinstellungen Windows wird.

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a>Überprüfen von UEFI-Einstellungen auf DFCI-verwalteten Geräten

In einer Testumgebung können Sie die Einstellungen in der Surface UEFI-Schnittstelle überprüfen.

1. Öffnen Sie Surface UEFI, das gleichzeitig das Drücken der Tasten **Volume +** und **Power** umfasst.
2. Wählen Sie **Geräte aus.** Das UEFI-Menü gibt konfigurierte Einstellungen wieder, wie in der folgenden Abbildung dargestellt.

    ![Surface UEFI](images/df3.png)

    Beachten Sie, wie:

      - Die Einstellungen sind ausgegraut, da lokale Benutzer die **Einstellung UEFI** ändern zulassen auf Keine festgelegt ist.
      - Audio ist auf deaktiviert, da **Mikrofone** und Lautsprecher auf **Deaktiviert festgelegt sind.**

## <a name="removing-dfci-policy-settings"></a>Entfernen von DFCI-Richtlinieneinstellungen

Wenn Sie ein DFCI-Profil erstellen, bleiben alle konfigurierten Einstellungen auf allen Geräten im Bereich der Verwaltung des Profils wirksam. Sie können dfCI-Richtlinieneinstellungen nur entfernen, indem Sie das DFCI-Profil direkt bearbeiten.

Wenn das ursprüngliche DFCI-Profil gelöscht wurde, können Sie Richtlinieneinstellungen entfernen, indem Sie ein neues Profil erstellen und dann die Einstellungen entsprechend bearbeiten.

## <a name="removing-dfci-management"></a>Entfernen der DFCI-Verwaltung

**So entfernen Sie die DFCI-Verwaltung, und geben Sie das Gerät in den neuen Zustand zurück:**

1. Ziehen Sie das Gerät aus Intune zurück:
    1. Wählen Endpoint Manager unter devicemanagement.microsoft.com Gruppen > **Alle Geräte aus.** Wählen Sie die Geräte aus, die Sie zurückziehen möchten, und wählen Sie **dann Zurückziehen/Löschen aus.** Weitere Informationen finden Sie unter Entfernen von [Geräten mithilfe von Wipe, Zurückziehen oder manuelles Aufrollen des Geräts.](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 
2. Löschen der Autopilot-Registrierung aus Intune:
    1.  Wählen **Sie Geräteregistrierung > Windows Registrierung > Geräte aus.**
    2. Wählen Windows Sie unter Autopilot-Geräte die Geräte aus, die Sie löschen möchten, und wählen Sie dann **Löschen aus.**
3. Verbinden gerät an das verkabelte Internet mit Einem Surface-Ethernetadapter. Starten Sie das Gerät neu, und öffnen Sie das UEFI-Menü (drücken und halten Sie die Lautstärketaste gedrückt, während Sie auch die Netzschaltfläche drücken und loslassen).
4. Wählen **Sie Verwaltung > Konfigurieren > Aktualisieren** aus dem Netzwerk aus, und wählen Sie dann **Abmelden aus.**

Um das Gerät weiterhin mit Intune zu verwalten, aber ohne DFCI-Verwaltung, registrieren Sie das Gerät selbst bei Autopilot und registrieren Es bei Intune. DFCI wird nicht auf selbst registrierte Geräte angewendet.

## <a name="learn-more"></a>Mehr erfahren
- [Ignite 2019: Ankündigung der Remoteverwaltung von Surface UEFI-Einstellungen von Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot und Surface-Geräte](windows-autopilot-and-surface-devices.md) 
- [Verwenden von DFCI-Profilen auf Windows Geräten in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
