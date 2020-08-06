---
title: Festlegen eines Ablaufverfolgungsfilters (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
ms.assetid: 7b976a84-7381-43a6-a828-ba83ada71cbe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47d797c84a05f50da026280f6e197f965d804426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619535"
---
# <a name="set-a-trace-filter-transact-sql"></a><span data-ttu-id="997d2-102">Festlegen eines Ablaufverfolgungsfilters (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="997d2-102">Set a Trace Filter (Transact-SQL)</span></span>
  <span data-ttu-id="997d2-103">In diesem Thema wird die Vorgehensweise zum Verwenden gespeicherter Prozeduren zum Erstellen eines Filters beschrieben, von dem nur die von Ihnen benötigten Informationen zum Nachverfolgen eines Ereignisses abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="997d2-103">This topic describes how to use stored procedures to create a filter that retrieves only the information you need on an event being traced.</span></span>  
  
### <a name="to-set-a-trace-filter"></a><span data-ttu-id="997d2-104">So legen Sie einen Ablaufverfolgungsfilter fest</span><span class="sxs-lookup"><span data-stu-id="997d2-104">To set a trace filter</span></span>  
  
1.  <span data-ttu-id="997d2-105">Wenn die Ablaufverfolgung bereits ausgeführt wird, führen Sie **sp_trace_setstatus** mit **@status = 0** aus, um die Ablaufverfolgung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="997d2-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="997d2-106">Führen Sie **sp_trace_setfilter** aus, um den Informationstyp zu konfigurieren, der für das nachzuverfolgende Ereignis abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="997d2-106">Execute **sp_trace_setfilter** to configure the type of information to retrieve for the event being traced.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="997d2-107">Im Gegensatz zu regulären gespeicherten Prozeduren [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] werden die Parameter aller gespeicherten Prozeduren (<strong>sp_trace_*xx*</strong>) streng typisiert und unterstützen die automatische Datentyp Konvertierung nicht.</span><span class="sxs-lookup"><span data-stu-id="997d2-107">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="997d2-108">Wenn diese Parameter nicht mit den richtigen Datentypen für Eingabeparameter aufgerufen werden, wie in der Argumentbeschreibung angegeben, gibt die gespeicherte Prozedur einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="997d2-108">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure will return an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997d2-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="997d2-109">See Also</span></span>  
 <span data-ttu-id="997d2-110">[Filtern einer Ablauf Verfolgung](../../relational-databases/sql-trace/filter-a-trace.md) </span><span class="sxs-lookup"><span data-stu-id="997d2-110">[Filter a Trace](../../relational-databases/sql-trace/filter-a-trace.md) </span></span>  
 <span data-ttu-id="997d2-111">[sp_trace_setfilter &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="997d2-111">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 <span data-ttu-id="997d2-112">[sp_trace_setstatus &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="997d2-112">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="997d2-113">[Gespeicherte System Prozeduren &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="997d2-113">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="997d2-114">Gespeicherte Prozeduren von SQL Server Profiler &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="997d2-114">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
