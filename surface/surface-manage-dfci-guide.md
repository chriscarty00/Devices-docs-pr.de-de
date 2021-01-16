---
title: Intune-Verwaltung von Surface UEFI-Einstellungen
description: In diesem Artikel wird erläutert, wie Sie eine DFCI-Umgebung in Microsoft Intune konfigurieren und Firmwareeinstellungen für zielorientierte Surface-Geräte verwalten.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
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
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271569"
---
# Intune-Verwaltung von Surface UEFI-Einstellungen

## Einführung

Die Möglichkeit, Geräte aus der Cloud zu verwalten, hat die Bereitstellung und Bereitstellung der IT während des gesamten Lebenszyklus erheblich vereinfacht. Mit in [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)integrierten Device Firmware Configuration Interface (DFCI)-Profilen erweitert die Surface -UEFI-Verwaltung den modernen Verwaltungsstapel bis auf die UEFI-Hardwareebene. DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, ermöglicht die Steuerung von Sicherheitseinstellungen, einschließlich Startoptionen und integrierter Peripheriegeräte, und bildet die Grundlage für erweiterte Sicherheitsszenarien in der Zukunft. Antworten auf häufig gestellte Fragen finden Sie unter [Ignite 2019: Ankündigung](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)der Remoteverwaltung von Surface -UEFI-Einstellungen von Intune .

### Hintergrund

Wie alle Computer unter Windows 10 verlassen sich die Geräte von Surface auf code, der im SoC gespeichert ist, der es der CPU ermöglicht, eine Schnittstelle mit Festplatten, Anzeigegeräten, USB-Ports und anderen Geräten zu erstellen. Die in diesem schreibgeschützten Speicher (ROM) gespeicherten Programme werden als Firmware (während auf dynamischen Medien gespeicherte Programme als Software bekannt sind) bekannt.

Im Gegensatz zu anderen Windows 10-Geräten, die derzeit auf dem Markt erhältlich sind, bietet Surface it-Administratoren die Möglichkeit, Firmware über eine umfangreiche Reihe von UEFI-Konfigurationseinstellungen zu konfigurieren und zu verwalten. Dies bietet eine Ebene der Hardwarekontrolle über die softwarebasierte Richtlinienverwaltung, wie sie über Richtlinien für die mobile Geräteverwaltung (Mobile Device Management, MDM), Configuration Manager oder Gruppenrichtlinien implementiert wird. Beispielsweise können Organisationen, die Geräte in äußerst sicheren Bereichen mit vertraulichen Informationen bereitstellen, die Kameranutzung verhindern, indem sie Funktionen auf Hardwareebene entfernen. Aus Geräte sicht entspricht das Deaktivieren der Kamera über eine Firmwareeinstellung dem physischen Entfernen der Kamera. Vergleichen Sie die zusätzliche Sicherheit der Verwaltung auf Firmwareebene mit der Ausschließlichung von Betriebssystemsoftwareeinstellungen. Wenn Sie beispielsweise den Windows-Audiodienst über eine Richtlinieneinstellung in einer Domänenumgebung deaktivieren, könnte ein lokaler Administrator den Dienst weiterhin erneut aktivieren.

### DFCI im Vergleich zu SEMM

Bisher war für die Verwaltung der Firmware die Registrierung von Geräten im Surface Enterprise Management Mode (SEMM) mit dem Aufwand für laufende manuelle IT-intensive Aufgaben erforderlich. Beispielsweise erfordert SEMM, dass die IT-Mitarbeiter physisch auf jeden PC zugreifen, um im Rahmen des Zertifikatverwaltungsprozesses eine zweistellige Pin ein eingeben zu können. Obwohl SEMM eine gute Lösung für Organisationen in einer rein lokalen Umgebung bleibt, ist die Verwendung durch die Komplexität und die itintensiven Anforderungen kostspielig.

 Mit integrierten Funktionen für die Verwaltung von UEFI-Firmware in Microsoft Intune ist die Möglichkeit, Hardware zu sperren, vereinfacht und einfacher mit neuen Features für Die Bereitstellung, Sicherheit und optimierte Aktualisierung in einer einzigen Konsole, die jetzt als [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)vereinheitlicht ist, zu verwenden. Die folgende Abbildung zeigt UEFI-Einstellungen, die direkt auf dem Gerät (links) und in der Endpoint -Manager-Konsole (rechts) angezeigt werden.

