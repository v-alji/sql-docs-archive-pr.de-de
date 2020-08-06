---
title: Zusammenfassen oder Aggregieren von Werten für alle Zeilen in einer Tabelle (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- aggregate functions [SQL Server], summarizing query results
ms.assetid: f5af876e-f937-4110-ba09-07999c35a699
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c4d80c8ab2b811b8e796f0a37b2180a2866c332
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720728"
---
# <a name="summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="4da8a-102">Wertzusammenfassung oder -aggregation für alle Zeilen in einer Tabelle (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4da8a-102">Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="4da8a-103">Mithilfe einer Aggregatfunktion können Sie eine Zusammenfassung für alle Werte in einer Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="4da8a-103">Using an aggregate function, you can create a summary for all the values in a table.</span></span> <span data-ttu-id="4da8a-104">Sie können z. B. folgende Abfrage erstellen, um den Gesamtpreis aller Bücher in der Tabelle `titles` anzeigen zu lassen:</span><span class="sxs-lookup"><span data-stu-id="4da8a-104">For example, you can create a query such as the following to display the total price for all books in the `titles` table:</span></span>  
  
```  
SELECT SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="4da8a-105">Sie können mehrere Aggregationen in derselben Abfrage erstellen, wenn Sie Aggregatfunktionen auf mehrere Spalten anwenden.</span><span class="sxs-lookup"><span data-stu-id="4da8a-105">You can create multiple aggregations in the same query by using aggregate functions with more than one column.</span></span> <span data-ttu-id="4da8a-106">Beispielsweise können Sie eine Abfrage erstellen, in der die Gesamtsumme der `price` -Spalte und der Durchschnittswert der `discount` -Spalte berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="4da8a-106">For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.</span></span>  
  
 <span data-ttu-id="4da8a-107">Sie können jedoch auch eine einzige Spalte in derselben Abfrage auf unterschiedliche Weise aggregieren (z. B. Ausgabe der Gesamtsumme, der Anzahl und des Durchschnittswerts).</span><span class="sxs-lookup"><span data-stu-id="4da8a-107">You can also aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query.</span></span> <span data-ttu-id="4da8a-108">In der folgenden Abfrage wird beispielsweise der Durchschnittswert und die Gesamtsumme für die `price` -Spalte in der Tabelle `titles` berechnet:</span><span class="sxs-lookup"><span data-stu-id="4da8a-108">For example, the following query averages and summarizes the `price` column from the `titles` table:</span></span>  
  
```  
SELECT AVG(price), SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="4da8a-109">Wenn Sie eine Suchbedingung hinzufügen, können Sie die Teilmenge von Zeilen aggregieren, die die entsprechende Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="4da8a-109">If you add a search condition, you can aggregate the subset of rows that meet that condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4da8a-110">Sie können außerdem alle Zeilen in der Tabelle oder nur die Zeilen zählen, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="4da8a-110">You can also count all the rows in the table or the ones that meet a specific condition.</span></span> <span data-ttu-id="4da8a-111">Weitere Informationen finden Sie unter [Zählen der Zeilen in einer Tabelle &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4da8a-111">For details, see [Count Rows in a Table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="4da8a-112">Wenn Sie für alle Zeilen in einer Tabelle einen einzigen Aggregatwert erstellen, werden nur die Aggregatwerte selbst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da8a-112">When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves.</span></span> <span data-ttu-id="4da8a-113">Wenn Sie z. B. die Gesamtsumme des Werts für die `price` -Spalte in der Tabelle `titles` berechnen, werden die einzelnen Buchtitel, Herausgebernamen usw. nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da8a-113">For example, if you are totaling the value of the `price` column of the `titles` table, you would not also display individual titles, publisher names, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4da8a-114">Wenn Sie Teilergebnisse berechnen, d.h. Gruppen erstellen, können Sie die Spaltenwerte für jede Gruppe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4da8a-114">If you are subtotaling - that is, creating groups - you can display column values for each group.</span></span> <span data-ttu-id="4da8a-115">Weitere Informationen finden Sie unter [Gruppieren von Zeilen in Abfrageergebnissen &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4da8a-115">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
### <a name="to-aggregate-values-for-all-rows"></a><span data-ttu-id="4da8a-116">So aggregieren Sie Werte für alle Zeilen</span><span class="sxs-lookup"><span data-stu-id="4da8a-116">To aggregate values for all rows</span></span>  
  
1.  <span data-ttu-id="4da8a-117">Stellen Sie sicher, dass die Tabelle, die Sie aggregieren möchten, bereits im Diagrammbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4da8a-117">Be sure the table you want to aggregate is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="4da8a-118">Klicken Sie mit der rechten Maustaste auf den Hintergrund des Diagrammbereichs, und wählen Sie im Kontextmenü die Option **Gruppieren nach** aus.</span><span class="sxs-lookup"><span data-stu-id="4da8a-118">Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu.</span></span> <span data-ttu-id="4da8a-119">Der [Abfrage-und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) fügt dem Raster im Kriterienbereich eine Spalte **vom Typ gruppieren nach** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4da8a-119">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="4da8a-120">Fügen Sie dem Kriterienbereich die Spalte hinzu, die aggregiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4da8a-120">Add the column you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="4da8a-121">Vergewissern Sie sich, dass die Spalte für die Ausgabe ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4da8a-121">Be sure that the column is marked for output.</span></span>  
  
     <span data-ttu-id="4da8a-122">Der Abfrage- und Sicht-Designer weist der Spalte, die zusammengefasst wird, automatisch einen Spaltenalias zu.</span><span class="sxs-lookup"><span data-stu-id="4da8a-122">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="4da8a-123">Sie können diesen Alias durch einen aussagekräftigeren Alias ersetzen.</span><span class="sxs-lookup"><span data-stu-id="4da8a-123">You can replace this alias with a more meaningful one.</span></span> <span data-ttu-id="4da8a-124">Ausführliche Informationen finden Sie unter [Erstellen von Spaltenaliasen &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4da8a-124">For details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="4da8a-125">Wählen Sie in der **Gruppieren nach**-Rasterspalte die gewünschte Aggregatfunktion aus, z. B.: **SUM**, **AVG**, **MIN**, **MAX**, **COUNT**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-125">In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**.</span></span> <span data-ttu-id="4da8a-126">Wenn im Resultset nur eindeutige Zeilen aggregiert werden sollen, wählen Sie eine Aggregatfunktion mit den DISTINCT-Optionen aus, z. B. **Min Distinct**.</span><span class="sxs-lookup"><span data-stu-id="4da8a-126">If you want to aggregate only unique rows in the result set, choose an aggregate function with the DISTINCT options, such as **Min Distinct**.</span></span> <span data-ttu-id="4da8a-127">Verwenden Sie nicht **Gruppieren nach**, **Ausdruck**oder **Wobei**, da diese Optionen bei einer Aggregation aller Zeilen nicht anwendbar sind.</span><span class="sxs-lookup"><span data-stu-id="4da8a-127">Do not choose **Group By**, **Expression**, or **Where**, because those options do not apply when you are aggregating all rows.</span></span>  
  
     <span data-ttu-id="4da8a-128">Der Abfrage- und Sicht-Designer ersetzt den Spaltennamen in der Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md) durch die angegebene Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="4da8a-128">The Query and View Designer replaces the column name in the statement in the [SQL pane](sql-pane-visual-database-tools.md) with the aggregate function that you specify.</span></span> <span data-ttu-id="4da8a-129">Die SQL-Anweisung könnte z. B. folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="4da8a-129">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT SUM(price)  
    FROM titles  
    ```  
  
5.  <span data-ttu-id="4da8a-130">Wenn Sie mehrere Aggregationen in der Abfrage erstellen möchten, wiederholen Sie die Schritte 3 und 4.</span><span class="sxs-lookup"><span data-stu-id="4da8a-130">If you want to create more than one aggregation in the query, repeat steps 3 and 4.</span></span>  
  
     <span data-ttu-id="4da8a-131">Wenn Sie der Liste der Abfrageergebnisse oder der ORDER BY-Liste eine weitere Spalte hinzufügen, wird vom Abfrage- und Sicht-Designer automatisch der Begriff **Gruppieren nach** in die **Gruppieren nach** Spalte des Rasters eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4da8a-131">When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span> <span data-ttu-id="4da8a-132">Wählen Sie die entsprechende Aggregatfunktion aus.</span><span class="sxs-lookup"><span data-stu-id="4da8a-132">Select the appropriate aggregate function.</span></span>  
  
6.  <span data-ttu-id="4da8a-133">Fügen Sie bei Bedarf Suchbedingungen hinzu, um die Teilmenge der zusammenzufassenden Zeilen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4da8a-133">Add search conditions, if any, to specify the subset of rows you want to summarize.</span></span>  
  
 <span data-ttu-id="4da8a-134">Bei Ausführung der Abfrage werden die angegebenen Aggregationen im Ergebnisbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4da8a-134">When you execute the query, the Results pane displays the aggregations that you specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4da8a-135">Der Abfrage- und Sicht-Designer behält die Aggregatfunktionen so lange als Bestandteil der SQL-Anweisung im SQL-Bereich bei, bis Sie den Gruppieren nach-Modus explizit ausschalten.</span><span class="sxs-lookup"><span data-stu-id="4da8a-135">The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode.</span></span> <span data-ttu-id="4da8a-136">Wenn Sie daher den Typ der Abfrage ändern oder ändern, welche Tabellen bzw. Tabellenwertobjekte im Diagrammbereich vorhanden sind, kann die resultierende Abfrage unter Umständen ungültige Aggregatfunktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4da8a-136">Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da8a-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4da8a-137">See Also</span></span>  
 <span data-ttu-id="4da8a-138">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4da8a-138">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4da8a-139">Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4da8a-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
