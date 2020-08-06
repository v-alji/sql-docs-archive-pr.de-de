---
title: Verwenden von Tabellenwertparameter (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- DECLARE
- CREATE TYPE
helpviewer_keywords:
- table-valued parameters
- table-valued parameters, about table-valued parameters
- parameters [SQL Server], table-valued
- TVP See table-valued parameters
ms.assetid: 5e95a382-1e01-4c74-81f5-055612c2ad99
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa7013fddc6b2ce12ad9ad0f9fcb511d93915e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617861"
---
# <a name="use-table-valued-parameters-database-engine"></a><span data-ttu-id="1ec84-102">Verwenden von Tabellenwertparameter (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1ec84-102">Use Table-Valued Parameters (Database Engine)</span></span>
  <span data-ttu-id="1ec84-103">Tabellenwertparameter werden mit benutzerdefinierten Tabellentypen deklariert.</span><span class="sxs-lookup"><span data-stu-id="1ec84-103">Table-valued parameters are declared by using user-defined table types.</span></span> <span data-ttu-id="1ec84-104">Mit Tabellenwertparametern können Sie mehrere Datenzeilen an eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung oder an eine Routine übergeben, z. B. eine gespeicherte Prozedur oder eine Funktion, ohne eine temporäre Tabelle oder viele Parameter erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1ec84-104">You can use table-valued parameters to send multiple rows of data to a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a routine, such as a stored procedure or function, without creating a temporary table or many parameters.</span></span>  
  
 <span data-ttu-id="1ec84-105">Tabellenwertparameter entsprechen Parameterarrays in OLE DB und ODBC, bieten jedoch eine größere Flexibilität und eine engere Integration mit [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ec84-105">Table-valued parameters are like parameter arrays in OLE DB and ODBC, but offer more flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1ec84-106">Ein weiterer Vorteil von Tabellenwertparametern besteht darin, dass sie in setbasierten Vorgängen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1ec84-106">Table-valued parameters also have the benefit of being able to participate in set-based operations.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="1ec84-107">übergibt Tabellenwertparameter mittels Verweise an Routinen, sodass keine Kopie der Eingabedaten erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="1ec84-107">passes table-valued parameters to routines by reference to avoid making a copy of the input data.</span></span> <span data-ttu-id="1ec84-108">Sie können [!INCLUDE[tsql](../../includes/tsql-md.md)] -Routinen mit Tabellenwertparametern erstellen und ausführen und diese über [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code, verwaltete und Native Clients in jeder beliebigen verwalteten Sprache aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1ec84-108">You can create and execute [!INCLUDE[tsql](../../includes/tsql-md.md)] routines with table-valued parameters, and call them from [!INCLUDE[tsql](../../includes/tsql-md.md)] code, managed and native clients in any managed language.</span></span>  
  
 <span data-ttu-id="1ec84-109">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="1ec84-109">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="1ec84-110">Vorteile</span><span class="sxs-lookup"><span data-stu-id="1ec84-110">Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="1ec84-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1ec84-111">Restrictions</span></span>](#Restrictions)  
  
 [<span data-ttu-id="1ec84-112">Tabellenwertparameter und BULK INSERT-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="1ec84-112">Table-Valued Parameters vs. BULK INSERT Operations</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="1ec84-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ec84-113">Example</span></span>](#Example)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="1ec84-114">Vorteile</span><span class="sxs-lookup"><span data-stu-id="1ec84-114">Benefits</span></span>  
 <span data-ttu-id="1ec84-115">Der Bereich eines Tabellenwertparameters entspricht wie auch bei anderen Parametern der gespeicherten Prozedur, der Funktion oder dem dynamischen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Text.</span><span class="sxs-lookup"><span data-stu-id="1ec84-115">A table-valued parameter is scoped to the stored procedure, function, or dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] text, exactly like other parameters.</span></span> <span data-ttu-id="1ec84-116">Ebenso entspricht der Bereich einer Tabellentypvariablen dem Bereich einer beliebigen lokalen Variablen, die mit einer DECLARE-Anweisung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ec84-116">Similarly, a variable of table type has scope like any other local variable that is created by using a DECLARE statement.</span></span> <span data-ttu-id="1ec84-117">Sie können Tabellenwertvariablen in dynamischen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen deklarieren und diese Variablen dann als Tabellenwertparameter an gespeicherte Prozeduren und Funktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ec84-117">You can declare table-valued variables within dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and pass these variables as table-valued parameters to stored procedures and functions.</span></span>  
  
 <span data-ttu-id="1ec84-118">Tabellenwertparameter bieten mehr Flexibilität und in einigen Fällen auch eine bessere Systemleistung als temporäre Tabellen oder andere Methoden zum Übergeben von Parameterlisten.</span><span class="sxs-lookup"><span data-stu-id="1ec84-118">Table-valued parameters offer more flexibility and in some cases better performance than temporary tables or other ways to pass a list of parameters.</span></span> <span data-ttu-id="1ec84-119">Tabellenwertparameter bieten die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="1ec84-119">Table-valued parameters offer the following benefits:</span></span>  
  
-   <span data-ttu-id="1ec84-120">Erfordern keine Sperren für die erste Auffüllung mit Daten von einem Client</span><span class="sxs-lookup"><span data-stu-id="1ec84-120">Do not acquire locks for the initial population of data from a client.</span></span>  
  
-   <span data-ttu-id="1ec84-121">Stellen ein einfaches Programmiermodell bereit</span><span class="sxs-lookup"><span data-stu-id="1ec84-121">Provide a simple programming model.</span></span>  
  
-   <span data-ttu-id="1ec84-122">Ermöglichen die Einbindung komplexer Geschäftslogik in eine einzelne Routine</span><span class="sxs-lookup"><span data-stu-id="1ec84-122">Enable you to include complex business logic in a single routine.</span></span>  
  
-   <span data-ttu-id="1ec84-123">Weniger Roundtrips zum Server</span><span class="sxs-lookup"><span data-stu-id="1ec84-123">Reduce round trips to the server.</span></span>  
  
-   <span data-ttu-id="1ec84-124">Unterstützen Tabellenstrukturen mit unterschiedlicher Kardinalität</span><span class="sxs-lookup"><span data-stu-id="1ec84-124">Can have a table structure of different cardinality.</span></span>  
  
-   <span data-ttu-id="1ec84-125">Weisen eine starke Typbindung auf</span><span class="sxs-lookup"><span data-stu-id="1ec84-125">Are strongly typed.</span></span>  
  
-   <span data-ttu-id="1ec84-126">Ermöglichen die Angabe von Sortierreihenfolge und eindeutigen Schlüsseln über den Client</span><span class="sxs-lookup"><span data-stu-id="1ec84-126">Enable the client to specify sort order and unique keys.</span></span>  
  
-   <span data-ttu-id="1ec84-127">Werden bei der Verwendung in einer gespeicherten Prozedur wie eine temporäre Tabelle zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="1ec84-127">Are cached like a temp table when used in a stored procedure.</span></span> <span data-ttu-id="1ec84-128">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]werden Tabellenwertparameter auch für parametrisierte Abfragen zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="1ec84-128">Starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], table-valued parameters are also cached for parameterized queries.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1ec84-129">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1ec84-129">Restrictions</span></span>  
 <span data-ttu-id="1ec84-130">Für Tabellenwertparameter gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="1ec84-130">Table-valued parameters have the following restrictions:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1ec84-131">Spaltenstatistiken für Tabellenwertparameter werden nicht verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1ec84-131">does not maintain statistics on columns of table-valued parameters.</span></span>  
  
