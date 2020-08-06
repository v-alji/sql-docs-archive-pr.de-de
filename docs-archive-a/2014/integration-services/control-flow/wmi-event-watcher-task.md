---
title: WMI-Ereignisüberwachung (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatchertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Event Watcher task [Integration Services]
ms.assetid: b5bb52e9-a77e-41e1-93f9-d4c3bc6b2c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be20624e5ccdf665e6274f647c342498e9c0f0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724834"
---
# <a name="wmi-event-watcher-task"></a><span data-ttu-id="471cd-102">WMI-Ereignisüberwachung (Task)</span><span class="sxs-lookup"><span data-stu-id="471cd-102">WMI Event Watcher Task</span></span>
  <span data-ttu-id="471cd-103">Der Task "WMI-Ereignisüberwachung" überwacht ein WMI-Ereignis (Windows Management Instrumentation) mithilfe einer WQL-Ereignisabfrage (Windows Management Instrumentation Query Language), um relevante Ereignisse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="471cd-103">The WMI Event Watcher task watches for a Windows Management Instrumentation (WMI) event using a Management Instrumentation Query Language (WQL) event query to specify events of interest.</span></span> <span data-ttu-id="471cd-104">Der Task WMI-Ereignisüberwachung kann für folgende Zwecke verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="471cd-104">You can use the WMI Event Watcher task for the following purposes:</span></span>  
  
-   <span data-ttu-id="471cd-105">Warten auf die Benachrichtigung, dass Dateien einem Ordner hinzugefügt wurden, und dann Initiieren der Dateiverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="471cd-105">Wait for notification that files have been added to a folder and then initiate the processing of the file.</span></span>  
  
-   <span data-ttu-id="471cd-106">Ausführen eines Pakets, mit dem Dateien gelöscht werden, wenn der verfügbare Arbeitsspeicher auf einem Server unter einen angegebenen Prozentsatz sinkt.</span><span class="sxs-lookup"><span data-stu-id="471cd-106">Run a package that deletes files when the available memory on a server drops lower than a specified percentage.</span></span>  
  
-   <span data-ttu-id="471cd-107">Überwachen der Installation einer Anwendung und dann Ausführen eines Pakets, das die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="471cd-107">Watch for installation of an application, and then run a package that uses the application.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="471cd-108">enthält einen Task, der WMI-Informationen liest.</span><span class="sxs-lookup"><span data-stu-id="471cd-108">includes a task that reads WMI information.</span></span>  
  
 <span data-ttu-id="471cd-109">Klicken Sie auf das folgende Thema, um weitere Informationen zu diesem Task zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="471cd-109">For more information about this task, click the following topic:</span></span>  
  
-   [<span data-ttu-id="471cd-110">WMI-Datenleser (Task)</span><span class="sxs-lookup"><span data-stu-id="471cd-110">WMI Data Reader Task</span></span>](wmi-data-reader-task.md)  
  
## <a name="wql-queries"></a><span data-ttu-id="471cd-111">WQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="471cd-111">WQL Queries</span></span>  
 <span data-ttu-id="471cd-112">WQL ist ein Dialekt von SQL mit Erweiterungen zur Unterstützung der WMI-Ereignisbenachrichtigung und sonstigen WMI-spezifischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="471cd-112">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="471cd-113">Weitere Informationen zu WQL finden Sie in der WMI-Dokumentation in der [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="471cd-113">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="471cd-114">Die WMI-Klassen variieren in den verschiedenen Windows-Versionen.</span><span class="sxs-lookup"><span data-stu-id="471cd-114">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="471cd-115">Die folgende Abfrage überwacht die Benachrichtigung, dass die CPU-Nutzung über 40 % beträgt.</span><span class="sxs-lookup"><span data-stu-id="471cd-115">The following query watches for notification that the CPU use is more than 40 percent.</span></span>  
  
```  
SELECT * from __InstanceModificationEvent WITHIN 2 WHERE TargetInstance ISA 'Win32_Processor' and TargetInstance.LoadPercentage > 40  
```  
  
 <span data-ttu-id="471cd-116">Die folgende Abfrage überwacht die Benachrichtigung, dass einem Ordner eine Datei hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="471cd-116">The following query watches for notification that a file has been added to a folder.</span></span>  
  
```  
SELECT * FROM __InstanceCreationEvent WITHIN 10 WHERE TargetInstance ISA "CIM_DirectoryContainsFile" and TargetInstance.GroupComponent= "Win32_Directory.Name=\"c:\\\\WMIFileWatcher\""   
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-event-watcher-task"></a><span data-ttu-id="471cd-117">Verfügbare benutzerdefinierte Meldungen für die Protokollierung für den Task "WMI-Ereignisüberwachung"</span><span class="sxs-lookup"><span data-stu-id="471cd-117">Custom Logging Messages Available on the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="471cd-118">In der folgenden Tabelle werden die benutzerdefinierten Protokolleinträge für den Task WMI-Ereignisüberwachung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="471cd-118">The following table lists the custom log entries for the WMI Event Watcher task.</span></span> <span data-ttu-id="471cd-119">Weitere Informationen finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) und [Benutzerdefinierte Meldungen für die Protokollierung](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="471cd-119">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="471cd-120">Protokolleintrag</span><span class="sxs-lookup"><span data-stu-id="471cd-120">Log entry</span></span>|<span data-ttu-id="471cd-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="471cd-121">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="471cd-122">Zeigt an, dass ein vom Task überwachtes Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="471cd-122">Indicates that an event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="471cd-123">Zeigt an, dass beim Task ein Timeout eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="471cd-123">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="471cd-124">Zeigt an, dass die Ausführung der WQL-Abfrage begonnen wurde.</span><span class="sxs-lookup"><span data-stu-id="471cd-124">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="471cd-125">Der Eintrag schließt die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="471cd-125">The entry includes the query.</span></span>|  
  
## <a name="configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="471cd-126">Konfiguration des Tasks "WMI-Ereignisüberwachung"</span><span class="sxs-lookup"><span data-stu-id="471cd-126">Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="471cd-127">Es gibt folgende Möglichkeiten, um den Task WMI-Datenleser zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="471cd-127">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="471cd-128">Geben Sie den zu verwendenden WMI-Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="471cd-128">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="471cd-129">Geben Sie die Quelle der WQL-Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="471cd-129">Specify the source of the WQL query.</span></span> <span data-ttu-id="471cd-130">Die Quelle kann extern zum Task oder eine Variable bzw. Datei sein, die Abfrage kann aber auch in einer Taskeigenschaft gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="471cd-130">The source can be external to the task, a variable or a file, or the query can be stored in a task property.</span></span>  
  
-   <span data-ttu-id="471cd-131">Geben Sie die Aktion an, die der Task ausführt, wenn das WMI-Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="471cd-131">Specify the action that the task takes when the WMI event occurs.</span></span> <span data-ttu-id="471cd-132">Sie können die Ereignisbenachrichtigung und den Status nach dem Ereignis protokollieren oder benutzerdefinierte [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Ereignisse auslösen, die Informationen zum WMI-Ereignis, zur Benachrichtigung und zum Status nach dem Ereignis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="471cd-132">You can log the event notification and the status after the event, or raise custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] events that provide information associated with the WMI event, the notification, and the status after the event.</span></span>  
  
-   <span data-ttu-id="471cd-133">Definieren Sie, wie der Task auf das Ereignis antwortet.</span><span class="sxs-lookup"><span data-stu-id="471cd-133">Define how the task responds to the event.</span></span> <span data-ttu-id="471cd-134">Der Task kann je nach Ereignis erfolgreich ausgeführt werden oder einen Fehler melden, der Task kann aber auch lediglich das Ereignis erneut überwachen.</span><span class="sxs-lookup"><span data-stu-id="471cd-134">The task can be configured to succeed or fail, depending on the event, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="471cd-135">Geben Sie die Aktion an, die der Task bei einem Timeout der WMI-Abfrage ausführt. Sie können das Timeout und den Status nach dem Timeout protokollieren oder aber ein benutzerdefiniertes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Ereignis mit dem Hinweis, dass beim WMI-Ereignis ein Timeout aufgetreten ist, auslösen und das Timeout und den Timeoutstatus protokollieren.</span><span class="sxs-lookup"><span data-stu-id="471cd-135">Specify the action the task takes when the WMI query times out. You can log the time-out and the status after time-out, or raise a custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] event, indicating that the WMI event timed out and logging the time-out and time-out status.</span></span>  
  
-   <span data-ttu-id="471cd-136">Definieren Sie, wie der Task auf das Timeout antwortet. Der Task kann erfolgreich ausgeführt werden oder einen Fehler melden, der Task kann aber auch lediglich das Ereignis erneut überwachen.</span><span class="sxs-lookup"><span data-stu-id="471cd-136">Define how the task responds to the time-out. The task can be configured to succeed or fail, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="471cd-137">Geben Sie an, wie oft der Task das Ereignis überwacht.</span><span class="sxs-lookup"><span data-stu-id="471cd-137">Specify the number of times the task watches for the event.</span></span>  
  
-   <span data-ttu-id="471cd-138">Geben Sie das Timeout an.</span><span class="sxs-lookup"><span data-stu-id="471cd-138">Specify the time-out.</span></span>  
  
 <span data-ttu-id="471cd-139">Falls die Quelle eine Datei ist, verwendet der Task WMI-Ereignisüberwachung einen Dateiverbindungs-Manager zum Herstellen einer Verbindung mit der Datei.</span><span class="sxs-lookup"><span data-stu-id="471cd-139">If the source is a file, the WMI Event Watcher task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="471cd-140">Weitere Informationen finden Sie unter [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="471cd-140">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="471cd-141">Der Task "WMI-Ereignisüberwachung" verwendet einen WMI-Verbindungs-Manager zum Herstellen einer Verbindung mit dem Server, von dem er WMI-Informationen liest.</span><span class="sxs-lookup"><span data-stu-id="471cd-141">The WMI Event Watcher task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="471cd-142">Weitere Informationen finden Sie unter [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="471cd-142">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
 <span data-ttu-id="471cd-143">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="471cd-143">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="471cd-144">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="471cd-144">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="471cd-145">Editor für den Task „WMI-Ereignisüberwachung“ &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="471cd-145">WMI Event Watcher Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="471cd-146">Editor für den Task „WMI-Ereignisüberwachung“ &#40;Seite „WMI-Optionen“&#41;</span><span class="sxs-lookup"><span data-stu-id="471cd-146">WMI Event Watcher Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-event-watcher-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="471cd-147">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="471cd-147">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="471cd-148">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="471cd-148">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="471cd-149">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="471cd-149">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="471cd-150">Programmgesteuerte Konfiguration des Tasks "WMI-Ereignisüberwachung"</span><span class="sxs-lookup"><span data-stu-id="471cd-150">Programmatic Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="471cd-151">Klicken Sie auf das folgende Thema, um weitere Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="471cd-151">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiEventWatcherTask.WmiEventWatcherTask>  
  
  
