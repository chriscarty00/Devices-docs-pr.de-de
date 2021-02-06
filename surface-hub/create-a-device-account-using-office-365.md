---
title: Erstellen eines Gerätekontos mithilfe der Benutzeroberfläche (Surface Hub v1)
description: Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Gerätekonto für Microsoft Surface Hub entweder mit der Office 365-UI oder mit dem Exchange Admin Center erstellen.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: Erstellen eines Gerätekontos, Office 365 UI, Exchange Admin Center, Microsoft 365 Admin Center, Skype for Business, Postfachrichtlinie für mobile Geräte
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: 9e6d72dc2b36bb149ee09c2edab885c80e60ac14
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314468"
---
# Erstellen eines Gerätekontos mithilfe der Benutzeroberfläche (Surface Hub v1)

 > [!NOTE]
 >Diese Seite enthält Informationen zum ursprünglichen Surface Hub (v1). Informationen zu Surface Hub 2S finden Sie unter [Erstellen des Surface Hub 2S-Gerätekontos.](surface-hub-2s-account.md)

Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Gerätekonto für Microsoft Surface Hub entweder mit der [Office 365-UI](#create-device-acct-o365) oder mit dem [Exchange Admin Center](#create-device-acct-eac) erstellen.

## <a href="" id="create-device-acct-o365"></a>Erstellen eines Gerätekontos mithilfe von Office 365


1.  [Erstellen Sie das Konto im Microsoft 365 Admin Center.](#create-device-acct-o365-admin-ctr)
2.  [Erstellen einer Postfachrichtlinie für mobile Geräte (ActiveSync) über das Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy)
3.  [Abschließen der Gerätekontoerstellung mit PowerShell](#create-device-acct-o365-complete-acct)
4.  [Konfigurieren der Exchange-Eigenschaften des Kontos mit PowerShell](#create-device-acct-o365-configure-exch-prop)
5.  [Aktivieren des Kontos mit Skype for Business](#create-device-acct-o365-skype-for-business)

### <a href="" id="create-device-acct-o365-admin-ctr"></a>Erstellen des Kontos im Admin Center

1.  Melden Sie sich bei Office 365 an, indem Sie https://portal.office.com
2.  Geben Sie die Administratoranmeldeinformationen für den Office 365-Mandanten an. Dadurch werden Sie zu Ihrem Microsoft 365 Admin Center iert.

    ![Microsoft 365 Admin Center.](images/setupdeviceaccto365-02.png)

3. Navigieren Sie im Admin **** Center im linken Bereich zu "Ressourcen", und klicken Sie dann auf "Räume" **& Gerät**.

    ![Räume & Geräteoption im Admin Center](images/room-equipment.png)

4. Klicken Sie auf **Hinzufügen**, um ein neues Raumkonto zu erstellen. Geben Sie einen Anzeigenamen und eine E-Mail-Adresse für das Konto ein, und klicken Sie dann auf **Hinzufügen**.

    ![Erstellen eines neuen Raumkontofensters](images/room-add.png)

5. Wählen Sie das Raumkonto, das Sie gerade erstellt haben, aus der Liste Aktive Benutzer aus. Im rechten Bereich werden die Kontoeigenschaften und mehrere optionale Aktionen angezeigt. Klicken Sie auf **Kennwort zurücksetzen**, um das Kennwort zu ändern, und heben Sie die Auswahl von **Diesen Benutzer bei der ersten Anmeldung sein Kennwort ändern lassen** auf, da es nicht möglich ist, beim Surface Hub-Anmeldeprozesses das Kennwort zu ändern.

6. Klicken Sie für den Abschnitt **Zugewiesene Lizenz** auf **Bearbeiten**, und klicken Sie dann auf den Dropdownpfeil neben der Lizenz, um die Details zu erweitern. Wählen Sie einen Speicherort für den Benutzer aus, und aktivieren Sie in der Liste der Lizenzen auf **Skype for Business Online (Plan 2)**, und klicken Sie dann auf **Speichern**. Die Lizenz kann abhängig von Ihrer Organisation variieren. (Beispielsweise kann Plan2 oder Plan3 angezeigt werden.)

### <a href="" id="create-device-acct-o365-mbx-policy"></a>Erstellen einer Postfachrichtlinie für mobile Geräte (ActiveSync) über das Exchange Admin Center

1.  Klicken Sie im linken Bereich des Admin Centers auf **ADMIN**, und klicken Sie dann auf **Exchange**.

    ![Admin Center mit aktiven Exchange-Benutzern.](images/setupdeviceaccto365-08.png)

2.  Dadurch wird eine weitere Registerkarte in Ihrem Browser geöffnet, über die Sie zum Exchange Admin Center gelangen, wo Sie die Postfacheinstellung für Surface Hub erstellen und festlegen können.

    ![Exchange Admin Center](images/setupdeviceaccto365-09.png)

3.  Zum Erstellen einer Postfachrichtlinie für mobile Geräte klicken Sie im linken Bereich auf **Mobil** und dann auf **Postfachrichtlinien für mobile Geräte**. Surface Hubs erfordern ein Konto mit einer Postfachrichtlinie für mobile Geräte, die kein Kennwort erfordert. Wenn Sie bereits über eine vorhandene Richtlinie verfügen, die dieser Anforderung entspricht, können Sie diese Richtlinie auf das Konto anwenden. Führen Sie andernfalls die folgenden Schritte aus, um eine neue Richtlinie zu erstellen, die nur für Surface Hub-Gerätekonten verwendet wird.

    ![Exchange Admin Center – Erstellen einer Postfachrichtlinie für mobile Geräte](images/setupdeviceaccto365-10.png)

4.  Zum Erstellen einer neuen Postfachrichtlinie für mobile Geräte für Surface Hub klicken Sie in den Steuerelementen oberhalb der Liste der Richtlinien auf die Schaltfläche **+** , um eine neue Richtlinie hinzuzufügen. Geben Sie als Namen einen Namen an, mit dem Sie diese Richtlinie von anderen Gerätekonten unterscheiden können (z. B. *SurfaceHubDeviceMobilePolicy*). Stellen Sie sicher, dass die Richtlinie kein Kennwort für die zugewiesenen Geräte erfordert. Überprüfen Sie daher, dass **Kennwort anfordern** deaktiviert bleibt, und klicken Sie dann auf **Speichern**.

    ![Abbildung der neuen Richtlinie für mobile Geräte](images/setupdeviceaccto365-11.png)

5.  Nachdem Sie die neue Postfachrichtlinie für mobile Geräte erstellt haben, wechseln Sie zurück zum **Exchange Admin Center**. Dort wird die neue Richtlinie angezeigt.

    ![Bild mit der neuen Postfachrichtlinie für mobile Geräte im Exchange Admin Center](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>Abschließen der Gerätekontoerstellung mit PowerShell

Ab hier müssen Sie den Vorgang zur Kontoerstellung mithilfe von PowerShell abschließen, um Konfigurationen einzurichten.

Um von diesen PowerShell-Skripts verwendete Cmdlets auszuführen, muss Folgendes für die PowerShell-Verwaltungskonsole installiert werden:

-   [Microsoft Online Services Sign-In Assistent für IT-Experten RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [Windows Azure Active Directory-Modul für Windows PowerShell](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [Skype for Business Online, Windows PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)

Installieren des folgenden Moduls in Powershell
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### Herstellen einer Verbindung mit Onlinediensten

1.  Führen Sie Windows PowerShell als Administrator aus.

    ![Abbildung zur Verdeutlichung, wie Sie Windows PowerShell starten und als Administrator ausführen](images/setupdeviceaccto365-17.png)

2.  Erstellen Sie ein Anmeldeinformationsobjekt, erstellen Sie dann eine neue Sitzung, die eine Verbindung mit Skype for Business Online herstellt, geben Sie das globale Mandantenadministratorkonto an, und klicken Sie dann auf **OK**.

    ![Bild für Anforderung für Windows PowerShell-Anmeldeinformationen](images/setupdeviceaccto365-18.png)

3.  Führen Sie zur Herstellung einer Verbindung mit Microsoft Online Services Folgendes aus:

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-19.png)

4.  Führen Sie nun zur Herstellung einer Verbindung mit Skype for Business Online-Diensten Folgendes aus:

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-20.png)

5.  Führen Sie zum Schluss zur Herstellung einer Verbindung mit Exchange Online-Diensten Folgendes aus:

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-21.png)

6.  Sie müssen nun die gerade erstellte Skype for Business Online-Sitzung und Exchange Online-Sitzung importieren, wodurch die Exchange- und Skype-Befehle importiert werden, sodass Sie diese lokal verwenden können.

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    Beachten Sie, dass dies einige Zeit dauern kann.

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-22.png)

7.  Wenn Sie mit den Onlinediensten verbunden sind, müssen Sie weitere Cmdlets ausführen, um dieses Kontos als Surface Hub-Gerätekonto zu konfigurieren.

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>Konfigurieren der Exchange-Eigenschaften des Kontos mit PowerShell

Nachdem Sie mit den Onlinediensten verbunden sind, können Sie die Einrichtung des Gerätekontos abschließen. Sie verwenden die E-Mail-Adresse des Gerätekontos für folgende Aufgaben:

-   Ändern des Postfachtyps von „regulär“ in „Raum“
-   Festlegen des Kennworts und Aktivieren des Raumpostfachkontos
-   Ändern verschiedener Exchange-Eigenschaften
-   Festlegen des Kennworts des Benutzerkontos auf „Läuft nie ab“.

1.  Sie müssen die E-Mail-Adresse des Kontos eingeben und eine Variable mit diesem Wert erstellen:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Rufen Sie den Wert zum Speichern aus dem Postfach ab:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Drucken Sie den Wert:

    ```powershell
    $strEmail
    ```

    Die richtige E-Mail-Adresse wird angezeigt.

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-23.png)

2. Führen Sie das folgende Cmdlet aus:

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern. Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Abbildung des PowerShell-Cmdlets](images/setupdeviceaccto365-26.png)

5.  Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>Aktivieren des Kontos mit Skype for Business

Aktivieren Sie das Gerätekonto mit Skype for Business.

Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende Voraussetzungen erfüllen:

-   Sie benötigen Skype for Business Online Eigenständig Plan 2 oder höher in Ihrem O365-Plan. Der Plan muss Konferenzfunktionen unterstützen.
-   Wenn Sie eine Enterprise-VoIP (PSTN-Telefonie) mithilfe von Telefoniedienstanbietern für den Surface Hub benötigen, benötigen Sie Skype for Business Online Eigenständig, Plan 3.
-   Die Mandantenbenutzer müssen über Exchange-Postfächer verfügen.
-   Für Ihr Surface Hub-Konto ist eine Skype for Business Online Standalone Plan 2- oder Skype for Business Online Standalone Plan 3-Lizenz erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.

1.  Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>Erstellen eines Gerätekontos mithilfe von Exchange Admin Center

>[!NOTE]
>Diese Methode funktioniert nur, wenn Sie eine Synchronisierung von einem lokalen Active Directory aus erstellen.

Sie können das Exchange Admin Center zum Erstellen eines Gerätekontos verwenden:

1.  [Erstellen eines Kontos und eines Postfachs mit dem Exchange Admin Center](#create-device-acct-exch-admin-ctr)
2.  [Erstellen einer Postfachrichtlinie für mobile Geräte über das Exchange Admin Center](#create-device-acct-exch-mbx-policy)
3.  [Konfigurieren des Kontos mit PowerShell](#create-device-acct-exch-powershell-conf)
4.  [Aktivieren des Kontos mit Skype for Business](#create-device-acct-exch-skype-for-business)

### <a href="" id="create-device-acct-exch-admin-ctr"></a>Erstellen eines Konto und eines Postfachs mit dem Exchange Admin Center

1.  Melden Sie sich beim Exchange Admin Center mit Exchange-Administratoranmeldeinformationen an.
2.  Navigieren Sie im Exchange Admin Center (EAC) im linken Bereich zu **Empfänger** .

    ![Abbildung von Postfächern im Exchange Admin Center](images/setupdeviceacctexch-01.png)

3.  Klicken Sie in den Steuerelementen oberhalb der Liste der Postfächer auf **+**, um ein neues Postfach zu erstellen, und geben Sie Folgendes an: **Anzeigename**, **Name** und **Benutzeranmeldename**. Klicken Sie anschließend auf **Speichern**.

    ![Abbildung der Erstellung ein neuen Postfachs](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>Erstellen einer Postfachrichtlinie für mobile Geräte aus dem Exchange Admin Center

>[!NOTE]
>Wenn Sie dem erstellten Konto eine Richtlinie erstellen und zuweisen möchten und Exchange 2010 verwenden, suchen Sie die entsprechenden Informationen zur Richtlinienerstellung und -zuweisung, wenn Sie die EMC (Exchange Management Console) verwenden.

 

1.  Wechseln Sie zum Exchange Admin Center.

    ![Abbildung des Exchange Admin Center](images/setupdeviceacctexch-03.png)

2.  Zum Erstellen einer Postfachrichtlinie für mobile Geräte klicken Sie im linken Bereich auf **Mobil** und dann auf **Postfachrichtlinien für mobile Geräte**. Surface Hubs erfordern ein Konto mit einer Postfachrichtlinie für mobile Geräte, die kein Kennwort erfordert. Wenn Sie bereits über eine vorhandene Richtlinie verfügen, die dieser Anforderung entspricht, können Sie diese Richtlinie auf das Konto anwenden. Führen Sie andernfalls die folgenden Schritte aus, um eine neue Richtlinie zu erstellen, die nur für Surface Hub-Gerätekonten verwendet wird.

    ![Abbildung der Verwendung von Exchange Admin Center zum Erstellen einer Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-05.png)

3.  Zum Erstellen einer neuen Postfachrichtlinie für mobile Geräte klicken Sie in den Steuerelementen oberhalb der Liste der Richtlinien auf die Schaltfläche **+** , um eine neue Richtlinie hinzuzufügen. Geben Sie als Namen einen Namen an, mit dem Sie diese Richtlinie von anderen Gerätekonten unterscheiden können (z. B. *SurfaceHubDeviceMobilePolicy*). Die Richtlinie darf nicht kennwortgeschützt sein. Stellen Sie daher sicher, dass **Kennwort anfordern** deaktiviert bleibt, und klicken Sie dann auf **Speichern**.

    ![Abbildung der neuen Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-06.png)

4.  Nachdem Sie die neue Postfachrichtlinie für mobile Geräte erstellt haben, wechseln Sie zurück zum Exchange Admin Center. Dort wird die neue Richtlinie angezeigt.

    ![Bild der neuen Postfachrichtlinie für mobile Geräte im Exchange Admin Center](images/setupdeviceacctexch-07.png)

5.  Zum Anwenden der ActiveSync-Richtlinie ohne Verwendung von PowerShell können Sie wie folgt vorgehen:

    -   Klicken Sie im Exchange Admin Center auf **Empfänger** &gt; **Postfächer**, und wählen Sie ein Postfach aus.

        ![Abbildung des Exchange Admin Center](images/setupdeviceacctexch-08.png)

    -   Scrollen Sie im Bereich **Details** zu **Telefon- und Sprachfunktionen**, und klicken Sie auf **Details anzeigen**, um den Bildschirm **Details des mobilen Geräts** anzuzeigen.

        ![Abbildung von Postfachdetails](images/setupdeviceacctexch-09.png)

    -   Die derzeit zugewiesene Postfachrichtlinie für mobile Geräte wird angezeigt. Zum Ändern der Postfachrichtlinie für mobile Geräte klicken Sie auf **Durchsuchen**.

        ![Abbildung der derzeit zugewiesenen Postfachrichtlinie für mobile Geräte](images/setupdeviceacctexch-10.png)

    -   Wählen Sie die entsprechende Postfachrichtlinie für mobile Geräte in der Liste aus, klicken Sie auf **OK** und dann auf **Speichern**.

        ![Abbildung der Liste von Postfachrichtlinien für mobile Geräte](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>Konfigurieren des Kontos mit PowerShell

Nachdem Sie mit den Onlinediensten verbunden sind, können Sie die Einrichtung des Gerätekontos abschließen. Sie verwenden die E-Mail-Adresse des Gerätekontos für folgende Aufgaben:

-   Ändern des Postfachtyps von „regulär“ in „Raum“
-   Ändern verschiedener Exchange-Eigenschaften
-   Festlegen des Kennworts des Benutzerkontos auf „Läuft nie ab“.

1.  Sie müssen die E-Mail-Adresse des Kontos eingeben und eine Variable mit diesem Wert erstellen:

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Rufen Sie den Wert zum Speichern aus dem Postfach ab:

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Drucken Sie den Wert, indem Sie Folgendes ausführen:

    ``` syntax
    $strEmail
    ```

    Die richtige E-Mail-Adresse wird angezeigt.

2.  Sie müssen das Konto in ein Raumpostfach konvertieren. Führen Sie daher dies aus:

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  Zum Authentifizieren des Gerätekontos auf einem Surface Hub müssen Sie das Raumpostfachkonto aktivieren und ein Kennwort festlegen, damit das Gerät das Konto zum Abrufen von Besprechungsinformationen mithilfe von ActiveSync und zum Anmelden bei Skype for Business verwenden kann.

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  Für das Gerätekonto können verschiedene Exchange-Eigenschaften festgelegt werden, um das Besprechungserlebnis zu verbessern. Sie können im Abschnitt [Exchange-Eigenschaften](exchange-properties-for-surface-hub-device-accounts.md) sehen, welche Eigenschaften festgelegt werden müssen.

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Jetzt müssen wir einige Eigenschaften in AD festlegen. Dazu benötigen Sie das Alias des Kontos (dies ist der Teil des Benutzerprinzipalnamens vor „@“).

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  Der Benutzer muss in AD aktiviert werden, bevor er mit einem Surface Hub authentifiziert werden kann. Führen Sie Folgendes aus:

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  Wenn das Kennwort nicht ablaufen soll, können Sie auch dies mit PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter [Kennwortverwaltung](password-management-for-surface-hub-device-accounts.md).

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>Aktivieren des Kontos mit Skype for Business

Aktivieren Sie das Gerätekonto mit Skype for Business.

Zum Aktivieren von Skype for Business muss Ihre Umgebung folgende Voraussetzungen erfüllen:

- Sie benötigen Skype for Business Online Eigenständig Plan 2 oder höher in Ihrem O365-Plan. Der Plan muss Konferenzfunktionen unterstützen.
- Wenn Sie eine Enterprise-VoIP (PSTN-Telefonie) mit Telefoniedienstanbietern für den Surface Hub benötigen, benötigen Sie Skype for Business Online Eigenständig, Plan 3.
- Die Mandantenbenutzer müssen über Exchange-Postfächer verfügen.
- Für Ihr Surface Hub-Konto ist eine Skype for Business Online Standalone Plan 2- oder Skype for Business Online Standalone Plan 3-Lizenz erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.

1. Beginnen Sie mit dem Erstellen einer Remote-PowerShell-Sitzung von einem PC aus.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. Abrufen des Surface Hub-Kontoregistrierungspools

Wenn Sie sich nicht sicher sind, welcher Wert für den `RegistrarPool` -Parameter in Ihrer Umgebung verwendet werden soll, können Sie den Wert aus einem vorhandenen Skype for Business-Benutzer mit diesem Cmdlet abrufen:

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. Um Ihr Surface Hub-Konto für Skype for Business Server zu aktivieren, führen Sie dieses Cmdlet aus:

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```