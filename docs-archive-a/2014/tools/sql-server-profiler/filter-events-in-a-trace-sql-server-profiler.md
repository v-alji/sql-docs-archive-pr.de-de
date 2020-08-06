---
title: Filtern von Ereignissen in einer Ablauf Verfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 0fd63573-3b35-4f67-9e1e-ed9aabee11a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: fef9dd6956d407011261c54f796a751a0bf94941
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723249"
---
# <a name="filter-events-in-a-trace-sql-server-profiler"></a><span data-ttu-id="fc56c-102">Filtern von Ereignissen in einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fc56c-102">Filter Events in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="fc56c-103">Durch Filter werden die in einer Ablaufverfolgung aufgezeichneten Ereignisse eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="fc56c-103">Filters limit the events collected in a trace.</span></span> <span data-ttu-id="fc56c-104">Ist kein Filter eingerichtet, werden alle Ereignisse der ausgewählten Ereignisklassen in der Ablaufverfolgungsausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fc56c-104">If a filter is not set, all events of the selected event classes are returned in the trace output.</span></span> <span data-ttu-id="fc56c-105">Es ist nicht obligatorisch, einen Filter für eine Ablaufverfolgung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fc56c-105">It is not mandatory to set a filter for a trace.</span></span> <span data-ttu-id="fc56c-106">Jedoch wird durch Filter der bei der Ablaufverfolgung entstehende Verarbeitungsaufwand verringert.</span><span class="sxs-lookup"><span data-stu-id="fc56c-106">However, a filter minimizes the overhead that is incurred during tracing.</span></span>  
  
 <span data-ttu-id="fc56c-107">Sie können Ablaufverfolgungsdefinitionen Filter hinzufügen, indem Sie die Registerkarte **Ereignisauswahl** des Dialogfelds **Ablaufverfolgungseigenschaften** oder des Dialogfelds **Eigenschaften der Ablaufverfolgungsvorlage** verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc56c-107">You add filters to trace definitions by using the **Events Selection** tab of the **Trace Properties** or **Trace Template Properties** dialog box.</span></span>  
  
### <a name="to-filter-events-in-a-trace"></a><span data-ttu-id="fc56c-108">So filtern Sie Ereignisse in einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="fc56c-108">To filter events in a trace</span></span>  
  
1.  <span data-ttu-id="fc56c-109">Klicken Sie im Dialogfeld **Ablaufverfolgungseigenschaften** oder **Eigenschaften der Ablaufverfolgungsvorlage** auf die Registerkarte **Ereignisauswahl** .</span><span class="sxs-lookup"><span data-stu-id="fc56c-109">In the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="fc56c-110">Die Registerkarte **Ereignisauswahl** enthält ein Rastersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="fc56c-110">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="fc56c-111">Bei dem Rastersteuerelement handelt es sich um eine Tabelle, die alle bei der Ablaufverfolgung zu berücksichtigenden Ereignisklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="fc56c-111">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="fc56c-112">Die Tabelle enthält für jede Ereignisklasse eine Zeile.</span><span class="sxs-lookup"><span data-stu-id="fc56c-112">The table contains one row for each event class.</span></span> <span data-ttu-id="fc56c-113">Abhängig von dem Typ und der Version des Servers, zu dem eine Verbindung hergestellt wurde, können sich die Ereignisklassen geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="fc56c-113">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="fc56c-114">Die Ereignisklassen werden in der Spalte **Events**des Rasters identifiziert und nach Ereigniskategorie gruppiert.</span><span class="sxs-lookup"><span data-stu-id="fc56c-114">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="fc56c-115">In den übrigen Spalten sind die Datenspalten aufgeführt, die für jede Ereignisklasse zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="fc56c-115">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="fc56c-116">Klicken Sie auf **Spaltenfilter.**</span><span class="sxs-lookup"><span data-stu-id="fc56c-116">Click **Column Filters.**</span></span>  
  
     <span data-ttu-id="fc56c-117">Die Registerkarte **Filter bearbeiten**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc56c-117">The **Edit Filter**dialog box appears.</span></span> <span data-ttu-id="fc56c-118">Die Registerkarte **Filter bearbeiten**enthält eine Liste von Vergleichsoperatoren, mit denen Sie Ereignisse in einer Ablaufverfolgung filtern können.</span><span class="sxs-lookup"><span data-stu-id="fc56c-118">The **Edit Filter**dialog box contains a list of comparison operators that you can use to filter events in a trace.</span></span>  
  
