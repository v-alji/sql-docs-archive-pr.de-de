---
title: Unterstützte Konstrukte in System intern kompilierten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 05515013-28b5-4ccf-9a54-ae861448945b
author: rothja
ms.author: jroth
ms.openlocfilehash: 65e6e794c5858a68c4b2a9b298513911b487cf52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622108"
---
# <a name="supported-constructs-in-natively-compiled-stored-procedures"></a><span data-ttu-id="f3dde-102">Unterstützte Konstrukte in systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-102">Supported Constructs in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="f3dde-103">Dieses Thema enthält eine Liste der unterstützten Funktionen für System intern kompilierte gespeicherte Prozeduren ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span><span class="sxs-lookup"><span data-stu-id="f3dde-103">This topic contains a list of supported features for natively compiled stored procedures ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span></span>  
  
-   [<span data-ttu-id="f3dde-104">Programmierbarkeit in systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-104">Programmability in Natively Compiled Stored Procedures</span></span>](#pncsp)  
  
-   [<span data-ttu-id="f3dde-105">Unterstützte Operatoren</span><span class="sxs-lookup"><span data-stu-id="f3dde-105">Supported Operators</span></span>](#so)  
  
-   [<span data-ttu-id="f3dde-106">Integrierte Funktionen in systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-106">Built-in Functions in Natively Compiled Stored Procedures</span></span>](#bfncsp)  
  
-   [<span data-ttu-id="f3dde-107">Abfrageoberfläche in systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-107">Query Surface Area in Natively Compiled Stored Procedures</span></span>](#qsancsp)  
  
-   [<span data-ttu-id="f3dde-108">Überwachung</span><span class="sxs-lookup"><span data-stu-id="f3dde-108">Auditing</span></span>](#auditing)  
  
-   [<span data-ttu-id="f3dde-109">Tabelle, Abfrage und Joinhinweise</span><span class="sxs-lookup"><span data-stu-id="f3dde-109">Table, Query, and Join Hints</span></span>](#tqh)  
  
-   [<span data-ttu-id="f3dde-110">Einschränkungen bei der Sortierung</span><span class="sxs-lookup"><span data-stu-id="f3dde-110">Limitations on Sorting</span></span>](#los)  
  
 <span data-ttu-id="f3dde-111">Informationen zu Datentypen, die in systemintern kompilierten gespeicherten Prozeduren unterstützt werden, finden Sie unter [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="f3dde-111">For information on data types supported in natively compiled stored procedures, see [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="f3dde-112">Vollständige Informationen zu nicht unterstützten Konstrukten sowie Informationen zu Umgehungslösungen zu einigen der nicht unterstützten Funktionen in systemintern kompilierten gespeicherten Prozeduren finden Sie unter [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f3dde-112">For complete information about unsupported constructs, and for information about how to work around some of the unsupported features in natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span> <span data-ttu-id="f3dde-113">Weitere Informationen zu nicht unterstützten Funktionen finden Sie unter [Von In-Memory-OLTP nicht unterstützte Transact-SQL-Konstrukte](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="f3dde-113">For more information about unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
##  <a name="programmability-in-natively-compiled-stored-procedures"></a><a name="pncsp"></a><span data-ttu-id="f3dde-114">Programmierbarkeit in System intern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-114">Programmability in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="f3dde-115">Folgende werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f3dde-115">The following are supported:</span></span>  
  
-   <span data-ttu-id="f3dde-116">BEGIN ATOMIC (auf der äußeren Ebene der gespeicherten Prozedur), LANGUAGE, ISOLATION LEVEL, DATEFORMAT und DATEFIRST</span><span class="sxs-lookup"><span data-stu-id="f3dde-116">BEGIN ATOMIC (at the outer level of the stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT, and DATEFIRST.</span></span>  
  
-   <span data-ttu-id="f3dde-117">Deklarieren von Variablen als NULL oder NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f3dde-117">Declaring variables as NULL or NOT NULL.</span></span> <span data-ttu-id="f3dde-118">Wenn eine Variable als NOT NULL deklariert wird, muss die Deklaration einen Initialisierer haben.</span><span class="sxs-lookup"><span data-stu-id="f3dde-118">If a variable is declared as NOT NULL, the declaration must have an initializer.</span></span> <span data-ttu-id="f3dde-119">Wenn eine Variable nicht als NOT NULL deklariert wird, ist ein Initialisierer optional.</span><span class="sxs-lookup"><span data-stu-id="f3dde-119">If a variable is not declared as NOT NULL, an initializer is optional.</span></span>  
  
-   <span data-ttu-id="f3dde-120">IF und WHILE</span><span class="sxs-lookup"><span data-stu-id="f3dde-120">IF and WHILE</span></span>  
  
-   <span data-ttu-id="f3dde-121">INSERT/UPDATE/DELETE</span><span class="sxs-lookup"><span data-stu-id="f3dde-121">INSERT/UPDATE/DELETE</span></span>  
  
     <span data-ttu-id="f3dde-122">Unterabfragen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-122">Subqueries are not supported.</span></span> <span data-ttu-id="f3dde-123">In einer WHERE- oder HAVING-Klausel werden AND und BETWEEN unterstützt; OR, NOT und IN werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-123">In the WHERE or HAVING clause, AND and BETWEEN are supported; OR, NOT, and IN are not supported.</span></span>  
  
-   <span data-ttu-id="f3dde-124">Speicheroptimierte Tabellentypen und Tabellenvariablen.</span><span class="sxs-lookup"><span data-stu-id="f3dde-124">Memory-optimized table types and table variables.</span></span>  
  
-   <span data-ttu-id="f3dde-125">RETURN</span><span class="sxs-lookup"><span data-stu-id="f3dde-125">RETURN</span></span>  
  
-   <span data-ttu-id="f3dde-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="f3dde-126">SELECT</span></span>  
  
-   <span data-ttu-id="f3dde-127">SET</span><span class="sxs-lookup"><span data-stu-id="f3dde-127">SET</span></span>  
  
-   <span data-ttu-id="f3dde-128">TRY/CATCH/THROW</span><span class="sxs-lookup"><span data-stu-id="f3dde-128">TRY/CATCH/THROW</span></span>  
  
     <span data-ttu-id="f3dde-129">Um die Leistung zu verbessern, können Sie einen einzelnen TRY/CATCH-Block für eine gesamte systemintern kompilierte gespeicherte Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3dde-129">To optimize performance, use a single TRY/CATCH block for an entire natively compiled stored procedure.</span></span>  
  
##  <a name="supported-operators"></a><a name="so"></a> <span data-ttu-id="f3dde-130">Unterstützte Operatoren</span><span class="sxs-lookup"><span data-stu-id="f3dde-130">Supported Operators</span></span>  
 <span data-ttu-id="f3dde-131">Die folgenden Operatoren werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-131">The following operators are supported.</span></span>  
  
-   <span data-ttu-id="f3dde-132">[Vergleichs Operatoren &#40;Transact-SQL-&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (z. b. >, \<, > = und <=) werden in Bedingungen (While) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-132">[Comparison Operators &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (for example, >, \<, >=, and <=) are supported in conditionals (IF, WHILE).</span></span>  
  
-   <span data-ttu-id="f3dde-133">Unäre Operatoren (+, -)</span><span class="sxs-lookup"><span data-stu-id="f3dde-133">Unary operators (+, -).</span></span>  
  
-   <span data-ttu-id="f3dde-134">Binäre Operatoren (\*, /, +, -, % (Modulo)).</span><span class="sxs-lookup"><span data-stu-id="f3dde-134">Binary operators (\*, /, +, -, % (modulo)).</span></span>  
  
     <span data-ttu-id="f3dde-135">Der Plusoperator (+) wird in Zahlen und Zeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-135">The plus operator (+) is supported on both numbers and strings.</span></span>  
  
-   <span data-ttu-id="f3dde-136">Logische Operatoren (AND, OR, NOT).</span><span class="sxs-lookup"><span data-stu-id="f3dde-136">Logical operators (AND, OR, NOT).</span></span> <span data-ttu-id="f3dde-137">OR und NOT werden in IF- und WHILE-Anweisungen, aber nicht in WHERE- oder HAVING-Klauseln unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-137">OR and NOT are supported in IF and WHILE statements but not in WHERE or HAVING clauses.</span></span>  
  
-   <span data-ttu-id="f3dde-138">Bitweise Operatoren ~, &, |, und ^</span><span class="sxs-lookup"><span data-stu-id="f3dde-138">Bitwise operators ~, &, |, and ^</span></span>  
  
##  <a name="built-in-functions-in-natively-compiled-stored-procedures"></a><a name="bfncsp"></a><span data-ttu-id="f3dde-139">Integrierte Funktionen in nativ kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-139">Built-in Functions in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="f3dde-140">Die folgenden Funktionen werden in Standardeinschränkungen in speicheroptimierten Tabellen und in systemintern kompilierten gespeicherte Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-140">The following functions are supported in default constraints on memory-optimized tables and in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="f3dde-141">Mathematische Funktionen: ARCCOS, ARCSIN, ARCTAN, ATN2, COS, COT, GRAD, EXP, LOG, LOG10, PI, POTENZ, BOGENMASS, ZUFALLSZAHL, SIN, WURZEL, QUADRAT und TAN</span><span class="sxs-lookup"><span data-stu-id="f3dde-141">Math Functions: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE, and TAN</span></span>  
  
-   <span data-ttu-id="f3dde-142">Datumsfunktionen: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME und YEAR.</span><span class="sxs-lookup"><span data-stu-id="f3dde-142">Date Functions: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME, and YEAR.</span></span>  
  
-   <span data-ttu-id="f3dde-143">Zeichenfolgenfunktionen: LEN, LTRIM, RTRIM und SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="f3dde-143">String Functions: LEN, LTRIM, RTRIM, and SUBSTRING</span></span>  
  
-   <span data-ttu-id="f3dde-144">Identitätsfunktionen: SCOPE_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="f3dde-144">Identity Function: SCOPE_IDENTITY</span></span>  
  
-   <span data-ttu-id="f3dde-145">NULL-Funktionen: ISNULL</span><span class="sxs-lookup"><span data-stu-id="f3dde-145">NULL functions: ISNULL</span></span>  
  
-   <span data-ttu-id="f3dde-146">Uniqueidentifier-Funktionen: NEWID und NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="f3dde-146">Uniqueidentifier functions: NEWID and NEWSEQUENTIALID</span></span>  
  
-   <span data-ttu-id="f3dde-147">Fehlerfunktionen: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY und ERROR_STATE</span><span class="sxs-lookup"><span data-stu-id="f3dde-147">Error Functions: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE</span></span>  
  
-   <span data-ttu-id="f3dde-148">Konvertierungen: CAST und CONVERT.</span><span class="sxs-lookup"><span data-stu-id="f3dde-148">Conversions: CAST and CONVERT.</span></span> <span data-ttu-id="f3dde-149">Konvertierungen zwischen Unicode- und Nicht-Unicode-Zeichenfolgen (n(var)char und (var)char) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-149">Conversions between Unicode and non-Unicode character strings (n(var)char and (var)char) are not supported.</span></span>  
  
-   <span data-ttu-id="f3dde-150">Systemfunktionen: @@rowcount.</span><span class="sxs-lookup"><span data-stu-id="f3dde-150">System Functions: @@rowcount.</span></span> <span data-ttu-id="f3dde-151">Durch Anweisungen in nativ kompilierten gespeicherten Prozeduren wird @@rowcount aktualisiert, und Sie können @@rowcount in einer nativ kompilierten gespeicherten Prozedur verwenden, um die Anzahl der Zeilen zu bestimmen, die von der letzten Anweisung betroffen sind, die innerhalb der nativ kompilierten gespeicherten Prozedur ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f3dde-151">Statements inside natively compiled stored procedures update @@rowcount and you can use @@rowcount in a natively compiled stored procedure to determine the number of rows affected by the last statement executed within that natively compiled stored procedure.</span></span> <span data-ttu-id="f3dde-152">Allerdings wird @@rowcount am Anfang und am Ende der Ausführung einer nativ kompilierten gespeicherten Prozedur auf 0 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-152">However, @@rowcount is reset to 0 at the start and at the end of the execution of a natively compiled stored procedure.</span></span>  
  
##  <a name="query-surface-area-in-natively-compiled-stored-procedures"></a><a name="qsancsp"></a><span data-ttu-id="f3dde-153">Abfrage Oberfläche in System intern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-153">Query Surface Area in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="f3dde-154">Folgende werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f3dde-154">The following are supported:</span></span>  
  
-   <span data-ttu-id="f3dde-155">BETWEEN</span><span class="sxs-lookup"><span data-stu-id="f3dde-155">BETWEEN</span></span>  
  
-   <span data-ttu-id="f3dde-156">Aliase für Spaltennamen (entweder mithilfe von AS oder = Syntax)</span><span class="sxs-lookup"><span data-stu-id="f3dde-156">Column name aliases (using either AS or = syntax).</span></span>  
  
-   <span data-ttu-id="f3dde-157">CROSS JOIN und INNER JOIN werden nur bei SELECT-Abfragen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-157">CROSS JOIN and INNER JOIN, supported only with SELECT queries.</span></span>  
  
-   <span data-ttu-id="f3dde-158">Ausdrücke werden in Auswahllisten und [Where &#40;Transact-SQL-&#41;](/sql/t-sql/queries/where-transact-sql) -Klausel unterstützt, wenn Sie einen unterstützten Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3dde-158">Expressions are supported in SELECT list and [WHERE &#40;Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) clause if they use a supported operator.</span></span> <span data-ttu-id="f3dde-159">Unter [Unterstützte Operatoren](#so) finden Sie eine Liste der zurzeit unterstützten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f3dde-159">See [Supported Operators](#so) for the list of currently-supported operators.</span></span>  
  
-   <span data-ttu-id="f3dde-160">Filterprädikat IS [NOT] NULL</span><span class="sxs-lookup"><span data-stu-id="f3dde-160">Filter predicate IS [NOT] NULL</span></span>  
  
-   <span data-ttu-id="f3dde-161">FROM \<memory optimized table></span><span class="sxs-lookup"><span data-stu-id="f3dde-161">FROM \<memory optimized table></span></span>  
  
-   <span data-ttu-id="f3dde-162">[Group by &#40;Transact-SQL-&#41;](/sql/t-sql/queries/select-group-by-transact-sql) wird zusammen mit den Aggregatfunktionen AVG, count, COUNT_BIG, min, Max und Sum unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-162">[GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) is supported, along with the aggregate functions AVG, COUNT, COUNT_BIG, MIN, MAX, and SUM.</span></span> <span data-ttu-id="f3dde-163">MIN und MAX werden für die Typen nvarchar, char, varchar, varchar, vabinary und binary nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-163">MIN and MAX are not supported for types nvarchar, char, varchar, varchar, varbinary, and binary.</span></span> <span data-ttu-id="f3dde-164">Die [Order By-Klausel &#40;Transact-SQL-&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) wird mit [Group by &#40;Transact-SQL-&#41;](/sql/t-sql/queries/select-group-by-transact-sql) unterstützt, wenn ein Ausdruck in der ORDER BY-Liste wörtlich in der Group by-Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f3dde-164">[ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) is supported with [GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) if an expression in the ORDER BY list appears verbatim in the GROUP BY list.</span></span> <span data-ttu-id="f3dde-165">Beispielsweise wird GROUP BY a + b ORDER BY a + b unterstützt, aber GROUP BY a, b ORDER BY a + b nicht.</span><span class="sxs-lookup"><span data-stu-id="f3dde-165">For example, GROUP BY a + b ORDER BY a + b is supported, but GROUP BY a, b ORDER BY a + b is not.</span></span>  
  
-   <span data-ttu-id="f3dde-166">HAVING unterliegt den gleichen Ausdruckseinschränkungen wie die WHERE-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f3dde-166">HAVING, subject to the same expression limitations as the WHERE clause.</span></span>  
  
-   <span data-ttu-id="f3dde-167">INSERT VALUES (eine Zeile pro Anweisung) und INSERT SELECT</span><span class="sxs-lookup"><span data-stu-id="f3dde-167">INSERT VALUES (one row per statement) and INSERT SELECT</span></span>  
  
-   <span data-ttu-id="f3dde-168">Order by <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3dde-168">ORDER BY <sup>1</sup></span></span>  
  
-   <span data-ttu-id="f3dde-169">Prädikate, die nicht auf eine Spalte verweisen.</span><span class="sxs-lookup"><span data-stu-id="f3dde-169">Predicates not referencing a column.</span></span>  
  
-   <span data-ttu-id="f3dde-170">SELECT, UPDATE und DELETE</span><span class="sxs-lookup"><span data-stu-id="f3dde-170">SELECT, UPDATE, and DELETE</span></span>  
  
-   <span data-ttu-id="f3dde-171">Top <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3dde-171">TOP <sup>1</sup></span></span>  
  
-   <span data-ttu-id="f3dde-172">Variablenzuweisung in der SELECT-Liste</span><span class="sxs-lookup"><span data-stu-id="f3dde-172">Variable assignment in the SELECT list.</span></span>  
  
-   <span data-ttu-id="f3dde-173">WHERE... Immer</span><span class="sxs-lookup"><span data-stu-id="f3dde-173">WHERE ... AND</span></span>  
  
 <span data-ttu-id="f3dde-174"><sup>1</sup> Order by und Top werden in nativ kompilierten gespeicherten Prozeduren mit einigen Einschränkungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f3dde-174"><sup>1</sup> ORDER BY and TOP are supported in natively compiled stored procedures, with some restrictions:</span></span>  
  
-   <span data-ttu-id="f3dde-175">Die `DISTINCT`-Klausel oder `SELECT`-Klausel bietet keine Unterstützung für `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="f3dde-175">There is no support for `DISTINCT` in the `SELECT` or `ORDER BY` clause.</span></span>  
  
-   <span data-ttu-id="f3dde-176">Die `WITH TIES`-Klausel bietet keine Unterstützung für `PERCENT` oder `TOP`.</span><span class="sxs-lookup"><span data-stu-id="f3dde-176">There is no support for `WITH TIES` or `PERCENT` in the `TOP` clause.</span></span>  
  
-   <span data-ttu-id="f3dde-177">`TOP` in Kombination mit `ORDER BY` unterstützt höchstens den Wert 8.192 bei Verwendung einer Konstante in der `TOP`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f3dde-177">`TOP` combined with `ORDER BY` does not support more than 8,192 when using a constant in the `TOP` clause.</span></span> <span data-ttu-id="f3dde-178">Dieser Grenzwert kann herabgesetzt werden, wenn die Abfrage Joins oder Aggregatfunktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="f3dde-178">This limit may be lowered in case the query contains joins or aggregate functions.</span></span> <span data-ttu-id="f3dde-179">(Beispielsweise liegt die Beschränkung bei einem Join mit zwei Tabellen bei 4.096 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="f3dde-179">(For example, with one join (two tables), the limit is 4,096 rows.</span></span> <span data-ttu-id="f3dde-180">Bei zwei Joins mit drei Tabellen lautet der Grenzwert 2.730 Zeilen).</span><span class="sxs-lookup"><span data-stu-id="f3dde-180">With two joins (three tables), the limit is 2,730 rows.)</span></span>  
  
     <span data-ttu-id="f3dde-181">Sie können Ergebnisse erhalten, die größer als 8.192 sind, indem Sie die Anzahl von Zeilen in einer Variablen speichern:</span><span class="sxs-lookup"><span data-stu-id="f3dde-181">You can obtain results greater than 8,192 by storing the number of rows in a variable:</span></span>  
  
    ```sql  
    DECLARE @v INT = 9000  
    SELECT TOP (@v) ... FROM ... ORDER BY ...  
    ```  
  
 <span data-ttu-id="f3dde-182">Eine Konstante in der `TOP`-Klausel führt jedoch im Vergleich zur Verwendung einer Variablen zu einer besseren Leistung.</span><span class="sxs-lookup"><span data-stu-id="f3dde-182">However, a constant in the `TOP` clause results in better performance compared to using a variable.</span></span>  
  
 <span data-ttu-id="f3dde-183">Diese Einschränkungen gelten nicht für den interpretierten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Zugriff auf speicheroptimierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="f3dde-183">These restrictions do not apply to interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] access on memory-optimized tables.</span></span>  
  
##  <a name="auditing"></a><a name="auditing"></a> <span data-ttu-id="f3dde-184">Überwachen</span><span class="sxs-lookup"><span data-stu-id="f3dde-184">Auditing</span></span>  
 <span data-ttu-id="f3dde-185">Überwachung auf Prozedurebene wird für systemintern kompilierte gespeicherte Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-185">Procedure level auditing is supported in natively compiled stored procedures.</span></span> <span data-ttu-id="f3dde-186">Überwachung auf Anweisungsebene wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3dde-186">Statement level auditing is not supported.</span></span>  
  
 <span data-ttu-id="f3dde-187">Weitere Informationen zur Überwachung finden Sie unter [Erstellen einer Serverüberwachung und Datenbanküberwachungsspezifikation](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="f3dde-187">For more information about auditing, see [Create a Server Audit and Database Audit Specification](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span></span>  
  
##  <a name="table-query-and-join-hints"></a><a name="tqh"></a><span data-ttu-id="f3dde-188">Tabellen-, Abfrage-und Joinhinweise</span><span class="sxs-lookup"><span data-stu-id="f3dde-188">Table, Query, and Join Hints</span></span>  
 <span data-ttu-id="f3dde-189">Folgende werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f3dde-189">The following are supported:</span></span>  
  
-   <span data-ttu-id="f3dde-190">INDEX-, FORCESCAN- und FORCESEEK-Hinweise, entweder in der Tabellenhinweissyntax oder in der [OPTION-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f3dde-190">INDEX, FORCESCAN, and FORCESEEK hints, either in table hints syntax or in [OPTION Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) of the query.</span></span>  
  
-   <span data-ttu-id="f3dde-191">FORCE ORDER</span><span class="sxs-lookup"><span data-stu-id="f3dde-191">FORCE ORDER</span></span>  
  
-   <span data-ttu-id="f3dde-192">INNER LOOP JOIN</span><span class="sxs-lookup"><span data-stu-id="f3dde-192">INNER LOOP JOIN</span></span>  
  
-   <span data-ttu-id="f3dde-193">OPTIMIZE FOR</span><span class="sxs-lookup"><span data-stu-id="f3dde-193">OPTIMIZE FOR</span></span>  
  
 <span data-ttu-id="f3dde-194">Weitere Informationen finden Sie unter [Hinweise &#40;Transact-SQL-&#41;](/sql/t-sql/queries/hints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3dde-194">For more information, see [Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span></span>  
  
##  <a name="limitations-on-sorting"></a><a name="los"></a> <span data-ttu-id="f3dde-195">Einschränkungen bei der Sortierung</span><span class="sxs-lookup"><span data-stu-id="f3dde-195">Limitations on Sorting</span></span>  
 <span data-ttu-id="f3dde-196">Sie können mehr als 8.000 Zeilen in einer Abfrage sortieren, die [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) und eine [ORDER BY-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3dde-196">You can sort greater than 8,000 rows in a query that uses [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span> <span data-ttu-id="f3dde-197">Ohne die [ORDER BY-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) kann [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) eine Sortierung von bis zu 8.000 Zeilen durchführen (weniger Zeilen, falls es Verknüpfungen gibt).</span><span class="sxs-lookup"><span data-stu-id="f3dde-197">However, without [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) can sort up to 8,000 rows (fewer rows if there are joins).</span></span>  
  
 <span data-ttu-id="f3dde-198">Wenn die Abfrage jeweils den Operator [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) und eine [ORDER BY-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) verwendet, können Sie bis zu 8192 Zeilen für den TOP-Operator angeben.</span><span class="sxs-lookup"><span data-stu-id="f3dde-198">If your query uses both the [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) operator and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), you can specify up to 8192 rows for the TOP operator.</span></span> <span data-ttu-id="f3dde-199">Wenn Sie mehr als 8192 Zeilen angeben, wird die folgende Fehlermeldung angezeigt: **Nachricht 41398, Ebene 16, Zustand 1, Prozedur *\<procedureName>\* , Zeile *\<lineNumber>\* der TOP-Operator kann maximal 8192 Zeilen zurückgeben; *\<number>* wurde angefordert.\*\*</span><span class="sxs-lookup"><span data-stu-id="f3dde-199">If you specify more than 8192 rows you get the error message: **Msg 41398, Level 16, State 1, Procedure *\<procedureName>*, Line *\<lineNumber>* The TOP operator can return a maximum of 8192 rows; *\<number>* was requested.**</span></span>  
  
 <span data-ttu-id="f3dde-200">Wenn keine TOP-Klausel vorhanden ist, kann eine beliebige Anzahl von Zeilen mit ORDER BY sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="f3dde-200">If you do not have a TOP clause, you can sort any number of rows with ORDER BY.</span></span>  
  
 <span data-ttu-id="f3dde-201">Wenn keine ORDER BY-Klausel verwendet wird, können Sie jeden ganzzahligen Wert mit dem TOP-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3dde-201">If you do not use an ORDER BY clause, you can use any integer value with the TOP operator.</span></span>  
  
 <span data-ttu-id="f3dde-202">Beispiel mit TOP N = 8192: Wird kompiliert</span><span class="sxs-lookup"><span data-stu-id="f3dde-202">Example with TOP N = 8192: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8192 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="f3dde-203">Beispiel mit TOP N > 8192: Kann nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="f3dde-203">Example with TOP N > 8192: Fails to compile.</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8193 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="f3dde-204">Die Einschränkung auf 8192 Zeilen gilt nur für `TOP N` , wobei `N` wie in den Beispielen oben eine Konstante ist.</span><span class="sxs-lookup"><span data-stu-id="f3dde-204">The 8192 row limitation only applies to `TOP N` where `N` is a constant, as in the preceding examples.</span></span>  <span data-ttu-id="f3dde-205">Wenn `N` größer als 8192 sein muss, können Sie den Wert einer Variablen zuweisen und die Variable mit `TOP`verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3dde-205">If you need `N` greater than 8192 you can assign the value to a variable and use that variable with `TOP`.</span></span>  
  
 <span data-ttu-id="f3dde-206">Beispiel mit einer Variablen: Wird kompiliert</span><span class="sxs-lookup"><span data-stu-id="f3dde-206">Example using a variable: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    DECLARE @v int = 8193   
    SELECT TOP (@v) ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="f3dde-207">**Einschränkungen für die zurückgegebenen Zeilen:** Es gibt zwei Fälle, in denen die Anzahl von Zeilen, die vom TOP-Operator zurückgegeben werden kann, verringert wird:</span><span class="sxs-lookup"><span data-stu-id="f3dde-207">**Limitations on rows returned:** There are two cases where that can potentially reduce the number of rows that can be returned by the TOP operator:</span></span>  
  
-   <span data-ttu-id="f3dde-208">Verwenden von JOINs in der Abfrage</span><span class="sxs-lookup"><span data-stu-id="f3dde-208">Using JOINs in the query.</span></span>  <span data-ttu-id="f3dde-209">Die Auswirkungen von JOINs auf die Einschränkung sind vom Abfrageplan abhängig.</span><span class="sxs-lookup"><span data-stu-id="f3dde-209">The influence of JOINs on the limitation depends on the query plan.</span></span>  
  
-   <span data-ttu-id="f3dde-210">Verwenden von Aggregatfunktionen oder Verweisen auf Aggregatfunktionen in der ORDER BY-Klausel</span><span class="sxs-lookup"><span data-stu-id="f3dde-210">Using aggregate functions or references to aggregate functions in the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="f3dde-211">Die Formel zum Berechnen eines im ungünstigsten Fall unterstützten Maximalwerts für N in TOP N lautet wie folgt: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span><span class="sxs-lookup"><span data-stu-id="f3dde-211">The formula to calculate a worst case maximum supported N in TOP N is: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dde-212">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3dde-212">See Also</span></span>  
 <span data-ttu-id="f3dde-213">[Nativ kompilierte gespeicherte Prozeduren](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f3dde-213">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="f3dde-214">Migrationsprobleme bei nativ kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f3dde-214">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
  
