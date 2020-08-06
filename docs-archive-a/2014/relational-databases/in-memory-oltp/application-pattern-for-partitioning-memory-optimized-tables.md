---
title: Anwendungsmuster zur Partitionierung von speicheroptimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 3f867763-a8e6-413a-b015-20e9672cc4d1
author: rothja
ms.author: jroth
ms.openlocfilehash: d2633cdf1b631a1d9209adf26f4773e27c4c44c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609210"
---
# <a name="application-pattern-for-partitioning-memory-optimized-tables"></a><span data-ttu-id="37efd-102">Anwendungsmuster zur Partitionierung von speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="37efd-102">Application Pattern for Partitioning Memory-Optimized Tables</span></span>
  [!INCLUDE[hek_2](../../includes/hek-2-md.md)] <span data-ttu-id="37efd-103">unterstützt ein Muster, bei dem eine begrenzte Menge aktiver Daten in einer speicheroptimierten Tabelle gespeichert wird, während Daten, auf die seltener zugegriffen wird, auf dem Datenträger verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="37efd-103">supports a pattern where a limited amount of active data is kept in a memory-optimized table, while less-frequently accessed data is processed on disk.</span></span> <span data-ttu-id="37efd-104">In einem typischen Szenario würden Daten auf Grundlage eines `datetime`-Schlüssels gespeichert.</span><span class="sxs-lookup"><span data-stu-id="37efd-104">Typically, this would be a scenario where data is stored based on a `datetime` key.</span></span>  
  
 <span data-ttu-id="37efd-105">Sie können partitionierte Tabellen mit speicheroptimierten Tabellen emulieren, indem Sie eine partitionierte Tabelle und eine speicheroptimierte Tabelle mit einem gemeinsamen Schema verwalten.</span><span class="sxs-lookup"><span data-stu-id="37efd-105">You can emulate partitioned tables with memory-optimized tables by maintaining a partitioned table and a memory-optimized table with a common schema.</span></span> <span data-ttu-id="37efd-106">Aktuelle Daten würden in die speicheroptimierte Tabelle eingefügt und aktualisiert, während Daten, auf die weniger häufig zugegriffen wird, in der herkömmlichen partitionierten Tabelle verwaltet würden.</span><span class="sxs-lookup"><span data-stu-id="37efd-106">Current data would be inserted and updated in the memory-optimized table, while less-frequently accessed data would be maintained in the traditional partitioned table.</span></span>  
  
 <span data-ttu-id="37efd-107">Eine Anwendung, die weiß, dass sich die aktiven Daten in einer speicheroptimierten Tabelle befinden, kann systemintern kompilierte gespeicherte Prozeduren verwenden, um auf die Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="37efd-107">An application that knows that the active data is in a memory-optimized table can use natively compiled stored procedures to access the data.</span></span> <span data-ttu-id="37efd-108">Vorgänge, die auf alle Daten zugreifen müssen oder die nicht wissen, welche Tabelle relevante Daten enthält, verwenden interpretiertes [!INCLUDE[tsql](../../includes/tsql-md.md)] , um die speicheroptimierte Tabelle mit der partitionierten Tabelle zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="37efd-108">Operations that need to access the entire span of data, or which may not know which table holds relevant data, use interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] to join the memory-optimized table with the partitioned table.</span></span>  
  
 <span data-ttu-id="37efd-109">Dieser Partitionswechsel wird folgendermaßen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="37efd-109">This partition switch is described as follows:</span></span>  
  
-   <span data-ttu-id="37efd-110">Fügen Sie Daten aus der In-Memory OLTP-Tabelle in eine Stagingtabelle ein, möglicherweise mit einem Umstellungsdatum.</span><span class="sxs-lookup"><span data-stu-id="37efd-110">Insert data from the In-Memory OLTP table into a staging table, possibly using a cutoff date.</span></span>  
  
-   <span data-ttu-id="37efd-111">Löschen Sie diese Daten aus der speicheroptimierten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="37efd-111">Delete the same data from the memory-optimized table.</span></span>  
  
-   <span data-ttu-id="37efd-112">Übertragen Sie die Stagingtabelle.</span><span class="sxs-lookup"><span data-stu-id="37efd-112">Swap in the staging table.</span></span>  
  
-   <span data-ttu-id="37efd-113">Fügen Sie die aktive Partition hinzu.</span><span class="sxs-lookup"><span data-stu-id="37efd-113">Add the active partition.</span></span>  
  
 <span data-ttu-id="37efd-114">![Partitionswechsel.](../../database-engine/media/hekaton-partitioned-tables.gif "Partitionswechsel.")</span><span class="sxs-lookup"><span data-stu-id="37efd-114">![Partition switch.](../../database-engine/media/hekaton-partitioned-tables.gif "Partition switch.")</span></span>  
