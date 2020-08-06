---
title: Ziel-Editor für Partitions Verarbeitung (Seite erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12845ecd644eabd949ea37fbb18ba6cc9cf342f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609299"
---
# <a name="partition-processing-destination-editor-advanced-page"></a><span data-ttu-id="ed72c-102">Ziel-Editor für Partitionsverarbeitung (Seite Erweitert)</span><span class="sxs-lookup"><span data-stu-id="ed72c-102">Partition Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="ed72c-103">Auf der Seite **Erweitert** des Dialogfelds **Ziel-Editor für Partitionsverarbeitung** konfigurieren Sie die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="ed72c-103">Use the **Advanced** page of the **Partition Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="ed72c-104">Weitere Informationen zum Ziel für Partitionsverarbeitung finden Sie unter [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ed72c-104">To learn more about the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed72c-105">Hier beschriebene Tasks gelten nicht für tabellarische Analysis Services-Modelle.</span><span class="sxs-lookup"><span data-stu-id="ed72c-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="ed72c-106">Sie können Partitionsspalten für tabellarische Modelle keine Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ed72c-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="ed72c-107">Sie können stattdessen den Analysis Services-Task "DDL ausführen" [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) verwenden, um die Partition zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed72c-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ed72c-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ed72c-108">Options</span></span>  
 <span data-ttu-id="ed72c-109">**Standardfehlerkonfiguration verwenden**</span><span class="sxs-lookup"><span data-stu-id="ed72c-109">**Use default error configuration.**</span></span>  
 <span data-ttu-id="ed72c-110">Gibt an, ob die Standardfehlerbehandlung von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed72c-110">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="ed72c-111">Standardmäßig ist dieser Wert auf `True` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ed72c-111">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="ed72c-112">**Schlüsselfehler Aktion**</span><span class="sxs-lookup"><span data-stu-id="ed72c-112">**Key error action**</span></span>  
 <span data-ttu-id="ed72c-113">Gibt an, wie Datensätze behandelt werden, die unzulässige Schlüsselwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ed72c-113">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="ed72c-114">Wert</span><span class="sxs-lookup"><span data-stu-id="ed72c-114">Value</span></span>|<span data-ttu-id="ed72c-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed72c-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed72c-116">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="ed72c-116">**ConvertToUnknown**</span></span>|<span data-ttu-id="ed72c-117">Konvertiert den unzulässigen Schlüsselwert in den Wert Unknown.</span><span class="sxs-lookup"><span data-stu-id="ed72c-117">Convert the unacceptable key value to the Unknown value.</span></span>|  
|<span data-ttu-id="ed72c-118">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="ed72c-118">**DiscardRecord**</span></span>|<span data-ttu-id="ed72c-119">Verwirft den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="ed72c-119">Discard the record.</span></span>|  
  
 <span data-ttu-id="ed72c-120">**Fehler ignorieren**</span><span class="sxs-lookup"><span data-stu-id="ed72c-120">**Ignore errors**</span></span>  
 <span data-ttu-id="ed72c-121">Gibt an, dass Fehler ignoriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed72c-121">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="ed72c-122">**Bei Fehler abbrechen**</span><span class="sxs-lookup"><span data-stu-id="ed72c-122">**Stop on error**</span></span>  
 <span data-ttu-id="ed72c-123">Gibt an, dass die Verarbeitung beendet werden soll, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ed72c-123">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="ed72c-124">**Anzahl von Fehlern**</span><span class="sxs-lookup"><span data-stu-id="ed72c-124">**Number of errors**</span></span>  
 <span data-ttu-id="ed72c-125">Gibt den Schwellenwert für die Anzahl von Fehlern an, ab dem die Verarbeitung beendet werden soll, wenn Sie **Bei Fehler beenden**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ed72c-125">Specify the error threshold at which processing should stop, if you have selected **Stop on error**.</span></span>  
  
 <span data-ttu-id="ed72c-126">**Aktion bei Fehler**</span><span class="sxs-lookup"><span data-stu-id="ed72c-126">**On error action**</span></span>  
 <span data-ttu-id="ed72c-127">Gibt die Aktion an, die bei Erreichen des Fehlerschwellenwerts ausgeführt wird, wenn Sie **Bei Fehler beenden**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ed72c-127">Specify the action to take when the error threshold is reached, if you have selected **Stop on error**.</span></span>  
  
|<span data-ttu-id="ed72c-128">Wert</span><span class="sxs-lookup"><span data-stu-id="ed72c-128">Value</span></span>|<span data-ttu-id="ed72c-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed72c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed72c-130">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="ed72c-130">**StopProcessing**</span></span>|<span data-ttu-id="ed72c-131">Beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="ed72c-131">Stop processing.</span></span>|  
|<span data-ttu-id="ed72c-132">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="ed72c-132">**StopLogging**</span></span>|<span data-ttu-id="ed72c-133">Beendet das Protokollieren der Fehler.</span><span class="sxs-lookup"><span data-stu-id="ed72c-133">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="ed72c-134">**Schlüssel nicht gefunden**</span><span class="sxs-lookup"><span data-stu-id="ed72c-134">**Key not found**</span></span>  
 <span data-ttu-id="ed72c-135">Gibt die Aktion an, die beim Fehler Schlüssel nicht gefunden ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed72c-135">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="ed72c-136">Standardmäßig ist dieser Wert **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="ed72c-136">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="ed72c-137">Wert</span><span class="sxs-lookup"><span data-stu-id="ed72c-137">Value</span></span>|<span data-ttu-id="ed72c-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed72c-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed72c-139">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="ed72c-139">**IgnoreError**</span></span>|<span data-ttu-id="ed72c-140">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-140">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-141">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="ed72c-141">**ReportAndContinue**</span></span>|<span data-ttu-id="ed72c-142">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-142">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-143">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="ed72c-143">**ReportAndStop**</span></span>|<span data-ttu-id="ed72c-144">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="ed72c-144">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ed72c-145">**Doppelter Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="ed72c-145">**Duplicate key**</span></span>  
 <span data-ttu-id="ed72c-146">Gibt die Aktion an, die beim Fehler Doppelter Schlüssel ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed72c-146">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="ed72c-147">Standardmäßig ist dieser Wert **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="ed72c-147">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="ed72c-148">Wert</span><span class="sxs-lookup"><span data-stu-id="ed72c-148">Value</span></span>|<span data-ttu-id="ed72c-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed72c-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed72c-150">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="ed72c-150">**IgnoreError**</span></span>|<span data-ttu-id="ed72c-151">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-151">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-152">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="ed72c-152">**ReportAndContinue**</span></span>|<span data-ttu-id="ed72c-153">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-153">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-154">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="ed72c-154">**ReportAndStop**</span></span>|<span data-ttu-id="ed72c-155">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="ed72c-155">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ed72c-156">**NULL-Schlüssel in unbekanntes konvertiert**</span><span class="sxs-lookup"><span data-stu-id="ed72c-156">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="ed72c-157">Gibt die Aktion an, die ausgeführt werden soll, wenn ein NULL-Schlüssel in den Wert Unknown konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ed72c-157">Specify the action to take when a null key has been converted to the Unknown value.</span></span> <span data-ttu-id="ed72c-158">Standardmäßig ist dieser Wert **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="ed72c-158">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="ed72c-159">Wert</span><span class="sxs-lookup"><span data-stu-id="ed72c-159">Value</span></span>|<span data-ttu-id="ed72c-160">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed72c-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed72c-161">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="ed72c-161">**IgnoreError**</span></span>|<span data-ttu-id="ed72c-162">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-162">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-163">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="ed72c-163">**ReportAndContinue**</span></span>|<span data-ttu-id="ed72c-164">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-164">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-165">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="ed72c-165">**ReportAndStop**</span></span>|<span data-ttu-id="ed72c-166">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="ed72c-166">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ed72c-167">**NULL-Schlüssel nicht zulässig**</span><span class="sxs-lookup"><span data-stu-id="ed72c-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="ed72c-168">Gibt die Aktion an, die ausgeführt wird, wenn NULL-Schlüssel unzulässig sind und ein NULL-Schlüssel entdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed72c-168">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="ed72c-169">Standardmäßig ist dieser Wert **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="ed72c-169">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="ed72c-170">Wert</span><span class="sxs-lookup"><span data-stu-id="ed72c-170">Value</span></span>|<span data-ttu-id="ed72c-171">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed72c-171">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed72c-172">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="ed72c-172">**IgnoreError**</span></span>|<span data-ttu-id="ed72c-173">Ignoriert den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-173">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-174">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="ed72c-174">**ReportAndContinue**</span></span>|<span data-ttu-id="ed72c-175">Berichtet den Fehler, und setzt die Verarbeitung fort.</span><span class="sxs-lookup"><span data-stu-id="ed72c-175">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ed72c-176">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="ed72c-176">**ReportAndStop**</span></span>|<span data-ttu-id="ed72c-177">Berichtet den Fehler, und beendet die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="ed72c-177">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ed72c-178">**Fehlerprotokollpfad**</span><span class="sxs-lookup"><span data-stu-id="ed72c-178">**Error log path**</span></span>  
 <span data-ttu-id="ed72c-179">Geben Sie den Pfad für das Fehlerprotokoll ein, oder wählen Sie mit der Schaltfläche **Durchsuchen (...)** ein Ziel aus.</span><span class="sxs-lookup"><span data-stu-id="ed72c-179">Type the path for the error log, or select a destination by using the browse **(...)** button.</span></span>  
  
 <span data-ttu-id="ed72c-180">**Durchsuchen (…)**</span><span class="sxs-lookup"><span data-stu-id="ed72c-180">**Browse (...)**</span></span>  
 <span data-ttu-id="ed72c-181">Wählen Sie einen Pfad für das Fehlerprotokoll aus.</span><span class="sxs-lookup"><span data-stu-id="ed72c-181">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed72c-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed72c-182">See Also</span></span>  
 <span data-ttu-id="ed72c-183">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ed72c-183">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ed72c-184">Ziel-Editor für Partitionsverarbeitung &#40;Seite Zuordnungen&#41;</span><span class="sxs-lookup"><span data-stu-id="ed72c-184">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
