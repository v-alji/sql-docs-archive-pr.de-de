---
title: Von IntelliSense unterstützte Transact-SQL-Syntax
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL IntelliSense
- IntelliSense [SQL Server], Transact-SQL syntax
ms.assetid: 194e8f4f-fd7e-4f32-a169-f23531128004
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d34fc79dd7817e64b34b61083415477860ce97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717788"
---
# <a name="transact-sql-syntax-supported-by-intellisense"></a><span data-ttu-id="7a196-102">Von IntelliSense unterstützte Transact-SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="7a196-102">Transact-SQL Syntax Supported by IntelliSense</span></span>
  <span data-ttu-id="7a196-103">Dieses Thema beschreibt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen und Syntaxelemente, die von IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-103">This topic describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and syntax elements that are supported by IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="statements-supported-by-intellisense"></a><span data-ttu-id="7a196-104">Von IntelliSense unterstützte Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7a196-104">Statements Supported by IntelliSense</span></span>  
 <span data-ttu-id="7a196-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]unterstützt IntelliSense nur die am häufigsten verwendeten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7a196-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supports only the most commonly used [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7a196-106">Einige allgemeine [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Bedingungen könnten verhindern, dass IntelliSense funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7a196-106">Some general [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor conditions might prevent IntelliSense from functioning.</span></span> <span data-ttu-id="7a196-107">Weitere Informationen finden Sie unter [Problembehandlung von IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="7a196-107">For more information, see [Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a196-108">IntelliSense ist nicht für verschlüsselte Datenbankobjekte verfügbar, z. B. verschlüsselte gespeicherte Prozeduren oder benutzerdefinierte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7a196-108">IntelliSense is not available for encrypted database objects, such as encrypted stored procedures or user-defined functions.</span></span> <span data-ttu-id="7a196-109">Für Parameter von erweiterten gespeicherten Prozeduren und benutzerdefinierten Typen für die CLR-Integration stehen weder Parameterhilfe noch QuickInfo zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7a196-109">Parameter help and Quick Info are not available for the parameters of extended stored procedures and CLR Integration user-defined types.</span></span>  
  
### <a name="select-statement"></a><span data-ttu-id="7a196-110">SELECT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7a196-110">SELECT Statement</span></span>  
 <span data-ttu-id="7a196-111">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor stellt IntelliSense-Unterstützung für die folgenden Syntaxelemente in der SELECT-Anweisung bereit:</span><span class="sxs-lookup"><span data-stu-id="7a196-111">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor provides IntelliSense support for the following syntax elements in the SELECT statement:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a196-112">SELECT</span><span class="sxs-lookup"><span data-stu-id="7a196-112">SELECT</span></span>|<span data-ttu-id="7a196-113">WHERE</span><span class="sxs-lookup"><span data-stu-id="7a196-113">WHERE</span></span>|  
|<span data-ttu-id="7a196-114">FROM</span><span class="sxs-lookup"><span data-stu-id="7a196-114">FROM</span></span>|<span data-ttu-id="7a196-115">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="7a196-115">ORDER BY</span></span>|  
|<span data-ttu-id="7a196-116">HAVING</span><span class="sxs-lookup"><span data-stu-id="7a196-116">HAVING</span></span>|<span data-ttu-id="7a196-117">UNION</span><span class="sxs-lookup"><span data-stu-id="7a196-117">UNION</span></span>|  
|<span data-ttu-id="7a196-118">FOR</span><span class="sxs-lookup"><span data-stu-id="7a196-118">FOR</span></span>|<span data-ttu-id="7a196-119">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="7a196-119">GROUP BY</span></span>|  
|<span data-ttu-id="7a196-120">TOP</span><span class="sxs-lookup"><span data-stu-id="7a196-120">TOP</span></span>|<span data-ttu-id="7a196-121">OPTION (Hinweis)</span><span class="sxs-lookup"><span data-stu-id="7a196-121">OPTION (hint)</span></span>|  
  
### <a name="additional-transact-sql-statements-that-are-supported"></a><span data-ttu-id="7a196-122">Weitere Transact-SQL-Anweisungen, die unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="7a196-122">Additional Transact-SQL Statements That Are Supported</span></span>  
 <span data-ttu-id="7a196-123">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor stellt zudem IntelliSense-Unterstützung für die in der folgenden Tabellen aufgeführten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen bereit.</span><span class="sxs-lookup"><span data-stu-id="7a196-123">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor also provides IntelliSense support for [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are shown in the following table.</span></span>  
  
|<span data-ttu-id="7a196-124">Transact-SQL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7a196-124">Transact-SQL statement</span></span>|<span data-ttu-id="7a196-125">Unterstützte Syntax</span><span class="sxs-lookup"><span data-stu-id="7a196-125">Syntax supported</span></span>|  
|-----------------------------|----------------------|  
|[<span data-ttu-id="7a196-126">INSERT</span><span class="sxs-lookup"><span data-stu-id="7a196-126">INSERT</span></span>](/sql/t-sql/statements/insert-transact-sql)|<span data-ttu-id="7a196-127">Die gesamte Syntax, mit Ausnahme der *execute_statement* -Klausel.</span><span class="sxs-lookup"><span data-stu-id="7a196-127">All syntax, except the *execute_statement* clause.</span></span>|  
|[<span data-ttu-id="7a196-128">UPDATE</span><span class="sxs-lookup"><span data-stu-id="7a196-128">UPDATE</span></span>](/sql/t-sql/queries/update-transact-sql)|<span data-ttu-id="7a196-129">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-129">All syntax.</span></span>|  
|[<span data-ttu-id="7a196-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="7a196-130">DELETE</span></span>](/sql/t-sql/statements/delete-transact-sql)|<span data-ttu-id="7a196-131">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-131">All syntax.</span></span>|  
|[<span data-ttu-id="7a196-132">DECLARE @local_variable</span><span class="sxs-lookup"><span data-stu-id="7a196-132">DECLARE @local_variable</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)|<span data-ttu-id="7a196-133">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-133">All syntax.</span></span>|  
|[<span data-ttu-id="7a196-134">Set@local_variable</span><span class="sxs-lookup"><span data-stu-id="7a196-134">SET @local_variable</span></span>](/sql/t-sql/language-elements/set-local-variable-transact-sql)|<span data-ttu-id="7a196-135">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-135">All syntax.</span></span>|  
|[<span data-ttu-id="7a196-136">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="7a196-136">EXECUTE</span></span>](/sql/t-sql/language-elements/execute-transact-sql)|<span data-ttu-id="7a196-137">Ausführung von benutzerdefinierten gespeicherten Prozeduren, gespeicherten Systemprozeduren, benutzerdefinierten Funktionen und Systemfunktionen.</span><span class="sxs-lookup"><span data-stu-id="7a196-137">Execution of user-defined stored procedures, system stored procedures, user-defined functions, and system functions.</span></span>|  
|[<span data-ttu-id="7a196-138">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="7a196-138">CREATE TABLE</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="7a196-139">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-139">All syntax.</span></span>|  
|[<span data-ttu-id="7a196-140">CREATE VIEW</span><span class="sxs-lookup"><span data-stu-id="7a196-140">CREATE VIEW</span></span>](/sql/t-sql/statements/create-view-transact-sql)|<span data-ttu-id="7a196-141">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-141">All syntax.</span></span>|  
|[<span data-ttu-id="7a196-142">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="7a196-142">CREATE PROCEDURE</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)|<span data-ttu-id="7a196-143">Gesamte Syntax mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="7a196-143">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="7a196-144">Es gibt keine IntelliSense-Unterstützung für die EXTERNAL NAME-Klausel.</span><span class="sxs-lookup"><span data-stu-id="7a196-144">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="7a196-145">In der AS-Klausel unterstützt IntelliSense nur die Anweisungen und die Syntaxelemente, die in diesem Thema aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-145">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="7a196-146">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="7a196-146">ALTER PROCEDURE</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)|<span data-ttu-id="7a196-147">Gesamte Syntax mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="7a196-147">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="7a196-148">Es gibt keine IntelliSense-Unterstützung für die EXTERNAL NAME-Klausel.</span><span class="sxs-lookup"><span data-stu-id="7a196-148">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="7a196-149">In der AS-Klausel unterstützt IntelliSense nur die Anweisungen und die Syntaxelemente, die in diesem Thema aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-149">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="7a196-150">USE</span><span class="sxs-lookup"><span data-stu-id="7a196-150">USE</span></span>](/sql/t-sql/language-elements/use-transact-sql)|<span data-ttu-id="7a196-151">Gesamte Syntax.</span><span class="sxs-lookup"><span data-stu-id="7a196-151">All syntax.</span></span>|  
  
## <a name="intellisense-in-supported-statements"></a><span data-ttu-id="7a196-152">IntelliSense in unterstützten Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7a196-152">IntelliSense in Supported Statements</span></span>  
 <span data-ttu-id="7a196-153">IntelliSense im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor unterstützt die folgenden Syntaxelemente, wenn sie in einer der unterstützten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7a196-153">IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following syntax elements when they are used in one of the supported [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
-   <span data-ttu-id="7a196-154">Alle Jointypen, einschließlich APPLY.</span><span class="sxs-lookup"><span data-stu-id="7a196-154">All join types, including APPLY</span></span>  
  
-   <span data-ttu-id="7a196-155">PIVOT und UNPIVOT.</span><span class="sxs-lookup"><span data-stu-id="7a196-155">PIVOT and UNPIVOT</span></span>  
  
-   <span data-ttu-id="7a196-156">Verweise auf die folgenden Datenbankobjekte:</span><span class="sxs-lookup"><span data-stu-id="7a196-156">References to the following database objects:</span></span>  
  
    -   <span data-ttu-id="7a196-157">Datenbanken und Schemas</span><span class="sxs-lookup"><span data-stu-id="7a196-157">Databases and schemas</span></span>  
  
    -   <span data-ttu-id="7a196-158">Tabellen, Sichten, Tabellenwertfunktionen und Tabellenausdrücke</span><span class="sxs-lookup"><span data-stu-id="7a196-158">Tables, views, table-valued functions, and table expressions</span></span>  
  
    -   <span data-ttu-id="7a196-159">Spalten</span><span class="sxs-lookup"><span data-stu-id="7a196-159">Columns</span></span>  
  
    -   <span data-ttu-id="7a196-160">Prozeduren und Prozedurparameter</span><span class="sxs-lookup"><span data-stu-id="7a196-160">Procedures and procedure parameters</span></span>  
  
    -   <span data-ttu-id="7a196-161">Skalare Funktionen und Skalarausdrücke</span><span class="sxs-lookup"><span data-stu-id="7a196-161">Scalar functions and scalar expressions</span></span>  
  
    -   <span data-ttu-id="7a196-162">Lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="7a196-162">Local variables</span></span>  
  
    -   <span data-ttu-id="7a196-163">Allgemeine Tabellenausdrücke (CTE)</span><span class="sxs-lookup"><span data-stu-id="7a196-163">Common table expressions (CTE)</span></span>  
  
-   <span data-ttu-id="7a196-164">Datenbankobjekte, auf die nur in der CREATE-Anweisung oder der ALTER-Anweisung im Skript oder im Batch verwiesen wird, die aber nicht in der Datenbank vorhanden sind, da das Skript bzw. der Batch noch nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7a196-164">Database objects that are referenced only in CREATE or ALTER statements in the script or batch, but which do not exist in the database because the script or batch has not yet been run.</span></span> <span data-ttu-id="7a196-165">Nachfolgend sind diese Objekte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="7a196-165">These objects are as follows:</span></span>  
  
    -   <span data-ttu-id="7a196-166">Tabellen und Prozeduren, die in einer CREATE TABLE-Anweisung oder CREATE PROCEDURE-Anweisung im Skript oder Batch angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7a196-166">Tables and procedures that have been specified in a CREATE TABLE or CREATE PROCEDURE statement in the script or batch.</span></span>  
  
    -   <span data-ttu-id="7a196-167">Änderungen an Tabellen und Prozeduren, die in einer ALTER TABLE-Anweisung oder ALTER PROCEDURE-Anweisung im Skript oder Batch angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7a196-167">Changes to tables and procedures that have been specified in an ALTER TABLE or ALTER PROCEDURE statement in the script or batch.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a196-168">IntelliSense ist nicht verfügbar für die Spalten einer CREATE VIEW-Anweisung, solange die CREATE VIEW-Anweisung nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7a196-168">IntelliSense is not available for the columns of a CREATE VIEW statement until the CREATE VIEW statement has been executed.</span></span>  
  
 <span data-ttu-id="7a196-169">IntelliSense wird für die zuvor genannten Elemente nicht bereitgestellt, wenn sie in anderen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-169">IntelliSense is not provided for the previously listed elements when they are used in other [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7a196-170">Es ist z. B. IntelliSense-Unterstützung für Spaltennamen verfügbar, die in einer SELECT-Anweisung verwendet werden, nicht jedoch für Spaltennamen, die in der CREATE FUNCTION-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-170">For example, there is IntelliSense support for column names that are used in a SELECT statement, but not for columns that are used in the CREATE FUNCTION statement.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7a196-171">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7a196-171">Examples</span></span>  
 <span data-ttu-id="7a196-172">In einem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript oder -Batch unterstützt IntelliSense im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor nur die Anweisungen und Syntaxelemente, die in diesem Thema aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-172">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports only the statements and syntax that are listed in this topic.</span></span> <span data-ttu-id="7a196-173">Die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Codebeispiele zeigen, welche Anweisungen und Syntaxelemente von IntelliSense unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7a196-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code examples show what statements and syntax elements IntelliSense supports.</span></span> <span data-ttu-id="7a196-174">Beispielsweise ist im folgenden Batch IntelliSense verfügbar für die `SELECT` -Anweisung, wenn diese eigencodiert ist, aber nicht, wenn `SELECT` in einer `CREATE FUNCTION` -Anweisung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7a196-174">For example, in the following batch, IntelliSense is available for the `SELECT` statement when it is coded by itself, but not when the `SELECT` is contained in a `CREATE FUNCTION` statement.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Name  
FROM Production.Product  
WHERE Name LIKE N'Road-250%' and Color = N'Red';  
GO  
CREATE FUNCTION Production.ufn_Red250 ()  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT Name  
    FROM AdventureWorks2012.Production.Product  
    WHERE Name LIKE N'Road-250%'  
      AND Color = N'Red'  
);GO  
```  
  
 <span data-ttu-id="7a196-175">Diese Funktionalität gilt auch für die Sätze von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen in der AS-Klausel einer CREATE PROCEDURE-Anweisung oder ALTER PROCEDURE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7a196-175">This functionality also applies to the sets of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the AS clause of a CREATE PROCEDURE or ALTER PROCEDURE statement.</span></span>  
  
 <span data-ttu-id="7a196-176">In einem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript oder -Batch unterstützt IntelliSense Objekte, die in einer CREATE-Anweisung oder ALTER-Anweisung angegeben sind. Allerdings sind diese Objekte nicht in der Datenbank vorhanden, da die Anweisungen nicht ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="7a196-176">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense supports objects that have been specified in a CREATE or ALTER statement; however, these objects do not exist in the database because the statements have not been executed.</span></span> <span data-ttu-id="7a196-177">Sie können z. B. den folgenden Code im Abfrage-Editor eingeben:</span><span class="sxs-lookup"><span data-stu-id="7a196-177">For example, you might enter the following code in the Query Editor:</span></span>  
  
```  
USE MyTestDB;  
GO  
CREATE TABLE MyTable  
    (PrimaryKeyCol   INT PRIMARY KEY,  
    FirstNameCol      NVARCHAR(50),  
   LastNameCol       NVARCHAR(50));  
GO  
SELECT   
```  
  
 <span data-ttu-id="7a196-178">Wenn Sie `SELECT`eingegeben haben, listet IntelliSense **PrimaryKeyCol**, **FirstNameCol**und **LastNameCol** als mögliche Elemente in der Auswahlliste auf, auch wenn das Skript nicht ausgeführt wurde und `MyTable` noch nicht in `MyTestDB`vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7a196-178">After you type `SELECT`, IntelliSense lists **PrimaryKeyCol**, **FirstNameCol**, and **LastNameCol** as possible elements in the select list, even if the script has not been executed and `MyTable` does not yet exist in `MyTestDB`.</span></span>  
  
  
