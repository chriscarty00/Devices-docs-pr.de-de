---
title: Verwenden eines Raumsteuerungssystems (Surface Hub)
description: Raumsteuerungssysteme können mit Microsoft Surface Hub verwendet werden.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: Verwenden eines Raumsteuerungssystems, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832653"
---
# <span data-ttu-id="cc9c7-104">Verwenden eines Raumsteuerungssystems (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="cc9c7-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="cc9c7-105">Raumsteuerungssysteme können mit Microsoft Surface Hub verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="cc9c7-106">Die Verwendung eines Raumsteuerungssystems mit Surface Hub umfasst die Verbindung von Raumsteuerungshardware mit Surface Hub. Diese wird in der Regel über den seriellen RJ11-Anschluss unten an Surface Hub hergestellt.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <span data-ttu-id="cc9c7-107">Terminaleinstellungen</span><span class="sxs-lookup"><span data-stu-id="cc9c7-107">Terminal settings</span></span>

<span data-ttu-id="cc9c7-108">Zum Herstellen der Verbindung mit einem Raumsteuerungssystem ist keine Konfiguration von Terminaleinstellungen an Surface Hub erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="cc9c7-109">Wenn Sie einen PC oder Laptop mit Surface Hub verbinden und serielle Befehle von Surface Hub senden möchten, können Sie ein Terminalemulationsprogramm wie Tera Term oder PuTTY verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="cc9c7-110">Einstellung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-110">Setting</span></span> | <span data-ttu-id="cc9c7-111">Wert</span><span class="sxs-lookup"><span data-stu-id="cc9c7-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="cc9c7-112">Baudrate</span><span class="sxs-lookup"><span data-stu-id="cc9c7-112">Baud rate</span></span> | <span data-ttu-id="cc9c7-113">115200</span><span class="sxs-lookup"><span data-stu-id="cc9c7-113">115200</span></span> |
| <span data-ttu-id="cc9c7-114">Datenbits</span><span class="sxs-lookup"><span data-stu-id="cc9c7-114">Data bits</span></span> | <span data-ttu-id="cc9c7-115">8</span><span class="sxs-lookup"><span data-stu-id="cc9c7-115">8</span></span> | 
| <span data-ttu-id="cc9c7-116">Stoppbits</span><span class="sxs-lookup"><span data-stu-id="cc9c7-116">Stop bits</span></span> | <span data-ttu-id="cc9c7-117">1</span><span class="sxs-lookup"><span data-stu-id="cc9c7-117">1</span></span> |
| <span data-ttu-id="cc9c7-118">Parität</span><span class="sxs-lookup"><span data-stu-id="cc9c7-118">Parity</span></span> | <span data-ttu-id="cc9c7-119">keine</span><span class="sxs-lookup"><span data-stu-id="cc9c7-119">none</span></span> |
| <span data-ttu-id="cc9c7-120">Flusssteuerung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-120">Flow control</span></span> | <span data-ttu-id="cc9c7-121">keine</span><span class="sxs-lookup"><span data-stu-id="cc9c7-121">none</span></span> |
| <span data-ttu-id="cc9c7-122">Zeilenvorschub</span><span class="sxs-lookup"><span data-stu-id="cc9c7-122">Line feed</span></span> | <span data-ttu-id="cc9c7-123">bei jedem Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="cc9c7-123">every carriage return</span></span> |
 

## <span data-ttu-id="cc9c7-124">Verdrahtungsdiagramm</span><span class="sxs-lookup"><span data-stu-id="cc9c7-124">Wiring diagram</span></span>

<span data-ttu-id="cc9c7-125">Sie können mit einem standardmäßigen RJ-11 (6P6C)-Stecker den seriellen Surface Hub-Anschluss mit einem Raumsteuerungssystem verbinden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="cc9c7-126">Dies ist die empfohlene Methode.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-126">This is the recommended method.</span></span> <span data-ttu-id="cc9c7-127">Sie können auch ein RJ-11-Kabel mit vier Leitern verwenden, aber diese Methode wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="cc9c7-128">In diesem Diagramm ist die korrekte Pinbelegung dargestellt, die für ein RJ-11 (6P6C)-auf-DB9-Kabel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![Abbildung des Verdrahtungsdiagramms](images/room-control-wiring-diagram.png)

## <span data-ttu-id="cc9c7-130">Befehlssätze</span><span class="sxs-lookup"><span data-stu-id="cc9c7-130">Command sets</span></span>

