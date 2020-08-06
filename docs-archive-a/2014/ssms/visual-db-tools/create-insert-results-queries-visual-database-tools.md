---
title: Erstellen von Abfragen zum Einfügen von Ergebnissen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- result sets [SQL Server], queries
- results [SQL Server], query
- Insert Results query
- queries [SQL Server], results
ms.assetid: 8770d630-09cc-47ec-a0e9-e9de2d7bbc89
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02643c2cf3295debe740a696941f8730d4417254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699117"
---
# <a name="create-insert-results-queries-visual-database-tools"></a><span data-ttu-id="01681-102">Erstellen von Abfragen zum Einfügen von Ergebnissen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="01681-102">Create Insert Results Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="01681-103">Mit einer Abfrage zum Einfügen von Ergebnissen können Sie Zeilen aus einer Tabelle in eine andere oder innerhalb einer Tabelle kopieren.</span><span class="sxs-lookup"><span data-stu-id="01681-103">You can copy rows from one table to another or within a table using an Insert Results query.</span></span> <span data-ttu-id="01681-104">Aus der Tabelle `titles` können Sie beispielsweise mit einer Abfrage zum Einfügen von Ergebnissen Informationen über alle Titel eines Herausgebers in eine zweite Tabelle kopieren, die dem betreffenden Herausgeber zur Verfügung gestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="01681-104">For example, in a `titles` table, you can use an Insert Results query to copy information about all the titles for one publisher to a second table that you can make available to that publisher.</span></span> <span data-ttu-id="01681-105">Das Erstellen einer Abfrage zum Einfügen von Ergebnissen ähnelt dem Erstellen von Abfragen zum Erstellen von Tabellen. Im Unterschied dazu werden jedoch Zeilen in eine vorhandene Tabelle kopiert.</span><span class="sxs-lookup"><span data-stu-id="01681-105">An Insert Results query is similar to Make Table Queries, but copies rows into an existing table.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="01681-106">Sie können Zeilen auch durch Ausschneiden und Einfügen von einer Tabelle in eine andere kopieren.</span><span class="sxs-lookup"><span data-stu-id="01681-106">You can also copy rows from one table to another using cut and paste.</span></span> <span data-ttu-id="01681-107">Erstellen Sie eine Abfrage für jede Tabelle, und führen Sie die Abfragen aus.</span><span class="sxs-lookup"><span data-stu-id="01681-107">Create a query for each table and run the queries.</span></span> <span data-ttu-id="01681-108">Kopieren Sie die gewünschten Zeilen von einem Ergebnisdatenblatt in ein anderes.</span><span class="sxs-lookup"><span data-stu-id="01681-108">Copy the rows you want from one results grid to the other.</span></span>  
  
 <span data-ttu-id="01681-109">Beim Erstellen einer Abfrage zum Einfügen von Ergebnissen müssen folgende Angaben gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="01681-109">When you create an Insert Results query, you specify:</span></span>  
  
-   <span data-ttu-id="01681-110">Die Datenbanktabelle, in die Zeilen kopiert werden sollen (die Zieltabelle)</span><span class="sxs-lookup"><span data-stu-id="01681-110">The database table to copy rows to (the destination table).</span></span>  
  
-   <span data-ttu-id="01681-111">Die Tabelle oder Tabellen, aus der Zeilen kopiert werden sollen (die Quelltabelle)</span><span class="sxs-lookup"><span data-stu-id="01681-111">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="01681-112">Die Quelltabelle oder -tabellen werden Teil einer Unterabfrage.</span><span class="sxs-lookup"><span data-stu-id="01681-112">The source table or tables become part of a subquery.</span></span> <span data-ttu-id="01681-113">Wenn Sie innerhalb einer Tabelle kopieren, ist die Quelltabelle auch die Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="01681-113">If you are copying within a table, the source table is the same as the destination table.</span></span>  
  
-   <span data-ttu-id="01681-114">Die Spalten der Quelltabelle, deren Inhalt Sie kopieren möchten</span><span class="sxs-lookup"><span data-stu-id="01681-114">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="01681-115">Die Spalten der Zieltabelle, in die die Daten kopiert werden sollen</span><span class="sxs-lookup"><span data-stu-id="01681-115">The target columns in the destination table to copy the data to.</span></span>  
  
