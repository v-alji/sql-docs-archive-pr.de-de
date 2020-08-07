---
title: MSSQLSERVER_2020 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2020 (Database Engine error)
ms.assetid: 4a8bf90f-a083-4c53-84f0-d23c711c8081
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5939267c37e90e7b8456dc01a4af79545e775656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620923"
---
# <a name="mssqlserver_2020"></a><span data-ttu-id="7788c-102">MSSQLSERVER_2020</span><span class="sxs-lookup"><span data-stu-id="7788c-102">MSSQLSERVER_2020</span></span>
    
## <a name="details"></a><span data-ttu-id="7788c-103">Details</span><span class="sxs-lookup"><span data-stu-id="7788c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7788c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7788c-104">Product Name</span></span>|<span data-ttu-id="7788c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7788c-105">SQL Server</span></span>|  
|<span data-ttu-id="7788c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7788c-106">Event ID</span></span>|<span data-ttu-id="7788c-107">2020</span><span class="sxs-lookup"><span data-stu-id="7788c-107">2020</span></span>|  
|<span data-ttu-id="7788c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7788c-108">Event Source</span></span>|<span data-ttu-id="7788c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7788c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7788c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7788c-110">Component</span></span>|<span data-ttu-id="7788c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7788c-111">SQLEngine</span></span>|  
|<span data-ttu-id="7788c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7788c-112">Symbolic Name</span></span>||  
|<span data-ttu-id="7788c-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7788c-113">Message Text</span></span>|<span data-ttu-id="7788c-114">Die für die Entität "% \* ls" gemeldeten Abhängigkeiten beinhalten keine Verweise auf Spalten.</span><span class="sxs-lookup"><span data-stu-id="7788c-114">The dependencies reported for entity "%.\*ls" do not include references to columns.</span></span> <span data-ttu-id="7788c-115">Dies hängt entweder damit zusammen, dass die Entität auf ein Objekt verweist, das nicht vorhanden ist, oder mit einem Fehler in einer oder mehreren Anweisungen in der Entität.</span><span class="sxs-lookup"><span data-stu-id="7788c-115">This is either because the entity references an object that does not exist or because of an error in one or more statements in the entity.</span></span>  <span data-ttu-id="7788c-116">Bevor Sie die Abfrage erneut ausführen, stellen Sie sicher, dass die Entität keine Fehler enthält und dass alle Objekte, auf die die Entität verweist, vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7788c-116">Before rerunning the query, ensure that there are no errors in the entity and that all objects referenced by the entity exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7788c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7788c-117">Explanation</span></span>  
 <span data-ttu-id="7788c-118">Die Systemfunktion **sys.dm_sql_referenced_entities** meldet jede Abhängigkeit auf Spaltenebene für schemagebundene Verweise.</span><span class="sxs-lookup"><span data-stu-id="7788c-118">The **sys.dm_sql_referenced_entities** system function will report any column-level dependency for schema-bound references.</span></span> <span data-ttu-id="7788c-119">Die Funktion meldet z. B. alle Abhängigkeiten auf Spaltenebene für eine indizierte Sicht, da für eine indizierte Sicht Schemabindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7788c-119">For example, the function will report all column-level dependencies for an indexed view because an indexed view requires schema binding.</span></span> <span data-ttu-id="7788c-120">Wenn die Entität, auf die verwiesen wird, jedoch nicht schemagebunden ist, werden Spaltenabhängigkeiten nur gemeldet, wenn alle Anweisungen, in denen auf die Spalten verwiesen wird, gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="7788c-120">However, when the referenced entity is not schema-bound, column dependencies are reported only when all statements in which the columns are referenced can be bound.</span></span> <span data-ttu-id="7788c-121">Anweisungen können nur erfolgreich gebunden werden, wenn alle Objekte vorhanden sind, wenn die Anweisungen analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="7788c-121">Statements can be successfully bound only if all objects exist at the time the statements are parsed.</span></span> <span data-ttu-id="7788c-122">Wenn eine in der Entität definierte Anweisung nicht gebunden werden kann, werden Spaltenabhängigkeiten nicht gemeldet, und die Spalte **referenced_minor_id** gibt 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="7788c-122">If any statement defined in the entity fails to bind, column dependencies will not be reported and the **referenced_minor_id** column will return 0.</span></span> <span data-ttu-id="7788c-123">Wenn Spaltenabhängigkeiten nicht aufgelöst werden können, wird Fehler 2020 ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7788c-123">When column dependencies cannot be resolved, error 2020 is raised.</span></span> <span data-ttu-id="7788c-124">Dieser Fehler verhindert nicht, dass die Abfrage Abhängigkeiten auf Objektebene zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7788c-124">This error does not prevent the query from returning object-level dependencies.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7788c-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7788c-125">User Action</span></span>  
 <span data-ttu-id="7788c-126">Korrigieren Sie alle in der Meldung vor Fehler 2020 identifizierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="7788c-126">Correct any errors identified in the message before error 2020.</span></span> <span data-ttu-id="7788c-127">Im folgenden Codebeispiel wird z. B. die Sicht `Production.ApprovedDocuments` für die Spalten `Title`, `ChangeNumber` und `Status` in der Tabelle `Production.Document` definiert.</span><span class="sxs-lookup"><span data-stu-id="7788c-127">For example, in the following code example the view `Production.ApprovedDocuments` is defined on the columns `Title`, `ChangeNumber`, and `Status` in the `Production.Document` table.</span></span> <span data-ttu-id="7788c-128">Die Systemfunktion **sys.dm_sql_referenced_entities** wird für die Objekte und Spalten abgefragt, von denen die `ApprovedDocuments`-Sicht abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="7788c-128">The **sys.dm_sql_referenced_entities** system function is queried for the objects and columns on which the `ApprovedDocuments` view depends.</span></span> <span data-ttu-id="7788c-129">Da die Sicht nicht mit der WITH SCHEMA_BINDING-Klausel erstellt wird, können die Spalten, auf die in der Sicht verwiesen wird, in der Tabelle geändert werden, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7788c-129">Because the view is not created using the WITH SCHEMA_BINDING clause, the columns referenced in the view can be modified in the referenced table.</span></span> <span data-ttu-id="7788c-130">Im Beispiel wird die Spalte `ChangeNumber` in der Tabelle `Production.Document` geändert, indem sie in `TrackingNumber` umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="7788c-130">The example alters the column `ChangeNumber` in the `Production.Document` table by renaming it to `TrackingNumber`.</span></span> <span data-ttu-id="7788c-131">Die Katalogsicht wird erneut für die `ApprovedDocuments`-Sicht abgefragt. Es ist jedoch keine Bindung an alle in der Sicht definierten Spalten möglich.</span><span class="sxs-lookup"><span data-stu-id="7788c-131">The catalog view is queried again for the `ApprovedDocuments` view; however it cannot bind to all the columns defined in the view.</span></span> <span data-ttu-id="7788c-132">Die Fehler 207 und 2020 werden zurückgegeben und geben das Problem an.</span><span class="sxs-lookup"><span data-stu-id="7788c-132">Errors 207 and 2020 are returned identifying the problem.</span></span> <span data-ttu-id="7788c-133">Um das Problem zu beheben, muss die Sicht geändert so werden, dass der neue Name der Spalte angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7788c-133">To resolve the problem, the view must be altered to reflect the new name of the column.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `CREATE VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title, ChangeNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 `EXEC sp_rename 'Production.Document.ChangeNumber', 'TrackingNumber', 'COLUMN';`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 <span data-ttu-id="7788c-134">Die Abfrage gibt die folgenden Fehlermeldungen zurück:</span><span class="sxs-lookup"><span data-stu-id="7788c-134">The query returns the following error messages.</span></span>  
  
 `Msg 207, Level 16, State 1, Procedure ApprovedDocuments, Line 3`  
  
 `Invalid column name 'ChangeNumber'.`  
  
 `Msg 2020, Level 16, State 1, Line 1`  
  
 `The dependencies reported for entity`  
  
 `"Production.ApprovedDocuments" do not include references to`  
  
 `columns. This is either because the entity references an`  
  
 `object that does not exist or because of an error in one or`  
  
 `more statements in the entity. Before rerunning the query,`  
  
 `ensure that there are no errors in the entity and that all`  
  
 `objects referenced by the entity exist.`  
  
 <span data-ttu-id="7788c-135">Im folgenden Beispiel wird der Spaltenname in der Sicht korrigiert.</span><span class="sxs-lookup"><span data-stu-id="7788c-135">The following example corrects the column name in the view.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `ALTER VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title,TrackingNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
## <a name="see-also"></a><span data-ttu-id="7788c-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7788c-136">See Also</span></span>  
 [<span data-ttu-id="7788c-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7788c-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
  
