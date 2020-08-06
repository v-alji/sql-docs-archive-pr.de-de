---
title: Vollständige Datenbankwiederherstellungen (vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation
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
- restoring [SQL Server], database
- full recovery model [SQL Server], performing restores
- log backups [SQL Server[
ms.assetid: 5b4c471c-b972-498e-aba9-92cf7a0ea881
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea6ec9f196acd0a64a0b785024bd6426cd6a5381
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622724"
---
# <a name="complete-database-restores-full-recovery-model"></a><span data-ttu-id="b57c4-102">Vollständige Datenbankwiederherstellungen (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="b57c4-102">Complete Database Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="b57c4-103">Das Ziel einer vollständigen Datenbankwiederherstellung besteht in der Wiederherstellung der gesamten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b57c4-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="b57c4-104">Die gesamte Datenbank ist für die Dauer der Wiederherstellung offline.</span><span class="sxs-lookup"><span data-stu-id="b57c4-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="b57c4-105">Bevor Teile der Datenbank wieder online zur Verfügung gestellt werden können, müssen alle Daten bis zu einem konsistenten Zeitpunkt wiederhergestellt werden. Ein solcher Punkt ist gegeben, wenn für alle Teile der Datenbank derselbe Zeitpunkt gilt und keine Transaktionen ohne Commit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b57c4-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="b57c4-106">Bei Verwendung des vollständigen Wiederherstellungsmodells müssen Sie nach dem Wiederherstellen der Datensicherung(en) alle nachfolgenden Transaktionsprotokollsicherungen und anschließend die Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b57c4-106">Under the full recovery model, after you restore your data backup or backups, you must restore all subsequent transaction log backups and then recover the database.</span></span> <span data-ttu-id="b57c4-107">Sie können eine Datenbank bis zu einem bestimmten *Wiederherstellungspunkt* innerhalb einer dieser Protokollsicherungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b57c4-107">You can restore a database to a specific *recovery point* within one of these log backups.</span></span> <span data-ttu-id="b57c4-108">Der Wiederherstellungspunkt kann einem bestimmten Datum mit einer bestimmten Uhrzeit, einer markierten Transaktion oder einer Protokollsequenznummer (Log Sequence Number, LSN) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b57c4-108">The recovery point can be a specific date and time, a marked transaction, or a log sequence number (LSN).</span></span>  
  
 <span data-ttu-id="b57c4-109">Beim Wiederherstellen einer Datenbank sollten Sie vor allem beim vollständigen und massenprotokollierten Wiederherstellungsmodell eine einzelne Wiederherstellungssequenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-109">When restoring a database, particularly under the full recovery model or bulk-logged recovery model, you should use a single restore sequence.</span></span> <span data-ttu-id="b57c4-110">Eine *Wiederherstellungssequenz* besteht aus mindestens einem Wiederherstellungsvorgang, mit dessen Hilfe Daten mindestens eine Wiederherstellungsphase durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="b57c4-110">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b57c4-111">Das Anfügen oder Wiederherstellen von Datenbanken aus unbekannten oder nicht vertrauenswürdigen Quellen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b57c4-111">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="b57c4-112">Diese Datenbanken können bösartigen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code ausführt oder Fehler durch Ändern des Schemas oder der physischen Datenbankstruktur erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-112">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="b57c4-113">Bevor Sie eine Datenbank aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, führen Sie auf einem Nichtproduktionsserver [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank aus. Überprüfen Sie außerdem den Code in der Datenbank, z.B. gespeicherte Prozeduren oder anderen benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="b57c4-113">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
 <span data-ttu-id="b57c4-114">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="b57c4-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="b57c4-115">Wiederherstellen einer Datenbank bis zum Zeitpunkt des Fehlers</span><span class="sxs-lookup"><span data-stu-id="b57c4-115">Restoring a Database to the Point of Failure</span></span>](#PointOfFailure)  
  
-   [<span data-ttu-id="b57c4-116">Wiederherstellen einer Datenbank bis zu einem Punkt in einer Protokoll Sicherung</span><span class="sxs-lookup"><span data-stu-id="b57c4-116">Restoring a Database to a Point Within a Log Backup</span></span>](#PointWithinBackup)  
  
-   [<span data-ttu-id="b57c4-117">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b57c4-117">Related Tasks</span></span>](#RelatedTasks)  
  
> [!NOTE]  
>  <span data-ttu-id="b57c4-118">Informationen zur Unterstützung von Sicherungskopien früherer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Versionen finden Sie im Kapitel [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)im Abschnitt „Kompatibilitätsunterstützung“.</span><span class="sxs-lookup"><span data-stu-id="b57c4-118">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="restoring-a-database-to-the-point-of-failure"></a><a name="PointOfFailure"></a> <span data-ttu-id="b57c4-119">Wiederherstellen einer Datenbank bis zum Zeitpunkt des Fehlers</span><span class="sxs-lookup"><span data-stu-id="b57c4-119">Restoring a Database to the Point of Failure</span></span>  
 <span data-ttu-id="b57c4-120">Zum Wiederherstellen einer Datenbank bis zum Zeitpunkt des Auftretens eines Fehlers werden in der Regel die folgenden grundlegenden Schritte ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="b57c4-120">Typically, recovering a database to the point of failure involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="b57c4-121">Sichern Sie das aktive Transaktionsprotokoll (das Protokollfragment).</span><span class="sxs-lookup"><span data-stu-id="b57c4-121">Back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="b57c4-122">Dadurch wird eine Sicherung des Protokollfragments erstellt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-122">This creates a tail-log backup.</span></span> <span data-ttu-id="b57c4-123">Wenn das aktive Transaktionsprotokoll nicht verfügbar ist, gehen alle Transaktionen in diesem Teil des Protokolls verloren.</span><span class="sxs-lookup"><span data-stu-id="b57c4-123">If the active transaction log is unavailable, all transactions in that part of the log are lost.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b57c4-124">Beim massenprotokollierten Wiederherstellungsmodell ist zum Sichern eines Protokolls, das massenprotokollierte Vorgänge enthält, der Zugriff auf alle Datendateien in der Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b57c4-124">Under the bulk-logged recovery model, backing up any log that contains bulk-logged operations requires access to all data files in the database.</span></span> <span data-ttu-id="b57c4-125">Wenn der Zugriff auf die Datendateien nicht möglich ist, kann das Transaktionsprotokoll nicht gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-125">If the data files cannot be accessed, the transaction log cannot be backed up.</span></span> <span data-ttu-id="b57c4-126">In diesem Fall müssen Sie alle Änderungen seit der letzten Protokollsicherung erneut manuell vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b57c4-126">In that case, you have to manually redo all changes that were made since the most recent log backup.</span></span>  
  
     <span data-ttu-id="b57c4-127">Weitere Informationen finden Sie unter [Protokollfragmentsicherungen &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b57c4-127">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="b57c4-128">Stellen Sie die letzte vollständige Datenbanksicherung wieder her, ohne die Datenbank selbst wiederherzustellen (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="b57c4-128">Restore the most recent full database backup without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
3.  <span data-ttu-id="b57c4-129">Wenn differenzielle Sicherungen vorhanden sind, stellen Sie die neueste Sicherung wieder her, ohne die Datenbank selbst wiederherzustellen (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="b57c4-129">If differential backups exist, restore the most recent one without recovering the database (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span></span>  
  
     <span data-ttu-id="b57c4-130">Durch die Wiederherstellung der neuesten differenziellen Sicherung wird die Anzahl der wiederherzustellenden Protokollsicherungen reduziert.</span><span class="sxs-lookup"><span data-stu-id="b57c4-130">Restoring the most recent differential backup reduces the number of log backups that must be restored.</span></span>  
  
4.  <span data-ttu-id="b57c4-131">Stellen Sie ausgehend von der ersten Transaktionsprotokollsicherung, die Sie nach der soeben wiederhergestellten Sicherung erstellt haben, die Protokolle der Reihe nach mit NORECOVERY wieder her.</span><span class="sxs-lookup"><span data-stu-id="b57c4-131">Starting with the first transaction log backup that was created after the backup you just restored, restore the logs in sequence with NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="b57c4-132">Stellen Sie die Datenbank wieder her (RESTORE DATABASE *database_name* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="b57c4-132">Recover the database (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span> <span data-ttu-id="b57c4-133">Alternativ kann dieser Schritt mit dem Wiederherstellen der letzten Protokollsicherung kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-133">Alternatively, this step can be combined with restoring the last log backup.</span></span>  
  
 <span data-ttu-id="b57c4-134">Die folgende Abbildung stellt diese Wiederherstellungssequenz dar:</span><span class="sxs-lookup"><span data-stu-id="b57c4-134">The following illustration shows this restore sequence.</span></span> <span data-ttu-id="b57c4-135">Wenn ein Fehler aufgetreten ist (1), wird eine Sicherung des Protokollfragments erstellt (2).</span><span class="sxs-lookup"><span data-stu-id="b57c4-135">After a failure occurs (1), a tail-log backup is created (2).</span></span> <span data-ttu-id="b57c4-136">Danach wird die Datenbank bis zu dem Zeitpunkt des Auftretens des Fehlers wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-136">Next, the database is restored to the point of the failure.</span></span> <span data-ttu-id="b57c4-137">Dieser Vorgang umfasst die Wiederherstellung einer Datenbanksicherung, eine nachfolgende differenzielle Sicherung sowie alle Protokollsicherungen nach der differenziellen Sicherung, einschließlich der Sicherung des Protokollfragments.</span><span class="sxs-lookup"><span data-stu-id="b57c4-137">This involves restoring a database backup, a subsequent differential backup, and every log backup taken after the differential backup, including the tail-log backup.</span></span>  
  
 <span data-ttu-id="b57c4-138">![Vollständige Datenbankwiederherstellung bis zum Auftreten des Fehlers](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Vollständige Datenbankwiederherstellung bis zum Auftreten des Fehlers")</span><span class="sxs-lookup"><span data-stu-id="b57c4-138">![Complete database restore to the time of a failure](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Complete database restore to the time of a failure")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b57c4-139">Informationen zum Wiederherstellen einer Datenbanksicherung auf einer anderen Serverinstanz finden Sie unter [Kopieren von Datenbanken durch Sichern und Wiederherstellen](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="b57c4-139">When you restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="b57c4-140">Grundlegende Transact-SQL-RESTORE-Syntax</span><span class="sxs-lookup"><span data-stu-id="b57c4-140">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="b57c4-141">Die grundlegende [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] -Syntax für die Wiederherstellungssequenz in der vorangehenden Abbildung sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="b57c4-141">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for the restore sequence in the preceding illustration is as follows:</span></span>  
  
1.  <span data-ttu-id="b57c4-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="b57c4-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span></span>  
  
2.  <span data-ttu-id="b57c4-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="b57c4-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span></span>  
  
3.  <span data-ttu-id="b57c4-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="b57c4-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span></span>  
  
     <span data-ttu-id="b57c4-145">Wiederholen Sie diesen Schritt der Protokollwiederherstellung für jede zusätzliche Protokollsicherung.</span><span class="sxs-lookup"><span data-stu-id="b57c4-145">Repeat this restore-log step for each additional log backup.</span></span>  
  
4.  <span data-ttu-id="b57c4-146">RESTORE DATABASE *database* WITH RECOVERY;</span><span class="sxs-lookup"><span data-stu-id="b57c4-146">RESTORE DATABASE *database* WITH RECOVERY;</span></span>  
  
###  <a name="example-recovering-to-the-point-of-failure-transact-sql"></a><a name="ExampleToPoFTsql"></a> <span data-ttu-id="b57c4-147">Beispiel: Wiederherstellen bis zum Zeitpunkt des Fehlers (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b57c4-147">Example: Recovering to the Point of Failure (Transact-SQL)</span></span>  
 <span data-ttu-id="b57c4-148">Im folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Beispiel werden die wesentlichen Optionen in einer Wiederherstellungssequenz veranschaulicht, mit der die Datenbank zum Zeitpunkt des Fehlers wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b57c4-148">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] example shows the essential options in a restore sequence that restores the database to the point of failure.</span></span> <span data-ttu-id="b57c4-149">Im Beispiel wird eine Sicherung des Protokollfragments der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-149">The example creates a tail-log backup of the database.</span></span> <span data-ttu-id="b57c4-150">Als Nächstes wird im Beispiel eine vollständige Datenbanksicherung und Protokollsicherung wiederhergestellt. Anschließend wird die Sicherung des Protokollfragments wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-150">Next, the example restores a full database backup and log backup and then restores the tail-log backup.</span></span> <span data-ttu-id="b57c4-151">Im Beispiel wird die Datenbank in einem separaten, abschließenden Schritt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-151">The example recovers the database in a separate, final step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b57c4-152">In diesem Beispiel werden eine Datenbanksicherung und eine Protokollsicherung verwendet, die im Abschnitt „Verwenden von Datenbanksicherungen im vollständigen Wiederherstellungsmodell“ in [Vollständige Datenbanksicherungen &#40;SQL Server&#41;](full-database-backups-sql-server.md)im Abschnitt „Kompatibilitätsunterstützung“.</span><span class="sxs-lookup"><span data-stu-id="b57c4-152">This example uses a database backup and log backup that is created in the "Using Database Backups Under the Full Recovery Model" section in [Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span></span> <span data-ttu-id="b57c4-153">Vor der Datenbanksicherung wurde die Beispieldatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] zur Verwendung des vollständigen Wiederherstellungsmodells festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-153">Before the database backup, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database was set to use the full recovery model.</span></span>  
  
```  
USE master;  
--Create tail-log backup.  
BACKUP LOG AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'    
   WITH NORECOVERY;   
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=1,   
    NORECOVERY;  
  
--Restore the regular log backup (from backup set 2).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=2,   
    NORECOVERY;  
  
--Restore the tail-log backup (from backup set 3).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'  
  WITH FILE=3,   
    NORECOVERY;  
GO  
--recover the database:  
RESTORE DATABASE AdventureWorks2012 WITH RECOVERY;  
GO  
```  
  
##  <a name="restoring-a-database-to-a-point-within-a-log-backup"></a><a name="PointWithinBackup"></a> <span data-ttu-id="b57c4-154">Wiederherstellen einer Datenbank bis zu einem Punkt in einer Protokollsicherung</span><span class="sxs-lookup"><span data-stu-id="b57c4-154">Restoring a Database to a Point Within a Log Backup</span></span>  
 <span data-ttu-id="b57c4-155">Beim vollständigen Wiederherstellungsmodell kann eine vollständige Datenbankwiederherstellung in der Regel bis zu einem Zeitpunkt, einer markierten Transaktion oder einer LSN in einer Protokollsicherung wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-155">Under the full recovery model, a complete database restore can usually be recovered to a point of time, a marked transaction, or an LSN within a log backup.</span></span> <span data-ttu-id="b57c4-156">Wenn jedoch beim massenprotokollierten Wiederherstellungsmodell die Protokollsicherung massenprotokollierte Änderungen enthält, ist die Zeitpunktwiederherstellung nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b57c4-156">However, under the bulk-logged recovery model, if the log backup contains bulk-logged changes, point-in-time recovery is not possible.</span></span>  
  
### <a name="sample-point-in-time-restore-scenarios"></a><span data-ttu-id="b57c4-157">Beispielszenarien für Zeitpunktwiederherstellungen</span><span class="sxs-lookup"><span data-stu-id="b57c4-157">Sample Point-in-Time Restore Scenarios</span></span>  
 <span data-ttu-id="b57c4-158">Im folgenden Beispiel wird angenommen, dass ein unternehmenswichtiges Datenbanksystem vorliegt, für das täglich um Mitternacht eine vollständige Datenbanksicherung erstellt wird. Eine differenzielle Datenbanksicherung wird von Montag bis Samstag stündlich erstellt, und Transaktionsprotokollsicherungen werden tagsüber alle 10 Minuten erstellt.</span><span class="sxs-lookup"><span data-stu-id="b57c4-158">The following example assumes a mission-critical database system for which a full database backup is created daily at midnight, a differential database backup is created on the hour, Monday through Saturday, and transaction log backups are created every 10 minutes throughout the day.</span></span> <span data-ttu-id="b57c4-159">Um die Datenbank in dem Status wiederherzustellen, der am Mittwoch um 5:19 Uhr vorlag,</span><span class="sxs-lookup"><span data-stu-id="b57c4-159">To restore the database to the state is was in at 5:19 A.M.</span></span> <span data-ttu-id="b57c4-160">gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b57c4-160">Wednesday, do the following:</span></span>  
  
1.  <span data-ttu-id="b57c4-161">Stellen Sie die vollständige Datenbanksicherung wieder her, die am Dienstag um Mitternacht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b57c4-161">Restore the full database backup that was created Tuesday at midnight.</span></span>  
  
2.  <span data-ttu-id="b57c4-162">Stellen Sie die differenzielle Datenbanksicherung wieder her, die am Donnerstag um 5:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="b57c4-162">Restore the differential database backup that was created at 5:00 A.M.</span></span> <span data-ttu-id="b57c4-163">erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b57c4-163">on Wednesday.</span></span>  
  
3.  <span data-ttu-id="b57c4-164">Wenden Sie die Transaktionsprotokollsicherung an, die am Donnerstag um 5:10 Uhr</span><span class="sxs-lookup"><span data-stu-id="b57c4-164">Apply the transaction log backup that was created at 5:10 A.M.</span></span> <span data-ttu-id="b57c4-165">erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b57c4-165">on Wednesday.</span></span>  
  
4.  <span data-ttu-id="b57c4-166">Wenden Sie die Transaktionsprotokollsicherung an, die am Mittwoch um 5:20 Uhr</span><span class="sxs-lookup"><span data-stu-id="b57c4-166">Apply the transaction log backup that was created 5:20 A.M.</span></span> <span data-ttu-id="b57c4-167">erstellt wurde, und geben Sie dabei an, dass beim Wiederherstellungsprozess ausschließlich Transaktionen angewendet werden sollen, die vor 5:19 Uhr stattfanden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-167">on Wednesday, specifying that the recovery process applies only to transactions that occurred before 5:19 A.M.</span></span>  
  
 <span data-ttu-id="b57c4-168">Sie können auch folgendermaßen vorgehen, wenn die Datenbank in dem Status von Donnerstag um 3:04 Uhr wiederhergestellt werden soll,</span><span class="sxs-lookup"><span data-stu-id="b57c4-168">Alternatively, if the database needs to be restored to its state at 3:04 A.M.</span></span> <span data-ttu-id="b57c4-169">die um 3:00 Uhr erstellte differenzielle Datenbanksicherung jedoch nicht</span><span class="sxs-lookup"><span data-stu-id="b57c4-169">Thursday, but the differential database backup that was created at 3:00 A.M.</span></span> <span data-ttu-id="b57c4-170">verfügbar ist:</span><span class="sxs-lookup"><span data-stu-id="b57c4-170">Thursday is unavailable, do the following:</span></span>  
  
1.  <span data-ttu-id="b57c4-171">Stellen Sie die Datenbanksicherung wieder her, die am Mittwoch um Mitternacht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b57c4-171">Restore the database backup that was created Wednesday at midnight.</span></span>  
  
2.  <span data-ttu-id="b57c4-172">Stellen Sie die differenzielle Datenbanksicherung wieder her, die am Donnerstag um 2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="b57c4-172">Restore the differential database backup that was created at 2:00 A.M.</span></span> <span data-ttu-id="b57c4-173">erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-173">on Thursday.</span></span>  
  
3.  <span data-ttu-id="b57c4-174">Wenden Sie alle Transaktionsprotokollsicherungen an, die am Donnerstag zwischen 2:10 Uhr</span><span class="sxs-lookup"><span data-stu-id="b57c4-174">Apply all the transaction log backups created from 2:10 A.M.</span></span> <span data-ttu-id="b57c4-175">auf 3:00 Uhr geändert.</span><span class="sxs-lookup"><span data-stu-id="b57c4-175">to 3:00 A.M.</span></span> <span data-ttu-id="b57c4-176">erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b57c4-176">on Thursday.</span></span>  
  
4.  <span data-ttu-id="b57c4-177">Wenden Sie die Transaktionsprotokollsicherung an, die am Donnerstag um 3:10 Uhr</span><span class="sxs-lookup"><span data-stu-id="b57c4-177">Apply the transaction log backup that was created at 3:10 A.M.</span></span> <span data-ttu-id="b57c4-178">erstellt wurde, und beenden Sie den Wiederherstellungsprozess um 3:04 Uhr.</span><span class="sxs-lookup"><span data-stu-id="b57c4-178">on Thursday, stopping the recovery process at 3:04 A.M.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b57c4-179">Ein Beispiel zum Wiederherstellen eines zu einem bestimmten Zeitpunkt bestehenden Datenbankzustands finden Sie unter [Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)im Abschnitt „Kompatibilitätsunterstützung“.</span><span class="sxs-lookup"><span data-stu-id="b57c4-179">For an example of a point-in-time restore, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b57c4-180">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b57c4-180">Related Tasks</span></span>  
 <span data-ttu-id="b57c4-181">**So stellen Sie eine vollständige Datenbanksicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="b57c4-181">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="b57c4-182">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-182">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="b57c4-183">Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-183">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="b57c4-184">**So stellen Sie eine differenzielle Datenbanksicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="b57c4-184">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="b57c4-185">Wiederherstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-185">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="b57c4-186">**So stellen Sie eine Transaktionsprotokollsicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="b57c4-186">**To restore a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="b57c4-187">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-187">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="b57c4-188">**So stellen Sie eine Sicherung mithilfe von SQL Server Management Objects (SMO) wieder her**</span><span class="sxs-lookup"><span data-stu-id="b57c4-188">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
 <span data-ttu-id="b57c4-189">**So stellen Sie eine Datenbank bis zu einem Punkt in einer Protokollsicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="b57c4-189">**To restore a database to a point within a log backup**</span></span>  
  
-   [<span data-ttu-id="b57c4-190">Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-190">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="b57c4-191">Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion</span><span class="sxs-lookup"><span data-stu-id="b57c4-191">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="b57c4-192">Wiederherstellen zu einer Protokollfolgenummer &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-192">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b57c4-193">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b57c4-193">See Also</span></span>  
 <span data-ttu-id="b57c4-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b57c4-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="b57c4-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b57c4-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b57c4-196">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b57c4-196">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b57c4-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b57c4-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="b57c4-198">[Vollständige Datenbanksicherungen &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b57c4-198">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b57c4-199">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b57c4-199">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b57c4-200">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b57c4-200">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="b57c4-201">Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57c4-201">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
