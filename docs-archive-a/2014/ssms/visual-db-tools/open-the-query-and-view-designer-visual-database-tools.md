---
title: Öffnen des Abfrage- und Sicht-Designers (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a36a0a9f014759269517a5774167f84c19b0b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618420"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a><span data-ttu-id="f7a69-102">Öffnen des Abfrage- und Sicht-Designers (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f7a69-102">Open the Query and View Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="f7a69-103">Der Abfrage- und Sicht-Designer wird automatisch geöffnet, wenn Sie die Definition einer Sicht öffnen, die Ergebnisse für eine Abfrage oder Sicht anzeigen bzw. eine Abfrage erstellen oder öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7a69-103">The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query.</span></span> <span data-ttu-id="f7a69-104">Er besteht aus vier separaten Bereichen:</span><span class="sxs-lookup"><span data-stu-id="f7a69-104">It consists of four separate panes:</span></span>  
  
-   <span data-ttu-id="f7a69-105">Der Diagrammbereich liefert eine grafische Darstellung der Tabellen bzw. Tabellenwertobjekte, die Sie aus der Datenverbindung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f7a69-105">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="f7a69-106">Weiterhin werden alle Joinbeziehungen zwischen ihnen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7a69-106">It also shows any join relationships among them.</span></span>  
  
-   <span data-ttu-id="f7a69-107">Im Kriterienbereich können Sie Abfrageoptionen angeben, d.h. welche Datenspalten angezeigt oder wie die Ergebnisse sortiert werden und welche Zeilen ausgewählt werden sollen. Hierzu geben Sie die gewünschten Optionen in einem Datenblatt ähnlich einer Kalkulationstabelle ein.</span><span class="sxs-lookup"><span data-stu-id="f7a69-107">The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="f7a69-108">Sie können den SQL-Bereich verwenden, um eine eigene SQL-Anweisung zu erstellen. Sie können auch den Kriterienbereich und den Diagrammbereich verwenden, um die Anweisung zu erstellen, wobei dadurch die SQL-Anweisungen im SQL-Bereich erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f7a69-108">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="f7a69-109">Beim Erstellen einer Abfrage wird der SQL-Bereich automatisch aktualisiert und zur besseren Lesbarkeit neu formatiert.</span><span class="sxs-lookup"><span data-stu-id="f7a69-109">As you build your query, the SQL pane automatically updates and reformats to be easily read.</span></span>  
  
-   <span data-ttu-id="f7a69-110">Im Ergebnisbereich werden die Ergebnisse der zuletzt ausgeführten SELECT-Abfrage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7a69-110">The Results pane shows the results of the most recently executed Select query.</span></span> <span data-ttu-id="f7a69-111">(Die Ergebnisse anderer Abfragetypen werden in Meldungsfeldern angezeigt.)</span><span class="sxs-lookup"><span data-stu-id="f7a69-111">(The results of other query types are displayed in message boxes.)</span></span>  
  
-   <span data-ttu-id="f7a69-112">Diese Bereiche sind sowohl beim Verwenden von Abfragen als auch beim Verwenden von Sichten nützlich.</span><span class="sxs-lookup"><span data-stu-id="f7a69-112">These panes are useful for working with both queries and views.</span></span>  
  
-   <span data-ttu-id="f7a69-113">Beim Öffnen einer Sicht oder Abfrage werden gleichzeitig einige oder alle Bereiche geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f7a69-113">When you open a view or query some or all of the panes open with it.</span></span> <span data-ttu-id="f7a69-114">Welche Bereiche geöffnet werden, hängt von den Einstellungen im Dialogfeld **Optionen** und von dem Datenbankmanagementsystem ab, mit dem Sie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f7a69-114">Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to.</span></span> <span data-ttu-id="f7a69-115">Standardmäßig werden alle vier Bereiche geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f7a69-115">The default is that all four open.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a><span data-ttu-id="f7a69-116">So öffnen Sie den Abfrage- und Sicht-Designer für eine Sicht</span><span class="sxs-lookup"><span data-stu-id="f7a69-116">To open the Query and View Designer for a view</span></span>  
  
1.  <span data-ttu-id="f7a69-117">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Sicht, die Sie öffnen möchten, und klicken Sie dann auf **Entwerfen** oder **Sicht öffnen**.</span><span class="sxs-lookup"><span data-stu-id="f7a69-117">In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.</span></span>  
  
     <span data-ttu-id="f7a69-118">Wenn Sie **Entwerfen**auswählen, werden die Bereiche des Abfrage- und Sicht-Designers entsprechend den Einstellungen im Dialogfeld **Optionen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f7a69-118">If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box.</span></span> <span data-ttu-id="f7a69-119">Wenn Sie **Sicht öffnen**auswählen, wird standardmäßig nur der Ergebnisbereich geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f7a69-119">If you chose **Open View**, only the Results pane opens by default.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a><span data-ttu-id="f7a69-120">So öffnen Sie den Abfrage- und Sicht-Designer für eine vorhandene Abfrage</span><span class="sxs-lookup"><span data-stu-id="f7a69-120">To open the Query and View Designer for an existing query</span></span>  
  
1.  <span data-ttu-id="f7a69-121">Erweitern Sie im Projektmappen-Explorer den Ordner **Abfragen** .</span><span class="sxs-lookup"><span data-stu-id="f7a69-121">In Solution Explorer, expand the **Queries** folder.</span></span>  
  
2.  <span data-ttu-id="f7a69-122">Doppelklicken Sie auf die Abfrage, die Sie öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="f7a69-122">Double-click the query you want to open.</span></span>  
  
3.  <span data-ttu-id="f7a69-123">Markieren Sie die Abfrageanweisung(en), klicken Sie mit der rechten Maustaste auf den markierten Bereich, und klicken Sie auf **Abfrage in Editor entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="f7a69-123">Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a69-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7a69-124">See Also</span></span>  
 <span data-ttu-id="f7a69-125">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f7a69-125">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="f7a69-126">Tools im Abfrage- und Sicht-Designer &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f7a69-126">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](query-and-view-designer-tools-visual-database-tools.md)  
  
  
