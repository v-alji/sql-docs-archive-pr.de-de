---
title: MSSQLSERVER_207 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 207 (Database Engine error)
ms.assetid: d1ab00c7-0331-437a-84fe-bae53b82feec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd6044c08ecd5a73f539bfbc1139d6257c2db9d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698259"
---
# <a name="mssqlserver_207"></a><span data-ttu-id="e0c1c-102">MSSQLSERVER_207</span><span class="sxs-lookup"><span data-stu-id="e0c1c-102">MSSQLSERVER_207</span></span>
    
## <a name="details"></a><span data-ttu-id="e0c1c-103">Details</span><span class="sxs-lookup"><span data-stu-id="e0c1c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0c1c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e0c1c-104">Product Name</span></span>|<span data-ttu-id="e0c1c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e0c1c-105">SQL Server</span></span>|  
|<span data-ttu-id="e0c1c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e0c1c-106">Event ID</span></span>|<span data-ttu-id="e0c1c-107">207</span><span class="sxs-lookup"><span data-stu-id="e0c1c-107">207</span></span>|  
|<span data-ttu-id="e0c1c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e0c1c-108">Event Source</span></span>|<span data-ttu-id="e0c1c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e0c1c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e0c1c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e0c1c-110">Component</span></span>|<span data-ttu-id="e0c1c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e0c1c-111">SQLEngine</span></span>|  
|<span data-ttu-id="e0c1c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e0c1c-112">Symbolic Name</span></span>|<span data-ttu-id="e0c1c-113">SQ_BADCOL</span><span class="sxs-lookup"><span data-stu-id="e0c1c-113">SQ_BADCOL</span></span>|  
|<span data-ttu-id="e0c1c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e0c1c-114">Message Text</span></span>|<span data-ttu-id="e0c1c-115">Ungültiger Spaltenname '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-115">Invalid column name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e0c1c-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e0c1c-116">Explanation</span></span>  
 <span data-ttu-id="e0c1c-117">Dieser Abfragefehler kann durch eines der folgenden Probleme verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-117">This query error can be caused by one of the following problems.</span></span>  
  
-   <span data-ttu-id="e0c1c-118">Der Spaltenname ist falsch geschrieben, oder die Spalte ist in keiner der angegebenen Tabellen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-118">The column name is misspelled or the column does not exist in any of the specified tables.</span></span>  
  
-   <span data-ttu-id="e0c1c-119">Bei der Sortierung der Datenbank wird nach Groß-/Kleinschreibung unterschieden, und die in der Abfrage angegebene Schreibweise entspricht nicht der Schreibweise, die in der Tabelle für die Spalte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-119">The collation of the database is case-sensitive and the case of the column name specified in the query does not match the case of the column defined in the table.</span></span> <span data-ttu-id="e0c1c-120">Wenn eine Spalte z.B. als **LastName** angegeben ist und die Datenbank eine Sortierung verwendet, die nach Groß-/Kleinschreibung unterscheidet, geben Abfragen, die auf die Spalte als **Lastname** oder **lastname** verweisen, den Fehler 207 zurück, da der Spaltenname nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-120">For example, when a column is defined in a table as **LastName** and the database uses a case-sensitive collation, queries that refer to the column as **Lastname** or **lastname** will cause error 207 to return because the column name does not match.</span></span>  
  
