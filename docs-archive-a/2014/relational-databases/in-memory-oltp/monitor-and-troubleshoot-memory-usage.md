---
title: Überwachung und Fehlerbehebung für die Arbeitsspeicherauslastung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 7a458b9c-3423-4e24-823d-99573544c877
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5805ed06ad78040dbdf6c8557e5f548ad57f618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725758"
---
# <a name="monitor-and-troubleshoot-memory-usage"></a><span data-ttu-id="b40f8-102">Überwachung und Fehlerbehebung für die Arbeitsspeicherauslastung</span><span class="sxs-lookup"><span data-stu-id="b40f8-102">Monitor and Troubleshoot Memory Usage</span></span>
  [!INCLUDE[hek_1](../../includes/hek-1-md.md)] <span data-ttu-id="b40f8-103">nutzt Arbeitsspeicher auf andere Weise als datenträgerbasierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-103">consumes memory in different patterns than disk-based tables.</span></span> <span data-ttu-id="b40f8-104">Sie können die Größe des von speicheroptimierten Tabellen und Indizes belegten und verwendeten Arbeitsspeichers in der Datenbank mit den DMVs oder Leistungsindikatoren überwachen, die für den Arbeitsspeicher und das Garbage Collection-Subsystem bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b40f8-104">You can monitor the amount of memory allocated and used by memory-optimized tables and indexes in your database using the DMVs or performance counters provided for memory and the garbage collection subsystem.</span></span>  <span data-ttu-id="b40f8-105">Auf diese Weise behalten Sie den Überblick auf System- und Datenbankebene und können Probleme aufgrund einer zu hohen Arbeitsspeicherauslastung vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b40f8-105">This gives you visibility at both the system and database level and lets you prevent problems due to memory exhaustion.</span></span>

 <span data-ttu-id="b40f8-106">In diesem Thema wird das Überwachen der [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] -Speicherauslastung behandelt.</span><span class="sxs-lookup"><span data-stu-id="b40f8-106">This topic covers monitoring your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] memory usage.</span></span>


##  <a name="create-a-sample-database-with-memory-optimized-tables"></a><a name="bkmk_CreateDB"></a> <span data-ttu-id="b40f8-107">Erstellen einer Beispieldatenbank mit speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="b40f8-107">Create a sample database with memory-optimized tables</span></span>
 <span data-ttu-id="b40f8-108">Sie können diesen Abschnitt überspringen, wenn Sie bereits über eine Datenbank mit speicheroptimierten Tabellen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-108">You can skip this section if you already have a database with memory-optimized tables.</span></span>

 <span data-ttu-id="b40f8-109">In den folgenden Schritten wird eine Datenbank mit drei speicheroptimierten Tabellen erstellt, die Sie im weiteren Verlauf dieses Themas verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b40f8-109">The following steps create a database with three memory-optimized tables that you can use in the remainder of this topic.</span></span> <span data-ttu-id="b40f8-110">Im Beispiel wurde die Datenbank einem Ressourcenpool zugeordnet, um zu steuern, wie viel Arbeitsspeicher von speicheroptimierten Tabellen eingenommen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b40f8-110">In the example, we mapped the database to a resource pool so that we can control how much memory can be taken by memory-optimized tables.</span></span>

