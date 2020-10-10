---
title: Intune-Verwaltung von Surface UEFI-Einstellungen
description: In diesem Artikel wird erläutert, wie Sie eine DFCI-Umgebung in Microsoft InTune konfigurieren und die Firmwareeinstellungen für zielgerichtete Surface-Geräte verwalten.
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
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: 20d1b187a565f210eedc632be1addeac5dd714ba
ms.sourcegitcommit: 7d5b0a7948eb540d6849a0e2c70a1058584cc5f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105860"
---
# Intune-Verwaltung von Surface UEFI-Einstellungen

## Einführung

Die Möglichkeit zum Verwalten von Geräten aus der Cloud hat die IT-Bereitstellung und-Bereitstellung im gesamten Lebenszyklus erheblich vereinfacht. Mit DFCI-Profilen (Device Firmware Configuration Interface), die in Microsoft InTune integriert sind (jetzt in [Public Preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)verfügbar), erweitert die Oberfläche-UEFI-Verwaltung den modernen Verwaltungs Stapel auf die UEFI-Hardwareebene. DFCI unterstützt die Zero-Touch-Bereitstellung, beseitigt BIOS-Kennwörter, bietet die Kontrolle über Sicherheitseinstellungen, einschließlich Startoptionen und integrierte Peripheriegeräte, und legt die Grundlagen für fortschrittliche Sicherheitsszenarien in der Zukunft fest. Antworten auf häufig gestellte Fragen finden Sie unter [Ignite 2019: Ankündigung der Remoteverwaltung von DGM-UEFI-Einstellungen aus InTune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

### Hintergrund

Wie bei jedem Computer, auf dem Windows 10 ausgeführt wird, beruhen die Surface-Geräte auf dem im SOC gespeicherten Code, der es der CPU ermöglicht, mit Festplatten, Anzeigegeräten, USB-Anschlüssen und anderen Geräten zu Schnitten. Die in diesem schreibgeschützten Speicher (Rom) gespeicherten Programme werden als Firmware bezeichnet (während Programme, die in dynamischen Medien gespeichert sind, als Software bezeichnet).

Im Gegensatz zu anderen auf dem Markt verfügbaren Windows 10-Geräten bietet Surface IT-Administratoren die Möglichkeit, die Firmware über einen umfangreichen Satz von UEFI-Konfigurationseinstellungen zu konfigurieren und zu verwalten. Dadurch wird eine Ebene der Hardwaresteuerung auf der Grundlage der softwarebasierten Richtlinienverwaltung bereitgestellt, wie Sie mithilfe von MDM-Richtlinien (Mobile Device Management), Configuration Manager oder Gruppenrichtlinien implementiert wurde. Organisationen, die Geräte in äußerst sicheren Bereichen mit vertraulichen Informationen bereitstellen, können beispielsweise die Kamera Nutzung verhindern, indem Sie die Funktionalität auf Hardwareebene entfernen. Aus Sicht des Geräts entspricht das Ausschalten der Kamera über eine Firmware-Einstellung dem physischen Entfernen der Kamera. Vergleichen Sie die zusätzliche Sicherheit der Verwaltung auf Firmware-Ebene, um sich nur auf die Softwareeinstellungen des Betriebssystems zu verlassen. Wenn Sie beispielsweise den Windows-Audiodienst über eine Richtlinieneinstellung in einer Domänenumgebung deaktivieren, kann ein lokaler Administrator den Dienst weiterhin wieder aktivieren.

### DFCI versus Semm

Bislang musste die Verwaltung der Firmware die Registrierung von Geräten in Surface Enterprise Management Mode (Semm) mit dem Overhead der laufenden manuellen IT-intensiven Aufgaben ausführen. Als Beispiel erfordert Semm, dass IT-Mitarbeiter physisch auf jeden PC zugreifen, um eine zweistellige Pin als Teil des Zertifikats Verwaltungsprozesses einzugeben. Zwar bleibt Semm eine gute Lösung für Organisationen in einer strikt lokalen Umgebung, doch die Komplexität und die IT-intensiven Anforderungen machen die Verwendung kostspielig.

Mit den neu integrierten UEFI-Firmware-Verwaltungsfunktionen in Microsoft InTune ist die Möglichkeit, die Hardware zu sperren, vereinfacht und mit neuen Features für Bereitstellung, Sicherheit und optimierte Updates in einer einzigen Konsole, die jetzt als [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)einheitlich ist, einfacher zu verwenden. Die folgende Abbildung zeigt die UEFI-Einstellungen, die direkt auf dem Gerät angezeigt werden (links) und in der Endpunkt-Manager-Konsole angezeigt werden (rechts).

![Auf dem Gerät (links) und in der Endpunkt-Manager-Konsole angezeigte UEFI-Einstellungen (rechts)](images/uefidfci.png)

Entscheidend ist, dass DFCI das Zero-Touch-Management ermöglicht, wodurch die manuelle Interaktion von IT-Administratoren nicht mehr erforderlich ist. DFCI wird mithilfe der Geräteprofil Funktion in InTune über Windows Autopilot bereitgestellt. Mit einem Geräteprofil können Sie Einstellungen hinzufügen und konfigurieren, die dann für Geräte bereitgestellt werden können, die für die Verwaltung in Ihrer Organisation registriert sind. Sobald das Gerät das Geräteprofil erhält, werden die Features und Einstellungen automatisch angewendet. Beispiele für allgemeine Geräteprofile sind e-Mail, Geräteeinschränkungen, VPN-, WLAN-und administrative Vorlagen. DFCI ist einfach ein zusätzliches Geräteprofil, mit dem Sie UEFI-Konfigurationseinstellungen aus der Cloud verwalten können, ohne die lokale Infrastruktur verwalten zu müssen.  

## Unterstützte Geräte

DFCI wird in den folgenden Geräten unterstützt:

- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- DGM-Buch 3
- Surface Laptop go

> [!NOTE]
> Surface pro X unterstützt nicht die Verwaltung von DFCI-Einstellungen für integrierte Kamera, Audio und WLAN/Bluetooth.

## Voraussetzungen

- Geräte müssen bei Windows Autopilot von einem [Microsoft Cloud Solution Provider (CSP)-Partner](https://partner.microsoft.com/membership/cloud-solution-provider) oder OEM-Verteiler registriert sein.

- Bevor Sie DFCI für Surface konfigurieren, sollten Sie mit den Konfigurationsanforderungen von Autopilot in  [Microsoft InTune](https://docs.microsoft.com/intune/) und [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD) vertraut sein.

## Vorbemerkungen

Fügen Sie Ihre Ziel Oberflächen Geräte einer Azure AD-Sicherheitsgruppe hinzu. Weitere Informationen zum Erstellen und Verwalten von Sicherheitsgruppen finden Sie in der [InTune-Dokumentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

## Konfigurieren der DFCI-Verwaltung für Surface-Geräte

Eine DFCI-Umgebung erfordert das Einrichten eines DFCI-Profils, das die Einstellungen und ein Autopilot-Profil enthält, um die Einstellungen auf registrierte Geräte anzuwenden. Ein Registrierungsstatus Profil wird ebenfalls empfohlen, um sicherzustellen, dass die Einstellungen während des OOBE-Setups heruntergedrückt werden, wenn Benutzer das Gerät zum ersten Mal starten. In diesem Leitfaden wird erläutert, wie die DFCI-Umgebung konfiguriert und UEFI-Konfigurationseinstellungen für zielgerichtete Surface-Geräte verwaltet werden.

## Erstellen eines DFCI-Profils

Bevor Sie die DFCI-Richtlinieneinstellungen konfigurieren, erstellen Sie zunächst ein DFCI-Profil, und weisen Sie es der Azure AD-Sicherheitsgruppe zu, die ihre Zielgeräte enthält.

1. Registrieren Sie sich bei Ihrem Mandanten unter Devicemanagement.Microsoft.com.
2. Wählen Sie im Microsoft Endpoint Manager Admin Center **Geräte > Konfigurationsprofile > Profil erstellen** aus, und geben Sie einen Namen ein. Beispiel: **DFCI-Konfigurationsrichtlinie.**
3. Wählen Sie **Windows 10 und höher** für den Plattformtyp aus.
4. Wählen Sie in der Dropdownliste Profiltyp die Option **Geräte Firmware-Konfigurationsschnittstelle** aus, um das DFCI-Blade mit allen verfügbaren Richtlinieneinstellungen zu öffnen. Informationen zu den DFCI-Einstellungen finden Sie in Tabelle 1 auf dieser Seite oder in der [InTune-Dokumentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows). Sie können DFCI-Einstellungen während des anfänglichen Setupvorgangs oder später durch Bearbeiten des DFCI-Profils konfigurieren.

    ![Erstellen eines DFCI-Profils](images/df1.png)

5. Klicken Sie auf **OK** , und wählen Sie dann **Erstellen**aus.
6. Wählen Sie **Aufgaben** aus, und wählen Sie unter **zu berücksichtigende Gruppen auswählen** die Azure AD-Sicherheitsgruppe aus, die ihre Zielgeräte enthält, wie in der folgenden Abbildung dargestellt. Klicken Sie auf **Speichern**.

    ![Sicherheitsgruppe zuweisen](images/df2a.png)

## Erstellen eines Autopilot-Profils

1. Wählen Sie in Endpunkt-Manager unter Devicemanagement.Microsoft.com **Geräte > Windows-Registrierung** aus, und Scrollen Sie nach unten zu **Bereitstellungs Profilen**.
2. Wählen Sie **Profil erstellen** aus, und geben Sie einen Namen ein. Beispiel: **mein Autopilot-Profil**, und wählen Sie **weiter**aus.
3. Wählen Sie die folgenden Einstellungen aus:

    - Bereitstellungsmodus: **Benutzer gesteuert**
    - Verknüpfungstyp: Azure **AD Joined**.

4. Lassen Sie die verbleibenden Standardeinstellungen unverändert, und wählen Sie **weiter**aus, wie in der folgenden Abbildung dargestellt.

    ![Erstellen eines Autopilot-Profils](images/df3b.png)

5. Wählen Sie auf der Seite Aufgaben die **Option Gruppen zum einbeziehen auswählen** aus, und klicken Sie auf Ihre Azure AD-Sicherheitsgruppe. Wählen Sie **Weiter** aus.
6. Übernehmen Sie die Zusammenfassung, und wählen Sie dann **Erstellen**aus. Das Autopilot-Profil wird nun erstellt und der Gruppe zugeordnet.

## Seite "Registrierungs Status konfigurieren"

Um sicherzustellen, dass Geräte die DFCI-Konfiguration während OOBE anwenden, bevor sich Benutzer anmelden, müssen Sie den Registrierungsstatus konfigurieren.

Weitere Informationen finden Sie unter [Einrichten einer Registrierungsstatus Seite](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).


## Konfigurieren von DFCI-Einstellungen auf Surface-Geräten

DFCI enthält eine optimierte Gruppe von UEFI-Konfigurationsrichtlinien, die ein zusätzliches Maß an Sicherheit bieten, indem Sie Geräte auf Hardwareebene sperren. DFCI ist für die Verwendung in Verbindung mit Einstellungen für die Verwaltung mobiler Geräte auf Softwareebene vorgesehen. Beachten Sie, dass sich die DFCI-Einstellungen nur auf Hardwarekomponenten auswirken, die in Surface-Geräte integriert sind, und nicht auf angeschlossenen Peripheriegeräten wie USB-Webcams. (Allerdings können Sie die Richtlinien für Geräteeinschränkungen in InTune verwenden, um den Zugriff auf angefügte Peripheriegeräte auf Softwareebene zu deaktivieren).

Sie konfigurieren DFCI-Richtlinieneinstellungen, indem Sie das DFCI-Profil von Endpoint Manager bearbeiten, wie in der folgenden Abbildung dargestellt. 

- Wählen Sie in Endpunkt-Manager unter Devicemanagement.Microsoft.com **Geräte > Windows > Konfigurationsprofile > "DFCI Profilname" > Eigenschaften > Einstellungen**aus.

    ![Konfigurieren von DFCI-Einstellungen](images/dfciconfig.png)

### Blockieren des Benutzerzugriffs auf UEFI-Einstellungen

Für viele Kunden ist es äußerst wichtig, dass Benutzer das Ändern von UEFI-Einstellungen blockieren, und ein Hauptgrund für die Verwendung von DFCI. Wie in Tabelle 1 zu finden ist, wird dies über die Einstellung " **lokale Benutzer können die UEFI-Einstellungen ändern**" verwaltet. Wenn Sie diese Einstellung nicht bearbeiten oder konfigurieren, können lokale Benutzer alle UEFI-Einstellungen ändern, die nicht von InTune verwaltet werden. Daher empfiehlt es sich dringend, die **UEFI-Einstellungen für lokale Benutzer zulassen zu deaktivieren.**
Mit den restlichen DFCI-Einstellungen können Sie die Funktionalität deaktivieren, die andernfalls für die Benutzer verfügbar wäre. Wenn Sie beispielsweise vertrauliche Informationen in sehr sicheren Bereichen schützen müssen, können Sie die Kamera deaktivieren, und wenn Sie nicht möchten, dass Benutzer von USB-Laufwerken Booten, können Sie diese Option auch deaktivieren.

### Tabelle1. DFCI-Szenarien

| Device Management-Ziel                        | Konfigurationsschritte                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Verhindern, dass lokale Benutzer die UEFI-Einstellungen ändern | Wählen Sie unter **Sicherheits Features > zulassen, dass die UEFI-Einstellungen für lokale Benutzer geändert**werden können die Option **keine**aus.              |
| Deaktivieren von Kameras                               | Wählen Sie unter **eingebaute Hardware > Kameras**die Option **deaktiviert**aus.                                       |
| Mikrofone und Lautsprecher deaktivieren              | Wählen Sie unter **eingebaute Hardware > Mikrofonen und Lautsprechern**die Option **deaktiviert**aus.                      |
| Radios deaktivieren (Bluetooth, Wi-Fi)             | Wählen Sie unter **eingebaute Hardware > Radios (Bluetooth, Wi-Fi usw.)** die Option **disabled**aus.                   |
| Deaktivieren des Starts von externen Medien (USB, SD)    | Wählen Sie unter **integrierte Hardware > Startoptionen > von externen Medien booten (USB, SD)** die Option **deaktiviert**aus. |

> [!CAUTION]
> Die Einstellung **Radios deaktivieren (Bluetooth, Wi-Fi)** sollte nur auf Geräten verwendet werden, die über eine kabelgebundene Ethernet-Verbindung verfügen.
 
> [!NOTE]
>  DFCI in InTune umfasst zwei Einstellungen, die derzeit nicht für Surface Devices gelten: (1) CPU-und IO-Virtualisierung und (2) Deaktivieren des Starts von Netzwerkadaptern.
 
InTune bietet Bereichs Tags zum Delegieren von Administratorrechten und Anwendungsregeln, um Gerätetypen zu verwalten. Weitere Informationen zur Unterstützung der Richtlinienverwaltung und vollständige Informationen zu allen DFCI-Einstellungen finden Sie in der [Microsoft InTune-Dokumentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).

## Registrieren von Geräten in Autopilot

Wie bereits erwähnt, kann DFCI nur auf Geräten angewendet werden, die von Ihrem Reseller oder Distributor in Windows Autopilot registriert sind und derzeit nur unter Surface pro 7, Surface pro X und Surface Laptop 3 unterstützt werden. Aus Sicherheitsgründen ist es nicht möglich, Ihre Geräte in Autopilot selbst bereitzustellen.

## Manuelles Synchronisieren von Autopilot-Geräten

Obwohl die Intune-Richtlinieneinstellungen normalerweise fast sofort angewendet werden, kann es eine Verzögerung von 10 Minuten geben, bevor die Einstellungen auf Zielgeräten wirksam werden. In seltenen Fällen sind Verzögerungen von bis zu 8 Stunden möglich. Um sicherzustellen, dass die Einstellungen so schnell wie möglich angewendet werden (beispielsweise in Testszenarien), können Sie die Zielgeräte manuell synchronisieren.

- Wechseln Sie in Endpoint Manager unter Devicemanagement.Microsoft.com zu **Geräte > Geräteregistrierung > Windows-Registrierung > Windows Autopilot-Geräten** , und wählen Sie **Synchronisieren**aus.

 Weitere Informationen finden Sie unter [Manuelles Synchronisieren Ihres Windows-Geräts](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

> [!NOTE]
> Wenn Sie die Einstellungen direkt in UEFI anpassen, müssen Sie sicherstellen, dass das Gerät vollständig in der Windows-Standardanmeldung neu gestartet wird.

## Überprüfen von UEFI-Einstellungen auf DFCI-verwalteten Geräten

In einer Testumgebung können Sie die Einstellungen in der Oberfläche UEFI-Schnittstelle überprüfen.

1. Öffnen Sie die Oberfläche UEFI, bei der gleichzeitig die **Lautstärke +** und die **Power** -Taste gedrückt werden.
2. Wählen Sie **Geräte**aus. Das UEFI-Menü spiegelt die konfigurierten Einstellungen wider, wie in der folgenden Abbildung zu sehen ist.

    ![DGM-UEFI](images/df3.png)

    Hinweis:

      - Die Einstellungen sind abgeblendet, da die **Einstellung lokaler Benutzer zum Ändern der UEFI-Einstellung zulassen** auf None festgelegt ist.
      - Audio ist auf "aus" eingestellt, da **Mikrofone und Lautsprecher** auf " **deaktiviert**" eingestellt sind.

## Entfernen von DFCI-Richtlinieneinstellungen

Wenn Sie ein DFCI-Profil erstellen, bleiben alle konfigurierten Einstellungen für alle Geräte innerhalb des Verwaltungsbereichs des Profils gültig. Sie können DFCI-Richtlinieneinstellungen nur entfernen, indem Sie das DFCI-Profil direkt bearbeiten.

Wenn das ursprüngliche DFCI-Profil gelöscht wurde, können Sie Richtlinieneinstellungen entfernen, indem Sie ein neues Profil erstellen und die Einstellungen nach Bedarf bearbeiten.

## Entfernen der DFCI-Verwaltung

**So entfernen Sie die DFCI-Verwaltung und geben das Gerät in den neuen Zustand der Factory zurück:**

1. Zurücksetzen des Geräts von InTune:
    1. Wählen Sie in Endpunkt-Manager bei Devicemanagement.Microsoft.com **die Option Gruppen > alle Geräte**aus. Wählen Sie die Geräte aus, die Sie zurückziehen möchten, und wählen Sie dann **zurückziehen/wischen aus.** Weitere Informationen finden Sie unter [Entfernen von Geräten mithilfe von wischen, zurückziehen oder manuelles Aufheben der Registrierung des Geräts](https://docs.microsoft.com/intune/remote-actions/devices-wipe). 
2. Löschen Sie die Autopilot-Registrierung von InTune:
    1.  Wählen Sie **Geräteregistrierung > Windows-Registrierungs > Geräten**aus.
    2. Wählen Sie unter Windows Autopilot Devices die Geräte aus, die Sie löschen möchten, und wählen Sie dann **Löschen**aus.
3. Verbinden Sie das Gerät mit dem kabelgebundenen Internet mit dem Surface-Branded-Ethernet-Adapter. Starten Sie das Gerät neu, und öffnen Sie das UEFI-Menü (halten Sie die Lautstärketaste gedrückt, während Sie auch die Power-Taste drücken und loslassen).
4. Wählen Sie **Verwaltung aus, > > Aktualisierung vom Netzwerk konfigurieren** , und wählen Sie dann **ablehnen aus.**

Wenn Sie das Gerät weiterhin mit InTune, aber ohne DFCI-Verwaltung verwalten möchten, registrieren Sie das Gerät automatisch für Autopilot, und registrieren Sie es für InTune. DFCI wird nicht auf selbstregistrierte Geräte angewendet.

## Mehr erfahren
- [Ignite 2019: Ankündigung der Remoteverwaltung von Oberflächen UEFI-Einstellungen aus InTune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot und Surface-Geräte](windows-autopilot-and-surface-devices.md) 
- [Verwenden von DFCI-Profilen auf Windows-Geräten in Microsoft InTune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