<span data-ttu-id="cc9c7-131">Raumsteuerungssysteme verwenden gängige Besprechungsraumszenarien für Befehle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="cc9c7-132">Befehle stammen vom Raumsteuerungssystem und werden über eine serielle Verbindung an einen Surface Hub kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="cc9c7-133">Befehle sind ASCII-basiert, und der Surface Hub bestätigt auftretende Zustandsänderungen.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="cc9c7-134">Der folgende Befehlsmodifizierer sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-134">The following command modifiers are available.</span></span> <span data-ttu-id="cc9c7-135">Befehle werden mit einem Neue-Zeile-Zeichen (\n) beendet.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="cc9c7-136">Antworten können zu einem beliebigen Zeitpunkt als Reaktion auf Zustandsänderungen erfolgen, die nicht direkt von einem Verwaltungsport-Befehl ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="cc9c7-137">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="cc9c7-137">Modifier</span></span> | <span data-ttu-id="cc9c7-138">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cc9c7-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="cc9c7-139">Erhöhen eines Werts</span><span class="sxs-lookup"><span data-stu-id="cc9c7-139">Increment a value</span></span> |
| - | <span data-ttu-id="cc9c7-140">Verringern eines Werts</span><span class="sxs-lookup"><span data-stu-id="cc9c7-140">Decrease a value</span></span> |
| = | <span data-ttu-id="cc9c7-141">Festlegen eines einzelnen Werts</span><span class="sxs-lookup"><span data-stu-id="cc9c7-141">Set a discrete value</span></span> |
| <span data-ttu-id="cc9c7-142">?</span><span class="sxs-lookup"><span data-stu-id="cc9c7-142">?</span></span> | <span data-ttu-id="cc9c7-143">Abfragen für einen aktuellen Wert</span><span class="sxs-lookup"><span data-stu-id="cc9c7-143">Queries for a current value</span></span> |
 

## <span data-ttu-id="cc9c7-144">Ein/Aus</span><span class="sxs-lookup"><span data-stu-id="cc9c7-144">Power</span></span>

<span data-ttu-id="cc9c7-145">Der Surface Hub kann sich in einem der folgenden Ein/Aus-Zustände befinden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="cc9c7-146">Zustand</span><span class="sxs-lookup"><span data-stu-id="cc9c7-146">State</span></span> | <span data-ttu-id="cc9c7-147">Energy Star-Zustand</span><span class="sxs-lookup"><span data-stu-id="cc9c7-147">Energy Star state</span></span>| <span data-ttu-id="cc9c7-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-149">0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-149">0</span></span> | <span data-ttu-id="cc9c7-150">S5</span><span class="sxs-lookup"><span data-stu-id="cc9c7-150">S5</span></span> | <span data-ttu-id="cc9c7-151">Aus</span><span class="sxs-lookup"><span data-stu-id="cc9c7-151">Off</span></span> |
| <span data-ttu-id="cc9c7-152">1</span><span class="sxs-lookup"><span data-stu-id="cc9c7-152">1</span></span> | - | <span data-ttu-id="cc9c7-153">Einschalten (unbestimmt)</span><span class="sxs-lookup"><span data-stu-id="cc9c7-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="cc9c7-154">2</span><span class="sxs-lookup"><span data-stu-id="cc9c7-154">2</span></span> | <span data-ttu-id="cc9c7-155">S3</span><span class="sxs-lookup"><span data-stu-id="cc9c7-155">S3</span></span> | <span data-ttu-id="cc9c7-156">Ruhezustand</span><span class="sxs-lookup"><span data-stu-id="cc9c7-156">Sleep</span></span> |
| <span data-ttu-id="cc9c7-157">5</span><span class="sxs-lookup"><span data-stu-id="cc9c7-157">5</span></span> | <span data-ttu-id="cc9c7-158">S0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-158">S0</span></span> | <span data-ttu-id="cc9c7-159">Bereit</span><span class="sxs-lookup"><span data-stu-id="cc9c7-159">Ready</span></span> |


