---
title: Wiedergeben von jeweils einem einzelnen Ereignis (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- events [SQL Server], replaying single event at a time
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: stevestein
ms.author: sstein
ms.openlocfilehash: 457bc94d9d8eae470fb60b450d30441c07e676df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722070"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a><span data-ttu-id="7deeb-102">Wiedergeben von jeweils einem einzelnen Ereignis (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="7deeb-102">Replay a Single Event at a Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="7deeb-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]jeweils ein einzelnes Ereignis einer Ablaufverfolgungsdatei oder -tabelle wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="7deeb-103">This topic describes how to replay one event at a time in a replay trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-replay-a-single-event-at-a-time"></a><span data-ttu-id="7deeb-104">So geben Sie jeweils ein einzelnes Ereignis wieder</span><span class="sxs-lookup"><span data-stu-id="7deeb-104">To replay a single event at a time</span></span>  
  
1.  <span data-ttu-id="7deeb-105">Öffnen Sie die Ablaufverfolgungsdatei oder -tabelle, die Sie wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7deeb-105">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="7deeb-106">Weitere Informationen finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) oder den Optimierungsratgeber von [Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md)die richtigen Ereignisse und Spalten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7deeb-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="7deeb-107">Stellen Sie sicher, dass die geöffnete Ablaufverfolgungsdatei oder -tabelle die Ereignisklassen enthält, die für die Wiedergabe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7deeb-107">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="7deeb-108">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7deeb-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="7deeb-109">Klicken Sie im Menü **Wiedergabe** auf **Schritt**, und stellen Sie eine Verbindung mit der Serverinstanz her, auf der die Ablaufverfolgung wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7deeb-109">On the **Replay** menu, click **Step**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="7deeb-110">Überprüfen Sie im Dialogfeld **Wiedergabekonfiguration** die Einstellungen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7deeb-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span> <span data-ttu-id="7deeb-111">Weitere Informationen zu den Einstellungen im Dialogfeld **Wiedergabekonfiguration** finden Sie unter [Wiedergeben einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) oder [Wiedergeben einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="7deeb-111">For more information about specifying settings on the **Replay Configuration** dialog box, see [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) or [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span></span>  
  
4.  <span data-ttu-id="7deeb-112">Klicken Sie im Dialogfeld **Wiedergabekonfiguration** auf **OK** , um das erste Ereignis wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="7deeb-112">To replay the first event, click **OK** in the **Replay Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="7deeb-113">Um die nachfolgenden Ereignisse wiederzugeben, klicken Sie im Menü **Wiedergabe** auf **Schritt**, oder drücken Sie F10.</span><span class="sxs-lookup"><span data-stu-id="7deeb-113">To replay subsequent events, on the **Replay** menu, click **Step**, or press F10.</span></span> <span data-ttu-id="7deeb-114">Klicken Sie für jedes Ereignis entweder auf **Schritt** , oder drücken Sie F10.</span><span class="sxs-lookup"><span data-stu-id="7deeb-114">Repeat clicking **Step** or pressing F10 for each event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7deeb-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7deeb-115">See Also</span></span>  
 <span data-ttu-id="7deeb-116">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="7deeb-116">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="7deeb-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7deeb-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
