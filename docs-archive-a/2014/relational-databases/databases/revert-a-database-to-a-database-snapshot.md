---
title: Wiederherstellen einer Datenbank zu einer Datenbank-Momentaufnahme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c78da3d7c559309c0563760e7062f01cf784648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617092"
---
# <a name="revert-a-database-to-a-database-snapshot"></a><span data-ttu-id="70d0b-102">Wiederherstellen einer Datenbank zu einer Datenbank-Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="70d0b-102">Revert a Database to a Database Snapshot</span></span>
  <span data-ttu-id="70d0b-103">Wenn Daten in einer Onlinedatenbank beschädigt werden, empfiehlt es sich gelegentlich, die Datenbank aus einer Datenbank-Momentaufnahme eines Zeitpunkts vor der Beschädigung wiederherzustellen, anstatt die Datenbank aus einer Sicherungskopie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-103">If data in an online database becomes damaged, in some cases, reverting the database to a database snapshot that predates the damage might be an appropriate alternative to restoring the database from a backup.</span></span> <span data-ttu-id="70d0b-104">Durch das Wiederherstellen einer Datenbank kann beispielsweise ein kürzlich zurückliegender, schwerwiegender Benutzerfehler (z. B. eine gelöschte Tabelle) rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="70d0b-104">For example, reverting a database might be useful for reverse a recent serious user error, such as a dropped table.</span></span> <span data-ttu-id="70d0b-105">Alle nach Erstellung der Momentaufnahme vorgenommenen Änderungen gehen jedoch verloren.</span><span class="sxs-lookup"><span data-stu-id="70d0b-105">However, all changes made after the snapshot was created are lost.</span></span>  
  
-   <span data-ttu-id="70d0b-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="70d0b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="70d0b-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="70d0b-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="70d0b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="70d0b-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="70d0b-109">Security</span><span class="sxs-lookup"><span data-stu-id="70d0b-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="70d0b-110">**Wiederherstellen einer Datenbank zu einer Datenbank-Momentaufnahme mit:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="70d0b-110">**To Revert a Database to a Database Snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="70d0b-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="70d0b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="70d0b-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="70d0b-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="70d0b-113">Die Wiederherstellung wird unter folgenden Bedingungen nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="70d0b-113">Reverting is unsupported under the following conditions:</span></span>  
  
-   <span data-ttu-id="70d0b-114">Die Datenbank darf derzeit nur über eine Datenbank-Momentaufnahme verfügen, mit der die Wiederherstellung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="70d0b-114">The database must currently have only one database snapshot, to which you plan to revert.</span></span>  
  
-   <span data-ttu-id="70d0b-115">Die Datenbank enthält schreibgeschützte oder komprimierte Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-115">Any read-only or compressed filegroups exist in the database.</span></span>  
  
-   <span data-ttu-id="70d0b-116">Alle Dateien sind nun offline, waren jedoch beim Erstellen der Momentaufnahme online.</span><span class="sxs-lookup"><span data-stu-id="70d0b-116">Any files are now offline but were online when the snapshot was created.</span></span>  
  
 <span data-ttu-id="70d0b-117">Beachten Sie folgende Einschränkungen, bevor Sie eine Wiederherstellung aus einer Datenbank-Momentaufnahme ausführen:</span><span class="sxs-lookup"><span data-stu-id="70d0b-117">Before reverting a database, consider the following limitations:</span></span>  
  
