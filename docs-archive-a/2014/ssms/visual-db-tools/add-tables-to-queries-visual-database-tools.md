---
title: Hinzufügen von Tabellen zu Abfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 572002bc913cc9916a75ce2b16c12064452d250f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618433"
---
# <a name="add-tables-to-queries-visual-database-tools"></a><span data-ttu-id="31dc8-102">Hinzufügen von Tabellen zu Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="31dc8-102">Add Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="31dc8-103">Beim Erstellen einer Abfrage rufen Sie Daten aus einer Tabelle oder aus anderen Objekten mit Tabellenstruktur ab, z.B. aus Ansichten und bestimmten benutzerdefinierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="31dc8-103">When you create a query, you are retrieving data from a table or other objects structured like tables - views and certain user-defined functions.</span></span> <span data-ttu-id="31dc8-104">Objekte, mit denen Sie in der Abfrage arbeiten möchten, müssen Sie dem **Diagrammbereich**hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="31dc8-104">To work with any of these objects in your query, you add them to the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a><span data-ttu-id="31dc8-105">So fügen Sie einer Abfrage eine Tabelle oder ein Tabellenwertobjekt hinzu</span><span class="sxs-lookup"><span data-stu-id="31dc8-105">To add a table or table-valued object to a query</span></span>  
  
1.  <span data-ttu-id="31dc8-106">Klicken Sie im **Diagrammbereich** des Abfrage- und Sicht-Designers mit der rechten Maustaste auf den Hintergrund, und wählen Sie im Kontextmenü **Tabelle hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="31dc8-106">In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="31dc8-107">Wählen Sie im Dialogfeld **Tabelle hinzufügen** die Registerkarte für den Objekttyp aus, den Sie zur Abfrage hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="31dc8-107">In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.</span></span>  
  
3.  <span data-ttu-id="31dc8-108">Doppelklicken Sie in der Liste der Elemente auf jedes Element, das hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="31dc8-108">In the list of items, double-click each item you want to add.</span></span>  
  
4.  <span data-ttu-id="31dc8-109">Klicken Sie auf **Schließen**, wenn Sie das Hinzufügen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="31dc8-109">When you finish adding items, click **Close**.</span></span>  
  
     <span data-ttu-id="31dc8-110">Der Abfrage- und Sicht-Designer aktualisiert den **Diagrammbereich**, den **Kriterienbereich**und den **SQL-Bereich** entsprechend.</span><span class="sxs-lookup"><span data-stu-id="31dc8-110">The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.</span></span>  
  
 <span data-ttu-id="31dc8-111">Tabellen und Sichten werden der Abfrage automatisch hinzugefügt, wenn Sie in der Anweisung im SQL-Bereich einen entsprechenden Verweis einfügen.</span><span class="sxs-lookup"><span data-stu-id="31dc8-111">Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="31dc8-112">Der Abfrage- und Sicht-Designer zeigt keine Datenspalten für eine Tabelle oder ein Objekt mit Tabellenstruktur an, wenn Sie nicht über die erforderlichen Zugriffsrechte verfügen oder wenn der Anbieter keine Informationen über die Tabelle oder das Objekt zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="31dc8-112">The Query and View Designer will not display data columns for a table or table-structured object if you do not have sufficient access rights to it or if the provider cannot return information about it.</span></span> <span data-ttu-id="31dc8-113">In diesen Fällen werden für die Tabelle oder für das Tabellenwertobjekt nur eine Titelleiste und das Kontrollkästchen \* (Alle Spalten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31dc8-113">In such cases, only a title bar and the \* (All Columns) check box are displayed for the table or table-valued object.</span></span>  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a><span data-ttu-id="31dc8-114">So fügen Sie einer neuen Abfrage eine vorhandene Abfrage hinzu</span><span class="sxs-lookup"><span data-stu-id="31dc8-114">To add an existing query to a new query</span></span>  
  
1.  <span data-ttu-id="31dc8-115">Vergewissern Sie sich, dass der **SQL-Bereich** in der neu erstellten Abfrage angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="31dc8-115">Make sure the **SQL Pane** is displayed in the new query you are creating.</span></span>  
  
2.  <span data-ttu-id="31dc8-116">Geben Sie im **SQL-Bereich**eine öffnende und schließende Klammer ()nach dem Wort FROM ein.</span><span class="sxs-lookup"><span data-stu-id="31dc8-116">In the **SQL Pane**, type a right and left parentheses () after the word FROM.</span></span>  
  
3.  <span data-ttu-id="31dc8-117">Öffnen Sie für die vorhandene Abfrage den Abfrage-Designer.</span><span class="sxs-lookup"><span data-stu-id="31dc8-117">Open the Query Designer for the existing query.</span></span> <span data-ttu-id="31dc8-118">(Es sind nun zwei Instanzen des Abfrage-Designers geöffnet.)</span><span class="sxs-lookup"><span data-stu-id="31dc8-118">(You now have two Query Designers open.)</span></span>  
  
4.  <span data-ttu-id="31dc8-119">Öffnen Sie den **SQL-Bereich** für die innere, d.h. die bereits vorhandene Abfrage, die Sie in die neue, äußere Abfrage einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="31dc8-119">Display the **SQL Pane** for the inner query - the existing query you are including in the new, outer query.</span></span>  
  
5.  <span data-ttu-id="31dc8-120">Markieren Sie im **SQL-Bereich**den gesamten Text, und kopieren Sie ihn in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="31dc8-120">Select all the text in the **SQL Pane**, and copy it to the Clipboard.</span></span>  
  
6.  <span data-ttu-id="31dc8-121">Klicken Sie auf den **SQL-Bereich** der neuen Abfrage, positionieren Sie den Cursor zwischen den eingefügten Klammern, und fügen Sie den Inhalt der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="31dc8-121">Click in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.</span></span>  
  
7.  <span data-ttu-id="31dc8-122">Fügen Sie dann im **SQL-Bereich**einen Alias nach der schließenden Klammer ein.</span><span class="sxs-lookup"><span data-stu-id="31dc8-122">Still in the **SQL Pane**, add an alias after the right parenthesis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31dc8-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31dc8-123">See Also</span></span>  
 <span data-ttu-id="31dc8-124">[Erstellen von Tabellenaliasen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31dc8-124">[Create Table Aliases &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="31dc8-125">[Entfernen von Tabellen aus Abfragen &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31dc8-125">[Remove Tables from Queries &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31dc8-126">[Angeben von Suchkriterien &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31dc8-126">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="31dc8-127">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="31dc8-127">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="31dc8-128">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="31dc8-128">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
