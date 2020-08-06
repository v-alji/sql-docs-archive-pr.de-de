---
title: Planen von Ablaufverfolgungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619759"
---
# <a name="schedule-traces"></a><span data-ttu-id="704b0-102">Planen von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="704b0-102">Schedule Traces</span></span>
  <span data-ttu-id="704b0-103">Es gibt zwei Möglichkeiten, um die Ablaufverfolgung in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu planen.</span><span class="sxs-lookup"><span data-stu-id="704b0-103">There are two ways to schedule tracing in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="704b0-104">Ihre Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="704b0-104">You can:</span></span>  
  
-   <span data-ttu-id="704b0-105">Beendigungszeit für Ablaufverfolgung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="704b0-105">Enable a trace stop time.</span></span>  
  
-   <span data-ttu-id="704b0-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zum Planen einer Ablaufverfolgung verwenden.</span><span class="sxs-lookup"><span data-stu-id="704b0-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to schedule a trace.</span></span>  
  
## <a name="specifying-a-stop-time"></a><span data-ttu-id="704b0-107">Angeben einer Beendigungszeit</span><span class="sxs-lookup"><span data-stu-id="704b0-107">Specifying a Stop Time</span></span>  
 <span data-ttu-id="704b0-108">Sie können eine Beendigungszeit für die Ablaufverfolgung angeben, wenn Sie gespeicherte Prozeduren von [!INCLUDE[tsql](../../includes/tsql-md.md)] oder [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="704b0-108">You can specify a trace stop time if you use [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures or if you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="704b0-109">Die Beendigungszeit muss festgelegt werden, wenn die Ablaufverfolgung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="704b0-109">The stop time must be set when the trace is originally configured.</span></span>  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a><span data-ttu-id="704b0-110">Planen von Ablaufverfolgungen mithilfe des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="704b0-110">Scheduling Traces by Using SQL Server Agent</span></span>  
 <span data-ttu-id="704b0-111">Die beste Möglichkeit zum Planen von Ablaufverfolgungen ist die Verwendung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents, um die Ablaufverfolgung zu starten und dann mit der gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur **sp_trace_setstatus**oder mit dem [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]eine Beendigungszeit für die Ablaufverfolgung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="704b0-111">The best way to schedule traces is to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to start the trace and then specify a trace stop time by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure **sp_trace_setstatus**, or [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="704b0-112">**So legen Sie einen Beendigungszeitfilter für Ablaufverfolgungen fest**</span><span class="sxs-lookup"><span data-stu-id="704b0-112">**To set an end time filter for a trace**</span></span>  
  
 [<span data-ttu-id="704b0-113">Filtern von Ereignissen anhand der Ereignisendzeit &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="704b0-113">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [<span data-ttu-id="704b0-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="704b0-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="704b0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="704b0-115">See Also</span></span>  
 [<span data-ttu-id="704b0-116">Automatisierte Administrationstasks &#40;SQL Server-Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="704b0-116">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../../ssms/agent/sql-server-agent.md)  
  
  