3.  <span data-ttu-id="fc56c-119">Wenn Sie einen Filter anwenden möchten, klicken Sie auf den Vergleichsoperator, und geben Sie den gewünschten Filterwert ein.</span><span class="sxs-lookup"><span data-stu-id="fc56c-119">To apply a filter, click the comparison operator, and type a value to use for the filter.</span></span>  
  
4.  <span data-ttu-id="fc56c-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc56c-120">Click **OK**.</span></span>  
  
 <span data-ttu-id="fc56c-121">**Überlegungen:**</span><span class="sxs-lookup"><span data-stu-id="fc56c-121">**Considerations:**</span></span>  
  
-   <span data-ttu-id="fc56c-122">Wenn Sie Filterbedingungen für die Datenspalten **StartTime** und **EndTime** der Registerkarte Ereignisauswahl festlegen, stellen Sie Folgendes sicher:</span><span class="sxs-lookup"><span data-stu-id="fc56c-122">If you set filter conditions on the **StartTime** and **EndTime** data columns of the Events Selection tab, then make sure that:</span></span>  
  
    -   <span data-ttu-id="fc56c-123">Das von Ihnen eingegebene Datum entspricht diesem Format: `YYYY/MM/DD HH:mm:sec`.</span><span class="sxs-lookup"><span data-stu-id="fc56c-123">The date you enter matches this format: `YYYY/MM/DD HH:mm:sec`.</span></span>  
  
         <span data-ttu-id="fc56c-124">ODER</span><span class="sxs-lookup"><span data-stu-id="fc56c-124">-OR-</span></span>  
  
    -   <span data-ttu-id="fc56c-125">Im Dialogfeld**Allgemeine Optionen** ist die Option **Einstellungen für Land/Region zum Anzeigen von Datums- und Uhrzeitwerten verwenden** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc56c-125">**Use regional settings to display date and time values** is checked in the **General Options** dialog box.</span></span> <span data-ttu-id="fc56c-126">Klicken Sie im **-Menü** Extras[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auf **Optionen**, um das Dialogfeld **Allgemeine Optionen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fc56c-126">To view the **General Options** dialog box, on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Tools** menu, click **Option**.</span></span>  
  
         <span data-ttu-id="fc56c-127">-UND-</span><span class="sxs-lookup"><span data-stu-id="fc56c-127">-AND-</span></span>  
  
    -   <span data-ttu-id="fc56c-128">Das von Ihnen eingegebene Datum liegt zwischen dem 1. Januar 1753 und dem 31. Dezember 9999.</span><span class="sxs-lookup"><span data-stu-id="fc56c-128">The date you enter is between January 1, 1753 and December 31, 9999.</span></span>  
  
-   <span data-ttu-id="fc56c-129">Wenn die Ablaufverfolgung für Ereignisse aus den Hilfsprogrammen **osql** oder **sqlcmd** ausgeführt wird, muss den Filtern in der **%** -Datenspalte immer **%** angehängt werden.</span><span class="sxs-lookup"><span data-stu-id="fc56c-129">If tracing events from the **osql** utility or from the **sqlcmd** utility, always append **%** to filters on the **TextData** data column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc56c-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc56c-130">See Also</span></span>  
 [<span data-ttu-id="fc56c-131">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fc56c-131">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
