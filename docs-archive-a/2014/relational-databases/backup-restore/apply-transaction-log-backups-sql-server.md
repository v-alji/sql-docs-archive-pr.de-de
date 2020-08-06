---
title: Anwenden von Transaktionsprotokollsicherungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], log backups
- transaction log backups [SQL Server], applying backups
- online restores [SQL Server], log backups
- transaction log backups [SQL Server], quantity needed for restore sequence
- backups [SQL Server], log backups
ms.assetid: 9b12be51-5469-46f9-8e86-e938e10aa3a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54c91106f8ca6f15539b4103220860143882c3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617141"
---
# <a name="apply-transaction-log-backups-sql-server"></a><span data-ttu-id="56887-102">Anwenden von Transaktionsprotokollsicherungen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="56887-102">Apply Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="56887-103">Dieses Thema ist nur für das vollständige und für das massenprotokollierte Wiederherstellungsmodell relevant.</span><span class="sxs-lookup"><span data-stu-id="56887-103">The topic is relevant only for the full recovery model or bulk-logged recovery model.</span></span>  
  
 <span data-ttu-id="56887-104">In diesem Thema wird das Anwenden von Transaktionsprotokollsicherungen als Bestandteil der Wiederherstellung einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank erläutert.</span><span class="sxs-lookup"><span data-stu-id="56887-104">This topic describes applying transaction log backups as part of restoring a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="56887-105">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="56887-105">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="56887-106">Anforderungen für die Wiederherstellung von Transaktionsprotokoll Sicherungen</span><span class="sxs-lookup"><span data-stu-id="56887-106">Requirements for Restoring Transaction Log Backups</span></span>](#Requirements)  
  
-   [<span data-ttu-id="56887-107">Wiederherstellungs-und Transaktionsprotokolle</span><span class="sxs-lookup"><span data-stu-id="56887-107">Recovery and Transaction Logs</span></span>](#RecoveryAndTlogs)  
  
-   [<span data-ttu-id="56887-108">Verwenden von Protokollsicherungen zum Wiederherstellen des Zustands vor dem Fehler</span><span class="sxs-lookup"><span data-stu-id="56887-108">Using Log Backups to Restore to the Point of Failure</span></span>](#PITrestore)  
  
-   [<span data-ttu-id="56887-109">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="56887-109">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="requirements-for-restoring-transaction-log-backups"></a><a name="Requirements"></a><span data-ttu-id="56887-110">Anforderungen für die Wiederherstellung von Transaktionsprotokoll Sicherungen</span><span class="sxs-lookup"><span data-stu-id="56887-110">Requirements for Restoring Transaction Log Backups</span></span>  
 <span data-ttu-id="56887-111">Für das Anwenden einer Transaktionsprotokollsicherung müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="56887-111">To apply a transaction log backup, the following requirements must be met:</span></span>  
  
-   <span data-ttu-id="56887-112">**Ausreichende Protokollsicherungen für eine Wiederherstellungssequenz:** Es müssen ausreichend Protokolldatensätze gesichert sein, damit eine Wiederherstellungssequenz abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="56887-112">**Enough Log Backups for a Restore Sequence :** You must have enough log records backed up to complete a restore sequence.</span></span> <span data-ttu-id="56887-113">Die erforderlichen Protokollsicherungen (einschließlich der [Sicherung des Protokollfragments](tail-log-backups-sql-server.md) , sofern erforderlich) müssen vor dem Start einer Wiederherstellungssequenz zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="56887-113">The necessary log backups, including the [tail-log backup](tail-log-backups-sql-server.md) where required, must be available before the start of the restore sequence.</span></span>  
  
-   <span data-ttu-id="56887-114">**Richtige Wiederherstellungsreihenfolge:**  Als Erstes muss die unmittelbar vorherige vollständige oder differenzielle Datenbanksicherung wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="56887-114">**Correct restore order:**  The immediately previous full database backup or differential database backup must be restored first.</span></span> <span data-ttu-id="56887-115">Alle nach dieser vollständigen oder differenziellen Datenbanksicherung erstellten Transaktionsprotokolle müssen dann in chronologischer Reihenfolge wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="56887-115">Then, all transaction logs that are created after that full or differential database backup must be restored in chronological order.</span></span> <span data-ttu-id="56887-116">Wenn eine Transaktionsprotokollsicherung in dieser Protokollkette verloren gegangen oder beschädigt ist, können Sie nur Transaktionsprotokolle vor dem fehlenden wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="56887-116">If a transaction log backup in this log chain is lost or damaged, you can restore only transaction logs before the missing transaction log.</span></span>  
  
-   <span data-ttu-id="56887-117">**Datenbank noch nicht wiederhergestellt:**  Die Datenbank kann erst wiederhergestellt werden, nachdem das letzte Transaktionsprotokoll angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="56887-117">**Database not yet recovered:**  The database cannot be recovered until after the final transaction log has been applied.</span></span> <span data-ttu-id="56887-118">Wenn Sie die Datenbank nach dem Wiederherstellen einer der Zwischen-Transaktionsprotokollsicherungen (einer Sicherung vor dem Ende der Protokollkette) wiederherstellen, können Sie die Datenbank nicht zu einem späteren Zeitpunkt als diesem wiederherstellen, ohne die gesamte Wiederherstellungssequenz, beginnend mit der vollständigen Datenbanksicherung, neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="56887-118">If you recover the database after restoring one of the intermediate transaction log backups, that before the end of the log chain, you cannot restore the database past that point without restarting the complete restore sequence, starting with the full database backup.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="56887-119">Eine bewährte Methode besteht darin, alle Protokollsicherungen (RESTORE LOG *Datenbankname* WITH NORECOVERY) wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="56887-119">A best practice is to restore all the log backups (RESTORE LOG *database_name* WITH NORECOVERY).</span></span> <span data-ttu-id="56887-120">Stellen Sie nach dem Wiederherstellen der letzten Protokollsicherung die Datenbank in einem separaten Vorgang (RESTORE DATABASE *Datenbankname* WITH RECOVERY) wieder her.</span><span class="sxs-lookup"><span data-stu-id="56887-120">Then, after restoring the last log backup, recover the database in a separate operation (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span>  
  
##  <a name="recovery-and-transaction-logs"></a><a name="RecoveryAndTlogs"></a><span data-ttu-id="56887-121">Wiederherstellungs-und Transaktionsprotokolle</span><span class="sxs-lookup"><span data-stu-id="56887-121">Recovery and Transaction Logs</span></span>  
 <span data-ttu-id="56887-122">Wenn Sie den Wiederherstellungsvorgang abschließen und die Datenbank wiederherstellen, wird während der Wiederherstellung für alle unvollständigen Transaktionen ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56887-122">When you finish the restore operation and recover the database, recovery rolls back all incomplete transactions.</span></span> <span data-ttu-id="56887-123">Dies wird als *Rollbackphase*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="56887-123">This is known as the *undo phase*.</span></span> <span data-ttu-id="56887-124">Das Rollback ist erforderlich, um die Integrität der Datenbank wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="56887-124">Rolling back is required to restore the integrity of the database.</span></span> <span data-ttu-id="56887-125">Nach dem Rollback wird die Datenbank online geschaltet, und es können keine weiteren Transaktionsprotokollsicherungen auf die Datenbank angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="56887-125">After rollback, the database goes online, and no more transaction log backups can be applied to the database.</span></span>  
  
 <span data-ttu-id="56887-126">So kann z. B. eine Reihe von Transaktionsprotokollsicherungen eine lang andauernde Transaktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="56887-126">For example, a series of transaction log backups contain a long-running transaction.</span></span> <span data-ttu-id="56887-127">Der Start der Transaktion wird in der ersten Transaktionsprotokollsicherung, das Ende der Transaktion jedoch in der zweiten Transaktionsprotokollsicherung aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="56887-127">The start of the transaction is recorded in the first transaction log backup, but the end of the transaction is recorded in the second transaction log backup.</span></span> <span data-ttu-id="56887-128">Es gibt keinen Datensatz für einen Commit- oder Rollbackvorgang in der ersten Transaktionsprotokollsicherung.</span><span class="sxs-lookup"><span data-stu-id="56887-128">There is no record of a commit or rollback operation in the first transaction log backup.</span></span> <span data-ttu-id="56887-129">Wenn ein Wiederherstellungsvorgang nach dem Anwenden der ersten Transaktionsprotokollsicherung ausgeführt wird, wird die lang andauernde Transaktion als unvollständig behandelt, und für die in der ersten Transaktionsprotokollsicherung aufgezeichneten Datenänderungen dieser Transaktion wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56887-129">If a recovery operation runs when the first transaction log backup is applied, the long-running transaction is treated as incomplete, and data modifications recorded in the first transaction log backup for the transaction are rolled back.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="56887-130">ist das Anwenden einer zweiten Transaktionsprotokollsicherung nach diesem Zeitpunkt nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="56887-130">does not allow for the second transaction log backup to be applied after this point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56887-131">Unter bestimmten Umständen können Sie eine Datei während der Protokollwiederherstellung explizit hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56887-131">In some circumstances, you can explicitly add a file during log restore.</span></span>  
  
##  <a name="using-log-backups-to-restore-to-the-point-of-failure"></a><a name="PITrestore"></a><span data-ttu-id="56887-132">Verwenden von Protokoll Sicherungen zur Wiederherstellung bis zum Zeitpunkt des Fehlers</span><span class="sxs-lookup"><span data-stu-id="56887-132">Using Log Backups to Restore to the Point of Failure</span></span>  
 <span data-ttu-id="56887-133">Nehmen Sie die folgende Ereignissequenz an.</span><span class="sxs-lookup"><span data-stu-id="56887-133">Assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="56887-134">Time</span><span class="sxs-lookup"><span data-stu-id="56887-134">Time</span></span>|<span data-ttu-id="56887-135">Ereignis</span><span class="sxs-lookup"><span data-stu-id="56887-135">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="56887-136">8:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-136">8:00 A.M.</span></span>|<span data-ttu-id="56887-137">Sichern der Datenbank zum Erstellen einer vollständigen Datenbanksicherung.</span><span class="sxs-lookup"><span data-stu-id="56887-137">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="56887-138">12:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-138">Noon</span></span>|<span data-ttu-id="56887-139">Sichern des Transaktionsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="56887-139">Back up transaction log.</span></span>|  
|<span data-ttu-id="56887-140">16:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-140">4:00 P.M.</span></span>|<span data-ttu-id="56887-141">Sichern des Transaktionsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="56887-141">Back up transaction log.</span></span>|  
|<span data-ttu-id="56887-142">18:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-142">6:00 P.M.</span></span>|<span data-ttu-id="56887-143">Sichern der Datenbank zum Erstellen einer vollständigen Datenbanksicherung.</span><span class="sxs-lookup"><span data-stu-id="56887-143">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="56887-144">20:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-144">8:00 P.M.</span></span>|<span data-ttu-id="56887-145">Sichern des Transaktionsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="56887-145">Back up transaction log.</span></span>|  
|<span data-ttu-id="56887-146">21:45 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-146">9:45 P.M.</span></span>|<span data-ttu-id="56887-147">Fehler tritt auf.</span><span class="sxs-lookup"><span data-stu-id="56887-147">Failure occurs.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="56887-148">Eine Erklärung dieser Beispielsequenz von Sicherungen finden Sie unter [Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="56887-148">For an explanation of this example sequence of backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="56887-149">Zum Wiederherstellen des Datenbankzustands von 21:45 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-149">To restore the database to its state at 9:45 P.M.</span></span> <span data-ttu-id="56887-150">(Zeitpunkt des Fehlers) kann eines der folgenden Verfahren verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="56887-150">(the point of failure), either of the following alternative procedures can be used:</span></span>  
  
 <span data-ttu-id="56887-151">**Alternative 1: Wiederherstellen der Datenbank mithilfe der letzten vollständigen Datenbanksicherung**</span><span class="sxs-lookup"><span data-stu-id="56887-151">**Alternative 1: Restore the database by using the most recent full database backup**</span></span>  
  
1.  <span data-ttu-id="56887-152">Erstellen Sie eine Sicherung des Protokollfragments des aktuell aktiven Transaktionsprotokolls zum Zeitpunkt des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="56887-152">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="56887-153">Stellen Sie nicht die vollständige Datenbanksicherung von 8:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-153">Do not restore the 8:00 A.M.</span></span> <span data-ttu-id="56887-154">von 18:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="56887-154">full database backup.</span></span> <span data-ttu-id="56887-155">Stellen Sie stattdessen die neuere vollständige Datenbanksicherung von 18:00 Uhr wieder her,</span><span class="sxs-lookup"><span data-stu-id="56887-155">Instead, restore the more recent 6:00 P.M.</span></span> <span data-ttu-id="56887-156">und wenden Sie dann die Transaktionsprotokollsicherung von 20:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-156">full database backup, and then apply the 8:00 P.M.</span></span> <span data-ttu-id="56887-157">und die Sicherung des Protokollfragments an.</span><span class="sxs-lookup"><span data-stu-id="56887-157">log backup and the tail-log backup.</span></span>  
  
 <span data-ttu-id="56887-158">**Alternative 2: Wiederherstellen der Datenbank mithilfe einer früheren vollständigen Datenbanksicherung**</span><span class="sxs-lookup"><span data-stu-id="56887-158">**Alternative 2: Restore the database by using an earlier full database backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56887-159">Dieser alternative Vorgang ist nützlich, wenn Sie aufgrund eines Problems die vollständige Datenbanksicherung von 18:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-159">This alternative process is useful if a problem prevents you from using the 6:00 P.M.</span></span> <span data-ttu-id="56887-160">von 18:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="56887-160">full database backup.</span></span> <span data-ttu-id="56887-161">Dieser Vorgang dauert länger als das Wiederherstellen der vollständigen Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="56887-161">This process takes longer than restoring from the 6:00 P.M.</span></span> <span data-ttu-id="56887-162">von 18:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="56887-162">full database backup.</span></span>  
  
1.  <span data-ttu-id="56887-163">Erstellen Sie eine Sicherung des Protokollfragments des aktuell aktiven Transaktionsprotokolls zum Zeitpunkt des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="56887-163">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="56887-164">Stellen Sie die vollständige Datenbanksicherung von 8:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="56887-164">Restore the 8:00 A.M.</span></span> <span data-ttu-id="56887-165">und anschließend alle vier Transaktionsprotokollsicherungen in der chronologischen Reihenfolge wieder her.</span><span class="sxs-lookup"><span data-stu-id="56887-165">full database backup, and then restore all four transaction log backups in sequence.</span></span> <span data-ttu-id="56887-166">Dadurch wird ein Rollforward für alle abgeschlossenen Transaktionen bis 21:45 Uhr ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56887-166">This rolls forward all completed transactions up to 9:45 P.M.</span></span>  
  
     <span data-ttu-id="56887-167">Diese Alternative verdeutlicht, welche redundante Sicherheit eine zwischen eine Folge vollständiger Datenbanksicherungen geschaltete Kette von Transaktionsprotokollsicherungen bietet.</span><span class="sxs-lookup"><span data-stu-id="56887-167">This alternative points out the redundant security offered by maintaining a chain of transaction log backups across a series of full database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56887-168">In einigen Fällen können Sie auch mit Transaktionsprotokollen eine Datenbank zu einem bestimmten Zeitpunkt wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="56887-168">In some cases, you can also use transaction logs to restore a database to a specific point in time.</span></span> <span data-ttu-id="56887-169">Informationen finden Sie unter [Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="56887-169">For more information, [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="56887-170">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="56887-170">Related Tasks</span></span>  
 <span data-ttu-id="56887-171">**So wenden Sie eine Transaktionsprotokollsicherung an**</span><span class="sxs-lookup"><span data-stu-id="56887-171">**To apply a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="56887-172">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="56887-172">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="56887-173">**So stellen Sie einen Wiederherstellungspunkt wieder her**</span><span class="sxs-lookup"><span data-stu-id="56887-173">**To restore to your recovery point**</span></span>  
  
-   [<span data-ttu-id="56887-174">Wiederherstellen einer Datenbank bis zum Fehlerzeitpunkt im vollständigen Wiederherstellungsmodell &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="56887-174">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="56887-175">Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="56887-175">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   <span data-ttu-id="56887-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="56887-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
-   [<span data-ttu-id="56887-177">Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion</span><span class="sxs-lookup"><span data-stu-id="56887-177">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="56887-178">Wiederherstellen zu einer Protokollfolgenummer &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="56887-178">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
 <span data-ttu-id="56887-179">**So stellen Sie eine Datenbank wieder her, nachdem Sie Sicherungen mit WITH NORECOVERY wiederhergestellt haben**</span><span class="sxs-lookup"><span data-stu-id="56887-179">**To recover a database after restoring backups using WITH NORECOVERY**</span></span>  
  
-   [<span data-ttu-id="56887-180">Wiederherstellen einer Datenbank ohne Wiederherstellung von Daten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="56887-180">Recover a Database Without Restoring Data &#40;Transact-SQL&#41;</span></span>](recover-a-database-without-restoring-data-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="56887-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56887-181">See Also</span></span>  
 [<span data-ttu-id="56887-182">Das Transaktionsprotokoll &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="56887-182">The Transaction Log &#40;SQL Server&#41;</span></span>](../logs/the-transaction-log-sql-server.md)  
  
  
