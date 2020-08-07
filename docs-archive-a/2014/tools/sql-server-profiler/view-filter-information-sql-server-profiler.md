---
title: Anzeigen von Filter Informationen (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: 8d002dea-376a-452c-b3ca-3e93656ed75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 931b83f8087d446cfc7b08d9582cbad5b02cf671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615736"
---
# <a name="view-filter-information-sql-server-profiler"></a><span data-ttu-id="a3ace-102">Anzeigen von Filterinformationen (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a3ace-102">View Filter Information (SQL Server Profiler)</span></span>
  <span data-ttu-id="a3ace-103">In diesem Thema wird beschrieben, wie Filter von Datenspalten für Ereignisklassen mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="a3ace-103">This topic describes how to view filters on data columns for event classes by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="a3ace-104">So zeigen Sie Filterinformationen an</span><span class="sxs-lookup"><span data-stu-id="a3ace-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="a3ace-105">Öffnen Sie eine Ablaufverfolgungsdatei, eine Ablaufverfolgungstabelle oder ein SQL-Skript, und klicken Sie im Menü **Datei** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a3ace-105">Open a trace file, trace table, or SQL script, and on the **File** menu, click **Properties**.</span></span> <span data-ttu-id="a3ace-106">Wenn Sie eine Ablaufverfolgungsvorlage bearbeiten oder eine neue Ablaufverfolgung erstellen, können Sie diesen Schritt auslassen.</span><span class="sxs-lookup"><span data-stu-id="a3ace-106">If you are editing a trace template or creating a new trace, skip this step.</span></span>  
  
2.  <span data-ttu-id="a3ace-107">Klicken Sie auf der Registerkarte **Ereignisauswahl** mit der rechten Maustaste auf den Namen der Datenspalte für den anzuzeigenden Filter, und klicken Sie dann auf **Spaltenfilter bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a3ace-107">On the **Events Selection** tab, right-click the data column name for the filter you want to view, and click **Edit Column Filter**.</span></span>  
  
3.  <span data-ttu-id="a3ace-108">Erweitern Sie im Dialogfeld **Filter bearbeiten** die Vergleichsoperatoren für den Filter, um den zugewiesenen Wert für das angegebene Kriterium anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a3ace-108">In the **Edit Filter** dialog box, expand the filter comparison operators to see the assigned value for the specified criterion.</span></span> <span data-ttu-id="a3ace-109">Wiederholen Sie Schritt 2 und 3 für alle Spalten, für die Sie Filterinformationen anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="a3ace-109">Repeat Steps 2 and 3 for all columns for which you want to view filter information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3ace-110">Vergleichsoperatoren mit zugewiesenen Werten sind fett formatiert.</span><span class="sxs-lookup"><span data-stu-id="a3ace-110">Comparison operators with assigned values are formatted bold.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ace-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3ace-111">See Also</span></span>  
 [<span data-ttu-id="a3ace-112">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a3ace-112">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
