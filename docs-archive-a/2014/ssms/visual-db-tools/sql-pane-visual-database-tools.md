---
title: SQL-Bereich (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], SQL pane
- View Designer, SQL pane
- SQL pane [Visual Database Tools]
ms.assetid: dbabab18-0614-415b-a2ef-9bcd0d320d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a87ec1d5517852fefb152e0ec7b3165fa32988b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695078"
---
# <a name="sql-pane-visual-database-tools"></a><span data-ttu-id="6d6d8-102">SQL-Bereich (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6d6d8-102">SQL Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="6d6d8-103">Sie können den SQL-Bereich verwenden, um eine eigene SQL-Anweisung zu erstellen. Sie können auch den Kriterienbereich und den Diagrammbereich verwenden, um die Anweisung zu erstellen, wobei dadurch die SQL-Anweisungen im SQL-Bereich erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-103">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="6d6d8-104">Beim Erstellen einer Abfrage wird der SQL-Bereich automatisch aktualisiert und neu formatiert, um die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-104">As you build your query, the SQL pane automatically updates and reformats for easy readability.</span></span>  
  
 <span data-ttu-id="6d6d8-105">Öffnen Sie zuerst den Abfrage- und Sicht-Designer, um den SQL-Bereich zu öffnen. (Wählen Sie dazu im Server-Explorer ein Datenbankobjekt aus, und klicken Sie im Menü **Datenbank** auf **Neue Abfrage**.)</span><span class="sxs-lookup"><span data-stu-id="6d6d8-105">To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, click **New Query**).</span></span> <span data-ttu-id="6d6d8-106">Zeigen Sie dann im Menü **Abfrage-Designer** auf **Bereich** , und klicken Sie auf **SQL**.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-106">Then from the **Query Designer** menu point to **Pane** and click **SQL**.</span></span>  
  
 <span data-ttu-id="6d6d8-107">Im SQL-Bereich können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="6d6d8-107">In the SQL pane you can:</span></span>  
  
-   <span data-ttu-id="6d6d8-108">neue Abfragen durch die Eingabe von SQL-Anweisungen erstellen</span><span class="sxs-lookup"><span data-stu-id="6d6d8-108">Create new queries by entering SQL statements.</span></span>  
  
-   <span data-ttu-id="6d6d8-109">die SQL-Anweisung ändern, die vom Abfrage- und Sicht-Designer basierend auf Ihren Einstellungen im Diagrammbereich und im Kriterienbereich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-109">Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="6d6d8-110">Anweisungen eingeben, die auf spezielle Funktionen der von Ihnen verwendeten Datenbank zugreifen</span><span class="sxs-lookup"><span data-stu-id="6d6d8-110">Enter statements that take advantage of features specific to the database you are using.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d6d8-111">Machen Sie sich mit den Regeln vertraut, über die Datenbankobjekte in der von Ihnen verwendeten Datenbank identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-111">Be sure you know the rules for identifying database objects in the database you are using.</span></span> <span data-ttu-id="6d6d8-112">Ausführliche Informationen finden Sie in der Dokumentation des Datenbankverwaltungssystems.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-112">For details, see the documentation for your database management system.</span></span>  
  
## <a name="statements-in-the-sql-pane"></a><span data-ttu-id="6d6d8-113">Anweisungen im SQL-Bereich</span><span class="sxs-lookup"><span data-stu-id="6d6d8-113">Statements in the SQL Pane</span></span>  
 <span data-ttu-id="6d6d8-114">Sie können die aktuelle Abfrage direkt im SQL-Bereich bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-114">You can edit the current query directly in the SQL pane.</span></span> <span data-ttu-id="6d6d8-115">Sobald Sie in einen anderen Bereich wechseln, formatiert der Abfrage- und Sicht-Designer automatisch Ihre Anweisung und aktualisiert anschließend die Angaben im Diagrammbereich und im Kriterienbereich.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-115">When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.</span></span>  
  
 <span data-ttu-id="6d6d8-116">Wenn der Diagramm- und der Kriterienbereich angezeigt werden und Ihre Anweisung nicht in diesen Bereichen dargestellt werden kann, meldet der Abfrage- und Sicht-Designer einen Fehler und bietet Ihnen zwei Optionen an:</span><span class="sxs-lookup"><span data-stu-id="6d6d8-116">If your statement cannot be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:</span></span>  
  
-   <span data-ttu-id="6d6d8-117">Ignorieren, dass die Anweisung nicht im Diagrammbereich und im Kriterienbereich dargestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-117">Ignore that the statement can not be represented in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="6d6d8-118">Rückgängigmachen der nicht darstellbaren Änderung und Zurücksetzen auf die aktuellste Version der SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-118">Undo the change that can not be represented and revert to the most recent version of the SQL statement.</span></span>  
  
 <span data-ttu-id="6d6d8-119">Wenn Sie ignorieren, dass die Anweisung nicht im Diagrammbereich und im Kriterienbereich dargestellt werden kann, werden die anderen Bereiche im Abfrage- und Sicht-Designer ausgeblendet. Damit wird angegeben, dass der Inhalt des SQL-Bereichs in diesen Bereichen nicht wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-119">If you choose to ignore that the statement can not be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.</span></span>  
  
 <span data-ttu-id="6d6d8-120">Sie können mit dem Bearbeiten der Anweisung fortfahren und diese wie jede andere SQL-Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-120">You can continue to edit the statement and execute it as you would any SQL statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d6d8-121">Wenn Sie eine SQL-Anweisung eingeben und anschließend weitere Änderungen an der Abfrage im Diagrammbereich bzw. Kriterienbereich vornehmen, erstellt der Abfrage- und Sicht-Designer die SQL-Anweisung neu und aktualisiert ihre Anzeige.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-121">If you enter an SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement.</span></span> <span data-ttu-id="6d6d8-122">In einigen Fällen wird hierbei eine SQL-Anweisung generiert, die in ihrer Struktur von der ursprünglich eingegebenen Anweisung abweicht (jedoch nach wie vor die gleichen Ergebnisse liefert).</span><span class="sxs-lookup"><span data-stu-id="6d6d8-122">In some cases, this action results in an SQL statement that is constructed differently from the one you originally entered (though it will always yield the same results).</span></span> <span data-ttu-id="6d6d8-123">Diese Abweichung tritt häufig dann auf, wenn Sie Suchbedingungen verwenden, in denen mehrere Klauseln durch AND und OR verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="6d6d8-123">This difference is particularly likely when you are working with search conditions that involve several clauses linked with AND and OR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6d8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d6d8-124">See Also</span></span>  
 <span data-ttu-id="6d6d8-125">[Erstellen von Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6d6d8-125">[Create Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="6d6d8-126">[Ausführen von Abfragen &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6d6d8-126">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6d6d8-127">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6d6d8-127">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6d6d8-128">[Diagrammbereich &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6d6d8-128">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6d6d8-129">[Kriterienbereich &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6d6d8-129">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6d6d8-130">Ergebnisbereich &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6d6d8-130">Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
