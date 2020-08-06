---
title: Problembehandlung bei vollen Transaktionsprotokollen (SQL Server-Fehler 9002) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], full
- troubleshooting [SQL Server], full transaction log
- 9002 (Database Engine error)
- transaction logs [SQL Server], truncation
- backing up transaction logs [SQL Server], full logs
- transaction logs [SQL Server], full log
- full transaction logs [SQL Server]
ms.assetid: 0f23aa84-475d-40df-bed3-c923f8c1b520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d03e259bd0aff8fce02558dbe08efb56748493c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608637"
---
# <a name="troubleshoot-a-full-transaction-log-sql-server-error-9002"></a><span data-ttu-id="c26a3-102">Problembehandlung bei vollen Transaktionsprotokollen (SQL Server-Fehler 9002)</span><span class="sxs-lookup"><span data-stu-id="c26a3-102">Troubleshoot a Full Transaction Log (SQL Server Error 9002)</span></span>
  <span data-ttu-id="c26a3-103">In diesem Thema werden mögliche Lösungen für volle Transaktionsprotokolle erörtert und Vermeidungsstrategien vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="c26a3-103">This topic discusses possible responses to a full transaction log and suggests how to avoid it in the future.</span></span> <span data-ttu-id="c26a3-104">Wenn das Transaktionsprotokoll voll ist, wird von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] der Fehler 9002 ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c26a3-104">When the transaction log becomes full, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] issues a 9002 error.</span></span> <span data-ttu-id="c26a3-105">Das Protokoll kann sich füllen, wenn die Datenbank online ist oder wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c26a3-105">The log can fill when the database is online or in recovery.</span></span> <span data-ttu-id="c26a3-106">Falls das Protokoll während des Onlinezustands der Datenbank voll ist, bleibt die Datenbank online, aber sie kann nur gelesen und nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c26a3-106">If the log fills while the database is online, the database remains online but can only be read, not updated.</span></span> <span data-ttu-id="c26a3-107">Wird das Protokoll während einer Wiederherstellung gefüllt, wird die Datenbank von [!INCLUDE[ssDE](../../includes/ssde-md.md)] als RESOURCE PENDING (ausstehende Ressource) markiert.</span><span class="sxs-lookup"><span data-stu-id="c26a3-107">If the log fills during recovery, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] marks the database as RESOURCE PENDING.</span></span> <span data-ttu-id="c26a3-108">In beiden Fällen ist eine Aktion seitens des Benutzers erforderlich, um Speicherplatz im Protokoll verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c26a3-108">In either case, user action is required to make log space available.</span></span>  
  
