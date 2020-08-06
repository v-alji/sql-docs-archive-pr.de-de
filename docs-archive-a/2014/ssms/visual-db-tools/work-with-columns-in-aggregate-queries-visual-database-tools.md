---
title: Verwenden von Spalten in Aggregatabfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query summary results
- GROUP BY clause, query summary results
- aggregate queries [SQL Server]
- WHERE clause, query summary results
ms.assetid: 1b82681f-3d4f-4b9a-bb1d-2060e44f2577
author: stevestein
ms.author: sstein
ms.openlocfilehash: 880f7529cebd7f51951e62952e3b5f13190f99b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695074"
---
# <a name="work-with-columns-in-aggregate-queries-visual-database-tools"></a><span data-ttu-id="6e7bd-102">Verwenden von Spalten in Aggregatabfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6e7bd-102">Work with Columns in Aggregate Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="6e7bd-103">Wenn Sie Aggregatabfragen erstellen, geht der [Abfrage- und Sicht-Designer](visual-database-tools.md) von bestimmten Annahmen aus, sodass eine gültige Abfrage konstruiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-103">When you create aggregate queries the [Query and View Designer](visual-database-tools.md) makes certain assumptions so that it can construct a valid query.</span></span> <span data-ttu-id="6e7bd-104">Wenn Sie z. B. eine Aggregatabfrage erstellen und eine Datenspalte für die Ausgabe kennzeichnen, nimmt der Abfrage- und Sicht-Designer die Spalte automatisch in die GROUP BY-Klausel auf und verhindert so, dass der Inhalt einer einzelnen Zeile in einer Zusammenfassung angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-104">For example, if you are creating an aggregate query and mark a data column for output, the Query and View Designer automatically makes the column part of the GROUP BY clause so that you do not inadvertently attempt to display the contents of an individual row in a summary.</span></span>  
  
## <a name="using-group-by"></a><span data-ttu-id="6e7bd-105">Verwenden von Gruppieren nach</span><span class="sxs-lookup"><span data-stu-id="6e7bd-105">Using Group By</span></span>  
 <span data-ttu-id="6e7bd-106">Der Abfrage- und Sicht-Designer greift beim Arbeiten mit Spalten auf folgende Richtlinien zurück:</span><span class="sxs-lookup"><span data-stu-id="6e7bd-106">The Query and View Designer uses the following guidelines for working with columns:</span></span>  
  
-   <span data-ttu-id="6e7bd-107">Wenn Sie die Option Gruppieren nach auswählen oder einer Abfrage eine Aggregatfunktion hinzufügen, werden alle für die Ausgabe gekennzeichneten oder in Sortiervorgängen verwendeten Spalten automatisch in die GROUP BY-Klausel aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-107">When you choose the Group By option or add an aggregate function to a query, all columns marked for output or used for sorting are automatically added to the GROUP BY clause.</span></span> <span data-ttu-id="6e7bd-108">Spalten werden nicht automatisch in die GROUP BY-Klausel aufgenommen, wenn sie bereits Teil einer Aggregatfunktion sind.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-108">Columns are not automatically added to the GROUP BY clause if they are already part of an aggregate function.</span></span>  
  
     <span data-ttu-id="6e7bd-109">Wenn Sie eine bestimmte Spalte aus der GROUP BY-Klausel herausnehmen möchten, müssen Sie im Kriterienbereich in der Spalte Gruppieren nach manuell eine andere Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-109">If you do not want a particular column to be part of the GROUP BY clause, you must manually change it by selecting a different option in the Group By column of the Criteria pane.</span></span> <span data-ttu-id="6e7bd-110">Der Abfrage- und Sicht-Designer prüft hierbei jedoch nicht, ob die Abfrage mit der von Ihnen ausgewählten Option nach wie vor ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-110">However, the Query and View Designer will not prevent you from choosing an option that can result in a query that will not run.</span></span>  
  
-   <span data-ttu-id="6e7bd-111">Wenn Sie einer Aggregatfunktion im Kriterien- oder SQL-Bereich manuell eine Ausgabespalte für die Abfrage hinzufügen, entfernt der Abfrage- und Sicht-Designer andere Ausgabespalten nicht automatisch aus der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-111">If you manually add a query output column to an aggregate function in either the Criteria or SQL pane, the Query and View Designer does not automatically remove other output columns from the query.</span></span> <span data-ttu-id="6e7bd-112">Sie müssen die verbleibenden Spalten daher manuell aus der Abfrageausgabe entfernen oder sie in die GROUP BY-Klausel einer Aggregatfunktion aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-112">Therefore, you must remove the remaining columns from the query output or make them part of the GROUP BY clause or of an aggregate function.</span></span>  
  
 <span data-ttu-id="6e7bd-113">Wenn Sie eine Suchbedingung im Kriterienbereich in die Spalte Filter eingeben, folgt der Abfrage- und Sicht-Designer bestimmten Regeln:</span><span class="sxs-lookup"><span data-stu-id="6e7bd-113">When you enter a search condition into the Filter column of the Criteria pane, the Query and View Designer follows these rules:</span></span>  
  
