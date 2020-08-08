---
title: SSD-Entfernung in kompatiblen Surface-Geräten
description: So übertragen Sie eine SSD von einem Surface-Gerät auf ein anderes.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918962"
---
# Bewährte Methoden für die SSD-Entfernung in kompatiblen Surface-Geräten

> [!IMPORTANT]
> Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen. In diesem Abschnitt werden die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beschrieben, wenn Sie SSDs auf Surface-Geräten mit wechselbaren SSDs entfernen und ersetzen. 

> [!WARNING]
> Durch das Öffnen von Geräten und das Ersetzen von Gerätekomponenten können elektrische Schocks, Geräteschäden, Brände sowie Risiken für Personenschäden und andere Gefahren auftreten.  Achten Sie bei derartigen Aktivitäten immer auf Vorsicht. Befolgen Sie die Sicherheitsvorkehrungen und Verfahren, die im rSSD-Entfernungs Leit Faden für Enterprise angegeben sind. Microsoft empfiehlt, dass Sie professionelle Unterstützung suchen, wenn Sie die im rSSD-Entfernungs Leit Faden für Enterprise angegebenen Sicherheitsvorkehrungen und Verfahren nicht befolgen können. 

## Voraussetzungen

> [!IMPORTANT]
> In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheits-und Sicherheitsrichtlinien und-Verfahren verstehen, die im [rSSD-Entfernungs Leit Faden für Unternehmen](https://www.microsoft.com/download/100440)beschrieben sind.

## Vorbereiten der SSD-Entfernung 

### Installieren der neuesten Updates 

Bevor Sie beginnen, stellen Sie sicher, dass Ihre Version von Windows über die neuesten Updates verfügt.

1.  Wechseln Sie zu **Start**  >  **Settings**  >  **Update & Security** , und wählen Sie auf **Updates überprüfen**aus. Installieren Sie alle verfügbaren Updates.  

2.  Vergewissern Sie sich, dass für den Zugriff auf das Gerät Kennwörter erforderlich sind.  
 
## Verwalten von BitLocker 

> [!NOTE]
> Dieser Abschnitt enthält Empfehlungen für Organisationen, die die BitLocker-Verschlüsselung für Festplatten aktiviert haben. Weitere Informationen finden Sie im [BitLocker-Wiederherstellungs Handbuch](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD deaktiviert ist

Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt sein kann, führen Sie die folgenden Schritte aus, um BitLocker zu deaktivieren:

1.  Geben **Settings**Sie in Einstellungen **BitLocker** ein, und wählen Sie **BitLocker verwalten**aus. 
2.  Wählen Sie **BitLocker deaktivieren**aus. 
3.  Schalten Sie das Gerät aus. 

### Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD aktiviert ist

Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker-Wiederherstellungsschlüssel zu generieren und ihn auf einem USB-Speicher zu speichern:

1.  Wechseln Sie zu **Einstellungen** , und geben Sie **BitLocker**ein.
2. Wählen Sie **BitLocker**  > -**Wiederherstellungsschlüssel generieren BitLocker**verwalten aus.
2.  Legen Sie ein USB-Laufwerk ein. 
3.  Speichern Sie den Wiederherstellungsschlüssel in einem USB-Speicher.  
4.  Entfernen Sie das USB-Laufwerk.  
5.  Schalten Sie das Gerät aus. 

## Entfernen und Ersetzen der SSD 

1.  Entfernen Sie die SSD mithilfe der Anweisungen im [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440). 
2. Legen Sie die ursprüngliche SSD auf einem neuen Gerät ab, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.
2.  Schalten Sie das neue Gerät ein. Das Gerät kann während des Starts eine Firmware-Aktualisierung durchlaufen.  
 
## Nach dem Entfernen und Ersetzen von SSD

### Verwalten von unverschlüsselten SSDs 

Wenn die SSD während der Übertragung unverschlüsselt bleibt, führen Sie die folgenden Schritte aus: 

1.  Wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (als Schlüsselsymbol auf der linken Seite dargestellt).  
2.  Geben Sie das Kennwort ein, und melden Sie sich bis zum Abschluss der zweistufigen Authentifizierung an (falls zutreffend).
3.  Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zum Konto **Start**  >  **Account**  >  **Abmelden**.  
4.  Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden. 
    - Wenn das Gerät BitLocker-deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Ersatz aktivieren möchten, wechseln Sie zu **BitLocker**BitLocker-BitLocker-  >  **Manage Bitlocker**  >  **Lebenslauf**BitLocker.  
6.  Führen **Sie** "mit", um die vollständige Gerätefunktionalität zu bestätigen.  
7.  Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.  Wenn Fehlermeldungen auftreten, wählen Sie **Problembehandlung**aus. 
8.  Überprüfen Sie das Office-Konto, indem Sie die **Office-App**öffnen, dann zu **Datei**  >  **Konto** navigieren und auf Fehlermeldungen überprüfen.  

### Verwalten von verschlüsselten SSDs 

> [!NOTE]
> Sie benötigen ein zweites Gerät zum Lesen des BitLocker-Wiederherstellungsschlüssels, der auf dem USB-Laufwerk gespeichert wurde. 

Wenn die SSD während der Übertragung verschlüsselt blieb, führen Sie die folgenden Schritte aus:

1.  Legen Sie das USB-Laufwerk mit dem BitLocker-Wiederherstellungsschlüssel in das zweite Gerät ein. 
2.  Öffnen Sie die txt-Datei, die den BitLocker-Wiederherstellungsschlüssel enthält. 
3.  Geben Sie den BitLocker-Wiederherstellungsschlüssel manuell in das neue Gerät ein, das die ursprüngliche SSD enthält.  
4.  Nachdem Sie den BitLocker-Wiederherstellungsschlüssel erfolgreich eingegeben haben, wechseln Sie zum **Anmeldeoptionen-**  >  **Kennwort** (dargestellt durch das Schlüsselsymbol auf der linken Seite).  
5.  Geben Sie das Kennwort ein, und melden Sie sich an, bis zum Abschluss der zweistufigen Authentifizierung (falls zutreffend). 
6.  Nachdem Sie sich vollständig angemeldet haben, wechseln Sie zum Konto **Start**  >  **Account**  >  **Abmelden**.  
7.  Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello ein, und fügen Sie eine PIN hinzu. 
8.  Wenn das Gerät BitLocker-deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Ersatz aktivieren möchten, wechseln Sie zu **Einstellungen**BitLocker-BitLocker-BitLocker-  >  **Bitlocker**  >  **Manage Bitlocker**  >  **Lebenslauf**-BitLocker.  
9.  Führen **Sie** "mit", um die vollständige Gerätefunktionalität zu bestätigen.  
10. Überprüfen Sie die Windows-Aktivierung, indem Sie zur Aktivierung der **Einstellungen**navigieren  >  **Activation**.  Wenn Fehlermeldungen auftreten, wählen Sie **Problembehandlung**aus.
11. Um das Office-Konto zu überprüfen, öffnen Sie die **Office-App**, wechseln Sie dann zu **Datei**  >  **Konto** , und überprüfen Sie, ob Fehlermeldungen vorhanden sind.

## Weitere Informationen 

Weitere Informationen finden Sie in den folgenden Artikeln:

- [rSSD-Entfernungs Leit Faden für Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker-Wiederherstellungsleitfaden](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Benötigen Sie weitere Hilfe? Wechseln Sie zu [Microsoft Community](https://answers.microsoft.com/).