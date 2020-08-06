---
title: Editor für den Task "WMI-Ereignisüberwachung" (Seite WMI-Optionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatcher.wmiquery.f1
helpviewer_keywords:
- WMI Event Watcher Task Editor
ms.assetid: 525f3de7-a021-4e52-9939-3a83c88f131a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d7d95501f6442df3723261c970c7a90f48cbdc87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718409"
---
# <a name="wmi-event-watcher-task-editor-wmi-options-page"></a><span data-ttu-id="26d9f-102">Editor für den Task 'WMI-Ereignisüberwachung' (Seite WMI-Optionen)</span><span class="sxs-lookup"><span data-stu-id="26d9f-102">WMI Event Watcher Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="26d9f-103">Auf der Seite **WMI-Optionen** des Dialogfelds **Editor für den Task „WMI-Ereignisüberwachung“** können Sie die Quelle der WQL-Abfrage (Windows Management Instrumentation Query Language) und das Verhalten angeben, mit dem der Task „WMI-Ereignisüberwachung“ auf WMI-Ereignisse (Microsoft Windows Instrumentation) antwortet.</span><span class="sxs-lookup"><span data-stu-id="26d9f-103">Use the **WMI Options** page of the **WMI Event Watcher Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and how the WMI Event Watcher task responds to Microsoft Windows Instrumentation (WMI) events.</span></span>  
  
 <span data-ttu-id="26d9f-104">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span><span class="sxs-lookup"><span data-stu-id="26d9f-104">To learn about this task, see [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span></span> <span data-ttu-id="26d9f-105">Weitere Informationen zur WMI Query Language (WQL) finden Sie im Thema zur Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) unter [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045)(Abfragen mit WQL) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="26d9f-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="26d9f-106">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="26d9f-106">Static Options</span></span>  
 <span data-ttu-id="26d9f-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="26d9f-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="26d9f-108">Wählen Sie einen WMI-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New WMI Connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="26d9f-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="26d9f-109">**Verwandte Themen:** [WMI-Verbindungs-Manager](connection-manager/wmi-connection-manager.md), [WMI-Verbindungs-Manager-Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="26d9f-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="26d9f-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="26d9f-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="26d9f-111">Wählen Sie den Quelltyp der WQL-Abfrage aus, die von dem Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26d9f-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="26d9f-112">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="26d9f-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="26d9f-113">Wert</span><span class="sxs-lookup"><span data-stu-id="26d9f-113">Value</span></span>|<span data-ttu-id="26d9f-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26d9f-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26d9f-115">**Direkteingabe**</span><span class="sxs-lookup"><span data-stu-id="26d9f-115">**Direct input**</span></span>|<span data-ttu-id="26d9f-116">Legen Sie die Quelle für eine WQL-Abfrage fest.</span><span class="sxs-lookup"><span data-stu-id="26d9f-116">Set the source to a WQL query.</span></span> <span data-ttu-id="26d9f-117">Bei Auswahl dieses Wertes wird die dynamische Option **WQLQuerySource**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26d9f-117">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="26d9f-118">**Dateiverbindung**</span><span class="sxs-lookup"><span data-stu-id="26d9f-118">**File connection**</span></span>|<span data-ttu-id="26d9f-119">Wählen Sie eine Datei aus, in der die WQL-Abfrage enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="26d9f-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="26d9f-120">Bei Auswahl dieses Wertes wird die dynamische Option **WQLQuerySource**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26d9f-120">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="26d9f-121">**Variable**</span><span class="sxs-lookup"><span data-stu-id="26d9f-121">**Variable**</span></span>|<span data-ttu-id="26d9f-122">Legen Sie die Quelle für eine Variable fest, die die WQL-Abfrage definiert.</span><span class="sxs-lookup"><span data-stu-id="26d9f-122">Set the source to a variable that defines WQL query.</span></span> <span data-ttu-id="26d9f-123">Bei Auswahl dieses Wertes wird die dynamische Option **WQLQuerySource**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26d9f-123">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
  
 <span data-ttu-id="26d9f-124">**ActionAtEvent**</span><span class="sxs-lookup"><span data-stu-id="26d9f-124">**ActionAtEvent**</span></span>  
 <span data-ttu-id="26d9f-125">Geben Sie an, ob das WMI-Ereignis das Ereignis protokolliert und eine [!INCLUDE[ssIS](../includes/ssis-md.md)] -Aktion initiiert oder nur das Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="26d9f-125">Specify whether the WMI event logs the event and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] action, or only logs the event.</span></span>  
  
 <span data-ttu-id="26d9f-126">**AfterEvent**</span><span class="sxs-lookup"><span data-stu-id="26d9f-126">**AfterEvent**</span></span>  
 <span data-ttu-id="26d9f-127">Gibt an, ob der Task nach dem Empfangen des WMI-Ereignisses erfolgreich ausgeführt wird oder fehlschlägt, oder ob die Überwachung des Auftretens dieses Ereignisses durch den Task fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="26d9f-127">Specify whether the task succeeds or fails after it receives the WMI event, or if the task continues watching for the event to occur again.</span></span>  
  
 <span data-ttu-id="26d9f-128">**ActionAtTimeout**</span><span class="sxs-lookup"><span data-stu-id="26d9f-128">**ActionAtTimeout**</span></span>  
 <span data-ttu-id="26d9f-129">Gibt an, ob ein WMI-Abfragetimeout durch den Task protokolliert und als Antwort ein [!INCLUDE[ssIS](../includes/ssis-md.md)] -Ereignis ausgelöst wird, oder ob nur der Timeout protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="26d9f-129">Specify whether the task logs a WMI query time-out and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] event in response, or only logs the time-out.</span></span>  
  
 <span data-ttu-id="26d9f-130">**AfterTimeout**</span><span class="sxs-lookup"><span data-stu-id="26d9f-130">**AfterTimeout**</span></span>  
 <span data-ttu-id="26d9f-131">Gibt an, ob der Task als Antwort auf einen Timeout erfolgreich ausgeführt wird oder fehlschlägt, oder ob der Task die Überwachung fortsetzt, bis ein weiterer Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="26d9f-131">Specify whether the task succeeds or fails in response to a time-out, or if the task continues watching for another time-out to recur.</span></span>  
  
 <span data-ttu-id="26d9f-132">**NumberOfEvents**</span><span class="sxs-lookup"><span data-stu-id="26d9f-132">**NumberOfEvents**</span></span>  
 <span data-ttu-id="26d9f-133">Gibt die Anzahl der zu überwachenden Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="26d9f-133">Specify the number of events to watch for.</span></span>  
  
 <span data-ttu-id="26d9f-134">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="26d9f-134">**Timeout**</span></span>  
 <span data-ttu-id="26d9f-135">Gibt die Zeit in Sekunden an, in der auf das Auftreten des Ereignisses gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="26d9f-135">Specify the number of seconds to wait for the event to occur.</span></span> <span data-ttu-id="26d9f-136">Der Wert 0 bedeutet, dass kein Timeout aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="26d9f-136">A value of 0 means that no time-out is in effect.</span></span>  
  
