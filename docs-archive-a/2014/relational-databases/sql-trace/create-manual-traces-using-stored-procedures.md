---
title: Erstellen manueller Ablaufverfolgungen mit gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: f6f47fa2-7c17-41d4-9f69-9be144d56832
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e2840dced22ccdba8fe71cc87c05d7fd6fb4be58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619048"
---
# <a name="create-manual-traces-using-stored-procedures"></a><span data-ttu-id="6c8f9-102">Erstellen manueller Ablaufverfolgungen mit gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6c8f9-102">Create Manual Traces using Stored Procedures</span></span>
  <span data-ttu-id="6c8f9-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stellt zum Erstellen von Ablaufverfolgungen für eine Instanz von [!INCLUDE[tsql](../../includes/tsql-md.md)] gespeicherte [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Systemprozeduren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create traces on an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="6c8f9-104">Sie können aus Ihren Anwendungen heraus diese gespeicherten Systemprozeduren verwenden, um Ablaufverfolgungen statt mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-104">These system stored procedures can be used from within your own applications to create traces manually, instead of using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="6c8f9-105">Dadurch können Sie benutzerdefinierte Anwendungen schreiben, die den speziellen Anforderungen Ihres Unternehmens entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-105">This allows you to write custom applications specific to the needs of your enterprise.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c8f9-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6c8f9-106">In This Section</span></span>  
 <span data-ttu-id="6c8f9-107">In der folgenden Tabelle werden die gespeicherten Systemprozeduren für die Ablaufverfolgung einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-107">The following table lists the system stored procedures for tracing an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
|<span data-ttu-id="6c8f9-108">Gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="6c8f9-108">Stored procedure</span></span>|<span data-ttu-id="6c8f9-109">Ausgeführter Task</span><span class="sxs-lookup"><span data-stu-id="6c8f9-109">Task performed</span></span>|  
|----------------------|--------------------|  
|[<span data-ttu-id="6c8f9-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql)|<span data-ttu-id="6c8f9-111">Gibt die Informationen zu in einer Ablaufverfolgung enthaltenen Ereignisse zurück.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-111">Returns information about events included in a trace.</span></span>|  
|[<span data-ttu-id="6c8f9-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql)|<span data-ttu-id="6c8f9-113">Gibt Informationen zu einer angegebene Ablaufverfolgung oder zu alle vorhandenen Ablaufverfolgungen zurück.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-113">Returns information about a specified trace or all existing traces.</span></span>|  
|[<span data-ttu-id="6c8f9-114">sp_trace_create &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-114">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)|<span data-ttu-id="6c8f9-115">Erstellt eine Ablaufverfolgungsdefinition.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-115">Creates a trace definition.</span></span> <span data-ttu-id="6c8f9-116">Die neue Ablaufverfolgung weist einen beendeten Status auf.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-116">The new trace will be in a stopped state.</span></span>|  
|[<span data-ttu-id="6c8f9-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)|<span data-ttu-id="6c8f9-118">Erstellt ein benutzerdefiniertes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-118">Creates a user-defined event.</span></span>|  
|[<span data-ttu-id="6c8f9-119">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-119">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)|<span data-ttu-id="6c8f9-120">Fügt einer Ablaufverfolgung eine Ereignisklasse oder eine Datenspalte hinzu oder entfernt eine Ereignisklasse oder eine Datenspalte aus einer Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-120">Adds an event class or data column to a trace, or removes one from it.</span></span>|  
|[<span data-ttu-id="6c8f9-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|<span data-ttu-id="6c8f9-122">Startet, beendet oder schließt eine Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-122">Starts, stops, or closes a trace.</span></span>|  
|[<span data-ttu-id="6c8f9-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql)|<span data-ttu-id="6c8f9-124">Gibt Informationen über für eine Ablaufverfolgung angewendete Filter zurück.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-124">Returns information about filters applied to a trace.</span></span>|  
|[<span data-ttu-id="6c8f9-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f9-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|<span data-ttu-id="6c8f9-126">Wendet einen neuen oder geänderten Filter für eine Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-126">Applies a new or modified filter to a trace.</span></span>|  
  
 <span data-ttu-id="6c8f9-127">**So definieren Sie eine eigene Ablaufverfolgung mithilfe von gespeicherten Prozeduren**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-127">**To define your own trace using stored procedures**</span></span>  
  
1.  <span data-ttu-id="6c8f9-128">Geben Sie die Ereignisse, die aufgezeichnet werden sollen, mit **sp_trace_setevent**an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-128">Specify the events to capture using **sp_trace_setevent**.</span></span>  
  
2.  <span data-ttu-id="6c8f9-129">Geben Sie Ereignisfilter an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-129">Specify any event filters.</span></span> <span data-ttu-id="6c8f9-130">Weitere Informationen finden Sie unter [Festlegen eines Ablaufverfolgungsfilters &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="6c8f9-130">For more information, see [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span></span>  
  
3.  <span data-ttu-id="6c8f9-131">Geben Sie das Ziel für die aufgezeichneten Ereignisdaten mit **sp_trace_create** an.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-131">Specify the destination for the captured event data using **sp_trace_create**.</span></span>  
  
 <span data-ttu-id="6c8f9-132">Ein Beispiel zum Verwenden gespeicherter Prozeduren der Ablaufverfolgung finden Sie unter [Erstellen einer Ablaufverfolgung &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6c8f9-132">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span></span>  
  
 <span data-ttu-id="6c8f9-133">**So legen Sie die Standardeinstellungen für Ablaufverfolgungsdefinitionen fest**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-133">**To set trace definition defaults**</span></span>  
  
 [<span data-ttu-id="6c8f9-134">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6c8f9-134">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
 <span data-ttu-id="6c8f9-135">**So legen Sie die Standardeinstellungen für die Ablaufverfolgungsanzeige fest**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-135">**To set trace display defaults**</span></span>  
  
 [<span data-ttu-id="6c8f9-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6c8f9-136">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="6c8f9-137">**So erstellen Sie eine Ablaufverfolgung**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-137">**To create a trace**</span></span>  
  
 [<span data-ttu-id="6c8f9-138">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6c8f9-138">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
 [<span data-ttu-id="6c8f9-139">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c8f9-139">Transact-SQL</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
 <span data-ttu-id="6c8f9-140">**So fügen Sie einer Ablaufverfolgungsvorlage Ereignisse hinzu bzw. entfernen sie**</span><span class="sxs-lookup"><span data-stu-id="6c8f9-140">**To add or remove events from a trace template**</span></span>  
  
 [<span data-ttu-id="6c8f9-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6c8f9-141">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="6c8f9-142">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c8f9-142">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
