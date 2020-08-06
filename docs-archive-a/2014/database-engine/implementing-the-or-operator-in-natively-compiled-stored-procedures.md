---
title: Implementieren des OR-Operators in System intern kompilierten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2528e74-2b1c-48cb-861b-c4e57b51ac35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ed762e062cbc6831eb46784ef71fc7889850676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718712"
---
# <a name="implementing-the-or-operator-in-natively-compiled-stored-procedures"></a><span data-ttu-id="5d52d-102">Implementieren des OR-Operators in systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5d52d-102">Implementing the OR Operator in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="5d52d-103">OR-Operatoren werden in Abfrageprädikaten systemintern kompilierter gespeicherter Prozeduren nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d52d-103">OR operators are not supported in query predicates in natively compiled stored procedures.</span></span> <span data-ttu-id="5d52d-104">Da NOT-Operatoren in Abfrageprädikaten systemintern kompilierter gespeicherter Prozeduren ebenfalls nicht unterstützt werden, können die Auswirkungen der OR-Operatoren nicht allein durch Verwendung der entsprechenden logischen Operatoren simuliert werden.</span><span class="sxs-lookup"><span data-stu-id="5d52d-104">Because NOT operators are also not supported in query predicates in natively compiled stored procedures, the effects of OR operators cannot be simulated through the use of equivalent logical operators alone.</span></span> <span data-ttu-id="5d52d-105">Die Auswirkungen eines OR-Operators können jedoch anhand von speicheroptimierten Tabellenvariablen simuliert werden.</span><span class="sxs-lookup"><span data-stu-id="5d52d-105">However, the effects of an OR operator may be simulated with memory-optimized table variables.</span></span>  
  
## <a name="or-operator-in-where-clause"></a><span data-ttu-id="5d52d-106">OR-Operator in einer WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="5d52d-106">OR Operator in WHERE Clause</span></span>  
 <span data-ttu-id="5d52d-107">Wenn Sie über einen OR-Operator in einer WHERE-Klausel verfügen, können Sie dessen Verhalten auf die folgende Weise simulieren:</span><span class="sxs-lookup"><span data-stu-id="5d52d-107">If you have an OR operator in a WHERE clause, you can use the following approach to simulate its behavior:</span></span>  
  
1.  <span data-ttu-id="5d52d-108">Erstellen Sie eine speicheroptimierte Tabellenvariable mit dem entsprechenden Schema.</span><span class="sxs-lookup"><span data-stu-id="5d52d-108">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="5d52d-109">Dies erfordert einen vordefinierten speicheroptimierten Tabellentyp.</span><span class="sxs-lookup"><span data-stu-id="5d52d-109">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="5d52d-110">Unterteilen Sie die WHERE-Klausel ab dem OR-Operator der obersten Ebene in zwei Teile. Dabei richten Sie sich nach den vom OR-Operator verknüpften Prädikaten.</span><span class="sxs-lookup"><span data-stu-id="5d52d-110">Starting with the top level OR operator, separate the WHERE clause into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="5d52d-111">Wenn Sie über mehr als einen OR-Operator in einer WHERE-Klausel verfügen, müssen Sie diesen Vorgang möglicherweise mehrere Male wiederholen.</span><span class="sxs-lookup"><span data-stu-id="5d52d-111">If you have more than one OR operator in a WHERE clause, you may need to do this more than once.</span></span> <span data-ttu-id="5d52d-112">Wiederholen Sie diesen Schritt, bis keine OR-Operatoren mehr übrig sind.</span><span class="sxs-lookup"><span data-stu-id="5d52d-112">Repeat this step until no OR operators remain.</span></span> <span data-ttu-id="5d52d-113">Angenommen, Sie verfügen über das folgende Prädikat:</span><span class="sxs-lookup"><span data-stu-id="5d52d-113">For example, if you have the following predicate:</span></span>  
  
    ```  
    pred1 OR (pred2 AND (pred3 OR pred4)) OR (pred5 AND pred6)  
    ```  
  
     <span data-ttu-id="5d52d-114">Nach diesem Schritt sollten Sie über die folgenden Prädikate verfügen:</span><span class="sxs-lookup"><span data-stu-id="5d52d-114">After this step, you should have the following predicates:</span></span>  
  
    ```  
    pred1  
    pred5 AND pred6  
    pred2 AND pred3  
    pred2 AND pred4  
    ```  
  
