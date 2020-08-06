---
title: Eigenschaften der Ablauf Verfolgungs Vorlage (Registerkarte Ereignis Auswahl) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetemplateproperties.eventsselection.f1
helpviewer_keywords:
- Trace Template Properties dialog box
ms.assetid: 5b202457-ab42-4902-8012-7f3f40aa09f5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: da497db6e9373c63836753dc2be96deb3ce90244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724089"
---
# <a name="trace-template-properties-events-selection-tab"></a><span data-ttu-id="f2b37-102">Eigenschaften der Ablaufverfolgungsvorlage (Registerkarte Ereignisauswahl)</span><span class="sxs-lookup"><span data-stu-id="f2b37-102">Trace Template Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="f2b37-103">Die Registerkarte **Ereignisauswahl** im Dialogfeld **Eigenschaften der Ablaufverfolgungsvorlage** wird zum Anzeigen, Bearbeiten und Angeben von Ereignisklassen und Datenspalten verwendet, die in eine [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] -Ablaufverfolgungsvorlage eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2b37-103">Use the **Events Selection** tab of the **Trace Template Properties** dialog box to view, edit, or specify event classes and data columns to include in a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace template.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2b37-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f2b37-104">Options</span></span>  
 <span data-ttu-id="f2b37-105">Spalte**Ereignisse**</span><span class="sxs-lookup"><span data-stu-id="f2b37-105">**Events** column</span></span>  
 <span data-ttu-id="f2b37-106">Geben Sie die Ereignisse an, für die eine Ablaufverfolgung ausgeführt werden soll, indem Sie das betreffende Kontrollkästchen in der Ereignisspalte aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f2b37-106">Specify events that should be traced by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="f2b37-107">Die Ereignisse sind nach Ereigniskategorien angeordnet.</span><span class="sxs-lookup"><span data-stu-id="f2b37-107">Events are organized by event category.</span></span>  
  
 <span data-ttu-id="f2b37-108">Wenn Sie auf der Registerkarte **Allgemein** die Option **Neue Vorlage auf vorhandener basieren** auswählen, werden die Ereignisse der angegebenen Vorlage entsprechend automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f2b37-108">If you selected **Base new template on existing one** on the **General** tab, events are automatically selected according to the specified template.</span></span> <span data-ttu-id="f2b37-109">Weitere Informationen zu Ereignisklassen finden Sie unter [Ereignisklassen in SQL Server – Referenz](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f2b37-109">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="f2b37-110">Datenspalten</span><span class="sxs-lookup"><span data-stu-id="f2b37-110">Data columns</span></span>  
 <span data-ttu-id="f2b37-111">Geben Sie die Datenspalten an, für die eine Ablaufverfolgung ausgeführt werden soll, indem Sie das Kontrollkästchen für das Ereignis und die benötigte Datenspalte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f2b37-111">Specify data columns that should be traced by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="f2b37-112">Die relevanten Ereignisspalten werden standardmäßig für die einzelnen in die Ablaufverfolgung eingeschlossenen Ereignisse aktiviert, sofern das Kontrollkästchen des entsprechenden Ereignisses aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f2b37-112">All relevant event columns are checked by default for each event included in the trace, if the checkbox corresponding to the event is checked.</span></span> <span data-ttu-id="f2b37-113">Wenn Sie auf der Registerkarte **Allgemein** die Option **Neue Vorlage auf vorhandener basieren** aktiviert haben, werden die Datenspalten und Filter der angegebenen Vorlage entsprechend automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f2b37-113">If you checked **Base new template on existing one** on the **General** tab, data columns and filters are automatically selected according to the specified template.</span></span>  
  
 <span data-ttu-id="f2b37-114">Sie können Filter festlegen, indem Sie auf die Spaltenüberschrift klicken und die Filterkriterien eingeben.</span><span class="sxs-lookup"><span data-stu-id="f2b37-114">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="f2b37-115">Gefilterte Datenspalten sind im Dialogfeld **Filter bearbeiten** links neben der Spaltenbezeichnung durch ein Filtersymbol gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f2b37-115">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="f2b37-116">**Alle Ereignisse anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f2b37-116">**Show all events**</span></span>  
 <span data-ttu-id="f2b37-117">Zeigt alle verfügbaren Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="f2b37-117">Show all available events.</span></span> <span data-ttu-id="f2b37-118">Diese Option ist standardmäßig aktiviert, wenn Sie eine neue Vorlage erstellen, die nicht auf einer vorhandenen Vorlage basiert.</span><span class="sxs-lookup"><span data-stu-id="f2b37-118">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="f2b37-119">Deaktivieren Sie diese Option, um alle nicht ausgewählten Ereignisse im Raster **Ereignisauswahl** auszublenden.</span><span class="sxs-lookup"><span data-stu-id="f2b37-119">Uncheck to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="f2b37-120">**Alle Spalten anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f2b37-120">**Show all columns**</span></span>  
 <span data-ttu-id="f2b37-121">Zeigt alle verfügbaren Datenspalten an.</span><span class="sxs-lookup"><span data-stu-id="f2b37-121">Show all available data columns.</span></span> <span data-ttu-id="f2b37-122">Diese Option ist standardmäßig aktiviert, wenn Sie eine neue Vorlage erstellen, die nicht auf einer vorhandenen Vorlage basiert.</span><span class="sxs-lookup"><span data-stu-id="f2b37-122">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="f2b37-123">Deaktivieren Sie diese Option, um alle nicht ausgewählten Datenspalten im Raster **Ereignisauswahl** auszublenden.</span><span class="sxs-lookup"><span data-stu-id="f2b37-123">Uncheck to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="f2b37-124">**Spaltenfilter**</span><span class="sxs-lookup"><span data-stu-id="f2b37-124">**Column Filters**</span></span>  
 <span data-ttu-id="f2b37-125">Öffnet das Dialogfeld **Filter bearbeiten**, in dem links neben der Datenspaltenbezeichnung ein Filtersymbol angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f2b37-125">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the data column label.</span></span> <span data-ttu-id="f2b37-126">Mithilfe des Dialogfelds **Filter bearbeiten** können Sie Datenspaltenfilter bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f2b37-126">Use the **Edit Filter** dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="f2b37-127">**Spalten organisieren**</span><span class="sxs-lookup"><span data-stu-id="f2b37-127">**Organize Columns**</span></span>  
 <span data-ttu-id="f2b37-128">Ändert die Reihenfolge der Spalten in der Ablaufverfolgung und gruppiert die Ergebnisse in einer oder mehreren Spalten.</span><span class="sxs-lookup"><span data-stu-id="f2b37-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b37-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2b37-129">See Also</span></span>  
 <span data-ttu-id="f2b37-130">[Angeben von Ereignissen und Datenspalten für eine Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f2b37-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f2b37-131">[Organisieren der in einer Ablauf Verfolgung angezeigten Spalten &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f2b37-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f2b37-132">[Ereignisse in einer Ablauf Verfolgung &#40;SQL Server Profiler Filtern&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f2b37-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f2b37-133">[Filter Informationen &#40;SQL Server Profiler anzeigen&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f2b37-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f2b37-134">[Ändern eines Filters &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f2b37-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f2b37-135">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="f2b37-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="f2b37-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f2b37-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
