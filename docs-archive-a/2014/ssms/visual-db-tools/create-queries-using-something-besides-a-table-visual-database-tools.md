---
title: Erstellen von Abfragen mit etwas neben einer Tabelle (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], queries
- queries [SQL Server], creating
ms.assetid: 8e4a1f0a-8a42-4733-be8d-e21d6dbddb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0444c20fe10080949930f23623d5699f7fd3712c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608202"
---
# <a name="create-queries-using-something-besides-a-table-visual-database-tools"></a><span data-ttu-id="30d03-102">Erstellen von Abfragen mit anderen Quellen als einer Tabelle (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="30d03-102">Create Queries using Something Besides a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="30d03-103">Wenn Sie eine Abrufabfrage erstellen, geben Sie die aufzunehmenden Spalten und Zeilen sowie den Ort an, von dem der Abfrageprozessor die Ausgangsdaten abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="30d03-103">Whenever you write a retrieval query, you articulate what columns you want, what rows you want, and where the query processor should find the original data.</span></span> <span data-ttu-id="30d03-104">Üblicherweise handelt es sich bei diesen Ausgangsdaten um eine Tabelle oder mehrere verknüpfte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="30d03-104">Typically, this original data consists of a table or several tables joined together.</span></span> <span data-ttu-id="30d03-105">Die zugrunde liegenden Daten können jedoch auch aus anderen Quellen stammen.</span><span class="sxs-lookup"><span data-stu-id="30d03-105">But the original data can come from sources other than tables.</span></span> <span data-ttu-id="30d03-106">Dies können Sichten, Abfragen, Synonyme oder benutzerdefinierte Funktionen sein, die eine Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="30d03-106">In fact, it can come from views, queries, synonyms, or user-defined functions that return a table.</span></span>  
  
## <a name="using-a-view-in-place-of-a-table"></a><span data-ttu-id="30d03-107">Verwenden einer Sicht anstelle einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="30d03-107">Using a View in Place of a Table</span></span>  
 <span data-ttu-id="30d03-108">Sie können Zeilen aus einer Sicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="30d03-108">You can select rows from a view.</span></span> <span data-ttu-id="30d03-109">Nehmen Sie z. B. an, dass die Datenbank eine Sicht mit der Bezeichnung "ExpensiveBooks" enthält, in der jede Zeile einen Titel mit einem Preis über 19,99 beschreibt.</span><span class="sxs-lookup"><span data-stu-id="30d03-109">For example, suppose the database includes a view called "ExpensiveBooks," in which each row describes a title whose price exceeds 19.99.</span></span> <span data-ttu-id="30d03-110">Die Definition der Sicht kann folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="30d03-110">The view definition might look like this:</span></span>  
  
```  
SELECT *  
FROM titles  
WHERE price > 19.99  
  
```  
  
 <span data-ttu-id="30d03-111">Sie können alle teuren Titel zum Thema Psychologie auswählen, indem Sie einfach alle Psychologiebücher aus der Sicht ExpensiveBooks abrufen.</span><span class="sxs-lookup"><span data-stu-id="30d03-111">You can select the expensive psychology books merely by selecting the psychology books from the ExpensiveBooks view.</span></span> <span data-ttu-id="30d03-112">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="30d03-112">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM ExpensiveBooks  
WHERE type = 'psychology'  
  
