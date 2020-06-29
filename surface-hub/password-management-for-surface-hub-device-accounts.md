---
title: Kennwortverwaltung (Surface Hub)
description: Jedes Microsoft Surface Hub-Gerätekonto erfordert ein Kennwort zur Authentifizierung und Aktivierung von Features auf dem Gerät.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: Kennwort, Kennwortverwaltung, Kennwortrotation, Gerätekonto
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834027"
---
# <span data-ttu-id="4baf2-104">Kennwortverwaltung (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="4baf2-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="4baf2-105">Jedes Microsoft Surface Hub-Gerätekonto erfordert ein Kennwort zur Authentifizierung und Aktivierung von Features auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="4baf2-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="4baf2-106">Aus Sicherheitsgründen sollten Sie das Kennwort regelmäßig ändern (oder „rotieren“).</span><span class="sxs-lookup"><span data-stu-id="4baf2-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="4baf2-107">Wenn das Kennwort des Gerätekontos jedoch geändert wird, verliert das zuvor auf dem Surface Hub gespeicherte Kennwort seine Gültigkeit, und alle vom Gerätekonto abhängigen Features werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4baf2-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="4baf2-108">Sie müssen das Kennwort des Gerätekontos im Surface Hub in der Einstellungs-App aktualisieren, um die Features erneut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4baf2-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="4baf2-109">Sie haben zwei Möglichkeiten, um die Kennwortverwaltung für Ihre Surface Hub-Gerätekonten zu vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="4baf2-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="4baf2-110">Deaktivieren Sie den Kennwortablauf für das Gerätekonto.</span><span class="sxs-lookup"><span data-stu-id="4baf2-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="4baf2-111">Lassen Sie die automatische Rotation von Gerätekontokennwörtern auf dem Surface Hub zu.</span><span class="sxs-lookup"><span data-stu-id="4baf2-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="4baf2-112">Deaktivieren der Kennwortrotation für das Gerätekonto</span><span class="sxs-lookup"><span data-stu-id="4baf2-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="4baf2-113">Legen Sie die **PasswordNeverExpires**-Eigenschaft des Gerätekontos auf „True“ fest.</span><span class="sxs-lookup"><span data-stu-id="4baf2-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="4baf2-114">Überprüfen Sie, ob dies mit den Sicherheitsanforderungen Ihrer Organisation vereinbar ist.</span><span class="sxs-lookup"><span data-stu-id="4baf2-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="4baf2-115">Zulassen der automatischen Rotation von Gerätekontokennwörtern auf dem Surface Hub</span><span class="sxs-lookup"><span data-stu-id="4baf2-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="4baf2-116">Der Surface Hub kann das Kennwort eines Gerätekontos verwalten, d. h. häufig ändern, ohne dass Sie die Informationen des Gerätekontos manuell aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4baf2-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="4baf2-117">Sie können dieses Feature in den **Einstellungen** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4baf2-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="4baf2-118">Nach der Aktivierung wird das Kennwort des Gerätekontos jede Woche während der Wartungszeiten geändert.</span><span class="sxs-lookup"><span data-stu-id="4baf2-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="4baf2-119">Wenn das Kennwort des Gerätekontos geändert wird, wird Ihnen das neue Kennwort allerdings nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4baf2-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="4baf2-120">Wenn Sie sich beim Konto anmelden oder das Kennwort erneut angeben möchten (z.B. zur Änderung der Einstellungen des Gerätekontos im Surface Hub), müssen Sie das Kennwort über Active Directory oder das Verwaltungsportal von Office 365 zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="4baf2-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4baf2-121">Wenn Ihre Organisation eine hybride Topologie verwendet (einige Dienste werden lokal und einige online über Office365 gehostet), müssen Sie das Gerätekonto im Format **Domäne\Benutzername** einrichten.</span><span class="sxs-lookup"><span data-stu-id="4baf2-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="4baf2-122">Andernfalls funktioniert die Kennwortrotation nicht.</span><span class="sxs-lookup"><span data-stu-id="4baf2-122">Otherwise, password rotation will not work.</span></span>
