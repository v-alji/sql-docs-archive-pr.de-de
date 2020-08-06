---
title: Erstellen von Tabellenerstellungsabfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- table creation [SQL Server], Make Table query
- inserting tables
- Make Table query
- adding tables
ms.assetid: 4493cffa-7b2d-4c24-8ef0-d49329198972
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91c4a3bf45935053789d6e884b1af5b338b4c7c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699116"
---
# <a name="create-make-table-queries-visual-database-tools"></a><span data-ttu-id="521cf-102">Erstellen von Tabellenerstellungsabfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="521cf-102">Create Make Table Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="521cf-103">Mit einer Tabellenerstellungsabfrage können Sie Zeilen in eine neue Tabelle kopieren. Dies ist hilfreich, wenn Datenteilmengen als Arbeitsgrundlage erstellt oder der Inhalt einer Tabelle von einer Datenbank in eine andere kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="521cf-103">You can copy rows into a new table using a Make Table query, which is useful for creating subsets of data to work with or copying the contents of a table from one database to another.</span></span> <span data-ttu-id="521cf-104">Eine Tabellenerstellungsabfrage ähnelt einer Abfrage zum Einfügen von Ergebnissen. Jedoch wird im Unterschied dazu eine neue Tabelle erstellt, in die Zeilen kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="521cf-104">A Make Table query is similar to an Insert Results query but creates a new table to copy rows into.</span></span>  
  
 <span data-ttu-id="521cf-105">Beim Erstellen einer Tabellenerstellungsabfrage müssen folgende Angaben gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="521cf-105">When you create a Make Table query, you specify:</span></span>  
  
-   <span data-ttu-id="521cf-106">Der Name der neuen Datenbanktabelle (der Zieltabelle)</span><span class="sxs-lookup"><span data-stu-id="521cf-106">The name of the new database table (the destination table).</span></span>  
  
-   <span data-ttu-id="521cf-107">Die Tabelle oder Tabellen, aus der Zeilen kopiert werden sollen (die Quelltabelle)</span><span class="sxs-lookup"><span data-stu-id="521cf-107">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="521cf-108">Das Kopieren ist aus einer einzelnen oder aus verknüpften Tabellen möglich.</span><span class="sxs-lookup"><span data-stu-id="521cf-108">You can copy from a single table or from joined tables.</span></span>  
  
-   <span data-ttu-id="521cf-109">Die Spalten der Quelltabelle, deren Inhalt Sie kopieren möchten</span><span class="sxs-lookup"><span data-stu-id="521cf-109">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="521cf-110">Die Sortierreihenfolge, wenn die Zeilen in einer besonderen Reihenfolge kopiert werden sollen</span><span class="sxs-lookup"><span data-stu-id="521cf-110">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="521cf-111">Suchbedingungen zum Definieren der zu kopierenden Zeilen</span><span class="sxs-lookup"><span data-stu-id="521cf-111">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="521cf-112">Gruppierungsoptionen, wenn Sie nur Kurzinformationen kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="521cf-112">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="521cf-113">Die folgende Abfrage erstellt z. B. eine neue Tabelle mit dem Namen `uk`_`customers` und kopiert Informationen aus der Tabelle `customers` hinein:</span><span class="sxs-lookup"><span data-stu-id="521cf-113">For example, the following query creates a new table called `uk`_`customers` and copies information from the `customers` table to it:</span></span>  
  
```  
SELECT *   
INTO uk_customers  
FROM customers  
WHERE country = 'UK'  
```  
  
 <span data-ttu-id="521cf-114">Folgende Bedingungen müssen erfüllt sein, damit eine Tabellenerstellungsabfrage erfolgreich verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="521cf-114">In order to use a Make Table query successfully:</span></span>  
  
-   <span data-ttu-id="521cf-115">Die Datenbank muss die SELECT...INTO-Syntax unterstützen.</span><span class="sxs-lookup"><span data-stu-id="521cf-115">Your database must support the SELECT...INTO syntax.</span></span>  
  
-   <span data-ttu-id="521cf-116">Sie müssen über eine Berechtigung zum Erstellen von Tabellen in der Zieldatenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="521cf-116">You must have permission to create a table in the target database.</span></span>  
  
### <a name="to-create-a-make-table-query"></a><span data-ttu-id="521cf-117">So erstellen Sie eine Tabellenerstellungsabfrage</span><span class="sxs-lookup"><span data-stu-id="521cf-117">To create a Make Table query</span></span>  
  