-   <span data-ttu-id="e0c1c-121">Auf einen in der SELECT-Klausel definierten Spaltenalias wird in einer anderen Klausel, beispielsweise WHERE oder GROUP BY, verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-121">A column alias, defined in the SELECT clause, is referenced in another clause such as a WHERE or GROUP BY clause.</span></span> <span data-ttu-id="e0c1c-122">Beispielsweise wird in der folgenden Abfrage der Spaltenalias `Year` in der SELECT-Klausel definiert, und in der GROUP BY-Klausel wird auf diesen verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-122">For example, the following query defines the column alias `Year` in the SELECT clause and refers to it in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year, SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY Year;  
    ```  
  
     <span data-ttu-id="e0c1c-123">Aufgrund der Reihenfolge, in der die Abfrageklauseln verarbeitet werden, wird in diesem Beispiel der Fehler 207 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-123">Due to the order in which query clauses are logically processed, the example returns error 207.</span></span> <span data-ttu-id="e0c1c-124">Die Verarbeitungsreihenfolge ist die Folgende:</span><span class="sxs-lookup"><span data-stu-id="e0c1c-124">The processing order is as follows:</span></span>  
  
    1.  <span data-ttu-id="e0c1c-125">FROM</span><span class="sxs-lookup"><span data-stu-id="e0c1c-125">FROM</span></span>  
  
    2.  <span data-ttu-id="e0c1c-126">EIN</span><span class="sxs-lookup"><span data-stu-id="e0c1c-126">ON</span></span>  
  
    3.  <span data-ttu-id="e0c1c-127">JOIN</span><span class="sxs-lookup"><span data-stu-id="e0c1c-127">JOIN</span></span>  
  
    4.  <span data-ttu-id="e0c1c-128">WHERE</span><span class="sxs-lookup"><span data-stu-id="e0c1c-128">WHERE</span></span>  
  
    5.  <span data-ttu-id="e0c1c-129">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="e0c1c-129">GROUP BY</span></span>  
  
    6.  <span data-ttu-id="e0c1c-130">WITH CUBE oder WITH ROLLUP</span><span class="sxs-lookup"><span data-stu-id="e0c1c-130">WITH CUBE or WITH ROLLUP</span></span>  
  
    7.  <span data-ttu-id="e0c1c-131">HAVING</span><span class="sxs-lookup"><span data-stu-id="e0c1c-131">HAVING</span></span>  
  
    8.  <span data-ttu-id="e0c1c-132">SELECT</span><span class="sxs-lookup"><span data-stu-id="e0c1c-132">SELECT</span></span>  
  
    9. <span data-ttu-id="e0c1c-133">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="e0c1c-133">DISTINCT</span></span>  
  
    10. <span data-ttu-id="e0c1c-134">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="e0c1c-134">ORDER BY</span></span>  
  
    11. <span data-ttu-id="e0c1c-135">TOP</span><span class="sxs-lookup"><span data-stu-id="e0c1c-135">TOP</span></span>  
  
     <span data-ttu-id="e0c1c-136">Da vor dem Verarbeiten der SELECT-Klausel kein Spaltenalias definiert wird, ist der Aliasname beim Verarbeiten der GROUP BY-Klausel unbekannt.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-136">Because a column alias is not defined until the SELECT clause is processed, the alias name is unknown when the GROUP BY clause is processed.</span></span>  
  
-   <span data-ttu-id="e0c1c-137">Die MERGE-Anweisung löst diesen Fehler aus, wenn die *<merge_matched>* -Klausel auf Spalten in der Quelltabelle verweist, jedoch von der Quelltabelle in der WHEN NOT MATCHED BY SOURCE-Klausel keine Zeilen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-137">The MERGE statement raises this error when the *<merge_matched>* clause references columns in the source table but no rows are returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="e0c1c-138">Dieser Fehler tritt auf, da auf die Spalten in der Quelltabelle nicht zugegriffen werden kann, wenn in der Abfrage keine Zeilen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-138">The error occurs because the columns in the source table cannot be accessed when no rows are returned to the query.</span></span> <span data-ttu-id="e0c1c-139">Die Klausel `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` kann beispielsweise dazu führen, dass die Anweisung fehlschlägt, wenn der Zugriff auf `Col1` in der Quelltabelle nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-139">For example, the clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` may cause the statement to fail if `Col1` in the source table is inaccessible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0c1c-140">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e0c1c-140">User Action</span></span>  
 <span data-ttu-id="e0c1c-141">Überprüfen Sie die folgenden Informationen, und korrigieren Sie die Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-141">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="e0c1c-142">Der Spaltenname ist in der Tabelle vorhanden und korrekt geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-142">The column name exists in the table and is spelled correctly.</span></span> <span data-ttu-id="e0c1c-143">Im folgenden Beispiel wird die **sys.columns**-Katalogsicht abgefragt, um alle Spaltennamen der angegebenen Tabelle zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-143">The following example queries the **sys.columns** catalog view to return all column names for a given table.</span></span>  
  
    ```  
    SELECT name FROM sys.columns WHERE object_id = OBJECT_ID('schema_name.table_name');  
    ```  
  
