---
title: Editor für den Task ' WMI-Daten Leser ' (Seite WMI-Optionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.wmiquery.f1
helpviewer_keywords:
- WMI Data Reader Task Editor
ms.assetid: 4b8d4716-882d-41b0-b77e-e0e2741a2cd5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfb28e7f8f352f708085bf664757391a05869752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621551"
---
# <a name="wmi-data-reader-task-editor-wmi-options-page"></a><span data-ttu-id="00b3c-102">Editor für den Task 'WMI-Datenleser' (Seite WMI-Optionen)</span><span class="sxs-lookup"><span data-stu-id="00b3c-102">WMI Data Reader Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="00b3c-103">Auf der Seite **WMI-Optionen** des Dialogfelds **Editor für den Task „WMI-Datenleser“** können Sie die Quelle der WQL-Abfrage (Windows Management Instrumentation Query Language) und das Ziel des Abfrageergebnisses angeben.</span><span class="sxs-lookup"><span data-stu-id="00b3c-103">Use the **WMI Options** page of the **WMI Data Reader Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and the destination of the query result.</span></span>  
  
 <span data-ttu-id="00b3c-104">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span><span class="sxs-lookup"><span data-stu-id="00b3c-104">To learn about this task, see [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span></span> <span data-ttu-id="00b3c-105">Weitere Informationen zur WMI Query Language (WQL) finden Sie im Thema zur Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) unter [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045)(Abfragen mit WQL) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="00b3c-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="00b3c-106">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="00b3c-106">Static Options</span></span>  
 <span data-ttu-id="00b3c-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="00b3c-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="00b3c-108">Wählen Sie einen WMI-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New WMI Connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="00b3c-109">**Verwandte Themen:** [WMI-Verbindungs-Manager](connection-manager/wmi-connection-manager.md), [WMI-Verbindungs-Manager-Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="00b3c-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="00b3c-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="00b3c-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="00b3c-111">Wählen Sie den Quelltyp der WQL-Abfrage aus, die von dem Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="00b3c-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="00b3c-112">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="00b3c-113">Wert</span><span class="sxs-lookup"><span data-stu-id="00b3c-113">Value</span></span>|<span data-ttu-id="00b3c-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="00b3c-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="00b3c-115">**Direkteingabe**</span><span class="sxs-lookup"><span data-stu-id="00b3c-115">**Direct input**</span></span>|<span data-ttu-id="00b3c-116">Legen Sie die Quelle für eine WQL-Abfrage fest.</span><span class="sxs-lookup"><span data-stu-id="00b3c-116">Set the source to a WQL query.</span></span> <span data-ttu-id="00b3c-117">Bei Auswahl dieses Werts wird die dynamische Option **WQLQuerySourceType**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b3c-117">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="00b3c-118">**Dateiverbindung**</span><span class="sxs-lookup"><span data-stu-id="00b3c-118">**File connection**</span></span>|<span data-ttu-id="00b3c-119">Wählen Sie eine Datei aus, in der die WQL-Abfrage enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="00b3c-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="00b3c-120">Bei Auswahl dieses Werts wird die dynamische Option **WQLQuerySourceType**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b3c-120">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="00b3c-121">**Variable**</span><span class="sxs-lookup"><span data-stu-id="00b3c-121">**Variable**</span></span>|<span data-ttu-id="00b3c-122">Legen Sie die Quelle für eine Variable fest, die die WQL-Abfrage definiert.</span><span class="sxs-lookup"><span data-stu-id="00b3c-122">Set the source to a variable that defines the WQL query.</span></span> <span data-ttu-id="00b3c-123">Bei Auswahl dieses Werts wird die dynamische Option **WQLQuerySourceType**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b3c-123">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
  
 <span data-ttu-id="00b3c-124">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="00b3c-124">**OutputType**</span></span>  
 <span data-ttu-id="00b3c-125">Geben Sie an, ob es sich bei der Ausgabe um eine Datentabelle, einen Eigenschaftswert oder einen Eigenschaftsnamen und -wert handeln soll.</span><span class="sxs-lookup"><span data-stu-id="00b3c-125">Specify whether the output should be a data table, property value, or property name and value.</span></span>  
  
 <span data-ttu-id="00b3c-126">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="00b3c-126">**OverwriteDestination**</span></span>  
 <span data-ttu-id="00b3c-127">Gibt an, ob die ursprünglichen Daten in der Zieldatei oder -variablen beibehalten, überschrieben oder an diese angefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-127">Specifies whether to keep, overwrite, or append to the original data in the destination file or variable.</span></span>  
  
 <span data-ttu-id="00b3c-128">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="00b3c-128">**DestinationType**</span></span>  
 <span data-ttu-id="00b3c-129">Wählen Sie den Zieltyp der WQL-Abfrage aus, die von dem Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="00b3c-129">Select the destination type of the WQL query that the task runs.</span></span> <span data-ttu-id="00b3c-130">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-130">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="00b3c-131">Wert</span><span class="sxs-lookup"><span data-stu-id="00b3c-131">Value</span></span>|<span data-ttu-id="00b3c-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="00b3c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="00b3c-133">**Dateiverbindung**</span><span class="sxs-lookup"><span data-stu-id="00b3c-133">**File connection**</span></span>|<span data-ttu-id="00b3c-134">Wählen Sie eine Datei aus, um die Ergebnisse der WQL-Abfrage darin zu speichern.</span><span class="sxs-lookup"><span data-stu-id="00b3c-134">Select a file to save the results of the WQL query in.</span></span> <span data-ttu-id="00b3c-135">Bei Auswahl dieses Werts wird die dynamische Option **DestinationType**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b3c-135">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
|<span data-ttu-id="00b3c-136">**Variable**</span><span class="sxs-lookup"><span data-stu-id="00b3c-136">**Variable**</span></span>|<span data-ttu-id="00b3c-137">Legen Sie die Variable fest, um die Ergebnisse der WQL-Abfrage darin zu speichern.</span><span class="sxs-lookup"><span data-stu-id="00b3c-137">Set the variable to store the results of the WQL query in.</span></span> <span data-ttu-id="00b3c-138">Bei Auswahl dieses Werts wird die dynamische Option **DestinationType**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00b3c-138">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
  
## <a name="wqlquerysourcetype-dynamic-options"></a><span data-ttu-id="00b3c-139">Dynamische Optionen von WQLQuerySourceType</span><span class="sxs-lookup"><span data-stu-id="00b3c-139">WQLQuerySourceType Dynamic Options</span></span>  
  
### <a name="wqlquerysourcetype--direct-input"></a><span data-ttu-id="00b3c-140">WQLQuerySourceType = Direct input</span><span class="sxs-lookup"><span data-stu-id="00b3c-140">WQLQuerySourceType = Direct input</span></span>  
 <span data-ttu-id="00b3c-141">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="00b3c-141">**WQLQuerySource**</span></span>  
 <span data-ttu-id="00b3c-142">Stellen Sie eine Abfrage bereit, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten (...), und geben Sie eine Abfrage mithilfe des Dialogfelds **WQL-Abfrage** ein.</span><span class="sxs-lookup"><span data-stu-id="00b3c-142">Provide a query, or click the ellipsis (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysourcetype--file-connection"></a><span data-ttu-id="00b3c-143">WQLQuerySourceType = File connection</span><span class="sxs-lookup"><span data-stu-id="00b3c-143">WQLQuerySourceType = File connection</span></span>  
 <span data-ttu-id="00b3c-144">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="00b3c-144">**WQLQuerySource**</span></span>  
 <span data-ttu-id="00b3c-145">Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-145">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="00b3c-146">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="00b3c-146">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysourcetype--variable"></a><span data-ttu-id="00b3c-147">WQLQuerySourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="00b3c-147">WQLQuerySourceType = Variable</span></span>  
 <span data-ttu-id="00b3c-148">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="00b3c-148">**WQLQuerySource**</span></span>  
 <span data-ttu-id="00b3c-149">Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-149">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="00b3c-150">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="00b3c-150">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="destinationtype-dynamic-options"></a><span data-ttu-id="00b3c-151">Dynamische Optionen von DestinationType</span><span class="sxs-lookup"><span data-stu-id="00b3c-151">DestinationType Dynamic Options</span></span>  
  
### <a name="destinationtype--file-connection"></a><span data-ttu-id="00b3c-152">DestinationType = File connection</span><span class="sxs-lookup"><span data-stu-id="00b3c-152">DestinationType = File connection</span></span>  
 <span data-ttu-id="00b3c-153">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="00b3c-153">**Destination**</span></span>  
 <span data-ttu-id="00b3c-154">Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-154">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="00b3c-155">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="00b3c-155">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="destinationtype--variable"></a><span data-ttu-id="00b3c-156">DestinationType = Variable</span><span class="sxs-lookup"><span data-stu-id="00b3c-156">DestinationType = Variable</span></span>  
 <span data-ttu-id="00b3c-157">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="00b3c-157">**Destination**</span></span>  
 <span data-ttu-id="00b3c-158">Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00b3c-158">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="00b3c-159">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="00b3c-159">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b3c-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00b3c-160">See Also</span></span>  
 <span data-ttu-id="00b3c-161">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="00b3c-161">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="00b3c-162">[Editor für den Task ' WMI-Daten Leser ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="00b3c-162">[WMI Data Reader Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="00b3c-163">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="00b3c-163">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="00b3c-164">WMI-Ereignisüberwachung (Task)</span><span class="sxs-lookup"><span data-stu-id="00b3c-164">WMI Event Watcher Task</span></span>](control-flow/wmi-event-watcher-task.md)  
  
  
