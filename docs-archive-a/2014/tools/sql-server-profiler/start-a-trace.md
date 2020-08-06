---
title: Starten einer Ablaufverfolgung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2b75519631269a1213077a4e295ac73fca1b950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719162"
---
# <a name="start-a-trace"></a><span data-ttu-id="d2f54-102">Starten einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d2f54-102">Start a Trace</span></span>
  <span data-ttu-id="d2f54-103">Nachdem Sie mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]eine neue Ablaufverfolgung definiert oder eine Vorlage erstellt haben, können Sie die Aufzeichnung von Daten mithilfe der neuen Ablaufverfolgungsdefinition oder Vorlage starten, anhalten oder beenden.</span><span class="sxs-lookup"><span data-stu-id="d2f54-103">After you have defined a new trace or created a template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can start, pause, or stop capturing data by using the new trace definition or template.</span></span>  
  
## <a name="starting-a-trace"></a><span data-ttu-id="d2f54-104">Starten einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d2f54-104">Starting a Trace</span></span>  
 <span data-ttu-id="d2f54-105">Wenn Sie eine Ablaufverfolgung starten und die definierte Quelle eine Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] oder [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]ist, erstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Warteschlange als temporären Speicherort für aufgezeichnete Serverereignisse.</span><span class="sxs-lookup"><span data-stu-id="d2f54-105">When you start a trace and the defined source is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a queue that provides a temporary holding place for captured server events.</span></span>  
  
 <span data-ttu-id="d2f54-106">Wenn Sie mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auf die SQL-Ablaufverfolgung zugreifen, wird durch das Starten einer Ablaufverfolgung ein neues Ablaufverfolgungsfenster geöffnet (sofern noch keines geöffnet ist), und die Daten werden sofort aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d2f54-106">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to access SQL Trace, a new trace window opens (if one is not already open) when a trace is started, and data is immediately captured.</span></span>  
  
 <span data-ttu-id="d2f54-107">Wenn Sie gespeicherte Systemprozeduren von [!INCLUDE[tsql](../../includes/tsql-md.md)] für den Zugriff auf die SQL-Ablaufverfolgung verwenden, müssen Sie bei jedem Start einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Ablaufverfolgung starten, damit die Daten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d2f54-107">When you use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to access SQL Trace, you must start a trace every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts for data to be captured.</span></span> <span data-ttu-id="d2f54-108">Nachdem eine Ablaufverfolgung gestartet wurde, können Sie nur den Namen der Ablaufverfolgung ändern.</span><span class="sxs-lookup"><span data-stu-id="d2f54-108">When a trace has been started, you can modify only the name of the trace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2f54-109">Bei vorhandenen Ablaufverfolgungen können Sie die Eigenschaften zwar anzeigen, aber nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d2f54-109">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="d2f54-110">Um die Eigenschaften zu ändern, müssen Sie die Ablaufverfolgung beenden oder anhalten.</span><span class="sxs-lookup"><span data-stu-id="d2f54-110">To modify the properties, stop or pause the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f54-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2f54-111">See Also</span></span>  
 <span data-ttu-id="d2f54-112">[Automatisches Starten einer Ablauf Verfolgung nach dem Herstellen einer Verbindung mit einem Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d2f54-112">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d2f54-113">[Anhalten einer Ablauf Verfolgung &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d2f54-113">[Pause a Trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d2f54-114">[Beendet eine Ablauf Verfolgung &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d2f54-114">[Stop a Trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d2f54-115">[Löschen eines Ablauf Verfolgungs Fensters &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d2f54-115">[Clear a Trace Window &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="d2f54-116">Ausführen einer Ablaufverfolgung, nachdem sie angehalten oder beendet wurde &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="d2f54-116">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
