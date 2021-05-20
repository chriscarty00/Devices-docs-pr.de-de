---
title: Erstellen von Bereitstellungspaketen für Surface Hub 2S
description: Auf dieser Seite wird beschrieben, wie Surface Hub 2S mithilfe von Bereitstellungspaketen und anderen Tools bereitgestellt wird.
keywords: Trennen Sie Werte durch Kommata
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576865"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a>Erstellen von Bereitstellungspaketen für Surface Hub 2S

Sie können Windows Configuration Designer (WCD) verwenden, um Bereitstellungspakete zum Automatisieren der Bereitstellung von Surface Hub 2S zu erstellen. Verwenden Sie Bereitstellungspakete, um Zertifikate hinzuzufügen, Proxys zu konfigurieren, Geräteadministratoren und Gerätekonten einrichten. Sie können auch Bereitstellungspakete zusammen mit einer Konfigurationsdatei verwenden, um mehrere Surface Hubs mit einem einzigen USB-Stick zu bereitstellen.

### <a name="install-windows-configuration-designer"></a>Installieren von Windows-Konfigurations-Designer

Installieren Windows Configuration Designer aus dem Windows Assessment and Deployment Kit (ADK) für Windows 10. Laden Sie [adK für Windows 10, Version 1703, herunter, und installieren Sie es.](https://go.microsoft.com/fwlink/p/?LinkId=845542) Weitere Informationen finden Sie unter [Herunterladen und Installieren von Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### <a name="add-certificates"></a>Hinzufügen von Zertifikaten

Sie können Zertifikate der Zertifizierungsstelle in Surface Hub 2S importieren.
Zum Hinzufügen von Zertifikaten zu Surface Hub 2S benötigen Sie eine Kopie jedes Zertifikats als X.509 im CER-Format. Sie können keine .crt-, PFX- oder andere Containerformate importieren. Zertifikate müssen in den Windows importiert und nach Hierarchie angeordnet werden:

> [!div class="mx-imgBorder"]
> ![Hinzufügen von Zertifikaten](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a>Konfigurieren des Proxys während der OOBE

Wechseln Windows Konfigurations-Designer zur Registerkarte Proxyeinstellungen konfigurieren, und geben Sie die entsprechenden Einstellungen wie unten gezeigt ein.

> [!div class="mx-imgBorder"]
> ![Proxyeinstellungen konfigurieren](images/sh2-proxy.png) 

> [!NOTE]
> Wenn Sie Proxyeinstellungen konfigurieren, deaktivieren Sie Einstellungen automatisch **erkennen,** wenn Sie ein Setupskript oder einen Proxyserver verwenden möchten. Sie können ein Setupskript *oder einen* Proxyserver verwenden, nicht beides.

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a>Partner Surface Hub 2S mit Azure Active Directory

Sie können Surface Hub 2S mit Azure Active Directory mithilfe eines Bereitstellungspakets verbinden: Als globaler Azure Active Directory-Administrator können Sie eine große Anzahl neuer Windows-Geräte mit Azure Active Directory und Intune mithilfe eines Massentokens verbinden.

Um ein Massentoken zu erstellen, geben Sie ihm einen Anzeigenamen, konfigurieren Sie das Ablaufdatum (maximal 30 Tage) und verwenden Sie Ihre Administratoranmeldeinformationen, um das Token wie unten gezeigt zu erwerben:

> [!div class="mx-imgBorder"]
> ![Einrichten von Geräteadministratoren (Beispiel 1)](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Einrichten von Geräteadministratoren (Beispiel 2)](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Einrichten von Geräteadministratoren (Beispiel 3)](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a>Bereitstellen mehrerer Geräte (.csv Datei)

Zusätzlich zum Bereitstellungspaket können Sie eine Surface Hub konfigurationsdatei verwenden, um das Einrichten Ihrer Geräte noch einfacher zu machen. Eine Surface Hub enthält eine Liste der Gerätekonten und Anzeigenamen für die drahtlose Projektion. Während der ersten Ausführung erhalten Sie eine Option zum Auswählen eines Gerätekontos und eines Anzeigenamens aus einer Konfigurationsdatei.

### <a name="to-create-a-surface-hub-configuration-file"></a>So erstellen Sie Surface Hub Konfigurationsdatei

1. Erstellen Microsoft Excel oder einem anderen CSV-Editor eine CSV-Datei mit dem Namen: **SurfaceHubConfiguration.csv**

2. Geben Sie eine Liste der Gerätekonten und Anzeigenamen in diesem Format ein:

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. Speichern Sie die Datei im Stammverzeichnis des USB-Sticks, auf dem Sie die PPKG-Datei kopiert haben.

    > [!div class="mx-imgBorder"]
    > ![Beispiel für Konfigurationsdatei](images/sh2-config-file.png)