<span data-ttu-id="37efd-115">Pflege aktiver Daten</span><span class="sxs-lookup"><span data-stu-id="37efd-115">Active Data Maintenance</span></span>  
  
 <span data-ttu-id="37efd-116">Die Aktionen ab dem Löschen von "ActiveOrders" müssen während eines Wartungsfensters durchgeführt werden, damit Abfragen im Zeitraum zwischen der Datenlöschung und Übertragung in die Stagingtabelle immer auf alle Daten zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="37efd-116">The actions starting with Deleting ActiveOrders need to be done during a maintenance window to avoid queries missing data during the time between deleting data and switching in the staging table.</span></span>  
  
 <span data-ttu-id="37efd-117">Ein Beispiel dazu finden Sie unter [Partitionierung auf Anwendungsebene](application-level-partitioning.md).</span><span class="sxs-lookup"><span data-stu-id="37efd-117">For a related sample, see [Application-Level Partitioning](application-level-partitioning.md).</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="37efd-118">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="37efd-118">Code Sample</span></span>  
 <span data-ttu-id="37efd-119">Im folgenden Beispiel wird gezeigt, wie eine speicheroptimierte Tabelle mit einer partitionierten datenträgerbasierten Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="37efd-119">The following sample shows how to use a memory-optimized table with a partitioned disk-based table.</span></span> <span data-ttu-id="37efd-120">Häufig verwendete Daten werden im Arbeitsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="37efd-120">Frequently-used data is stored in memory.</span></span> <span data-ttu-id="37efd-121">Um die Daten auf dem Datenträger zu speichern, erstellen Sie eine neue Partition, und kopieren Sie die Daten in die partitionierte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="37efd-121">To save the data to disk, create a new partition and copy the data to the partitioned table.</span></span>  
  
 <span data-ttu-id="37efd-122">Im ersten Teil dieses Beispiels werden die Datenbank und die erforderlichen Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="37efd-122">The first part of this sample creates the database and necessary objects.</span></span> <span data-ttu-id="37efd-123">Im zweiten Teil des Beispiels wird gezeigt, wie Daten aus einer speicheroptimierten Tabelle in eine partitionierte Tabelle verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="37efd-123">The second part of the sample shows how to move data from a memory-optimized table into a partitioned table.</span></span>  
  
```sql  
CREATE DATABASE partitionsample;  
GO  
  
-- enable for In-Memory OLTP - change file path as needed  
ALTER DATABASE partitionsample ADD FILEGROUP partitionsample_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE partitionsample ADD FILE( NAME = 'partitionsample_mod' , FILENAME = 'c:\data\partitionsample_mod') TO FILEGROUP partitionsample_mod;  
GO  
  
USE partitionsample;  
GO  
  
-- frequently used portion of the SalesOrders - memory-optimized  
  
CREATE TABLE dbo.SalesOrders_hot (  
   so_id INT IDENTITY PRIMARY KEY NONCLUSTERED,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL INDEX ix_date NONCLUSTERED,  
   so_total MONEY NOT NULL,  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- cold portion of the SalesOrders - partitioned disk-based table  
CREATE PARTITION FUNCTION [ByDatePF](datetime2) AS RANGE RIGHT   
   FOR VALUES();  
GO  
  
CREATE PARTITION SCHEME [ByDateRange]   
   AS PARTITION [ByDatePF]   
   ALL TO ([PRIMARY]);  
GO  
  
CREATE TABLE dbo.SalesOrders_cold (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) ON [ByDateRange](so_date)  
GO  
  
-- table for temporary partitions  
CREATE TABLE dbo.SalesOrders_cold_staging (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date datetime2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold_staging PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc),  
   CONSTRAINT CHK_SalesOrders_cold_staging CHECK (so_date >= '1900-01-01')  
)  
GO  
  
-- aggregate view of the hot and cold data  
CREATE VIEW dbo.SalesOrders  
AS SELECT so_id,  
   cust_id,  
   so_date,  
   so_total,  
   1 AS 'is_hot'  
   FROM dbo.SalesOrders_hot  
   UNION ALL  
   SELECT so_id,  
          cust_id,  
          so_date,  
          so_total,  
          0 AS 'is_hot'  
          FROM dbo.SalesOrders_cold;  
GO  
  
-- move all sales orders up to the split date to cold storage  
CREATE PROCEDURE dbo.usp_SalesOrdersOffloadToCold @splitdate datetime2  
   AS  
   BEGIN  
      BEGIN TRANSACTION;  
      -- create new heap based on the hot data to be moved to cold storage  
      INSERT INTO dbo.SalesOrders_cold_staging WITH( TABLOCKX)  
      SELECT so_id , cust_id , so_date , so_total  
         FROM dbo.SalesOrders_hot WITH ( serializable)  
         WHERE so_date <= @splitdate;  
  
      -- remove moved data  
      DELETE FROM dbo.SalesOrders_hot WITH( SERIALIZABLE)  
         WHERE so_date <= @splitdate;  
  
      -- update partition function, and switch in new partition  
      ALTER PARTITION SCHEME [ByDateRange] NEXT USED [PRIMARY];  
  
      DECLARE @p INT = ( SELECT MAX( partition_number) FROM sys.partitions WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold'));  
      EXEC sp_executesql N'alter table dbo.SalesOrders_cold_staging  
         SWITCH TO dbo.SalesOrders_cold partition @i' , N'@i int' , @i = @p;  
  
      ALTER PARTITION FUNCTION [ByDatePF]()  
      SPLIT RANGE( @splitdate);  
  
      -- modify constraint on staging table to align with new partition  
      ALTER TABLE dbo.SalesOrders_cold_staging DROP CONSTRAINT CHK_SalesOrders_cold_staging;  
  
      DECLARE @s nvarchar( 100) = CONVERT( nvarchar( 100) , @splitdate , 121);  
      DECLARE @sql nvarchar( 1000) = N'alter table dbo.SalesOrders_cold_staging   
         add constraint CHK_SalesOrders_cold_staging check (so_date > ''' + @s + ''')';  
      PRINT @sql;  
      EXEC sp_executesql @sql;  
  
      COMMIT;  
END;  
GO  
  
-- insert sample values in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(1,SYSDATETIME(), 1);   
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the table  
SELECT *  FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE  @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , * FROM sys.dm_db_partition_stats ps  
   WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold');  
  
-- insert more rows in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , partition_number , row_count  FROM sys.dm_db_partition_stats ps  
  WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold') AND index_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="37efd-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37efd-124">See Also</span></span>  
 [<span data-ttu-id="37efd-125">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="37efd-125">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