-   <span data-ttu-id="6e7bd-114">Wenn die Spalte **Gruppieren nach** des Datenblatts nicht angezeigt wird (weil Sie die Abfrage noch nicht als Aggregatabfrage definiert haben), wird die Suchbedingung in der WHERE-Klausel platziert.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-114">If the **Group By** column of the grid is not displayed (because you have not yet specified an aggregate query), the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="6e7bd-115">Wenn Sie bereits in einer Aggregatabfrage arbeiten und in der Spalte **Gruppieren nach** die Option **Ort** ausgewählt haben, wird die Suchbedingung in der WHERE-Klausel platziert.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-115">If you are already in an aggregate query and have selected the option **Where** in the **Group By** column, the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="6e7bd-116">Wenn die Spalte **Gruppieren nach** einen anderen Wert als **Ort**enthält, wird die Suchbedingung in der HAVING-Klausel platziert.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-116">If the **Group By** column contains any value other than **Where**, the search condition is placed in the HAVING clause.</span></span>  
  
## <a name="using-the-having-and-where-clauses"></a><span data-ttu-id="6e7bd-117">Verwenden der HAVING- und WHERE-Klauseln</span><span class="sxs-lookup"><span data-stu-id="6e7bd-117">Using the HAVING and WHERE Clauses</span></span>  
 <span data-ttu-id="6e7bd-118">Die folgenden Prinzipien beschreiben, wie Sie in einer Aggregatabfrage beim Festlegen von Suchbedingungen auf Spalten verweisen können.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-118">The following principles describe how you can reference columns in an aggregate query in search conditions.</span></span> <span data-ttu-id="6e7bd-119">Im Allgemeinen können Sie eine Spalte in einer Suchbedingung verwenden, um die zusammengefassten Zeilen zu filtern (WHERE-Klausel) oder um zu bestimmen, welche gruppierten Ergebnisse in der endgültigen Ausgabe angezeigt werden sollen (HAVING-Klausel).</span><span class="sxs-lookup"><span data-stu-id="6e7bd-119">In general, you can use a column in a search condition to filter the rows that should be summarized (a WHERE clause) or to determine which grouped results appear in the final output (a HAVING clause).</span></span>  
  
-   <span data-ttu-id="6e7bd-120">Einzelne Datenspalten können entweder in der WHERE- oder in der HAVING-Klausel angegeben werden. Dies hängt davon ab, wie die Spalten an anderer Stelle in der Abfrage verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-120">Individual data columns can appear in either the WHERE or HAVING clause, depending on how they are used elsewhere in the query.</span></span>  
  
-   <span data-ttu-id="6e7bd-121">WHERE-Klauseln dienen zum Auswählen einer Teilmenge der Zeilen für die Zusammenfassung und Gruppierung. Sie werden daher angewendet, bevor Gruppierungsvorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-121">WHERE clauses are used to select a subset of rows for summarizing and grouping and are thus applied before any grouping is done.</span></span> <span data-ttu-id="6e7bd-122">Aus diesem Grund können Sie eine Datenspalte auch dann in einer WHERE-Klausel verwenden, wenn sie nicht in der GROUP BY-Klausel oder in einer Aggregatfunktion enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-122">Therefore, you can use a data column in a WHERE clause even if it is not part of the GROUP BY clause or contained in an aggregate function.</span></span> <span data-ttu-id="6e7bd-123">Beispielsweise gibt die folgende Anweisung alle Titel mit einem Preis über $10,00 zurück und berechnet den Durchschnittspreis:</span><span class="sxs-lookup"><span data-stu-id="6e7bd-123">For example, the following statement selects all titles that cost more than $10.00 and averages the price:</span></span>  
  
    ```  
    SELECT AVG(price)  
    FROM titles  
    WHERE price > 10  
    ```  
  
-   <span data-ttu-id="6e7bd-124">Wenn Sie beim Erstellen einer Suchbedingung eine Spalte verwenden, die ebenfalls Bestandteil einer GROUP BY-Klausel oder Aggregatfunktion ist, kann die Suchbedingung entweder als WHERE- oder als HAVING-Klausel eingebunden werden. Sie können dies entscheiden, sobald Sie die Bedingung erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-124">If you create a search condition that involves a column also used in a GROUP BY clause or aggregate function, the search condition can appear as either a WHERE clause or a HAVING clause - you can decide which when you create the condition.</span></span> <span data-ttu-id="6e7bd-125">Die folgende Anweisung erstellt z. B. einen Durchschnittspreis aller Bücher für jeden Herausgeber und zeigt anschließend den Mittelwert derjenigen Herausgeber an, bei denen der Durchschnittspreis über 10,00 $ liegt:</span><span class="sxs-lookup"><span data-stu-id="6e7bd-125">For example, the following statement creates an average price for the titles for each publisher, then displays the average for the publishers in which the average price is greater than $10.00:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
    ```  
  
-   <span data-ttu-id="6e7bd-126">Wenn Sie eine Aggregatfunktion in einer Suchbedingung verwenden, beinhaltet die Bedingung eine Zusammenfassung und muss somit Teil der HAVING-Klausel sein.</span><span class="sxs-lookup"><span data-stu-id="6e7bd-126">If you use an aggregate function in a search condition, the condition involves a summary and must therefore be part of the HAVING clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e7bd-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e7bd-127">See Also</span></span>  
 <span data-ttu-id="6e7bd-128">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6e7bd-128">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6e7bd-129">Sortieren und Gruppieren von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6e7bd-129">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
