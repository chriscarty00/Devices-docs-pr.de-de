---
title: Speichern des BitLocker-Schlüssels (Surface Hub)
description: Jedes Microsoft Surface Hub-Gerät wird automatisch mit BitLocker-Laufwerkverschlüsselungssoftware eingerichtet. Microsoft empfiehlt, die BitLocker-Wiederherstellungsschlüssel unbedingt zu sichern.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, Bitlocker-Wiederherstellungsschlüssel
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833865"
---
# <span data-ttu-id="f47d5-105">Speichern des BitLocker-Schlüssels (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="f47d5-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="f47d5-106">Jedes Microsoft Surface Hub-Gerät wird automatisch mit BitLocker-Laufwerkverschlüsselungssoftware eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="f47d5-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="f47d5-107">Microsoft empfiehlt, die BitLocker-Wiederherstellungsschlüssel unbedingt zu sichern.</span><span class="sxs-lookup"><span data-stu-id="f47d5-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="f47d5-108">Es gibt verschiedene Möglichkeiten, den BitLocker-Schlüssel auf dem Surface Hub zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f47d5-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="f47d5-109">Wenn Sie den Surface Hub mit einer Domäne verbunden haben, sichert das Gerät den Schlüssel in der Domäne und speichert ihn im Computerobjekt.</span><span class="sxs-lookup"><span data-stu-id="f47d5-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="f47d5-110">Wenn Sie den BitLocker-Schlüssel nach dem Verbinden des Geräts mit einer Domäne nicht finden, unterstützt das Active Directory-Schema die BitLocker-Schlüsselsicherung wahrscheinlich nicht.</span><span class="sxs-lookup"><span data-stu-id="f47d5-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="f47d5-111">Wenn Sie das Schema nicht ändern möchten, können Sie den BitLocker-Schlüssel speichern, indem Sie unter „Einstellungen“ die Vorgehensweise für die Verwendung eines lokalen Administratorkontos ausführen, die später in dieser Liste beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f47d5-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="f47d5-112">Wenn Sie den Surface Hub mit Azure Active Directory (Azure AD) verbunden haben, wird der BitLocker-Schlüssel in dem Konto gespeichert, das zum Verknüpfen des Geräts verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f47d5-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="f47d5-113">Wenn Sie ein lokales Administratorkonto zum Verwalten des Geräts verwenden, können Sie den BitLocker-Schlüssel speichern, indem Sie zur **Einstellungs** -App wechseln und zur **Aktualisierung & Sicherheits** &gt; **Wiederherstellung**navigieren.</span><span class="sxs-lookup"><span data-stu-id="f47d5-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="f47d5-114">Schließen Sie ein USB-Laufwerk an, und wählen Sie die Option zum Speichern des BitLocker-Schlüssels aus.</span><span class="sxs-lookup"><span data-stu-id="f47d5-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="f47d5-115">Der Schlüssel wird in einer Textdatei auf dem USB-Laufwerk gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f47d5-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="f47d5-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f47d5-116">Related topics</span></span>

[<span data-ttu-id="f47d5-117">Verwalten von Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f47d5-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="f47d5-118">Microsoft Surface Hub-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="f47d5-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





