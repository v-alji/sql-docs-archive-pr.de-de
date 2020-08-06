---
title: Limit für SQL Server Profiler-Leistungsindikatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.performancecounterlimit.f1
helpviewer_keywords:
- Performance Counters List dialog box
ms.assetid: d10140ef-36c4-449c-b365-1cff1b2524e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27bda135abaf9d91b078e36a69a87098a734acbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721694"
---
# <a name="sql-server-profiler---performance-counters-limit"></a><span data-ttu-id="c66ca-102">SQL Server Profiler - Beschränken der Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="c66ca-102">SQL Server Profiler - Performance Counters Limit</span></span>
  <span data-ttu-id="c66ca-103">Mithilfe des Dialogfelds zum Beschränken der Leistungsindikatoren, können Sie die Informationen aus einer Leistungsprotokolldatei des Systemmonitors beschränken, wenn er mit einer [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] -Ablaufverfolgung korreliert wird.</span><span class="sxs-lookup"><span data-stu-id="c66ca-103">Use the Performance Counters Limit dialog box to limit the information from a System Monitor performance log file when correlating it with a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace.</span></span> <span data-ttu-id="c66ca-104">Mithilfe dieses Dialogfelds können Sie Indikatoren auswählen, die angezeigt und für die Korrelation verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c66ca-104">You can use this dialog box to select counters that should be displayed and used for correlation.</span></span>  
  
 <span data-ttu-id="c66ca-105">Das Dialogfeld zum **Beschränken der Leistungsindikatoren** wird mit den Leistungsobjekten und -indikatoren aufgefüllt, die in der Leistungsprotokolldatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c66ca-105">The **Performance Counters Limit** dialog box is populated with the performance objects and counters that the performance log file contains.</span></span>  
  
### <a name="to-select-performance-objects-and-counters-to-correlate-with-a-trace"></a><span data-ttu-id="c66ca-106">So wählen Sie Leistungsobjekte und -indikatoren aus, die mit einer Ablaufverfolgung korreliert werden sollen</span><span class="sxs-lookup"><span data-stu-id="c66ca-106">To select performance objects and counters to correlate with a trace</span></span>  
  
1.  <span data-ttu-id="c66ca-107">Erweitern Sie ein Leistungsobjekt, um anzuzeigen, welche Indikatoren in der Leistungsprotokolldatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c66ca-107">Expand a performance object to see which counters are included in the performance log file.</span></span>  
  
2.  <span data-ttu-id="c66ca-108">Aktivieren Sie die Indikatoren, die mit der [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] -Ablaufverfolgungsdatei korreliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c66ca-108">Check the counters that you want to correlate with the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace file.</span></span>  
  
     <span data-ttu-id="c66ca-109">Wenn Sie alle Indikatoren für ein Leistungsobjekt auswählen möchten, setzen Sie in das Feld neben dem Leistungsobjekt ein Häkchen.</span><span class="sxs-lookup"><span data-stu-id="c66ca-109">If you want to select all counters for a performance object, check the box that is adjacent to the performance object.</span></span> <span data-ttu-id="c66ca-110">Wenn Sie den obersten Knoten aktivieren, der für den Computer steht, werden alle Leistungsobjekte und -indikatoren ausgewählt, die in der Leistungsprotokolldatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c66ca-110">Checking the topmost node, which indicates the computer, selects all performance objects and counters contained in the performance log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c66ca-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c66ca-111">See Also</span></span>  
 [<span data-ttu-id="c66ca-112">Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="c66ca-112">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data.md)  
  
  
