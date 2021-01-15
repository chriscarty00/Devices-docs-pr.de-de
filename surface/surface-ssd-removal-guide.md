---
title: Entfernen von SSD auf kompatiblen Surface-Geräten
description: Dieser Artikel richtet sich an qualifizierte IT-Techniker und beschreibt die empfohlenen bewährten Methoden zum Entfernen und Ersetzen von SSDs in Surface Laptop 3, Surface Pro X und Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270630"
---
# Bewährte Methoden für das Entfernen von SSD von kompatiblen Surface-Geräten

> [!IMPORTANT]
> Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen. Es beschreibt die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beim Entfernen und Ersetzen von SSDs auf den folgenden kompatiblen Surface-Geräten: 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3

> [!WARNING]
> Das Öffnen von Geräten und das Ersetzen von Gerätekomponenten kann stromauflösend, Geräteschäden, Löschrisiken und persönliche Schäden sowie andere Gefahren darstellen.  Verwenden Sie bei solchen Aktivitäten stets Vorsicht. Befolgen Sie die Sicherheitsvorkehrungen und -verfahren, die im [rSSD Removal Guide for Enterprise identifiziert sind.](https://www.microsoft.com/download/100440) Es wird empfohlen, professionelle Unterstützung zu erhalten, wenn Sie die im "rSSD Removal Guide for Enterprise" angegebenen Sicherheitsvorkehrungen und Verfahren nicht befolgen können.

## Voraussetzungen

> [!IMPORTANT]
> In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheitsvorkehrungen und Sicherheitsrichtlinien und -verfahren verstehen, die im "rSSD Removal Guide for Enterprise" beschrieben sind.

## Vorbereiten der Entfernung von SSD 

### Installieren der neuesten Updates 

Bevor Sie beginnen, stellen Sie sicher, dass in Ihrer Version von Windows die neuesten Updates installiert sind:

1.  Go to **Start**  >  **Settings**  >  **Update & Security,** and select **Check for updates**.
2. Installieren Sie alle verfügbaren Updates.
3. Überprüfen Sie alle Kennwörter, die für den Zugriff auf das Gerät erforderlich sind.  
 
## „BitLocker verwalten“ 

> [!NOTE]
> Dieser Abschnitt enthält Empfehlungen für Organisationen, die die BitLocker-Verschlüsselung für Festplatten aktiviert haben. Weitere Informationen finden Sie im [BitLocker-Wiederherstellungshandbuch.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD deaktiviert ist

Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt werden kann, führen Sie die folgenden Schritte aus, um BitLocker zu deaktivieren:

1.  Geben **Sie in**den Einstellungen **BitLocker ein,** und wählen Sie dann **"BitLocker verwalten" aus.** 
2.  Wählen **Sie BitLocker deaktivieren aus.** 
3.  Schalten Sie das Gerät herunter. 

### Wenn die BitLocker-Verschlüsselung während des Entfernens und Ersetzens von SSD aktiviert ist

Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker-Wiederherstellungsschlüssel zu generieren und ihn im USB-Speicher zu speichern:

1.  Geben **Sie in**den Einstellungen **BitLocker ein.**
2. Wählen **Sie "BitLocker**  > **verwalten" aus, um den BitLocker-Wiederherstellungsschlüssel zu generieren.**
2.  Fügen Sie ein USB-Laufwerk ein. 
4.  Speichern Sie den Wiederherstellungsschlüssel im USB-Speicher.  
5.  Entfernen Sie das USB-Laufwerk.  
6.  Schalten Sie das Gerät herunter. 

## Entfernen und Ersetzen von SSD 

1.  Entfernen Sie das SSD mithilfe der entsprechenden Anweisungen für Ihr Gerät, das im [rSSD Removal Guide for Enterprise enthalten ist.](https://www.microsoft.com/download/100440) 
2.  Stellen Sie das ursprüngliche SSD in ein neues Gerät ein, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.
3.  Schalten Sie das neue Gerät ein. Das Gerät kann während des Starts ein Firmwareupdate durchgehen.  
 
## Nach dem Entfernen und Ersetzen von SSD

### Verwalten unverschlüsselter SSDs 

Wenn das SSD während der Übertragung unverschlüsselt ist, führen Sie die folgenden Schritte aus: 

1.  Wechseln Sie **zu "Kennwort für Anmeldeoptionen"**  >  **** (dargestellt durch das Schlüsselsymbol auf der linken Seite).  
2.  Geben Sie das Kennwort ein, und melden Sie sich an, bis die zweistufige Authentifizierung abgeschlossen ist (falls zutreffend).
3.  Nachdem Sie vollständig angemeldet sind, wechseln Sie zu **"Konto**  >  ****  >  **abmelden starten".**  
4.  Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden. 
    - Wenn das Gerät bitLocker-deaktiviert war, um das Entfernen und Ersetzen von SSD zu vereinfachen, und Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **BitLocker**  >  **Verwalten BitLocker**  >  **Fortsetzen BitLocker**.  
6.  Führen Sie [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) aus, um die vollständige Gerätefunktionalität zu überprüfen.  
7.  Suchen Sie nach der Windows-Aktivierung, indem Sie zur **Einstellungsaktivierung**  >  **navigieren.**  Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.** 
8.  Überprüfen Sie das Office-Konto, indem Sie die **Office-App**öffnen, zu **"Dateikonto"** navigieren und dann nach  >  **** Fehlermeldungen suchen.  

### Verwalten verschlüsselter SSDs 

> [!NOTE]
> Sie müssen über ein zweites Gerät verfügen, um den BitLocker-Wiederherstellungsschlüssel zu lesen, der auf dem USB-Laufwerk gespeichert wurde. 

Wenn das SSD während der Übertragung verschlüsselt ist, führen Sie die folgenden Schritte aus:

1.  Fügen Sie das USB-Laufwerk, das den BitLocker-Wiederherstellungsschlüssel enthält, in das zweite Gerät ein. 
2.  Öffnen Sie die TXT-Datei, die den Bitlocker-Wiederherstellungsschlüssel enthält. 
3.  Geben Sie den BitLocker-Wiederherstellungsschlüssel manuell auf dem neuen Gerät ein, das das ursprüngliche SSD enthält.  
4.  Nachdem Sie den BitLocker-Wiederherstellungsschlüssel erfolgreich eingegeben haben, wechseln Sie zu **"Kennwort**für Anmeldeoptionen" (dargestellt durch das Schlüsselsymbol  >  **** auf der linken Seite).  
5.  Geben Sie das Kennwort ein, und melden Sie sich an, bis die zweistufige Authentifizierung abgeschlossen ist (falls zutreffend).
6.  Nachdem Sie vollständig angemeldet sind, wechseln Sie zu **"Konto**  >  ****  >  **abmelden starten".**  
7.  Melden Sie sich mit dem Kennwort wieder an, richten Sie Windows Hello ein, und fügen Sie eine PIN hinzu. 
8.  If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings**  >  **BitLocker**  >  **Manage BitLocker**Resume  >  **BitLocker**.  
9.  Führen Sie **[SDT aus,](surface-diagnostic-toolkit-for-business-intro.md)** um die vollständige Gerätefunktionalität zu überprüfen.  
10. Um die Aktivierung von Windows zu überprüfen, wählen **Sie "Einstellungsaktivierung"**  >  **aus.**  Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.**
11. Um den Status des Office-Kontos zu überprüfen, **** öffnen Sie die **Office-App,** und wechseln Sie dann zu "Dateikonto", um nach  >  **** Fehlermeldungen zu suchen.

## Mehr erfahren

- [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker-Wiederherstellungsleitfaden](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Benötigen Sie weitere Hilfe? Wechseln Sie zur [Microsoft Community](https://answers.microsoft.com/).