---
title: Ziel-Editor für Dimensions Verarbeitung (Seite erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621601"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a><span data-ttu-id="44caa-102">Ziel-Editor für Dimensionsverarbeitung (Seite Erweitert)</span><span class="sxs-lookup"><span data-stu-id="44caa-102">Dimension Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="44caa-103">Verwenden Sie zum Konfigurieren der Fehlerbehandlung die Seite **Erweitert** im Dialogfeld **Ziel-Editor für Dimensionsverarbeitung** .</span><span class="sxs-lookup"><span data-stu-id="44caa-103">Use the **Advanced** page of the **Dimension Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="44caa-104">Weitere Informationen zum Ziel für Dimensionsverarbeitung finden Sie unter [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="44caa-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="44caa-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="44caa-105">Options</span></span>  
 <span data-ttu-id="44caa-106">**Standardfehlerkonfiguration verwenden**</span><span class="sxs-lookup"><span data-stu-id="44caa-106">**Use default error configuration.**</span></span>  
 <span data-ttu-id="44caa-107">Gibt an, ob die Standardfehlerbehandlung von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="44caa-107">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="44caa-108">Standardmäßig ist dieser Wert auf `True` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="44caa-108">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="44caa-109">**Schlüsselfehler Aktion**</span><span class="sxs-lookup"><span data-stu-id="44caa-109">**Key error action**</span></span>  
 <span data-ttu-id="44caa-110">Gibt an, wie Datensätze behandelt werden, die unzulässige Schlüsselwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="44caa-110">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="44caa-111">Wert</span><span class="sxs-lookup"><span data-stu-id="44caa-111">Value</span></span>|<span data-ttu-id="44caa-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44caa-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44caa-113">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="44caa-113">**ConvertToUnknown**</span></span>|<span data-ttu-id="44caa-114">Konvertiert den unzulässigen Schlüsselwert in den Wert `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="44caa-114">Convert the unacceptable key value to the `UnknownMember` value.</span></span>|  
|<span data-ttu-id="44caa-115">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="44caa-115">**DiscardRecord**</span></span>|<span data-ttu-id="44caa-116">Verwirft den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="44caa-116">Discard the record.</span></span>|  
  
 <span data-ttu-id="44caa-117">**Fehler ignorieren**</span><span class="sxs-lookup"><span data-stu-id="44caa-117">**Ignore errors**</span></span>  
 <span data-ttu-id="44caa-118">Gibt an, dass Fehler ignoriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44caa-118">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="44caa-119">**Bei Fehler abbrechen**</span><span class="sxs-lookup"><span data-stu-id="44caa-119">**Stop on error**</span></span>  
 <span data-ttu-id="44caa-120">Gibt an, dass die Verarbeitung beendet werden soll, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="44caa-120">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="44caa-121">**Anzahl von Fehlern**</span><span class="sxs-lookup"><span data-stu-id="44caa-121">**Number of errors**</span></span>  
 <span data-ttu-id="44caa-122">Gibt den Grenzwert für die Anzahl der Fehler an, bei dem die Verarbeitung beendet werden soll, wenn Sie **Bei Fehler beenden**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="44caa-122">Specify the error threshold at which processing should stop, if you have selected **Stop on errors**.</span></span>  
  
 <span data-ttu-id="44caa-123">**Aktion bei Fehler**</span><span class="sxs-lookup"><span data-stu-id="44caa-123">**On error action**</span></span>  
 <span data-ttu-id="44caa-124">Gibt die Aktion an, die bei Erreichen des Fehlergrenzwertes ausgeführt wird, wenn Sie **Bei Fehler beenden**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="44caa-124">Specify the action to take when the error threshold is reached, if you have selected **Stop on errors**.</span></span>  
  
|<span data-ttu-id="44caa-125">Wert</span><span class="sxs-lookup"><span data-stu-id="44caa-125">Value</span></span>|<span data-ttu-id="44caa-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44caa-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44caa-127">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="44caa-127">**StopProcessing**</span></span>|<span data-ttu-id="44caa-128">Beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="44caa-128">Stop processing.</span></span>|  
|<span data-ttu-id="44caa-129">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="44caa-129">**StopLogging**</span></span>|<span data-ttu-id="44caa-130">Beendet das Protokollieren der Fehler.</span><span class="sxs-lookup"><span data-stu-id="44caa-130">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="44caa-131">**Schlüssel nicht gefunden**</span><span class="sxs-lookup"><span data-stu-id="44caa-131">**Key not found**</span></span>  
 <span data-ttu-id="44caa-132">Gibt die Aktion an, die beim Fehler Schlüssel nicht gefunden ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="44caa-132">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="44caa-133">Standardmäßig ist dieser Wert **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="44caa-133">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="44caa-134">Wert</span><span class="sxs-lookup"><span data-stu-id="44caa-134">Value</span></span>|<span data-ttu-id="44caa-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44caa-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44caa-136">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="44caa-136">**IgnoreError**</span></span>|<span data-ttu-id="44caa-137">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-137">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-138">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="44caa-138">**ReportAndContinue**</span></span>|<span data-ttu-id="44caa-139">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-139">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-140">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="44caa-140">**ReportAndStop**</span></span>|<span data-ttu-id="44caa-141">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="44caa-141">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="44caa-142">**Doppelter Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="44caa-142">**Duplicate key**</span></span>  
 <span data-ttu-id="44caa-143">Gibt die Aktion an, die beim Fehler Doppelter Schlüssel ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="44caa-143">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="44caa-144">Standardmäßig ist dieser Wert **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="44caa-144">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="44caa-145">Wert</span><span class="sxs-lookup"><span data-stu-id="44caa-145">Value</span></span>|<span data-ttu-id="44caa-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44caa-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44caa-147">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="44caa-147">**IgnoreError**</span></span>|<span data-ttu-id="44caa-148">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-148">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-149">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="44caa-149">**ReportAndContinue**</span></span>|<span data-ttu-id="44caa-150">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-150">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-151">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="44caa-151">**ReportAndStop**</span></span>|<span data-ttu-id="44caa-152">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="44caa-152">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="44caa-153">**NULL-Schlüssel in unbekanntes konvertiert**</span><span class="sxs-lookup"><span data-stu-id="44caa-153">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="44caa-154">Gibt die Aktion an, die ausgeführt werden soll, wenn ein NULL-Schlüssel in den Wert `UnknownMember` konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="44caa-154">Specify the action to take when a null key has been converted to the `UnknownMember` value.</span></span> <span data-ttu-id="44caa-155">Standardmäßig ist dieser Wert **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="44caa-155">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="44caa-156">Wert</span><span class="sxs-lookup"><span data-stu-id="44caa-156">Value</span></span>|<span data-ttu-id="44caa-157">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44caa-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44caa-158">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="44caa-158">**IgnoreError**</span></span>|<span data-ttu-id="44caa-159">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-159">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-160">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="44caa-160">**ReportAndContinue**</span></span>|<span data-ttu-id="44caa-161">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-161">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-162">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="44caa-162">**ReportAndStop**</span></span>|<span data-ttu-id="44caa-163">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="44caa-163">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="44caa-164">**NULL-Schlüssel nicht zulässig**</span><span class="sxs-lookup"><span data-stu-id="44caa-164">**Null key not allowed**</span></span>  
 <span data-ttu-id="44caa-165">Gibt die Aktion an, die ausgeführt wird, wenn NULL-Schlüssel unzulässig sind und ein NULL-Schlüssel entdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="44caa-165">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="44caa-166">Standardmäßig ist dieser Wert **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="44caa-166">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="44caa-167">Wert</span><span class="sxs-lookup"><span data-stu-id="44caa-167">Value</span></span>|<span data-ttu-id="44caa-168">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44caa-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44caa-169">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="44caa-169">**IgnoreError**</span></span>|<span data-ttu-id="44caa-170">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-170">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-171">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="44caa-171">**ReportAndContinue**</span></span>|<span data-ttu-id="44caa-172">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="44caa-172">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="44caa-173">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="44caa-173">**ReportAndStop**</span></span>|<span data-ttu-id="44caa-174">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="44caa-174">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="44caa-175">**Fehlerprotokollpfad**</span><span class="sxs-lookup"><span data-stu-id="44caa-175">**Error log path**</span></span>  
 <span data-ttu-id="44caa-176">Geben Sie den Pfad für das Fehlerprotokoll ein, oder klicken Sie auf die Schaltfläche zum **Durchsuchen (...)** , um ein Ziel auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="44caa-176">Type the path of the error log, or click the **browse(...)** button to select a destination.</span></span>  
  
 <span data-ttu-id="44caa-177">**Durchsuchen (…)**</span><span class="sxs-lookup"><span data-stu-id="44caa-177">**Browse (...)**</span></span>  
 <span data-ttu-id="44caa-178">Wählen Sie einen Pfad für das Fehlerprotokoll aus.</span><span class="sxs-lookup"><span data-stu-id="44caa-178">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44caa-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44caa-179">See Also</span></span>  
 <span data-ttu-id="44caa-180">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="44caa-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="44caa-181">[Ziel-Editor für Dimensions Verarbeitung &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="44caa-181">[Dimension Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="44caa-182">Ziel-Editor für Dimensionsverarbeitung &#40;Seite Zuordnungen&#41;</span><span class="sxs-lookup"><span data-stu-id="44caa-182">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
