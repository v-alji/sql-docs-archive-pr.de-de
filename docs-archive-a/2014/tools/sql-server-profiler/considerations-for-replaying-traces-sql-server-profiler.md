---
title: Überlegungen zum Wiedergeben von Ablaufverfolgungen (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 73fa339f-b71a-4be4-97ca-d4ae84c8b90b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c2f030a0191596e40ef1ee9e2b0b2d4da34c773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694962"
---
# <a name="considerations-for-replaying-traces-sql-server-profiler"></a><span data-ttu-id="91b3b-102">Überlegungen zum Wiedergeben von Ablaufverfolgungen (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="91b3b-102">Considerations for Replaying Traces (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="91b3b-103">können die folgenden Arten von Ablaufverfolgungen nicht wiedergegeben werden:</span><span class="sxs-lookup"><span data-stu-id="91b3b-103">cannot replay the following kinds of traces:</span></span>  
  
-   <span data-ttu-id="91b3b-104">Ablaufverfolgungen, die die Transaktionsreplikation und andere Transaktionsprotokollaktivität enthalten.</span><span class="sxs-lookup"><span data-stu-id="91b3b-104">Traces that contain transactional replication and other transaction log activity.</span></span> <span data-ttu-id="91b3b-105">Diese Ereignisse werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="91b3b-105">These events are skipped.</span></span> <span data-ttu-id="91b3b-106">Andere Replikationsarten markieren nicht das Transaktionsprotokoll und sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="91b3b-106">Other types of replication do not mark the transaction log so they are not affected.</span></span>  
  
-   <span data-ttu-id="91b3b-107">Ablaufverfolgungen, die Vorgänge mit global eindeutigen Bezeichnern (Globally Unique Identifier, GUID) enthalten.</span><span class="sxs-lookup"><span data-stu-id="91b3b-107">Traces that contain operations that involve globally unique identifiers (GUID).</span></span> <span data-ttu-id="91b3b-108">Diese Ereignisse werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="91b3b-108">These events will be skipped.</span></span>  
  
-   <span data-ttu-id="91b3b-109">Ablaufverfolgungen, die Vorgänge mit den Spalten **text**, **ntext**und **image** mit dem Hilfsprogramm **bcp** , den Anweisungen BULK INSERT, READTEXT, WRITETEXT und UPDATETEXT und Volltextvorgängen enthalten.</span><span class="sxs-lookup"><span data-stu-id="91b3b-109">Traces that contain operations on **text**, **ntext**, and **image** columns involving the **bcp** utility, the BULK INSERT, READTEXT, WRITETEXT, and UPDATETEXT statements, and full-text operations.</span></span> <span data-ttu-id="91b3b-110">Diese Ereignisse werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="91b3b-110">These events are skipped.</span></span>  
  
-   <span data-ttu-id="91b3b-111">Ablaufverfolgungen, die eine Sitzungsbindung enthalten: gespeicherte Systemprozeduren **sp_getbindtoken** und **sp_bindsession** .</span><span class="sxs-lookup"><span data-stu-id="91b3b-111">Traces that contain session binding: **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span> <span data-ttu-id="91b3b-112">Diese Ereignisse werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="91b3b-112">These events are skipped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91b3b-113">Wenn Sie nicht die vorkonfigurierte Wiedergabevorlage (**TSQL_Replay**) verwenden und nicht alle erforderlichen Daten erfassen, wird die Ablaufverfolgung von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] nicht wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="91b3b-113">If you do not use the preconfigured replay template (**TSQL_Replay**), and do not capture all required data, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] does not replay the trace.</span></span> <span data-ttu-id="91b3b-114">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91b3b-114">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
 <span data-ttu-id="91b3b-115">Informationen zu den Berechtigungen, die zum Wiedergeben einer Ablaufverfolgung erforderlich sind, finden Sie unter [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="91b3b-115">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b3b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91b3b-116">See Also</span></span>  
 <span data-ttu-id="91b3b-117">[bcp (Hilfsprogramm)](../bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="91b3b-117">[bcp Utility](../bcp-utility.md) </span></span>  
 <span data-ttu-id="91b3b-118">[Ereignisklassen in SQL Server: Referenz](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="91b3b-118">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="91b3b-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91b3b-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span></span>  
 <span data-ttu-id="91b3b-120">[sp_bindsession (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91b3b-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 <span data-ttu-id="91b3b-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91b3b-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="91b3b-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91b3b-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span></span>  
 <span data-ttu-id="91b3b-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91b3b-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span></span>  
 [<span data-ttu-id="91b3b-124">UPDATETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91b3b-124">UPDATETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/updatetext-transact-sql)  
  
  
