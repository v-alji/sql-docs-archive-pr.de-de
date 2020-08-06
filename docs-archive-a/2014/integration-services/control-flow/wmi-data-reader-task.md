---
title: WMI-Datenleser (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Data Reader task [Integration Services]
ms.assetid: dae57067-0275-4ac3-8f34-1b9d169f1112
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d2f16a28e8b6c94c7275468dedb6d2dfec76d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609997"
---
# <a name="wmi-data-reader-task"></a><span data-ttu-id="10f45-102">WMI-Datenleser (Task)</span><span class="sxs-lookup"><span data-stu-id="10f45-102">WMI Data Reader Task</span></span>
  <span data-ttu-id="10f45-103">Der Task WMI-Datenleser führt Abfragen mithilfe von WQL (WMI Query Language) aus, womit Informationen von WMI zu einem Computersystem zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="10f45-103">The WMI Data Reader task runs queries using the Windows Management Instrumentation (WMI) Query Language that returns information from WMI about a computer system.</span></span> <span data-ttu-id="10f45-104">Der Task WMI-Datenleser kann für folgende Zwecke verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="10f45-104">You can use the WMI Data Reader task for the following purposes:</span></span>  
  
-   <span data-ttu-id="10f45-105">Abfragen der Windows-Ereignisprotokolle auf einem lokalen Computer oder einem Remotecomputer und Schreiben der Informationen in eine Datei oder Variable.</span><span class="sxs-lookup"><span data-stu-id="10f45-105">Query the Windows event logs on a local or remote computer and write the information to a file or variable.</span></span>  
  
-   <span data-ttu-id="10f45-106">Abrufen von Informationen zum Vorhandensein, zum Status oder zu Eigenschaften von Hardwarekomponenten und Ermitteln mithilfe dieser Informationen, ob andere Tasks in der Ablaufsteuerung ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="10f45-106">Obtain information about the presence, state, or properties of hardware components, and then use this information to determine whether other tasks in the control flow should run.</span></span>  
  
-   <span data-ttu-id="10f45-107">Abrufen einer Liste der Anwendungen und Ermitteln der installierten Version jeder Anwendung.</span><span class="sxs-lookup"><span data-stu-id="10f45-107">Get a list of applications and determine what version of each application is installed.</span></span>  
  
 <span data-ttu-id="10f45-108">Es gibt folgende Möglichkeiten, um den Task WMI-Datenleser zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="10f45-108">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="10f45-109">Geben Sie den zu verwendenden WMI-Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="10f45-109">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="10f45-110">Geben Sie die Quelle der WQL-Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="10f45-110">Specify the source of the WQL query.</span></span> <span data-ttu-id="10f45-111">Die Abfrage kann in einer Taskeigenschaft gespeichert sein, die Abfrage kann aber auch außerhalb des Tasks in einer Variablen oder einer Datei gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="10f45-111">The query can be stored in a task property, or the query can be stored outside the task, in a variable or a file.</span></span>  
  
-   <span data-ttu-id="10f45-112">Definieren Sie das Format der WQL-Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="10f45-112">Define the format of the WQL query results.</span></span> <span data-ttu-id="10f45-113">Der Task unterstützt ein Tabellen-, Eigenschaftsname/Wert-Paar- oder Eigenschaftswertformat.</span><span class="sxs-lookup"><span data-stu-id="10f45-113">The task supports a table, property name/value pair, or property value format.</span></span>  
  
-   <span data-ttu-id="10f45-114">Geben Sie das Ziel der Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="10f45-114">Specify the destination of the query.</span></span> <span data-ttu-id="10f45-115">Das Ziel kann eine Variable oder eine Datei sein.</span><span class="sxs-lookup"><span data-stu-id="10f45-115">The destination can be a variable or a file.</span></span>  
  
-   <span data-ttu-id="10f45-116">Geben Sie an, ob das Abfrageziel überschrieben, beibehalten oder angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="10f45-116">Indicate whether the query destination is overwritten, kept, or appended.</span></span>  
  
 <span data-ttu-id="10f45-117">Falls es sich bei der Quelle oder dem Ziel um eine Datei handelt, verwendet der Task WMI-Datenleser einen Dateiverbindungs-Manager zum Herstellen einer Verbindung mit der Datei.</span><span class="sxs-lookup"><span data-stu-id="10f45-117">If the source or destination is a file, the WMI Data Reader task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="10f45-118">Weitere Informationen finden Sie unter [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="10f45-118">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="10f45-119">Der Task WMI-Datenleser verwendet einen WMI-Verbindungs-Manager zum Herstellen einer Verbindung mit dem Server, von dem er WMI-Informationen liest.</span><span class="sxs-lookup"><span data-stu-id="10f45-119">The WMI Data Reader task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="10f45-120">Weitere Informationen finden Sie unter [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="10f45-120">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="wql-query"></a><span data-ttu-id="10f45-121">WQL-Abfrage</span><span class="sxs-lookup"><span data-stu-id="10f45-121">WQL Query</span></span>  
 <span data-ttu-id="10f45-122">WQL ist ein Dialekt von SQL mit Erweiterungen zur Unterstützung der WMI-Ereignisbenachrichtigung und sonstigen WMI-spezifischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="10f45-122">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="10f45-123">Weitere Informationen zu WQL finden Sie in der WMI-Dokumentation in der [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span><span class="sxs-lookup"><span data-stu-id="10f45-123">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10f45-124">Die WMI-Klassen variieren in den verschiedenen Windows-Versionen.</span><span class="sxs-lookup"><span data-stu-id="10f45-124">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="10f45-125">Die folgende WQL-Abfrage gibt Einträge aus dem Anwendungsereignisprotokoll zurück.</span><span class="sxs-lookup"><span data-stu-id="10f45-125">The following WQL query returns entries in the Application log event.</span></span>  
  
```  
SELECT * FROM Win32_NTLogEvent WHERE LogFile = 'Application' AND (SourceName='SQLISService' OR SourceName='SQLISPackage') AND TimeGenerated > '20050117'  
```  
  
 <span data-ttu-id="10f45-126">Die folgende WQL-Abfrage gibt Informationen zum logischen Datenträger zurück.</span><span class="sxs-lookup"><span data-stu-id="10f45-126">The following WQL query returns logical disk information.</span></span>  
  
```  
SELECT FreeSpace, DeviceId, Size, SystemName, Description FROM Win32_LlogicalDisk  
```  
  
 <span data-ttu-id="10f45-127">Die folgende WQL-Abfrage gibt eine Liste der QFE-Updates (Quick Fix Engineering) für das Betriebssystem zurück.</span><span class="sxs-lookup"><span data-stu-id="10f45-127">The following WQL query returns a list of the quick fix engineering (QFE) updates to the operating system.</span></span>  
  
```  
Select * FROM Win32_QuickFixEngineering  
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-data-reader-task"></a><span data-ttu-id="10f45-128">Verfügbare benutzerdefinierte Meldungen für die Protokollierung für den Task 'WMI-Datenleser'</span><span class="sxs-lookup"><span data-stu-id="10f45-128">Custom Logging Messages Available on the WMI Data Reader Task</span></span>  
 <span data-ttu-id="10f45-129">In der folgenden Tabelle werden die benutzerdefinierten Protokolleinträge für den Task WMI-Datenleser aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="10f45-129">The following table lists the custom log entries for the WMI Data Reader task.</span></span> <span data-ttu-id="10f45-130">Weitere Informationen finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) und [Benutzerdefinierte Meldungen für die Protokollierung](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="10f45-130">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="10f45-131">Protokolleintrag</span><span class="sxs-lookup"><span data-stu-id="10f45-131">Log entry</span></span>|<span data-ttu-id="10f45-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10f45-132">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="10f45-133">Zeigt an, dass das Lesen der WMI-Daten begonnen wurde.</span><span class="sxs-lookup"><span data-stu-id="10f45-133">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="10f45-134">Berichtet die vom Task ausgeführte WQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="10f45-134">Reports the WQL query that the task ran.</span></span>|  
  
## <a name="configuration-of-the-wmi-data-reader-task"></a><span data-ttu-id="10f45-135">Konfiguration des Tasks "WMI-Datenleser"</span><span class="sxs-lookup"><span data-stu-id="10f45-135">Configuration of the WMI Data Reader Task</span></span>  
 <span data-ttu-id="10f45-136">Eigenschaften können Sie programmgesteuert oder mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="10f45-136">You can set properties programmatically or through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="10f45-137">Klicken Sie auf eines der folgenden Themen, um Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="10f45-137">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="10f45-138">Editor für den Task „WMI-Datenleser“ &#40;Seite WMI-Optionen&#41;</span><span class="sxs-lookup"><span data-stu-id="10f45-138">WMI Data Reader Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-data-reader-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="10f45-139">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="10f45-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="10f45-140">Klicken Sie auf das folgende Thema, um Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="10f45-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiDataReaderTask.WmiDataReaderTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="10f45-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="10f45-141">Related Tasks</span></span>  
 <span data-ttu-id="10f45-142">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="10f45-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="10f45-143">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="10f45-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="10f45-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10f45-144">See Also</span></span>  
 <span data-ttu-id="10f45-145">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="10f45-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="10f45-146">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="10f45-146">Control Flow</span></span>](control-flow.md)  
  
  
