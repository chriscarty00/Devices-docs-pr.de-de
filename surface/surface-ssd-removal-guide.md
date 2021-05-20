---
title: Entfernen von SSD auf kompatiblen Surface-Geräten
description: In diesem Artikel für qualifizierte IT-Techniker werden die empfohlenen bewährten Methoden für das Entfernen und Ersetzen von SSDs in Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X und Surface Laptop Go beschrieben.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576905"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>Bewährte Methoden für das Entfernen von SSD von kompatiblen Surface-Geräten

> [!IMPORTANT]
> Dieser Artikel ist nur für die Verwendung durch qualifizierte IT-Techniker in einer Unternehmensorganisation vorgesehen. Es werden die empfohlenen bewährten Methoden für die Verwendung durch qualifizierte IT-Techniker beim Entfernen und Ersetzen von SSDs auf den folgenden kompatiblen Surface-Geräten beschrieben: 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> Das Öffnen von Geräten und das Ersetzen von Gerätekomponenten kann zu Elektrischen Schlägen, Geräteschäden, Brand- und Verletzungsrisiken und anderen Gefahren führen.  Verwenden Sie immer Vorsicht, wenn Sie solche Aktivitäten unternehmen. Befolgen Sie die Sicherheitsvorkehrungen und -verfahren, die im [rSSD Removal Guide für](https://www.microsoft.com/download/100440)Enterprise. Es wird empfohlen, professionelle Unterstützung zu erhalten, wenn Sie die im "rSSD Removal Guide for Enterprise" angegebenen Sicherheitsvorkehrungen und Verfahren nicht befolgen Enterprise.

## <a name="prerequisites"></a>Voraussetzungen

> [!IMPORTANT]
> In diesem Artikel wird davon ausgegangen, dass Sie die allgemeinen Sicherheits- und Sicherheitsrichtlinien und -verfahren verstehen, die im "rSSD Removal Guide for Enterprise" beschrieben werden.

## <a name="prepare-for-ssd-removal"></a>Vorbereiten der SSD-Entfernung 

### <a name="install-the-latest-updates"></a>Installieren der neuesten Updates 

Bevor Sie beginnen, stellen Sie sicher, dass Windows die neuesten Updates installiert sind:

1.  Wechseln Sie **zu Start**  >  **Einstellungen**  >  **Update & Security**, und wählen Sie Nach Updates suchen **aus.**
2. Installieren Sie alle verfügbaren Updates.
3. Überprüfen Sie alle Kennwörter, die für den Zugriff auf das Gerät erforderlich sind.  
 
## <a name="manage-bitlocker"></a>„BitLocker verwalten“ 

> [!NOTE]
> Dieser Abschnitt enthält Empfehlungen für Organisationen, die BitLocker für Festplatten aktiviert haben. Weitere Informationen finden Sie unter [BitLocker Wiederherstellungshandbuch](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>Wenn BitLocker während des Entfernens und Ersetzens von SSD deaktiviert ist

Wenn das Gerät vor dem Entfernen und Ersetzen von SSD unverschlüsselt sein kann, führen Sie die folgenden Schritte aus, um die BitLocker:

1.  Geben **Einstellungen**in **BitLocker** ein, und wählen Sie dann Verwalten **BitLocker**aus. 
2.  Wählen **Sie Deaktivieren BitLocker**aus. 
3.  Schalten Sie das Gerät herunter. 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>Wenn BitLocker während des Entfernens und Ersetzens von SSD aktiviert ist

Wenn das Gerät vor dem Entfernen und Ersetzen von SSD verschlüsselt ist, führen Sie die folgenden Schritte aus, um einen BitLocker zu generieren und im USB-Speicher zu speichern:

1.  Geben **Einstellungen**geben Sie **BitLocker ein.**
2. Wählen **Sie Manage BitLocker**Generate BitLocker Recovery Key  > **aus.**
2.  Fügen Sie ein USB-Laufwerk ein. 
4.  Speichern Sie den Wiederherstellungsschlüssel im USB-Speicher.  
5.  Entfernen Sie das USB-Laufwerk.  
6.  Schalten Sie das Gerät herunter. 

## <a name="remove-and-replace-ssd"></a>Entfernen und Ersetzen von SSD 

1.  Entfernen Sie die SSD mithilfe der entsprechenden Anweisungen für Ihr Gerät, die in [rSSD Removal Guide for Enterprise.](https://www.microsoft.com/download/100440) 
2.  Legen Sie die ursprüngliche SSD in ein neues Gerät ein, und verbinden Sie das neue Gerät mit einer kabelgebundenen Internetverbindung.
3.  Schalten Sie das neue Gerät ein. Das Gerät kann während des Startvorgangs ein Firmwareupdate durchgehen.  
 
## <a name="after-ssd-removal-and-replacement"></a>Nach dem Entfernen und Ersetzen von SSD

### <a name="manage-unencrypted-ssds"></a>Verwalten unverschlüsselter SSDs 

Wenn die SSD während der Übertragung unverschlüsselt ist, führen Sie die folgenden Schritte aus: 

1.  Wechseln Sie **zu Anmeldeoptionen**  >  **Kennwort** (dargestellt durch das Tastensymbol auf der linken Seite).  
2.  Geben Sie das Kennwort ein, und melden Sie sich bis zum Abschluss der zweistufigen Authentifizierung an (sofern zutreffend).
3.  Wechseln Sie nach der vollständigen Anmeldung zu **Konto**  >  **abmelden**  >  **starten.**  
4.  Melden Sie sich mit dem Kennwort wieder an, und richten Sie Windows Hello und eine PIN ein, wenn Sie dazu aufgefordert werden. 
    - Wenn das Gerät BitLocker deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu erleichtern, und Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **BitLocker**Verwalten BitLocker  >  ****  >  **Fortsetzen BitLocker**.  
6.  Führen Sie [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) aus, um die vollständige Gerätefunktionalität zu überprüfen.  
7.  Überprüfen Sie Windows Aktivierung, indem Sie zu **Einstellungen**  >  **navigieren.**  Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.** 
8.  Überprüfen Sie das Office, indem Sie **die Office-App**öffnen, zu Dateikonto navigieren und dann ****  >  **** nach Fehlermeldungen suchen.  

### <a name="managing-encrypted-ssds"></a>Verwalten verschlüsselter SSDs 

> [!NOTE]
> Sie müssen über ein zweites Gerät verfügen, um den BitLocker wiederherstellungsschlüssel zu lesen, der auf dem USB-Laufwerk gespeichert wurde. 

Wenn die SSD während der Übertragung verschlüsselt ist, führen Sie die folgenden Schritte aus:

1.  Fügen Sie das USB-Laufwerk, das den BitLocker wiederherstellungsschlüssel enthält, in das zweite Gerät ein. 
2.  Öffnen Sie .txt Datei, die den Bitlocker-Wiederherstellungsschlüssel enthält. 
3.  Geben Sie manuell BitLocker wiederherstellungsschlüssel auf dem neuen Gerät ein, das die ursprüngliche SSD enthält.  
4.  Nachdem Sie den Wiederherstellungsschlüssel BitLocker eingegeben haben, wechseln Sie zu **Kennwort**für Anmeldeoptionen (dargestellt durch das Tastensymbol  >  **** auf der linken Seite).  
5.  Geben Sie das Kennwort ein, und melden Sie sich an, bis die zweistufige Authentifizierung abgeschlossen ist (sofern zutreffend).
6.  Wechseln Sie nach der vollständigen Anmeldung zu **Konto**  >  **abmelden**  >  **starten.**  
7.  Melden Sie sich mit dem Kennwort wieder an, und richten Sie dann Windows Hello ein, und fügen Sie eine PIN hinzu. 
8.  Wenn das Gerät BitLocker deaktiviert wurde, um das Entfernen und Ersetzen von SSD zu erleichtern, und wenn Sie BitLocker nach dem Austausch aktivieren möchten, wechseln Sie zu **Einstellungen**  >  **BitLocker**  >  **Verwalten**BitLocker  >  **Fortsetzen BitLocker**.  
9.  Führen **[Sie SDT aus,](surface-diagnostic-toolkit-for-business-intro.md)** um die vollständige Gerätefunktionalität zu überprüfen.  
10. Um die Windows zu überprüfen, wählen Sie **Einstellungen**  >  **Aktivierung aus.**  Wenn Fehlermeldungen angezeigt werden, wählen Sie **Problembehandlung aus.**
11. Um den Status des Office zu überprüfen, öffnen Sie die **Office-App,** und wechseln Sie dann zu Dateikonto, um nach ****  >  **** Fehlermeldungen zu suchen.

## <a name="learn-more"></a>Mehr erfahren

- [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker-Wiederherstellungsleitfaden](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Benötigen Sie weitere Hilfe? Wechseln Sie [zu Microsoft Community](https://answers.microsoft.com/).