---
title: Überwachen der Leistung von systemintern kompilierten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 55548cb2-77a8-4953-8b5a-f2778a4f13cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d14d27cdc20c0f090c7a030efe05cfce4842f437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725749"
---
# <a name="monitoring-performance-of-natively-compiled-stored-procedures"></a><span data-ttu-id="639df-102">Überwachen der Leistung von systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="639df-102">Monitoring Performance of Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="639df-103">In diesem Thema wird erläutert, wie Sie die Leistung von systemintern kompilierten gespeicherten Prozeduren überwachen können.</span><span class="sxs-lookup"><span data-stu-id="639df-103">This topic discusses how you can monitor the performance of natively compiled stored procedures</span></span>  
  
## <a name="using-extended-events"></a><span data-ttu-id="639df-104">Unter Verwendung erweiterter Ereignisse</span><span class="sxs-lookup"><span data-stu-id="639df-104">Using Extended Events</span></span>  
 <span data-ttu-id="639df-105">Verwenden Sie das erweiterte Ereignis `sp_statement_completed`, um die Ausführung einer Abfrage zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="639df-105">Use the `sp_statement_completed` extended event to trace execution of a query.</span></span> <span data-ttu-id="639df-106">Erstellen Sie eine Sitzung für erweiterte Ereignisse mit diesem Ereignis. Optional können Sie für eine bestimmte systemintern kompilierte gespeicherte Prozedur nach object_id filtern. Das erweiterte Ereignis wird nach der Ausführung jeder Abfrage ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="639df-106">Create an extended event session with this event, optionally with a filter on object_id for a particular natively compiled stored procedure, The extended event is raised after the execution of each query.</span></span> <span data-ttu-id="639df-107">Die vom erweiterten Ereignis angegebene CPU-Zeit und Dauer geben an, wie lange die CPU genutzt und wie lange die Abfrage ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="639df-107">The CPU time and duration reported by the extended event indicate how much CPU the query used and the execution time.</span></span> <span data-ttu-id="639df-108">Bei einer systemintern kompilierten gespeicherten Prozedur, die viel CPU-Zeit beansprucht, treten u. U. Leistungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="639df-108">A natively compiled stored procedure that uses a lot of CPU time may have performance problems.</span></span>  
  
 <span data-ttu-id="639df-109">Neben `line_number` kann auch `object_id` im erweiterten Ereignis verwendet werden, um die Abfrage zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="639df-109">`line_number`, along with the `object_id` in the extended event can be used to investigate the query.</span></span> <span data-ttu-id="639df-110">Mithilfe der folgenden Abfrage kann die Prozedurdefinition abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="639df-110">The following query can be used to retrieve the procedure definition.</span></span> <span data-ttu-id="639df-111">Anhand der Zeilennummer wird die Abfrage innerhalb der Definition identifiziert:</span><span class="sxs-lookup"><span data-stu-id="639df-111">The line number can be used to identify the query within the definition:</span></span>  
  
