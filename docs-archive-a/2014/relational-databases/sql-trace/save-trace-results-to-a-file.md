---
title: Speichern von Ablaufverfolgungsergebnissen in einer Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 74f80667-62f3-4e14-bb1a-f0c2b6ef3402
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 644fc812bbb4863c336ff2f53f5b2d67ee0a4d5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609041"
---
# <a name="save-trace-results-to-a-file"></a><span data-ttu-id="94f04-102">Speichern von Ablaufverfolgungsergebnissen in einer Datei</span><span class="sxs-lookup"><span data-stu-id="94f04-102">Save Trace Results to a File</span></span>
  <span data-ttu-id="94f04-103">Ablaufverfolgungsergebnisse können in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="94f04-103">You can save trace results to a file.</span></span> <span data-ttu-id="94f04-104">Die Ablaufverfolgungsergebnisse werden in eine Ablaufverfolgungsdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="94f04-104">A trace file is a file where the trace results are written.</span></span> <span data-ttu-id="94f04-105">Eine Ablaufverfolgungsdatei kann in einem lokalen Verzeichnis (z. B.\\*Ordnername*\\*Dateiname.trc*) oder in einem Netzwerkverzeichnis (z. B. \\\Computername\Freigabename\Dateiname.trc) gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="94f04-105">A trace file can be located either in a local directory (such as C:\\*foldername*\\*filename.trc*) or a network directory (such as \\\computername\sharename\filename.trc).</span></span>  
  
 <span data-ttu-id="94f04-106">Die Ablaufverfolgungsdateien können für die folgenden Aufgaben verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="94f04-106">You can use the trace files to do the following:</span></span>  
  
-   <span data-ttu-id="94f04-107">Wiedergeben von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="94f04-107">Replay traces</span></span>  
  
-   <span data-ttu-id="94f04-108">Überwachen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94f04-108">Audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="94f04-109">Ausführen einer Leistungsanalyse</span><span class="sxs-lookup"><span data-stu-id="94f04-109">Conduct performance analysis</span></span>  
  
-   <span data-ttu-id="94f04-110">Korrelation von Ablaufverfolgungsereignissen mit Leistungsindikatoren zur Optimierung der Suche nach Problemen</span><span class="sxs-lookup"><span data-stu-id="94f04-110">Correlate trace events with performance counters to enhance problem detection</span></span>  
  
-   <span data-ttu-id="94f04-111">Datenbankoptimierungsratgeber-Analyse</span><span class="sxs-lookup"><span data-stu-id="94f04-111">Perform Database Engine Tuning Advisor analysis</span></span>  
  
-   <span data-ttu-id="94f04-112">Ausführen der Abfrageoptimierung</span><span class="sxs-lookup"><span data-stu-id="94f04-112">Carry out query optimization</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="94f04-113">speichert Ablauf Verfolgungs Ergebnisse in einer Datei, wenn ein Pfad und ein Dateiname für das- **@tracefile** Argument der gespeicherten Prozedur **sp_trace_create**angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="94f04-113">saves trace results to a file when a path and file name are specified for the **@tracefile** argument of the stored procedure **sp_trace_create**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94f04-114">Wenn ein Pfad zur gespeicherten Prozedur **sp_trace_create** zum Speichern der Ablaufverfolgungsdatei angegeben ist, muss der Server Zugriff auf das Verzeichnis haben.</span><span class="sxs-lookup"><span data-stu-id="94f04-114">If a path is specified to the **sp_trace_create** stored procedure for saving the trace file, the directory must be accessible to the server.</span></span> <span data-ttu-id="94f04-115">Achten Sie auch darauf, dass es sich bei Angabe eines lokalen Verzeichnisses für **sp_trace_create**um ein lokales Verzeichnis auf dem Servercomputer handelt.</span><span class="sxs-lookup"><span data-stu-id="94f04-115">Also be aware that if a local directory is specified to **sp_trace_create**, it is a local directory on the server computer.</span></span>  
  
 <span data-ttu-id="94f04-116">Wenn [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] verwendet wird, können Sie Ablaufverfolgungsergebnisse in einer Datei oder Tabelle speichern.</span><span class="sxs-lookup"><span data-stu-id="94f04-116">If [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is used, it allows you to save trace results to a file or to a table.</span></span> <span data-ttu-id="94f04-117">Das Speichern von Ablaufverfolgungsergebnissen in einer Tabelle ermöglicht den gleichen Zugriff wie beim Speichern der Ablaufverfolgung in einer Datei. Außerdem können Sie für die Tabelle Abfragen ausführen, um nach bestimmten Ereignissen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="94f04-117">Saving trace results to a table allows the same access as saving the trace to a file plus you can query the table to search for specific events.</span></span>  
  
 <span data-ttu-id="94f04-118">Weitere Informationen zum Speichern von Ablaufverfolgungsergebnissen finden Sie unter [Speichern von Ablaufverfolgungsergebnissen in einer Tabelle &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) und [Speichern von Ablaufverfolgungsergebnissen in einer Datei &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="94f04-118">For more information about saving trace results, see [Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) and [Save Trace Results to a File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f04-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94f04-119">See Also</span></span>  
 <span data-ttu-id="94f04-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="94f04-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="94f04-121">[Erstellen einer Ablaufverfolgung &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="94f04-121">[Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span></span>  
 [<span data-ttu-id="94f04-122">Erstellen einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="94f04-122">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
