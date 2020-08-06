---
title: Vollständige Datenbanksicherungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- backups [SQL Server], database
- backing up databases [SQL Server], full backups
- estimating database backup size
- backing up [SQL Server], size of backup
- database backups [SQL Server], full backups
- size [SQL Server], backups
- database backups [SQL Server], about backing up databases
ms.assetid: 4d933d19-8d21-4aa1-8153-d230cb3a3f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ee871b6cabbe6c2b2cb4f444fd1e2d42d711dfbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699825"
---
# <a name="full-database-backups-sql-server"></a><span data-ttu-id="355b1-102">Vollständige Datenbanksicherungen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="355b1-102">Full Database Backups (SQL Server)</span></span>
  <span data-ttu-id="355b1-103">Mit einer vollständigen Datenbanksicherung wird die gesamte Datenbank gesichert.</span><span class="sxs-lookup"><span data-stu-id="355b1-103">A full database backup backs up the whole database.</span></span> <span data-ttu-id="355b1-104">Dazu gehört ein Teil des Transaktionsprotokolls, damit nach der Wiederherstellung einer vollständigen Datenbanksicherung die vollständige Datenbank wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="355b1-104">This includes part of the transaction log so that the full database can be recovered after a full database backup is restored.</span></span> <span data-ttu-id="355b1-105">Vollständige Datenbanksicherungen stellen die Datenbank bei Abschluss der Sicherung dar.</span><span class="sxs-lookup"><span data-stu-id="355b1-105">Full database backups represent the database at the time the backup finished.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="355b1-106">Wenn eine Datenbank größer wird, ist zum Abschließen von vollständigen Datenbanksicherungen jedoch mehr Zeit und mehr Speicherplatz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="355b1-106">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="355b1-107">Deshalb können Sie bei einer großen Datenbank eine vollständige Datenbanksicherung durch mehrere *differenzielle Datenbanksicherungen*ergänzen.</span><span class="sxs-lookup"><span data-stu-id="355b1-107">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="355b1-108">Weitere Informationen finden Sie unter [Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="355b1-108">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="355b1-109">Bei einer Datenbanksicherung ist TRUSTWORTHY auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="355b1-109">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="355b1-110">Weitere Informationen zum Festlegen von TRUSTWORTHY auf ON finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="355b1-110">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="355b1-111">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="355b1-111">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="355b1-112">Datenbanksicherungen im einfachen Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="355b1-112">Database Backups Under the Simple Recovery Model</span></span>](#DbBuRMs)  
  
-   [<span data-ttu-id="355b1-113">Datenbanksicherungen im vollständigen Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="355b1-113">Database Backups Under the Full Recovery Model</span></span>](#DbBuRMf)  
  
-   [<span data-ttu-id="355b1-114">Verwenden einer vollständigen Datenbanksicherung zum Wiederherstellen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="355b1-114">Use a Full Database Backup to Restore the Database</span></span>](#RestoreDbBu)  
  
-   [<span data-ttu-id="355b1-115">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="355b1-115">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="database-backups-under-the-simple-recovery-model"></a><a name="DbBuRMs"></a> <span data-ttu-id="355b1-116">Datenbanksicherungen im einfachen Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="355b1-116">Database Backups Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="355b1-117">Im einfachen Wiederherstellungsmodell besteht nach jeder Sicherung die Gefahr, dass in der Datenbank Datenverluste auftreten, wenn ein Notfall auftritt.</span><span class="sxs-lookup"><span data-stu-id="355b1-117">Under the simple recovery model, after each backup, the database is exposed to potential work loss if a disaster were to occur.</span></span> <span data-ttu-id="355b1-118">Die Gefahr des Datenverlusts steigt mit jedem Update bis zur nächsten Sicherung, wenn die Gefahr auf null zurückgeht und ein neuer Zyklus der Datenverlustgefahr beginnt.</span><span class="sxs-lookup"><span data-stu-id="355b1-118">The work-loss exposure increases with each update until the next backup, when the work-loss exposure returns to zero and a new cycle of work-loss exposure starts.</span></span> <span data-ttu-id="355b1-119">Die Gefahr des Datenverlusts steigt in der Zeit zwischen den Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="355b1-119">Work-loss exposure increases over time between backups.</span></span> <span data-ttu-id="355b1-120">In der folgenden Abbildung wird die Gefahr des Datenverlusts für eine Sicherungsstrategie veranschaulicht, in der nur vollständige Datenbanksicherungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="355b1-120">The following illustration shows the work-loss exposure for a backup strategy that uses only full database backups.</span></span>  
  
 <span data-ttu-id="355b1-121">![Datenverlust zwischen Datenbanksicherungen](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Datenverlust zwischen Datenbanksicherungen")</span><span class="sxs-lookup"><span data-stu-id="355b1-121">![Shows work-loss exposure between database backups](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Shows work-loss exposure between database backups")</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="355b1-122">Beispiel ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="355b1-122">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="355b1-123">Im folgenden Beispiel wird veranschaulicht, wie eine vollständige Datenbanksicherung erstellt wird, indem WITH FORMAT zum Überschreiben aller vorhandenen Sicherungen und zum Erstellen eines neuen Mediensatzes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="355b1-123">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span>  
  
```  
-- Back up the AdventureWorks2012 database to new media set.  
BACKUP DATABASE AdventureWorks2012  
    TO DISK = 'Z:\SQLServerBackups\AdventureWorksSimpleRM.bak'   
    WITH FORMAT;  
GO  
```  
  
##  <a name="database-backups-under-the-full-recovery-model"></a><a name="DbBuRMf"></a> <span data-ttu-id="355b1-124">Datenbanksicherungen im vollständigen Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="355b1-124">Database Backups Under the Full Recovery Model</span></span>  
 <span data-ttu-id="355b1-125">Bei Datenbanken, für die die vollständige und massenprotokollierte Wiederherstellung verwendet wird, sind Datensicherungen erforderlich, aber nicht ausreichend.</span><span class="sxs-lookup"><span data-stu-id="355b1-125">For databases that use full and bulk-logged recovery, database backups are necessary but not sufficient.</span></span> <span data-ttu-id="355b1-126">Transaktionsprotokollsicherungen sind ebenfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="355b1-126">Transaction log backups are also required.</span></span> <span data-ttu-id="355b1-127">In der folgenden Abbildung wird die einfachste Sicherungsstrategie veranschaulicht, die im vollständigen Wiederherstellungsmodell möglich ist.</span><span class="sxs-lookup"><span data-stu-id="355b1-127">The following illustration shows the least complex backup strategy that is possible under the full recovery model.</span></span>  
  
 <span data-ttu-id="355b1-128">![Reihen vollständiger Datenbanksicherungen und Protokollsicherungen](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Reihen vollständiger Datenbanksicherungen und Protokollsicherungen")</span><span class="sxs-lookup"><span data-stu-id="355b1-128">![Series of full database backups and log backups](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series of full database backups and log backups")</span></span>  
  
 <span data-ttu-id="355b1-129">Informationen zum Verwenden von Transaktionsprotokollsicherungen finden Sie unter [Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="355b1-129">For information about how to create log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="355b1-130">Beispiel ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="355b1-130">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="355b1-131">Im folgenden Beispiel wird veranschaulicht, wie eine vollständige Datenbanksicherung erstellt wird, indem WITH FORMAT zum Überschreiben aller vorhandenen Sicherungen und zum Erstellen eines neuen Mediensatzes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="355b1-131">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span> <span data-ttu-id="355b1-132">Anschließend wird das Transaktionsprotokoll im Beispiel gesichert.</span><span class="sxs-lookup"><span data-stu-id="355b1-132">Then, the example backs up the transaction log.</span></span> <span data-ttu-id="355b1-133">In einer realen Situation müssten Sie mehrere reguläre Protokollsicherungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="355b1-133">In a real-life situation, you would have to perform a series of regular log backups.</span></span> <span data-ttu-id="355b1-134">Für dieses Beispiel muss die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank auf die Verwendung des vollständigen Wiederherstellungsmodells festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="355b1-134">For this example, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database is set to use the full recovery model.</span></span>  
  
```  
USE master;  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
GO  
-- Back up the AdventureWorks2012 database to new media set (backup set 1).  
BACKUP DATABASE AdventureWorks2012  
  TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak'   
  WITH FORMAT;  
GO  
--Create a routine log backup (backup set 2).  
BACKUP LOG AdventureWorks2012 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak';  
GO  
```  
  
##  <a name="use-a-full-database-backup-to-restore-the-database"></a><a name="RestoreDbBu"></a> <span data-ttu-id="355b1-135">Verwenden einer vollständigen Datenbanksicherung zum Wiederherstellen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="355b1-135">Use a Full Database Backup to Restore the Database</span></span>  
 <span data-ttu-id="355b1-136">Sie können eine gesamte Datenbank in einem Schritt erneut erstellen, indem Sie die Datenbank aus einer vollständigen Datenbanksicherung an einem beliebigen Speicherort wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="355b1-136">You can re-create a whole database in one step by restoring the database from a full database backup to any location.</span></span> <span data-ttu-id="355b1-137">In der Sicherung ist ein ausreichender Bestandteil des Transaktionsprotokolls enthalten, sodass Sie die Datenbank bis zu dem Zeitpunkt wiederherstellen können, zu dem die Sicherung abgeschlossen war.</span><span class="sxs-lookup"><span data-stu-id="355b1-137">Enough of the transaction log is included in the backup to let you recover the database to the time when the backup finished.</span></span> <span data-ttu-id="355b1-138">Die wiederhergestellte Datenbank entspricht dem Zustand der ursprünglichen Datenbank beim Abschluss der Datenbanksicherung, abzüglich aller Transaktionen, für die kein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="355b1-138">The restored database matches the state of the original database when the database backup finished, minus any uncommitted transactions.</span></span> <span data-ttu-id="355b1-139">Bei Verwendung des vollständigen Wiederherstellungsmodells sollten dann alle nachfolgenden Transaktionsprotokollsicherungen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="355b1-139">Under the full recovery model, you should then restore all subsequent transaction log backups.</span></span> <span data-ttu-id="355b1-140">Wenn die Datenbank wiederhergestellt wurde, wird für Transaktionen ohne Commit ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="355b1-140">When the database is recovered, uncommitted transactions are rolled back.</span></span>  
  
 <span data-ttu-id="355b1-141">Weitere Informationen finden Sie unter [Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](complete-database-restores-simple-recovery-model.md) oder [Vollständige Datenbankwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="355b1-141">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="355b1-142">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="355b1-142">Related Tasks</span></span>  
 <span data-ttu-id="355b1-143">**So erstellen Sie eine vollständige Datenbanksicherung**</span><span class="sxs-lookup"><span data-stu-id="355b1-143">**To create a full database backup**</span></span>  
  
-   [<span data-ttu-id="355b1-144">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="355b1-144">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   <span data-ttu-id="355b1-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="355b1-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="355b1-146">**So planen Sie Sicherungsaufträge**</span><span class="sxs-lookup"><span data-stu-id="355b1-146">**To schedule backup jobs**</span></span>  
  
 [<span data-ttu-id="355b1-147">Verwenden des Wartungsplanungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="355b1-147">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="355b1-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="355b1-148">See Also</span></span>  
 <span data-ttu-id="355b1-149">[Sichern und Wiederherstellen von SQL Server-Datenbanken](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="355b1-149">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="355b1-150">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="355b1-150">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="355b1-151">Sichern und Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="355b1-151">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
  
