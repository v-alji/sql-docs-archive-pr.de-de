---
title: Erstellen von Löschabfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- row removal [SQL Server], Delete query
- Delete query
- queries [SQL Server], types
- removing rows
- removing data
- data deletions [SQL Server]
- deleting rows
- deleting data
ms.assetid: 0db3af43-1ec4-48c8-b769-2bb9c76d3434
author: stevestein
ms.author: sstein
ms.openlocfilehash: a76c3aaef623365e419f40f3058308f6217d75d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622327"
---
# <a name="create-delete-queries-visual-database-tools"></a><span data-ttu-id="ba908-102">Löschen von Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ba908-102">Create Delete Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="ba908-103">Sie können alle Zeilen in einer Tabelle löschen, indem Sie eine Löschabfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba908-103">You can delete all rows in a table by using a Delete query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba908-104">Wenn Sie alle Zeilen in einer Tabelle löschen, werden zwar die enthaltenen Daten, jedoch nicht die Tabelle selbst gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ba908-104">Deleting all rows from a table clears the data in the table but does not delete the table itself.</span></span> <span data-ttu-id="ba908-105">Um eine Tabelle in einer Datenbank zu löschen, klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ba908-105">To delete a table from a database, right-click the table in Object Explorer and click **Delete**.</span></span>  
  
 <span data-ttu-id="ba908-106">Wenn Sie eine Löschabfrage erstellen, ändert sich der Kriterienbereich entsprechend und zeigt die verfügbaren Optionen zum Löschen von Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="ba908-106">When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows.</span></span> <span data-ttu-id="ba908-107">Da in einer Löschabfrage keine Daten angezeigt werden, sind die Spalten "Ausgabe", "Sortieren nach" und "Sortierreihenfolge" ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="ba908-107">Because you do not display data in a Delete query, the Output, Sort By, and Sort Order columns are removed.</span></span> <span data-ttu-id="ba908-108">Außerdem werden die Kontrollkästchen neben den Spaltennamen in dem Rechteck, das die Tabelle oder das Tabellenwertobjekt darstellt, nicht mehr angezeigt, da keine einzelnen Spalten zum Löschen angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="ba908-108">In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you cannot specify individual columns to delete.</span></span>  
  
 <span data-ttu-id="ba908-109">Falls der Abfrage- und Sicht-Designer eine oder mehrere der Zeilen nicht löschen kann, werden keine Zeilen gelöscht. Eine Meldung gibt an, welche Zeilen Informationen enthalten, die nicht aus der Datenbank gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="ba908-109">If the Query and View Designer can't delete one or more of the rows none of them will be deleted and you will receive a message telling you which row(s) contain information that can't be deleted from the database.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ba908-110">Eine ausgeführte Löschabfrage kann nicht mehr rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ba908-110">You cannot undo the action of executing a Delete query.</span></span> <span data-ttu-id="ba908-111">Erstellen Sie vorsichtshalber vor Ausführung der Löschabfrage eine Sicherungskopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="ba908-111">As a precaution, back up your data before executing a Delete query.</span></span>  
  
### <a name="to-create-a-delete-query"></a><span data-ttu-id="ba908-112">So erstellen Sie eine Löschabfrage</span><span class="sxs-lookup"><span data-stu-id="ba908-112">To create a Delete query</span></span>  
  
1.  <span data-ttu-id="ba908-113">Fügen Sie dem Diagrammbereich die Tabelle hinzu, aus der Zeilen gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ba908-113">Add the table to delete rows from to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="ba908-114">Zeigen Sie im Menü **Abfrage-Designer** auf **Typ ändern**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ba908-114">From the **Query Designer** menu, point to **Change Type**, and then click **Delete**.</span></span> <span data-ttu-id="ba908-115">**Hinweis** Wenn beim Starten der Löschabfrage mehrere Tabellen im Diagrammbereich angezeigt werden, zeigt der Abfrage- und Sicht-Designer das [Dialogfeld „Tabelle löschen“](visual-database-tools.md) an, in dem Sie zur Eingabe des Namens der Tabelle aufgefordert werden, aus der Zeilen gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ba908-115">**Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the [Delete Table Dialog Box](visual-database-tools.md) to prompt you for the name of the table to delete rows from.</span></span>  
  
 <span data-ttu-id="ba908-116">Beim Ausführen einer Löschabfrage werden keine Ergebnisse im [Ergebnisbereich](results-pane-visual-database-tools.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba908-116">When you execute the Delete query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="ba908-117">Stattdessen wird eine Meldung mit der Anzahl der gelöschten Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba908-117">Instead, a message appears indicating how many rows were deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba908-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba908-118">See Also</span></span>  
 <span data-ttu-id="ba908-119">[Unterstützte Abfrage Typen &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ba908-119">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ba908-120">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ba908-120">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