-   <span data-ttu-id="e0c1c-144">Die Unterscheidung nach Groß-/Kleinschreibung der Datenbanksortierung.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-144">The case sensitivity of the database collation.</span></span> <span data-ttu-id="e0c1c-145">Mit der folgenden Anweisung wird die Sortierung der angegebenen Datenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-145">The following statement returns the collation of the specified database.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="e0c1c-146">Die Abkürzung CS im Sortierungsnamen gibt an, dass bei der Sortierung nach Groß-/Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-146">The abbreviation CS in the collation name indicates the collation is case-sensitive.</span></span> <span data-ttu-id="e0c1c-147">Beispiel: Latin1_General_CS_AS ist eine Sortierung, bei der nach Groß-/Kleinschreibung und nach Akzent unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-147">For example, Latin1_General_CS_AS is a case-sensitive and accent-sensitive collation.</span></span> <span data-ttu-id="e0c1c-148">Ändern Sie den Spaltennamen zu der in der Tabelle definierten Schreibweise des Spaltennamens.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-148">Modify the column name to match the case of the column name as it is defined in the table.</span></span>  
  
-   <span data-ttu-id="e0c1c-149">Ein Verweis auf einen Spaltenalias ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-149">A column alias is referenced incorrectly.</span></span> <span data-ttu-id="e0c1c-150">Ändern Sie die Anweisung, indem Sie den Ausdruck wiederholen, mit dem der Alias in der entsprechenden Klausel definiert wird, oder indem Sie eine abgeleitete Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-150">Modify the statement by repeating the expression that defines the alias in the appropriate clause or by using a derived table.</span></span> <span data-ttu-id="e0c1c-151">Im folgenden Beispiel werden die Ausdrücke wiederholt, mit denen in der GROUP BY-Klausel der Alias `Year` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-151">The following example repeats the expressions that define the `Year` alias in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year ,SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY DATEPART(yyyy,OrderDate);  
    ```  
  
     <span data-ttu-id="e0c1c-152">Im folgenden Beispiel wird eine abgeleitete Tabelle verwendet, um den Aliasnamen für andere Klauseln in der Abfrage verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-152">The following example uses a derived table to make the alias name available to other clauses in the query.</span></span> <span data-ttu-id="e0c1c-153">Beachten Sie, dass der Alias `Year` in der FROM-Klausel definiert wird, die zuerst verarbeitet wird. Dadurch ist der Alias für die Verwendung in anderen Klauseln der Abfrage verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-153">Notice that the alias `Year` is defined in the FROM clause, which is processed first, and so makes the alias available for use in other clauses in the query.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT d.Year, SUM(TotalDue) AS Total  
    FROM (SELECT DATEPART(yyyy,OrderDate) AS Year, TotalDue  
          FROM Sales.SalesOrderHeader)AS d  
    GROUP BY Year;  
    ```  
  
-   <span data-ttu-id="e0c1c-154">Die WHEN NOT MATCHED BY SOURCE-Klausel in der MERGE-Anweisung verweist auf einen Wert, auf den zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-154">The WHEN NOT MATCHED BY SOURCE clause in the MERGE statement refers to a value that can be accessed.</span></span> <span data-ttu-id="e0c1c-155">Ändern Sie die MERGE-Anweisung so, dass die Quelltabelle in der WHEN NOT MATCHED BY SOURCE-Klausel mindestens eine Zeile zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-155">Modify the MERGE statement so that at least one row is returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="e0c1c-156">Möglicherweise müssen Sie z. B. die für die Klausel angegebene Suchbedingung hinzufügen oder überarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-156">For example, you might need to add or revise the search condition specified for the clause.</span></span> <span data-ttu-id="e0c1c-157">Wahlweise können Sie die Klausel so ändern, dass diese einen Wert angibt, der nicht auf die Quelltabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-157">Alternatively, you can modify the clause to specify a value that does not reference the source table.</span></span> <span data-ttu-id="e0c1c-158">Beispiel: `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span><span class="sxs-lookup"><span data-stu-id="e0c1c-158">For example, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c1c-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0c1c-159">See Also</span></span>  
 <span data-ttu-id="e0c1c-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0c1c-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span></span>  
 <span data-ttu-id="e0c1c-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0c1c-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="e0c1c-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e0c1c-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="e0c1c-163">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e0c1c-163">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
