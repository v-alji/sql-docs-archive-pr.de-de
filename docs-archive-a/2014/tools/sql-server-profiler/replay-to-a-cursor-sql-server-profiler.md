---
title: Wiedergabe bis zu einem Cursor (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- replaying cursors
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 89eadc41-4424-4a1c-ba61-0b52c851cdb1
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfc5ba06b60100bf8ecc8d04909371021a5b00e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722050"
---
# <a name="replay-to-a-cursor-sql-server-profiler"></a><span data-ttu-id="9dba0-102">Wiedergeben bis zu einer Cursorposition (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="9dba0-102">Replay to a Cursor (SQL Server Profiler)</span></span>
  <span data-ttu-id="9dba0-103">In diesem Thema wird beschrieben, wie Ablaufverfolgungsdateien oder -tabellen mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]so wiedergegeben werden können, dass sie anhalten, wenn sie eine Cursorposition erreichen.</span><span class="sxs-lookup"><span data-stu-id="9dba0-103">This topic describes how to replay trace files or tables that pause when a cursor is reached by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="9dba0-104">Durch das Anhalten von Ablaufverfolgungen an Cursorpositionen wird das Debugging erleichtert, da lange Ablaufverfolgungsskripts in kürzere Segmente unterteilt und inkrementell analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="9dba0-104">Pausing traces at cursors supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-the-cursor"></a><span data-ttu-id="9dba0-105">So geben Sie bis zur Cursorposition wieder</span><span class="sxs-lookup"><span data-stu-id="9dba0-105">To replay to the cursor</span></span>  
  
1.  <span data-ttu-id="9dba0-106">Öffnen Sie die Ablaufverfolgungsdatei oder -tabelle, die Sie wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="9dba0-106">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="9dba0-107">Weitere Informationen finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) oder den Optimierungsratgeber von [Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md)die richtigen Ereignisse und Spalten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="9dba0-107">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="9dba0-108">Stellen Sie sicher, dass die geöffnete Ablaufverfolgungsdatei oder -tabelle die Ereignisklassen enthält, die für die Wiedergabe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9dba0-108">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="9dba0-109">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dba0-109">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="9dba0-110">Klicken Sie im Ablaufverfolgungsfenster auf ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9dba0-110">In the trace window, click an event.</span></span>  
  
3.  <span data-ttu-id="9dba0-111">Klicken Sie im Menü **Wiedergeben** auf **Ausführen bis Cursorposition**, und stellen Sie eine Verbindung zu dem Server her, auf dem Sie die Ablaufverfolgung wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="9dba0-111">On the **Replay** menu, click **Run to Cursor**, and then connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="9dba0-112">Überprüfen Sie im Dialogfeld **Wiedergabekonfiguration** die Einstellungen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9dba0-112">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9dba0-113">Die Wiedergabe beginnt; sie hält an, wenn sie die erste Cursorposition erreicht.</span><span class="sxs-lookup"><span data-stu-id="9dba0-113">The replay starts, pausing when the first cursor is reached.</span></span>  
  
5.  <span data-ttu-id="9dba0-114">Drücken Sie F5, um die Ablaufverfolgung fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="9dba0-114">Press F5 to resume the trace.</span></span>  
  
6.  <span data-ttu-id="9dba0-115">Wiederholen Sie Schritt 5 bis zum Ende der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="9dba0-115">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dba0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9dba0-116">See Also</span></span>  
 <span data-ttu-id="9dba0-117">[Wiedergeben bis zu einem Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="9dba0-117">[Replay to a Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="9dba0-118">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="9dba0-118">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="9dba0-119">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9dba0-119">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
