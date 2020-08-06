---
title: Binden einer Datenbank mit speicheroptimierten Tabellen an einen Ressourcenpool | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f222b1d5-d2fa-4269-8294-4575a0e78636
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cd163c5d3bc7a2cd9051b8d37b8127a1cc88c30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630646"
---
# <a name="bind-a-database-with-memory-optimized-tables-to-a-resource-pool"></a><span data-ttu-id="8f71c-102">Binden einer Datenbank mit speicheroptimierten Tabellen an einen Ressourcenpool</span><span class="sxs-lookup"><span data-stu-id="8f71c-102">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>
  <span data-ttu-id="8f71c-103">Ein Ressourcenpool stellt eine Teilmenge der physischen Ressourcen dar, die kontrolliert werden können.</span><span class="sxs-lookup"><span data-stu-id="8f71c-103">A resource pool represents a subset of physical resources that can be governed.</span></span> <span data-ttu-id="8f71c-104">Standardmäßig sind [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken an den Standardressourcenpool gebunden und nutzen dessen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-104">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases are bound to and consume the resources of the default resource pool.</span></span> <span data-ttu-id="8f71c-105">Um die Auslastung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcen durch eine oder mehrere speicheroptimierte Tabellen und die Auslastung des für speicheroptimierte Tabellen erforderlichen Arbeitsspeichers durch andere Prozesse zu verhindern, wird empfohlen, einen eigenen Ressourcenpool zu erstellen, der die Arbeitsspeichernutzung für die Datenbank mit speicheroptimierten Tabellen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8f71c-105">To protect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from having its resources consumed by one or more memory-optimized tables, and to prevent other memory users from consuming memory needed by memory-optimized tables, you should create a separate resource pool to manage memory consumption for the database with memory-optimized tables.</span></span>  
  
 <span data-ttu-id="8f71c-106">Eine Datenbank kann nur an einen Ressourcenpool gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="8f71c-106">A database can be bound on only one resource pool.</span></span> <span data-ttu-id="8f71c-107">Sie können jedoch mehrere Datenbanken an denselben Pool binden.</span><span class="sxs-lookup"><span data-stu-id="8f71c-107">However, you can bind multiple databases to the same pool.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8f71c-108">unterstützt das Binden einer Datenbank ohne speicheroptimierte Tabellen an einen Ressourcenpool, dies hat jedoch keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-108">allows binding a database without memory-optimized tables to a resource pool but it has no effect.</span></span> <span data-ttu-id="8f71c-109">Sie sollten eine Datenbank an einen benannten Ressourcenpool binden, wenn Sie zu einem späteren Zeitpunkt möglicherweise speicheroptimierte Tabellen in der Datenbank erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8f71c-109">You may want to bind a database to a named resource pool if, in future, you may want to create memory-optimized tables in the database.</span></span>  
  
 <span data-ttu-id="8f71c-110">Bevor Sie eine Datenbank an einen Ressourcenpool binden können, müssen die Datenbank und der Ressourcenpool vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8f71c-110">Before you can bind a database to a resource pool both the database and the resource pool must exist.</span></span> <span data-ttu-id="8f71c-111">Die Bindung wird wirksam, wenn die Datenbank das nächste Mal online geschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="8f71c-111">The binding takes effect the next time the database is brought online.</span></span> <span data-ttu-id="8f71c-112">Weitere Informationen finden Sie unter [Database States](../databases/database-states.md) .</span><span class="sxs-lookup"><span data-stu-id="8f71c-112">See [Database States](../databases/database-states.md) for more information.</span></span>  
  
 <span data-ttu-id="8f71c-113">Weitere Informationen zu Ressourcenpools finden Sie unter [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8f71c-113">For information about resource pools, see [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span></span>  
  
  
## <a name="create-the-database-and-resource-pool"></a><span data-ttu-id="8f71c-114">Erstellen der Datenbank und des Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="8f71c-114">Create the database and resource pool</span></span>  
 <span data-ttu-id="8f71c-115">Sie können die Datenbank und den Ressourcenpool in beliebiger Reihenfolge erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-115">You can create the database and resource pool in any order.</span></span> <span data-ttu-id="8f71c-116">Wichtig ist, dass beide vor dem Binden der Datenbank an den Ressourcenpool bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8f71c-116">What matters is that they both exist prior to binding the database to the resource pool.</span></span>  
  
### <a name="create-the-database"></a><span data-ttu-id="8f71c-117">Erstellen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="8f71c-117">Create the database</span></span>  
 <span data-ttu-id="8f71c-118">Durch folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] wird eine Datenbank mit dem Namen "IMOLTP_DB" erstellt, die mindestens eine speicheroptimierte Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="8f71c-118">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a database named IMOLTP_DB which will contain one or more memory-optimized tables.</span></span> <span data-ttu-id="8f71c-119">Der Pfad \<driveAndPath> muss vor der Ausführung dieses Befehls vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8f71c-119">The path \<driveAndPath> must exist prior to running this command.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP_DB  
GO  
ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_fg CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_fg' , FILENAME = 'c:\data\IMOLTP_DB_fg') TO FILEGROUP IMOLTP_DB_fg;  
GO  
```  
  
### <a name="determine-the-minimum-value-for-min_memory_percent-and-max_memory_percent"></a><span data-ttu-id="8f71c-120">Bestimmen des Mindestwerts für MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT</span><span class="sxs-lookup"><span data-stu-id="8f71c-120">Determine the minimum value for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT</span></span>  
 <span data-ttu-id="8f71c-121">Sobald Sie die Arbeitsspeicheranforderungen für die speicheroptimierten Tabellen bestimmt haben, müssen Sie den erforderlichen Prozentsatz des verfügbaren Arbeitsspeichers bestimmen und die Arbeitsspeicherprozentsätze auf diesen oder einen höheren Wert festlegen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-121">Once you determine the memory needs for your memory-optimized tables, you need to determine what percentage of available memory you need, and set the memory percentages to that value or higher.</span></span>  
  
 <span data-ttu-id="8f71c-122">**Beispiel:**  </span><span class="sxs-lookup"><span data-stu-id="8f71c-122">**Example:** </span></span>  
<span data-ttu-id="8f71c-123">In diesem Beispiel wird davon ausgegangen, dass Sie Ihre Berechnungen ergeben haben, dass die speicheroptimierten Tabellen und Indizes 16 GB Arbeitsspeicher benötigen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-123">For this example we will assume that from your calculations you determined that your memory-optimized tables and indexes need 16 GB of memory.</span></span> <span data-ttu-id="8f71c-124">Weiter wird davon ausgegangen, dass Sie über 32 GB Arbeitsspeicher verfügen, der für Ihre Verwendung reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="8f71c-124">Assume that you have 32 GB of memory committed for your use.</span></span>  
  
 <span data-ttu-id="8f71c-125">Auf den ersten Blick müssen Sie MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT scheinbar auf 50 festlegen (50 % von 32 ist 16).</span><span class="sxs-lookup"><span data-stu-id="8f71c-125">At first glance it could seem that you need to set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to 50 (16 is 50% of 32).</span></span>  <span data-ttu-id="8f71c-126">Allerdings würde das Ihren speicheroptimierten Tabellen nicht genügend Arbeitsspeicher zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-126">However, that would not give your memory-optimized tables sufficient memory.</span></span> <span data-ttu-id="8f71c-127">In der folgenden Tabelle ([Prozentsatz des für speicheroptimierte Tabellen und Indizes verfügbaren Arbeitsspeichers](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) sehen Sie, dass 32GB Arbeitsspeicher zugesichert sind, wovon jedoch nur 80% für speicheroptimierte Tabellen und Indizes zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-127">Looking at the table below ([Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) we see that if there is 32 GB of committed memory, only 80% of that is available for memory-optimized tables and indexes.</span></span>  <span data-ttu-id="8f71c-128">Daher werden die Mindest- und Höchstprozentsätze auf Grundlage des verfügbaren Arbeitsspeichers und nicht des reservierten Arbeitsspeichers berechnet.</span><span class="sxs-lookup"><span data-stu-id="8f71c-128">Therefore, we calculate the min and max percentages based upon the available memory, not the committed memory.</span></span>  
  
 `memoryNeedeed = 16`   
 `memoryCommitted = 32`   
 `availablePercent = 0.8`   
 `memoryAvailable = memoryCommitted * availablePercent`   
 `percentNeeded = memoryNeeded / memoryAvailable`  
  
 <span data-ttu-id="8f71c-129">Unter Verwendung der tatsächlichen Zahlen:</span><span class="sxs-lookup"><span data-stu-id="8f71c-129">Plugging in real numbes:</span></span>   
`percentNeeded = 16 / (32 * 0.8) = 16 / 25.6 = 0.625`  
  
 <span data-ttu-id="8f71c-130">Daher benötigen Sie mindestens 62,5 % des verfügbaren Arbeitsspeichers, um die Anforderung von 16 GB für die speicheroptimierten Tabellen und Indizes zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-130">Thus you need at least 62.5% of the available memory to meet the 16 GB requirement of your memory-optimized tables and indexes.</span></span>  <span data-ttu-id="8f71c-131">Da die Werte für MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT ganze Zahlen sein müssen, werden sie auf mindestens 63 % festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8f71c-131">Since the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT must be integers, we set them to at least 63%.</span></span>  
  
### <a name="create-a-resource-pool-and-configure-memory"></a><span data-ttu-id="8f71c-132">Erstellen eines Ressourcenpools und Konfigurieren des Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="8f71c-132">Create a resource pool and configure memory</span></span>  
 <span data-ttu-id="8f71c-133">Beim Konfigurieren des Arbeitsspeichers für speicheroptimierte Tabellen sollte die Kapazitätsplanung auf MIN_MEMORY_PERCENT und nicht auf MAX_MEMORY_PERCENT beruhen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-133">When configuring memory for memory-optimized tables, the capacity planning should be done based on MIN_MEMORY_PERCENT, not on MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="8f71c-134">Weitere Informationen über MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT finden Sie unter [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8f71c-134">See [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) for information on MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="8f71c-135">Auf diese Weise ist die Speicherverfügbarkeit für speicheroptimierte Tabellen besser vorhersagbar, da MIN_MEMORY_PERCENT Arbeitsspeichermangel für andere Ressourcenpools verursacht, um die Verfügbarkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="8f71c-135">This provides more predictable memory availability for memory-optimized tables as MIN_MEMORY_PERCENT causes memory pressure to other resource pools to make sure it is honored.</span></span> <span data-ttu-id="8f71c-136">Um sicherzustellen, dass Arbeitsspeicher verfügbar ist, und um OOM-Bedingungen (Out of Memory, nicht genügend Arbeitsspeicher) zu vermeiden, sollten die Werte für MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT identisch sein.</span><span class="sxs-lookup"><span data-stu-id="8f71c-136">To ensure that memory is available and help avoid out-of-memory conditions, the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT should be the same.</span></span> <span data-ttu-id="8f71c-137">Unter [Prozentsatz des für speicheroptimierte Tabellen und Indizes verfügbaren Arbeitsspeichers](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) unten finden Sie den Prozentsatz des verfügbaren Arbeitsspeichers für speicheroptimierte Tabellen basierend auf der Menge an zugesichertem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="8f71c-137">See [Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) below for the percent of memory available for memory-optimized tables based on the amount of committed memory.</span></span>  
  
 <span data-ttu-id="8f71c-138">Unter [Bewährte Methoden: Verwenden von In-Memory OLTP in einer Umgebung mit virtuellen Computern](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) finden Sie weitere Informationen, wenn Sie in einer VM-Umgebung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f71c-138">See [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information when working in a VM environment.</span></span>  
  
 <span data-ttu-id="8f71c-139">Durch folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code wird ein Ressourcenpool mit dem Namen "Pool_IMOLTP" erstellt. Die Hälfte des verfügbaren Arbeitsspeichers wird dem Pool zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="8f71c-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a resource pool named Pool_IMOLTP with half of the memory available for its use.</span></span>  <span data-ttu-id="8f71c-140">Nachdem der Pool erstellt wurde, wird die Ressourcenkontrolle neu konfiguriert, um "Pool_IMOLTP" einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-140">After the pool is created Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
-- set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to the same value  
CREATE RESOURCE POOL Pool_IMOLTP   
  WITH   
    ( MIN_MEMORY_PERCENT = 63,   
    MAX_MEMORY_PERCENT = 63 );  
GO  
  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="bind-the-database-to-the-pool"></a><span data-ttu-id="8f71c-141">Binden der Datenbank an den Pool</span><span class="sxs-lookup"><span data-stu-id="8f71c-141">Bind the database to the pool</span></span>  
 <span data-ttu-id="8f71c-142">Binden Sie die Datenbank mithilfe der `sp_xtp_bind_db_resource_pool` -Systemfunktion an den Ressourcenpool.</span><span class="sxs-lookup"><span data-stu-id="8f71c-142">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="8f71c-143">Die Funktion akzeptiert zwei Parameter: den Datenbanknamen und den Ressourcenpoolnamen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-143">The function takes two parameters: the database name and the resource pool name.</span></span>  
  
 <span data-ttu-id="8f71c-144">Mit folgender [!INCLUDE[tsql](../../includes/tsql-md.md)] wird eine Bindung zwischen der IMOLTP_DB-Datenbank und dem Pool_IMOLTP-Ressourcenpool definiert.</span><span class="sxs-lookup"><span data-stu-id="8f71c-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="8f71c-145">Die Bindung wird erst wirksam, nachdem die Datenbank online geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="8f71c-145">The binding does not become effective until you bring the database online.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
 <span data-ttu-id="8f71c-146">Die sp_xtp_bind_db_resourece_pool-Systemfunktion akzeptiert zwei Zeichenfolgenparameter: database_name und pool_name.</span><span class="sxs-lookup"><span data-stu-id="8f71c-146">The system function sp_xtp_bind_db_resourece_pool takes two string parameters: database_name and pool_name.</span></span>  
  
## <a name="confirm-the-binding"></a><span data-ttu-id="8f71c-147">Bestätigen der Bindung</span><span class="sxs-lookup"><span data-stu-id="8f71c-147">Confirm the binding</span></span>  
 <span data-ttu-id="8f71c-148">Bestätigen Sie die Bindung, und beachten Sie die Ressourcenpool-ID für IMOLTP_DB.</span><span class="sxs-lookup"><span data-stu-id="8f71c-148">Confirm the binding, noting the resource pool id for IMOLTP_DB.</span></span> <span data-ttu-id="8f71c-149">Sie darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="8f71c-149">It should not be NULL.</span></span>  
  
```sql  
SELECT d.database_id, d.name, d.resource_pool_id  
FROM sys.databases d  
GO  
```  
  
## <a name="make-the-binding-effective"></a><span data-ttu-id="8f71c-150">Inkraftsetzen der Bindung</span><span class="sxs-lookup"><span data-stu-id="8f71c-150">Make the binding effective</span></span>  
 <span data-ttu-id="8f71c-151">Nachdem die Datenbank an den Ressourcenpool gebunden wurde, müssen Sie sie offline und anschließend wieder online schalten, damit die Bindung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="8f71c-151">You must take the database offline and back online after binding it to the resource pool for binding to take effect.</span></span> <span data-ttu-id="8f71c-152">Wenn die Datenbank zuvor an einen anderen Pool gebunden war, wird dadurch der zugeordnete Arbeitsspeicher aus dem vorherigen Ressourcenpool entfernt, und die Speicherbelegungen für die speicheroptimierte Tabelle und die Indizes stammen jetzt aus dem neu an die Datenbank gebundenen Ressourcenpool.</span><span class="sxs-lookup"><span data-stu-id="8f71c-152">If your database was bound to an a different pool earlier, this removes the allocated memory from the previous resource pool and memory allocations for your memory-optimized table and indexes will now come from the resource pool newly bound with the database.</span></span>  
  
```sql  
USE master  
GO  
  
ALTER DATABASE IMOLTP_DB SET OFFLINE  
GO  
ALTER DATABASE IMOLTP_DB SET ONLINE  
GO  
  
USE IMOLTP_DB  
GO  
```  
  
 <span data-ttu-id="8f71c-153">Jetzt ist die Datenbank an den Ressourcenpool gebunden.</span><span class="sxs-lookup"><span data-stu-id="8f71c-153">And now, the database is bound to the resource pool.</span></span>  
  
## <a name="change-min-memory-percent-and-max-memory-percent-on-an-existing-pool"></a><span data-ttu-id="8f71c-154">Ändern des prozentualen Arbeitsspeichers und des maximalen Arbeitsspeichers für einen vorhandenen Pool</span><span class="sxs-lookup"><span data-stu-id="8f71c-154">Change MIN MEMORY PERCENT and MAX MEMORY PERCENT on an existing pool</span></span>  
 <span data-ttu-id="8f71c-155">Wenn Sie dem Server zusätzlichen Arbeitsspeicher hinzufügen oder sich die für die speicheroptimierten Tabellen erforderliche Menge an Arbeitsspeicher ändert, müssen Sie möglicherweise den Wert von MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT ändern.</span><span class="sxs-lookup"><span data-stu-id="8f71c-155">If you add additional memory to the server or the amount of memory needed for your memory-optimized tables changes, you may need to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="8f71c-156">Die folgenden Schritte veranschaulichen, wie Sie den Wert von MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT für einen Ressourcenpool ändern.</span><span class="sxs-lookup"><span data-stu-id="8f71c-156">The following steps show you how to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on a resource pool.</span></span> <span data-ttu-id="8f71c-157">Richtlinien für die für MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT zu verwendenden Werte finden Sie im entsprechenden Abschnitt weiter unten.</span><span class="sxs-lookup"><span data-stu-id="8f71c-157">See the section below, for guidance on what values to use for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="8f71c-158">Weitere Informationen finden Sie im Thema [Bewährte Methoden: Verwenden von In-Memory-OLTP in einer VM-Umgebung](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8f71c-158">See the topic [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information.</span></span>  
  
1.  <span data-ttu-id="8f71c-159">Ändern Sie den Wert von MIN_MEMORY_PERCENT und MAX_MEMORY_PERCENT mithilfe von `ALTER RESOURCE POOL` .</span><span class="sxs-lookup"><span data-stu-id="8f71c-159">Use `ALTER RESOURCE POOL` to change the value of both MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  
  
2.  <span data-ttu-id="8f71c-160">Verwenden Sie `ALTER RESURCE GOVERNOR` , um die Ressourcenkontrolle mit den neuen Werten neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8f71c-160">Use `ALTER RESURCE GOVERNOR` to reconfigure the Resource Governor with the new values.</span></span>  
  
 <span data-ttu-id="8f71c-161">**Beispielcode**</span><span class="sxs-lookup"><span data-stu-id="8f71c-161">**Sample Code**</span></span>  
  
```sql  
ALTER RESOURCE POOL Pool_IMOLTP  
WITH  
     ( MIN_MEMORY_PERCENT = 70,  
       MAX_MEMORY_PERCENT = 70 )   
GO  
  
-- reconfigure the Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE  
GO  
```  
  
## <a name="percent-of-memory-available-for-memory-optimized-tables-and-indexes"></a><span data-ttu-id="8f71c-162">Prozentsatz des für speicheroptimierte Tabellen und Indizes verfügbaren Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="8f71c-162">Percent of memory available for memory-optimized tables and indexes</span></span>  
 <span data-ttu-id="8f71c-163">Wenn Sie eine Datenbank mit speicheroptimierten Tabellen und eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Arbeitsauslastung demselben Ressourcenpool zuordnen, legt die Ressourcenkontrolle einen internen Schwellenwert für [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] fest, damit bei der Poolverwendung keine Konflikte auftreten.</span><span class="sxs-lookup"><span data-stu-id="8f71c-163">If you map a database with memory-optimized tables and a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] workload to the same resource pool, the Resource Governor sets an internal threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use so that the users of the pool do not have conflicts over pool usage.</span></span> <span data-ttu-id="8f71c-164">Im Allgemeinen liegt der Nutzungsschwellenwert für [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] bei ca. 80 % des Pools.</span><span class="sxs-lookup"><span data-stu-id="8f71c-164">Generally speaking, the threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use is about 80% of the pool.</span></span> <span data-ttu-id="8f71c-165">In der folgenden Tabelle sind tatsächliche Schwellenwerte für verschiedene Arbeitsspeichergrößen angegeben.</span><span class="sxs-lookup"><span data-stu-id="8f71c-165">The following table shows actual thresholds for various memory sizes.</span></span>  
  
 <span data-ttu-id="8f71c-166">Wenn Sie einen dedizierten Ressourcenpool für die [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] -Datenbank erstellen, müssen Sie schätzen, wie viel physischer Arbeitsspeicher nach Berücksichtigung von Zeilenversionen und Datenzunahme für die Tabellen im Arbeitsspeicher benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="8f71c-166">When you create a dedicated resource pool for the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database, you need to estimate how much physical memory you need for the in-memory tables after accounting for row versions and data growth.</span></span> <span data-ttu-id="8f71c-167">Nach dem Schätzen des benötigten Arbeitsspeichers erstellen Sie einen Ressourcenpool mit einem Prozentwert des Commit-Zielarbeitsspeichers für die SQL-Instanz, wie durch die Spalte „committed_target_kb“ im DMV `sys.dm_os_sys_info` dargestellt (siehe [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="8f71c-167">Once estimate the memory needed, you create a resource pool with a percent of the commit target memory for SQL Instance as reflected by column 'committed_target_kb' in the DMV `sys.dm_os_sys_info` (see [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span></span> <span data-ttu-id="8f71c-168">Sie können beispielsweise einen Ressourcenpool "P1" mit 40 % des gesamten Arbeitsspeichers erstellen, der für die Instanz verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f71c-168">For example, you can create a resource pool P1 with 40% of the total memory available to the instance.</span></span> <span data-ttu-id="8f71c-169">Von diesen 40 % erhält die [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Engine einen kleineren Prozentsatz zum Speichern von [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Daten.</span><span class="sxs-lookup"><span data-stu-id="8f71c-169">Out of this 40%, the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine gets a smaller percent to store [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] data.</span></span>  <span data-ttu-id="8f71c-170">So wird sichergestellt, dass [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] nicht den gesamten Arbeitsspeicher aus diesem Pool beansprucht.</span><span class="sxs-lookup"><span data-stu-id="8f71c-170">This is done to make sure [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] does not consume all the memory from this pool.</span></span>  <span data-ttu-id="8f71c-171">Der Wert des kleineren Prozentsatzes ist abhängig vom zugesicherten Zielspeicher.</span><span class="sxs-lookup"><span data-stu-id="8f71c-171">This value of the smaller percent depends upon the Target committed Memory.</span></span> <span data-ttu-id="8f71c-172">In der folgenden Tabelle wird der für eine [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] -Datenbank in einem Ressourcenpool (benannt oder Standard) verfügbare Arbeitsspeicher aufgeführt, bevor ein OOM-Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8f71c-172">The following table describes memory available to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database in a resource pool (named or default) before an OOM error is raised.</span></span>  
  
|<span data-ttu-id="8f71c-173">Zugesicherter Zielspeicher</span><span class="sxs-lookup"><span data-stu-id="8f71c-173">Target Committed Memory</span></span>|<span data-ttu-id="8f71c-174">Für speicherinterne Tabellen verfügbarer Prozentsatz</span><span class="sxs-lookup"><span data-stu-id="8f71c-174">Percent available for in-memory tables</span></span>|  
|-----------------------------|---------------------------------------------|  
|<span data-ttu-id="8f71c-175"><= 8 GB</span><span class="sxs-lookup"><span data-stu-id="8f71c-175"><= 8 GB</span></span>|<span data-ttu-id="8f71c-176">70 %</span><span class="sxs-lookup"><span data-stu-id="8f71c-176">70%</span></span>|  
|<span data-ttu-id="8f71c-177"><= 16 GB</span><span class="sxs-lookup"><span data-stu-id="8f71c-177"><= 16 GB</span></span>|<span data-ttu-id="8f71c-178">75 %</span><span class="sxs-lookup"><span data-stu-id="8f71c-178">75%</span></span>|  
|<span data-ttu-id="8f71c-179"><= 32 GB</span><span class="sxs-lookup"><span data-stu-id="8f71c-179"><= 32 GB</span></span>|<span data-ttu-id="8f71c-180">80 %</span><span class="sxs-lookup"><span data-stu-id="8f71c-180">80%</span></span>|  
|<span data-ttu-id="8f71c-181">\<= 96 GB</span><span class="sxs-lookup"><span data-stu-id="8f71c-181">\<= 96 GB</span></span>|<span data-ttu-id="8f71c-182">85%</span><span class="sxs-lookup"><span data-stu-id="8f71c-182">85%</span></span>|  
|<span data-ttu-id="8f71c-183">>96 GB</span><span class="sxs-lookup"><span data-stu-id="8f71c-183">>96 GB</span></span>|<span data-ttu-id="8f71c-184">90%</span><span class="sxs-lookup"><span data-stu-id="8f71c-184">90%</span></span>|  
  
 <span data-ttu-id="8f71c-185">Wenn der zugesicherte Zielspeicher beispielsweise 100 GB beträgt und Sie schätzen, dass für die speicheroptimierten Tabellen und Indizes 60 GB Arbeitsspeicher benötigt werden, können Sie einen Ressourcenpool mit MAX_MEMORY_PERCENT = 67 erstellen (60 GB erforderlich/0,90 = 66,667 GB – aufgerundet auf 67 GB; 67 GB/100 GB installiert = 67 %). So wird sichergestellt, dass für die [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]-Objekte die erforderlichen 60 GB vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8f71c-185">For example, if your 'target committed memory' is 100 GB, and you estimate your memory-optimized tables and indexes need 60GBof memory, then you can create a resource pool with MAX_MEMORY_PERCENT = 67 (60GB needed / 0.90 = 66.667GB - round up to 67GB; 67GB / 100GB installed = 67%) to ensure that your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] objects have the 60GB they need.</span></span>  
  
 <span data-ttu-id="8f71c-186">Sobald eine Datenbank an einen benannten Ressourcenpool gebunden wurde, können Sie mit der folgenden Abfrage die Speicherbelegungen für unterschiedliche Ressourcenpools anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-186">Once a database has been bound to a named resource pool, use the following query to see memory allocations across different resource pools.</span></span>  
  
```sql  
SELECT pool_id  
     , Name  
     , min_memory_percent  
     , max_memory_percent  
     , max_memory_kb/1024 AS max_memory_mb  
     , used_memory_kb/1024 AS used_memory_mb   
     , target_memory_kb/1024 AS target_memory_mb  
   FROM sys.dm_resource_governor_resource_pools  
```  
  
 <span data-ttu-id="8f71c-187">Diese Beispielausgabe zeigt, dass speicheroptimierte Objekte 1.356 MB Arbeitsspeicher im Ressourcenpool "PoolIMOLTP" mit einer oberen Grenze von 2.307 MB belegen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-187">This sample output shows that the memory taken by memory-optimized objects is 1356 MB in resource pool, PoolIMOLTP, with an upper bound of 2307 MB.</span></span> <span data-ttu-id="8f71c-188">Diese Obergrenze steuert, wie viel Arbeitsspeicher insgesamt von speicheroptimierten Benutzer- und Systemobjekten belegt werden kann, die dem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8f71c-188">This upper bound controls the total memory that can be taken by user and system memory-optimized objects mapped to this pool.</span></span>  
  
 <span data-ttu-id="8f71c-189">**Beispielausgabe** </span><span class="sxs-lookup"><span data-stu-id="8f71c-189">**Sample Output** </span></span>  
<span data-ttu-id="8f71c-190">Diese Ausgabe stammt aus der oben erstellten Datenbank und den entsprechenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-190">This output is from the database and tables we created above.</span></span>  
  
```  
pool_id     Name        min_memory_percent max_memory_percent max_memory_mb used_memory_mb target_memory_mb  
----------- ----------- ------------------ ------------------ ------------- -------------- ----------------   
1           internal    0                  100                3845          125            3845  
2           default     0                  100                3845          32             3845  
259         PoolIMOLTP 0                  100                3845          1356           2307  
```  
  
 <span data-ttu-id="8f71c-191">Weitere Informationen finden Sie unter [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8f71c-191">For more information see [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span></span>  
  
 <span data-ttu-id="8f71c-192">Wenn Sie die Datenbank nicht an einen benannten Ressourcenpool binden, wird sie an den Pool „default“ gebunden.</span><span class="sxs-lookup"><span data-stu-id="8f71c-192">If you do not bind your database to a named resource pool, it is bound to the 'default' pool.</span></span> <span data-ttu-id="8f71c-193">Da der Standardressourcenpool von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die meisten anderen Zuordnungen verwendet wird, können Sie nicht die DMV "sys.dm_resource_governor_resource_pools" verwenden, um den von speicheroptimierten Tabellen beanspruchten Arbeitsspeicher für die gewünschte Datenbank exakt zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="8f71c-193">Since default resource pool is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for most other allocations, you will not be able to monitor memory consumed by memory-optimized tables using the DMV sys.dm_resource_governor_resource_pools accurately for the database of interest.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f71c-194">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f71c-194">See Also</span></span>  
 <span data-ttu-id="8f71c-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8f71c-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="8f71c-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8f71c-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="8f71c-197">[Resource Governor](../resource-governor/resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="8f71c-197">[Resource Governor](../resource-governor/resource-governor.md) </span></span>  
 <span data-ttu-id="8f71c-198">[Ressourcenpool für die Ressourcenkontrolle](../resource-governor/resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8f71c-198">[Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="8f71c-199">[Erstellen eines Ressourcenpools](../resource-governor/create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8f71c-199">[Create a Resource Pool](../resource-governor/create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="8f71c-200">[Ändern der Einstellungen für den Ressourcenpool](../resource-governor/change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f71c-200">[Change Resource Pool Settings](../resource-governor/change-resource-pool-settings.md) </span></span>  
 [<span data-ttu-id="8f71c-201">Löschen eines Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="8f71c-201">Delete a Resource Pool</span></span>](../resource-governor/delete-a-resource-pool.md)  
  
  