-   <span data-ttu-id="70d0b-118">Die Wiederherstellung bezieht sich nicht auf die Wiederherstellung von Medien.</span><span class="sxs-lookup"><span data-stu-id="70d0b-118">Reverting is not intended for media recovery.</span></span> <span data-ttu-id="70d0b-119">.</span><span class="sxs-lookup"><span data-stu-id="70d0b-119">.</span></span> <span data-ttu-id="70d0b-120">Eine Datenbank-Momentaufnahme ist eine unvollständige Kopie der Datenbankdateien. Wenn also die Datenbank oder die Datenbank-Momentaufnahme beschädigt wurde, ist die Wiederherstellung aus einer Momentaufnahme wahrscheinlich unmöglich.</span><span class="sxs-lookup"><span data-stu-id="70d0b-120">A database snapshot is an incomplete copy of the database files, so if either the database or the database snapshot is corrupted, reverting from a snapshot is likely to be impossible.</span></span> <span data-ttu-id="70d0b-121">Zudem ist es eher unwahrscheinlich, dass das Problem durch eine Wiederherstellung im Falle einer Beschädigung behoben wird, selbst wenn eine Wiederherstellung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="70d0b-121">Furthermore, even when it is possible, reverting in the event of corruption is unlikely to correct the problem.</span></span> <span data-ttu-id="70d0b-122">Regelmäßige Sicherungen und Tests des Wiederherstellungsplans sind deshalb für den Schutz einer Datenbank unverzichtbar.</span><span class="sxs-lookup"><span data-stu-id="70d0b-122">Therefore, taking regular backups and testing your restore plan are essential to protect a database.</span></span> <span data-ttu-id="70d0b-123">Weitere Informationen finden Sie unter [Sichern und Wiederherstellen von SQL Server-Datenbanken](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-123">For more information, see [Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70d0b-124">Wenn Sie die Quelldatenbank zu dem Zeitpunkt wiederherstellen müssen, an dem Sie eine Datenbank-Momentaufnahme erstellt haben, nutzen Sie das Modell der vollständigen Wiederherstellung, und implementieren Sie eine Sicherungsrichtlinie, die Ihnen dies ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="70d0b-124">If you need to be able to restore the source database to the point in time at which you created a database snapshot, use the full recovery model and implement a backup policy that enables you to do that.</span></span>  
  
-   <span data-ttu-id="70d0b-125">Die ursprüngliche Quelldatenbank wird von der wiederhergestellten Datenbank überschrieben, sodass sämtliche Aktualisierungen der Datenbank seit der Erstellung der Momentaufnahme verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-125">The original source database is overwritten by the reverted database, so any updates to the database since the snapshot's creation are lost.</span></span>  
  
-   <span data-ttu-id="70d0b-126">Die bisherige Protokolldatei wird bei der Wiederherstellung ebenfalls überschrieben, und das Protokoll wird neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="70d0b-126">The revert operation also overwrites the old log file and rebuilds the log.</span></span> <span data-ttu-id="70d0b-127">Daher ist kein Rollforward der wiederhergestellten Datenbank bis zum Zeitpunkt des Benutzerfehlers möglich.</span><span class="sxs-lookup"><span data-stu-id="70d0b-127">Consequently, you cannot roll the reverted database forward to the point of user error.</span></span> <span data-ttu-id="70d0b-128">Es empfiehlt sich somit, dass Sie das Protokoll vor dem Wiederherstellen einer Datenbank sichern.</span><span class="sxs-lookup"><span data-stu-id="70d0b-128">Therefore, we recommend that you back up the log before reverting a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70d0b-129">Es ist zwar nicht möglich, das ursprüngliche Protokoll wiederherzustellen und damit ein Rollforward der Datenbank auszuführen. Die Angaben in der ursprünglichen Protokolldatei können jedoch beim Rekonstruieren verlorener Daten helfen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-129">Although you cannot restore the original log to roll forward the database, the information in the original log file can be useful for reconstructing lost data.</span></span>  
  
-   <span data-ttu-id="70d0b-130">Durch Zurückkehren wird die Protokollsicherungskette unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-130">Reverting breaks the log backup chain.</span></span> <span data-ttu-id="70d0b-131">Bevor Sie also eine Protokollsicherung der Datenbank anfertigen können, muss daher eine vollständige Datenbank- oder Dateisicherung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-131">Therefore, before you can take log backups of the reverted database, you must first take a full database backup or file backup.</span></span> <span data-ttu-id="70d0b-132">Wir empfehlen eine vollständige Datenbanksicherung.</span><span class="sxs-lookup"><span data-stu-id="70d0b-132">We recommend a full database backup.</span></span>  
  
-   <span data-ttu-id="70d0b-133">Während des Zurückkehrens sind sowohl die Momentaufnahme als auch die Quelldatenbank nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="70d0b-133">During a revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="70d0b-134">Die Quelldatenbank und die Momentaufnahme sind jeweils gekennzeichnet, dass derzeit eine Wiederherstellung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="70d0b-134">The source database and snapshot are both marked "In restore."</span></span> <span data-ttu-id="70d0b-135">Tritt ein Fehler beim Zurückkehren auf, wird beim Neustart der Datenbank versucht, das Zurückkehren abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-135">If an error occurs during the revert operation, when the database starts up again, the revert operation will try to finish reverting.</span></span>  
  
-   <span data-ttu-id="70d0b-136">Die Metadaten einer Datenbank nach dem Zurückkehren entsprechen den Metadaten zum Zeitpunkt der Momentaufnahme.</span><span class="sxs-lookup"><span data-stu-id="70d0b-136">The metadata of a reverted database is the same as the metadata at the time of the snapshot.</span></span>  
  
-   <span data-ttu-id="70d0b-137">Durch das Wiederherstellen werden alle Volltextkataloge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="70d0b-137">Reverting drops all the full-text catalogs.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="70d0b-138">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="70d0b-138">Prerequisites</span></span>  
 <span data-ttu-id="70d0b-139">Stellen Sie sicher, dass die Quelldatenbank und die Datenbank-Momentaufnahme die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="70d0b-139">Ensure that the source database and database snapshot meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="70d0b-140">Vergewissern Sie sich, dass die Datenbank nicht beschädigt wurde.</span><span class="sxs-lookup"><span data-stu-id="70d0b-140">Verify that the database has not become corrupted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70d0b-141">Wenn die Datenbank beschädigt wurde, müssen Sie sie aus einer Sicherungskopie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-141">If the database has been corrupted, you will need to restore it from backups.</span></span> <span data-ttu-id="70d0b-142">Weitere Informationen finden Sie unter [Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) oder [Vollständige Datenbankwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-142">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span></span>  
  
-   <span data-ttu-id="70d0b-143">Ermitteln Sie eine aktuelle Momentaufnahme, die vor Auftreten des Fehlers erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="70d0b-143">Identify a recent snapshot that was created before the error.</span></span> <span data-ttu-id="70d0b-144">Weitere Informationen finden Sie unter [Anzeigen einer Datenbankmomentaufnahme &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)anzeigen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-144">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
-   <span data-ttu-id="70d0b-145">Löschen Sie alle anderen Momentaufnahmen, die derzeit für die Datenbank vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="70d0b-145">Drop any other snapshots that currently exist on the database.</span></span> <span data-ttu-id="70d0b-146">Weitere Informationen finden Sie unter [Löschen einer Datenbank-Momentaufnahme &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md)angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="70d0b-146">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="70d0b-147">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="70d0b-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="70d0b-148">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="70d0b-148">Permissions</span></span>  
 <span data-ttu-id="70d0b-149">Alle Benutzer, die über RESTORE DATABASE-Berechtigungen für die Quelldatenbank verfügen, können diese in dem Zustand zum Zeitpunkt der Erstellung der Datenbank-Momentaufnahme wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-149">Any user who has RESTORE DATABASE permissions on the source database can revert it to its state when a database snapshot was created.</span></span>  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="70d0b-150">So stellen Sie eine Datenbank aus einer Datenbank-Momentaufnahme wieder her (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="70d0b-150">How to Revert a Database to a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="70d0b-151">**So stellen Sie eine Datenbank aus zu einer Datenbank-Momentaufnahme wieder her**</span><span class="sxs-lookup"><span data-stu-id="70d0b-151">**To revert a database to a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70d0b-152">Ein Beispiel für diese Prozedur finden Sie in [Beispiele (Transact-SQL)](#TsqlExample)an späterer Stelle in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="70d0b-152">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="70d0b-153">Ermitteln Sie die Datenbank-Momentaufnahme, aus der Sie die Datenbank wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="70d0b-153">Identify the database snapshot to which you want to revert the database.</span></span> <span data-ttu-id="70d0b-154">Sie können die Momentaufnahmen für eine Datenbank in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] anzeigen (weitere Informationen finden Sie unter [Anzeigen einer Datenbankmomentaufnahme &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="70d0b-154">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span></span> <span data-ttu-id="70d0b-155">Zudem können Sie die Quelldatenbank einer Sicht anhand der **source_database_id** -Spalte der [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) -Katalogsicht identifizieren.</span><span class="sxs-lookup"><span data-stu-id="70d0b-155">Also, you can identify the source database of a view from the **source_database_id** column of the [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
2.  <span data-ttu-id="70d0b-156">Löschen Sie alle anderen Datenbankmomentaufnahmen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-156">Drop any other database snapshots.</span></span>  
  
     <span data-ttu-id="70d0b-157">Informationen zum Löschen von Momentaufnahmen finden Sie unter [Löschen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-157">For information on dropping snapshots, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span> <span data-ttu-id="70d0b-158">Verwendet die Datenbank das vollständige Wiederherstellungsmodell sollten Sie das Protokoll vor dem Wiederherstellen sichern.</span><span class="sxs-lookup"><span data-stu-id="70d0b-158">If the database uses the full recovery model, before reverting, you should back up the log.</span></span> <span data-ttu-id="70d0b-159">Weitere Informationen finden Sie unter [Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) oder [Sichern des Transaktionsprotokolls bei beschädigter Datenbank &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-159">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) or [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="70d0b-160">Führen Sie den Wiederherstellungsvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="70d0b-160">Perform the revert operation.</span></span>  
  
     <span data-ttu-id="70d0b-161">Für einen Wiederherstellungsvorgang sind RESTORE DATABASE-Berechtigungen für die Quelldatenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70d0b-161">A revert operation requires RESTORE DATABASE permissions on the source database.</span></span> <span data-ttu-id="70d0b-162">Verwenden Sie zum Wiederherstellen der Datenbank die folgende Transact-SQL-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="70d0b-162">To revert the database, use the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="70d0b-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=** _database_snapshot_name_</span><span class="sxs-lookup"><span data-stu-id="70d0b-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_</span></span>  
  
     <span data-ttu-id="70d0b-164">Dabei ist *database_name* die Quelldatenbank und *database_snapshot_name* der Name der Momentaufnahmen, aus dem die Datenbank wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="70d0b-164">Where *database_name* is the source database and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="70d0b-165">Beachten Sie, dass Sie in dieser Anweisung einen Momentaufnahmenamen statt eines Sicherungsmediums angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-165">Notice that in this statement, you must specify a snapshot name rather than a backup device.</span></span>  
  
     <span data-ttu-id="70d0b-166">Weitere Informationen finden Sie unter [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="70d0b-166">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70d0b-167">Während des Wiederherstellungsvorgangs stehen weder die Momentaufnahme noch die Quelldatenbank zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="70d0b-167">During the revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="70d0b-168">Die Quelldatenbank und die Momentaufnahme sind als von einem Wiederherstellungsvorgang betroffen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="70d0b-168">The source database and snapshot are both marked as "In restore."</span></span> <span data-ttu-id="70d0b-169">Falls während der Wiederherstellung ein Fehler auftritt, wird beim nächsten Start der Datenbank versucht, die Wiederherstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="70d0b-169">If an error occurs during the revert operation, it will try to finish reverting when the database starts up again.</span></span>  
  
4.  <span data-ttu-id="70d0b-170">Hat sich seit der Erstellung der Datenbankmomentaufnahme der Datenbankbesitzer geändert, ist es möglicherweise sinnvoll, den Datenbankbesitzer der wiederhergestellten Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="70d0b-170">If the database owner changed since creation of the database snapshot, you may want to update the database owner of the reverted database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70d0b-171">In der wiederhergestellten Datenbank bleiben die Berechtigungen und die Konfiguration (wie z. B. Datenbankbesitzer und Wiederherstellungsmodell) der Datenbankmomentaufnahme erhalten.</span><span class="sxs-lookup"><span data-stu-id="70d0b-171">The reverted database retains the permissions and configuration (such as database owner and recovery model) of the database snapshot.</span></span>  
  
5.  <span data-ttu-id="70d0b-172">Starten Sie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="70d0b-172">Start the database.</span></span>  
  
6.  <span data-ttu-id="70d0b-173">Sie haben die Option, die wiederhergestellte Datenbank zu sichern; dies empfiehlt sich besonders, wenn das vollständige (oder das massenprotokollierte) Wiederherstellungsmodell für die Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70d0b-173">Optionally, back up the reverted database, especially if it uses the full (or bulk-logged) recovery model.</span></span> <span data-ttu-id="70d0b-174">Weitere Informationen zum Sichern einer Datenbank finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-174">To back up a database, see [Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="70d0b-175">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="70d0b-175">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="70d0b-176">Dieser Abschnitt enthält die folgenden Beispiele für das Wiederherstellen einer Datenbank aus einer Datenbank-Momentaufnahme:</span><span class="sxs-lookup"><span data-stu-id="70d0b-176">This section contains the following examples of reverting a database to a database snapshot:</span></span>  
  
-   <span data-ttu-id="70d0b-177">A.</span><span class="sxs-lookup"><span data-stu-id="70d0b-177">A.</span></span> [<span data-ttu-id="70d0b-178">Wiederherstellen einer Momentaufnahme für die AdventureWorks-Datenbank</span><span class="sxs-lookup"><span data-stu-id="70d0b-178">Reverting a snapshot on the AdventureWorks database</span></span>](#Reverting_AW)  
  
-   <span data-ttu-id="70d0b-179">B.</span><span class="sxs-lookup"><span data-stu-id="70d0b-179">B.</span></span> [<span data-ttu-id="70d0b-180">Wiederherstellen einer Momentaufnahme für die Sales-Datenbank</span><span class="sxs-lookup"><span data-stu-id="70d0b-180">Reverting a snapshot on the Sales database</span></span>](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> <span data-ttu-id="70d0b-181">A.</span><span class="sxs-lookup"><span data-stu-id="70d0b-181">A.</span></span> <span data-ttu-id="70d0b-182">Wiederherstellen einer Momentaufnahme für die AdventureWorks-Datenbank</span><span class="sxs-lookup"><span data-stu-id="70d0b-182">Reverting a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="70d0b-183">In diesem Beispiel wird davon ausgegangen, dass derzeit in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank nur eine Momentaufnahme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="70d0b-183">This example assumes that only one snapshot currently exists on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="70d0b-184">Das Beispiel, mit dem die Momentaufnahme erstellt wird, zu dem die Datenbank hier wiederhergestellt wird, finden Sie unter [Erstellen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-184">For the example that creates the snapshot to which the database is reverted here, see [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> <span data-ttu-id="70d0b-185">B.</span><span class="sxs-lookup"><span data-stu-id="70d0b-185">B.</span></span> <span data-ttu-id="70d0b-186">Wiederherstellen einer Momentaufnahme für die Sales-Datenbank</span><span class="sxs-lookup"><span data-stu-id="70d0b-186">Reverting a snapshot on the Sales database</span></span>  
 <span data-ttu-id="70d0b-187">In diesem Beispiel wird davon ausgegangen, dass derzeit zwei Momentaufnahmen für die **Sales** -Datenbank vorhanden sind: **sales_snapshot0600** und **sales_snapshot1200**.</span><span class="sxs-lookup"><span data-stu-id="70d0b-187">This example assumes that two snapshots currently exist on the **Sales** database: **sales_snapshot0600** and **sales_snapshot1200**.</span></span> <span data-ttu-id="70d0b-188">Durch dieses Beispiel wird die ältere Momentaufnahme gelöscht und die Datenbank mithilfe der aktuelleren Momentaufnahme wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="70d0b-188">The example deletes the older of the snapshots and reverts the database to the more recent snapshot.</span></span>  
  
 <span data-ttu-id="70d0b-189">Den Code zum Erstellen der Beispieldatenbank und der Momentaufnahmen, für die dieses Beispiel gilt, finden Sie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="70d0b-189">For the code for creating the sample database and snapshots on which this example depends, see:</span></span>  
  
-   <span data-ttu-id="70d0b-190">Informationen zur **Sales**-Datenbank und zur **sales_snapshot0600**-Momentaufnahme finden Sie in „Erstellen einer Datenbank mit Dateigruppen“ und „Erstellen einer Datenbankmomentaufnahme“ in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70d0b-190">For the **Sales** database and the **sales_snapshot0600** snapshot, see "Creating a database with filegroups" and "Creating a database snapshot" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
-   <span data-ttu-id="70d0b-191">Informationen zur **sales_snapshot1200** -Momentaufnahme finden Sie unter „Erstellen einer Momentaufnahme für die Sales-Datenbank“ in [Erstellen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="70d0b-191">For the **sales_snapshot1200** snapshot, see "Creating a snapshot on the Sales database" in [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="70d0b-192">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="70d0b-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="70d0b-193">Erstellen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="70d0b-193">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="70d0b-194">Anzeigen einer Datenbank-Momentaufnahme &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="70d0b-194">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="70d0b-195">Löschen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="70d0b-195">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="70d0b-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70d0b-196">See Also</span></span>  
 <span data-ttu-id="70d0b-197">[Datenbank-Momentaufnahmen &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="70d0b-197">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="70d0b-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="70d0b-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="70d0b-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="70d0b-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="70d0b-200">Datenbankspiegelung und Datenbankmomentaufnahmen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="70d0b-200">Database Mirroring and Database Snapshots &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
  