```sql  
select [definition] from sys.sql_modules where object_id=object_id  
```  
  
 <span data-ttu-id="639df-112">Weitere Informationen zum `sp_statement_completed` erweiterten Ereignis finden [Sie unter Abrufen der Anweisung, die ein Ereignis verursacht](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx)hat.</span><span class="sxs-lookup"><span data-stu-id="639df-112">For more information about the `sp_statement_completed` extended event, see [How to retrieve the statement that caused an event](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span></span>  
  
## <a name="using-data-management-views"></a><span data-ttu-id="639df-113">Unter Verwendung von Datenverwaltungssichten</span><span class="sxs-lookup"><span data-stu-id="639df-113">Using Data Management Views</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="639df-114">unterstützt Ausführungsstatistiken für systemintern kompilierte gespeicherte Prozeduren sowohl auf Prozedur- als auch auf Abfrageebene.</span><span class="sxs-lookup"><span data-stu-id="639df-114">supports collecting execution statistics for natively compiled stored procedures, both on the procedure level and the query level.</span></span> <span data-ttu-id="639df-115">Das Sammeln statistischer Ausführungsdaten ist aufgrund der Leistungsauswirkungen standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="639df-115">Collecting execution statistics is not enabled by default due to performance impact.</span></span>  
  
 <span data-ttu-id="639df-116">Die Statistiksammlung für systemintern kompilierte gespeicherte Prozeduren kann mit [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql) aktiviert und deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="639df-116">You can enable and disable statistics collection on natively compiled stored procedures using [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="639df-117">Wenn die Erfassung von Statistiken mit [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql) aktiviert ist, können Sie [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) verwenden, um die Leistung einer nativ kompilierten gespeicherten Prozedur zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="639df-117">When statistics collection is enabled with [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), you can use [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="639df-118">Wenn die Erfassung von Statistiken mit [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql) aktiviert ist, können Sie [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) verwenden, um die Leistung einer nativ kompilierten gespeicherten Prozedur zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="639df-118">When statistics collection is enabled with [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), you can use [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="639df-119">Zu Beginn aktivieren Sie die Statistiksammlung.</span><span class="sxs-lookup"><span data-stu-id="639df-119">At the start of collection, enable statistics collection.</span></span> <span data-ttu-id="639df-120">Anschließend führen Sie die systemintern kompilierte gespeicherte Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="639df-120">Then, execute the natively compiled stored procedure.</span></span> <span data-ttu-id="639df-121">Am Ende deaktivieren Sie die Statistiksammlung.</span><span class="sxs-lookup"><span data-stu-id="639df-121">At the end of collection, disable statistics collection.</span></span> <span data-ttu-id="639df-122">Anschließend analysieren Sie die von den DMVs zurückgegebene Ausführungsstatistik.</span><span class="sxs-lookup"><span data-stu-id="639df-122">Then, analyze the execution statistics returned by the DMVs.</span></span>  
  
 <span data-ttu-id="639df-123">Nachdem die Statistiksammlung abgeschlossen wurde, können die Ausführungsstatistiken zu nativ kompilierten gespeicherten Prozeduren mit [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) für eine Prozedur und für Abfragen mit [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="639df-123">After you collect statistics, the execution statistics for natively compiled stored procedures can be queried for a procedure with [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), and for queries with [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="639df-124">Wenn die Statistiksammlung für systemintern kompilierte gespeicherte Prozeduren aktiviert ist, wird worker_time in Millisekunden erfasst.</span><span class="sxs-lookup"><span data-stu-id="639df-124">For natively compiled stored procedures when statistics collection is enabled, worker time is collected in milliseconds.</span></span> <span data-ttu-id="639df-125">Wird die Abfrage in weniger als einer Millisekunde ausgeführt, lautet der Wert 0.</span><span class="sxs-lookup"><span data-stu-id="639df-125">If the query executes in less than a millisecond, the value will be 0.</span></span> <span data-ttu-id="639df-126">Wenn zahlreiche Ausführungen weniger als 1 Millisekunde dauern, wird **total_worker_time** bei nativ kompilierten gespeicherten Prozeduren u.U. nicht exakt angegeben.</span><span class="sxs-lookup"><span data-stu-id="639df-126">For natively compiled stored procedures, **total_worker_time** may not be accurate if many executions take less than 1 millisecond.</span></span>  
  
 <span data-ttu-id="639df-127">Mit der folgenden Abfrage werden nach der Statistiksammlung die Prozedurnamen und Ausführungsstatistiken für systemintern kompilierte gespeicherte Prozeduren in der aktuellen Datenbank zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="639df-127">The following query returns the procedure names and execution statistics for natively compiled stored procedures in the current database, after statistics collection:</span></span>  
  
```sql  
select object_id,  
       object_name(object_id) as 'object name',  
       cached_time,  
       last_execution_time,  
       execution_count,  
       total_worker_time,  
       last_worker_time,  
       min_worker_time,  
       max_worker_time,  
       total_elapsed_time,  
       last_elapsed_time,  
       min_elapsed_time,  
       max_elapsed_time   
from sys.dm_exec_procedure_stats  
where database_id=db_id() and object_id in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by total_worker_time desc  
```  
  
 <span data-ttu-id="639df-128">Mit der folgenden Abfrage werden der Abfragetext und Ausführungsstatistiken für alle Abfragen in systemintern kompilierten gespeicherten Prozeduren der aktuellen Datenbank zurückgegeben, für die statistische Daten gesammelt wurden. Die Ergebnisse sind nach total_worker_time in absteigender Reihenfolge sortiert:</span><span class="sxs-lookup"><span data-stu-id="639df-128">The following query returns the query text as well as execution statistics for all queries in natively compiled stored procedures in the current database for which statistics have been collected, ordered by total worker time, in descending order:</span></span>  
  
```sql  
select st.objectid,   
       object_name(st.objectid) as 'object name',   
       SUBSTRING(st.text, (qs.statement_start_offset/2) + 1, ((qs.statement_end_offset-qs.statement_start_offset)/2) + 1) as 'query text',   
       qs.creation_time,  
       qs.last_execution_time,  
       qs.execution_count,  
       qs.total_worker_time,  
       qs.last_worker_time,  
       qs.min_worker_time,  
       qs.max_worker_time,  
       qs.total_elapsed_time,  
       qs.last_elapsed_time,  
       qs.min_elapsed_time,  
       qs.max_elapsed_time  
from sys.dm_exec_query_stats qs cross apply sys.dm_exec_sql_text(sql_handle) st  
where  st.dbid=db_id() and st.objectid in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by qs.total_worker_time desc  
```  
  
 <span data-ttu-id="639df-129">Systemintern kompilierte gespeicherte Prozeduren unterstützen SHOWPLAN_XML (geschätzter Ausführungsplan).</span><span class="sxs-lookup"><span data-stu-id="639df-129">Natively compiled stored procedures support SHOWPLAN_XML (estimated execution plan).</span></span> <span data-ttu-id="639df-130">Der geschätzte Ausführungsplan kann verwendet werden, um den Abfrageplan auf Planungsfehler zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="639df-130">The estimated execution plan can be used to inspect the query plan, to find any bad plan issues.</span></span> <span data-ttu-id="639df-131">Häufige Gründe für fehlerhafte Pläne sind:</span><span class="sxs-lookup"><span data-stu-id="639df-131">Common reasons for bad plans are:</span></span>  
  
-   <span data-ttu-id="639df-132">Statistiken wurden vor der Erstellung der Prozedur nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="639df-132">Stats were not updated before the procedure was created.</span></span>  
  
-   <span data-ttu-id="639df-133">Fehlende Indizes</span><span class="sxs-lookup"><span data-stu-id="639df-133">Missing indexes</span></span>  
  
 <span data-ttu-id="639df-134">Um Showplan XML abzurufen, führen Sie folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code aus:</span><span class="sxs-lookup"><span data-stu-id="639df-134">Showplan XML is obtained by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
SET SHOWPLAN_XML ON  
GO  
EXEC my_proc   
GO  
SET SHOWPLAN_XML OFF  
GO  
```  
  
 <span data-ttu-id="639df-135">Alternativ können Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Prozedurnamen auswählen und auf **Geschätzten Ausführungsplan anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="639df-135">Alternatively, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the procedure name and click **Display Estimated Execution Plan**.</span></span>  
  
 <span data-ttu-id="639df-136">Im geschätzten Ausführungsplan für systemintern kompilierte gespeicherte Prozeduren werden die Abfrageoperatoren und Ausdrücke für die Abfragen der Prozedur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="639df-136">The estimated execution plan for natively compiled stored procedures shows the query operators and expressions for the queries in the procedure.</span></span> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="639df-137">unterstützt nicht alle SHOWPLAN_XML-Attribute für systemintern kompilierte gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="639df-137">does not support all SHOWPLAN_XML attributes for natively compiled stored procedures.</span></span> <span data-ttu-id="639df-138">Attribute in Zusammenhang mit Kostenberechnungen des Abfrageoptimierers sind nicht Teil der SHOWPLAN_XML für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="639df-138">For example, attributes related to query optimizer costing are not part of the SHOWPLAN_XML for the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639df-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="639df-139">See Also</span></span>  
 [<span data-ttu-id="639df-140">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="639df-140">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
