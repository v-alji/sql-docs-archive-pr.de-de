---
title: Erstellen einer Ablaufverfolgung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], example
- traces [SQL Server], creating
ms.assetid: 79dd4254-e3c6-467a-bb6f-f99e51757e99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 35644891b2dca8359d6dc68fbddb67288d241cb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619049"
---
# <a name="create-a-trace-transact-sql"></a><span data-ttu-id="10746-102">Erstellen einer Ablaufverfolgung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="10746-102">Create a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="10746-103">In diesem Thema werden Vorgehensweisen zum Verwenden gespeicherter Prozeduren zum Erstellen einer Ablaufverfolgung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10746-103">This topic describes how to use stored procedures to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="10746-104">So erstellen Sie eine Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="10746-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="10746-105">Führen Sie **sp_trace_create** mit den notwendigen Parametern aus, um eine neue Ablaufverfolgung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10746-105">Execute **sp_trace_create** with the required parameters to create a new trace.</span></span> <span data-ttu-id="10746-106">Der Status der neuen Ablaufverfolgung besagt, dass sie beendet ist (*Status* ist **0**).</span><span class="sxs-lookup"><span data-stu-id="10746-106">The new trace will be in a stopped state (*status* is **0**).</span></span>  
  
2.  <span data-ttu-id="10746-107">Führen Sie **sp_trace_setevent** mit den notwendigen Parametern aus, um die zu verfolgenden Ereignisse und Spalten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="10746-107">Execute **sp_trace_setevent** with the required parameters to select the events and columns to trace.</span></span>  
  
3.  <span data-ttu-id="10746-108">Führen Sie wahlweise **sp_trace_setfilter** aus, um beliebige Filter oder eine Kombination aus Filtern festzulegen.</span><span class="sxs-lookup"><span data-stu-id="10746-108">Optionally, execute **sp_trace_setfilter** to set any or a combination of filters.</span></span>  
  
     <span data-ttu-id="10746-109">**sp_trace_setevent** und **sp_trace_setfilter** können nur für vorhandene, beendete Ablaufverfolgungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="10746-109">**sp_trace_setevent** and **sp_trace_setfilter** can be executed only on existing traces that are stopped.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="10746-110">Im Gegensatz zu regulären gespeicherten Prozeduren werden die Parameter für alle gespeicherten Prozeduren von SQL Server Profiler (<strong>sp_trace_*xx*</strong>) genau eingegeben und unterstützen die automatische Datentypkonvertierung nicht.</span><span class="sxs-lookup"><span data-stu-id="10746-110">Unlike regular stored procedures, parameters of all SQL Server Profiler stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="10746-111">Wenn diese Parameter nicht mit den richtigen Datentypen für Eingabeparameter aufgerufen werden, wie in der Argumentbeschreibung angegeben, gibt die gespeicherte Prozedur einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="10746-111">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10746-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10746-112">Example</span></span>  
 <span data-ttu-id="10746-113">Im folgenden Code wird das Erstellen einer Ablaufverfolgung mit [!INCLUDE[tsql](../../includes/tsql-md.md)]veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="10746-113">The following code demonstrates creating a trace using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="10746-114">Der Code ist in drei Abschnitte unterteilt: Erstellen der Ablaufverfolgung, Auffüllen der Ablaufverfolgungsdatei und Beenden der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="10746-114">It is in three sections: creating the trace, populating the trace file, and stopping the trace.</span></span> <span data-ttu-id="10746-115">Passen Sie die Ablaufverfolgung an, indem Sie die Ereignisse hinzufügen, die Sie aufzeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="10746-115">Customize the trace by adding the events that you want to trace.</span></span> <span data-ttu-id="10746-116">Die Liste der Ereignisse und Spalten finden Sie unter [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="10746-116">For the list of events and columns, see [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span></span>  
  
 <span data-ttu-id="10746-117">Mit dem folgenden Code wird eine Ablaufverfolgung erstellt, anschließend werden dieser Ereignisse hinzugefügt, und sie wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="10746-117">The following code creates a trace, adds events to the trace, and then starts the trace:</span></span>  
  
```  
DECLARE @RC int, @TraceID int, @on BIT  
EXEC @rc = sp_trace_create @TraceID output, 0, N'C:\SampleTrace'  
  
-- Select the return code to see if the trace creation was successful.  
SELECT RC = @RC, TraceID = @TraceID  
  
-- Set the events and data columns you need to capture.  
SELECT @on = 1  
  
-- 10 is RPC:Completed event. 1 is TextData column.   
EXEC sp_trace_setevent @TraceID, 10, 1, @on   
-- 13 is SQL:BatchStarting, 11 is LoginName  
EXEC sp_trace_setevent @TraceID, 13, 11, @on   
-- 13 is SQL:BatchStarting, 14 is StartTime  
EXEC sp_trace_setevent @TraceID, 13, 14, @on   
-- 12 is SQL:BatchCompleted, 15 is EndTime  
EXEC sp_trace_setevent @TraceID, 12, 15, @on   
-- 13 is SQL:BatchStarting, 1 is TextData  
EXEC sp_trace_setevent @TraceID, 13, 1, @on   
  
-- Set any filter. Not provided in this example  
--EXEC sp_trace_setfilter 1, 10, 0, 6, N'%Profiler%'  
  
-- Start Trace (status 1 = start)  
EXEC @RC = sp_trace_setstatus @TraceID, 1  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="10746-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10746-118">Example</span></span>  
 <span data-ttu-id="10746-119">Nachdem nun die Ablaufverfolgung erstellt und gestartet worden ist, führen Sie den folgenden Code aus, um die Ablaufverfolgung mit Aktivität aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="10746-119">Now that the trace has been created and started, execute the following code to populate the trace with activity.</span></span>  
  
```  
SELECT * FROM master.sys.databases  
GO  
SELECT * FROM ::fn_trace_getinfo(default)  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="10746-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10746-120">Example</span></span>  
 <span data-ttu-id="10746-121">Die Ablaufverfolgung kann jederzeit beendet und neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="10746-121">The trace can be stopped and restarted at any time.</span></span> <span data-ttu-id="10746-122">Führen Sie in diesem Beispiel den folgenden Code aus, um die Ablaufverfolgung zu beenden und zu schließen und die Ablaufverfolgungsdefinition zu löschen.</span><span class="sxs-lookup"><span data-stu-id="10746-122">In this example, execute the following code to stop the trace, close the trace, and delete the trace definition.</span></span>  
  
```  
DECLARE @TraceID int  
-- Populate a variable with the trace_id of the current trace  
SELECT  @TraceID = TraceID FROM ::fn_trace_getinfo(default) WHERE VALUE = N'C:\SampleTrace.trc'  
  
-- First stop the trace.   
EXEC sp_trace_setstatus @TraceID, 0  
  
-- Close and then delete its definition from SQL Server.   
EXEC sp_trace_setstatus @TraceID, 2  
  
```  
  
## <a name="example"></a><span data-ttu-id="10746-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10746-123">Example</span></span>  
 <span data-ttu-id="10746-124">Öffnen Sie zum Untersuchen der Ablaufverfolgungsdatei die Datei SampleTrace.trc mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10746-124">To examine the trace file, open the SampleTrace.trc file using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10746-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10746-125">See Also</span></span>  
 <span data-ttu-id="10746-126">[Gespeicherte Prozeduren von SQL Server Profiler &#40;SQL Server Profiler&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10746-126">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="10746-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10746-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="10746-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10746-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="10746-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="10746-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)  
  
  
