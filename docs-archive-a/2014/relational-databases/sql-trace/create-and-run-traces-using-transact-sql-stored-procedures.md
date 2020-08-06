---
title: Erstellen und Ausführen von Ablaufverfolgungen mit gespeicherten Transact-SQL-Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 80347417-338d-4bea-8885-91fae5181cfe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2905ce2822598502ef6337d1a083fb6fde001c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619050"
---
# <a name="create-and-run-traces-using-transact-sql-stored-procedures"></a><span data-ttu-id="25eed-102">Erstellen und Ausführen von Ablaufverfolgungen mit gespeicherten Transact-SQL-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="25eed-102">Create and Run Traces Using Transact-SQL Stored Procedures</span></span>
  <span data-ttu-id="25eed-103">Der Ablaufverfolgungsprozess mithilfe der SQL-Ablaufverfolgung hängt davon ab, ob Sie die Ablaufverfolgung mithilfe von Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] oder mithilfe gespeicherter Systemprozeduren ausführen.</span><span class="sxs-lookup"><span data-stu-id="25eed-103">The process of tracing with SQL Trace varies depending on whether you create and run your trace by using Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or by using system stored procedures.</span></span>  
  
 <span data-ttu-id="25eed-104">Anstelle von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]können Sie gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Systemprozeduren zum Erstellen und Ausführen von Ablaufverfolgungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="25eed-104">As an alternative to [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create and run traces.</span></span> <span data-ttu-id="25eed-105">Der Ablaufverfolgungsprozess mithilfe gespeicherter Systemprozeduren sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="25eed-105">The process of tracing by using system stored procedures is as follows:</span></span>  
  
1.  <span data-ttu-id="25eed-106">Erstellen Sie eine Ablaufverfolgung mithilfe von **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="25eed-106">Create a trace by using **sp_trace_create**.</span></span>  
  
2.  <span data-ttu-id="25eed-107">Fügen Sie mit **sp_trace_setevent**Ereignisse hinzu.</span><span class="sxs-lookup"><span data-stu-id="25eed-107">Add events with **sp_trace_setevent**.</span></span>  
  
3.  <span data-ttu-id="25eed-108">(Optional) Legen Sie mit **sp_trace_setfilter**einen Filter fest.</span><span class="sxs-lookup"><span data-stu-id="25eed-108">(Optional) Set a filter with **sp_trace_setfilter**.</span></span>  
  
4.  <span data-ttu-id="25eed-109">Starten Sie die Ablaufverfolgung mit **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="25eed-109">Start the trace with **sp_trace_setstatus**.</span></span>  
  
5.  <span data-ttu-id="25eed-110">Halten Sie die Ablaufverfolgung mit **sp_trace_setstatus**an.</span><span class="sxs-lookup"><span data-stu-id="25eed-110">Stop the trace with **sp_trace_setstatus**.</span></span>  
  
6.  <span data-ttu-id="25eed-111">Schließen Sie die Ablaufverfolgung mit **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="25eed-111">Close the trace with **sp_trace_setstatus**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25eed-112">Beim Verwenden gespeicherter [!INCLUDE[tsql](../../includes/tsql-md.md)] -Systemprozeduren wird eine serverseitige Ablaufverfolgung erstellt. Dadurch wird sichergestellt, dass keine Ereignisse verloren gehen, sofern auf dem Datenträger Speicherplatz vorhanden ist und keine Schreibfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="25eed-112">Using [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures creates a server-side trace, which guarantees that no events will be lost as long as there is space on the disk and no write errors occur.</span></span> <span data-ttu-id="25eed-113">Wenn der Datenträger voll ist oder ein Datenträgerfehler auftritt, wird die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weiterhin ausgeführt, aber die Ablaufverfolgung wird angehalten.</span><span class="sxs-lookup"><span data-stu-id="25eed-113">If the disk becomes full or the disk fails, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance continues to run, but tracing stops.</span></span> <span data-ttu-id="25eed-114">Wenn **C2-Überwachungsmodus** festgelegt ist und ein Schreibfehler auftritt, wird die Ablaufverfolgung angehalten, und die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="25eed-114">If the **c2 audit mode** is set, and there is a write failure, tracing stops and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span> <span data-ttu-id="25eed-115">Weitere Informationen finden zur Einstellung **C2-Überwachungsmodus** finden Sie unter [C2-Überwachungsmodus (Serverkonfigurationsoption)](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="25eed-115">For more information about the **c2 audit mode** setting, see [c2 audit mode Server Configuration Option](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25eed-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="25eed-116">In This Section</span></span>  
  
|<span data-ttu-id="25eed-117">Thema</span><span class="sxs-lookup"><span data-stu-id="25eed-117">Topic</span></span>|<span data-ttu-id="25eed-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25eed-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="25eed-119">Optimieren der SQL-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="25eed-119">Optimize SQL Trace</span></span>](sql-trace.md)|<span data-ttu-id="25eed-120">Enthält Informationen dazu, wie Sie die Auswirkungen der Ablaufverfolgung auf die Systemleistung verringern können.</span><span class="sxs-lookup"><span data-stu-id="25eed-120">Contains information about ways you can reduce the effects of tracing on system performance.</span></span>|  
|[<span data-ttu-id="25eed-121">Filtern einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="25eed-121">Filter a Trace</span></span>](filter-a-trace.md)|<span data-ttu-id="25eed-122">Enthält Informationen zum Verwenden von Filtern für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="25eed-122">Contains information about using filters for tracing.</span></span>|  
|[<span data-ttu-id="25eed-123">Beschränken der Größe von Ablaufverfolgungsdatei und -tabelle</span><span class="sxs-lookup"><span data-stu-id="25eed-123">Limit Trace File and Table Sizes</span></span>](limit-trace-file-and-table-sizes.md)|<span data-ttu-id="25eed-124">Enthält Informationen dazu, wie Sie die Größe von Dateien und Tabellen, in die Ablaufverfolgungsdaten geschrieben werden, beschränken können.</span><span class="sxs-lookup"><span data-stu-id="25eed-124">Contains information about how to limit the size of files and tables where trace data is written.</span></span> <span data-ttu-id="25eed-125">Beachten Sie, dass Ablaufverfolgungsinformationen nur von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in Tabellen geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="25eed-125">Note that only [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can write trace information to tables.</span></span>|  
|[<span data-ttu-id="25eed-126">Planen von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="25eed-126">Schedule Traces</span></span>](schedule-traces.md)|<span data-ttu-id="25eed-127">Enthält Informationen zum Einstellen der Start- und Beendigungszeit für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="25eed-127">Contains information about how to set the start time and the end time for tracing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25eed-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25eed-128">See Also</span></span>  
 <span data-ttu-id="25eed-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25eed-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="25eed-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25eed-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="25eed-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25eed-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 [<span data-ttu-id="25eed-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="25eed-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
  