-   <span data-ttu-id="1ec84-132">Tabellenwertparameter müssen als READONLY-Eingabeparameter an [!INCLUDE[tsql](../../includes/tsql-md.md)] -Routinen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ec84-132">Table-valued parameters must be passed as input READONLY parameters to [!INCLUDE[tsql](../../includes/tsql-md.md)] routines.</span></span> <span data-ttu-id="1ec84-133">Für Tabellenwertparameter im Hauptteil einer Routine können keine DML-Vorgänge wie UPDATE, DELETE oder INSERT durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1ec84-133">You cannot perform DML operations such as UPDATE, DELETE, or INSERT on a table-valued parameter in the body of a routine.</span></span>  
  
-   <span data-ttu-id="1ec84-134">Tabellenwertparameter können nicht als Ziel einer SELECT INTO-Anweisung oder einer INSERT EXEC-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ec84-134">You cannot use a table-valued parameter as target of a SELECT INTO or INSERT EXEC statement.</span></span> <span data-ttu-id="1ec84-135">Tabellenwertparameter können in der FROM-Klausel von SELECT INTO oder in der Zeichenfolge oder gespeicherten Prozedur von INSERT EXEC enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="1ec84-135">A table-valued parameter can be in the FROM clause of SELECT INTO or in the INSERT EXEC string or stored procedure.</span></span>  
  
