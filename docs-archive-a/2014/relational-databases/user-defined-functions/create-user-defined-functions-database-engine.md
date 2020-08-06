---
title: Erstellen von benutzerdefinierten Funktionen (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SCHEMABINDING clause
- schema-bound functions [SQL Server]
- user-defined functions [SQL Server], creating
- CREATE FUNCTION statement
- valid statements [SQL Server]
ms.assetid: f0d5dd10-73fd-4e05-9177-07f56552bdf7
author: rothja
ms.author: jroth
ms.openlocfilehash: 790fa1b969f933890e050311173fcde3f12c37ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621909"
---
# <a name="create-user-defined-functions-database-engine"></a><span data-ttu-id="d510f-102">Erstellen von benutzerdefinierten Funktionen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="d510f-102">Create User-defined Functions (Database Engine)</span></span>
  <span data-ttu-id="d510f-103">In diesem Thema wird beschrieben, wie eine benutzerdefinierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktion mit [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d510f-103">This topic describes how to create a user-defined function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d510f-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d510f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d510f-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d510f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d510f-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d510f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d510f-107">Security</span><span class="sxs-lookup"><span data-stu-id="d510f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d510f-108">**So erstellen Sie eine benutzerdefinierte Funktion:**</span><span class="sxs-lookup"><span data-stu-id="d510f-108">**To create a user-defined function:**</span></span>  
  
     [<span data-ttu-id="d510f-109">Erstellen einer Skalarfunktion</span><span class="sxs-lookup"><span data-stu-id="d510f-109">Create a Scalar Function</span></span>](#Scalar)  
  
     [<span data-ttu-id="d510f-110">Erstellen einer Tabellenwertfunktion</span><span class="sxs-lookup"><span data-stu-id="d510f-110">Create a Table-valued Function</span></span>](#TVF)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d510f-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d510f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d510f-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d510f-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d510f-113">Mit benutzerdefinierten Funktionen können keine Aktionen ausgeführt werden, die den Status einer Datenbank ändern.</span><span class="sxs-lookup"><span data-stu-id="d510f-113">User-defined functions cannot be used to perform actions that modify the database state.</span></span>  
  
-   <span data-ttu-id="d510f-114">Benutzerdefinierte Funktion dürfen keine OUTPUT INTO-Klausel enthalten, deren Ziel eine Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="d510f-114">User-defined functions cannot contain an OUTPUT INTO clause that has a table as its target.</span></span>  
  
-   <span data-ttu-id="d510f-115">Von benutzerdefinierten Funktionen können nicht mehrere Resultsets zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d510f-115">User-defined functions can not return multiple result sets.</span></span> <span data-ttu-id="d510f-116">Falls mehrere Resultsets zurückgegeben werden müssen, verwenden Sie eine gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d510f-116">Use a stored procedure if you need to return multiple result sets.</span></span>  
  
-   <span data-ttu-id="d510f-117">Die Fehlerbehandlung ist in einer benutzerdefinierten Funktion eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="d510f-117">Error handling is restricted in a user-defined function.</span></span> <span data-ttu-id="d510f-118">Eine UDF unterstützt nicht Try... Catch @ERROR oder RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="d510f-118">A UDF does not support TRY...CATCH, @ERROR or RAISERROR.</span></span>  
  
-   <span data-ttu-id="d510f-119">Von benutzerdefinierten Funktionen kann zwar keine gespeicherte Prozedur, aber eine erweiterte gespeicherte Prozedur aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d510f-119">User-defined functions cannot call a stored procedure, but can call an extended stored procedure.</span></span>  
  
-   <span data-ttu-id="d510f-120">Von benutzerdefinierten Funktionen können kein dynamisches SQL bzw. keine temporären Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d510f-120">User-defined functions cannot make use of dynamic SQL or temp tables.</span></span> <span data-ttu-id="d510f-121">Tabellenvariablen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d510f-121">Table variables are allowed.</span></span>  
  
-   <span data-ttu-id="d510f-122">SET-Anweisungen sind in einer benutzerdefinierten Funktionen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="d510f-122">SET statements are not allowed in a user-defined function.</span></span>  
  
-   <span data-ttu-id="d510f-123">Die FOR XML-Klausel ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="d510f-123">The FOR XML clause is not allowed</span></span>  
  
-   <span data-ttu-id="d510f-124">Benutzerdefinierte Funktionen können geschachtelt werden. Dies bedeutet, dass eine benutzerdefinierte Funktion eine andere aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="d510f-124">User-defined functions can be nested; that is, one user-defined function can call another.</span></span> <span data-ttu-id="d510f-125">Die Schachtelungsebene wird um eins erhöht, wenn die aufgerufene Funktion mit der Ausführung beginnt, und wird wieder um eins erniedrigt, wenn die aufgerufene Funktion die Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="d510f-125">The nesting level is incremented when the called function starts execution, and decremented when the called function finishes execution.</span></span> <span data-ttu-id="d510f-126">Benutzerdefinierte Funktionen unterstützen bis zu 32 geschachtelte Ebenen.</span><span class="sxs-lookup"><span data-stu-id="d510f-126">User-defined functions can be nested up to 32 levels.</span></span> <span data-ttu-id="d510f-127">Ein Überschreiten der maximalen Schachtelungsebenen verursacht das Fehlschlagen der gesamten Funktionsaufrufskette.</span><span class="sxs-lookup"><span data-stu-id="d510f-127">Exceeding the maximum levels of nesting causes the whole calling function chain to fail.</span></span> <span data-ttu-id="d510f-128">Alle Verweise auf verwalteten Code von einer benutzerdefinierten Transact-SQL-Funktion aus gelten hinsichtlich des Maximums von 32 Schachtelungsebenen als eine Ebene.</span><span class="sxs-lookup"><span data-stu-id="d510f-128">Any reference to managed code from a Transact-SQL user-defined function counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="d510f-129">Methoden, die aus verwaltetem Code aufgerufen werden, werden nicht mitgezählt.</span><span class="sxs-lookup"><span data-stu-id="d510f-129">Methods invoked from within managed code do not count against this limit.</span></span>  
  
-   <span data-ttu-id="d510f-130">Die folgenden Service Broker-Anweisungen können nicht in die Definition einer benutzerdefinierten Transact-SQL-Funktion eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="d510f-130">The following Service Broker statements cannot be included in the definition of a Transact-SQL user-defined function:</span></span>  
  
    -   <span data-ttu-id="d510f-131">BEGIN DIALOG CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="d510f-131">BEGIN DIALOG CONVERSATION</span></span>  
  
    -   <span data-ttu-id="d510f-132">END CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="d510f-132">END CONVERSATION</span></span>  
  
    -   <span data-ttu-id="d510f-133">GET CONVERSATION GROUP</span><span class="sxs-lookup"><span data-stu-id="d510f-133">GET CONVERSATION GROUP</span></span>  
  
    -   <span data-ttu-id="d510f-134">MOVE CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="d510f-134">MOVE CONVERSATION</span></span>  
  
    -   <span data-ttu-id="d510f-135">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="d510f-135">RECEIVE</span></span>  
  
    -   <span data-ttu-id="d510f-136">SEND</span><span class="sxs-lookup"><span data-stu-id="d510f-136">SEND</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d510f-137">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d510f-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d510f-138">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d510f-138">Permissions</span></span>  
 <span data-ttu-id="d510f-139">Erfordert die CREATE FUNCTION-Berechtigung in der Datenbank und die ALTER-Berechtigung für das Schema, in dem die Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d510f-139">Requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span> <span data-ttu-id="d510f-140">Wenn die Funktion einen benutzerdefinierten Typ angibt, wird die EXECUTE-Berechtigung für den Typ benötigt.</span><span class="sxs-lookup"><span data-stu-id="d510f-140">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="scalar-functions"></a><a name="Scalar"></a><span data-ttu-id="d510f-141">Skalarfunktionen</span><span class="sxs-lookup"><span data-stu-id="d510f-141">Scalar Functions</span></span>  
 <span data-ttu-id="d510f-142">Im folgenden Beispiel wird eine Skalarfunktion mit mehreren Anweisungen in der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="d510f-142">The following example creates a multistatement scalar function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="d510f-143">Die Funktion nimmt einen Eingabewert ( `ProductID`) an und gibt einen einzelnen Datenwert zurück, der die aggregierte Menge des Lagerbestands für das angegebene Produkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="d510f-143">The function takes one input value, a `ProductID`, and returns a single data value, the aggregated quantity of the specified product in inventory.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufnGetInventoryStock', N'FN') IS NOT NULL  
    DROP FUNCTION ufnGetInventoryStock;  
GO  
CREATE FUNCTION dbo.ufnGetInventoryStock(@ProductID int)  
RETURNS int   
AS   
-- Returns the stock level for the product.  
BEGIN  
    DECLARE @ret int;  
    SELECT @ret = SUM(p.Quantity)   
    FROM Production.ProductInventory p   
    WHERE p.ProductID = @ProductID   
        AND p.LocationID = '6';  
     IF (@ret IS NULL)   
        SET @ret = 0;  
    RETURN @ret;  
END;  
GO  
  
```  
  
 <span data-ttu-id="d510f-144">Im folgenden Beispiel wird die `ufnGetInventoryStock` -Funktion verwendet, um den aktuellen Lagerbestand für Produkte mit einer `ProductModelID` zwischen 75 und 80 zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d510f-144">The following example uses the `ufnGetInventoryStock` function to return the current inventory quantity for products that have a `ProductModelID` between 75 and 80.</span></span>  
  
```  
SELECT ProductModelID, Name, dbo.ufnGetInventoryStock(ProductID)AS CurrentSupply  
FROM Production.Product  
WHERE ProductModelID BETWEEN 75 and 80;  
  
```  
  
##  <a name="table-valued-functions"></a><a name="TVF"></a><span data-ttu-id="d510f-145">Tabellenwert Funktionen</span><span class="sxs-lookup"><span data-stu-id="d510f-145">Table-Valued Functions</span></span>  
 <span data-ttu-id="d510f-146">Im folgenden Beispiel wird eine Inline-Tabellenwertfunktion in der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="d510f-146">The following example creates an inline table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="d510f-147">Die Funktion nimmt einen Eingabeparameter (eine Kunden-ID (Geschäfts-ID)) an und gibt die Spalten `ProductID`, `Name`sowie das Aggregat der bisherigen Verkaufseinnahmen dieses Jahres als `YTD Total` für jedes Produkt zurück, das an das Geschäft verkauft wurde.</span><span class="sxs-lookup"><span data-stu-id="d510f-147">The function takes one input parameter, a customer (store) ID, and returns the columns `ProductID`, `Name`, and the aggregate of year-to-date sales as `YTD Total` for each product sold to the store.</span></span>  
  
```  
IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);  
  
```  
  
 <span data-ttu-id="d510f-148">Das folgende Beispiel ruft die Funktion auf und gibt die Kunden-ID 602 an.</span><span class="sxs-lookup"><span data-stu-id="d510f-148">The following example invokes the function and specifies customer ID 602.</span></span>  
  
```  
SELECT * FROM Sales.ufn_SalesByStore (602);  
  
```  
  
 <span data-ttu-id="d510f-149">Im folgenden Beispiel wird eine Tabellenwertfunktion in der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="d510f-149">The following example creates a table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="d510f-150">Die Funktion nimmt einen einzelnen Eingabeparameter ( `EmployeeID` ) an und gibt eine Liste aller Mitarbeiter zurück, die dem angegebenen Mitarbeiter direkt oder indirekt unterstellt sind.</span><span class="sxs-lookup"><span data-stu-id="d510f-150">The function takes a single input parameter, an `EmployeeID` and returns a list of all the employees who report to the specified employee directly or indirectly.</span></span> <span data-ttu-id="d510f-151">Die Funktion wird dann unter Angabe der Mitarbeiternummer 109 aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d510f-151">The function is then invoked specifying employee ID 109.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufn_FindReports', N'TF') IS NOT NULL  
    DROP FUNCTION dbo.ufn_FindReports;  
GO  
CREATE FUNCTION dbo.ufn_FindReports (@InEmpID INTEGER)  
RETURNS @retFindReports TABLE   
(  
    EmployeeID int primary key NOT NULL,  
    FirstName nvarchar(255) NOT NULL,  
    LastName nvarchar(255) NOT NULL,  
    JobTitle nvarchar(50) NOT NULL,  
    RecursionLevel int NOT NULL  
)  
--Returns a result set that lists all the employees who report to the   
--specific employee directly or indirectly.*/  
AS  
BEGIN  
WITH EMP_cte(EmployeeID, OrganizationNode, FirstName, LastName, JobTitle, RecursionLevel) -- CTE name and columns  
    AS (  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, 0 -- Get the initial list of Employees for Manager n  
        FROM HumanResources.Employee e   
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        WHERE e.BusinessEntityID = @InEmpID  
        UNION ALL  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, RecursionLevel + 1 -- Join recursive member to anchor  
        FROM HumanResources.Employee e   
            INNER JOIN EMP_cte  
            ON e.OrganizationNode.GetAncestor(1) = EMP_cte.OrganizationNode  
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        )  
-- copy the required columns to the result of the function   
   INSERT @retFindReports  
   SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
   FROM EMP_cte   
   RETURN  
END;  
GO  
-- Example invocation  
SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
FROM dbo.ufn_FindReports(1);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="d510f-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d510f-152">See Also</span></span>  
 <span data-ttu-id="d510f-153">[Benutzerdefinierte Funktionen](user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="d510f-153">[User-Defined Functions](user-defined-functions.md) </span></span>  
 [<span data-ttu-id="d510f-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d510f-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