```  
  
 <span data-ttu-id="30d03-113">In ähnlicher Weise kann eine Sicht in ein JOIN-Vorgang eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="30d03-113">Similarly, a view can participate in a JOIN operation.</span></span> <span data-ttu-id="30d03-114">Sie können z. B. die Verkäufe an teuren Büchern ermitteln, indem Sie die Tabelle der Verkäufe mit der Sicht ExpensiveBooks verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="30d03-114">For example, you can find the sales of expensive books merely by joining the sales table to the ExpensiveBooks view.</span></span> <span data-ttu-id="30d03-115">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="30d03-115">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM sales   
         INNER JOIN   
         ExpensiveBooks   
         ON sales.title_id   
         =  ExpensiveBooks.title_id  
  
```  
  
 <span data-ttu-id="30d03-116">Weitere Informationen zum Hinzufügen einer Sicht zu einer Abfrage finden Sie unter [Hinzufügen von Tabellen zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30d03-116">For more information about adding a view to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-query-in-place-of-a-table"></a><span data-ttu-id="30d03-117">Verwenden einer Abfrage anstelle einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="30d03-117">Using a Query in Place of a Table</span></span>  
 <span data-ttu-id="30d03-118">Sie können Zeilen aus einer Abfrage auswählen.</span><span class="sxs-lookup"><span data-stu-id="30d03-118">You can select rows from a query.</span></span> <span data-ttu-id="30d03-119">Nehmen Sie z.B. an, dass Sie bereits eine Abfrage erstellt haben, die die Titel und IDs für Bücher zurückgibt, für die ein Mitautor angegeben ist, also alle Bücher mit mehreren Autoren.</span><span class="sxs-lookup"><span data-stu-id="30d03-119">For example, suppose you have already written a query retrieving titles and identifiers of the coauthored books - the books with more than one author.</span></span> <span data-ttu-id="30d03-120">Die SQL-Anweisung könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="30d03-120">The SQL might look like this:</span></span>  
  
```  
SELECT   
     titles.title_id, title, type  
FROM   
     titleauthor   
         INNER JOIN  
         titles   
         ON titleauthor.title_id   
         =  titles.title_id   
GROUP BY   
     titles.title_id, title, type  
HAVING COUNT(*) > 1  
  
```  
  
 <span data-ttu-id="30d03-121">Sie können nun eine weitere Abfrage erstellen, die auf diesem Ergebnis aufbaut.</span><span class="sxs-lookup"><span data-stu-id="30d03-121">You can then write another query that builds on this result.</span></span> <span data-ttu-id="30d03-122">Dies kann z. B. eine Abfrage sein, die alle Psychologiebücher ermittelt, die von mehreren Autoren geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="30d03-122">For example, you can write a query that retrieves the coauthored psychology books.</span></span> <span data-ttu-id="30d03-123">In dieser Abfrage können Sie die bereits vorhandene Abfrage als Quelle für die neuen Abfragedaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="30d03-123">To write this new query, you can use the existing query as the source of the new query's data.</span></span> <span data-ttu-id="30d03-124">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="30d03-124">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    title  
FROM   
    (  
    SELECT   
        titles.title_id,   
        title,   
        type  
    FROM   
        titleauthor   
            INNER JOIN  
            titles   
            ON titleauthor.title_id   
            =  titles.title_id   
    GROUP BY   
        titles.title_id,   
        title,   
        type  
    HAVING COUNT(*) > 1  
    )   
    co_authored_books  
WHERE     type = 'psychology'  
  
```  
  
 <span data-ttu-id="30d03-125">Der hervorgehobene Text zeigt die vorhandene Abfrage, die die Ausgangsdaten für die neue Abfrage liefert.</span><span class="sxs-lookup"><span data-stu-id="30d03-125">The emphasized text shows the existing query used as the source of the new query's data.</span></span> <span data-ttu-id="30d03-126">Beachten Sie, dass in der neuen Abfrage ein Alias (co_authored_books) für die vorhandene Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30d03-126">Note that the new query uses an alias ("co_authored_books") for the existing query.</span></span> <span data-ttu-id="30d03-127">Weitere Informationen zu Aliasen finden Sie unter [Erstellen von Tabellenaliasen &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) und [Erstellen von Spaltenaliasen &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30d03-127">For more information about aliases, see [Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) and [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="30d03-128">In ähnlicher Weise kann eine Abfrage in ein JOIN-Vorgang eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="30d03-128">Similarly, a query can participate in a JOIN operation.</span></span> <span data-ttu-id="30d03-129">Sie können z. B. die Verkäufe an teuren Büchern mit Mitautorenschaft ermitteln, indem Sie die Sicht ExpensiveBooks mit der Abfrage verknüpfen, die die Bücher mit mehreren Autoren zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="30d03-129">For example, you can find the sales of expensive coauthored books merely by joining the ExpensiveBooks view to the query retrieving the coauthored books.</span></span> <span data-ttu-id="30d03-130">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="30d03-130">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    ExpensiveBooks.title  
FROM   
    ExpensiveBooks   
        INNER JOIN  
        (  
        SELECT   
            titles.title_id,   
            title,   
            type  
        FROM   
            titleauthor   
                INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
        GROUP BY   
            titles.title_id,   
            title,   
            type  
        HAVING COUNT(*) > 1  
        )  
```  
  
 <span data-ttu-id="30d03-131">Weitere Informationen zum Hinzufügen einer Abfrage zu einer Abfrage finden Sie unter [Hinzufügen von Tabellen zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30d03-131">For more information about adding a query to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-user-defined-function-in-place-of-a-table"></a><span data-ttu-id="30d03-132">Verwenden einer benutzerdefinierten Funktion anstelle einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="30d03-132">Using a User-Defined Function in Place of a Table</span></span>  
 <span data-ttu-id="30d03-133">In SQL Server 2000 oder höher können Sie eine benutzerdefinierte Funktion erstellen, die eine Tabelle zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="30d03-133">In SQL Server 2000 or higher, you can create a user-defined function that returns a table.</span></span> <span data-ttu-id="30d03-134">Solche Funktionen eignen sich zum Ausführen komplexer oder prozeduraler Logiken.</span><span class="sxs-lookup"><span data-stu-id="30d03-134">Such functions are useful for performing complex or procedural logic.</span></span>  
  
 <span data-ttu-id="30d03-135">Angenommen die Tabelle der Mitarbeiter enthält eine zusätzliche Spalte employee.manager_emp_id und eine Fremdschlüsselbeziehung liegt zwischen manager_emp_id und employee.emp_id vor.</span><span class="sxs-lookup"><span data-stu-id="30d03-135">For example, suppose the employee table contains an additional column, employee.manager_emp_id, and that a foreign key exists from manager_emp_id to employee.emp_id.</span></span> <span data-ttu-id="30d03-136">Innerhalb jeder Zeile der Tabelle der Mitarbeiter gibt die Spalte manager_emp_id den Vorgesetzten des Mitarbeiters an.</span><span class="sxs-lookup"><span data-stu-id="30d03-136">Within each row of the employee table, the manager_emp_id column indicates the employee's boss.</span></span> <span data-ttu-id="30d03-137">Genauer gesagt wird die emp_id des Vorgesetzten des Mitarbeiters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30d03-137">More precisely, it indicates the employee's boss's emp_id.</span></span> <span data-ttu-id="30d03-138">Sie können eine benutzerdefinierte Funktion erstellen, die eine Tabelle mit jeweils einer Zeile für jeden Mitarbeiter zurückgibt, der innerhalb der Organisationshierarchie unter einem Manager mit der angegebenen Tätigkeitsstufe arbeitet.</span><span class="sxs-lookup"><span data-stu-id="30d03-138">You can create a user-defined function that returns a table containing one row for each employee working within a particular high-level manager's organizational hierarchy.</span></span> <span data-ttu-id="30d03-139">Die Funktion trägt die Bezeichnung „fn_GetWholeTeam“ und ist so formuliert, dass eine Eingabevariable übergeben werden kann: die emp_id des Managers, dessen Team Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="30d03-139">You might call the function fn_GetWholeTeam, and design it to take an input variable - the emp_id of the manager whose team you want to retrieve.</span></span>  
  
 <span data-ttu-id="30d03-140">Sie können eine Abfrage erstellen, die die Funktion fn_GetWholeTeam als Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="30d03-140">You can write a query that uses the fn_GetWholeTeam function as a source of data.</span></span> <span data-ttu-id="30d03-141">Hierfür kann folgende SQL-Anweisung formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="30d03-141">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *   
FROM   
     fn_GetWholeTeam ('VPA30890F')  
  
```  
  
 <span data-ttu-id="30d03-142">"VPA30890F" ist die emp_id des Managers, dessen Organisation abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="30d03-142">"VPA30890F" is the emp_id of the manager whose organization you want to retrieve.</span></span> <span data-ttu-id="30d03-143">Weitere Informationen zum Hinzufügen einer Abfrage zu einer benutzerdefinierten Funktion finden Sie unter [Hinzufügen von Tabellen zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30d03-143">For more information about adding a user-defined function to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="30d03-144">Eine vollständige Beschreibung der benutzerdefinierten Funktionen finden Sie unter [Benutzerdefinierte Funktionen](../../relational-databases/user-defined-functions/user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="30d03-144">For a complete description of user-defined functions, see [User-Defined Functions](../../relational-databases/user-defined-functions/user-defined-functions.md).</span></span>  
  
  
