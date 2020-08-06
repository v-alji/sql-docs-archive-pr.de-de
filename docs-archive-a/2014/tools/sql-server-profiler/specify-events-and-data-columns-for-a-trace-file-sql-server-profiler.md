---
title: Angeben von Ereignissen und Datenspalten für eine Ablaufverfolgungsdatei (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- adding events
- traces [SQL Server], data columns
- deleting events
- removing events
- traces [SQL Server], events
ms.assetid: 7da715a3-2f03-4063-b6a4-20fd7b44e675
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb8639a187f1e7e091e382031886659bd47d7d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607468"
---
# <a name="specify-events-and-data-columns-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="3cb92-102">Angeben von Ereignissen und Datenspalten für eine Ablaufverfolgungsdatei (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="3cb92-102">Specify Events and Data Columns for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="3cb92-103">In diesem Thema wird beschrieben, wie Ereignisklassen und Datenspalten mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3cb92-103">This topic describes how to specify event classes and data columns for traces by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-specify-events-and-data-columns-for-a-trace"></a><span data-ttu-id="3cb92-104">So geben Sie Ereignisse und Datenspalten für eine Ablaufverfolgung an</span><span class="sxs-lookup"><span data-stu-id="3cb92-104">To specify events and data columns for a trace</span></span>  
  
1.  <span data-ttu-id="3cb92-105">Klicken Sie im Dialogfeld **Ablaufverfolgungseigenschaften** oder **Eigenschaften der Ablaufverfolgungsvorlage** auf die Registerkarte **Ereignisauswahl** .</span><span class="sxs-lookup"><span data-stu-id="3cb92-105">On the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="3cb92-106">Die Registerkarte **Ereignisauswahl** enthält ein Rastersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="3cb92-106">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="3cb92-107">Bei dem Rastersteuerelement handelt es sich um eine Tabelle, die alle bei der Ablaufverfolgung zu berücksichtigenden Ereignisklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="3cb92-107">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="3cb92-108">Die Tabelle enthält für jede Ereignisklasse eine Zeile.</span><span class="sxs-lookup"><span data-stu-id="3cb92-108">The table contains one row for each event class.</span></span> <span data-ttu-id="3cb92-109">Die Ereignisklassen können sich leicht voneinander unterscheiden. Dies hängt vom Typ und der Version des Servers ab, zu dem eine Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="3cb92-109">The event classes can differ slightly depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="3cb92-110">Die Ereignisklassen werden in der Spalte **Events**des Rasters identifiziert und nach Ereigniskategorie gruppiert.</span><span class="sxs-lookup"><span data-stu-id="3cb92-110">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="3cb92-111">In den übrigen Spalten sind die Datenspalten aufgeführt, die für jede Ereignisklasse zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="3cb92-111">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="3cb92-112">Klicken Sie im Dialogfeld **Ereignisauswahl**das Rastersteuerelement, um Ereignisse und Datenspalten zur Ablaufverfolgungsdatei hinzuzufügen oder aus ihr zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3cb92-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file.</span></span>  
  
3.  <span data-ttu-id="3cb92-113">Um Ereignisse aus der Ablaufverfolgung zu entfernen, deaktivieren Sie das Kontrollkästchen in der **Ereignisse** -Spalte für jede Ereignisklasse.</span><span class="sxs-lookup"><span data-stu-id="3cb92-113">To remove events from the trace, clear the check box in the **Events** column for each event class.</span></span>  
  
4.  <span data-ttu-id="3cb92-114">Um Ereignisse in einer Ablaufverfolgung einzuschließen, aktivieren Sie das Kontrollkästchen in der **Ereignisse** -Spalte für jede Ereignisklasse, oder aktivieren Sie eine Datenspalte, die sich auf ein Ereignis bezieht.</span><span class="sxs-lookup"><span data-stu-id="3cb92-114">To include events in a trace, check the box in the **Events** column for each event class, or check a data column that corresponds to an event.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3cb92-115">Wenn die Ablaufverfolgung mit Systemmonitordaten abhängig wird, müssen die Datenspalten **Startzeit** und **Beendigungszeit** in der Ablaufverfolgung eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="3cb92-115">If the trace is going be correlated with System Monitor or Performance Monitor data, both **Start Time** and **End Time** data columns must be included in the trace.</span></span>  
  
 <span data-ttu-id="3cb92-116">Wenn Sie eine Ereignisklasse einschließen, wird auch jede zugeordnete Datenspalte in die Ablaufverfolgung aufgenommen, wenn Sie das Kontrollkästchen aktiviert haben, das mit einem Ereignis korrespondiert.</span><span class="sxs-lookup"><span data-stu-id="3cb92-116">When you include an event class, every associated data column is also included to the trace, if you have checked the box corresponding to an event.</span></span> <span data-ttu-id="3cb92-117">Wenn Sie das Kontrollkästchen für eine bestimmte Spalte aktiviert haben, wird nur diese Spalte in die Ablaufverfolgung aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="3cb92-117">If you checked the box for a particular column, only that column is included in the trace.</span></span>  
  
1.  <span data-ttu-id="3cb92-118">Um Datenspalten aus einer Ereignisklasse zu entfernen, deaktivieren Sie die Kontrollkästchen der Datenspalte in der Ereignisklassenzeile, oder klicken Sie mit der rechten Maustaste auf den Spaltenheader, und wählen Sie die Option **Spaltenauswahl aufheben** aus.</span><span class="sxs-lookup"><span data-stu-id="3cb92-118">To remove data columns from an event class, clear the check boxes from the data column in the event class row, or right-click on the column header and select the **Deselect column** option.</span></span>  
  
2.  <span data-ttu-id="3cb92-119">Wenden Sie optional Filter auf die Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="3cb92-119">Optionally, apply filters to the trace.</span></span> <span data-ttu-id="3cb92-120">Weitere Informationen finden Sie unter [Filtern von Ereignissen in einer Ablaufverfolgung &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="3cb92-120">For more information, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb92-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cb92-121">See Also</span></span>  
 [<span data-ttu-id="3cb92-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3cb92-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
