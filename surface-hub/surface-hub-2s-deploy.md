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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834187"
---
# Erstellen von Bereitstellungspaketen für Surface Hub 2S

Sie können den Windows-Konfigurations-Designer (WCD) verwenden, um Bereitstellungspakete zu erstellen, um den Bereitstellungsprozess von Surface Hub 2S zu automatisieren. Verwenden Sie Bereitstellungspakete, um Zertifikate hinzuzufügen, Proxys zu konfigurieren, geräteadministratoren und Geräte Konten einzurichten. Sie können auch Bereitstellungspakete zusammen mit einer Konfigurationsdatei verwenden, um mehrere Surface-Hubs mit einem einzigen USB-Daumen Laufwerk bereitzustellen.

### Installieren von Windows-Konfigurations-Designer

Installieren Sie den Windows-Konfigurations-Designer aus dem Windows Assessment and Deployment Kit (ADK) für Windows 10. Laden Sie das [ADK für Windows 10, Version 1703, herunter,](https://go.microsoft.com/fwlink/p/?LinkId=845542)und installieren Sie es. Weitere Informationen finden Sie unter [herunterladen und Installieren des Windows-ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### Hinzufügen von Zertifikaten

Sie können Zertifikat Zertifizierungsstellenzertifikate in Surface Hub 2S importieren.
Wenn Sie dem Surface Hub 2S Zertifikate hinzufügen möchten, benötigen Sie eine Kopie der einzelnen Zertifikate als X. 509 im CER-Format. Sie können CRT-, PFX-oder andere Containerformate nicht importieren. Zertifikate müssen in den Windows-Konfigurations-Designer importiert und nach Hierarchie geordnet werden:

 ![Hinzufügen von Zertifikaten](images/sh2-wcd.png)

### Konfigurieren des Proxys während OOBE

Wechseln Sie im Windows-Konfigurations-Designer zur Registerkarte Proxyeinstellungen konfigurieren, und geben Sie die entsprechenden Einstellungen wie unten dargestellt ein.

 ![Proxyeinstellungen konfigurieren](images/sh2-proxy.png) 

> [!NOTE]
> Wenn Sie Proxyeinstellungen konfigurieren, deaktivieren Sie die Option zum **automatischen Erkennen von Einstellungen** , wenn Sie beabsichtigen, ein Setupskript oder einen Proxy Server zu verwenden. Sie können ein Setupskript *oder* einen Proxy Server verwenden, nicht beide.

### Affiliate Surface Hub 2S mit Azure Active Directory

Sie können Surface Hub 2S mit Azure Active Directory mit einem Bereitstellungspaket verknüpfen: als globaler Azure Active Directory-Administrator können Sie mit einem Massen Token eine große Anzahl von neuen Windows-Geräten an Azure Active Directory und InTune teilnehmen.

Wenn Sie ein Massen Token erstellen möchten, geben Sie ihm einen Anzeigenamen, konfigurieren Sie das Ablaufdatum (maximal 30 Tage), und verwenden Sie Ihre Administratoranmeldeinformationen zum Abrufen des Tokens, wie unten dargestellt:

 ![Einrichten von geräteadministratoren](images/sh2-token.png) <br><br>
 ![Einrichten von geräteadministratoren](images/sh2-token2.png) <br><br>
 ![Einrichten von geräteadministratoren](images/sh2-token3.png) <br><br>

### Bereitstellen mehrerer Geräte (CSV-Datei)

Zusätzlich zum Bereitstellungspaket können Sie eine Surface Hub-Konfigurationsdatei verwenden, um die Einrichtung Ihrer Geräte noch einfacher zu gestalten. Eine Surface Hub-Konfigurationsdatei enthält eine Liste der Geräte Konten und Anzeigenamen für die drahtlose Projektion. Während der ersten Ausführung erhalten Sie eine Option, mit der Sie ein Geräte Konto und einen Anzeigenamen aus einer Konfigurationsdatei auswählen können.

### So erstellen Sie eine Surface Hub-Konfigurationsdatei

1. Erstellen Sie mithilfe von Microsoft Excel oder einem anderen CSV-Editor eine CSV-Datei mit dem Namen: **SurfaceHubConfiguration.csv**
2. Geben Sie eine Liste der Geräte Konten und Anzeige Namen in diesem Format ein:

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. Speichern Sie die Datei im Stammverzeichnis des USB-Thumb-Laufwerks, auf dem Sie die PPKG-Datei kopiert haben.

    ![Beispiel für eine Konfigurationsdatei](images/sh2-config-file.png)
