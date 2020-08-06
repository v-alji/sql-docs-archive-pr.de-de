---
title: Ändern eines Filters (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616883"
---
# <a name="modify-a-filter-sql-server-profiler"></a><span data-ttu-id="fd046-102">Ändern eines Filters (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fd046-102">Modify a Filter (SQL Server Profiler)</span></span>
  <span data-ttu-id="fd046-103">Sie können Ablaufverfolgungsvorlagen, die Ablaufverfolgungsdefinitionen enthalten, Filter hinzufügen, um die Anzahl der von einer Ablaufverfolgung gesammelten Ereignisse zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="fd046-103">You add filters to trace templates, which contain the trace definitions, to limit the number of events that are gathered by a trace.</span></span> <span data-ttu-id="fd046-104">Durch die Beschränkung der gesammelten Ereignisse können die bei der Ablaufverfolgung entstehenden Leistungseinbußen reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="fd046-104">Limiting the number of events gathered can reduce the performance effects of tracing.</span></span> <span data-ttu-id="fd046-105">Wenn Sie Filter für eine Ablaufverfolgungsvorlage einrichten und feststellen, dass bei der Ablaufverfolgung nicht die von Ihnen benötigten Informationen gesammelt werden, können Sie den Filter bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="fd046-105">If you set filters for a trace template and find that the trace is not gathering the kind of information that you need, you can edit the filter.</span></span>  
  
### <a name="to-modify-a-filter"></a><span data-ttu-id="fd046-106">So ändern Sie einen Filter</span><span class="sxs-lookup"><span data-stu-id="fd046-106">To modify a filter</span></span>  
  
1.  <span data-ttu-id="fd046-107">Öffnen Sie in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]die Vorlage für den Ablaufverfolgungsfilter, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="fd046-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], open the template for the trace filter that you want to modify.</span></span> <span data-ttu-id="fd046-108">Klicken Sie im Menü **Datei** auf **Vorlagen**, und wählen Sie dann **Vorlage bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="fd046-108">On the **File** menu, click **Templates**, and then choose **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="fd046-109">Wählen Sie auf der Registerkarte **Allgemein** des Dialogfelds **Eigenschaften der Ablaufverfolgungsvorlage** eine Vorlage aus der Liste **Vorlagennamen auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="fd046-109">In the **General** tab of the **Trace Template Properties** dialog, select a template from the **Select template name** list.</span></span>  
  
3.  <span data-ttu-id="fd046-110">Klicken Sie auf die Registerkarte **Ereignisauswahl** .</span><span class="sxs-lookup"><span data-stu-id="fd046-110">Click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="fd046-111">Die Registerkarte **Ereignisauswahl** enthält ein Rastersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="fd046-111">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="fd046-112">Bei dem Rastersteuerelement handelt es sich um eine Tabelle, die alle bei der Ablaufverfolgung zu berücksichtigenden Ereignisklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="fd046-112">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="fd046-113">Die Tabelle enthält für jede Ereignisklasse eine Zeile.</span><span class="sxs-lookup"><span data-stu-id="fd046-113">The table contains one row for each event class.</span></span> <span data-ttu-id="fd046-114">Abhängig von dem Typ und der Version des Servers, zu dem eine Verbindung hergestellt wurde, können sich die Ereignisklassen geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="fd046-114">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="fd046-115">Die Ereignisklassen werden in der Spalte **Events**des Rasters identifiziert und nach Ereigniskategorie gruppiert.</span><span class="sxs-lookup"><span data-stu-id="fd046-115">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="fd046-116">In den übrigen Spalten sind die Datenspalten aufgeführt, die für jede Ereignisklasse zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="fd046-116">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
4.  <span data-ttu-id="fd046-117">Klicken Sie auf **Spaltenfilter**.</span><span class="sxs-lookup"><span data-stu-id="fd046-117">Click **Column Filters**.</span></span>  
  
5.  <span data-ttu-id="fd046-118">Klicken Sie im Dialogfeld **Filter bearbeiten** auf den Wert neben dem zu bearbeitenden Vergleichsoperator, und geben Sie einen neuen Wert ein bzw. löschen Sie einen Wert.</span><span class="sxs-lookup"><span data-stu-id="fd046-118">In the **Edit Filter** dialog box, click the value next to the comparison operator that you want to edit, and type the new value or delete a value.</span></span> <span data-ttu-id="fd046-119">Darüber hinaus können Sie zusätzliche Filter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fd046-119">You can also add additional filters.</span></span>  
  
6.  <span data-ttu-id="fd046-120">Klicken Sie auf **OK** , und speichern Sie die Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fd046-120">Click **OK** and save the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd046-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd046-121">See Also</span></span>  
 [<span data-ttu-id="fd046-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fd046-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