![Auf dem Gerät (links) und in der Endpoint -Manager-Konsole (rechts) angezeigte UEFI-Einstellungen](images/uefidfci.png)

DfCI ermöglicht vorerst die Verwaltung ohne Touch, sodass keine manuelle Interaktion durch die IT-Administratoren erforderlich ist. DFCI wird über Windows Autopilot mithilfe der Geräteprofilfunktion in Intune bereitgestellt. Mit einem Geräteprofil können Sie Einstellungen hinzufügen und konfigurieren, die dann auf Geräten bereitgestellt werden können, die für die Verwaltung in Ihrer Organisation registriert sind. Sobald das Gerät das Geräteprofil empfängt, werden die Features und Einstellungen automatisch angewendet. Beispiele für allgemeine Geräteprofile sind E-Mail, Geräteeinschränkungen, VPN, WLAN und administrative Vorlagen. DFCI ist einfach ein zusätzliches Geräteprofil, mit dem Sie die UEFI-Konfigurationseinstellungen aus der Cloud verwalten können, ohne die lokale Infrastruktur verwalten zu müssen.  

## Unterstützte Geräte

DFCI wird auf den folgenden Geräten unterstützt:

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go

> [!NOTE]
> Surface Pro X unterstützt keine Verwaltung von DFCI-Einstellungen für integrierte Kamera, Audio und WLAN/Bluetooth.

## Voraussetzungen

