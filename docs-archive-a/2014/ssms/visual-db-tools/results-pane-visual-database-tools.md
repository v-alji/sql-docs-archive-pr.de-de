---
title: Ergebnisbereich (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- result sets [SQL Server], queries
- synchronization [SQL Server], query results with definition
- displaying query results in grid
- grid showing query results [SQL Server]
- showing query results in grid
- Query Designer [SQL Server], Results pane
- results [SQL Server], query
- viewing query results
- queries [SQL Server], results
- Results pane
ms.assetid: 6309a1bc-a628-4141-8bb5-b35924bd19f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: f0db32336931f74777be56befcde9501dc484b69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608194"
---
# <a name="results-pane-visual-database-tools"></a><span data-ttu-id="31f8f-102">Results Pane (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="31f8f-102">Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="31f8f-103">Im Ergebnisbereich werden die Ergebnisse der zuletzt ausgeführten SELECT-Abfrage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31f8f-103">The Results pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="31f8f-104">(Die Ergebnisse anderer Abfragetypen werden in Meldungsfeldern angezeigt.) Um den Ergebnisbereich zu öffnen, öffnen oder erstellen Sie eine Abfrage bzw. eine Sicht oder kehren zu den Daten einer Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="31f8f-104">(The results of other query types are displayed in message boxes.) To open the results pane, open or create a query or view or return a table's data.</span></span> <span data-ttu-id="31f8f-105">Wird der Ergebnisbereich standardmäßig nicht angezeigt, zeigen Sie im **Abfrage-Designer** auf **Bereich**, und klicken Sie dann auf **Ergebnisse**.</span><span class="sxs-lookup"><span data-stu-id="31f8f-105">If the results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then click **Results**.</span></span>  
  
## <a name="what-you-can-do-in-the-results-pane"></a><span data-ttu-id="31f8f-106">Mögliche Aktionen im Ergebnisbereich</span><span class="sxs-lookup"><span data-stu-id="31f8f-106">What You Can Do in the Results Pane</span></span>  
  
-   <span data-ttu-id="31f8f-107">Anzeigen des Resultsets für die zuletzt ausgeführte SELECT-Abfrage in einem Datenblatt, das einer Kalkulationstabelle ähnelt.</span><span class="sxs-lookup"><span data-stu-id="31f8f-107">View the result set for the most recently executed SELECT query in a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="31f8f-108">In Abfragen oder Sichten, die Daten aus einer einzelnen Tabelle oder Sicht anzeigen, können Sie die Werte in einzelnen Spalten im Resultset bearbeiten, neue Zeilen hinzufügen und vorhandene Zeilen löschen.</span><span class="sxs-lookup"><span data-stu-id="31f8f-108">For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.</span></span>  
  
## <a name="limitations-in-the-results-pane"></a><span data-ttu-id="31f8f-109">Einschränkungen im Ergebnisbereich</span><span class="sxs-lookup"><span data-stu-id="31f8f-109">Limitations in the Results Pane</span></span>  
  
-   <span data-ttu-id="31f8f-110">Ergebnisse, die von Tabellenwert-Funktionen zurückgegeben werden, können nur in einigen Fällen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="31f8f-110">Results returned by table-valued functions can only be updated in some cases.</span></span>  
  
-   <span data-ttu-id="31f8f-111">Abfragen oder Sichten, die Spalten von mehr als einer Tabelle oder Sicht beinhalten, können nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="31f8f-111">Queries or views that include columns from more than one table or view cannot be updated.</span></span>  
  
-   <span data-ttu-id="31f8f-112">Von einer gespeicherten Prozedur zurückgegebene Ergebnisse können nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="31f8f-112">Results returned by a stored procedure cannot be updated.</span></span>  
  
-   <span data-ttu-id="31f8f-113">Abfragen oder Sichten, die GROUP BY-Klauseln oder DISTINCT-Klauseln enthalten, sind nicht aktualisierbar.</span><span class="sxs-lookup"><span data-stu-id="31f8f-113">Queries or views using the GROUP BY or DISTINCT clauses are not updatable.</span></span>  
  
## <a name="navigating-in-the-results-pane"></a><span data-ttu-id="31f8f-114">Navigieren im Ergebnisbereich</span><span class="sxs-lookup"><span data-stu-id="31f8f-114">Navigating in the Results Pane</span></span>  
 <span data-ttu-id="31f8f-115">Verwenden Sie die Navigationsleiste am unteren Rand des Ergebnisbereichs, um schnell durch die Datensätze zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="31f8f-115">You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.</span></span>  
  
 <span data-ttu-id="31f8f-116">Die Navigationsleiste ist mit Schaltflächen versehen, um zu den ersten und letzten Datensatz zu gehen, den nächsten und vorhergehenden Datensatz, und zu einem bestimmten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="31f8f-116">There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.</span></span>  
  
 <span data-ttu-id="31f8f-117">Um zu einem bestimmten Datensatz zu gelangen, geben Sie die Zahl der Zeile in das Textfeld der Navigationsleiste ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="31f8f-117">To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.</span></span>  
  
 <span data-ttu-id="31f8f-118">Weitere Informationen zum Verwenden von Tastenkombinationen im Abfrage- und Sicht-Designer finden Sie unter [Navigieren im Abfrage- und Sicht-Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="31f8f-118">For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="keeping-the-results-set-synchronized-with-the-query-definition"></a><span data-ttu-id="31f8f-119">Synchronhalten des Resultsets mit der Abfragedefinition</span><span class="sxs-lookup"><span data-stu-id="31f8f-119">Keeping the Results Set Synchronized with the Query Definition</span></span>  
 <span data-ttu-id="31f8f-120">Während Sie mit den Ergebnissen einer Abfrage oder Sicht arbeiten, ist es möglich, dass die Datensätze im Ergebnisbereich nicht mehr mit der Abfragedefinition synchron sind.</span><span class="sxs-lookup"><span data-stu-id="31f8f-120">While you are working on the results of a query or view it is possible for the records in the results pane to get out of synchronization with the query's definition.</span></span> <span data-ttu-id="31f8f-121">Wenn Sie z. B. eine Abfrage für vier von fünf Spalten einer Tabelle ausführen und dann den Diagrammbereich verwenden, um die fünfte Spalte zur Abfragedefinition hinzuzufügen, werden die Daten der fünften Spalte nicht automatisch dem Ergebnisbereich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="31f8f-121">For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data will not automatically be added to the Results pane.</span></span> <span data-ttu-id="31f8f-122">Führen Sie die Abfrage erneut aus, damit der Ergebnisbereich die neue Abfragedefinition wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="31f8f-122">To make the results pane reflect the new query definition, run the query again.</span></span>  
  
 <span data-ttu-id="31f8f-123">Wenn eine Abfrage geändert wird, werden in der unteren rechten Ecke des Ergebnisbereichs ein Warnsymbol und der Text "Abfrage geändert" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31f8f-123">If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the results pane.</span></span> <span data-ttu-id="31f8f-124">Das Warnsymbol wird auch in der oberen linken Ecke des Bereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31f8f-124">The icon is repeated in the upper-left corner of the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f8f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31f8f-125">See Also</span></span>  
 <span data-ttu-id="31f8f-126">[Erstellen von Abfragen &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31f8f-126">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31f8f-127">[Ausführen von Abfragen &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31f8f-127">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31f8f-128">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31f8f-128">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31f8f-129">[Diagrammbereich &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31f8f-129">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31f8f-130">[Kriterienbereich &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31f8f-130">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="31f8f-131">Verwenden von Daten im Ergebnisbereich &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="31f8f-131">Work with Data in the Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