<span data-ttu-id="cc9c7-160">Im Ersatz-PC-Modus stehen nur die Energiezustände „Bereit“ und „Aus“ zur Verfügung, die lediglich die Anzeige ändern.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="cc9c7-161">Der Verwaltungsport kann nicht zum Einschalten des Ersatz-PCs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="cc9c7-162">Zustand</span><span class="sxs-lookup"><span data-stu-id="cc9c7-162">State</span></span> | <span data-ttu-id="cc9c7-163">Energy Star-Zustand</span><span class="sxs-lookup"><span data-stu-id="cc9c7-163">Energy Star state</span></span>| <span data-ttu-id="cc9c7-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-165">0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-165">0</span></span> | <span data-ttu-id="cc9c7-166">S5</span><span class="sxs-lookup"><span data-stu-id="cc9c7-166">S5</span></span> | <span data-ttu-id="cc9c7-167">Aus</span><span class="sxs-lookup"><span data-stu-id="cc9c7-167">Off</span></span> |
| <span data-ttu-id="cc9c7-168">5</span><span class="sxs-lookup"><span data-stu-id="cc9c7-168">5</span></span> | <span data-ttu-id="cc9c7-169">S0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-169">S0</span></span> | <span data-ttu-id="cc9c7-170">Bereit</span><span class="sxs-lookup"><span data-stu-id="cc9c7-170">Ready</span></span> |

<span data-ttu-id="cc9c7-171">Bei Steuerungsgeräten müssen alle Zustände außer „5/Bereit" als deaktiviert betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="cc9c7-172">Jeder PowerOn-Befehl führt zu zweizustands Änderungen und Antworten.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="cc9c7-173">Befehl</span><span class="sxs-lookup"><span data-stu-id="cc9c7-173">Command</span></span> | <span data-ttu-id="cc9c7-174">Zustandsänderung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-174">State change</span></span>| <span data-ttu-id="cc9c7-175">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc9c7-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="cc9c7-176">PowerOn</span></span> | <span data-ttu-id="cc9c7-177">Das Gerät wird eingeschaltet (Anzeige + PC).</span><span class="sxs-lookup"><span data-stu-id="cc9c7-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="cc9c7-178">Der PC-Dienst benachrichtigt den SMC darüber, dass der PC bereit ist.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="cc9c7-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-179">Power=0</span></span></br></br><span data-ttu-id="cc9c7-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="cc9c7-180">Power=5</span></span> |
| <span data-ttu-id="cc9c7-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="cc9c7-181">PowerOff</span></span> | <span data-ttu-id="cc9c7-182">Das Gerät wechselt in den Umgebungszustand (PC eingeschaltet, Anzeige abgeblendet).</span><span class="sxs-lookup"><span data-stu-id="cc9c7-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="cc9c7-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-183">Power=0</span></span> |
| <span data-ttu-id="cc9c7-184">Power?</span><span class="sxs-lookup"><span data-stu-id="cc9c7-184">Power?</span></span> |  <span data-ttu-id="cc9c7-185">Der SMC meldet den zuletzt bekannten Energiezustand.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="cc9c7-186">Leistung=<#></span><span class="sxs-lookup"><span data-stu-id="cc9c7-186">Power=<#></span></span> |



## <span data-ttu-id="cc9c7-187">Helligkeit</span><span class="sxs-lookup"><span data-stu-id="cc9c7-187">Brightness</span></span>

<span data-ttu-id="cc9c7-188">Die aktuelle Helligkeitsstufe umfasst einen Bereich von 0 bis 100.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="cc9c7-189">Änderungen der Helligkeitsstufen können durch ein Raumsteuerungssystem oder ein anderes System gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="cc9c7-190">Befehl</span><span class="sxs-lookup"><span data-stu-id="cc9c7-190">Command</span></span> | <span data-ttu-id="cc9c7-191">Zustandsänderung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-191">State change</span></span> |<span data-ttu-id="cc9c7-192">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc9c7-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="cc9c7-193">Brightness+</span></span> | <span data-ttu-id="cc9c7-194">Der System-Managementcontroller (SMC) sendet den Befehl zum Erhöhen der Helligkeit.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="cc9c7-195">Der PC-Dienst im Raumsteuerungssystem benachrichtigt den SMC über die neue Helligkeitsstufe.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="cc9c7-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="cc9c7-196">Brightness = 51</span></span> |
| <span data-ttu-id="cc9c7-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="cc9c7-197">Brightness-</span></span> |  <span data-ttu-id="cc9c7-198">Der SMC sendet den Befehl zum Verringern der Helligkeit.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="cc9c7-199">Der PC-Dienst benachrichtigt den SMC über die neue Helligkeitsstufe.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="cc9c7-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="cc9c7-200">Brightness = 50</span></span> |