##  <a name="table-valued-parameters-vs-bulk-insert-operations"></a><a name="BulkInsert"></a><span data-ttu-id="1ec84-136">Tabellenwert Parameter im Vergleich zu BULK INSERT Vorgängen</span><span class="sxs-lookup"><span data-stu-id="1ec84-136">Table-Valued Parameters vs. BULK INSERT Operations</span></span>  
 <span data-ttu-id="1ec84-137">Die Verwendung von Tabellenwertparametern ist mit anderen Methoden zur Verwendung setbasierter Variablen vergleichbar. Sehr große Datasets können mit Tabellenwertparametern jedoch häufig schneller verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1ec84-137">Using table-valued parameters is comparable to other ways of using set-based variables; however, using table-valued parameters frequently can be faster for large data sets.</span></span> <span data-ttu-id="1ec84-138">Im Vergleich zu Massenvorgängen, bei denen die Startkosten höher sind, eignen sich Tabellenwertparameter optimal zum Einfügen von weniger als 1000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="1ec84-138">Compared to bulk operations that have a greater startup cost than table-valued parameters, table-valued parameters perform well for inserting less than 1000 rows.</span></span>  
  
 <span data-ttu-id="1ec84-139">Wiederverwendete Tabellenparameter nutzen den Zwischenspeicher für temporäre Tabellen.</span><span class="sxs-lookup"><span data-stu-id="1ec84-139">Table-valued parameters that are reused benefit from temporary table caching.</span></span> <span data-ttu-id="1ec84-140">Diese Zwischenspeicherung ermöglicht eine bessere Skalierbarkeit als vergleichbare BULK INSERT-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="1ec84-140">This table caching enables better scalability than equivalent BULK INSERT operations.</span></span> <span data-ttu-id="1ec84-141">Bei kleineren Vorgängen zum Einfügen von Zeilen können Sie u. U. eine bessere Leistung erzielen, wenn Sie Parameterlisten oder Batch-Anweisungen statt BULK INSERT-Vorgänge oder Tabellenwertparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ec84-141">By using small row-insert operations a small performance benefit might be gained by using parameter lists or batched statements instead of BULK INSERT operations or table-valued parameters.</span></span> <span data-ttu-id="1ec84-142">Die Programmierung dieser Methoden ist allerdings komplexer, und die Leistung nimmt mit steigender Zeilenanzahl schnell ab.</span><span class="sxs-lookup"><span data-stu-id="1ec84-142">However, these methods are less convenient to program, and performance decreases quickly as rows increase.</span></span>  
  
 <span data-ttu-id="1ec84-143">Tabellenwertparameter eignen sich mindestens so gut wie vergleichbare Parameterarray-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="1ec84-143">Table-valued parameters perform equally well or better than an equivalent parameter array implementation.</span></span>  
  
##  <a name="example"></a><a name="Example"></a> <span data-ttu-id="1ec84-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ec84-144">Example</span></span>  
 <span data-ttu-id="1ec84-145">Im folgenden Beispiel wird [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet. Es zeigt, wie Sie einen Tabellenwertparameter erstellen, eine Variable deklarieren, die darauf verweist, Daten in die Parameterliste einfügen und die Werte dann an eine gespeicherte Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ec84-145">The following example uses [!INCLUDE[tsql](../../includes/tsql-md.md)] and shows you how to create a table-valued parameter type, declare a variable to reference it, fill the parameter list, and then pass the values to a stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
/* Create a table type. */  
CREATE TYPE LocationTableType AS TABLE   
( LocationName VARCHAR(50)  
, CostRate INT );  
GO  
  
/* Create a procedure to receive data for the table-valued parameter. */  
CREATE PROCEDURE dbo. usp_InsertProductionLocation  
    @TVP LocationTableType READONLY  
    AS   
    SET NOCOUNT ON  
    INSERT INTO AdventureWorks2012.Production.Location  
           (Name  
           ,CostRate  
           ,Availability  
           ,ModifiedDate)  
        SELECT *, 0, GETDATE()  
        FROM  @TVP;  
        GO  
  
/* Declare a variable that references the type. */  
DECLARE @LocationTVP AS LocationTableType;  
  
/* Add data to the table variable. */  
INSERT INTO @LocationTVP (LocationName, CostRate)  
    SELECT Name, 0.00  
    FROM AdventureWorks2012.Person.StateProvince;  
  
/* Pass the table variable data to a stored procedure. */  
EXEC usp_InsertProductionLocation @LocationTVP;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ec84-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ec84-146">See Also</span></span>  
 <span data-ttu-id="1ec84-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ec84-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span></span>  
 <span data-ttu-id="1ec84-148">[DEKLARIEREN SIE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ec84-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="1ec84-149">[sys. types &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ec84-149">[sys.types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span></span>  
 <span data-ttu-id="1ec84-150">[sys. Parameters &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ec84-150">[sys.parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span></span>  
 <span data-ttu-id="1ec84-151">[sys. parameter_type_usages &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ec84-151">[sys.parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span></span>  
 <span data-ttu-id="1ec84-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ec84-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="1ec84-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1ec84-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