1.  <span data-ttu-id="521cf-118">Fügen Sie dem Diagrammbereich die Quelltabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="521cf-118">Add the source table or tables to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="521cf-119">Zeigen Sie im Menü **Abfrage-Designer** auf **Typ ändern**, und klicken Sie dann auf **Tabelle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="521cf-119">From the **Query Designer** menu, point to **Change Type**, and then click **Make Table**.</span></span>  
  
3.  <span data-ttu-id="521cf-120">Geben Sie im Dialogfeld **Tabelle erstellen** den Namen der Zieltabelle ein.</span><span class="sxs-lookup"><span data-stu-id="521cf-120">In the **Make Table** dialog box, type the name of the destination table.</span></span> <span data-ttu-id="521cf-121">Der Abfrage- und Sicht-Designer überprüft nicht, ob der Name bereits verwendet wird oder ob Sie über eine Berechtigung zum Erstellen der Tabelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="521cf-121">The Query and View Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
     <span data-ttu-id="521cf-122">Geben Sie zum Erstellen einer Zieltabelle in einer anderen Datenbank einen vollständigen Tabellennamen an, der den Namen der Zieldatenbank, den Besitzer (falls erforderlich) und den Namen der Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="521cf-122">To create a destination table in another database, specify a fully qualified table name including the name of the target database, the owner (if required), and the name of the table.</span></span>  
  
4.  <span data-ttu-id="521cf-123">Legen Sie die zu kopierenden Spalten fest, indem Sie diese der Abfrage hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="521cf-123">Specify the columns to copy by adding them to the query.</span></span> <span data-ttu-id="521cf-124">Ausführliche Informationen finden Sie unter [Hinzufügen von Spalten zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="521cf-124">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="521cf-125">Spalten werden nur kopiert, wenn sie der Abfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="521cf-125">Columns will be copied only if you add them to the query.</span></span> <span data-ttu-id="521cf-126">Zum Kopieren ganzer Zeilen wählen Sie \*\* \* (alle Spalten)\*\* aus.</span><span class="sxs-lookup"><span data-stu-id="521cf-126">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="521cf-127">Der Abfrage- und Sicht-Designer fügt die ausgewählten Spalten der Spalte **Spalte** im Kriterienbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="521cf-127">The Query and View Designer adds the columns you choose to the **Column** column of the Criteria pane.</span></span>  
  
5.  <span data-ttu-id="521cf-128">Geben Sie eine Sortierreihenfolge an, falls Sie die Zeilen in einer bestimmten Reihenfolge kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="521cf-128">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="521cf-129">Weitere Informationen finden Sie unter **Sortieren und Gruppieren von Abfrageergebnissen**.</span><span class="sxs-lookup"><span data-stu-id="521cf-129">For details, see **Sorting and Grouping Query Results**.</span></span>  
  
6.  <span data-ttu-id="521cf-130">Geben Sie die zu kopierenden Zeilen durch Eingabe von Suchbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="521cf-130">Specify the rows to copy by entering search conditions.</span></span> <span data-ttu-id="521cf-131">Weitere Informationen finden Sie unter [Angeben von Suchbedingungen &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="521cf-131">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="521cf-132">Wenn Sie keine Suchbedingung festlegen, werden alle Zeilen der Quelltabelle in die Zieltabelle kopiert.</span><span class="sxs-lookup"><span data-stu-id="521cf-132">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="521cf-133">Wenn Sie dem Kriterienbereich eine zu durchsuchende Spalte hinzufügen, wird diese vom Abfrage- und Sicht-Designer ebenfalls in die Liste der zu kopierenden Spalten aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="521cf-133">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="521cf-134">Wenn Sie eine Spalte für eine Suche verwenden, aber nicht kopieren möchten, deaktivieren Sie das Kontrollkästchen in dem Rechteck neben dem Spaltennamen, das die Tabelle oder das Objekt mit Tabellenstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="521cf-134">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-structured object.</span></span>  
  
7.  <span data-ttu-id="521cf-135">Geben Sie Gruppierungsoptionen an, wenn Sie Kurzinformationen kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="521cf-135">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="521cf-136">Weitere Informationen finden Sie unter [Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="521cf-136">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="521cf-137">Beim Ausführen einer Tabellenerstellungsabfrage werden keine Ergebnisse im [Ergebnisbereich](results-pane-visual-database-tools.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="521cf-137">When you execute a Make Table query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="521cf-138">Stattdessen wird eine Meldung mit der Anzahl der kopierten Zeilen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="521cf-138">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521cf-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="521cf-139">See Also</span></span>  
 <span data-ttu-id="521cf-140">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="521cf-140">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="521cf-141">Typen von Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="521cf-141">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
