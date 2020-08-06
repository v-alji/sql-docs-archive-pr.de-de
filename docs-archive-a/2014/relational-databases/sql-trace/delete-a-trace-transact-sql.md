---
title: Löschen einer Ablaufverfolgung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3551cff36ef6e2c2e9cc6a4d9b7056ae44cb950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618605"
---
# <a name="delete-a-trace-transact-sql"></a><span data-ttu-id="89d83-102">Löschen einer Ablaufverfolgung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="89d83-102">Delete a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="89d83-103">In diesem Thema wird beschrieben, wie Sie mithilfe von gespeicherten Prozeduren eine Ablaufverfolgung löschen.</span><span class="sxs-lookup"><span data-stu-id="89d83-103">This topic describes how to use stored procedures to delete a trace.</span></span>  
  
 <span data-ttu-id="89d83-104">Ein Beispiel zum Verwenden gespeicherter Prozeduren der Ablaufverfolgung finden Sie unter [Erstellen einer Ablaufverfolgung &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="89d83-104">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span></span>  
  
### <a name="to-delete-a-trace"></a><span data-ttu-id="89d83-105">So löschen Sie eine Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="89d83-105">To delete a trace</span></span>  
  
1.  <span data-ttu-id="89d83-106">Führen Sie **sp_trace_setstatus** mit **@status = 0** aus, um die Ablaufverfolgung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="89d83-106">Execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="89d83-107">Führen Sie **sp_trace_setstatus** mit **@status = 2** aus, um die Ablaufverfolgung zu schließen und die zugehörigen Informationen vom Server zu löschen.</span><span class="sxs-lookup"><span data-stu-id="89d83-107">Execute **sp_trace_setstatus** by specifying **@status = 2** to close the trace and delete its information from the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89d83-108">Eine Ablaufverfolgung muss beendet werden, bevor sie geschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="89d83-108">A trace must be stopped first before it can be closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d83-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89d83-109">See Also</span></span>  
 <span data-ttu-id="89d83-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89d83-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="89d83-111">[Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89d83-111">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="89d83-112">Gespeicherte Prozeduren von SQL Server Profiler &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="89d83-112">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