3.  <span data-ttu-id="5d52d-115">Führen Sie eine Abfrage mit jedem der beiden Teile aus, die in Schritt 2 als Prädikat angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5d52d-115">Execute a query with each of the two parts found in Step 2 as the predicate.</span></span> <span data-ttu-id="5d52d-116">Fügen Sie das Ergebnis für jede Abfrage in die unter Schritt 1 erstellte speicheroptimierte Tabellenvariable ein.</span><span class="sxs-lookup"><span data-stu-id="5d52d-116">Insert the result for each query into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="5d52d-117">Entfernen Sie ggf. Duplikate aus der speicheroptimierten Tabellenvariablen.</span><span class="sxs-lookup"><span data-stu-id="5d52d-117">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="5d52d-118">Verwenden Sie den Inhalt der speicheroptimierten Tabellenvariablen als Ergebnis der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="5d52d-118">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="5d52d-119">Im folgenden Beispiel werden Tabellen aus der AdventureWorks2012-Datenbank verwendet, die für [!INCLUDE[hek_2](../includes/hek-2-md.md)]aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5d52d-119">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="5d52d-120">Um die Dateien für dieses Beispiel herunterzuladen, navigieren Sie zu [AdventureWorks-Datenbanken-2012, 2008R2 und 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="5d52d-120">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="5d52d-121">Um das [!INCLUDE[hek_2](../includes/hek-2-md.md)] -Codebeispiel auf AdventureWorks2012 anzuwenden, rufen Sie [Beispiel zu SQL Server 2014 In-Memory OLTP](https://msftdbprodsamples.codeplex.com/releases/view/114491)auf.</span><span class="sxs-lookup"><span data-stu-id="5d52d-121">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="5d52d-122">Fügen Sie der Datenbank die folgende gespeicherte Prozedur hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d52d-122">Add the following stored procedure to the database.</span></span> <span data-ttu-id="5d52d-123">Diese gespeicherte Prozedur wird konvertiert, sodass sie die systeminterne Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d52d-123">We will convert this stored procedure to use native compilation.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_ondisk  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
AS BEGIN  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  WHERE  s.SalesOrderId = @SalesOrderId  
      OR s.SalesOrderDetailId = @SalesOrderDetailId  
      OR s.CarrierTrackingNumber = @CarrierTrackingNumber  
      OR s.ProductID = @ProductId  
      OR (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
END  
GO  
```  
  
 <span data-ttu-id="5d52d-124">Nach der Konvertierung erhalten Sie folgendes Schema für die Tabelle und die gespeicherte Prozedur:</span><span class="sxs-lookup"><span data-stu-id="5d52d-124">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesOrderDetailType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailTempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  recordcount int not null  
  INDEX ix_fuzzySearchSalesOrderDetailTempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_inmem  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.fuzzySearchSalesOrderDetailType  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderId = @SalesOrderId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderDetailId = @SalesOrderDetailId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.CarrierTrackingNumber COLLATE Latin1_General_BIN2 = @CarrierTrackingNumber COLLATE Latin1_General_BIN2   
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.ProductID = @ProductId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
  
  -- After the above statements, there will be duplicates inside @retValue  
  -- Delete the duplicates from @retValue  
  DECLARE @duplicates Sales.fuzzySearchSalesOrderDetailTempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, recordcount)   
  SELECT SalesOrderId, SalesOrderDetailId, COUNT(*) AS recordCount  
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId  
  
  -- Now we have one row per pair  
  -- clear and rebuild the result set  
  DELETE FROM @retValue  
  
  INSERT INTO @retValue  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates d ON s.SalesOrderId = d.SalesOrderId AND s.SalesOrderDetailId = d.SalesOrderDetailId  
  
  -- After this every pair of (SalesOrderId, SalesOrderDetailId) in @retValue should be unique.  
  SELECT SalesorderId, SalesOrderDetailId, ModifiedDate FROM @retValue  
END  
GO  
```  
  
## <a name="or-operator-in-join-condition"></a><span data-ttu-id="5d52d-125">OR-Operator in einer JOIN-Bedingung</span><span class="sxs-lookup"><span data-stu-id="5d52d-125">OR Operator in JOIN Condition</span></span>  
 <span data-ttu-id="5d52d-126">Wenn Sie über einen OR-Operator in einer JOIN-Bedingung einer SELECT-Anweisung verfügen, können Sie dessen Verhalten auf die folgende Weise simulieren.</span><span class="sxs-lookup"><span data-stu-id="5d52d-126">If you have an OR operator in a JOIN condition of a SELECT statement, you may use the following approach to simulate its behavior.</span></span> <span data-ttu-id="5d52d-127">Wenn Sie über mehr als einen OR-Operator in einer JOIN-Bedingung bzw. über mehrere JOIN-Bedingungen bei OR-Operatoren verfügen, müssen Sie diesen Schritt ggf. mehrere Male ausführen.</span><span class="sxs-lookup"><span data-stu-id="5d52d-127">If you have more than one OR operator in a JOIN condition or you have multiple JOIN condition with OR operators, you may need to do this more than once.</span></span>  
  
 <span data-ttu-id="5d52d-128">Wenn Sie über OUTER JOIN-Bedingungen verfügen, können Sie diese Umgehungslösung mit der Umgehungslösung für OUTER JOIN-Bedingungen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5d52d-128">If you have OUTER JOIN conditions, you may combine this workaround with the workaround for OUTER JOIN conditions.</span></span>  
  
1.  <span data-ttu-id="5d52d-129">Erstellen Sie eine speicheroptimierte Tabellenvariable mit dem entsprechenden Schema.</span><span class="sxs-lookup"><span data-stu-id="5d52d-129">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="5d52d-130">Dies erfordert einen vordefinierten speicheroptimierten Tabellentyp.</span><span class="sxs-lookup"><span data-stu-id="5d52d-130">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="5d52d-131">Unterteilen Sie das Prädikat in der JOIN-Bedingung in zwei Teile. Dabei richten Sie sich nach den durch den OR-Operator verknüpften Prädikaten.</span><span class="sxs-lookup"><span data-stu-id="5d52d-131">Separate the predicate in the JOIN condition into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="5d52d-132">Wenn Sie über mehrere JOIN-Bedingungen verfügen, müssen Sie diesen Schritt u. U. für jede JOIN-Bedingung ausführen und die resultierenden Fragmente dann auf verschiedene Weisen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5d52d-132">If you have multiple JOIN conditions, you may need to do this for each JOIN condition and then create a set of combinations of the resulting fragments.</span></span> <span data-ttu-id="5d52d-133">Wenn Sie beispielsweise über drei JOIN-Bedingungen mit einem OR-Operator pro JOIN-Bedingung verfügen, haben Sie möglicherweise 2x2x2=8 Prädikate.</span><span class="sxs-lookup"><span data-stu-id="5d52d-133">For example, if you have three JOIN conditions with one OR operator in each JOIN condition, you may have 2x2x2=8 predicates.</span></span>  
  
3.  <span data-ttu-id="5d52d-134">Erstellen Sie für jedes unter Schritt 2 erstellte Prädikat eine Abfrage, durch die das Ergebnis in die unter Schritt 1 erstellte speicheroptimierte Tabellenvariable eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5d52d-134">For each predicate produced by Step 2, create a query that will insert its result into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="5d52d-135">Entfernen Sie ggf. Duplikate aus der speicheroptimierten Tabellenvariablen.</span><span class="sxs-lookup"><span data-stu-id="5d52d-135">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="5d52d-136">Verwenden Sie den Inhalt der speicheroptimierten Tabellenvariablen als Ergebnis der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="5d52d-136">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="5d52d-137">Im folgenden Beispiel werden Tabellen aus der AdventureWorks2012-Datenbank verwendet, die für [!INCLUDE[hek_2](../includes/hek-2-md.md)]aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5d52d-137">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="5d52d-138">Um die Dateien für dieses Beispiel herunterzuladen, navigieren Sie zu [AdventureWorks-Datenbanken-2012, 2008R2 und 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="5d52d-138">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="5d52d-139">Um das [!INCLUDE[hek_2](../includes/hek-2-md.md)] -Codebeispiel auf AdventureWorks2012 anzuwenden, rufen Sie [Beispiel zu SQL Server 2014 In-Memory OLTP](https://msftdbprodsamples.codeplex.com/releases/view/114491)auf.</span><span class="sxs-lookup"><span data-stu-id="5d52d-139">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="5d52d-140">Fügen Sie der Datenbank die folgende gespeicherte Prozedur hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d52d-140">Add the following stored procedure to the database.</span></span> <span data-ttu-id="5d52d-141">Diese gespeicherte Prozedur wird konvertiert, sodass sie die systeminterne Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d52d-141">We will convert this stored procedure to use native compilation.</span></span> <span data-ttu-id="5d52d-142">In diesem Beispiel werden INNER JOIN-Bedingungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d52d-142">This sample uses INNER JOIN conditions.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_ondisk  
  @SpecialOfferId int  
AS BEGIN  
  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  JOIN Sales.SpecialOffer_onDisk offer   
    ON s.SpecialOfferID = offer.SpecialOfferID   
    OR s.ProductID IN (SELECT ProductId FROM Sales.SpecialOfferProduct sop WHERE sop.SpecialOfferID = @SpecialOfferId)  
END  
```  
  
 <span data-ttu-id="5d52d-143">Nach der Konvertierung erhalten Sie folgendes Schema für die Tabelle und die gespeicherte Prozedur:</span><span class="sxs-lookup"><span data-stu-id="5d52d-143">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_Type AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesSpecialOffers_Type NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_TempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  recordcount int null  
  INDEX ix_fuzzySearchSalesSpecialOffers_TempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_inmem  
  @SpecialOfferId int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.FuzzySearchSalesSpecialOffers_Type  
  
  -- Find all special offers matching the conditions  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOffer_inmem offer   
    ON s.SpecialOfferID = offer.SpecialOfferID  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOfferProduct_inmem sop   
    ON sop.SpecialOfferId = @SpecialOfferId AND s.ProductID = sop.ProductId  
  
  -- Now we need to remove the duplicates from @matchingSpecialOffers  
  DECLARE @duplicates Sales.fuzzySearchSalesSpecialOffers_TempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, SpecialOfferid, recordcount)  
  SELECT SalesOrderId, SalesOrderDetailId, SpecialOfferId, COUNT(*)   
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId, SpecialOfferId  
  
  -- now there should be no duplicates within @duplicate  
  -- use @duplicate for join.  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates offer   
    ON    s.SalesOrderId = offer.SalesOrderId   
      AND s.SalesOrderDetailId = offer.SalesOrderDetailID   
      AND s.SpecialOfferId = offer.SpecialOfferId  
END  
GO  
```  
  
## <a name="side-effects"></a><span data-ttu-id="5d52d-144">Nebeneffekte</span><span class="sxs-lookup"><span data-stu-id="5d52d-144">Side Effects</span></span>  
 <span data-ttu-id="5d52d-145">Wenn Sie über mehr als einen OR-Operator in der WHERE-Klausel oder JOIN-Bedingung verfügen, kann die Anzahl der Abfragen, die zur Simulation des Verhaltens ausgeführt werden müssen, exponentiell ansteigen.</span><span class="sxs-lookup"><span data-stu-id="5d52d-145">If you have more than one OR operator in the WHERE clause or JOIN condition, the number of queries you need to execute to simulate the behavior may increase exponentially.</span></span> <span data-ttu-id="5d52d-146">Das kann die Abfrageleistung verlangsamen und zu einer höheren Arbeitsspeicherauslastung führen, weil speicheroptimierte Tabellenvariablen verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5d52d-146">This may slow down query performance and may increase memory usage due to the need to use memory-optimized table variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d52d-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d52d-147">See Also</span></span>  
 [<span data-ttu-id="5d52d-148">Migrationsprobleme bei nativ kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5d52d-148">Migration Issues for Natively Compiled Stored Procedures</span></span>](../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)  
  
