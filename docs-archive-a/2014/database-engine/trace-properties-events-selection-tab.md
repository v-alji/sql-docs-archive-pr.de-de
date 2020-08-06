---
title: Ablauf Verfolgungs Eigenschaften (Registerkarte Ereignis Auswahl) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.eventsselection.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: e1892f24-7272-4d5d-8926-6150cc82b2c3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11f4725865d39c21e36f5fd09eaf2afd4cde3017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718634"
---
# <a name="trace-properties-events-selection-tab"></a><span data-ttu-id="39d16-102">Ablaufverfolgungseigenschaften (Registerkarte 'Ereignisauswahl')</span><span class="sxs-lookup"><span data-stu-id="39d16-102">Trace Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="39d16-103">Mithilfe der Registerkarte **Ereignisauswahl** im Dialogfeld **Ablaufverfolgungseigenschaften** können Sie die Ablaufverfolgung von Ereignissen oder Datenspalten anzeigen und angeben.</span><span class="sxs-lookup"><span data-stu-id="39d16-103">Use the **Events Selection** tab of the **Trace Properties** dialog box to view or specify traced events and data columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="39d16-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="39d16-104">Options</span></span>  
 <span data-ttu-id="39d16-105">Spalte**Ereignisse**</span><span class="sxs-lookup"><span data-stu-id="39d16-105">**Events** column</span></span>  
 <span data-ttu-id="39d16-106">Gibt die Ereignisse an, für die eine Ablaufverfolgung ausgeführt wird, indem das betreffende Kontrollkästchen in der Ereignisspalte aktiviert bzw. deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="39d16-106">Specify traced events by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="39d16-107">Die**Ereignisse** sind nach Ereigniskategorien angeordnet.</span><span class="sxs-lookup"><span data-stu-id="39d16-107">**Events** are organized by event category.</span></span> <span data-ttu-id="39d16-108">In der Vorlage angegebene Ereignisklassen werden automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="39d16-108">Event classes specified in the template are automatically selected.</span></span> <span data-ttu-id="39d16-109">Weitere Informationen finden Sie unter [Ereignisklassen in SQL Server – Referenz](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="39d16-109">For more information, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="39d16-110">Datenspalten</span><span class="sxs-lookup"><span data-stu-id="39d16-110">Data columns</span></span>  
 <span data-ttu-id="39d16-111">Gibt die Datenspalten an, für die eine Ablaufverfolgung ausgeführt wird, indem das Kontrollkästchen für das Ereignis und die benötigte Datenspalte aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="39d16-111">Specify traced data columns by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="39d16-112">Alle relevanten Ereignisspalten sind für die in der Ablaufverfolgung enthaltenen Ereignisse standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="39d16-112">All relevant event columns are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="39d16-113">Sie können Filter festlegen, indem Sie auf die Spaltenüberschrift klicken und die Filterkriterien eingeben.</span><span class="sxs-lookup"><span data-stu-id="39d16-113">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="39d16-114">Gefilterte Datenspalten sind im Dialogfeld **Filter bearbeiten** links neben der Spaltenbezeichnung durch ein Filtersymbol gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="39d16-114">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="39d16-115">Weitere Informationen finden Sie unter [SQL Server Profiler – Filter bearbeiten](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span><span class="sxs-lookup"><span data-stu-id="39d16-115">For more information, see [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span></span>  
  
 <span data-ttu-id="39d16-116">**Alle Ereignisse anzeigen**</span><span class="sxs-lookup"><span data-stu-id="39d16-116">**Show all events**</span></span>  
 <span data-ttu-id="39d16-117">Zeigt alle verfügbaren Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="39d16-117">Show all available events.</span></span> <span data-ttu-id="39d16-118">Standardmäßig werden nur Zeilen im Raster **Ereignisauswahl** angezeigt, die ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="39d16-118">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="39d16-119">Deaktivieren Sie dieses Kontrollkästchen, um alle nicht ausgewählten Ereignisse im Raster **Ereignisauswahl** auszublenden.</span><span class="sxs-lookup"><span data-stu-id="39d16-119">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="39d16-120">**Alle Spalten anzeigen**</span><span class="sxs-lookup"><span data-stu-id="39d16-120">**Show all columns**</span></span>  
 <span data-ttu-id="39d16-121">Zeigt alle verfügbaren Datenspalten an.</span><span class="sxs-lookup"><span data-stu-id="39d16-121">Show all available data columns.</span></span> <span data-ttu-id="39d16-122">Standardmäßig werden nur ausgewählte Datenspalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39d16-122">By default, only data columns that are selected display.</span></span> <span data-ttu-id="39d16-123">Deaktivieren Sie dieses Kontrollkästchen, um alle nicht ausgewählten Datenspalten im Raster **Ereignisauswahl** auszublenden.</span><span class="sxs-lookup"><span data-stu-id="39d16-123">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="39d16-124">**Spaltenfilter**</span><span class="sxs-lookup"><span data-stu-id="39d16-124">**Column Filters**</span></span>  
 <span data-ttu-id="39d16-125">Öffnet das Dialogfeld **Filter bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="39d16-125">Launches the **Edit Filter** dialog box.</span></span> <span data-ttu-id="39d16-126">Mithilfe dieses Dialogfelds können Sie Datenspaltenfilter bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="39d16-126">You can use this dialog to edit data column filters.</span></span>  
  
 <span data-ttu-id="39d16-127">**Spalten organisieren**</span><span class="sxs-lookup"><span data-stu-id="39d16-127">**Organize Columns**</span></span>  
 <span data-ttu-id="39d16-128">Ändert die Reihenfolge der Spalten in der Ablaufverfolgung und gruppiert die Ergebnisse in einer oder mehreren Spalten.</span><span class="sxs-lookup"><span data-stu-id="39d16-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d16-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39d16-129">See Also</span></span>  
 <span data-ttu-id="39d16-130">[Angeben von Ereignissen und Datenspalten für eine Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="39d16-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="39d16-131">[Organisieren der in einer Ablauf Verfolgung angezeigten Spalten &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="39d16-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="39d16-132">[Ereignisse in einer Ablauf Verfolgung &#40;SQL Server Profiler Filtern&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="39d16-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="39d16-133">[Filter Informationen &#40;SQL Server Profiler anzeigen&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="39d16-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="39d16-134">[Ändern eines Filters &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="39d16-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="39d16-135">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="39d16-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="39d16-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="39d16-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
