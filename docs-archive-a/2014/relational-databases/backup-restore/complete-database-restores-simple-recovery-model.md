---
title: Vollständige Datenbankwiederherstellungen (einfaches Wiederherstellungsmodell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- simple recovery model [SQL Server]
- restoring [SQL Server], database
ms.assetid: 49828927-1727-4d1d-9ef5-3de43f68c026
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67eee8d7d6f44c9ff83795bf2a8bd612309bf0a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622721"
---
# <a name="complete-database-restores-simple-recovery-model"></a><span data-ttu-id="c7077-102">Vollständige Datenbankwiederherstellungen (einfaches Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="c7077-102">Complete Database Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="c7077-103">Das Ziel einer vollständigen Datenbankwiederherstellung besteht in der Wiederherstellung der gesamten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c7077-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="c7077-104">Die gesamte Datenbank ist für die Dauer der Wiederherstellung offline.</span><span class="sxs-lookup"><span data-stu-id="c7077-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="c7077-105">Bevor Teile der Datenbank wieder online zur Verfügung gestellt werden können, müssen alle Daten bis zu einem konsistenten Zeitpunkt wiederhergestellt werden. Ein solcher Punkt ist gegeben, wenn für alle Teile der Datenbank derselbe Zeitpunkt gilt und keine Transaktionen ohne Commit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c7077-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="c7077-106">Im einfachen Wiederherstellungsmodell kann die Datenbank nicht bis zu einem bestimmten Zeitpunkt innerhalb eines bestimmten Sicherungsvorgangs wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c7077-106">Under the simple recovery model, the database cannot be restored to a specific point in time within a specific backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c7077-107">Das Anfügen oder Wiederherstellen von Datenbanken aus unbekannten oder nicht vertrauenswürdigen Quellen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c7077-107">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="c7077-108">Diese Datenbanken können bösartigen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Code ausführt oder Fehler durch Ändern des Schemas oder der physischen Datenbankstruktur erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c7077-108">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="c7077-109">Bevor Sie eine Datenbank aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, führen Sie auf einem Nichtproduktionsserver [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank aus. Überprüfen Sie außerdem den Code in der Datenbank, z.B. gespeicherte Prozeduren oder anderen benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="c7077-109">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="c7077-110">Informationen zur Unterstützung von Sicherungskopien früherer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Versionen finden Sie im Kapitel [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)im Abschnitt „Kompatibilitätsunterstützung“.</span><span class="sxs-lookup"><span data-stu-id="c7077-110">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="overview-of-database-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="c7077-111">Übersicht über die Datenbankwiederherstellung mit dem einfachen Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="c7077-111">Overview of Database Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="c7077-112">Für eine vollständige Datenbankwiederherstellung mit dem einfachen Wiederherstellungsmodell sind nur ein oder zwei [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Anweisungen erforderlich, je nachdem, ob Sie eine differenzielle Datenbanksicherung wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c7077-112">A full database restore under the simple recovery model involves one or two [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statements, depending on whether you want to restore a differential database backup.</span></span> <span data-ttu-id="c7077-113">Stellen Sie lediglich die letzte Sicherung wieder her, wie in der folgenden Abbildung dargestellt, wenn Sie nur eine vollständige Datenbanksicherung verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7077-113">If you are using only a full database backup, just restore the most recent backup, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="c7077-114">![Wiederherstellung nur einer vollständigen Datenbanksicherung](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Wiederherstellung nur einer vollständigen Datenbanksicherung")</span><span class="sxs-lookup"><span data-stu-id="c7077-114">![Restoring only a full database backup](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restoring only a full database backup")</span></span>  
  
 <span data-ttu-id="c7077-115">Wenn Sie auch eine differenzielle Datenbanksicherung verwenden, stellen Sie die letzte vollständige Datenbanksicherung wieder her, ohne die Datenbank wiederherzustellen. Anschließend stellen Sie die letzte differenzielle Datenbanksicherung wieder her und stellen die Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="c7077-115">If you are also using a differential database backup, restore the most recent full database backup without recovering the database, and then restore the most recent differential database backup and recover the database.</span></span> <span data-ttu-id="c7077-116">Die folgende Abbildung veranschaulicht diesen Prozess:</span><span class="sxs-lookup"><span data-stu-id="c7077-116">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="c7077-117">![Wiederherstellung von vollständigen und von differenziellen Datenbanksicherungen](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Wiederherstellung von vollständigen und von differenziellen Datenbanksicherungen")</span><span class="sxs-lookup"><span data-stu-id="c7077-117">![Restoring full and differential database backups](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restoring full and differential database backups")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7077-118">Informationen zum Wiederherstellen einer Datenbanksicherung auf einer anderen Serverinstanz finden Sie unter [Kopieren von Datenbanken durch Sichern und Wiederherstellen](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="c7077-118">If you plan to restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="c7077-119">Grundlegende Transact-SQL-RESTORE-Syntax</span><span class="sxs-lookup"><span data-stu-id="c7077-119">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="c7077-120">Die grundlegende [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Syntax zur Wiederherstellung einer vollständigen Datenbanksicherung lautet:</span><span class="sxs-lookup"><span data-stu-id="c7077-120">The basic [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a full database backup is:</span></span>  
  
 <span data-ttu-id="c7077-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span><span class="sxs-lookup"><span data-stu-id="c7077-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7077-122">Verwenden Sie WITH NORECOVERY, wenn Sie planen, auch eine differenzielle Datenbanksicherung wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="c7077-122">Use WITH NORECOVERY if you plan to also restore a differential database backup.</span></span>  
  
 <span data-ttu-id="c7077-123">Die grundlegende [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Syntax zur Wiederherstellung einer Datenbanksicherung lautet:</span><span class="sxs-lookup"><span data-stu-id="c7077-123">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a database backup is:</span></span>  
  
 <span data-ttu-id="c7077-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="c7077-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span></span>  
  
###  <a name="example-transact-sql"></a><a name="Example"></a> <span data-ttu-id="c7077-125">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c7077-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c7077-126">Das folgende Beispiel zeigt zunächst, wie die [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung zum Erstellen einer vollständigen Datenbanksicherung und einer differenziellen Datenbanksicherung der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7077-126">The following example first shows how to use the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to create a full database backup and a differential database backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="c7077-127">Anschließend werden diese Sicherungen im Beispiel nacheinander wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c7077-127">The example then restores these backups in sequence.</span></span> <span data-ttu-id="c7077-128">Die Datenbank wird zu dem Status wiederhergestellt, in dem sie sich beim Abschließen der differenziellen Datenbanksicherung befand.</span><span class="sxs-lookup"><span data-stu-id="c7077-128">The database is restored to its state as of the time that the differential database backup finished.</span></span>  
  
 <span data-ttu-id="c7077-129">Im Beispiel werden die wichtigen Optionen in einer Wiederherstellungssequenz für das Szenario der vollständigen Datenbankwiederherstellung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c7077-129">The example shows the critical options in a restore sequence for the complete database restore scenario.</span></span> <span data-ttu-id="c7077-130">Eine *Wiederherstellungssequenz* besteht aus mindestens einem Wiederherstellungsvorgang, mit dessen Hilfe Daten mindestens eine Wiederherstellungsphase durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="c7077-130">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span> <span data-ttu-id="c7077-131">Hierfür unwichtige Syntax und Informationen werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="c7077-131">Syntax and details that are not relevant to this purpose are omitted.</span></span> <span data-ttu-id="c7077-132">Wenn Sie eine Datenbank wiederherstellen, wird empfohlen, die Option RECOVERY aus Gründen der Klarheit explizit anzugeben, obwohl das die Standardvorgabe ist.</span><span class="sxs-lookup"><span data-stu-id="c7077-132">When you recover a database, we recommend explicitly specifying the RECOVERY option for clarity, even though it is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7077-133">Das Beispiel beginnt mit einer [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung, mit der das Wiederherstellungsmodell auf `SIMPLE`festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c7077-133">The example starts with an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement that sets the recovery model to `SIMPLE`.</span></span>  
  
```  
USE master;  
--Make sure the database is using the simple recovery model.  
ALTER DATABASE AdventureWorks2012 SET RECOVERY SIMPLE;  
GO  
-- Back up the full AdventureWorks2012 database.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
  WITH FORMAT;  
GO  
--Create a differential database backup.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'  
   WITH DIFFERENTIAL;  
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=1, NORECOVERY;  
--Restore the differential backup (from backup set 2).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=2, RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c7077-134">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c7077-134">Related Tasks</span></span>  
 <span data-ttu-id="c7077-135">**So stellen Sie eine vollständige Datenbanksicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="c7077-135">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="c7077-136">Wiederherstellen einer Datenbanksicherung unter dem einfachen Wiederherstellungsmodell &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c7077-136">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="c7077-137">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c7077-137">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="c7077-138">Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c7077-138">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="c7077-139">**So stellen Sie eine differenzielle Datenbanksicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="c7077-139">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="c7077-140">Wiederherstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c7077-140">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="c7077-141">**So stellen Sie eine Sicherung mithilfe von SQL Server Management Objects (SMO) wieder her**</span><span class="sxs-lookup"><span data-stu-id="c7077-141">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  

  
## <a name="see-also"></a><span data-ttu-id="c7077-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7077-142">See Also</span></span>  
 <span data-ttu-id="c7077-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7077-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="c7077-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7077-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c7077-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7077-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="c7077-146">[Vollständige Datenbanksicherungen &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c7077-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="c7077-147">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c7077-147">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="c7077-148">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c7077-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="c7077-149">Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c7077-149">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
