---
title: Verwenden von "Where"-und WHERE-Klauseln in derselben Abfrage (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- search conditions [SQL Server], HAVING clause
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- HAVING clause, search criteria
- search conditions [SQL Server], WHERE clause
- WHERE clause, search criteria
- excluding rows
ms.assetid: 1e07cf56-b4b7-4c49-8ddd-c276812a7148
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f6b471a60bf225ee61bdbbf0ecec30f21a92cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696366"
---
# <a name="use-having-and-where-clauses-in-the-same-query-visual-database-tools"></a><span data-ttu-id="e624f-102">Verwenden von HAVING- und WHERE-Klauseln in derselben Abfrage (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e624f-102">Use HAVING and WHERE Clauses in the Same Query (Visual Database Tools)</span></span>
  <span data-ttu-id="e624f-103">In einigen Fällen kann es sinnvoll sein, einzelne Zeilen aus Gruppen auszuschließen (mit einer WHERE-Klausel), bevor eine Bedingung auf Gruppen als Ganzes (mithilfe der HAVING-Klausel) angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e624f-103">In some instances, you might want to exclude individual rows from groups (using a WHERE clause) before applying a condition to groups as a whole (using a HAVING clause).</span></span>  
  
 <span data-ttu-id="e624f-104">Die HAVING-Klausel ähnelt der WHERE-Klausel, gilt jedoch nur für Gruppen als Ganzes (d. h. für die Zeilen im Resultset, die Gruppen darstellen), während die WHERE-Klausel auf einzelne Zeilen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e624f-104">A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows.</span></span> <span data-ttu-id="e624f-105">Eine Abfrage kann sowohl eine WHERE-Klausel als auch eine HAVING-Klausel enthalten.</span><span class="sxs-lookup"><span data-stu-id="e624f-105">A query can contain both a WHERE clause and a HAVING clause.</span></span> <span data-ttu-id="e624f-106">Dabei trifft Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="e624f-106">In that case:</span></span>  
  
-   <span data-ttu-id="e624f-107">Zuerst wird die WHERE-Klausel auf die einzelnen Zeilen der Tabellen bzw. Objekte mit Tabellenwert im Diagrammbereich angewendet.</span><span class="sxs-lookup"><span data-stu-id="e624f-107">The WHERE clause is applied first to the individual rows in the tables or table-valued objects in the Diagram pane.</span></span> <span data-ttu-id="e624f-108">Gruppiert werden nur die Zeilen, die die Bedingungen der WHERE-Klausel erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e624f-108">Only the rows that meet the conditions in the WHERE clause are grouped.</span></span>  
  
-   <span data-ttu-id="e624f-109">Die HAVING-Klausel wird dann im Resultset auf die Zeilen angewendet.</span><span class="sxs-lookup"><span data-stu-id="e624f-109">The HAVING clause is then applied to the rows in the result set.</span></span> <span data-ttu-id="e624f-110">Nur die Gruppen werden in das Abfrageergebnis aufgenommen, die die HAVING-Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e624f-110">Only the groups that meet the HAVING conditions appear in the query output.</span></span> <span data-ttu-id="e624f-111">Die HAVING-Klausel kann nur auf Spalten angewendet werden, die auch Teil einer GROUP BY-Klausel oder einer Aggregatfunktion sind.</span><span class="sxs-lookup"><span data-stu-id="e624f-111">You can apply a HAVING clause only to columns that also appear in the GROUP BY clause or in an aggregate function.</span></span>  
  
 <span data-ttu-id="e624f-112">Angenommen, Sie verknüpfen die Tabellen `titles` und `publishers` , um eine Abfrage zu erstellen, in der der durchschnittliche Buchpreis für eine Gruppe von Herstellern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e624f-112">For example, imagine that you are joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers.</span></span> <span data-ttu-id="e624f-113">Der Durchschnittspreis soll jedoch nur für eine bestimmte Gruppe von Herausgebern angezeigt werden, beispielsweise nur für die Herausgeber in Kalifornien.</span><span class="sxs-lookup"><span data-stu-id="e624f-113">You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California.</span></span> <span data-ttu-id="e624f-114">Außerdem sollen nur Durchschnittspreise über 10,00 $ in der Ausgabe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e624f-114">And even then, you want to see the average price only if it is over $10.00.</span></span>  
  
 <span data-ttu-id="e624f-115">Die erste Bedingung können Sie mithilfe einer WHERE-Klausel aufbauen, durch die Hersteller, die nicht aus Kalifornien stammen, vor der Berechnung der Durchschnittspreise verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="e624f-115">You can establish the first condition by including a WHERE clause, which discards any publishers that are not in California, before calculating average prices.</span></span> <span data-ttu-id="e624f-116">Die zweite Bedingung erfordert eine HAVING-Klausel, da sie auf den Ergebnissen einer Gruppierung und Zusammenfassung von Daten aufbaut.</span><span class="sxs-lookup"><span data-stu-id="e624f-116">The second condition requires a HAVING clause, because the condition is based on the results of grouping and summarizing the data.</span></span> <span data-ttu-id="e624f-117">Die resultierende SQL-Anweisung könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="e624f-117">The resulting SQL statement might look like this:</span></span>  
  
```  
SELECT titles.pub_id, AVG(titles.price)  
FROM titles INNER JOIN publishers  
   ON titles.pub_id = publishers.pub_id  
WHERE publishers.state = 'CA'  
GROUP BY titles.pub_id  
HAVING AVG(price) > 10  
```  
  
 <span data-ttu-id="e624f-118">Sie können im Kriterienbereich sowohl HAVING-Klauseln als auch WHERE-Klauseln erstellen.</span><span class="sxs-lookup"><span data-stu-id="e624f-118">You can create both HAVING and WHERE clauses in the Criteria pane.</span></span> <span data-ttu-id="e624f-119">Wenn Sie eine Suchbedingung für eine Spalte angeben, wird diese Bedingung standardmäßig zu einem Bestandteil der HAVING-Klausel.</span><span class="sxs-lookup"><span data-stu-id="e624f-119">By default, if you specify a search condition for a column, the condition becomes part of the HAVING clause.</span></span> <span data-ttu-id="e624f-120">Sie können die Bedingung jedoch auch in eine WHERE-Klausel ändern.</span><span class="sxs-lookup"><span data-stu-id="e624f-120">However, you can change the condition to be a WHERE clause.</span></span>  
  
 <span data-ttu-id="e624f-121">Für dieselbe Spalte kann sowohl eine WHERE-Klausel als auch eine HAVING-Klausel erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e624f-121">You can create a WHERE clause and HAVING clause involving the same column.</span></span> <span data-ttu-id="e624f-122">Dazu müssen Sie die Spalte zunächst zweimal im Kriterienbereich einfügen und dann eine Instanz als Teil der HAVING-Klausel und die andere Instanz als Teil der WHERE-Klausel angeben.</span><span class="sxs-lookup"><span data-stu-id="e624f-122">To do so, you must add the column twice to the Criteria pane, then specify one instance as part of the HAVING clause and the other instance as part of the WHERE clause.</span></span>  
  
### <a name="to-specify-a-where-condition-in-an-aggregate-query"></a><span data-ttu-id="e624f-123">So legen Sie eine WHERE-Bedingung in einer Aggregatabfrage fest</span><span class="sxs-lookup"><span data-stu-id="e624f-123">To specify a WHERE condition in an aggregate query</span></span>  
  
1.  <span data-ttu-id="e624f-124">Geben Sie die Gruppen für die Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="e624f-124">Specify the groups for your query.</span></span> <span data-ttu-id="e624f-125">Weitere Informationen finden Sie unter [Gruppieren von Zeilen in Abfrageergebnissen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e624f-125">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="e624f-126">Fügen Sie dem Kriterienbereich die Spalte hinzu, auf der die WHERE-Bedingung basieren soll, sofern diese dort nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e624f-126">If it is not already in the Criteria pane, add the column on which you want to base the WHERE condition.</span></span>  
  
3.  <span data-ttu-id="e624f-127">Löschen Sie die Spalte **Ausgabe** , es sei denn, die Datenspalte ist in die GROUP BY-Klausel oder eine Aggregatfunktion eingebunden.</span><span class="sxs-lookup"><span data-stu-id="e624f-127">Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.</span></span>  
  
4.  <span data-ttu-id="e624f-128">Geben Sie die WHERE-Bedingung in der Spalte **Filter** an.</span><span class="sxs-lookup"><span data-stu-id="e624f-128">In the **Filter** column, specify the WHERE condition.</span></span> <span data-ttu-id="e624f-129">Der Abfrage- und Sicht-Designer fügt der HAVING-Klausel der SQL-Anweisung die Bedingung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e624f-129">The Query and View Designer adds the condition to the HAVING clause of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e624f-130">In der im Beispiel für diese Prozedur dargestellten Abfrage werden die beiden Tabellen `titles` und `publishers`miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e624f-130">The query shown in the example for this procedure joins two tables, `titles` and `publishers`.</span></span>  
  
     <span data-ttu-id="e624f-131">An dieser Stelle der Abfrage enthält die SQL-Anweisung eine HAVING-Klausel:</span><span class="sxs-lookup"><span data-stu-id="e624f-131">At this point in the query, the SQL statement contains a HAVING clause:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    GROUP BY titles.pub_id  
    HAVING publishers.state = 'CA'  
    ```  
  
5.  <span data-ttu-id="e624f-132">Wählen Sie in der Spalte **Gruppieren nach** aus der Liste von Gruppierungs- und Zusammenfassungsoptionen die Option **Where** aus.</span><span class="sxs-lookup"><span data-stu-id="e624f-132">In the **Group By** column, select **Where** from the list of group and summary options.</span></span> <span data-ttu-id="e624f-133">Der Abfrage- und Sicht-Designer entfernt die Bedingung aus der HAVING-Klausel in der SQL-Anweisung und fügt sie der WHERE-Klausel hinzu.</span><span class="sxs-lookup"><span data-stu-id="e624f-133">The Query and View Designer removes the condition from the HAVING clause in the SQL statement and adds it to the WHERE clause.</span></span>  
  
     <span data-ttu-id="e624f-134">Daraufhin wird stattdessen eine WHERE-Klausel in die SQL-Anweisung eingebunden:</span><span class="sxs-lookup"><span data-stu-id="e624f-134">The SQL statement changes to include a WHERE clause instead:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    WHERE publishers.state = 'CA'  
    GROUP BY titles.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e624f-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e624f-135">See Also</span></span>  
 <span data-ttu-id="e624f-136">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e624f-136">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e624f-137">Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="e624f-137">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
