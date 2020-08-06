---
title: Wiedergabe Ablauf Verfolgungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
author: stevestein
ms.author: sstein
ms.openlocfilehash: c485317d1343958f9c430b73d858130097d44d75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722049"
---
# <a name="replay-traces"></a><span data-ttu-id="e62ac-102">Wiedergeben von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="e62ac-102">Replay Traces</span></span>
  <span data-ttu-id="e62ac-103">Bei der Wiedergabe handelt es sich um die Fähigkeit, Aktivitäten zu reproduzieren, die in einer Ablaufverfolgung aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="e62ac-103">Replay is the ability to reproduce activity that has been captured in a trace.</span></span> <span data-ttu-id="e62ac-104">Wenn Sie eine Ablaufverfolgung erstellen oder bearbeiten, können Sie sie in einer Datei speichern, um sie zu einem späteren Zeitpunkt wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="e62ac-104">When you create or edit a trace, you can save the trace to a file and replay it later.</span></span> <span data-ttu-id="e62ac-105">Sie können mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Ablaufverfolgungsaktivitäten von einem einzelnen Computer wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="e62ac-105">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay trace activity from a single computer.</span></span> <span data-ttu-id="e62ac-106">Verwenden Sie für große Arbeitsauslastungen das Distributed Replay Utility, um Ablaufverfolgungsdaten von mehreren Computern wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="e62ac-106">For large workloads, use the Distributed Replay Utility to replay trace data from multiple computers.</span></span>  
  
 <span data-ttu-id="e62ac-107">In diesem Abschnitt wird die Verwendung der Wiedergabefunktionen von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e62ac-107">This section describes how to use the replay features of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="e62ac-108">Weitere Informationen zum Distributed Replay Utility finden Sie unter [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="e62ac-108">For more information about the Distributed Replay Utility, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="e62ac-109">verfügt über eine Multithread-Wiedergabe-Engine, die Benutzerverbindungen und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung simulieren kann.</span><span class="sxs-lookup"><span data-stu-id="e62ac-109">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e62ac-110">Die Wiedergabe ist nützlich für die Behandlung von Anwendungs- oder Prozessproblemen.</span><span class="sxs-lookup"><span data-stu-id="e62ac-110">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="e62ac-111">Wenn Sie das Problem identifiziert und Korrekturen implementiert haben, sollten Sie die Ablaufverfolgung, in der das mögliche Problem aufgetreten ist, für die korrigierte Anwendung bzw. den korrigierten Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="e62ac-111">When you have identified the problem and implemented corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="e62ac-112">Geben Sie anschließend die ursprüngliche Ablaufverfolgung wieder, und vergleichen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e62ac-112">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="e62ac-113">Bei der Wiedergabe von Ablaufverfolgungen wird das Debuggen im [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] mithilfe der Optionen **Breakpoint ein/aus** und **Ausführen bis Cursorposition** im Menü **Wiedergeben** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e62ac-113">Trace replay supports debugging by using the **Toggle Breakpoint** and the **Run to Cursor** options on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu.</span></span> <span data-ttu-id="e62ac-114">Diese Optionen verbessern vor allem die Analyse von langen Skripts, weil sie die Wiedergabe der Ablaufverfolgung in kleine Segmente unterteilen können, damit sie schrittweise analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e62ac-114">These options especially improve the analysis of long scripts because they can break the replay of the trace into short segments so they can be analyzed incrementally.</span></span>  
  
 <span data-ttu-id="e62ac-115">Informationen zu den Berechtigungen, die zum Wiedergeben einer Ablaufverfolgung erforderlich sind, finden Sie unter [Erforderliche Berechtigungen zum Ausführen von SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="e62ac-115">For information about the permissions required to replay traces, see [Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e62ac-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e62ac-116">In This Section</span></span>  
  
|<span data-ttu-id="e62ac-117">Thema</span><span class="sxs-lookup"><span data-stu-id="e62ac-117">Topic</span></span>|<span data-ttu-id="e62ac-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e62ac-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e62ac-119">Anforderungen für die Wiedergabe</span><span class="sxs-lookup"><span data-stu-id="e62ac-119">Replay Requirements</span></span>](replay-requirements.md)|<span data-ttu-id="e62ac-120">Beschreibt die Ereignisse, die in einer Ablaufverfolgungsdefinition vorhanden sein müssen, damit die Ablaufverfolgung mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]wiedergegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e62ac-120">Describes the events that must be included in a trace definition so that it can be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="e62ac-121">Wiedergabeoptionen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="e62ac-121">Replay Options &#40;SQL Server Profiler&#41;</span></span>](replay-options-sql-server-profiler.md)|<span data-ttu-id="e62ac-122">Beschreibt die Optionen, die Sie im Dialogfeld **Wiedergabekonfiguration** von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]festlegen können.</span><span class="sxs-lookup"><span data-stu-id="e62ac-122">Describes the options you can set in the **Replay Configuration** dialog box of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="e62ac-123">Überlegungen zum Wiedergeben von Ablaufverfolgungen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="e62ac-123">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)|<span data-ttu-id="e62ac-124">Beschreibt Ablaufverfolgungsereignisse, die nicht mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] wiedergegeben werden können, und die Auswirkungen der Wiedergabe von Ablaufverfolgungen auf die Serverleistung.</span><span class="sxs-lookup"><span data-stu-id="e62ac-124">Describes trace events that can not be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and the effects on server performance of replaying traces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e62ac-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e62ac-125">See Also</span></span>  
 [<span data-ttu-id="e62ac-126">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="e62ac-126">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
