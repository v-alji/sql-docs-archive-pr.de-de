---
title: Sortieren mit ORDER BY (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93bdb9ed01c7935c5b9dae543804fca758a9262d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722137"
---
# <a name="sort-with-order-by-visual-database-tools"></a><span data-ttu-id="4c593-102">Sortieren mit ORDER BY (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4c593-102">Sort with ORDER BY (Visual Database Tools)</span></span>
  <span data-ttu-id="4c593-103">Sie können mithilfe einer ORDER BY-Klausel die Abfrageergebnisse nach einer oder mehreren Spalten in den zurückgegebenen Zeilen sortieren.</span><span class="sxs-lookup"><span data-stu-id="4c593-103">You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause.</span></span> <span data-ttu-id="4c593-104">Sie können eine ORDER BY-Klausel definieren, indem Sie Optionen im Kriteriendetailbereich auswählen.</span><span class="sxs-lookup"><span data-stu-id="4c593-104">You can define an ORDER BY clause by choosing options in the Criteria Details pane.</span></span>  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a><span data-ttu-id="4c593-105">So sortieren Sie eine Abfrage mit einer ORDER BY-Klausel</span><span class="sxs-lookup"><span data-stu-id="4c593-105">To sort a query using an ORDER BY clause</span></span>  
  
1.  <span data-ttu-id="4c593-106">Öffnen Sie eine Abfrage, oder erstellen Sie eine neue.</span><span class="sxs-lookup"><span data-stu-id="4c593-106">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="4c593-107">Klicken Sie im [Kriterienbereich](visual-database-tools.md)auf die Spalte **Sortierungsart** für die Zeile, die der Spalte entspricht, nach der die Abfrageergebnisse sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4c593-107">In the [Criteria Pane](visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.</span></span>  
  
3.  <span data-ttu-id="4c593-108">Wählen Sie *Aufsteigend* oder *Absteigend* aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="4c593-108">Choose *Ascending* or *Descending* from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c593-109">Durch das Entfernen des Eintrags **Sortierungsart** für eine Spalte wird diese aus der ORDER BY-Klausel entfernt.</span><span class="sxs-lookup"><span data-stu-id="4c593-109">Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="4c593-110">Beachten Sie beim Arbeiten im Kriterienbereich, dass die UNION-Klausel der Abfrage entsprechend der zuletzt ausgeführten Aktionen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4c593-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c593-111">Geben Sie beim Sortieren mehrerer Spalten mithilfe der Spalte **Sortierreihenfolge** die Reihenfolge an, in der die Spalten relativ zueinander durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="4c593-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column.</span></span> <span data-ttu-id="4c593-112">Weitere Informationen finden Sie unter **Gewusst wie: Sortieren mehrerer Spalten in Abfragen**.</span><span class="sxs-lookup"><span data-stu-id="4c593-112">For more information, see **How to: Sort Multiple Columns in Queries**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c593-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c593-113">See Also</span></span>  
 <span data-ttu-id="4c593-114">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4c593-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4c593-115">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4c593-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4c593-116">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4c593-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