## <span data-ttu-id="cc9c7-201">Volume</span><span class="sxs-lookup"><span data-stu-id="cc9c7-201">Volume</span></span>

<span data-ttu-id="cc9c7-202">Die aktuelle Lautstärkestufe ist ein Bereich von 0 bis 100.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="cc9c7-203">Änderungen der Lautstärkestufen können durch ein Raumsteuerungssystem oder ein anderes System gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="cc9c7-204">Der Befehl „Volume” steuert nur die Lautstärke für den eingebetteten oder den Ersatz-PC-Modus, nicht über [Gastquellen](connect-and-display-with-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="cc9c7-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="cc9c7-205">Befehl</span><span class="sxs-lookup"><span data-stu-id="cc9c7-205">Command</span></span> | <span data-ttu-id="cc9c7-206">Zustandsänderung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-206">State change</span></span> | <span data-ttu-id="cc9c7-207">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc9c7-207">Response</span></span></br><span data-ttu-id="cc9c7-208">(Aktiviert im [Ersatz-PC-Modus](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span><span class="sxs-lookup"><span data-stu-id="cc9c7-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="cc9c7-209">Volume+</span></span> |  <span data-ttu-id="cc9c7-210">Der SMC sendet den Befehl zum Erhöhen der Lautstärke.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="cc9c7-211">Der PC-Dienst benachrichtigt den SMC über die neue Lautstärkestufe.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="cc9c7-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="cc9c7-212">Volume = 51</span></span> |
| <span data-ttu-id="cc9c7-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="cc9c7-213">Volume-</span></span> |  <span data-ttu-id="cc9c7-214">Der SMC sendet den Befehl zum Verringern der Lautstärke.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="cc9c7-215">Der PC-Dienst benachrichtigt den SMC über die neue Lautstärkestufe.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="cc9c7-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="cc9c7-216">Volume = 50</span></span> |


 

## <span data-ttu-id="cc9c7-217">Stummschalten für Audio</span><span class="sxs-lookup"><span data-stu-id="cc9c7-217">Mute for audio</span></span>

<span data-ttu-id="cc9c7-218">Audio kann stummgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-218">Audio can be muted.</span></span>

| <span data-ttu-id="cc9c7-219">Befehl</span><span class="sxs-lookup"><span data-stu-id="cc9c7-219">Command</span></span> | <span data-ttu-id="cc9c7-220">Zustandsänderung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-220">State change</span></span> | <span data-ttu-id="cc9c7-221">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc9c7-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="cc9c7-222">AudioMute+</span></span> |  <span data-ttu-id="cc9c7-223">Der SMC sendet den Befehl zum Stummschalten von Audioinhalten.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="cc9c7-224">Der PC-Dienst benachrichtigt den SMC darüber, dass Audioinhalte stummgeschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="cc9c7-225">keine</span><span class="sxs-lookup"><span data-stu-id="cc9c7-225">none</span></span> |


 

## <span data-ttu-id="cc9c7-226">Videoquelle</span><span class="sxs-lookup"><span data-stu-id="cc9c7-226">Video source</span></span>

<span data-ttu-id="cc9c7-227">Es können mehrere Anzeigequellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-227">Several display sources can be used.</span></span>

| <span data-ttu-id="cc9c7-228">Zustand</span><span class="sxs-lookup"><span data-stu-id="cc9c7-228">State</span></span> | <span data-ttu-id="cc9c7-229">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="cc9c7-230">0</span><span class="sxs-lookup"><span data-stu-id="cc9c7-230">0</span></span> |  <span data-ttu-id="cc9c7-231">Integrierter PC</span><span class="sxs-lookup"><span data-stu-id="cc9c7-231">Onboard PC</span></span> |
| <span data-ttu-id="cc9c7-232">1</span><span class="sxs-lookup"><span data-stu-id="cc9c7-232">1</span></span> |  <span data-ttu-id="cc9c7-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="cc9c7-233">DisplayPort</span></span> |
| <span data-ttu-id="cc9c7-234">2</span><span class="sxs-lookup"><span data-stu-id="cc9c7-234">2</span></span> |  <span data-ttu-id="cc9c7-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="cc9c7-235">HDMI</span></span> |
| <span data-ttu-id="cc9c7-236">3</span><span class="sxs-lookup"><span data-stu-id="cc9c7-236">3</span></span> |  <span data-ttu-id="cc9c7-237">VGA</span><span class="sxs-lookup"><span data-stu-id="cc9c7-237">VGA</span></span> |


 

<span data-ttu-id="cc9c7-238">Änderungen der Anzeigequelle können durch ein Raumsteuerungssystem oder ein anderes System gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="cc9c7-239">Befehl</span><span class="sxs-lookup"><span data-stu-id="cc9c7-239">Command</span></span> | <span data-ttu-id="cc9c7-240">Zustandsänderung</span><span class="sxs-lookup"><span data-stu-id="cc9c7-240">State change</span></span> | <span data-ttu-id="cc9c7-241">Antwort</span><span class="sxs-lookup"><span data-stu-id="cc9c7-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cc9c7-242">Quelle=#</span><span class="sxs-lookup"><span data-stu-id="cc9c7-242">Source=#</span></span> |  <span data-ttu-id="cc9c7-243">Der SMC wechselt zur gewünschten Quelle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="cc9c7-244">Der PC-Dienst benachrichtigt den SMC darüber, dass die Anzeigequelle gewechselt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="cc9c7-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cc9c7-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="cc9c7-246">Source+</span><span class="sxs-lookup"><span data-stu-id="cc9c7-246">Source+</span></span> |  <span data-ttu-id="cc9c7-247">Der SMC wechselt zur nächsten aktiven Eingabequelle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="cc9c7-248">Der PC-Dienst benachrichtigt den SMC über die aktuelle Eingabequelle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="cc9c7-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cc9c7-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="cc9c7-250">Source-</span><span class="sxs-lookup"><span data-stu-id="cc9c7-250">Source-</span></span> | <span data-ttu-id="cc9c7-251">Der SMC wechselt zur vorherigen aktiven Eingabequelle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="cc9c7-252">Der PC-Dienst benachrichtigt den SMC über die aktuelle Eingabequelle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="cc9c7-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cc9c7-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="cc9c7-254">Source?</span><span class="sxs-lookup"><span data-stu-id="cc9c7-254">Source?</span></span> |  <span data-ttu-id="cc9c7-255">Der SMC fragt beim PC-Dienst die aktive Eingabequelle ab.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="cc9c7-256">Der PC-Dienst benachrichtigt den SMC über die aktuelle Eingabequelle.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="cc9c7-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cc9c7-257">Source=&lt;#&gt;</span></span> |

## <span data-ttu-id="cc9c7-258">Fehler</span><span class="sxs-lookup"><span data-stu-id="cc9c7-258">Errors</span></span>

<span data-ttu-id="cc9c7-259">Fehler werden entsprechend dem Format in dieser Tabelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="cc9c7-260">Fehler</span><span class="sxs-lookup"><span data-stu-id="cc9c7-260">Error</span></span> | <span data-ttu-id="cc9c7-261">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc9c7-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="cc9c7-262">Fehler: Unbekannter Befehl '&lt;Eingabe&gt;'.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cc9c7-263">Die Anweisung enthält einen unbekannten anfänglichen Befehl.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="cc9c7-264">Beispielsweise wäre „VOL+“ ungültig und würde „Fehler: Unbekannter Befehl 'VOL'“ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="cc9c7-265">Fehler: Unbekannter Operator '&lt;Eingabe&gt;'.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cc9c7-266">Die Anweisung enthält einen unbekannten Operator.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="cc9c7-267">Beispielsweise wäre &quot;Volume!&quot; ungültig und würde &quot; Fehler: Unbekannter Operator '!'&quot; zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="cc9c7-268">Fehler: Unbekannter Parameter '&lt;Eingabe&gt;'.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cc9c7-269">Die Anweisung enthält einen unbekannten Parameter.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="cc9c7-270">Beispielsweise wäre „Volume=abc“ ungültig und würde „Fehler: Unbekannter Parameter 'abc'“ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="cc9c7-271">Fehler: Befehl nicht verfügbar, wenn aus '&lt;Eingabe&gt;'.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cc9c7-272">Wenn Surface Hub ausgeschaltet ist, geben andere Befehle als „Ein/Aus“ diesen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="cc9c7-273">Beispielsweise wäre „Volume+“ ungültig und würde „Fehler: Befehl nicht verfügbar, wenn aus 'Volume'“ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <span data-ttu-id="cc9c7-274">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cc9c7-274">Related topics</span></span>


[<span data-ttu-id="cc9c7-275">Verwalten von Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cc9c7-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="cc9c7-276">Microsoft Surface Hub-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="cc9c7-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





