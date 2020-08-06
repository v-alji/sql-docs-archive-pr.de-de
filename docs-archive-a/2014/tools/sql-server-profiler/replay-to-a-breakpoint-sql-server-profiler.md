---
title: Wiedergabe bis zu einem Breakpoint (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f33b6862847b042a2613d8c2aa035dd5805493ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722053"
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a><span data-ttu-id="408fe-102">Wiedergeben bis zu einem Breakpoint (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="408fe-102">Replay to a Breakpoint (SQL Server Profiler)</span></span>
  <span data-ttu-id="408fe-103">In diesem Thema wird das Festlegen von Breakpoints in einer Ablaufverfolgungsdatei oder -tabelle beschrieben, die Sie mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="408fe-103">This topic describes how to set breakpoints in a trace file or table that you want to replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="408fe-104">Durch das Festlegen von Breakpoints in einer Ablaufverfolgungsdatei oder in einer Tabelle können Sie die Wiedergabe der Ablaufverfolgung bei speziellen Ereignissen anhalten.</span><span class="sxs-lookup"><span data-stu-id="408fe-104">Setting breakpoints in a trace file or table before you start to replay the trace, enables you to pause replay of the trace at specific events.</span></span> <span data-ttu-id="408fe-105">Die Verwendung von Breakpoints bei der Wiedergabe einer Ablaufverfolgung unterstützt das Debuggen, da Sie die Wiedergabe langer Ablaufverfolgungsskripts in kurze Segmente unterteilen und sie jeweils inkrementell analysieren können.</span><span class="sxs-lookup"><span data-stu-id="408fe-105">Using breakpoints while replaying a trace supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-a-breakpoint"></a><span data-ttu-id="408fe-106">So geben Sie bis zu einem Breakpoint wieder</span><span class="sxs-lookup"><span data-stu-id="408fe-106">To replay to a breakpoint</span></span>  
  
1.  <span data-ttu-id="408fe-107">Öffnen Sie die Ablaufverfolgungsdatei oder -tabelle, die Sie wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="408fe-107">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="408fe-108">Weitere Informationen finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) oder den Optimierungsratgeber von [Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md)die richtigen Ereignisse und Spalten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="408fe-108">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="408fe-109">Stellen Sie sicher, dass die geöffnete Ablaufverfolgungsdatei oder -tabelle die Ereignisklassen enthält, die für die Wiedergabe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="408fe-109">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="408fe-110">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="408fe-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="408fe-111">Klicken Sie im Ablaufverfolgungsfenster auf ein Ereignis, das Sie als Breakpoint verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="408fe-111">In the trace window, click an event that you want to use as a breakpoint.</span></span> <span data-ttu-id="408fe-112">Wenden Sie zum Festlegen eines Breakpoints eine der drei folgenden Methoden an:</span><span class="sxs-lookup"><span data-stu-id="408fe-112">Use one of the following three methods to set a breakpoint:</span></span>  
  
    -   <span data-ttu-id="408fe-113">Drücken Sie F9.</span><span class="sxs-lookup"><span data-stu-id="408fe-113">Press F9.</span></span>  
  
    -   <span data-ttu-id="408fe-114">Klicken Sie im Menü **Wiedergeben** auf **Breakpoint ein/aus**</span><span class="sxs-lookup"><span data-stu-id="408fe-114">On the **Replay** menu, click **Toggle Breakpoint**.</span></span>  
  
    -   <span data-ttu-id="408fe-115">Klicken Sie mit der rechten Maustaste auf das Ereignis, und klicken Sie anschließend auf **Breakpoint ein/aus**.</span><span class="sxs-lookup"><span data-stu-id="408fe-115">Right-click the event, and then click **Toggle Breakpoint**.</span></span>  
  
     <span data-ttu-id="408fe-116">Neben dem ausgewählten Ablaufverfolgungsereignis wird ein rotes Aufzählungszeichen angezeigt, mit dem das Ereignis als Breakpoint in der Ablaufverfolgung gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="408fe-116">A red bullet appears next to the selected trace event, indicating that it is the trace breakpoint.</span></span>  
  
     <span data-ttu-id="408fe-117">Wiederholen Sie diesen Schritt, um mehrere Breakpoints festzulegen.</span><span class="sxs-lookup"><span data-stu-id="408fe-117">Repeat this step to set several breakpoints.</span></span>  
  
3.  <span data-ttu-id="408fe-118">Klicken Sie im Menü **Wiedergeben** auf **Starten**, und stellen Sie dann eine Verbindung mit dem Server her, auf dem die Ablaufverfolgung wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="408fe-118">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="408fe-119">Überprüfen Sie im Dialogfeld **Wiedergabekonfiguration** die Einstellungen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="408fe-119">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="408fe-120">Die Wiedergabe wird gestartet und hält an, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="408fe-120">The replay starts, pausing when the breakpoint is reached.</span></span>  
  
5.  <span data-ttu-id="408fe-121">Drücken Sie F5, um die Wiedergabe fortzusetzen, und zum nächsten Breakpoint überzugehen.</span><span class="sxs-lookup"><span data-stu-id="408fe-121">Press F5 to resume the replay and proceed to the next breakpoint.</span></span>  
  
6.  <span data-ttu-id="408fe-122">Wiederholen Sie Schritt 5 bis zum Ende der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="408fe-122">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408fe-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="408fe-123">See Also</span></span>  
 <span data-ttu-id="408fe-124">[Wiedergeben bis zu einer Cursorposition &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="408fe-124">[Replay to a Cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="408fe-125">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="408fe-125">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="408fe-126">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="408fe-126">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
