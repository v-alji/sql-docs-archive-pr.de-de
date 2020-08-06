---
title: Speicher optimierte Tabellen Variablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: bd102e95-53e2-4da6-9b8b-0e4f02d286d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: bec720c53c257240ee92274a6391ebc3f17faa25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618879"
---
# <a name="memory-optimized-table-variables"></a><span data-ttu-id="c78cd-102">Speicheroptimierte Tabellenvariablen</span><span class="sxs-lookup"><span data-stu-id="c78cd-102">Memory-Optimized Table Variables</span></span>
  <span data-ttu-id="c78cd-103">Zusätzlich zu speicheroptimierten Tabellen (für den effizienten Datenzugriff) und nativ kompilierten gespeicherten Prozeduren (für effiziente Abfrageverarbeitung und Ausführung von Geschäftslogik) wird mit [!INCLUDE[hek_2](../includes/hek-2-md.md)] eine dritte Objektart eingeführt: speicheroptimierte Tabellentypen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-103">In addition to memory-optimized tables (for efficient data access) and natively compiled stored procedures (for efficient query processing and business logic execution) [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduces a third kind of object: the memory-optimized table type.</span></span> <span data-ttu-id="c78cd-104">Eine Tabellenvariable, die mithilfe eines speicheroptimierten Tabellentyps erstellt wird, ist eine speicheroptimierte Tabellenvariable.</span><span class="sxs-lookup"><span data-stu-id="c78cd-104">A table variable created using a memory-optimized table type is a memory-optimized table variable.</span></span>  
  
 <span data-ttu-id="c78cd-105">Speicheroptimierte Tabellenvariablen bieten im Vergleich zu datenträgerbasierten Tabellenvariablen die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="c78cd-105">Memory-optimized table variables offer the following advantages when compared to disk-based table variables:</span></span>  
  
-   <span data-ttu-id="c78cd-106">Die Variablen werden nur im Arbeitsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c78cd-106">The variables are only stored in memory.</span></span> <span data-ttu-id="c78cd-107">Die Datenzugriffe sind effizienter, da für speicheroptimierte Tabellentypen derselbe speicheroptimierte Algorithmus und dieselben Datenstrukturen verwendet werden wie für speicheroptimierte Tabellen, insbesondere wenn die Variablen in systemintern kompilierten gespeicherten Prozeduren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c78cd-107">Data access is more efficient because memory-optimized table type use the same memory-optimized algorithm and data structures used for memory-optimized tables, especially when the variables are used in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="c78cd-108">Bei speicheroptimierten Tabellenvariablen findet keine tempdb-Nutzung statt.</span><span class="sxs-lookup"><span data-stu-id="c78cd-108">With memory-optimized table variables, there is no tempdb utilization.</span></span> <span data-ttu-id="c78cd-109">Tabellenvariablen werden nicht in tempdb gespeichert und verwenden keine Ressourcen in tempdb.</span><span class="sxs-lookup"><span data-stu-id="c78cd-109">Table variables are not stored in tempdb and do not use any resources in tempdb.</span></span>  
  
 <span data-ttu-id="c78cd-110">Typische Verwendungsszenarien für speicheroptimierte Tabellenvariablen sind:</span><span class="sxs-lookup"><span data-stu-id="c78cd-110">The typical usage scenarios for memory-optimized table variables are:</span></span>  
  
-   <span data-ttu-id="c78cd-111">Speichern von Zwischenergebnissen und Erstellen von einzelnen Resultsets, die auf mehreren Abfragen basieren, in systemintern kompilierten gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="c78cd-111">Storing intermediate results and creating single result sets based on multiple queries in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="c78cd-112">Übergeben von Tabellenwertparametern an systemintern kompilierte gespeicherte Prozeduren und an interpretierte gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="c78cd-112">Passing table-valued parameters into natively compiled stored procedures and interpreted stored procedures.</span></span>  
  
-   <span data-ttu-id="c78cd-113">Ersetzen datenträgerbasierter Tabellenvariablen und in einigen Fällen von lokalen #temp-Tabellen einer gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="c78cd-113">Replacing disk-based table variables, and in some cases #temp tables that are local to a stored procedure.</span></span> <span data-ttu-id="c78cd-114">Dies ist besonders dann nützlich, wenn im System viele tempdb-Konflikte auftreten.</span><span class="sxs-lookup"><span data-stu-id="c78cd-114">This is particularly useful if there is a lot of tempdb contention in the system.</span></span>  
  
