---
title: 'Demo: Leistungsverbesserungen von In-Memory OLTP | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c6def45d-d2d4-4d24-8068-fab4cd94d8cc
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4858e4c35263ab3dd1d9fdcf55a2b136dd8eeaf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617980"
---
# <a name="demonstration-performance-improvement-of-in-memory-oltp"></a><span data-ttu-id="baa08-102">Demo: Leistungsverbesserungen von In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="baa08-102">Demonstration: Performance Improvement of In-Memory OLTP</span></span>
  <span data-ttu-id="baa08-103">Dieses Beispiel zeigt Leistungsverbesserungen bei Verwendung von In-Memory OLTP, indem die Unterschiede bei der Antwortzeit bei Ausführung einer identischen Transact-SQL-Abfrage für speicheroptimierte und herkömmliche datenträgerbasierte Tabellen verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="baa08-103">This example shows performance improvements when using In-Memory OLTP by comparing differences in response times when running an identical Transact-SQL query against memory-optimized and traditional disk-based tables.</span></span> <span data-ttu-id="baa08-104">Darüber hinaus wird eine systemintern kompilierte gespeicherte Prozedur erstellt (basierend auf der gleichen Abfrage) und dann ausgeführt, um zu veranschaulichen, dass die besten Antwortzeiten in der Regel beim Abfragen einer speicheroptimierten Tabelle mit einer systemintern kompilierten gespeicherten Prozedur erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="baa08-104">Additionally, a natively-compiled stored procedure is also created (based on the same query) and then run to demonstrate that you typically get the best response times when querying a memory-optimized table with a natively-compiled stored procedure.</span></span> <span data-ttu-id="baa08-105">Dieses Beispiel zeigt nur einen Aspekt der Leistungsverbesserungen beim Zugriff auf Daten in speicheroptimierten Tabellen; Effizienz beim Datenzugriff bei der Durchführung von Einfügungen.</span><span class="sxs-lookup"><span data-stu-id="baa08-105">This sample only shows one aspect of performance improvements when accessing data in memory-optimized tables; data access efficiency when performing inserts.</span></span> <span data-ttu-id="baa08-106">Dieses Beispiel verwendet nur einen einzelnen Thread und nutzt nicht die Parallelitätsvorteile von In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="baa08-106">This sample is single-threaded and does not take advantage of the concurrency benefits of In-Memory OLTP.</span></span> <span data-ttu-id="baa08-107">Eine Arbeitsauslastung, die Parallelität verwendet, bietet noch größere Leistungsvorteile.</span><span class="sxs-lookup"><span data-stu-id="baa08-107">A workload that uses concurrency will see a greater performance gain.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="baa08-108">Ein weiteres Beispiel zur Veranschaulichung Speicher optimierter Tabellen finden Sie unter [SQL Server 2014 in-Memory-OLTP-Beispiel](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="baa08-108">Another sample demonstrating memory-optimized tables is available at [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="baa08-109">Für dieses Beispiel führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="baa08-109">To complete this sample you will perform the following:</span></span>  
  
1.  <span data-ttu-id="baa08-110">Erstellen Sie eine Datenbank namens **imoltp** , und ändern Sie die Dateidetails, um Sie für die Verwendung von in-Memory OLTP einzurichten.</span><span class="sxs-lookup"><span data-stu-id="baa08-110">Create a database named **imoltp** and alter its file details to set it up for using In-Memory OLTP.</span></span>  
  
2.  <span data-ttu-id="baa08-111">Erstellen Sie die Datenbankobjekte für das Beispiel: drei Tabellen und eine systemintern kompilierte gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="baa08-111">Create the database objects for our sample: three tables and a natively-compiled stored procedure.</span></span>  
  
3.  <span data-ttu-id="baa08-112">Führen Sie die verschiedenen Abfragen aus, und zeigen Sie die Antwortzeiten für jede Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="baa08-112">Run the different queries and display the response times for each query.</span></span>  
  
 <span data-ttu-id="baa08-113">Um die **imoltp** -Datenbank für unser Beispiel einzurichten, erstellen Sie zunächst einen leeren Ordner: **c:\ imoltp_data**, und führen Sie dann den folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="baa08-113">To setup the **imoltp** database for our example, first create an empty folder: **c:\imoltp_data**, and then run the following code:</span></span>  
  
```sql  
USE master  
GO  
  
-- Create a new database.  
CREATE DATABASE imoltp  
GO  
  
-- Prepare the database for In-Memory OLTP by  
-- adding a memory-optimized filegroup to the database.  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_file_group  
    CONTAINS MEMORY_OPTIMIZED_DATA;  
  
-- Add a file (to hold the memory-optimized data) to the new filegroup.  
ALTER DATABASE imoltp ADD FILE (name='imoltp_file', filename='c:\imoltp_data\imoltp_file')  
    TO FILEGROUP imoltp_file_group;  
GO  
  
```  
  
 <span data-ttu-id="baa08-114">Führen Sie als Nächstes den folgenden Code aus, um die datenträgerbasierte Tabelle, zwei (2) speicheroptimierte Tabellen und die systemintern kompilierte gespeicherte Prozedur zu erstellen, die zur Veranschaulichung der verschiedenen Datenzugriffsmethoden verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="baa08-114">Next, run the following code to create the disk-based table, two (2) memory-optimized tables, and the natively-compiled stored procedure that will be used to demonstrate the different data access methods:</span></span>  
  
```sql  
USE imoltp  
GO  
  
-- If the tables or stored procedure already exist, drop them to start clean.  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'DiskBasedTable')  
   DROP TABLE [dbo].[DiskBasedTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'InMemTable')  
   DROP TABLE [dbo].[InMemTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'InMemTable2')  
   DROP TABLE [dbo].[InMemTable2]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'usp_InsertData')  
   DROP PROCEDURE [dbo].[usp_InsertData]  
GO  
  
-- Create a traditional disk-based table.  
CREATE TABLE [dbo].[DiskBasedTable] (  
  c1 INT NOT NULL PRIMARY KEY,  
  c2 NCHAR(48) NOT NULL  
)  
GO  
  
-- Create a memory-optimized table.  
CREATE TABLE [dbo].[InMemTable] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a 2nd memory-optimized table.  
CREATE TABLE [dbo].[InMemTable2] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a natively-compiled stored procedure.  
CREATE PROCEDURE [dbo].[usp_InsertData]   
  @rowcount INT,  
  @c NCHAR(48)  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS   
  BEGIN ATOMIC   
  WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @i INT = 1;  
  WHILE @i <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[inMemTable2](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
END  
GO  
  
```  
  
 <span data-ttu-id="baa08-115">Das Setup ist abgeschlossen, und Sie können nun die Abfragen ausführen, die die Antwortzeiten anzeigen, anhand derer die Leistung der verschiedenen Datenzugriffsmethoden verglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="baa08-115">The setup is complete and we are ready to execute the queries that will display the response times comparing the performance between the data access methods.</span></span>  
  
 <span data-ttu-id="baa08-116">Führen Sie zum Abschließen des Beispiels den folgenden Code mehrmals aus.</span><span class="sxs-lookup"><span data-stu-id="baa08-116">To complete the example run the following code multiple times.</span></span> <span data-ttu-id="baa08-117">Ignorieren Sie die Ergebnisse der ersten Ausführung, da diese durch die anfängliche Speicherbelegung beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="baa08-117">Ignore the results from the first run which is negatively affected by initial memory allocation.</span></span>  
  
```sql  
SET STATISTICS TIME OFF;  
SET NOCOUNT ON;  
  
-- Delete data from all tables to reset the example.  
DELETE FROM [dbo].[DiskBasedTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[inMemTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[InMemTable2]   
    WHERE [c1]>0  
GO  
  
-- Declare parameters for the test queries.  
DECLARE @i INT = 1;  
DECLARE @rowcount INT = 100000;  
DECLARE @c NCHAR(48) = N'12345678901234567890123456789012345678';  
DECLARE @timems INT;  
DECLARE @starttime datetime2 = sysdatetime();  
  
-- Disk-based table queried with interpreted Transact-SQL.  
BEGIN TRAN  
  WHILE @I <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[DiskBasedTable](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (disk-based table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with interpreted Transact-SQL.  
SET @i = 1;  
SET @starttime = sysdatetime();  
  
BEGIN TRAN  
  WHILE @i <= @rowcount  
    BEGIN  
      INSERT INTO [dbo].[InMemTable](c1,c2) VALUES (@i, @c);  
      SET @i += 1;  
    END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with a natively-compiled stored procedure.  
SET @starttime = sysdatetime();  
  
EXEC usp_InsertData @rowcount, @c;  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with natively-compiled stored procedure).';  
  
```  
  
 <span data-ttu-id="baa08-118">Die erwarteten Ergebnisse geben tatsächliche Antwortzeiten an, die zeigen, dass die Verwendung speicheroptimierter Tabellen und systemintern kompilierter gespeicherter Prozeduren in der Regel konsistent schnellere Antwortzeiten bietet als die Ausführung der gleichen Arbeitsauslastungen für herkömmliche datenträgerbasierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="baa08-118">The expected results provide actual response times showing how using memory-optimized tables and natively-compiled stored procedures typically provides consistently faster response times than the same workloads running against traditional disk-based tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa08-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baa08-119">See Also</span></span>  
 <span data-ttu-id="baa08-120">[Erweiterungen von AdventureWorks zur Veranschaulichung von in-Memory OLTP](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="baa08-120">[Extensions to AdventureWorks to Demonstrate In-Memory OLTP](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="baa08-121">[In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="baa08-121">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="baa08-122">[Speicher optimierte Tabellen](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="baa08-122">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="baa08-123">[Nativ kompilierte gespeicherte Prozeduren](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="baa08-123">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="baa08-124">[Anforderungen für die Verwendung von speicheroptimierten Tabellen](requirements-for-using-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="baa08-124">[Requirements for Using Memory-Optimized Tables](requirements-for-using-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="baa08-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa08-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="baa08-126">[ALTER DATABASE-Optionen Datei und Dateigruppe &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="baa08-126">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 [<span data-ttu-id="baa08-127">Erstellen von Prozeduren und Speicher optimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="baa08-127">CREATE PROCEDURE and Memory-Optimized Tables</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
