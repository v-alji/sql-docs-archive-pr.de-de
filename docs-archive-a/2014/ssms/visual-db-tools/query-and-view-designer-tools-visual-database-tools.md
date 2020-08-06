---
title: Tools im Abfrage- und Sicht-Designer (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.querydesigner
- vdt.pane.diagram
- vdt.pane.grid
- vdt.dlgbox.querybuilder
- vdt.pane.sql
- vdt.pane.results
helpviewer_keywords:
- Query Designer [SQL Server], panes
- View Designer, panes
- Query Designer [SQL Server], components
- View Designer, components
ms.assetid: 12e4b5a5-b793-4b6c-a0e5-c450c49bf26f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29bd3fa9e171551197927aae0d1bc00446df6e7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720782"
---
# <a name="query-and-view-designer-tools-visual-database-tools"></a><span data-ttu-id="6a8a1-102">Tools im Abfrage- und Sicht-Designer (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-102">Query and View Designer Tools (Visual Database Tools)</span></span>
  <span data-ttu-id="6a8a1-103">Beim Erstellen von Abfragen, Sichten, Inlinefunktionen oder gespeicherten Prozeduren mit einer einzelnen Anweisung stehen Ihnen im Designer vier Bereiche zur Verfügung: der Diagrammbereich, der Kriterienbereich, der SQL-Bereich und der Ergebnisbereich.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-103">When you design a query, view, in-line function, or single-statement stored procedure, the designer you use consists of four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span>  
  
 <span data-ttu-id="6a8a1-104">![Abfrage-Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Abfrage-Designer")</span><span class="sxs-lookup"><span data-stu-id="6a8a1-104">![Query Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Query Designer")</span></span>  
  
-   <span data-ttu-id="6a8a1-105">Der Diagrammbereich zeigt die Tabellen sowie weitere Tabellenwertobjekte an, für die eine Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-105">The Diagram pane displays the tables and other table-valued objects that you are querying.</span></span> <span data-ttu-id="6a8a1-106">Jedes Rechteck stellt eine Tabelle oder ein Tabellenwertobjekt dar und gibt die verfügbaren Datenspalten an.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-106">Each rectangle represents a table or table-valued object and shows the available data columns.</span></span> <span data-ttu-id="6a8a1-107">Joins werden durch Linien zwischen den Rechtecken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-107">Joins are indicated by lines between the rectangles.</span></span> <span data-ttu-id="6a8a1-108">Weitere Informationen finden Sie unter [Diagrammbereich &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-108">For more information, see [Diagram Pane &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="6a8a1-109">Im Kriterienbereich wird ein Datenblatt ähnlich einer Kalkulationstabelle angezeigt. In dem Datenblatt können Sie Optionen festlegen, z. B. welche Datenspalten angezeigt, welche Zeilen ausgewählt oder wie Zeilen gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-109">The Criteria pane contains a spreadsheet-like grid in which you specify options, such as which data columns to display, what rows to select, how to group rows, and so on.</span></span> <span data-ttu-id="6a8a1-110">Weitere Informationen finden Sie unter [Kriterienbereich &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-110">For more information, see [Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="6a8a1-111">Im SQL-Bereich wird die SQL-Anweisung für die Abfrage oder Sicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-111">The SQL pane displays the SQL statement for the query or view.</span></span> <span data-ttu-id="6a8a1-112">Sie können die vom Designer erstellte SQL-Anweisung bearbeiten oder eine eigene SQL-Anweisung eingeben.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-112">You can edit the SQL statement created by the Designer or you can enter your own SQL statement.</span></span> <span data-ttu-id="6a8a1-113">Dieser Bereich ist besonders hilfreich bei der Eingabe von SQL-Anweisungen, die nicht im Diagramm- oder Kriterienbereich erstellt werden können, z. B. bei Union-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-113">It is particularly useful for entering SQL statements that cannot be created using the Diagram and Criteria panes, such as union queries.</span></span> <span data-ttu-id="6a8a1-114">Weitere Informationen finden Sie unter [SQL-Bereich &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-114">For more information, see [SQL Pane &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="6a8a1-115">Im Ergebnisbereich wird ein Datenblatt mit den in der Abfrage oder Sicht abgerufenen Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-115">The Results pane shows a grid with data retrieved by the query or view.</span></span> <span data-ttu-id="6a8a1-116">Im Abfrage- und Sicht-Designer enthält dieser Bereich die Ergebnisse der zuletzt ausgeführten SELECT-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-116">In the Query and View Designer, the pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="6a8a1-117">Sie können die Datenbank durch Bearbeiten der Zellenwerte im Datenblatt ändern, und Sie können Zeilen hinzufügen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-117">You can modify the database by editing values in the cells of the grid, and you can add or delete rows.</span></span> <span data-ttu-id="6a8a1-118">Weitere Informationen finden Sie unter [Ergebnisbereich &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-118">For more information, see [Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="6a8a1-119">Sie können jeden dieser Bereiche verwenden, um eine Abfrage oder Sicht zu erstellen oder anzuzeigen. Beispielsweise können Sie eine anzuzeigende Spalte im Diagrammbereich auswählen, im Kriterienbereich eingeben oder im SQL-Bereich in eine SQL-Anweisung einbinden.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-119">You can create a query or view by working in any of the panes: you can specify a column to display by choosing it in the Diagram pane, entering it into the Criteria pane, or making it part of the SQL statement in the SQL pane.</span></span>  
  
## <a name="displaying-and-hiding-panes"></a><span data-ttu-id="6a8a1-120">Anzeigen und Ausblenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="6a8a1-120">Displaying and Hiding Panes</span></span>  
 <span data-ttu-id="6a8a1-121">Klicken Sie mit der rechten Maustaste auf die Entwurfsoberfläche, zeigen Sie auf **Bereich**, und klicken Sie dann auf den Namen des Bereichs, um einen Bereich auszublenden oder einen nicht sichtbaren Bereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-121">To hide a pane or display a pane that is not visible, right-click the design surface, point to **Pane**, and then click the name of the pane.</span></span> <span data-ttu-id="6a8a1-122">Wenn der Abfrage- und Sicht-Designer im Abfrage-Designermodus geöffnet wird, ist der Bereich **Ergebnisse** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-122">If the Query and View Designer is opened in Query Designer mode, the **Results** pane is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a8a1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a8a1-123">See Also</span></span>  
 <span data-ttu-id="6a8a1-124">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6a8a1-124">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6a8a1-125">[Öffnen Sie den Abfrage-und Sicht-Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6a8a1-125">[Open the Query and View Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6a8a1-126">SQL-Editor &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6a8a1-126">SQL Editor &#40;Visual Database Tools&#41;</span></span>](sql-editor-visual-database-tools.md)  
  
  