-   <span data-ttu-id="c78cd-115">Tabellenvariablen können zum Simulieren von Cursorn in systemintern kompilierten gespeicherten Prozeduren verwendet werden, um Einschränkungen der Oberfläche in systemintern kompilierten gespeicherten Prozeduren zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-115">Table variables can be used to simulate cursors in natively compiled stored procedures, which can help you work around surface area limitations in natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="c78cd-116">Wie bei speicheroptimierten Tabellen erstellt [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] eine DLL für jeden speicheroptimierten Tabellentyp.</span><span class="sxs-lookup"><span data-stu-id="c78cd-116">Like memory-optimized tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] generates a DLL for each memory-optimized table type.</span></span> <span data-ttu-id="c78cd-117">(Die Kompilierung wird aufgerufen, wenn der Speicher optimierte Tabellentyp erstellt wird, und nicht, wenn er zum Erstellen von Speicher optimierten Tabellen Variablen verwendet wird.) Diese DLL beinhaltet die Funktionen für den Zugriff auf Indizes und das Abrufen von Daten aus den Tabellen Variablen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-117">(Compilation is invoked when the memory-optimized table type is created and not when used to create memory-optimized table variables.) This DLL includes the functions for accessing indexes and retrieving data from the table variables.</span></span> <span data-ttu-id="c78cd-118">Wenn eine speicheroptimierte Tabellenvariable basierend auf dem Tabellentyp deklariert wird, wird in der Benutzersitzung eine Instanz der Tabelle und der Indexstrukturen entsprechend dem Tabellentyp erstellt.</span><span class="sxs-lookup"><span data-stu-id="c78cd-118">When a memory-optimized table variable is declared based on the table type, an instance of the table and index structures corresponding to the table type is created in the user session.</span></span> <span data-ttu-id="c78cd-119">Die Tabellenvariable kann anschließend auf dieselbe Weise wie datenträgerbasierte Tabellenvariablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c78cd-119">The table variable can then be used in the same way as disk-based table variables.</span></span> <span data-ttu-id="c78cd-120">Sie können in der Tabellenvariablen Zeilen einfügen, aktualisieren und löschen, und Sie können die Variablen in [!INCLUDE[tsql](../includes/tsql-md.md)] -Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c78cd-120">You can insert, update, and delete rows in the table variable, and you can use the variables in [!INCLUDE[tsql](../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="c78cd-121">Sie können die Variablen auch als Tabellenwertparameter (TVPs) an systemintern kompilierte und interpretierte gespeicherte Prozeduren übergeben.</span><span class="sxs-lookup"><span data-stu-id="c78cd-121">You can also pass the variables into natively compiled and interpreted stored procedures, as table-valued parameters (TVP).</span></span>  
  
 <span data-ttu-id="c78cd-122">Das folgende Beispiel zeigt einen Speicher optimierten Tabellentyp aus dem AdventureWorks-basierten in-Memory-OLTP-Beispiel ([SQL Server 2014 in-Memory OLTP-Beispiel](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span><span class="sxs-lookup"><span data-stu-id="c78cd-122">The following sample shows a memory-optimized table type from the AdventureWorks-based In-Memory OLTP sample ([SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span></span>  
  
```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem
   AS TABLE
(
   OrderQty         smallint   NOT NULL,
   ProductID        int        NOT NULL,

   SpecialOfferID   int        NOT NULL
      INDEX  IX_SpecialOfferID  NONCLUSTERED,

   LocalID          int        NOT NULL,

   INDEX IX_ProductID HASH (ProductID)
      WITH ( BUCKET_COUNT = 8 )
)
WITH ( MEMORY_OPTIMIZED = ON );
```  
  
 <span data-ttu-id="c78cd-123">Das Beispiel zeigt, dass die Syntax von speicheroptimierten Tabellentypen der von datenträgerbasierten Tabellentypen ähnelt, mit folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="c78cd-123">The sample shows that the syntax of memory-optimized table types is similar to disk-based table types, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="c78cd-124">`MEMORY_OPTIMIZED=ON` gibt an, dass der Tabellentyp speicheroptimiert ist.</span><span class="sxs-lookup"><span data-stu-id="c78cd-124">`MEMORY_OPTIMIZED=ON` indicates that the table type is memory-optimized.</span></span>  
  
-   <span data-ttu-id="c78cd-125">Der Typ muss mindestens einen Index aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-125">The type must have at least one index.</span></span> <span data-ttu-id="c78cd-126">Wie bei speicheroptimierten Tabellen können Sie nicht gruppierte und Hashindizes verwenden.</span><span class="sxs-lookup"><span data-stu-id="c78cd-126">As with memory-optimized tables, you can use hash and nonclustered indexes.</span></span>  
  
     <span data-ttu-id="c78cd-127">Für einen Hashindex sollte die Bucketanzahl etwa einmal bis zweimal so groß sein wie die Anzahl der erwarteten eindeutigen Indexschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c78cd-127">For a hash index, the bucket count should be about one to two times the number of expected unique index keys.</span></span> <span data-ttu-id="c78cd-128">Weitere Informationen finden Sie unter [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c78cd-128">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="c78cd-129">Der Datentypbeschränkungen und die Einschränkungen für speicheroptimierte Tabellen gelten auch für speicheroptimierte Tabellentypen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-129">The data type and constraint restrictions on memory-optimized tables also apply to memory-optimized table types.</span></span> <span data-ttu-id="c78cd-130">Beispielsweise werden Standardeinschränkungen in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] unterstützt, Check-Einschränkungen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="c78cd-130">For example, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] default constraints are supported, but check constraints are not.</span></span>  
  
 <span data-ttu-id="c78cd-131">Speicheroptimierte Tabellenvariablen verhalten sich in folgenden Fällen wie speicheroptimierte Tabellen:</span><span class="sxs-lookup"><span data-stu-id="c78cd-131">Like memory-optimized tables, memory-optimized table variables,</span></span>  
  
-   <span data-ttu-id="c78cd-132">Sie unterstützen keine parallelen Pläne.</span><span class="sxs-lookup"><span data-stu-id="c78cd-132">Do not support parallel plans.</span></span>  
  
-   <span data-ttu-id="c78cd-133">Sie müssen in den Arbeitsspeicher passen und nutzen keine Datenträgerressourcen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-133">Must fit in memory and do not use disk resources.</span></span>  
  
 <span data-ttu-id="c78cd-134">Datenträgerbasierte Tabellenvariablen werden in tempdb gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c78cd-134">Disk-based table variables exist in tempdb.</span></span> <span data-ttu-id="c78cd-135">Speicheroptimierte Tabellenvariablen werden in der Benutzerdatenbank gespeichert. (Sie belegen aber keinen Speicherplatz und werden nicht wiederhergestellt.)</span><span class="sxs-lookup"><span data-stu-id="c78cd-135">Memory-optimized table variables exist in the user database (but they do not consume storage and are not recovered).</span></span>  
  
 <span data-ttu-id="c78cd-136">Eine speicheroptimierte Tabellenvariable kann nicht mithilfe von Inlinesyntax erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c78cd-136">You cannot create a memory-optimized table variable using in-line syntax.</span></span> <span data-ttu-id="c78cd-137">Im Gegensatz zu datenträgerbasierten Tabellenvariablen müssen Sie zuerst einen Typ erstellen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-137">Unlike disk-based table variables, you must create a type first.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="c78cd-138">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="c78cd-138">Table-Valued Parameters</span></span>  
 <span data-ttu-id="c78cd-139">Im folgenden Beispielskript wird die Deklaration einer Tabellenvariablen als speicheroptimierter Tabellentyp `Sales.SalesOrderDetailType_inmem`, das Einfügen von drei Zeilen in die Variable und das Übergeben der Variablen als TVP an `Sales.usp_InsertSalesOrder_inmem` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c78cd-139">The following sample script shows the declaration of a table variable as the memory-optimized table type `Sales.SalesOrderDetailType_inmem`, the insert of three rows into the variable, and passing the variable as a TVP into `Sales.usp_InsertSalesOrder_inmem`.</span></span>  
  
```sql  
DECLARE @od Sales.SalesOrderDetailType_inmem,  
  @SalesOrderID uniqueidentifier,  
  @DueDate datetime2 = SYSDATETIME()  
  
INSERT @od (LocalID, ProductID, OrderQty, SpecialOfferID) VALUES  
  (1, 888, 2, 1),  
  (2, 450, 13, 1),  
  (3, 841, 1, 1)  
  
EXEC Sales.usp_InsertSalesOrder_inmem  
  @SalesOrderID = @SalesOrderID,  
  @DueDate = @DueDate,  
 @OnlineOrderFlag = 1,  
  @SalesOrderDetails = @od  
```  
  
 <span data-ttu-id="c78cd-140">Speicheroptimierte Tabellentypen können als Typ für Tabellenwertparameter (TVPs) von gespeicherten Prozeduren verwendet werden. Clients können genauso darauf verweisen wie auf datenträgerbasierte Tabellentypen und TVPs.</span><span class="sxs-lookup"><span data-stu-id="c78cd-140">Memory-optimized table types can be used as the type for stored procedure table-valued parameters (TVPs) and can be referenced by clients exactly the same as disk-based table types and TVPs.</span></span> <span data-ttu-id="c78cd-141">Daher funktioniert der Aufruf gespeicherter Prozeduren mit speicheroptimierten TVPs und systemintern kompilierter gespeicherter Prozeduren genauso wie der Aufruf interpretierter gespeicherter Prozeduren mit datenträgerbasierten TVPs.</span><span class="sxs-lookup"><span data-stu-id="c78cd-141">Therefore, the invocation of stored procedures with memory-optimized TVPs, and natively compiled stored procedures works exactly the same as the invocation of interpreted stored procedures with disk-based TVPs.</span></span>  
  
## <a name="temp-table-replacement"></a><span data-ttu-id="c78cd-142">Ersatz für #temp-Tabellen</span><span class="sxs-lookup"><span data-stu-id="c78cd-142">#temp Table Replacement</span></span>  
 <span data-ttu-id="c78cd-143">Im folgenden Beispiel werden speicheroptimierte Tabellentypen und Tabellenvariablen als Ersatz für lokale #temp-Tabellen einer gespeicherten Prozedur verwendet.</span><span class="sxs-lookup"><span data-stu-id="c78cd-143">The following sample shows memory-optimized table types and table variables as a replacement for #temp tables that are local to a stored procedure.</span></span>  
  
```sql  
-- Using SQL procedure and temp table  
CREATE TABLE #tempTable (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
  
CREATE PROCEDURE sqlProc  
AS  
BEGIN  
  TRUNCATE TABLE #tempTable  
  
  INSERT #tempTable VALUES (1)  
  INSERT #tempTable VALUES (2)  
  INSERT #tempTable VALUES (3)  
  SELECT * FROM #tempTable  
END  
GO  
  
-- Using natively compiled stored procedure and table variable  
CREATE TYPE TT AS TABLE (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
GO  
  
CREATE PROCEDURE NCSPProc  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @tableVariable TT  
  INSERT @tableVariable VALUES (1)  
  INSERT @tableVariable VALUES (2)  
  INSERT @tableVariable VALUES (3)  
  SELECT c FROM @tableVariable  
END  
GO  
```  
  
## <a name="creating-a-single-result-set"></a><span data-ttu-id="c78cd-144">Erstellen eines einzelnen Resultsets</span><span class="sxs-lookup"><span data-stu-id="c78cd-144">Creating a Single Result Set</span></span>  
 <span data-ttu-id="c78cd-145">Im folgenden Beispiel wird gezeigt, wie Zwischenergebnisse gespeichert und einzelne Resultsets basierend auf mehreren Abfragen in systemintern kompilierten gespeicherten Prozeduren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c78cd-145">The following sample shows how to store intermediate results and create single result sets based on multiple queries in natively compiled stored procedures.</span></span> <span data-ttu-id="c78cd-146">Im Beispiel wird die Vereinigung `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2` berechnet.</span><span class="sxs-lookup"><span data-stu-id="c78cd-146">The sample is computing the union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span></span>  
  
```sql  
CREATE DATABASE hk  
GO  
ALTER DATABASE hk ADD FILEGROUP hk_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE hk ADD FILE( NAME = 'hk_mod' , FILENAME = 'c:\data\hk_mod') TO FILEGROUP hk_mod;  
  
USE hk  
GO  
  
CREATE TYPE tab1 AS TABLE (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON)  
  
CREATE TABLE dbo.t1 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
CREATE TABLE dbo.t2 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
  
INSERT INTO dbo.t1 VALUES (1), (2)  
INSERT INTO dbo.t2 VALUES (3), (4)  
GO  
  
CREATE PROCEDURE dbo.p1  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS  
  BEGIN ATOMIC WITH ( TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english' )  
  
    DECLARE @t dbo.tab1  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t1;  
  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t2;  
  
    SELECT c1 FROM @t;  
  END  
GO  
  
EXEC dbo.p1  
GO  
```  
  
## <a name="memory-consumption-for-table-variables"></a><span data-ttu-id="c78cd-147">Arbeitsspeichernutzung für Tabellenvariablen</span><span class="sxs-lookup"><span data-stu-id="c78cd-147">Memory Consumption for Table Variables</span></span>  
 <span data-ttu-id="c78cd-148">Die Arbeitsspeichernutzung für Tabellenvariablen ist mit Ausnahme von nicht gruppierten Indizes mit der Nutzung speicheroptimierter Tabellen vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="c78cd-148">Memory consumption for table variables is similar to memory-optimized tables, with the exception of nonclustered indexes.</span></span> <span data-ttu-id="c78cd-149">Wenn Sie viele Zeilen in speicheroptimierte Tabellenvariablen mit nicht gruppierten Indizes einfügen und die Indexschlüssel groß sind, beanspruchen diese Tabellenvariablen eine unverhältnismäßig große Speichermenge.</span><span class="sxs-lookup"><span data-stu-id="c78cd-149">If you insert a lot of rows into memory-optimized table variables with nonclustered indexes and if the index keys are large, these table variables will use a disproportionate amount of memory.</span></span> <span data-ttu-id="c78cd-150">Nicht gruppierte Indizes für große Tabellenvariablen erfordern proportional mehr Arbeitsspeicher, als ein nicht gruppierter Index für dieselbe Anzahl von Zeilen, die in eine Tabelle eingefügt wurden, benötigen würde (mehr Speicherplatz in Indexseiten).</span><span class="sxs-lookup"><span data-stu-id="c78cd-150">Nonclustered indexes on large table variables require proportionately more memory than a nonclustered index would require for the same number of rows inserted into a table (more memory in the index pages).</span></span>  
  
 <span data-ttu-id="c78cd-151">Arbeitsspeicher für Tabellenvariablen wird aus dem Ressourcenpool der für die Datenbank zuständigen Ressourcenkontrolle entnommen.</span><span class="sxs-lookup"><span data-stu-id="c78cd-151">Memory for table variables comes from the database's Resource Governor resource pool.</span></span>  
  
 <span data-ttu-id="c78cd-152">Im Gegensatz zu speicheroptimierten Tabellen wird der von Tabellenvariablen genutzte Arbeitsspeicher (einschließlich gelöschter Zeilen) freigegeben, wenn die Tabellenvariable den Gültigkeitsbereich verlässt.</span><span class="sxs-lookup"><span data-stu-id="c78cd-152">Unlike memory-optimized tables, the memory consumed (including deleted rows) by table variables is freed when the table variable goes out of scope.</span></span>  
  
 <span data-ttu-id="c78cd-153">Arbeitsspeicher wird als Teil des einzelnen PGPOOL-Arbeitsspeicherconsumers der Datenbank behandelt.</span><span class="sxs-lookup"><span data-stu-id="c78cd-153">Memory is accounted for as part of the single PGPOOL memory consumer of the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78cd-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c78cd-154">See Also</span></span>  
 [<span data-ttu-id="c78cd-155">Transact-SQL-Unterstützung für OLTP im Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="c78cd-155">Transact-SQL Support for In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/transact-sql-support-for-in-memory-oltp.md)  
  
  
