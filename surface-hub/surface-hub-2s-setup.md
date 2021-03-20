---
title: Erstes Setup für Surface Hub 2S
description: Erfahren Sie, wie Sie das Setup für Surface Hub 2S zum ersten Mal abschließen.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442193"
---
# <a name="first-time-setup-for-surface-hub-2s"></a>Erstes Setup für Surface Hub 2S

Wenn Sie Surface Hub 2S zum ersten Mal starten, wechselt das Gerät automatisch in den ersten Setupmodus, um Sie durch die Kontokonfiguration und die zugehörigen Einstellungen zu führen.

## <a name="configuring-surface-hub-2s-account"></a>Konfigurieren des Surface Hub 2S-Kontos

1. **Konfigurieren Sie Ihr Locale.** Geben Sie Informationen zu Region, Sprache, Tastaturlayout und Zeitzone ein. Wählen Sie **Weiter** aus.

   ![* Konfigurieren Des Locale *](images/sh2-run1.png)

1. **Stellen Sie eine Verbindung mit einem Drahtlosnetzwerk herzustellen.** Wählen Sie Ihr bevorzugtes Drahtlosnetzwerk aus, und wählen Sie **Weiter aus.**

   - Diese Option wird nicht angezeigt, wenn sie über ein Ethernetkabel verbunden ist.

   - Sie können keine Verbindung mit einem Drahtlosnetzwerk in Hotspots (Unternehmensportale) herstellen, die Anmeldeanforderungen an die Website eines Anbieters umleiten.

3. **Geben Sie Gerätekontoinformationen ein.** Verwenden **Sie Domäne\Benutzer** für lokale und Hybridumgebungen und **benutzer\@example.com** für Onlineumgebungen. Wählen Sie **Weiter aus.**

   ![* Geben Sie Gerätekontoinformationen * ein.](images/sh2-run2.png)

1. **Geben Sie weitere Informationen ein.** Geben Sie auf Wunsch Ihre Exchange-Serveradresse an, und wählen Sie dann **Weiter aus.**

   ![* Geben Sie weitere Informationen ein; Beispiel: Exchange-Servername*](images/sh2-run3.png)

1. **Nennen Sie dieses Gerät.** Geben Sie einen Namen für Ihr Gerät ein, oder verwenden Sie den vorgeschlagenen Namen basierend auf dem Anzeigenamen ihres Kontos und dem Benutzernamen des Benutzerprinzips [UPN]. **Wählen Sie Weiter**aus.

   - Der **Anzeigename** wird in der unteren linken Ecke von Surface Hub 2S angezeigt und beim Projiziert auf das Gerät angezeigt.

   - Der **Gerätename** identifiziert das Gerät, wenn es mit Active Directory oder Azure Active Directory verbunden ist, und beim Registrieren des Geräts bei Intune.

   ![* Nennen Sie dieses Gerät*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a>Konfigurieren von Geräteadministratorkonten

Sie können Geräteadministratoren nur beim ersten Setup einrichten. Weitere Informationen finden Sie unter [Surface Hub 2S device affiliation](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation).

Wählen Sie **im Fenster Setupadministratoren** für dieses Gerät eine der folgenden Optionen aus: Active Directory-Domänendienste, Azure Active Directory oder Lokaler Administrator.

![* Setupadministratoren für dieses Gerät *](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Geben Sie die Anmeldeinformationen eines Benutzers ein, der über Berechtigungen zum Beitreten des Geräts zu Active Directory verfügt.

    ![* Setupadministratoren mit Domänen beitreten *](images/sh2-run6.png)

2. Wählen Sie die Active Directory-Sicherheitsgruppe aus, die Mitglieder enthält, die sich bei der App "Einstellungen" auf Surface Hub 2S anmelden dürfen.

   ![* Geben Sie eine Sicherheitsgruppe ein *](images/sh2-run7.png)

1. Wählen Sie **Fertig stellen**aus. Das Gerät wird neu gestartet.

### <a name="azure-active-directory"></a>Azure Active Directory

Wenn Sie Ihr Gerät azure Active Directory 2013 nennen, wird das Gerät sofort neu gestartet und die folgende Seite angezeigt.

![* Wenn Ihre Organisation Office 365 oder andere Geschäftsdienste von Microsoft verwendet, registrieren wir dieses Gerät bei Ihrer Organisation*](images/sh2-run8.png)

1. Wählen Sie **Weiter** aus.

1. Geben Sie die E-Mail-Adresse oder den UPN eines Kontos mit **Intune Plan 1** oder höher ein, und wählen Sie dann **Weiter aus.**

   ![* Eingeben eines Arbeits- oder Schulkontos*](images/sh2-run9.png)

1. Wenn Sie umgeleitet werden, authentifizieren Sie sich über die Anmeldeseite Ihrer Organisation, und stellen Sie auf Anfrage zusätzliche Anmeldeinformationen zur Verfügung. Das Gerät wird neu gestartet.

## <a name="local-administrator-account"></a>Lokales Administratorkonto

- Geben Sie einen Benutzernamen und ein Kennwort für Ihren lokalen Administrator ein. Das Gerät wird neu gestartet.

  ![* Einrichten eines Administratorkontos*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a>Verwenden von Bereitstellungspaketen

Wenn Sie beim Starten von Surface Hub 2S ein USB-Stick mit einem Bereitstellungspaket in einen der USB-Ports einfügen, zeigt das Gerät die folgende Seite an.

1. Geben Sie die angeforderten Einstellungen ein, und wählen **Sie Einrichten aus.**

   ![* Geben Sie regionale Einstellungen für das Bereitstellungspaket ein*](images/sh2-run11.png)

   ![* Bereitstellen dieses Geräts von Wechselmedien*](images/sh2-run12.png)

2. Wählen Sie das Bereitstellungspaket aus, das Sie verwenden möchten.

   ![* Wählen Sie das zu verwendende Bereitstellungspaket aus*](images/sh2-run13.png)

3. Wenn Sie eine CSV-Datei mit mehreren Geräten erstellt haben, können Sie eine Gerätekonfiguration auswählen. Weitere Informationen finden Sie unter [Erstellen von Bereitstellungspaketen für Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).

   ![* Wählen Sie ein Gerätekonto und einen Anzeigenamen aus Ihrer Konfigurationsdatei* aus.](images/sh2-run14.png)

4. Befolgen Sie die Anweisungen, um das Setup zum ersten Mal abzuschließen.