## <a name="responding-to-a-full-transaction-log"></a><span data-ttu-id="c26a3-109">Mögliche Vorgehensweisen bei einem vollen Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="c26a3-109">Responding to a Full Transaction Log</span></span>  
 <span data-ttu-id="c26a3-110">Die richtige Reaktion auf ein volles Transaktionsprotokoll hängt zum Teil davon ab, aufgrund welcher Bedingungen das Protokoll gefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="c26a3-110">The appropriate response to a full transaction log depends partly on what condition or conditions caused the log to fill.</span></span> <span data-ttu-id="c26a3-111">Mithilfe der Spalten **log_reuse_wait** und **log_reuse_wait_desc** der **sys.database**-Katalogsicht können Sie feststellen, wodurch eine Protokollkürzung verhindert wurde.</span><span class="sxs-lookup"><span data-stu-id="c26a3-111">To discover what is preventing log truncation in a given case, use the **log_reuse_wait** and **log_reuse_wait_desc** columns of the **sys.database** catalog view.</span></span> <span data-ttu-id="c26a3-112">Weitere Informationen finden Sie unter [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c26a3-112">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span> <span data-ttu-id="c26a3-113">Eine Beschreibung von Faktoren, die eine Protokollkürzung verzögern können, finden Sie unter [Das Transaktionsprotokoll &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c26a3-113">For descriptions of factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c26a3-114">Wenn sich die Datenbank zu dem Zeitpunkt, als der Fehler 9002 auftrat, gerade im Wiederherstellungsmodus befand, müssen Sie nach Behebung des Problems die Datenbank mithilfe von ALTER DATABASE *database_name* SET ONLINE wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="c26a3-114">If the database was in recovery when the 9002 error occurred, after resolving the problem, recover the database by using ALTER DATABASE *database_name* SET ONLINE.</span></span>  
  
 <span data-ttu-id="c26a3-115">Alternativ sind als Reaktion auf ein volles Transaktionsprotokoll auch folgende Aktionen möglich:</span><span class="sxs-lookup"><span data-stu-id="c26a3-115">Alternatives for responding to a full transaction log include:</span></span>  
  
-   <span data-ttu-id="c26a3-116">Sichern des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="c26a3-116">Backing up the log.</span></span>  
  
-   <span data-ttu-id="c26a3-117">Freigeben von Speicherplatz, damit das Protokoll automatisch vergrößert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c26a3-117">Freeing disk space so that the log can automatically grow.</span></span>  
  
-   <span data-ttu-id="c26a3-118">Verschieben der Protokolldatei auf einen Datenträger mit ausreichendem Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="c26a3-118">Moving the log file to a disk drive with sufficient space.</span></span>  
  
-   <span data-ttu-id="c26a3-119">Vergrößern einer Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="c26a3-119">Increasing the size of a log file.</span></span>  
  
-   <span data-ttu-id="c26a3-120">Hinzufügen einer Protokolldatei auf einem anderen Datenträger.</span><span class="sxs-lookup"><span data-stu-id="c26a3-120">Adding a log file on a different disk.</span></span>  
  
-   <span data-ttu-id="c26a3-121">Abschließen oder Abbrechen einer Transaktion mit langer Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="c26a3-121">Completing or killing a long-running transaction.</span></span>  
  
 <span data-ttu-id="c26a3-122">Diese Alternativen werden in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="c26a3-122">These alternatives are discussed in the following sections.</span></span> <span data-ttu-id="c26a3-123">Wählen Sie diejenige Aktion aus, die sich am besten für Ihre Situation eignet.</span><span class="sxs-lookup"><span data-stu-id="c26a3-123">Choose a response that fits your situation best.</span></span>  
  
### <a name="backing-up-the-log"></a><span data-ttu-id="c26a3-124">Sichern des Protokolls</span><span class="sxs-lookup"><span data-stu-id="c26a3-124">Backing up the Log</span></span>  
 <span data-ttu-id="c26a3-125">Falls bei Verwendung des vollständigen oder massenprotokollierten Wiederherstellungsmodells das Transaktionsprotokoll nicht vor kurzem gesichert wurde, kann durch die Sicherung eine Protokollkürzung verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="c26a3-125">Under the full recovery model or bulk-logged recovery model, if the transaction log has not been backed up recently, backup might be what is preventing log truncation.</span></span> <span data-ttu-id="c26a3-126">Wenn das Protokoll noch nie gesichert wurde, müssen Sie zwei Protokollsicherungen erstellen, damit das Protokoll von [!INCLUDE[ssDE](../../includes/ssde-md.md)] bis zu dem Punkt abgeschnitten werden kann, an dem die letzte Sicherung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="c26a3-126">If the log has never been backed up, you must create two log backups to permit the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to truncate the log to the point of the last backup.</span></span> <span data-ttu-id="c26a3-127">Durch Kürzen des Protokolls wird Speicherplatz für neue Protokolldatensätze freigegeben.</span><span class="sxs-lookup"><span data-stu-id="c26a3-127">Truncating the log frees space for new log records.</span></span> <span data-ttu-id="c26a3-128">Sichern Sie das Protokoll in kürzeren Abständen, damit es nicht wieder so schnell aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="c26a3-128">To keep the log from filling up again, take log backups frequently.</span></span>  
  
 <span data-ttu-id="c26a3-129">**So erstellen Sie eine Transaktionsprotokollsicherung**</span><span class="sxs-lookup"><span data-stu-id="c26a3-129">**To create a transaction log backup**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c26a3-130">Wenn die Datenbank beschädigt ist, gehen Sie unter [Protokollfragmentsicherungen &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c26a3-130">If the database is damaged, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="c26a3-131">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c26a3-131">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="c26a3-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="c26a3-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
### <a name="freeing-disk-space"></a><span data-ttu-id="c26a3-133">Freigeben von Speicherplatz</span><span class="sxs-lookup"><span data-stu-id="c26a3-133">Freeing Disk Space</span></span>  
 <span data-ttu-id="c26a3-134">Möglicherweise können Sie durch Löschen oder Verschieben anderer Dateien Speicherplatz auf dem Datenträger freigeben, das die Transaktionsprotokolldatei für die Datenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="c26a3-134">You might be able to free disk space on the disk drive that contains the transaction log file for the database by deleting or moving other files.</span></span> <span data-ttu-id="c26a3-135">Aufgrund des freigegebenen Speicherplatzes kann die Protokolldatei dann durch den Wiederherstellungsmechanismus automatisch vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="c26a3-135">The freed disk space allows the recovery system to enlarge the log file automatically.</span></span>  
  
### <a name="moving-the-log-file-to-a-different-disk"></a><span data-ttu-id="c26a3-136">Verschieben der Protokolldatei auf einen anderen Datenträger</span><span class="sxs-lookup"><span data-stu-id="c26a3-136">Moving the Log File to a Different Disk</span></span>  
 <span data-ttu-id="c26a3-137">Wenn Sie auf dem Datenträger, auf dem die Protokolldatei aktuell gespeichert ist, nicht genügend Speicherplatz freigeben können, können Sie die Datei auf einen anderen Datenträger mit ausreichendem Speicherplatz verschieben.</span><span class="sxs-lookup"><span data-stu-id="c26a3-137">If you cannot free enough disk space on the drive that currently contains the log file, consider moving the file to another drive with sufficient space.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c26a3-138">Protokolldateien sollten unter keinen Umständen in komprimierten Dateisystemen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c26a3-138">Log files should never be placed on compressed file systems.</span></span>  
  
 <span data-ttu-id="c26a3-139">**So verschieben Sie eine Protokolldatei**</span><span class="sxs-lookup"><span data-stu-id="c26a3-139">**To move a log file**</span></span>  
  
-   [<span data-ttu-id="c26a3-140">Verschieben von Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="c26a3-140">Move Database Files</span></span>](../databases/move-database-files.md)  
  
### <a name="increasing-the-size-of-a-log-file"></a><span data-ttu-id="c26a3-141">Vergrößern einer Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="c26a3-141">Increasing the Size of a Log File</span></span>  
 <span data-ttu-id="c26a3-142">Wenn auf dem Protokolldatenträger Speicherplatz vorhanden ist, können Sie die Protokolldatei vergrößern.</span><span class="sxs-lookup"><span data-stu-id="c26a3-142">If space is available on the log disk, you can increase the size of the log file.</span></span> <span data-ttu-id="c26a3-143">Die maximale Größe für Protokolldateien beträgt zwei Terabyte (TB) pro Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="c26a3-143">The maximum size for log files is two terabytes (TB) per log file.</span></span>  
  
 <span data-ttu-id="c26a3-144">**So erhöhen Sie die Dateigröße**</span><span class="sxs-lookup"><span data-stu-id="c26a3-144">**To increase the file size**</span></span>  
  
 <span data-ttu-id="c26a3-145">Wenn die automatische Vergrößerung deaktiviert ist, die Datenbank online ist und auf dem Datenträger ausreichend Speicherplatz verfügbar ist, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c26a3-145">If autogrow is disabled, the database is online, and sufficient space is available on the disk, either:</span></span>  
  
-   <span data-ttu-id="c26a3-146">Erhöhen Sie die Dateigröße manuell, um die Datei einmalig um einen bestimmten Wert zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="c26a3-146">Manually increase the file size to produce a single growth increment.</span></span>  
  
-   <span data-ttu-id="c26a3-147">Aktivieren Sie die automatische Vergrößerung, indem Sie mit der ALTER DATABASE-Anweisung für die Option FILEGROWTH ein Vergrößerungsinkrement ungleich Null festlegen.</span><span class="sxs-lookup"><span data-stu-id="c26a3-147">Turn on autogrow by using the ALTER DATABASE statement to set a non-zero growth increment for the FILEGROWTH option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c26a3-148">Erhöhen Sie in beiden Fällen den MAXSIZE-Wert, wenn die aktuelle Größenbeschränkung erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="c26a3-148">In either case, if the current size limit has been reached, increase the MAXSIZE value.</span></span>  
  
### <a name="adding-a-log-file-on-a-different-disk"></a><span data-ttu-id="c26a3-149">Hinzufügen einer Protokolldatei auf einem anderen Datenträger</span><span class="sxs-lookup"><span data-stu-id="c26a3-149">Adding a Log File on a Different Disk</span></span>  
 <span data-ttu-id="c26a3-150">Fügen Sie der Datenbank mithilfe von ALTER DATABASE <database_name> ADD LOG FILE eine neue Protokolldatei auf einem anderen Datenträger hinzu, auf dem ausreichend Speicherplatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c26a3-150">Add a new log file to the database on a different disk that has sufficient space by using ALTER DATABASE <database_name> ADD LOG FILE.</span></span>  
  
 <span data-ttu-id="c26a3-151">**So fügen Sie eine Protokolldatei hinzu**</span><span class="sxs-lookup"><span data-stu-id="c26a3-151">**To add a log file**</span></span>  
  
-   [<span data-ttu-id="c26a3-152">Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="c26a3-152">Add Data or Log Files to a Database</span></span>](../databases/add-data-or-log-files-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="c26a3-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c26a3-153">See Also</span></span>  
 <span data-ttu-id="c26a3-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c26a3-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="c26a3-155">[Verwalten der Größe der Transaktionsprotokolldatei](manage-the-size-of-the-transaction-log-file.md) </span><span class="sxs-lookup"><span data-stu-id="c26a3-155">[Manage the Size of the Transaction Log File](manage-the-size-of-the-transaction-log-file.md) </span></span>  
 <span data-ttu-id="c26a3-156">[Transaktionsprotokollsicherungen &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c26a3-156">[Transaction Log Backups &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="c26a3-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c26a3-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-log-file-recover-suspect-db-transact-sql)  
  
  