- Geräte müssen von einem Microsoft [Cloud Solution Provider (CSP)-Partner](https://partner.microsoft.com/membership/cloud-solution-provider) oder #A0 bei Windows Autopilot registriert werden.

- Bevor Sie DFCI für Surface konfigurieren, sollten Sie mit den Konfigurationsanforderungen für Autopilot in  [Microsoft Intune](https://docs.microsoft.com/intune/) und Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD) vertraut sein.

## Vorbemerkungen

Fügen Sie Ihre Ziel-Surface-Geräte einer Azure AD-Sicherheitsgruppe hinzu. Weitere Informationen zum Erstellen und Verwalten von Sicherheitsgruppen finden Sie in der [Intune-Dokumentation.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## Konfigurieren der Verwaltung von DFCI für Surface-Geräte

Eine DFCI-Umgebung erfordert das Einrichten eines DFCI-Profils, das die Einstellungen enthält, und eines Autopilot-Profils, um die Einstellungen auf registrierte Geräte anzuwenden. Außerdem wird ein Registrierungsstatusprofil empfohlen, um sicherzustellen, dass die Einstellungen während des Setups derOoBE nach unten übertragen werden, wenn Benutzer das Gerät zum ersten Mal starten. In diesem Handbuch wird erläutert, wie Sie die DFCI-Umgebung konfigurieren und die UEFI-Konfigurationseinstellungen für zielorientierte Surface-Geräte verwalten.

## Erstellen eines DFCI-Profils

Erstellen Sie vor dem Konfigurieren von DFCI-Richtlinieneinstellungen zuerst ein DFCI-Profil, und weisen Sie es der Azure AD-Sicherheitsgruppe zu, die Ihre Zielgeräte enthält.

1. Melden Sie sich bei Ihrem Mandanten unter devicemanagement.microsoft.com.
2. Wählen Sie im Microsoft Endpoint Manager Admin Center "Geräte **> Konfigurationsprofile"** > Profil erstellen und einen Namen eingeben. Beispiel: **DFCI-Konfigurationsrichtlinie.**
3. Wählen **Sie Windows 10 und höher für** den Plattformtyp aus.
4. Wählen Sie in der Dropdownliste "Profiltyp" die Option **"Device Firmware Configuration Interface"** aus, um das Blatt DFCI zu öffnen, das alle verfügbaren Richtlinieneinstellungen enthält. Informationen zu den Einstellungen für DFCI finden Sie in Tabelle 1 auf dieser Seite oder in der [Intune-Dokumentation.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) Sie können die Einstellungen für DFCI während des anfänglichen Setups oder höher konfigurieren, indem Sie das DfCI-Profil bearbeiten.

    ![Erstellen eines DFCI-Profils](images/df1.png)

5. Klicken Sie **auf "OK",** und wählen Sie dann **"Erstellen" aus.**
6. Wählen **Sie Aufgaben** aus, und wählen Sie unter "Gruppen auswählen" die Azure AD-Sicherheitsgruppe aus, die Ihre Zielgeräte enthält, wie in der folgenden Abbildung dargestellt. **** Klicken Sie auf **Speichern**.

    ![Sicherheitsgruppe zuweisen](images/df2a.png)

## Erstellen eines Autopilotprofils

1. Wählen Sie im Endpoint Manager unter devicemanagement.microsoft.com Geräte aus, > die Registrierung von **Windows** aktivieren, und führen Sie einen Bildlauf nach unten zu **Bereitstellungsprofilen durch.**
2. Wählen **Sie "Profil erstellen"** aus, und geben Sie einen Namen ein. Beispiel: **Mein Autopilot-Profil,** und wählen Sie **"Weiter" aus.**
3. Wählen Sie die folgenden Einstellungen aus:

    - Bereitstellungsmodus: **Benutzergesteuert**.
    - Join type: Azure **AD joined**.

4. Lassen Sie die verbleibenden Standardeinstellungen unverändert, und wählen **Sie "Weiter"** aus, wie in der folgenden Abbildung dargestellt.

    ![Erstellen eines Autopilotprofils](images/df3b.png)

5. Wählen Sie auf der Seite "Zuweisungen" **"Gruppen auswählen" aus, die sie** enthalten sollen, und klicken Sie auf Ihre Azure AD-Sicherheitsgruppe. Wählen Sie **Weiter** aus.
6. Akzeptieren Sie die Zusammenfassung, und wählen Sie dann Erstellen **aus.** Das Autopilotprofil wird nun erstellt und der Gruppe zugewiesen.

## Seite "Registrierungsstatus konfigurieren"

Um sicherzustellen, dass geräte die DFCI-Konfiguration während der OOBE anwenden, bevor sich Benutzer anmelden, müssen Sie den Registrierungsstatus konfigurieren.

Weitere Informationen finden Sie auf der Seite ["Einrichten einer Registrierungsstatusseite".](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)


## Konfigurieren von DFCI-Einstellungen auf Surface-Geräten

DFCI enthält einen optimierten Satz von UEFI-Konfigurationsrichtlinien, die ein zusätzliches Maß an Sicherheit bieten, indem Geräte auf Hardwareebene gesperrt werden. DFCI ist für die Verwendung in Verbindung mit Verwaltungseinstellungen für mobile Geräte auf Softwareebene konzipiert. Beachten Sie, dass sich die DfCI-Einstellungen nur auf Hardwarekomponenten auswirken, die in Surface Geräte integrierte sind, und nicht auf angeschlossene Peripheriegeräte wie USB-Webcams erweitert werden. (Sie können jedoch Geräteeinschränkungsrichtlinien in Intune verwenden, um den Zugriff auf angeschlossene Peripheriegeräte auf Softwareebene zu deaktivieren).

Sie konfigurieren die DFCI-Richtlinieneinstellungen, indem Sie das DfCI-Profil im Endpunkt-Manager bearbeiten, wie in der folgenden Abbildung dargestellt. 

- Wählen Sie im Endpoint Manager unter devicemanagement.microsoft.com die Option "Geräte **> Windows >-Konfigurationsprofile" > "DFCI-Profilname"**> "Eigenschaften" > aus.

    ![Konfigurieren von EINSTELLUNGEN für DFCI](images/dfciconfig.png)

### Blockieren des Benutzerzugriffs auf die UEFI-Einstellungen

Für viele Kunden ist die Möglichkeit, Benutzer am Ändern von UEFI-Einstellungen zu blockieren, von entscheidender Bedeutung und ein Hauptgrund für die Verwendung von DFCI. Wie in Tabelle 1 aufgeführt, wird dies über die Einstellung "Lokalen Benutzer das Ändern von **UEFI-Einstellungen zulassen" verwaltet.** Wenn Sie diese Einstellung nicht bearbeiten oder konfigurieren, können lokale Benutzer alle UEFI-Einstellungen ändern, die nicht von Intune verwaltet werden. Daher wird dringend empfohlen, die Änderung von Einstellungen für die **UEFI** für lokalen Benutzer zu deaktivieren.
Mit den restlichen DFCI-Einstellungen können Sie Funktionen deaktivieren, die benutzern andernfalls zur Verfügung stehen würden. Wenn Sie z. B. vertrauliche Informationen in äußerst sicheren Bereichen schützen müssen, können Sie die Kamera deaktivieren, und wenn Sie nicht möchten, dass Benutzer von einem USB-Laufwerk starten, können Sie dies auch deaktivieren.

### Tabelle1. DFCI-Szenarien

| Ziel der Geräteverwaltung                        | Konfigurationsschritte                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Blockieren der Änderung von Einstellungen für die UEFI für lokale Benutzer | Wählen **Sie unter "Sicherheitsfeatures> lokalen Benutzern das Ändern von UEFI-Einstellungen erlauben,** die Option **Keine aus.**              |
| Deaktivieren von Kameras                               | Wählen **Sie unter "Built in Hardware > Cameras"** die Option **"Deaktiviert" aus.**                                       |
| Deaktivieren von Mikrofonen und Lautsprechern              | Wählen Sie unter "Integrierte **Hardware- > Mikrofone und Lautsprecher"** die Option **"Deaktiviert" aus.**                      |
| Deaktivieren von Funkaktivierungen (Bluetooth, WLAN)             | Wählen Sie unter "Built **in Hardware > Radios (Bluetooth, WI-Fi, etc...)"** die Option **"Deaktiviert" aus.**                   |
| Starten von externen Medien deaktivieren (USB, SD)    | Wählen **Sie unter "Built in Hardware > Boot Options > Boot from external media (USB, SD)**" die Option **"Deaktiviert" aus.** |

> [!CAUTION]
> Die **Einstellung "Funkgeräte deaktivieren" (Bluetooth, WLAN)** sollte nur auf Geräten verwendet werden, die über eine kabelgebundene Ethernetverbindung verfügen.
 
> [!NOTE]
>  DFCI in Intune enthält zwei Einstellungen, die derzeit nicht für Surface-Geräte gelten: (1) CPU- und E/A-Virtualisierung und (2) Deaktivieren des Startes von Netzwerkadaptern.
 
Intune bietet Bereichstags zum Delegieren von Administratorrechten und Anwendbarkeitsregeln zum Verwalten von Gerätetypen. Weitere Informationen zur Unterstützung der Richtlinienverwaltung und ausführliche Informationen zu allen DFCI-Einstellungen finden Sie in der [Microsoft Intune-Dokumentation.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

## Registrieren von Geräten in Autopilot

Wie oben erwähnt, kann DFCI nur auf Geräten angewendet werden, die von Ihrem Händler oder Händler in Windows Autopilot registriert sind, und wird nur unter Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X und Surface Laptop 3 unterstützt. Aus Sicherheitsgründen ist es nicht möglich, Ihre Geräte in Autopilot "selbst bereitstellen". Weitere Informationen finden Sie unter Surface [Registration Support für Windows Autopilot](surface-autopilot-registration-support.md). 

## Manuelles Synchronisieren von Autopilot-Geräten

Obwohl die Richtlinieneinstellungen von Intune in der Regel fast sofort angewendet werden, kann es zu einer Verzögerung von 10 Minuten kommen, bevor die Einstellungen auf Zielgeräten wirksam werden. In seltenen Fällen sind Verzögerungen von bis zu 8 Stunden möglich. Um sicherzustellen, dass die Einstellungen so schnell wie möglich angewendet werden (z. B. in Testszenarien), können Sie die Zielgeräte manuell synchronisieren.

- Wechseln Sie im Endpoint Manager bei devicemanagement.microsoft.com zu "Geräte > Geräteregistrierung > windows-Registrierung **> Windows Autopilot-Geräte,** und wählen Sie **"Synchronisieren" aus.**

 Weitere Informationen finden Sie unter ["Manuelles Synchronisieren Ihres Windows-Geräts".](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> Wenn Sie Einstellungen direkt in UEFI anpassen, müssen Sie sicherstellen, dass das Gerät vollständig mit der standardmäßigen Windows-Anmeldung neu gestartet wird.

## Überprüfen von UEFI-Einstellungen auf DFCI-verwalteten Geräten

In einer Testumgebung können Sie die Einstellungen in der Surface -UEFI-Schnittstelle überprüfen.

1. Öffnen Sie das Surface UEFI, das gleichzeitig das Drücken der **Tasten "Volume +"** und **"Ein/Aus"** umfasst.
2. Wählen Sie **"Geräte" aus.** Das Menü "UEFI" enthält konfigurierte Einstellungen, wie in der folgenden Abbildung dargestellt.

    ![Surface UEFI](images/df3.png)

    Beachten Sie, wie:

      - Die Einstellungen sind ausgegraut, da lokale Benutzer die Einstellung **"UEFI** ändern" auf "Keine" festlegen.
      - Die Audiowiedergabe ist deaktiviert, da **Mikrofone und Lautsprecher** auf **"Deaktiviert" festgelegt sind.**

## Entfernen von Richtlinieneinstellungen für DFCI

Wenn Sie ein DFCI-Profil erstellen, bleiben alle konfigurierten Einstellungen auf allen Geräten im Verwaltungsbereich des Profils wirksam. Sie können die Richtlinieneinstellungen für DFCI nur entfernen, indem Sie das Profil direkt bearbeiten.

Wenn das ursprüngliche DFCI-Profil gelöscht wurde, können Sie Richtlinieneinstellungen entfernen, indem Sie ein neues Profil erstellen und die Einstellungen entsprechend bearbeiten.

## Entfernen der Verwaltung von DFCI

**So entfernen Sie die DFCI-Verwaltung und kehren das Gerät in den werksseitig neuen Zustand zurück:**

1. Zurückziehen des Geräts aus Intune:
    1. In Endpoint Manager at devicemanagement.microsoft.com, choose **Groups > All Devices**. Wählen Sie die Geräte aus, die Sie zurückziehen möchten, und wählen Sie dann **"Zurückziehen/Zurückziehen" aus.** Weitere Informationen finden Sie unter "Entfernen von [Geräten mithilfe von Wipe", "Zurückziehen"](https://docs.microsoft.com/intune/remote-actions/devices-wipe)oder "Manuelles Entfernen der Registrierung des Geräts". 
2. Löschen Sie die Autopilot-Registrierung aus Intune:
    1.  Wählen **Sie "Geräteregistrierung" > "Windows-Registrierung" > "Geräte" aus.**
    2. Wählen Sie unter Windows Autopilot Geräte die Geräte aus, die Sie löschen möchten, und wählen Sie dann **"Löschen" aus.**
3. Verbinden Sie das Gerät mit dem verkabelten Internet mit dem Ethernetadapter des Surface-Marken. Starten Sie das Gerät neu, und öffnen Sie das UEFI-Menü (drücken und halten Sie die Lautstärketaste gedrückt, während Sie gleichzeitig den Netzschalter drücken und loslassen).
4. Wählen **Sie "> Konfigurieren > Aktualisieren** aus dem Netzwerk" und dann **"Abmelden" aus.**

Um das Gerät weiterhin mit Intune zu verwalten, aber ohne DFCI-Verwaltung, registrieren Sie das Gerät selbst bei Autopilot und registrieren es bei Intune. DFCI wird nicht auf selbst registrierte Geräte angewendet.

## Mehr erfahren
- [Ignite 2019: Ankündigung der Remoteverwaltung von Surface -UEFI-Einstellungen von Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot und Surface-Geräte](windows-autopilot-and-surface-devices.md) 
- [Verwenden von DFCI-Profilen auf Windows-Geräten in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
