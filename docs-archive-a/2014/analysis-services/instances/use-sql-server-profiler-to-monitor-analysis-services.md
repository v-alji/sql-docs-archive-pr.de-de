---
title: Verwenden Sie SQL Server Profiler, um Analysis Services zu überwachen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
author: minewiskan
ms.author: owend
ms.openlocfilehash: e144c1d858670f8a46b164ffc9885e6e082c4b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610163"
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a><span data-ttu-id="8f24d-102">Verwenden von SQL Server Profiler zum Überwachen von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8f24d-102">Use SQL Server Profiler to Monitor Analysis Services</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="8f24d-103">verfolgt Engine-Prozessereignisse wie das Starten eines Batches oder einer Transaktion und erfasst Daten zu diesen Ereignissen. So können Sie die Server- und Datenbankaktivität überwachen (z.B. Benutzerabfragen oder Anmeldeaktivität).</span><span class="sxs-lookup"><span data-stu-id="8f24d-103">tracks engine process events, such as the start of a batch or a transaction, and it captures data about those events, thus enabling you to monitor server and database activity (for example, user queries or login activity).</span></span> <span data-ttu-id="8f24d-104">Sie können [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Daten in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle oder -Datei aufzeichnen und später analysieren oder die aufgezeichneten Ereignisse in der gleichen oder einer anderen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz wiedergeben, um den genauen Ablauf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f24d-104">You can capture [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] data to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or a file for later analysis, and you can also replay the events captured on the same or another [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to see exactly what happened.</span></span> <span data-ttu-id="8f24d-105">Ereignisse können in Echtzeit oder schrittweise wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f24d-105">You can replay events in real time or on a step-by-step basis.</span></span> <span data-ttu-id="8f24d-106">Sehr hilfreich ist es auch, die Ablaufverfolgungsereignisse zusammen mit den Leistungsindikatoren auf dem gleichen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8f24d-106">It is also very useful to run the trace events along with the Performance counters on the same machine.</span></span> <span data-ttu-id="8f24d-107">Der Profiler kann diese auf der Grundlage von Zeit korrelieren und gemeinsam in einer einzelnen Zeitskala anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f24d-107">The profiler can correlate these two based on time and display them together along a single timeline.</span></span> <span data-ttu-id="8f24d-108">Ablaufverfolgungsereignisse bieten Ihnen mehr Details, während Leistungsindikatoren eine Aggregatsicht liefern.</span><span class="sxs-lookup"><span data-stu-id="8f24d-108">Trace events will give you more details while Performance counters give you an aggregate view.</span></span> <span data-ttu-id="8f24d-109">Informationen zum Erstellen und Ausführen von Ablaufverfolgungen finden Sie unter [Erstellen von Profilerablaufverfolgungen für Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8f24d-109">For information about how to create and run traces, see [Create Profiler Traces for Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span></span>  
  
 <span data-ttu-id="8f24d-110">In der folgenden Tabelle werden die Themen in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f24d-110">The following table describes the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f24d-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8f24d-111">In This Section</span></span>  
  
|<span data-ttu-id="8f24d-112">Thema</span><span class="sxs-lookup"><span data-stu-id="8f24d-112">Topic</span></span>|<span data-ttu-id="8f24d-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8f24d-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8f24d-114">Einführung in die Überwachung von Analysis Services mit SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8f24d-114">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|<span data-ttu-id="8f24d-115">Beschreibt das Verwenden von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] zum Überwachen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="8f24d-115">Describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>|  
|[<span data-ttu-id="8f24d-116">Erstellen von Profilerablaufverfolgungen für Replay &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8f24d-116">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)|<span data-ttu-id="8f24d-117">Beschreibt die Anforderungen für das Erstellen einer Ablaufverfolgung zur Wiedergabe mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f24d-117">Describes the requirements for creating a trace for replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="8f24d-118">Analysis Services-Ablaufverfolgungsereignisse</span><span class="sxs-lookup"><span data-stu-id="8f24d-118">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)|<span data-ttu-id="8f24d-119">Beschreibt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Ereignisklassen.</span><span class="sxs-lookup"><span data-stu-id="8f24d-119">Describes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] event classes.</span></span> <span data-ttu-id="8f24d-120">Diese Ereignisklassen sind Aktionen zugeordnet, die von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generiert werden, und werden zum Wiedergeben von Ablaufverfolgungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f24d-120">These event classes map to actions generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and are used for trace replays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f24d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f24d-121">See Also</span></span>  
 [<span data-ttu-id="8f24d-122">Überwachen einer Instanz von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8f24d-122">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  
