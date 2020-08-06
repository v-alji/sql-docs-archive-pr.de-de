---
title: Neusortieren von Ausgabespalten (Visual Database Tools)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- reordering output columns [SQL Server]
- output columns [SQL Server]
ms.assetid: 76462885-de4a-4290-a26b-90696d3671f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 97fa3f768b03f24b8c8d154624a2d7a91aba45f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618419"
---
# <a name="reorder-output-columns-visual-database-tools"></a><span data-ttu-id="7258d-102">Neusortieren von Ausgabespalten (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7258d-102">Reorder Output Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="7258d-103">Die Reihenfolge, in der Datenspalten einer Auswahlabfrage hinzugefügt werden, legt deren Reihenfolge in den angezeigten Ergebnissen fest.</span><span class="sxs-lookup"><span data-stu-id="7258d-103">The order in which you add data columns to a Select query determines the order in which they appear in the results.</span></span> <span data-ttu-id="7258d-104">Die erste zur Abfrage hinzugefügte Spalte wird in den Ergebnissen ganz links angezeigt, die zweite Spalte rechts daneben usw.</span><span class="sxs-lookup"><span data-stu-id="7258d-104">The first column you add to the query appears leftmost in the results, the second column next, and so on.</span></span>  
  
 <span data-ttu-id="7258d-105">Wenn Sie Updateabfragen oder Abfragen zum Einfügen von Ergebnissen erstellen, wirkt sich die Reihenfolge der hinzugefügten Spalten auf die Reihenfolge aus, in der Daten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7258d-105">If you are creating Update or Insert queries, the order in which you add columns affects the order in which data is processed.</span></span>  
  
 <span data-ttu-id="7258d-106">Sie können steuern, an welcher Stelle im Resultset eine Datenspalte angezeigt oder in welcher Reihenfolge sie verwendet wird, indem Sie die Spalten neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="7258d-106">To control where a data column appears in the result set, or in what order it is used, you can reorder the columns.</span></span>  
  
### <a name="to-reorder-columns-for-output"></a><span data-ttu-id="7258d-107">So ordnen Sie Spalten für die Ausgabe neu an</span><span class="sxs-lookup"><span data-stu-id="7258d-107">To reorder columns for output</span></span>  
  
1.  <span data-ttu-id="7258d-108">Markieren Sie im [Kriterienbereich](visual-database-tools.md)die Zeile mit der Spalte, indem Sie links neben der Zeile auf die Schaltfläche für die Zeilenauswahl klicken.</span><span class="sxs-lookup"><span data-stu-id="7258d-108">In the [Criteria pane](visual-database-tools.md), select the row containing the column by clicking the row selector button to the left of the row.</span></span>  
  
2.  <span data-ttu-id="7258d-109">Setzen Sie den Mauszeiger auf den Zeilenselektor, und ziehen Sie die Zeile an eine neue Stelle.</span><span class="sxs-lookup"><span data-stu-id="7258d-109">Point to the row selector button and drag the row to a new location.</span></span>  
  
     <span data-ttu-id="7258d-110">Oder</span><span class="sxs-lookup"><span data-stu-id="7258d-110">-or-</span></span>  
  
     <span data-ttu-id="7258d-111">Bearbeiten Sie die Spaltennamen im [SQL-Bereich](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7258d-111">Edit the order of the column names in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7258d-112">Sie können eine Datenspalte an einer bestimmten Stelle im Kriterienbereich einfügen, indem Sie in den Kriterienbereich eine Leerspalte einfügen und die einzufügende Datenspalte angeben.</span><span class="sxs-lookup"><span data-stu-id="7258d-112">You can add a data row at a specific location in the Criteria pane by inserting a blank row into the Criteria pane, and then specifying the data column to insert.</span></span> <span data-ttu-id="7258d-113">Ausführliche Informationen finden Sie unter [Hinzufügen von Spalten zu Abfragen &#40;Visual Database Tools&#41;](add-columns-to-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7258d-113">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](add-columns-to-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7258d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7258d-114">See Also</span></span>  
 <span data-ttu-id="7258d-115">[Sortieren und Gruppieren von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7258d-115">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7258d-116">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7258d-116">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7258d-117">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7258d-117">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
