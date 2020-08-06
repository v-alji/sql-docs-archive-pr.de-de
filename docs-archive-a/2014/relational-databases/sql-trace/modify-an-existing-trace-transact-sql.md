---
title: Ändern einer vorhandenen Ablaufverfolgung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 55b8172ef8e6188059c484ab41f1a719e0e9f8c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609043"
---
# <a name="modify-an-existing-trace-transact-sql"></a><span data-ttu-id="4ba92-102">Ändern einer vorhandenen Ablaufverfolgung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4ba92-102">Modify an Existing Trace (Transact-SQL)</span></span>
  <span data-ttu-id="4ba92-103">In diesem Thema wird beschrieben, wie gespeicherte Prozeduren verwendet werden können, um eine vorhandene Ablaufverfolgung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4ba92-103">This topic describes how to use stored procedures to modify an existing trace.</span></span>  
  
### <a name="to-modify-an-existing-trace"></a><span data-ttu-id="4ba92-104">So ändern Sie eine vorhandene Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ba92-104">To modify an existing trace</span></span>  
  
1.  <span data-ttu-id="4ba92-105">Wenn die Ablaufverfolgung bereits ausgeführt wird, führen Sie **sp_trace_setstatus** mit **@status = 0** aus, um die Ablaufverfolgung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="4ba92-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="4ba92-106">Um Ablaufverfolgungsereignisse zu ändern, führen Sie **sp_trace_setevent** aus, wobei Sie die Änderungen über die Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="4ba92-106">To modify trace events, execute **sp_trace_setevent** by specifying the changes through the parameters.</span></span> <span data-ttu-id="4ba92-107">Der Reihenfolge nach sortiert stehen die folgenden Parameter zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="4ba92-107">Listed in order, the parameters are:</span></span>  
  
    -   <span data-ttu-id="4ba92-108">**@traceid**(Ablaufverfolgungs-ID)</span><span class="sxs-lookup"><span data-stu-id="4ba92-108">**@traceid** (Trace ID)</span></span>  
  
    -   <span data-ttu-id="4ba92-109">**@eventid**(Ereignis-ID)</span><span class="sxs-lookup"><span data-stu-id="4ba92-109">**@eventid** (Event ID)</span></span>  
  
    -   <span data-ttu-id="4ba92-110">**@columnid**(Spalten-ID)</span><span class="sxs-lookup"><span data-stu-id="4ba92-110">**@columnid** (Column ID)</span></span>  
  
    -   <span data-ttu-id="4ba92-111">**@on**Auf</span><span class="sxs-lookup"><span data-stu-id="4ba92-111">**@on** (ON)</span></span>  
  
     <span data-ttu-id="4ba92-112">Beachten Sie beim Ändern des **@on** Parameters die Interaktion mit dem **@columnid** Parameter:</span><span class="sxs-lookup"><span data-stu-id="4ba92-112">When you modify the **@on** parameter, keep in mind its interaction with the **@columnid** parameter:</span></span>  
  
    |<span data-ttu-id="4ba92-113">EIN</span><span class="sxs-lookup"><span data-stu-id="4ba92-113">ON</span></span>|<span data-ttu-id="4ba92-114">Column ID</span><span class="sxs-lookup"><span data-stu-id="4ba92-114">Column ID</span></span>|<span data-ttu-id="4ba92-115">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="4ba92-115">Result</span></span>|  
    |--------|---------------|------------|  
    |<span data-ttu-id="4ba92-116">ON (**1**)</span><span class="sxs-lookup"><span data-stu-id="4ba92-116">ON (**1**)</span></span>|<span data-ttu-id="4ba92-117">NULL</span><span class="sxs-lookup"><span data-stu-id="4ba92-117">NULL</span></span>|<span data-ttu-id="4ba92-118">Das Ereignis ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4ba92-118">Event is turned on.</span></span> <span data-ttu-id="4ba92-119">Alle Spalten werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4ba92-119">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="4ba92-120">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4ba92-120">NOT NULL</span></span>|<span data-ttu-id="4ba92-121">Die Spalte ist für das angegebene Ereignis aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4ba92-121">Column is turned on for the specified event.</span></span>|  
    |<span data-ttu-id="4ba92-122">OFF (**0**)</span><span class="sxs-lookup"><span data-stu-id="4ba92-122">OFF (**0**)</span></span>|<span data-ttu-id="4ba92-123">NULL</span><span class="sxs-lookup"><span data-stu-id="4ba92-123">NULL</span></span>|<span data-ttu-id="4ba92-124">Das Ereignis ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4ba92-124">Event is turned off.</span></span> <span data-ttu-id="4ba92-125">Alle Spalten werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4ba92-125">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="4ba92-126">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4ba92-126">NOT NULL</span></span>|<span data-ttu-id="4ba92-127">Die Spalte ist für das angegebene Ereignis deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4ba92-127">Column is turned off for the specified event.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ba92-128">Im Gegensatz zu regulären gespeicherten Prozeduren werden die Parameter aller gespeicherten Prozeduren von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) streng typisiert, und für sie wird keine automatische Datentypkonvertierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ba92-128">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="4ba92-129">Wenn diese Parameter nicht mit den richtigen Datentypen für Eingabeparameter aufgerufen werden, wie in der Argumentbeschreibung angegeben, gibt die gespeicherte Prozedur einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="4ba92-129">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4ba92-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ba92-130">See Also</span></span>  
 <span data-ttu-id="4ba92-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ba92-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="4ba92-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ba92-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="4ba92-133">[Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ba92-133">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="4ba92-134">Gespeicherte Prozeduren von SQL Server Profiler &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4ba92-134">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
