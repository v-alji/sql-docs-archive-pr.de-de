---
title: Dateiwiederherstellungen (vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- full recovery model [SQL Server], performing restores
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- file restores [SQL Server], full recovery model
- restoring files [SQL Server], full recovery model
- Transact-SQL restore sequence
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: d2236a2a-4cf1-4c3f-b542-f73f6096e15c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 488515ec900867f13d33580402e36a3f98747bb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699831"
---
# <a name="file-restores-full-recovery-model"></a><span data-ttu-id="67611-102">Dateiwiederherstellungen (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="67611-102">File Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="67611-103">Dieses Thema ist nur für Datenbanken relevant, die mehrere Dateien oder Dateigruppen enthalten, die das vollständige oder massenprotokollierte Wiederherstellungsmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="67611-103">This topic is relevant only for databases that contain multiple files or filegroups under the full or bulk-load recovery model.</span></span>  
  
 <span data-ttu-id="67611-104">Das Ziel einer Dateiwiederherstellung besteht darin, eine oder mehrere beschädigte Dateien wiederherzustellen, ohne dabei die gesamte Datenbank wiederherstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="67611-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="67611-105">Ein Dateiwiederherstellungsszenario besteht aus einer einzigen Wiederherstellungssequenz, bei der die entsprechenden Daten kopiert werden, ein Rollforward ausgeführt wird und die Daten wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="67611-105">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data</span></span>  
  
 <span data-ttu-id="67611-106">Wenn die wiederherzustellende Dateigruppe Lese-/Schreibzugriff aufweist, muss nach der Wiederherstellung der letzten Daten bzw. der letzten differenziellen Sicherung eine fortlaufende Kette von Protokollsicherungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="67611-106">If the filegroup that is being restored is read/write, an unbroken chain of log backups must be applied after the last data or differential backup is restored.</span></span> <span data-ttu-id="67611-107">Auf diese Weise wird die Dateigruppe auf den Stand der Protokolldatensätze in der aktuellen Protokolldatei gebracht.</span><span class="sxs-lookup"><span data-stu-id="67611-107">This brings the filegroup forward to the log records in the current active log records in the log file.</span></span> <span data-ttu-id="67611-108">Der Wiederherstellungspunkt befindet sich normalerweise – aber nicht zwingend – gegen Ende der Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="67611-108">The recovery point is typically near the end of log, but not necessarily.</span></span>  
  
 <span data-ttu-id="67611-109">Ist die wiederherzustellende Dateigruppe schreibgeschützt, müssen normalerweise keine Protokollsicherungen angewendet werden; dieser Schritt wird daher ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="67611-109">If the filegroup that is being restored is read-only, usually applying log backups is unnecessary and is skipped.</span></span> <span data-ttu-id="67611-110">Wenn die Sicherung durchgeführt wurde, nachdem die Datei schreibgeschützt worden war, ist dies die letzte Sicherung, die wiederhergestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="67611-110">If the backup was taken after the file became read-only, that is the last backup to restore.</span></span> <span data-ttu-id="67611-111">Die Ausführung des Rollforwards endet am Zielpunkt.</span><span class="sxs-lookup"><span data-stu-id="67611-111">Roll forward stops at the target point.</span></span>  
  
 <span data-ttu-id="67611-112">Für die Dateiwiederherstellung sind folgende Szenarien möglich:</span><span class="sxs-lookup"><span data-stu-id="67611-112">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="67611-113">Offlinedateiwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="67611-113">Offline file restore</span></span>  
  
     <span data-ttu-id="67611-114">Bei einer *Offlinedateiwiederherstellung*ist die Datenbank offline, während die beschädigten Dateien oder Dateigruppen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="67611-114">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="67611-115">Am Ende der Wiederherstellungssequenz wird die Datenbank wieder online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="67611-115">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="67611-116">Offlinewiederherstellungen werden von allen Editionen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67611-116">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="67611-117">Onlinedateiwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="67611-117">Online file restore</span></span>  
  
     <span data-ttu-id="67611-118">Bei einer *Onlinedateiwiederherstellung*bleibt die Datenbank online, wenn die Datenbank während einer Dateiwiederherstellung online ist.</span><span class="sxs-lookup"><span data-stu-id="67611-118">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="67611-119">Dateigruppen, in denen eine Datei wiederhergestellt wird, sind während des Wiederherstellungsvorgangs jedoch offline.</span><span class="sxs-lookup"><span data-stu-id="67611-119">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="67611-120">Sobald die Dateien einer Offlinedateigruppe wiederhergestellt sind, wird die Dateigruppe automatisch wieder online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="67611-120">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="67611-121">Informationen zur Unterstützung von Onlinewiederherstellungen von Seiten und Dateien finden Sie unter [Von den SQL Server 2014-Editionen unterstützte Funktionen](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="67611-121">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="67611-122">Weitere Informationen zur Onlinewiederherstellung finden Sie unter [Onlinewiederherstellung &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="67611-122">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="67611-123">Wenn Sie möchten, dass die Datenbank für eine Dateiwiederherstellung offline ist, können Sie die Datenbank vor dem Starten der Wiederherstellungssequenz offline schalten, indem Sie die folgende [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)-Anweisung ausführen: ALTER DATABASE *Datenbankname* SET OFFLINE</span><span class="sxs-lookup"><span data-stu-id="67611-123">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  
  
  
##  <a name="restoring-damaged-files-from-file-backups"></a><a name="Overview"></a> <span data-ttu-id="67611-124">Wiederherstellen von beschädigten Dateien aus Dateisicherungen</span><span class="sxs-lookup"><span data-stu-id="67611-124">Restoring Damaged Files from File Backups</span></span>  
  
1.  <span data-ttu-id="67611-125">Erstellen Sie vor dem Wiederherstellen von beschädigten Dateien nach Möglichkeit eine [Sicherung des Protokollfragments](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="67611-125">Before restoring one or more damaged files, attempt to create a [tail-log backup](tail-log-backups-sql-server.md).</span></span>  
  
     <span data-ttu-id="67611-126">Wenn das Protokoll beschädigt wurde, kann keine Sicherung des Protokollfragments erstellt werden, und Sie müssen die gesamte Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="67611-126">If the log has been damaged, a tail-log backup cannot be created, and you must restore the whole database.</span></span>  
  
     <span data-ttu-id="67611-127">Informationen zum Sichern eines Transaktionsprotokolls finden Sie unter [Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="67611-127">For information about how to back up a transaction log, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="67611-128">Bei einer Offlinedateiwiederherstellung müssen Sie immer im Voraus eine Sicherung des Protokollfragments erstellen.</span><span class="sxs-lookup"><span data-stu-id="67611-128">For an offline file restore, you must always take a tail-log backup before the file restore.</span></span> <span data-ttu-id="67611-129">Bei einer Onlinedateiwiederherstellung müssen Sie die Sicherung des Protokollfragments immer danach erstellen.</span><span class="sxs-lookup"><span data-stu-id="67611-129">For an online file restore, you must always take the log backup after the file restore.</span></span> <span data-ttu-id="67611-130">Die Protokollsicherung ist erforderlich, um für die wiederherzustellenden Dateien einen mit der restlichen Datenbank konsistenten Status zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="67611-130">This log backup is necessary to allow for the file to be recovered to a state consistent with the rest of the database.</span></span>  
  
2.  <span data-ttu-id="67611-131">Stellen Sie jede beschädigte Datei von der letzten Dateisicherung dieser Datei wieder her.</span><span class="sxs-lookup"><span data-stu-id="67611-131">Restore each damaged file from the most recent file backup of that file.</span></span>  
  
3.  <span data-ttu-id="67611-132">Stellen Sie für jede wiederhergestellte Datei die letzte differenzielle Dateisicherung wieder her (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="67611-132">Restore the most recent differential file backup, if any, for each restored file.</span></span>  
  
4.  <span data-ttu-id="67611-133">Stellen Sie Transaktionsprotokollsicherungen in der chronologischen Reihenfolge wieder her, beginnend mit der Sicherung für die älteste der wiederhergestellten Dateien bis hin zu der in Schritt 1 erstellen Sicherung des Protokollfragments.</span><span class="sxs-lookup"><span data-stu-id="67611-133">Restore transaction log backups in sequence, starting with the backup that covers the oldest of the restored files and ending with the tail-log backup created in step 1.</span></span>  
  
     <span data-ttu-id="67611-134">Um eine Datenbank in einen konsistenten Status zu versetzen, müssen Sie die Transaktionsprotokollsicherungen wiederherstellen, die nach den Dateisicherungen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="67611-134">You must restore the transaction log backups that were created after the file backups to bring the database to a consistent state.</span></span> <span data-ttu-id="67611-135">Für die Transaktionsprotokollsicherungen kann schnell ein Rollforward ausgeführt werden, weil nur die Änderungen, die die wiederhergestellten Dateien betreffen, angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="67611-135">The transaction log backups can be rolled forward quickly, because only the changes that apply to the restored files are applied.</span></span> <span data-ttu-id="67611-136">Die Wiederherstellung einzelner Dateien ist der Wiederherstellung der gesamten Datenbank vorzuziehen, da nicht beschädigte Dateien dann nicht kopiert werden müssen und für diese Dateien auch kein Rollforward ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="67611-136">Restoring individual files can be better than restoring the whole database, because undamaged files are not copied and then rolled forward.</span></span> <span data-ttu-id="67611-137">Es muss jedoch trotzdem die gesamte Kette der Protokollsicherungen gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="67611-137">However, the whole chain of log backups still has to be read.</span></span>  
  
5.  <span data-ttu-id="67611-138">Stellen Sie die Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="67611-138">Recover the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67611-139">Mit Dateisicherungen kann der Status der Datenbank zu einem früheren Zeitpunkt wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="67611-139">File backups can be used to restore the database to an earlier point in time.</span></span> <span data-ttu-id="67611-140">Dazu müssen Sie einen vollständigen Dateisicherungssatz wiederherstellen und anschließend die Transaktionsprotokollsicherungen in der chronologischen Reihenfolge wiederherstellen, um einen Zielpunkt zu erreichen, der nach dem Ende der letzten wiederhergestellten Dateisicherung liegt.</span><span class="sxs-lookup"><span data-stu-id="67611-140">To do this, you must restore a complete set of file backups, and then restore transaction log backups in sequence to reach a target point that is after the end of the most recent restored file backup.</span></span> <span data-ttu-id="67611-141">Weitere Informationen zum Wiederherstellen eines zu einem bestimmten Zeitpunkt bestehenden Datenbankzustands finden Sie unter [Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="67611-141">For more information about point-in-time recovery, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
## <a name="transact-sql-restore-sequence-for-an-offline-file-restore-full-recovery-model"></a><span data-ttu-id="67611-142">Transact-SQL-Wiederherstellungssequenz für die Offlinedateiwiederherstellung (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="67611-142">Transact-SQL Restore Sequence for an Offline File Restore (Full Recovery Model)</span></span>  
 <span data-ttu-id="67611-143">Ein Dateiwiederherstellungsszenario besteht aus einer einzigen Wiederherstellungssequenz, bei der die entsprechenden Daten kopiert werden, ein Rollforward ausgeführt wird und die Daten wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="67611-143">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data.</span></span>  
  
 <span data-ttu-id="67611-144">In diesem Abschnitt werden die grundlegenden [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Optionen für eine vollständige Dateiwiederherstellungssequenz erläutert.</span><span class="sxs-lookup"><span data-stu-id="67611-144">This section shows the essential [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a file-restore sequence.</span></span> <span data-ttu-id="67611-145">Hierfür unwichtige Syntax und Informationen werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="67611-145">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="67611-146">Die folgende Beispielwiederherstellungssequenz zeigt eine Offlinewiederherstellung von zwei sekundären Dateien ( `A` und `B`) mit WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="67611-146">The following sample restore sequence shows an offline restore of two secondary files, `A` and `B`, using WITH NORECOVERY.</span></span> <span data-ttu-id="67611-147">Anschließend werden zwei Protokollsicherungen mit NORECOVERY angewendet, gefolgt von der Sicherung des Protokollfragments, die mit WITH RECOVERY wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="67611-147">Next, two log backups are applied with NORECOVERY, followed with the tail-log backup, and this is restored using WITH RECOVERY.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67611-148">Die folgende Beispielwiederherstellungssequenz startet, indem sie die Datei offline schaltet und dann eine Sicherung des Protokollfragments erstellt.</span><span class="sxs-lookup"><span data-stu-id="67611-148">The following sample restore sequence starts by taking the file offline and then creates a tail-log backup.</span></span>  
  
```  
--Take the file offline.  
ALTER DATABASE database_name MODIFY FILE SET OFFLINE;  
-- Back up the currently active transaction log.  
BACKUP LOG database_name  
   TO <tail_log_backup>  
   WITH NORECOVERY;  
GO   
-- Restore the files.  
RESTORE DATABASE database_name FILE=name   
   FROM <file_backup_of_file_A>   
   WITH NORECOVERY;  
RESTORE DATABASE database_name FILE=<name> ......  
   FROM <file_backup_of_file_B>   
   WITH NORECOVERY;  
-- Restore the log backups.  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <tail_log_backup>   
   WITH RECOVERY;  
```  
  
## <a name="examples"></a><span data-ttu-id="67611-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="67611-149">Examples</span></span>  
  
-   [<span data-ttu-id="67611-150">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-150">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="67611-151">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-151">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="67611-152">Beispiel: Offlinewiederherstellung der primären Dateigruppe und einer weiteren Dateigruppe &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-152">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="67611-153">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="67611-153">Related Tasks</span></span>  
 <span data-ttu-id="67611-154">**So stellen Sie Dateien und Dateigruppen wieder her**</span><span class="sxs-lookup"><span data-stu-id="67611-154">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="67611-155">Wiederherstellen von Dateien an einem neuen Speicherort &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-155">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="67611-156">Wiederherstellen von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-156">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="67611-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="67611-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="67611-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67611-158">See Also</span></span>  
 <span data-ttu-id="67611-159">[Sicherung und Wiederherstellung: Interoperabilität und gleichzeitige Verwendung &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67611-159">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="67611-160">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67611-160">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="67611-161">[Vollständige Dateisicherungen &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67611-161">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="67611-162">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67611-162">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="67611-163">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67611-163">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="67611-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67611-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="67611-165">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="67611-165">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="67611-166">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-166">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
