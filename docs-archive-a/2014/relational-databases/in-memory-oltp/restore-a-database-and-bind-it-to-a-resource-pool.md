---
title: Wiederherstellen einer Datenbank und Binden der Datenbank an einen Ressourcenpool | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0b518c93ca9d5e7157ceaa20d9548d7b6061017d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607765"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a><span data-ttu-id="e662a-102">Wiederherstellen einer Datenbank und Binden der Datenbank an einen Ressourcenpool</span><span class="sxs-lookup"><span data-stu-id="e662a-102">Restore a Database and Bind it to a Resource Pool</span></span>
  <span data-ttu-id="e662a-103">Obwohl Sie über genügend Arbeitsspeicher zum Wiederherstellen einer Datenbank mit speicheroptimierten Tabellen verfügen, sollten Sie bewährte Methoden befolgen und die Datenbank an einen benannten Ressourcenpool binden.</span><span class="sxs-lookup"><span data-stu-id="e662a-103">Even though you have enough memory to restore a database with memory-optimized tables, you want to follow best practices and bind the database to a named resource pool.</span></span> <span data-ttu-id="e662a-104">Da die Datenbank vorhanden sein muss, bevor Sie diese an den Pool binden können, besteht die Wiederherstellung der Datenbank aus mehreren Schritten.</span><span class="sxs-lookup"><span data-stu-id="e662a-104">Since the database must exist before you can bind it to the pool restoring your database is a multi-step process.</span></span> <span data-ttu-id="e662a-105">In diesem Thema werden die einzelnen Schritte erläutert.</span><span class="sxs-lookup"><span data-stu-id="e662a-105">This topic walks you through that process.</span></span>  
  
##  <a name="restore-with-norecovery"></a><span data-ttu-id="e662a-106">Wiederherstellen mit NORECOVERY</span><span class="sxs-lookup"><span data-stu-id="e662a-106">Restore with NORECOVERY</span></span>  
 <span data-ttu-id="e662a-107">Wenn Sie eine Datenbank mit NORECOVERY wiederherstellen, wird die Datenbank erstellt und das Datenträgerimage wiederhergestellt, ohne dass Speicher beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="e662a-107">When you restore a database, NORECOVERY causes the database to be created and the disk image restored without consuming memory.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
##  <a name="create-the-resource-pool"></a><span data-ttu-id="e662a-108">Erstellen des Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="e662a-108">Create the resource pool</span></span>  
 <span data-ttu-id="e662a-109">Durch folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code wird ein Ressourcenpool mit dem Namen "Pool_IMOLTP" erstellt. 50 % des verfügbaren Arbeitsspeichers werden dem Pool zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="e662a-109">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a resource pool named Pool_IMOLTP with 50% of memory available for its use.</span></span>  <span data-ttu-id="e662a-110">Nachdem der Pool erstellt wurde, wird die Ressourcenkontrolle neu konfiguriert, um "Pool_IMOLTP" einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e662a-110">After the pool is created, the Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
##  <a name="bind-the-database-and-resource-pool"></a><span data-ttu-id="e662a-111">Binden der Datenbank und des Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="e662a-111">Bind the database and resource pool</span></span>  
 <span data-ttu-id="e662a-112">Binden Sie die Datenbank mithilfe der `sp_xtp_bind_db_resource_pool` -Systemfunktion an den Ressourcenpool.</span><span class="sxs-lookup"><span data-stu-id="e662a-112">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="e662a-113">Die Funktion akzeptiert zwei Parameter: den Datenbanknamen gefolgt vom Ressourcenpoolnamen.</span><span class="sxs-lookup"><span data-stu-id="e662a-113">The function takes two parameters: the database name followed by the resource pool name.</span></span>  
  
 <span data-ttu-id="e662a-114">Mit folgender [!INCLUDE[tsql](../../includes/tsql-md.md)] wird eine Bindung zwischen der IMOLTP_DB-Datenbank und dem Pool_IMOLTP-Ressourcenpool definiert.</span><span class="sxs-lookup"><span data-stu-id="e662a-114">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="e662a-115">Die Bindung wird erst wirksam, nachdem der nächste Schritt ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e662a-115">The binding does not become effective until you complete the next step.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
##  <a name="restore-with-recovery"></a><span data-ttu-id="e662a-116">Wiederherstellen mit RECOVERY</span><span class="sxs-lookup"><span data-stu-id="e662a-116">Restore with RECOVERY</span></span>  
 <span data-ttu-id="e662a-117">Wenn Sie die Datenbank mit RECOVERY wiederherstellen, werden die Datenbank online geschaltet und alle Daten wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="e662a-117">When you restore the database with recovery the database is brought online and all the data restored.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
##  <a name="monitor-the-resource-pool-performance"></a><span data-ttu-id="e662a-118">Überwachen der Ressourcenpoolleistung</span><span class="sxs-lookup"><span data-stu-id="e662a-118">Monitor the resource pool performance</span></span>  
 <span data-ttu-id="e662a-119">Überwachen Sie das "Statistiken für Ressourcenpools"-Objekt in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sobald die Datenbank an den benannten Ressourcenpool gebunden und mit RECOVERY wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e662a-119">Once the database is bound to the named resource pool and restored with recovery, monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Resource Pool Stats Object.</span></span> <span data-ttu-id="e662a-120">Weitere Informationen finden Sie unter [SQL Server, "Statistiken für Ressourcenpools"-Objekt](../performance-monitor/sql-server-resource-pool-stats-object.md).</span><span class="sxs-lookup"><span data-stu-id="e662a-120">For more information see [SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e662a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e662a-121">See Also</span></span>  
 <span data-ttu-id="e662a-122">[Binden einer Datenbank mit speicheroptimierten Tabellen an einen Ressourcenpool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="e662a-122">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span></span>  
 <span data-ttu-id="e662a-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e662a-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="e662a-124">[SQL Server, 'Statistiken für Ressourcenpools'-Objekt](../performance-monitor/sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="e662a-124">[SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="e662a-125">sys.dm_resource_governor_resource_pools</span><span class="sxs-lookup"><span data-stu-id="e662a-125">sys.dm_resource_governor_resource_pools</span></span>](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql)  
  
  