1.  <span data-ttu-id="b40f8-111">Starten Sie [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b40f8-111">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>

2.  <span data-ttu-id="b40f8-112">Klicken Sie auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b40f8-112">Click **New Query**.</span></span>

3.  <span data-ttu-id="b40f8-113">Fügen Sie den folgenden Code im Fenster für die neue Abfrage ein, und führen Sie die einzelnen Abschnitte aus.</span><span class="sxs-lookup"><span data-stu-id="b40f8-113">Paste this code into the new query window and execute each section.</span></span>

    ```
    -- create a database to be used
    CREATE DATABASE IMOLTP_DB
    GO

    ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_xtp_fg CONTAINS MEMORY_OPTIMIZED_DATA
    ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_xtp' , FILENAME = 'C:\Data\IMOLTP_DB_xtp') TO FILEGROUP IMOLTP_DB_xtp_fg;
    GO

    USE IMOLTP_DB
    GO

    -- create the resoure pool
    CREATE RESOURCE POOL PoolIMOLTP WITH (MAX_MEMORY_PERCENT = 60);
    ALTER RESOURCE GOVERNOR RECONFIGURE;
    GO

    -- bind the database to a resource pool
    EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'PoolIMOLTP'

    -- you can query the binding using the catalog view as described here
    SELECT d.database_id
         , d.name
         , d.resource_pool_id
    FROM sys.databases d
    GO

    -- take database offline/online to finalize the binding to the resource pool
    USE master
    GO

    ALTER DATABASE IMOLTP_DB SET OFFLINE
    GO
    ALTER DATABASE IMOLTP_DB SET ONLINE
    GO

    -- create some tables
    USE IMOLTP_DB
    GO

    -- create table t1
    CREATE TABLE dbo.t1 (
           c1 int NOT NULL CONSTRAINT [pk_t1_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- load t1 150K rows
    DECLARE @i int = 0
    BEGIN TRAN
    WHILE (@i <= 150000)
       BEGIN
          INSERT t1 VALUES (@i, 'a', replicate ('b', 8000))
          SET @i += 1;
       END
    Commit
    GO

    -- Create another table, t2
    CREATE TABLE dbo.t2 (
           c1 int NOT NULL CONSTRAINT [pk_t2_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- Create another table, t3 
    CREATE TABLE dbo.t3 (
           c1 int NOT NULL CONSTRAINT [pk_t3_c1] PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 1000000)
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO
    ```

##  <a name="monitoring-memory-usage"></a><span data-ttu-id="b40f8-114">Überwachen der Arbeitsspeicherverwendung</span><span class="sxs-lookup"><span data-stu-id="b40f8-114">Monitoring Memory Usage</span></span>

###  <a name="using-ssmanstudiofull"></a><span data-ttu-id="b40f8-115">Verwenden von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b40f8-115">Using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>
 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="b40f8-116">Im Lieferumfang sind integrierte Standardberichte enthalten, um den von Tabellen im Arbeitsspeicher beanspruchten Speicherplatz zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-116">ships with built-in standard reports to monitor the memory consumed by in-memory tables.</span></span> <span data-ttu-id="b40f8-117">Sie können auf diese Berichte mithilfe des Objekt-Explorers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-117">You can access these reports using Object Explorer.</span></span> <span data-ttu-id="b40f8-118">Mit dem Objekt-Explorer können Sie auch den Arbeitsspeicher überwachen, der von einzelnen speicheroptimierten Tabellen beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="b40f8-118">You can also use the object explorer to monitor memory consumed by individual memory-optimized tables.</span></span>

#### <a name="consumption-at-the-database-level"></a><span data-ttu-id="b40f8-119">Verbrauch auf Datenbankebene</span><span class="sxs-lookup"><span data-stu-id="b40f8-119">Consumption at the database level</span></span>
 <span data-ttu-id="b40f8-120">Sie können die Arbeitsspeicherauslastung auf Datenbankebene wie folgt überwachen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-120">You can monitor memory use at the database level as follows.</span></span>

1.  <span data-ttu-id="b40f8-121">Starten Sie [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , und stellen eine Verbindung mit einem Server her.</span><span class="sxs-lookup"><span data-stu-id="b40f8-121">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and connect to a server.</span></span>

2.  <span data-ttu-id="b40f8-122">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Datenbank, für die Berichte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-122">In Object Explorer, right-click the database you want reports on.</span></span>

3.  <span data-ttu-id="b40f8-123">Wählen Sie im Kontextmenü **Berichte** -> **Standard Berichte** -> **Speicherauslastung nach speicheroptimierten Objekten**aus.</span><span class="sxs-lookup"><span data-stu-id="b40f8-123">In the context menu select, **Reports** -> **Standard Reports** -> **Memory Usage By Memory Optimized Objects**</span></span>

 <span data-ttu-id="b40f8-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="b40f8-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span></span>

 <span data-ttu-id="b40f8-125">Dieser Bericht zeigt die Arbeitsspeicherauslastung durch die oben erstellte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b40f8-125">This report shows memory consumption by the database we created above.</span></span>

 <span data-ttu-id="b40f8-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="b40f8-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span></span>

###  <a name="using-dmvs"></a><span data-ttu-id="b40f8-127">Verwenden von DMVs</span><span class="sxs-lookup"><span data-stu-id="b40f8-127">Using DMVs</span></span>
 <span data-ttu-id="b40f8-128">Es gibt mehrere DMVs zum Überwachen des durch speicheroptimierte Tabellen, Indizes, Systemobjekte und Laufzeitstrukturen verwendeten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="b40f8-128">There are a number of DMVs available to monitor memory consumed by memory-optimized tables, indexes, system objects, and by run-time structures.</span></span>

#### <a name="memory-consumption-by-memory-optimized-tables-and-indexes"></a><span data-ttu-id="b40f8-129">Arbeitsspeichernutzung durch speicheroptimierte Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="b40f8-129">Memory consumption by memory-optimized tables and indexes</span></span>
 <span data-ttu-id="b40f8-130">Sie können die Arbeitsspeichernutzung für alle Benutzertabellen, Indizes und Systemobjekte ermitteln, indem Sie `sys.dm_db_xtp_table_memory_stats` wie hier dargestellt abfragen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-130">You can find memory consumption for all user tables, indexes, and system objects by querying `sys.dm_db_xtp_table_memory_stats` as shown here.</span></span>

```sql
SELECT object_name(object_id) AS Name
     , *
   FROM sys.dm_db_xtp_table_memory_stats
```

 <span data-ttu-id="b40f8-131">**Beispielausgabe**</span><span class="sxs-lookup"><span data-stu-id="b40f8-131">**Sample Output**</span></span>

```
Name       object_id   memory_allocated_for_table_kb memory_used_by_table_kb memory_allocated_for_indexes_kb memory_used_by_indexes_kb
---------- ----------- ----------------------------- ----------------------- ------------------------------- -------------------------
t3         629577281   0                             0                       128                             0
t1         565577053   1372928                       1200008                 7872                            1942
t2         597577167   0                             0                       128                             0
NULL       -6          0                             0                       2                               2
NULL       -5          0                             0                       24                              24
NULL       -4          0                             0                       2                               2
NULL       -3          0                             0                       2                               2
NULL       -2          192                           25                      16                              16
```

 <span data-ttu-id="b40f8-132">Weitere Informationen finden Sie unter [sys. dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span><span class="sxs-lookup"><span data-stu-id="b40f8-132">For more information, see [sys.dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span></span>

#### <a name="memory-consumption-by-internal-system-structures"></a><span data-ttu-id="b40f8-133">Arbeitsspeichernutzung durch interne Systemstrukturen</span><span class="sxs-lookup"><span data-stu-id="b40f8-133">Memory consumption by internal system structures</span></span>
 <span data-ttu-id="b40f8-134">Arbeitsspeicher wird auch durch Systemobjekte beansprucht, z. B. Transaktionsstrukturen, Puffer für Daten- und Änderungsdateien, Garbage Collection-Strukturen usw.</span><span class="sxs-lookup"><span data-stu-id="b40f8-134">Memory is also consumed by system objects, such as, transactional structures, buffers for data and delta files, garbage collection structures, and more.</span></span> <span data-ttu-id="b40f8-135">Sie können den für diese Systemobjekte verwendeten Arbeitsspeicher abrufen, indem Sie `sys.dm_xtp_system_memory_consumers` wie hier dargestellt abfragen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-135">You can find the memory used for these system objects by querying `sys.dm_xtp_system_memory_consumers` as shown here.</span></span>

```sql
SELECT memory_consumer_desc
     , allocated_bytes/1024 AS allocated_bytes_kb
     , used_bytes/1024 AS used_bytes_kb
     , allocation_count
   FROM sys.dm_xtp_system_memory_consumers
```

 <span data-ttu-id="b40f8-136">**Beispielausgabe**</span><span class="sxs-lookup"><span data-stu-id="b40f8-136">**Sample Output**</span></span>

```
memory_consumer_ desc allocated_bytes_kb   used_bytes_kb        allocation_count
------------------------- -------------------- -------------------- ----------------
VARHEAP                   0                    0                    0
VARHEAP                   384                  0                    0
DBG_GC_OUTSTANDING_T      64                   64                   910
ACTIVE_TX_MAP_LOOKAS      0                    0                    0
RECOVERY_TABLE_CACHE      0                    0                    0
RECENTLY_USED_ROWS_L      192                  192                  261
RANGE_CURSOR_LOOKSID      0                    0                    0
HASH_CURSOR_LOOKASID      128                  128                  455
SAVEPOINT_LOOKASIDE       0                    0                    0
PARTIAL_INSERT_SET_L      192                  192                  351
CONSTRAINT_SET_LOOKA      192                  192                  646
SAVEPOINT_SET_LOOKAS      0                    0                    0
WRITE_SET_LOOKASIDE       192                  192                  183
SCAN_SET_LOOKASIDE        64                   64                   31
READ_SET_LOOKASIDE        0                    0                    0
TRANSACTION_LOOKASID      448                  448                  156
PGPOOL:256K               768                  768                  3
PGPOOL: 64K               0                    0                    0
PGPOOL:  4K               0                    0                    0
```

 <span data-ttu-id="b40f8-137">Weitere Informationen finden Sie unter [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b40f8-137">For more information see [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span></span>


#### <a name="memory-consumption-at-run-time-when-accessing-memory-optimized-tables"></a><span data-ttu-id="b40f8-138">Arbeitsspeichernutzung zur Laufzeit beim Zugriff auf speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="b40f8-138">Memory consumption at run-time when accessing memory-optimized tables</span></span>
 <span data-ttu-id="b40f8-139">Mit der folgenden Abfrage können Sie den von Laufzeitstrukturen wie dem Prozedurcache beanspruchten Arbeitsspeicher bestimmen. Führen Sie diese Abfrage aus, um den von Laufzeitstrukturen wie dem Prozedurcache beanspruchten Arbeitsspeicher abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-139">You can determine the memory consumed by run time structures, such as the procedure cache with the following query: run this query to get the memory used by run-time structures such as for the procedure cache.</span></span> <span data-ttu-id="b40f8-140">Alle Laufzeitstrukturen werden mit XTP markiert.</span><span class="sxs-lookup"><span data-stu-id="b40f8-140">All run-time structures are tagged with XTP.</span></span>

```sql
SELECT memory_object_address
     , pages_in_bytes
     , bytes_used
     , type
   FROM sys.dm_os_memory_objects WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="b40f8-141">**Beispielausgabe**</span><span class="sxs-lookup"><span data-stu-id="b40f8-141">**Sample Output**</span></span>

```
memory_object_address pages_ in_bytes bytes_used type
--------------------- ------------------- ---------- ----
0x00000001F1EA8040    507904              NULL       MEMOBJ_XTPDB
0x00000001F1EAA040    68337664            NULL       MEMOBJ_XTPDB
0x00000001FD67A040    16384               NULL       MEMOBJ_XTPPROCCACHE
0x00000001FD68C040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD284040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD302040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD382040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD402040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD482040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD502040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD67E040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001F813C040    8192                NULL       MEMOBJ_XTPBLOCKALLOC
0x00000001F813E040    16842752            NULL       MEMOBJ_XTPBLOCKALLOC
```

 <span data-ttu-id="b40f8-142">Weitere Informationen finden Sie unter [sys. dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b40f8-142">For more information, see [sys.dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span></span>

#### <a name="memory-consumed-by-hek_2-engine-across-the-instance"></a><span data-ttu-id="b40f8-143">Arbeitsspeichernutzung durch die [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Engine in der Instanz</span><span class="sxs-lookup"><span data-stu-id="b40f8-143">Memory consumed by [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine across the instance</span></span>
 <span data-ttu-id="b40f8-144">Der von der [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Engine und den speicheroptimierten Objekten belegte Arbeitsspeicher wird auf dieselbe Weise wie jeder andere Arbeitsspeicherconsumer innerhalb einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b40f8-144">Memory allocated to the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine and the memory-optimized objects is managed the same way as any other memory consumer within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b40f8-145">Der gesamte von der [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Engine belegte Arbeitsspeicher wird von Clerks des Typs MEMORYCLERK_XTP nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="b40f8-145">The clerks of type MEMORYCLERK_XTP accounts for all the memory allocated to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span> <span data-ttu-id="b40f8-146">Rufen Sie mit der folgenden Abfrage den gesamten von der [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Engine verwendeten Arbeitsspeicher ab.</span><span class="sxs-lookup"><span data-stu-id="b40f8-146">Use the following query to find all the memory used by the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span>

```sql
-- this DMV accounts for all memory used by the hek_2 engine
SELECT type
     , name
     , memory_node_id
     , pages_kb/1024 AS pages_MB 
   FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="b40f8-147">Die Beispielausgabe zeigt, dass 18 MB des insgesamt zugeordneten Arbeitsspeichers auf die Arbeitsspeichernutzung auf Systemebene und 1.358 MB auf die Datenbank mit der ID 5 entfallen.</span><span class="sxs-lookup"><span data-stu-id="b40f8-147">The sample output shows that the total memory allocated is 18 MB system-level memory consumption and 1358MB allocated to database id of 5.</span></span> <span data-ttu-id="b40f8-148">Da diese Datenbank einem dedizierten Ressourcenpool zugeordnet ist, wird dieser Arbeitsspeicher auf diesen Ressourcenpool angerechnet.</span><span class="sxs-lookup"><span data-stu-id="b40f8-148">Since this database is mapped to a dedicated resource pool, this memory is accounted for in that resource pool.</span></span>

 <span data-ttu-id="b40f8-149">**Beispielausgabe**</span><span class="sxs-lookup"><span data-stu-id="b40f8-149">**Sample Output**</span></span>

```
type                 name       memory_node_id pages_MB
-------------------- ---------- -------------- --------------------
MEMORYCLERK_XTP      Default    0              18
MEMORYCLERK_XTP      DB_ID_5    0              1358
MEMORYCLERK_XTP      Default    64             0
```

 <span data-ttu-id="b40f8-150">Weitere Informationen finden Sie unter [sys. dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b40f8-150">For more information, see [sys.dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span></span>

##   <a name="managing-memory-consumed-by-memory-optimized-objects"></a><span data-ttu-id="b40f8-151">Verwalten des von speicheroptimierten Objekten beanspruchten Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="b40f8-151">Managing memory consumed by memory-optimized objects</span></span>
 <span data-ttu-id="b40f8-152">Sie können den insgesamt von speicheroptimierten Tabellen beanspruchten Arbeitsspeicher steuern, indem Sie ihn an einen benannten Ressourcenpool binden, wie im Thema [Binden einer Datenbank mit speicheroptimierten Tabellen an einen Ressourcenpool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b40f8-152">You can control the total memory consumed by memory-optimized tables by binding it to a named resource pool as described in the topic [Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span></span>

##  <a name="troubleshooting-memory-issues"></a><span data-ttu-id="b40f8-153">Problembehandlung bei Arbeitsspeicherproblemen</span><span class="sxs-lookup"><span data-stu-id="b40f8-153">Troubleshooting Memory Issues</span></span>
 <span data-ttu-id="b40f8-154">Die Problembehandlung für den Arbeitsspeicher besteht aus drei Schritten:</span><span class="sxs-lookup"><span data-stu-id="b40f8-154">Troubleshooting memory issues is a three step process:</span></span>

1.  <span data-ttu-id="b40f8-155">Identifizieren Sie, wie viel Arbeitsspeicher von den Objekten in der Datenbank oder Instanz beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="b40f8-155">Identify how much memory is being consumed by the objects in your database or instance.</span></span> <span data-ttu-id="b40f8-156">Wie oben beschrieben, können Sie eine Vielzahl von Überwachungstools verwenden, die für speicheroptimierte Tabellen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b40f8-156">You can use a rich set of monitoring tools available for memory-optimized tables as described earlier.</span></span>  <span data-ttu-id="b40f8-157">Dies sind beispielsweise die DMVs `sys.dm_db_xtp_table_memory_stats` und `sys.dm_os_memory_clerks`.</span><span class="sxs-lookup"><span data-stu-id="b40f8-157">For example the DMVs `sys.dm_db_xtp_table_memory_stats` or `sys.dm_os_memory_clerks`.</span></span>

2.  <span data-ttu-id="b40f8-158">Bestimmen Sie, wie die Arbeitsspeichernutzung zunimmt und wie viel Spielraum noch vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b40f8-158">Determine how memory consumption is growing and how much head room you have left.</span></span> <span data-ttu-id="b40f8-159">Durch die regelmäßige Überwachung der Arbeitsspeichernutzung können Sie beurteilen, in welchem Maße die Arbeitsspeicherauslastung zunimmt.</span><span class="sxs-lookup"><span data-stu-id="b40f8-159">By monitoring the memory consumption periodically, you can know how the memory use is growing.</span></span> <span data-ttu-id="b40f8-160">Wenn Sie die Datenbank z. B. einem benannten Ressourcenpool zugeordnet haben, können Sie mit dem Leistungsindikator "Verwendeter Arbeitsspeicher (KB)" überwachen, wie die Speicherauslastung zunimmt.</span><span class="sxs-lookup"><span data-stu-id="b40f8-160">For example, if you have mapped the database to a named resource pool, you can monitor the performance counter Used Memory (KB) to see how memory usage is growing.</span></span>

3.  <span data-ttu-id="b40f8-161">Ergreifen Sie entsprechende Maßnahmen, um mögliche Probleme mit dem Arbeitsspeicher zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b40f8-161">Take action to mitigate the potential memory issues.</span></span> <span data-ttu-id="b40f8-162">Weitere Informationen finden Sie unter [Beheben von Problemen mit](resolve-out-of-memory-issues.md)dem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="b40f8-162">For more information, see [Resolve Out Of Memory Issues](resolve-out-of-memory-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b40f8-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b40f8-163">See Also</span></span>
 <span data-ttu-id="b40f8-164">[Binden einer Datenbank mit Speicher optimierten Tabellen an einen Ressourcen Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [ändern MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT für einen vorhandenen Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span><span class="sxs-lookup"><span data-stu-id="b40f8-164">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [Change MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on an existing pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span></span>


