---
title: Transaktionsprotokollsicherungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up [SQL Server], transaction logs
- transaction log backups [SQL Server], creating
- log backups [SQL Server[
- transaction log backups [SQL Server], sequencing
ms.assetid: f4a44a35-0f44-4a42-91d5-d73ac658a3b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 752447d6c38a2df0fcbdce72fbba12edd7a9eeb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718316"
---
# <a name="transaction-log-backups-sql-server"></a><span data-ttu-id="c643c-102">Transaktionsprotokollsicherungen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c643c-102">Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="c643c-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken relevant, die das vollständige oder das massenprotokollierte Wiederherstellungsmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="c643c-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span> <span data-ttu-id="c643c-104">In diesem Thema wird das Sichern des Transaktionsprotokolls einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank erläutert.</span><span class="sxs-lookup"><span data-stu-id="c643c-104">This topic discusses backing up the transaction log of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="c643c-105">Vor dem Erstellen von Protokollsicherungen muss bereits mindestens eine vollständige Sicherung durchgeführt worden sein.</span><span class="sxs-lookup"><span data-stu-id="c643c-105">Minimally, you must have created at least one full backup before you can create any log backups.</span></span> <span data-ttu-id="c643c-106">Danach kann das Transaktionsprotokoll jederzeit gesichert werden, es sei denn, das Protokoll wurde gerade gesichert.</span><span class="sxs-lookup"><span data-stu-id="c643c-106">After that, the transaction log can be backed up at any time unless the log is already being backed up.</span></span> <span data-ttu-id="c643c-107">Es empfiehlt sich, Protokollsicherungen häufig auszuführen, damit auf diese Weise die Gefahr von Datenverlusten verringert und das Abschneiden des Transaktionsprotokolls angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c643c-107">We recommend that you take log backups frequently, both to minimize work loss exposure and to truncate the transaction log.</span></span> <span data-ttu-id="c643c-108">In der Regel erstellt ein Datenbankadministrator von Zeit zu Zeit eine vollständige Datenbanksicherung, z. B. einmal pro Woche, sowie optional in kürzeren Abständen eine Reihe von differenziellen Datenbanksicherungen, z. B. täglich.</span><span class="sxs-lookup"><span data-stu-id="c643c-108">Typically, a database administrator creates a full database backup occasionally, such as weekly, and, optionally, creates a series of differential database backup at a shorter interval, such as daily.</span></span> <span data-ttu-id="c643c-109">Unabhängig von den Datenbanksicherungen sichert der Datenbankadministrator das Transaktionsprotokoll sehr häufig, z. B. alle 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="c643c-109">Independently of the database backups, the database administrator backs up the transaction log at frequent intervals, such as every 10 minutes.</span></span> <span data-ttu-id="c643c-110">Der optimale Abstand zwischen Sicherungen ist abhängig von Faktoren wie der Wichtigkeit der Daten, der Größe der Datenbank und der Arbeitsauslastung des Servers.</span><span class="sxs-lookup"><span data-stu-id="c643c-110">For a given type of backup, the optimal interval depends on factors such as the importance of the data, the size of the database, and the workload of the server.</span></span>  
  
 <span data-ttu-id="c643c-111">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="c643c-111">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="c643c-112">Funktionsweise einer Sequenz von Protokoll Sicherungen</span><span class="sxs-lookup"><span data-stu-id="c643c-112">How a Sequence of Log Backups Works</span></span>](#LogBackupSequence)  
  
-   [<span data-ttu-id="c643c-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="c643c-113">Recommendations</span></span>](#Recommendations)  
  
-   [<span data-ttu-id="c643c-114">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c643c-114">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="c643c-115">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="c643c-115">Related Content</span></span>](#RelatedContent)  
  
##  <a name="how-a-sequence-of-log-backups-works"></a><a name="LogBackupSequence"></a><span data-ttu-id="c643c-116">Funktionsweise einer Sequenz von Protokoll Sicherungen</span><span class="sxs-lookup"><span data-stu-id="c643c-116">How a Sequence of Log Backups Works</span></span>  
 <span data-ttu-id="c643c-117">Die Sequenz der Transaktionsprotokollsicherungen ( *Protokollkette* ) ist unabhängig von den Datensicherungen.</span><span class="sxs-lookup"><span data-stu-id="c643c-117">The sequence of transaction log backups *log chain* is independent of data backups.</span></span> <span data-ttu-id="c643c-118">Stellen Sie sich z. B. folgende Ereignissequenz vor.</span><span class="sxs-lookup"><span data-stu-id="c643c-118">For example, assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="c643c-119">Time</span><span class="sxs-lookup"><span data-stu-id="c643c-119">Time</span></span>|<span data-ttu-id="c643c-120">Ereignis</span><span class="sxs-lookup"><span data-stu-id="c643c-120">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="c643c-121">8:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c643c-121">8:00 A.M.</span></span>|<span data-ttu-id="c643c-122">Sichern der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c643c-122">Back up database.</span></span>|  
|<span data-ttu-id="c643c-123">12:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c643c-123">Noon</span></span>|<span data-ttu-id="c643c-124">Sichern des Transaktionsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="c643c-124">Back up transaction log.</span></span>|  
|<span data-ttu-id="c643c-125">16:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c643c-125">4:00 P.M.</span></span>|<span data-ttu-id="c643c-126">Sichern des Transaktionsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="c643c-126">Back up transaction log.</span></span>|  
|<span data-ttu-id="c643c-127">18:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c643c-127">6:00 P.M.</span></span>|<span data-ttu-id="c643c-128">Sichern der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c643c-128">Back up database.</span></span>|  
|<span data-ttu-id="c643c-129">20:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c643c-129">8:00 P.M.</span></span>|<span data-ttu-id="c643c-130">Sichern des Transaktionsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="c643c-130">Back up transaction log.</span></span>|  
  
 <span data-ttu-id="c643c-131">Die um 20:00 Uhr erstellte Sicherung des Transaktionsprotokolls</span><span class="sxs-lookup"><span data-stu-id="c643c-131">The transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="c643c-132">enthält Transaktionsprotokoll-Datensätze von 16:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="c643c-132">contains transaction log records from 4:00 P.M.</span></span> <span data-ttu-id="c643c-133">bis 20:00 Uhr, wobei der Zeitpunkt eingeschlossen ist, zu dem um 18:00 Uhr die vollständige Sicherung der Datenbank erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c643c-133">through 8:00 P.M., spanning the time when the full database backup was created at 6:00 P.M.</span></span> <span data-ttu-id="c643c-134">Die Sequenz der Transaktionsprotokollsicherungen reicht ohne Unterbrechung von der um 08:00 Uhr erstellten ersten vollständigen Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="c643c-134">The sequence of transaction log backups is continuous from the initial full database backup created at 8:00 A.M.</span></span> <span data-ttu-id="c643c-135">bis zur letzten Sicherung des Transaktionsprotokolls um 20:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="c643c-135">to the last transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="c643c-136">Informationen zum Anwenden dieser Protokollsicherungen finden Sie im Beispiel unter [Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c643c-136">For information about how to apply these log backups, see the example in [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c643c-137">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="c643c-137">Recommendations</span></span>  
  
-   <span data-ttu-id="c643c-138">Wenn ein Transaktionsprotokoll beschädigt wird, gehen die Änderungen seit der letzten gültigen Sicherung verloren.</span><span class="sxs-lookup"><span data-stu-id="c643c-138">If a transaction log is damaged, work that is performed since the most recent valid backup is lost.</span></span> <span data-ttu-id="c643c-139">Daher empfehlen wir dringend, Protokolldateien auf einem fehlertoleranten Datenträger zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c643c-139">Therefore we strongly recommend that you put your log files on fault-tolerant storage.</span></span>  
  
-   <span data-ttu-id="c643c-140">Wenn eine Datenbank beschädigt ist oder in Kürze wiederhergestellt werden soll, ist es ratsam, eine [Sicherung des Protokollfragments](tail-log-backups-sql-server.md) zu erstellen, damit Sie den aktuellen Stand der Datenbank wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="c643c-140">If a database is damaged or you are about to restore the database, we recommend that you create a [tail-log backup](tail-log-backups-sql-server.md) to enable you to restore the database to the current point in time.</span></span>  
  
-   <span data-ttu-id="c643c-141">Standardmäßig wird bei jedem erfolgreichen Sicherungsvorgang dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll und dem Systemereignisprotokoll ein Eintrag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c643c-141">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="c643c-142">Wenn Sie das Protokoll regelmäßig sichern, kann die Anzahl dieser Erfolgsmeldungen schnell ansteigen, d. h., es entstehen sehr große Fehlerprotokolle, die das Suchen nach anderen Meldungen erschweren können.</span><span class="sxs-lookup"><span data-stu-id="c643c-142">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="c643c-143">In solchen Fällen können Sie diese Protokolleinträge mithilfe des Ablaufverfolgungsflags 3226 unterdrücken, wenn keines der Skripts von diesen Einträgen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="c643c-143">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="c643c-144">Weitere Informationen finden Sie unter [Ablaufverfolgungsflags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c643c-144">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c643c-145">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c643c-145">Related Tasks</span></span>  
 <span data-ttu-id="c643c-146">**So erstellen Sie eine Transaktionsprotokollsicherung**</span><span class="sxs-lookup"><span data-stu-id="c643c-146">**To create a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="c643c-147">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c643c-147">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="c643c-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="c643c-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="c643c-149">Informationen zum Planen von Sicherungsaufträgen finden Sie unter [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c643c-149">To schedule backup jobs, see [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="c643c-150">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="c643c-150">Related Content</span></span>  
 <span data-ttu-id="c643c-151">Keine.</span><span class="sxs-lookup"><span data-stu-id="c643c-151">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c643c-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c643c-152">See Also</span></span>  
 <span data-ttu-id="c643c-153">[Das Transaktionsprotokoll &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c643c-153">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="c643c-154">[Sichern und Wiederherstellen von SQL Server-Datenbanken](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c643c-154">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="c643c-155">[Protokollfragmentsicherungen &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c643c-155">[Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="c643c-156">Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c643c-156">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](transaction-log-backups-sql-server.md)  
  
  