-   <span data-ttu-id="01681-116">Suchbedingungen zum Definieren der zu kopierenden Zeilen</span><span class="sxs-lookup"><span data-stu-id="01681-116">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="01681-117">Die Sortierreihenfolge, wenn die Zeilen in einer besonderen Reihenfolge kopiert werden sollen</span><span class="sxs-lookup"><span data-stu-id="01681-117">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="01681-118">Gruppierungsoptionen, wenn Sie nur Kurzinformationen kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="01681-118">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="01681-119">Beispielsweise kopiert die folgende Abfrage Titelinformationen aus der Tabelle `titles` in eine Archivtabelle mit dem Namen `archivetitles`.</span><span class="sxs-lookup"><span data-stu-id="01681-119">For example, the following query copies title information from the `titles` table to an archive table called `archivetitles`.</span></span> <span data-ttu-id="01681-120">Die Abfrage kopiert den Inhalt von vier Spalten für alle Titel eines bestimmten Herausgebers:</span><span class="sxs-lookup"><span data-stu-id="01681-120">The query copies the contents of four columns for all titles belonging to a particular publisher:</span></span>  
  
```  
INSERT INTO archivetitles   
   (title_id, title, type, pub_id)  
SELECT title_id, title, type, pub_id  
FROM titles  
WHERE (pub_id = '0766')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="01681-121">Verwenden Sie eine Abfrage zum Einfügen von Werten, um Werte in eine neue Zeile einzufügen.</span><span class="sxs-lookup"><span data-stu-id="01681-121">To insert values into a new row, use an Insert Values query.</span></span>  
  
 <span data-ttu-id="01681-122">Sie können den Inhalt ausgewählter Spalten oder aller Spalten einer Zeile kopieren.</span><span class="sxs-lookup"><span data-stu-id="01681-122">You can copy the contents of selected columns or of all columns in a row.</span></span> <span data-ttu-id="01681-123">In beiden Fällen müssen die kopierten Daten mit den Spalten der Zeilen kompatibel sein, in die sie eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="01681-123">In either case, the data you are copying must be compatible with the columns in the rows you are copying to.</span></span> <span data-ttu-id="01681-124">Wenn Sie z. B. den Inhalt einer Spalte wie `price`kopieren, müssen von der Spalte in der Zeile, in die kopiert wird, numerische Daten mit Dezimalstellen angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="01681-124">For example, if you copy the contents of a column such as `price`, the column in the row you are copying to must accept numeric data with decimal places.</span></span> <span data-ttu-id="01681-125">Beim Kopieren einer vollständigen Zeile müssen in der Zieltabelle kompatible Spalten in derselben physischen Position wie in der Quelltabelle vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="01681-125">If you are copying an entire row, the destination table must have compatible columns in the same physical position as the source table.</span></span>  
  
 <span data-ttu-id="01681-126">Wenn Sie eine Abfrage zum Einfügen von Ergebnissen erstellen, ändert sich der Kriterienbereich und zeigt die für das Kopieren von Daten verfügbaren Optionen an.</span><span class="sxs-lookup"><span data-stu-id="01681-126">When you create an Insert Results query, the Criteria pane changes to reflect options available for copying data.</span></span> <span data-ttu-id="01681-127">Eine Spalte Anfügen wird hinzugefügt, in der Sie die Spalten angeben können, in die Daten kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="01681-127">An Append column is added to allow you to specify the columns into which data should be copied.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="01681-128">Eine ausgeführte Abfrage zum Einfügen von Ergebnissen kann nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="01681-128">You cannot undo the action of executing an Insert Results query.</span></span> <span data-ttu-id="01681-129">Erstellen Sie vorsichtshalber vor Ausführung der Abfrage eine Sicherungskopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="01681-129">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-results-query"></a><span data-ttu-id="01681-130">So erstellen Sie eine Abfrage zum Einfügen von Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="01681-130">To create an Insert Results query</span></span>  
  
1.  <span data-ttu-id="01681-131">Erstellen Sie eine neue Abfrage, und fügen Sie die Tabelle hinzu, aus der Zeilen kopiert werden sollen (die Quelltabelle).</span><span class="sxs-lookup"><span data-stu-id="01681-131">Create a new query and add the table from which you want to copy rows (the source table).</span></span> <span data-ttu-id="01681-132">Wenn Sie Zeilen innerhalb einer Tabelle kopieren, können Sie die Quelltabelle als Zieltabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="01681-132">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
2.  <span data-ttu-id="01681-133">Zeigen Sie im Menü **Abfrage-Designer** auf **Typ ändern**, und klicken Sie dann auf **Ergebnisse einfügen**.</span><span class="sxs-lookup"><span data-stu-id="01681-133">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
3.  <span data-ttu-id="01681-134">Wählen Sie im [Dialogfeld „Zieltabelle für Anfügeabfrage auswählen“](visual-database-tools.md)die Tabelle aus, in die die Zeilen kopiert werden sollen (die Zieltabelle).</span><span class="sxs-lookup"><span data-stu-id="01681-134">In the [Choose Target Table for Insert Results Dialog Box](visual-database-tools.md), select the table to copy rows to (the destination table).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="01681-135">Der Abfrage- und Sicht-Designer kann nicht im Voraus bestimmen, welche Tabellen und Sichten aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="01681-135">The Query and View Designer cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="01681-136">Daher werden im Dialogfeld **Zieltabelle für Anfügeabfrage auswählen** in der Liste **Tabellenname** alle in der abgefragten Datenverbindung verfügbaren Tabellen und Sichten angezeigt, d. h. auch diejenigen, in die möglicherweise keine Zeilen kopiert werden können.</span><span class="sxs-lookup"><span data-stu-id="01681-136">Therefore, the **Table Name** list in the **Choose Table for Insert From Query** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
4.  <span data-ttu-id="01681-137">Wählen Sie in dem Rechteck, das die Tabelle oder das Tabellenwertobjekt darstellt, die Namen der Spalten aus, deren Inhalt kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="01681-137">In the rectangle representing the table or table-valued object, choose the names of the columns whose contents you want to copy.</span></span> <span data-ttu-id="01681-138">Zum Kopieren ganzer Zeilen wählen Sie \*\* \* (alle Spalten)\*\* aus.</span><span class="sxs-lookup"><span data-stu-id="01681-138">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="01681-139">Der Abfrage- und Sicht-Designer fügt die ausgewählten Spalten zur Spalte **Spalte** im Kriterienbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="01681-139">The Query and View Designer adds the columns you choose to the **Column** column of the Criteriapane.</span></span>  
  
5.  <span data-ttu-id="01681-140">Wählen Sie im Kriterienbereich in der Spalte **Anfügen** für jede zu kopierende Spalte eine Zielspalte in der Zieltabelle aus.</span><span class="sxs-lookup"><span data-stu-id="01681-140">In the **Append** column of the Criteria pane, select a target column in the destination table for each column you are copying.</span></span> <span data-ttu-id="01681-141">Wählen Sie *TableName \* aus.* beim Kopieren ganzer Zeilen.</span><span class="sxs-lookup"><span data-stu-id="01681-141">Choose *tablename.\** if you are copying entire rows.</span></span> <span data-ttu-id="01681-142">Die Spalten der Zieltabelle und der Quelltabelle müssen dieselben (oder kompatible) Datentypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="01681-142">The columns in the destination table must have the same (or compatible) data types as the columns in the source table.</span></span>  
  
6.  <span data-ttu-id="01681-143">Geben Sie eine Sortierreihenfolge an, falls Sie die Zeilen in einer bestimmten Reihenfolge kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="01681-143">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="01681-144">Ausführliche Informationen finden Sie unter [Sortieren und Gruppieren von Abfrageergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01681-144">For details, see [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span></span>  
  
7.  <span data-ttu-id="01681-145">Geben Sie durch Eingabe von Suchbedingungen in der Spalte **Filter** die zu kopierenden Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="01681-145">Specify the rows to copy by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="01681-146">Weitere Informationen finden Sie unter [Angeben von Suchbedingungen &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01681-146">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="01681-147">Wenn Sie keine Suchbedingung festlegen, werden alle Zeilen der Quelltabelle in die Zieltabelle kopiert.</span><span class="sxs-lookup"><span data-stu-id="01681-147">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="01681-148">Wenn Sie dem Kriterienbereich eine zu durchsuchende Spalte hinzufügen, wird diese vom Abfrage- und Sicht-Designer ebenfalls in die Liste der zu kopierenden Spalten aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="01681-148">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="01681-149">Wenn Sie eine Spalte für eine Suche verwenden, aber nicht kopieren möchten, deaktivieren Sie das Kontrollkästchen neben dem Spaltennamen in dem Rechteck, das die Tabelle oder das Tabellenwertobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="01681-149">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
8.  <span data-ttu-id="01681-150">Geben Sie Gruppierungsoptionen an, wenn Sie Kurzinformationen kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="01681-150">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="01681-151">Weitere Informationen finden Sie unter [Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01681-151">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="01681-152">Beim Ausführen einer Abfrage zum Einfügen von Ergebnissen werden im [Ergebnisbereich](results-pane-visual-database-tools.md)keine Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01681-152">When you execute an Insert Results query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="01681-153">Stattdessen wird eine Meldung mit der Anzahl der kopierten Zeilen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="01681-153">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01681-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01681-154">See Also</span></span>  
 <span data-ttu-id="01681-155">[Typen von Abfragen &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="01681-155">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="01681-156">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="01681-156">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