## <a name="wqlquerysource-dynamic-options"></a><span data-ttu-id="26d9f-137">WQLQuerySource (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="26d9f-137">WQLQuerySource Dynamic Options</span></span>  
  
### <a name="wqlquerysource--direct-input"></a><span data-ttu-id="26d9f-138">WQLQuerySource = Direct input</span><span class="sxs-lookup"><span data-stu-id="26d9f-138">WQLQuerySource = Direct input</span></span>  
 <span data-ttu-id="26d9f-139">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="26d9f-139">**WQLQuerySource**</span></span>  
 <span data-ttu-id="26d9f-140">Stellen Sie eine Abfrage bereit, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten (...), und geben Sie eine Abfrage mithilfe des Dialogfelds **WQL-Abfrage** ein.</span><span class="sxs-lookup"><span data-stu-id="26d9f-140">Provide a query, or click the ellipsis button (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysource--file-connection"></a><span data-ttu-id="26d9f-141">WQLQuerySource = File connection</span><span class="sxs-lookup"><span data-stu-id="26d9f-141">WQLQuerySource = File connection</span></span>  
 <span data-ttu-id="26d9f-142">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="26d9f-142">**WQLQuerySource**</span></span>  
 <span data-ttu-id="26d9f-143">Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="26d9f-143">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="26d9f-144">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="26d9f-144">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysource--variable"></a><span data-ttu-id="26d9f-145">WQLQuerySource = Variable</span><span class="sxs-lookup"><span data-stu-id="26d9f-145">WQLQuerySource = Variable</span></span>  
 <span data-ttu-id="26d9f-146">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="26d9f-146">**WQLQuerySource**</span></span>  
 <span data-ttu-id="26d9f-147">Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="26d9f-147">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="26d9f-148">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="26d9f-148">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d9f-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26d9f-149">See Also</span></span>  
 <span data-ttu-id="26d9f-150">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="26d9f-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="26d9f-151">[Editor für den Task ' WMI-Ereignisüberwachung ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="26d9f-151">[WMI Event Watcher Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="26d9f-152">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="26d9f-152">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="26d9f-153">WMI-Datenleser (Task)</span><span class="sxs-lookup"><span data-stu-id="26d9f-153">WMI Data Reader Task</span></span>](control-flow/wmi-data-reader-task.md)  
  
  
