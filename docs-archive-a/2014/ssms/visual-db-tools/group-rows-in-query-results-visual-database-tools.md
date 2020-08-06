---
title: Gruppieren von Zeilen in Abfrageergebnissen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing table subsets
- grouping rows
- grouping query results
ms.assetid: b07082d5-4d55-4903-9af9-4c470554c6d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52de25c86425d95f5917d89c8a3f4fec8939fb16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618981"
---
# <a name="group-rows-in-query-results-visual-database-tools"></a><span data-ttu-id="177c8-102">Gruppieren von Zeilen in Abfrageergebnissen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="177c8-102">Group Rows in Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="177c8-103">Zum Bilden von Teilergebnissen oder zum Anzeigen weiterer Kurzinformationen für Teilbereiche einer Tabelle erstellen Sie Gruppen mithilfe einer Aggregatabfrage.</span><span class="sxs-lookup"><span data-stu-id="177c8-103">If you want to create subtotals or show other summary information for subsets of a table, you create groups using an aggregate query.</span></span> <span data-ttu-id="177c8-104">In jeder Gruppe werden die Daten aus allen Zeilen der Tabelle mit demselben Wert zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="177c8-104">Each group summarizes the data for all the rows in the table that have the same value.</span></span>  
  
 <span data-ttu-id="177c8-105">Angenommen, Sie möchten den durchschnittlichen Preis für ein Buch in der Tabelle `titles` anzeigen lassen, wobei die Ergebnisse nach Herausgeber aufgeteilt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="177c8-105">For example, you might want to see the average price of a book in the `titles` table, but break the results down by publisher.</span></span> <span data-ttu-id="177c8-106">Dazu gruppieren Sie die Abfrage nach Herausgeber (z. B. `pub_id`).</span><span class="sxs-lookup"><span data-stu-id="177c8-106">To do so, you group the query by publisher (for example, `pub_id`).</span></span> <span data-ttu-id="177c8-107">Hierfür kann folgende Abfrageausgabe formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="177c8-107">The resulting query output might look like this:</span></span>  
  
 <span data-ttu-id="177c8-108">![Abfrageergebnisse: Durchschnittspreis gruppiert nach Verlag](../../database-engine/media//dv3w9e1.gif "Abfrageergebnisse: Durchschnittspreis gruppiert nach Verlag")</span><span class="sxs-lookup"><span data-stu-id="177c8-108">![Query results: average price grouped by publisher](../../database-engine/media//dv3w9e1.gif "Query results: average price grouped by publisher")</span></span>  
  
 <span data-ttu-id="177c8-109">Beim Gruppieren von Daten können nur Daten aus Zusammenfassungen bzw. gruppierte Daten angezeigt werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="177c8-109">When you group data, you can display only summary or grouped data, such as:</span></span>  
  
-   <span data-ttu-id="177c8-110">Die Werte der gruppierten Spalten (die in der GROUP BY-Klausel auftreten).</span><span class="sxs-lookup"><span data-stu-id="177c8-110">The values of the grouped columns (those that appear in the GROUP BY clause).</span></span> <span data-ttu-id="177c8-111">Im oben angeführten Beispiel ist `pub_id` die gruppierte Spalte.</span><span class="sxs-lookup"><span data-stu-id="177c8-111">In the example above, `pub_id` is the grouped column.</span></span>  
  
-   <span data-ttu-id="177c8-112">Die Werte, die von Aggregatfunktionen wie SUM( ) und AVG( ) erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="177c8-112">Values produced by aggregate functions such as SUM( ) and AVG( ).</span></span> <span data-ttu-id="177c8-113">Im oben aufgeführten Beispiel wird die zweite Spalte erstellt, indem die Funktion AVG( ) auf die Spalte `price` angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="177c8-113">In the example above, the second column is produced by using the AVG( ) function with the `price` column.</span></span>  
  
 <span data-ttu-id="177c8-114">Werte aus einzelnen Zeilen können nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="177c8-114">You cannot display values from individual rows.</span></span> <span data-ttu-id="177c8-115">Wenn Sie z. B. nur nach Herausgeber gruppieren, können nicht gleichzeitig die einzelnen Titel in der Abfrage angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="177c8-115">For example, if you group only by publisher, you cannot also display individual titles in the query.</span></span> <span data-ttu-id="177c8-116">Wenn Sie daher dem Abfrageergebnis Spalten hinzufügen, fügt der [Abfrage- und Sicht-Designer](visual-database-tools.md) diese automatisch der GROUP BY-Klausel der Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="177c8-116">Therefore, if you add columns to the query output, the [Query and View Designer](visual-database-tools.md) automatically adds them to the GROUP BY clause of the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="177c8-117">Wenn eine Spalte stattdessen aggregiert werden soll, können Sie für diese Spalte eine Aggregatfunktion angeben.</span><span class="sxs-lookup"><span data-stu-id="177c8-117">If you want a column to be aggregated instead, you can specify an aggregate function for that column.</span></span>  
  
 <span data-ttu-id="177c8-118">Wenn Sie nach mehreren Spalten gruppieren, werden von jeder Gruppe der Abfrage die Aggregatwerte für alle Gruppenspalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="177c8-118">If you group by more than one column, each group in the query shows the aggregate values for all grouping columns.</span></span>  
  
 <span data-ttu-id="177c8-119">In der folgenden Abfrage für die Tabelle `titles` sind die Zeilen beispielsweise sowohl nach Herausgeber (`pub_id`) als auch nach Buchtyp (`type`) gruppiert.</span><span class="sxs-lookup"><span data-stu-id="177c8-119">For example, the following query against the `titles` table groups by publisher (`pub_id`) and also by book type (`type`).</span></span> <span data-ttu-id="177c8-120">Die Abfrageergebnisse sind nach Herausgeber geordnet und zeigen für jeden Buchtyp des jeweiligen Herausgebers Kurzinformationen an:</span><span class="sxs-lookup"><span data-stu-id="177c8-120">The query results are ordered by publisher and show summary information for each different type of book that the publisher produces:</span></span>  
  
```  
SELECT pub_id, type, SUM(price) Total_price  
FROM titles  
GROUP BY pub_id, type  
```  
  
 <span data-ttu-id="177c8-121">Die entsprechende Ausgabe könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="177c8-121">The resulting output might look like this:</span></span>  
  
 <span data-ttu-id="177c8-122">![Abfrageergebnisse: Preis gruppiert nach Verlag und Art](../../database-engine/media//dv3w9e2.gif "Abfrageergebnisse: Preis gruppiert nach Verlag und Art")</span><span class="sxs-lookup"><span data-stu-id="177c8-122">![Query results: price grouped by publisher and type](../../database-engine/media//dv3w9e2.gif "Query results: price grouped by publisher and type")</span></span>  
  
### <a name="to-group-rows"></a><span data-ttu-id="177c8-123">So gruppieren Sie Zeilen</span><span class="sxs-lookup"><span data-stu-id="177c8-123">To group rows</span></span>  
  
1.  <span data-ttu-id="177c8-124">Starten Sie die Abfrage, indem Sie dem Diagrammbereich die Tabellen hinzufügen, die zusammengefasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="177c8-124">Start the query by adding the tables you want to summarize to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="177c8-125">Klicken Sie mit der rechten Maustaste auf den Hintergrund des Diagrammbereichs, und wählen Sie im Kontextmenü die Option **Gruppe hinzufügen nach** aus.</span><span class="sxs-lookup"><span data-stu-id="177c8-125">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="177c8-126">Der Abfrage- und Sicht-Designer fügt dem Datenblatt im Kriterienbereich die Spalte **Gruppieren nach** hinzu.</span><span class="sxs-lookup"><span data-stu-id="177c8-126">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="177c8-127">Fügen Sie dem Kriterienbereich die Spalte(n) hinzu, die gruppiert werden soll(en).</span><span class="sxs-lookup"><span data-stu-id="177c8-127">Add the column or columns you want to group to the Criteria pane.</span></span> <span data-ttu-id="177c8-128">Wenn die Spalte im Abfrageergebnis aufgeführt werden soll, muss die Spalte **Ausgabe** für die Ausgabe aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="177c8-128">If you want the column to appear in the query output, be sure that the **Output** column is selected for output.</span></span>  
  
     <span data-ttu-id="177c8-129">Der Abfrage- und Sicht-Designer fügt der Anweisung im SQL-Bereich eine GROUP BY-Klausel hinzu.</span><span class="sxs-lookup"><span data-stu-id="177c8-129">The Query and View Designer adds a GROUP BY clause to the statement in the SQL pane.</span></span> <span data-ttu-id="177c8-130">Die SQL-Anweisung könnte z. B. folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="177c8-130">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT pub_id  
    FROM titles  
    GROUP BY pub_id  
    ```  
  
4.  <span data-ttu-id="177c8-131">Fügen Sie dem Kriterienbereich die Spalte(n) hinzu, die aggregiert werden soll(en).</span><span class="sxs-lookup"><span data-stu-id="177c8-131">Add the column or columns you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="177c8-132">Vergewissern Sie sich, dass die Spalte für die Ausgabe ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="177c8-132">Be sure that the column is marked for output.</span></span>  
  
5.  <span data-ttu-id="177c8-133">Wählen Sie in der Datenblattzelle **Gruppieren nach** der zu aggregierenden Spalte die entsprechende Aggregatfunktion aus.</span><span class="sxs-lookup"><span data-stu-id="177c8-133">In the **Group By** grid cell for the column that is going to be aggregated, select the appropriate aggregate function.</span></span>  
  
     <span data-ttu-id="177c8-134">Der Abfrage- und Sicht-Designer weist der Spalte, die zusammengefasst wird, automatisch einen Spaltenalias zu.</span><span class="sxs-lookup"><span data-stu-id="177c8-134">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="177c8-135">Sie können diesen automatisch generierten durch einen aussagekräftigeren Alias ersetzen.</span><span class="sxs-lookup"><span data-stu-id="177c8-135">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="177c8-136">Weitere Informationen finden Sie unter [Erstellen von Spaltenaliasen &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="177c8-136">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="177c8-137">![Hinzufügen eines Spaltenalias zum Resultset der Abfrage](../../database-engine/media//dv3w9e3.gif "Hinzufügen eines Spaltenalias zum Resultset der Abfrage")</span><span class="sxs-lookup"><span data-stu-id="177c8-137">![Adding a column alias to the query result set](../../database-engine/media//dv3w9e3.gif "Adding a column alias to the query result set")</span></span>  
  
     <span data-ttu-id="177c8-138">Die entsprechende Anweisung im Bereich **SQL** könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="177c8-138">The corresponding statement in the **SQL** pane might look like this:</span></span>  
  
    ```  
    SELECT   pub_id, SUM(price) AS Totalprice  
    FROM     titles  
    GROUP BY pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="177c8-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="177c8-139">See Also</span></span>  
 [<span data-ttu-id="177c8-140">Sortieren und Gruppieren von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="177c8-140">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
