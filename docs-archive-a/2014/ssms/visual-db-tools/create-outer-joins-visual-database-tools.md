---
title: Erstellen von äußeren Joins (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- joins [SQL Server], outer
ms.assetid: 18de47b1-f936-427d-b852-fe6d20334f71
author: stevestein
ms.author: sstein
ms.openlocfilehash: f02c0be049e2e75e1a657bb3c027d20430d562cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725209"
---
# <a name="create-outer-joins-visual-database-tools"></a><span data-ttu-id="d1527-102">Erstellen von äußeren Joins (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d1527-102">Create Outer Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="d1527-103">In der Standardeinstellung wird vom [Abfrage- und Sicht-Designer](visual-database-tools.md) ein innerer Join zwischen Tabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d1527-103">By default, the [Query and View Designer](visual-database-tools.md) creates an inner join between tables.</span></span> <span data-ttu-id="d1527-104">Innere Joins entfernen die Zeilen, die nicht mit einer Zeile aus der anderen Tabelle übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d1527-104">Inner joins eliminate the rows that do not match with a row from the other table.</span></span> <span data-ttu-id="d1527-105">Äußere Joins dagegen geben alle Zeilen aus mindestens einer der in der FROM-Klausel genannten Tabellen oder Sichten zurück, sofern diese Zeilen ggf. die WHERE- oder HAVING-Suchbedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d1527-105">Outer joins, however, return all rows from at least one of the tables or views mentioned in the FROM clause, as long as those rows meet any WHERE or HAVING search conditions.</span></span> <span data-ttu-id="d1527-106">Wenn Sie Datenzeilen in das Resultset einschließen möchten, die keine Übereinstimmung in der verknüpften Tabelle aufweisen, können Sie einen äußeren Join erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1527-106">If you want to include data rows in the result set that do not have a match in the joined table, you can create an outer join.</span></span>  
  
 <span data-ttu-id="d1527-107">Beim Erstellen eines äußeren Join ist die Reihenfolge relevant, in der Tabellen in der SQL-Anweisung angezeigt werden (wie im SQL-Bereich widergespiegelt).</span><span class="sxs-lookup"><span data-stu-id="d1527-107">When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant.</span></span> <span data-ttu-id="d1527-108">Die zuerst hinzugefügte Tabelle wird als "linke" Tabelle und die zweite hinzugefügte Tabelle als "rechte" Tabelle betrachtet.</span><span class="sxs-lookup"><span data-stu-id="d1527-108">The first table you add becomes the "left" table and the second table becomes the "right" table.</span></span> <span data-ttu-id="d1527-109">(Die tatsächliche Reihenfolge, in der die Tabellen im [Diagrammbereich](diagram-pane-visual-database-tools.md) angezeigt werden, spielt keine Rolle.) Durch das Angeben eines linken oder rechten äußeren Joins verweisen Sie auf die Reihenfolge, in der Tabellen zur Abfrage hinzugefügt wurden, sowie auf die Reihenfolge, in der sie in der SQL-Anweisung im [SQL-Bereich](sql-pane-visual-database-tools.md)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1527-109">(The actual order in which the tables appear in the [Diagram pane](diagram-pane-visual-database-tools.md) is not significant.) When you specify a left or right outer join, you are referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-an-outer-join"></a><span data-ttu-id="d1527-110">So erstellen Sie einen äußeren Joins</span><span class="sxs-lookup"><span data-stu-id="d1527-110">To create an outer join</span></span>  
  
1.  <span data-ttu-id="d1527-111">Erstellen Sie den Joins automatisch oder manuell.</span><span class="sxs-lookup"><span data-stu-id="d1527-111">Create the join, either automatically or manually.</span></span> <span data-ttu-id="d1527-112">Weitere Informationen finden Sie unter [Automatisches Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) oder [Manuelles Verknüpfen von Tabellen &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1527-112">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) or [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="d1527-113">Wählen Sie im Diagrammbereich die Joinlinie aus. Wählen Sie anschließend im Menü **Abfrage-Designer** die Option **Alle Zeilen von \<tablename> auswählen** aus, und wählen Sie den Befehl aus, der die Tabelle enthält, deren zusätzliche Zeilen Sie einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d1527-113">Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename>**, selecting the command that includes the table whose extra rows you want to include.</span></span>  
  
    -   <span data-ttu-id="d1527-114">Wählen Sie die erste Tabelle aus, um eine linken äußeren Joins zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1527-114">Choose the first table to create a left outer join.</span></span>  
  
    -   <span data-ttu-id="d1527-115">Wählen Sie die zweite Tabelle aus, um eine rechten äußeren Joins zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1527-115">Choose the second table to create a right outer join.</span></span>  
  
    -   <span data-ttu-id="d1527-116">Wählen Sie beide Tabellen aus, um eine vollständigen äußeren Joins zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1527-116">Choose both tables to create a full outer join.</span></span>  
  
 <span data-ttu-id="d1527-117">Wenn Sie angeben, ändert der Abfrage- und Sicht-Designer die Joinlinie zum Anzeigen eines äußeren Joins.</span><span class="sxs-lookup"><span data-stu-id="d1527-117">When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.</span></span>  
  
 <span data-ttu-id="d1527-118">Außerdem ändert der Abfrage- und Sicht-Designer die SQL-Anweisung im SQL-Bereich, um die Änderung des Jointyps widerzuspiegeln, wie in der folgenden Anweisung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d1527-118">In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:</span></span>  
  
```  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
```  
  
 <span data-ttu-id="d1527-119">Da ein äußerer Join Zeilen ohne Übereinstimmungen einschließt, kann diese zum Suchen von Zeilen verwendet werden, die Fremdschlüsseleinschränkungen verletzen.</span><span class="sxs-lookup"><span data-stu-id="d1527-119">Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints.</span></span> <span data-ttu-id="d1527-120">Erstellen Sie hierzu einen äußeren Join, und fügen Sie anschließend eine Suchbedingung zum Suchen von Zeilen hinzu, in denen die Primärschlüsselspalte der äußersten rechten Tabelle Null ist.</span><span class="sxs-lookup"><span data-stu-id="d1527-120">To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null.</span></span> <span data-ttu-id="d1527-121">Mit dem folgenden äußeren Join werden z. B. Zeilen in der Tabelle `employee` gesucht, für die keine übereinstimmenden Zeilen in der Tabelle `jobs` vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="d1527-121">For example, the following outer join finds rows in the `employee` table that do not have corresponding rows in the `jobs` table:</span></span>  
  
```  
SELECT employee.emp_id, employee.job_id  
FROM employee LEFT OUTER JOIN jobs   
   ON employee.job_id = jobs.job_id  
WHERE (jobs.job_id IS NULL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1527-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1527-122">See Also</span></span>  
 <span data-ttu-id="d1527-123">[Abfragen mit Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d1527-123">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d1527-124">Verknüpfen (Dialogfeld) &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d1527-124">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
