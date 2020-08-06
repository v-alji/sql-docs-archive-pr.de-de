---
title: Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- correlating trace with log data
- logs [SQL Server], traces
- Profiler [SQL Server Profiler], correlating trace with log data
- traces [SQL Server], logs
- SQL Server Profiler, correlating trace with log data
ms.assetid: 1e4412c8-d27c-4aae-9b35-214128d1d00a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 879441c948f0ad04b971159a37ec0dcec90e3ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694961"
---
# <a name="correlate-a-trace-with-windows-performance-log-data"></a><span data-ttu-id="ab50f-102">Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten</span><span class="sxs-lookup"><span data-stu-id="ab50f-102">Correlate a Trace with Windows Performance Log Data</span></span>
  <span data-ttu-id="ab50f-103">Mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]können Sie ein Microsoft Windows-Leistungsprotokoll öffnen, die Leistungsindikatoren auswählen, die Sie mit einer Ablaufverfolgung korrelieren möchten, und die ausgewählten Leistungsindikatoren zusammen mit der Ablaufverfolgung auf der grafischen Benutzeroberfläche von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ab50f-103">Using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can open a Microsoft Windows performance log, choose the counters you want to correlate with a trace, and display the selected performance counters alongside the trace in the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] graphical user interface.</span></span> <span data-ttu-id="ab50f-104">Wenn Sie ein Ereignis im Ablaufverfolgungsfenster auswählen, zeigt ein senkrechter roter Strich im Datenfensterbereich des Systemmonitors von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] an, welche Leistungsprotokolldaten mit dem ausgewählten Ablaufverfolgungsereignis korrelieren.</span><span class="sxs-lookup"><span data-stu-id="ab50f-104">When you select an event in the trace window, a vertical red bar in the System Monitor data window pane of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indicates the performance log data that correlates with the selected trace event.</span></span>  
  
 <span data-ttu-id="ab50f-105">Öffnen Sie eine Ablaufverfolgungsdatei oder -tabelle, die die Datenspalten **StartTime** und **EndTime** enthält, und klicken Sie dann im **im Menü**Datei[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auf **Leistungsdaten importieren**, um eine Ablaufverfolgung mit Leistungsindikatoren zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="ab50f-105">To correlate a trace with performance counters, open a trace file or table that contains the **StartTime** and **EndTime** data columns, and then click **Import Performance Data** on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **File** menu.</span></span> <span data-ttu-id="ab50f-106">Anschließend können Sie das Leistungsprotokoll öffnen und die Systemmonitor-Objekte und -Leistungsindikatoren auswählen, die Sie mit der Ablaufverfolgung korrelieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ab50f-106">You can then open a performance log, and select the System Monitor objects and counters that you want to correlate with the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab50f-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab50f-107">See Also</span></span>  
 [<span data-ttu-id="ab50f-108">Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="ab50f-108">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](correlate-a-trace-with-windows-performance-log-data.md)  
  
  
