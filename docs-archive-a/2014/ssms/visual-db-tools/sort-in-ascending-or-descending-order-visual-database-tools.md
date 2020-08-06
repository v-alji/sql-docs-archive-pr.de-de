---
title: Sortieren in aufsteigender oder absteigender Reihenfolge (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b5e6b00f62cfc297cc5930bc8cf3a41314a2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621781"
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a><span data-ttu-id="daef8-102">Sortieren in aufsteigender oder absteigender Reihenfolge (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="daef8-102">Sort in Ascending or Descending Order (Visual Database Tools)</span></span>
  <span data-ttu-id="daef8-103">Mithilfe der Schlüsselwörter `ASC` und `DESC` und der `ORDER BY`-Klausel können Abfrageergebnisse in einer oder mehreren Spalten des Resultsets in auf- oder absteigender Reihenfolge sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="daef8-103">You can sort query results in ascending or descending order on one or more of the columns in the result set by using the `ASC` or `DESC` keywords with the `ORDER BY` clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="daef8-104">Die Sortierreihenfolge wird teilweise durch die Sortierreihenfolge der Spalte bestimmt.</span><span class="sxs-lookup"><span data-stu-id="daef8-104">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="daef8-105">Sie können die Sortierreihenfolge im [Dialogfeld Sortierreihenfolge](visual-database-tools.md)ändern.</span><span class="sxs-lookup"><span data-stu-id="daef8-105">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="daef8-106">Bei der folgenden Prozedur wird vorausgesetzt, dass im Abfrage- und Sicht-Designer eine Abfrage geöffnet ist, in der zum Sortieren einer oder mehrerer Spalten die ORDER BY-Klausel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="daef8-106">The following procedure assumes that you have a query open in Query and View Designer that uses the ORDER BY clause to sort one or more columns.</span></span>  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a><span data-ttu-id="daef8-107">So geben Sie die Sortierreihenfolge der Ergebnisse an und ändern diese</span><span class="sxs-lookup"><span data-stu-id="daef8-107">To specify or change the order in which results are sorted</span></span>  
  
1.  <span data-ttu-id="daef8-108">Klicken Sie im [Kriterienbereich](criteria-pane-visual-database-tools.md)für die neu zu sortierende Spalte auf das Feld **Sortierungsart** .</span><span class="sxs-lookup"><span data-stu-id="daef8-108">In the [Criteria pane](criteria-pane-visual-database-tools.md), click the **Sort Type** field for the column that you want to reorder.</span></span>  
  
2.  <span data-ttu-id="daef8-109">Wählen Sie **Aufsteigend** oder **Absteigend** aus, um die Sortierreihenfolge für die Spalte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="daef8-109">Choose **Ascending** or **Descending** to specify the sort order for the column.</span></span>  
  
 <span data-ttu-id="daef8-110">Beachten Sie beim Arbeiten im Kriterienbereich, dass die UNION-Klausel der Abfrage entsprechend der zuletzt ausgeführten Aktionen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="daef8-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="daef8-111">Geben Sie beim Sortieren mehrerer Spalten mithilfe der Spalte Sortierreihenfolge die Reihenfolge an, in der die Spalten relativ zueinander durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="daef8-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column.</span></span> <span data-ttu-id="daef8-112">Weitere Informationen finden Sie unter [Sortieren mehrerer Spalten in Abfragen &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="daef8-112">For more information, see [Sort Multiple Columns in Queries &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daef8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daef8-113">See Also</span></span>  
 <span data-ttu-id="daef8-114">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="daef8-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="daef8-115">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="daef8-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="daef8-116">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="daef8-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
