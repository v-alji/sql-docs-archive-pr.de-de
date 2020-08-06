---
title: Zählen der Zeilen in einer Tabelle (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- totals [SQL Server], row counts
- row counts [SQL Server]
- column values [SQL Server]
- number of rows
- number of values
- counting rows
ms.assetid: dda4296a-1d16-4e77-8d6f-e295f6dd4e87
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6dca92fb955b776f56d9b51f28b1a486b89f18f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700514"
---
# <a name="count-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="3cb58-102">Zählen der Zeilen in einer Tabelle (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3cb58-102">Count Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="3cb58-103">Mit dem Zählen der Zeilen in einer Tabelle können folgende Werte bestimmt werden:</span><span class="sxs-lookup"><span data-stu-id="3cb58-103">You can count rows in a table to determine:</span></span>  
  
-   <span data-ttu-id="3cb58-104">Die Gesamtanzahl von Zeilen in einer Tabelle, beispielsweise die Anzahl von allen Büchern in einer `titles` -Tabelle</span><span class="sxs-lookup"><span data-stu-id="3cb58-104">The total number of rows in a table, for example, a count of all the books in a `titles` table.</span></span>  
  
-   <span data-ttu-id="3cb58-105">Die Anzahl von Zeilen in einer Tabelle, die eine bestimmte Bedingung erfüllen, beispielsweise die Anzahl von Büchern eines Herausgebers in einer Tabelle `titles`</span><span class="sxs-lookup"><span data-stu-id="3cb58-105">The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.</span></span>  
  
-   <span data-ttu-id="3cb58-106">Die Anzahl von Werten in einer bestimmten Spalte</span><span class="sxs-lookup"><span data-stu-id="3cb58-106">The number of values in a particular column.</span></span>  
  
 <span data-ttu-id="3cb58-107">Beim Zählen der Werte in einer Spalte werden NULL-Werte nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="3cb58-107">When you count values in a column, nulls are not included in the count.</span></span> <span data-ttu-id="3cb58-108">So kann z. B. in einer Tabelle `titles` die Anzahl von Büchern gezählt werden, für die in der Spalte `advance` Werte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3cb58-108">For example, you might count the number of books in a `titles` table that have values in the `advance` column.</span></span> <span data-ttu-id="3cb58-109">In der Standardeinstellung werden nicht nur eindeutige, sondern alle Werte berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="3cb58-109">By default, the count includes all values, not just unique values.</span></span>  
  
 <span data-ttu-id="3cb58-110">Die Prozeduren für die drei Zählverfahren ähneln sich.</span><span class="sxs-lookup"><span data-stu-id="3cb58-110">The procedures for all three types of counts are similar.</span></span>  
  
### <a name="to-count-all-the-rows-in-a-table"></a><span data-ttu-id="3cb58-111">So zählen Sie alle Zeilen in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="3cb58-111">To count all the rows in a table</span></span>  
  
1.  <span data-ttu-id="3cb58-112">Stellen Sie sicher, dass die Tabelle, die Sie zusammenfassen möchten, bereits im Diagrammbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3cb58-112">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="3cb58-113">Klicken Sie mit der rechten Maustaste auf den Hintergrund des Diagrammbereichs, und wählen Sie im Kontextmenü die Option **Gruppe hinzufügen nach** aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-113">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="3cb58-114">Der [Abfrage- und Sicht-Designer](visual-database-tools.md) fügt dem Datenblatt im Kriterienbereich die Spalte **Gruppieren nach** hinzu.</span><span class="sxs-lookup"><span data-stu-id="3cb58-114">The [Query and View Designer](visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="3cb58-115">Wählen Sie \*\* \* (alle Spalten)\*\* in dem Rechteck aus, das die Tabelle oder das Tabellen Wertobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="3cb58-115">Select **\* (All Columns)** in the rectangle representing the table or table-valued object.</span></span>  
  
     <span data-ttu-id="3cb58-116">Der Abfrage- und Sicht-Designer setzt den Ausdruck **Anzahl** automatisch in die Spalte **Gruppieren nach** des Kriterienbereichs ein und weist der Spalte, die zusammengefasst werden soll, einen Spaltenalias zu.</span><span class="sxs-lookup"><span data-stu-id="3cb58-116">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="3cb58-117">Sie können diesen automatisch generierten durch einen aussagekräftigeren Alias ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3cb58-117">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="3cb58-118">Weitere Informationen finden Sie unter [Erstellen von Spaltenaliasen &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3cb58-118">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="3cb58-119">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-119">Run the query.</span></span>  
  
### <a name="to-count-all-the-rows-that-meet-a-condition"></a><span data-ttu-id="3cb58-120">So zählen Sie alle Zeilen, die eine Bedingung erfüllen</span><span class="sxs-lookup"><span data-stu-id="3cb58-120">To count all the rows that meet a condition</span></span>  
  
1.  <span data-ttu-id="3cb58-121">Stellen Sie sicher, dass die Tabelle, die Sie zusammenfassen möchten, bereits im Diagrammbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3cb58-121">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="3cb58-122">Klicken Sie mit der rechten Maustaste auf den Hintergrund des Diagrammbereichs, und wählen Sie im Kontextmenü die Option **Gruppe hinzufügen nach** aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-122">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="3cb58-123">Der Abfrage- und Sicht-Designer fügt dem Datenblatt im Kriterienbereich die Spalte **Gruppieren nach** hinzu.</span><span class="sxs-lookup"><span data-stu-id="3cb58-123">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="3cb58-124">Wählen Sie \*\* \* (alle Spalten)\*\* in dem Rechteck aus, das die Tabelle oder das Objekt mit Tabellenstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="3cb58-124">Select **\*(All Columns)** in the rectangle representing the table or table-structured object.</span></span>  
  
     <span data-ttu-id="3cb58-125">Der Abfrage- und Sicht-Designer setzt den Ausdruck **Anzahl** automatisch in die Spalte **Gruppieren nach** des Kriterienbereichs ein und weist der Spalte, die zusammengefasst werden soll, einen Spaltenalias zu.</span><span class="sxs-lookup"><span data-stu-id="3cb58-125">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="3cb58-126">Informationen, wie eine aussagekräftigere Spaltenüberschrift in einer Abfrageausgabe erstellt wird, finden Sie unter [Erstellen von Spaltenaliasen &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3cb58-126">To create a more useful column heading in query output, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="3cb58-127">Fügen Sie die zu durchsuchende Datenspalte hinzu, und deaktivieren Sie das Kontrollkästchen in der Spalte **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="3cb58-127">Add the data column that you want to search, and then clear the check box in the **Output** column.</span></span>  
  
     <span data-ttu-id="3cb58-128">Der Abfrage- und Sicht-Designer fügt automatisch den Ausdruck **Gruppieren nach** in die **Gruppieren nach** -Spalte des Rasters ein.</span><span class="sxs-lookup"><span data-stu-id="3cb58-128">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
5.  <span data-ttu-id="3cb58-129">Ändern Sie den Ausdruck **Gruppieren nach** in der **Gruppieren nach** Spalte in **Wobei**.</span><span class="sxs-lookup"><span data-stu-id="3cb58-129">Change **Group By** in the **Group By** column to **Where**.</span></span>  
  
6.  <span data-ttu-id="3cb58-130">Geben Sie die Suchbedingung in die Spalte **Filter** der zu durchsuchenden Datenspalte ein.</span><span class="sxs-lookup"><span data-stu-id="3cb58-130">In the **Filter** column for the data column to search, enter the search condition.</span></span>  
  
7.  <span data-ttu-id="3cb58-131">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-131">Run the query.</span></span>  
  
### <a name="to-count-the-values-in-a-column"></a><span data-ttu-id="3cb58-132">So zählen Sie die Werte in einer Spalte</span><span class="sxs-lookup"><span data-stu-id="3cb58-132">To count the values in a column</span></span>  
  
1.  <span data-ttu-id="3cb58-133">Stellen Sie sicher, dass die Tabelle, die Sie zusammenfassen möchten, bereits im Diagrammbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3cb58-133">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="3cb58-134">Klicken Sie mit der rechten Maustaste auf den Hintergrund des Diagrammbereichs, und wählen Sie im Kontextmenü die Option **Gruppe hinzufügen nach** aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-134">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="3cb58-135">Der Abfrage- und Sicht-Designer fügt dem Datenblatt im Kriterienbereich die Spalte **Gruppieren nach** hinzu.</span><span class="sxs-lookup"><span data-stu-id="3cb58-135">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="3cb58-136">Fügen Sie dem Kriterienbereich die Spalte hinzu, in der gezählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3cb58-136">Add the column that you want to count to the Criteria pane.</span></span>  
  
     <span data-ttu-id="3cb58-137">Der Abfrage- und Sicht-Designer fügt automatisch den Ausdruck **Gruppieren nach** in die **Gruppieren nach** -Spalte des Rasters ein.</span><span class="sxs-lookup"><span data-stu-id="3cb58-137">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
4.  <span data-ttu-id="3cb58-138">Ändern Sie den Ausdruck **Gruppieren nach** in der Spalte **Gruppieren nach** in **Anzahl**.</span><span class="sxs-lookup"><span data-stu-id="3cb58-138">Change **Group By** in the **Group By** column to **Count**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cb58-139">Wenn nur eindeutige Werte gezählt werden sollen, wählen Sie **Count Distinct**aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-139">To count only unique values, choose **Count Distinct**.</span></span>  
  
5.  <span data-ttu-id="3cb58-140">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="3cb58-140">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb58-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cb58-141">See Also</span></span>  
 <span data-ttu-id="3cb58-142">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3cb58-142">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3cb58-143">Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3cb58-143">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
