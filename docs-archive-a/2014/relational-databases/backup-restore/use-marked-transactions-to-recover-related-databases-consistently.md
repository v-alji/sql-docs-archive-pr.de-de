---
title: Verwenden von markierten Transaktionen zum konsistenten wiederherstellen verwandter Datenbanken (vollständiges Wiederherstellungs Modell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction marks [SQL Server]
- marked transactions [SQL Server]
- database restores [SQL Server], inserting transaction marks for
- recovery [SQL Server], related databases
- restoring databases [SQL Server], related database recovery
- database restores [SQL Server], related databases
- marked transactions [SQL Server], creating
- BEGIN TRAN...WITH MARK statement
- two-phase commit
ms.assetid: 50a73574-1a69-448e-83dd-9abcc7cb7e1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8dd368ad14f6e521fb8d504bdea774e3088c2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721510"
---
# <a name="use-marked-transactions-to-recover-related-databases-consistently-full-recovery-model"></a><span data-ttu-id="a0d5f-102">Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="a0d5f-102">Use Marked Transactions to Recover Related Databases Consistently (Full Recovery Model)</span></span>
  <span data-ttu-id="a0d5f-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken relevant, die das vollständige oder das massenprotokollierte Wiederherstellungsmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="a0d5f-104">Wenn Sie Updates für zwei oder mehr Datenbanken, ( *zugehörige Datenbanken*), ausführen, können Sie diese mithilfe von Transaktionsmarkierungen bis zu einem logisch konsistenten Punkt wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-104">When you make related updates to two or more databases, *related databases*, you can use transaction marks to recover them to a logically consistent point.</span></span> <span data-ttu-id="a0d5f-105">Bei dieser Wiederherstellung gehen jedoch alle Transaktionen verloren, für die nach der Markierung, die als Wiederherstellungspunkt verwendet wird, ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-105">However, this recovery loses any transaction that is committed after the mark that was used as the recovery point.</span></span> <span data-ttu-id="a0d5f-106">Das Markieren von Transaktionen empfiehlt sich nur, wenn Sie verbundene Datenbanken prüfen oder wenn Sie in Kauf nehmen, dass Transaktionen, für die kürzlich ein Commit ausgeführt wurde, verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-106">Marking transactions is suitable only when you are testing related databases or when you are willing to lose recently committed transactions.</span></span>  
  
 <span data-ttu-id="a0d5f-107">Durch das routinemäßige Markieren zugehöriger Transaktionen in allen verbundenen Datenbanken werden eine Reihe allgemeiner Wiederherstellungspunkte in den Datenbanken erstellt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-107">Routinely marking related transactions in every related database establishes a series of common recovery points in the databases.</span></span> <span data-ttu-id="a0d5f-108">Die Transaktionsmarkierungen werden im Transaktionsprotokoll aufgezeichnet und in Protokollsicherungen eingebunden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-108">The transaction marks are recorded in the transaction log and included in log backups.</span></span> <span data-ttu-id="a0d5f-109">Wenn ein Notfall eintreten sollte, können Sie die einzelnen Datenbanken bis zu dieser Transaktionsmarkierung und damit bis zu einem konsistenten Zeitpunkt wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-109">In the event of a disaster, you can restore each of the databases to the same transaction mark to recover them to a consistent point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0d5f-110">Protokollsicherungen für die verschiedenen Datenbanken können unabhängig voneinander erstellt werden. Sie müssen auch nicht gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-110">Log backups on the different databases can be created independently of each other and do not have to be simultaneous.</span></span>  
  
 <span data-ttu-id="a0d5f-111">Für das Wiederherstellen zugehöriger Datenbanken in den folgenden Szenarien ist es erforderlich, dass in allen verbundenen Datenbanken bereits markierte Transaktionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="a0d5f-111">Recovering related databases in the following scenarios requires that you have already marked transactions in every related database:</span></span>  
  
-   <span data-ttu-id="a0d5f-112">Mindestens ein Transaktionsprotokoll ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-112">One or more transaction logs are destroyed.</span></span> <span data-ttu-id="a0d5f-113">Stellen Sie für den Datenbanksatz einen konsistenten Status zum Zeitpunkt der letzten Protokollsicherung wieder her.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-113">You have to restore the set of databases to a consistent state at the time of your last log backup.</span></span>  
  
-   <span data-ttu-id="a0d5f-114">Sie müssen für den gesamten Datenbanksatz einen gegenseitig konsistenten Status zu einem früheren Zeitpunkt wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-114">You have to restore the entire set of databases to a mutually consistent state at some earlier point in time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a0d5f-115">Sie können verbundene Datenbanken nur bis zu einer markierten Transaktion wiederherstellen, nicht bis zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-115">You can recover related databases only to a marked transaction, not to a specific point in time.</span></span>  
  
 <span data-ttu-id="a0d5f-116">Weitere Informationen zum Erstellen markierter Transaktionen finden Sie unter "Erstellen der markierten Transaktionen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-116">For information about how to create marking transactions, see "Creating the Marked Transactions," later in this topic.</span></span>  
  
## <a name="typical-scenario-for-using-marked-transactions"></a><span data-ttu-id="a0d5f-117">Typisches Szenario zum Verwenden markierter Transaktionen</span><span class="sxs-lookup"><span data-stu-id="a0d5f-117">Typical Scenario for Using Marked Transactions</span></span>  
 <span data-ttu-id="a0d5f-118">Ein typisches Szenario zum Verwenden markierter Transaktionen umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="a0d5f-118">A typical scenario for using marked transactions includes the following steps:</span></span>  
  
1.  <span data-ttu-id="a0d5f-119">Erstellen Sie eine vollständige oder differenzielle Datenbanksicherung für die einzelnen verbundenen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-119">Create a full or differential database backup of each of the related databases.</span></span>  
  
2.  <span data-ttu-id="a0d5f-120">Markieren Sie in allen Datenbanken einen Transaktionsblock.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-120">Mark a transaction block in all the databases.</span></span>  
  
3.  <span data-ttu-id="a0d5f-121">Sichern Sie das Transaktionsprotokoll für alle Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-121">Back up the transaction log for all the databases.</span></span>  
  
4.  <span data-ttu-id="a0d5f-122">Stellen Sie mithilfe von WITH NORECOVERY Datenbanksicherungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-122">Restore database backups WITH NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="a0d5f-123">Stellen Sie mithilfe von WITH STOPATMARK Protokolle wieder her.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-123">Restore logs WITH STOPATMARK.</span></span>  
  
## <a name="considerations-for-using-marked-transactions"></a><span data-ttu-id="a0d5f-124">Überlegungen zum Verwenden markierter Transaktionen</span><span class="sxs-lookup"><span data-stu-id="a0d5f-124">Considerations for Using Marked Transactions</span></span>  
 <span data-ttu-id="a0d5f-125">Beachten Sie Folgendes, bevor Sie benannte Markierungen in das Transaktionsprotokoll einfügen:</span><span class="sxs-lookup"><span data-stu-id="a0d5f-125">Before inserting named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="a0d5f-126">Transaktionsmarkierungen belegen Protokollspeicherplatz und sollten deshalb nur für Transaktionen verwendet werden, die eine wichtige Rolle bei der Wiederherstellungsstrategie für die Datenbank spielen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-126">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="a0d5f-127">Nachdem für eine markierte Transaktion ein Commit ausgeführt wurde, wird in die [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) -Tabelle in **msdb**eine Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-127">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="a0d5f-128">Wenn sich eine markierte Transaktion über mehrere Datenbanken auf demselben Datenbankserver oder auf verschiedenen Servern erstreckt, müssen die Markierungen in den Protokollen aller betroffenen Datenbanken aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-128">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span>  
  
## <a name="creating-the-marked-transactions"></a><span data-ttu-id="a0d5f-129">Erstellen der markierten Transaktionen</span><span class="sxs-lookup"><span data-stu-id="a0d5f-129">Creating the Marked Transactions</span></span>  
 <span data-ttu-id="a0d5f-130">Verwenden Sie die [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) -Anweisung und die WITH MARK [*description*]-Klausel, um markierte Transaktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-130">To create a marked transaction, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="a0d5f-131">Der optionale *description* -Parameter ist eine Textbeschreibung der Markierung.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-131">The optional *description* is a textual description of the mark.</span></span> <span data-ttu-id="a0d5f-132">Ein Markierungsname für die Transaktion ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-132">A mark name for the transaction is required.</span></span> <span data-ttu-id="a0d5f-133">Ein Markierungsname kann erneut verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-133">A mark name can be reused.</span></span> <span data-ttu-id="a0d5f-134">Im Transaktionsprotokoll werden der Markierungsname, die Beschreibung, die Datenbank, der Benutzer, datetime-Informationen und die Protokollfolgenummer (LSN, Log Sequence Number) aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-134">The transaction log records the mark name, description, database, user, datetime information, and the log sequence number (LSN).</span></span> <span data-ttu-id="a0d5f-135">Die datetime-Informationen werden zusammen mit dem Markierungsnamen für die eindeutige Identifizierung der Markierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-135">The datetime information is used along with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="a0d5f-136">**So erstellen Sie markierte Transaktionen in einem Datenbanksatz:**</span><span class="sxs-lookup"><span data-stu-id="a0d5f-136">**To create marked transactions in a set of databases:**</span></span>  
  
1.  <span data-ttu-id="a0d5f-137">Benennen Sie die Transaktion in der BEGIN TRAN-Anweisung, und verwenden Sie die WITH MARK-Klausel</span><span class="sxs-lookup"><span data-stu-id="a0d5f-137">Name the transaction in the BEGIN TRAN statement and use the WITH MARK clause</span></span>  
  
     <span data-ttu-id="a0d5f-138">Die BEGIN TRAN *Neuer Markierungsname* WITH MARK-Anweisung kann innerhalb einer vorhandenen Transaktion geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-138">You can nest the statement BEGIN TRAN *new_mark_name* WITH MARK within an existing transaction.</span></span> <span data-ttu-id="a0d5f-139">Der Wert von *Neuer Markierungsname* stellt den Markierungsnamen für die Transaktion dar, selbst wenn die Transaktion einen Transaktionsnamen umfasst.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-139">The value of *new_mark_name* is the mark name for the transaction, even if the transaction possesses a transaction name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0d5f-140">Wenn Sie eine zweite geschachtelte BEGIN TRAN...WITH MARK-Anweisung ausgeben, wird diese ausgelassen, führt allerdings zu einer Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-140">If you issue a second nested BEGIN TRAN...WITH MARK, that statement is skipped but causes a warning message.</span></span>  
  
2.  <span data-ttu-id="a0d5f-141">Führen Sie ein Update für alle Datenbanken im Datenbanksatz aus.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-141">Run an update against all of the databases in the set.</span></span>  
  
     <span data-ttu-id="a0d5f-142">Die Markierung für eine bestimmte Transaktion wird nur in Transaktionsprotokollen auf der Serverinstanz eingefügt, auf der die BEGIN TRAN...WITH MARK-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-142">The mark for a specific transaction is inserted into transaction logs only on the server instance where the BEGIN TRAN...WITH MARK statement is executed.</span></span> <span data-ttu-id="a0d5f-143">Die Transaktionsmarkierung wird in das Transaktionsprotokoll der Datenbanken platziert, die von der markierten Transaktion auf dieser Serverinstanz aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-143">The transaction mark is placed in the transaction log of every database updated by the marked transaction on that server instance.</span></span> <span data-ttu-id="a0d5f-144">Wenn sich die Datenbanken auf verschiedenen Serverinstanzen befinden, müssen auf den einzelnen Serverinstanzen identische Markierungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-144">If the databases reside on different server instances, identical marks must be created on each of the server instances.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a0d5f-145">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a0d5f-145">Examples</span></span>  
 <span data-ttu-id="a0d5f-146">Im folgenden Beispiel wird das Transaktionsprotokoll bis zur Markierung in der markierten Transaktion mit dem Namen `ListPriceUpdate`wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-146">The following example restores the transaction log to the mark in the marked transaction named `ListPriceUpdate`.</span></span>  
  
```sql  
USE AdventureWorks  
GO  
BEGIN TRANSACTION ListPriceUpdate  
   WITH MARK 'UPDATE Product list prices';  
GO  
  
UPDATE Production.Product  
   SET ListPrice = ListPrice * 1.10  
   WHERE ProductNumber LIKE 'BK-%';  
GO  
  
COMMIT TRANSACTION ListPriceUpdate;  
GO  
  
-- Time passes. Regular database   
-- and log backups are taken.  
-- An error occurs in the database.  
USE master  
GO  
  
RESTORE DATABASE AdventureWorks  
FROM AdventureWorksBackups  
WITH FILE = 3, NORECOVERY;  
GO  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups   
   WITH FILE = 4,  
   RECOVERY,   
   STOPATMARK = 'ListPriceUpdate';  
```  
  
## <a name="forcing-a-mark-to-spread-to-other-servers"></a><span data-ttu-id="a0d5f-147">Erzwingen einer Markierung für andere Server</span><span class="sxs-lookup"><span data-stu-id="a0d5f-147">Forcing a Mark to Spread to Other Servers</span></span>  
 <span data-ttu-id="a0d5f-148">Ein Transaktionsmarkierungsname wird nicht automatisch an einen anderen Server verteilt, wenn die Transaktion dort verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-148">A transaction mark name is not automatically distributed to another server as the transaction spreads there.</span></span> <span data-ttu-id="a0d5f-149">Um die Weitergabe der Markierung an die anderen Server zu erzwingen, muss eine gespeicherte Prozedur geschrieben werden, die eine BEGIN TRAN *name* WITH MARK-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-149">To force the mark to spread to the other servers, a stored procedure must be written that contains a BEGIN TRAN *name* WITH MARK statement.</span></span> <span data-ttu-id="a0d5f-150">Diese gespeicherte Prozedur muss dann auf dem Remoteserver unter dem Gültigkeitsbereich der Transaktion auf dem ursprünglichen Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-150">That stored procedure must then be executed on the remote server under the scope of the transaction in the originating server.</span></span>  
  
 <span data-ttu-id="a0d5f-151">Angenommen, eine partitionierte Datenbank ist in mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-151">For example, consider a partitioned database that exists on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0d5f-152">In jeder Instanz gibt es eine Datenbank namens `coyote`.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-152">On each instance is a database named `coyote`.</span></span> <span data-ttu-id="a0d5f-153">Erstellen Sie zuerst in allen Datenbanken eine gespeicherte Prozedur, z. B. `sp_SetMark`.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-153">First, in every database, create a stored procedure, for example, `sp_SetMark`.</span></span>  
  
```sql  
CREATE PROCEDURE sp_SetMark  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION @name WITH MARK  
UPDATE coyote.dbo.Marks SET one = 1  
COMMIT TRANSACTION;  
GO  
```  
  
 <span data-ttu-id="a0d5f-154">Erstellen Sie anschließend die gespeicherte Prozedur `sp_MarkAll` , in der eine Transaktion enthalten ist, mit der in jeder Datenbank eine Markierung platziert wird.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-154">Next, create stored procedure `sp_MarkAll` containing a transaction that places a mark in every database.</span></span> <span data-ttu-id="a0d5f-155">`sp_MarkAll` kann von jeder Instanz aus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-155">`sp_MarkAll` can be run from any of the instances.</span></span>  
  
```sql  
CREATE PROCEDURE sp_MarkAll  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION  
EXEC instance0.coyote.dbo.sp_SetMark @name  
EXEC instance1.coyote.dbo.sp_SetMark @name  
EXEC instance2.coyote.dbo.sp_SetMark @name  
COMMIT TRANSACTION;  
GO  
```  
  
### <a name="two-phase-commit"></a><span data-ttu-id="a0d5f-156">Zweiphasencommit</span><span class="sxs-lookup"><span data-stu-id="a0d5f-156">Two-Phase Commit</span></span>  
 <span data-ttu-id="a0d5f-157">Das Ausführen eines Commits einer verteilten Transaktion verläuft in zwei Phasen: Vorbereitung und Commit.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-157">Committing a distributed transaction occurs in two phases: prepare and commit.</span></span> <span data-ttu-id="a0d5f-158">Wenn für eine markierte Transaktion ein Commit ausgeführt wird, wird der Commitprotokolleintrag für jede Datenbank in der markierten Transaktion an einem Punkt des Protokolls platziert, an dem in keinem der Protokolle zweifelhafte Transaktionen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-158">When a marked transaction is committed, the commit log record for each database in the marked transaction is placed in the log at a point where there are no in-doubt transactions in any of the logs.</span></span> <span data-ttu-id="a0d5f-159">Damit wird sichergestellt, dass keine Transaktionen auftreten, für die in einem Protokoll das vollzogene Ausführen eines Commits angezeigt wird, während in einem anderen Protokoll das vollzogene Ausführen eines Commits nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-159">At this point, it is guaranteed that there are no transactions that appear as committed in one log, but not committed in another log.</span></span>  
  
 <span data-ttu-id="a0d5f-160">Gehen Sie dazu während der Ausführung eines Commits für eine markierte Transaktion folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="a0d5f-160">The following steps accomplish this during the commit of a marked transaction:</span></span>  
  
1.  <span data-ttu-id="a0d5f-161">Die Vorbereitungsphase einer Markierungstransaktion hält alle neuen Vorbereitungen und Commits zurück.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-161">Prepare phase of a marking transaction stalls all new prepares and commits.</span></span>  
  
2.  <span data-ttu-id="a0d5f-162">Nur Commits für bereits vorbereitete Transaktionen werden fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-162">Only commits of already prepared transactions are allowed to continue.</span></span>  
  
3.  <span data-ttu-id="a0d5f-163">Die Markierungstransaktion wartet dann, bis alle vorbereiteten Transaktionen ausgeglichen wurden (mit Timeout).</span><span class="sxs-lookup"><span data-stu-id="a0d5f-163">Marking transaction then waits for all prepared transactions to drain (with time-out).</span></span>  
  
4.  <span data-ttu-id="a0d5f-164">Die markierte Transaktion wird vorbereitet, und ein Commit wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-164">Marked transaction is prepared and committed.</span></span>  
  
5.  <span data-ttu-id="a0d5f-165">Das Zurückhalten neuer Vorbereitungen und Commits wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-165">The stall of new prepares and commits is removed.</span></span>  
  
 <span data-ttu-id="a0d5f-166">Das Zurückhalten, das durch markierte Transaktionen generiert wird, die sich über mehrere Datenbanken erstrecken, kann die Leistung des Servers hinsichtlich der Transaktionsverarbeitung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-166">The stalls generated by marked transactions that span multiple databases can reduce the transaction processing performance of the server.</span></span>  
  
 <span data-ttu-id="a0d5f-167">Es wird davon abgeraten, markierte Transaktionen gleichzeitig auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-167">We recommend that you do not run concurrent marked transactions.</span></span> <span data-ttu-id="a0d5f-168">Es kommt zwar selten vor, aber es ist möglich, dass der Commit einer verteilten markierten Transaktion einen Deadlock mit anderen verteilten Transaktionen verursacht, für die gleichzeitig ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-168">It is rare but possible for the commit of a distributed marked transaction to deadlock with other distributed marked transactions that are committing at the same time.</span></span> <span data-ttu-id="a0d5f-169">Wenn dies passiert, wird die Markierungstransaktion als Deadlockopfer gewählt, und ein Rollback wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-169">When this happens, the marking transaction is chosen as the deadlock victim and is rolled back.</span></span> <span data-ttu-id="a0d5f-170">In diesem Fall kann die Anwendung versuchen, die markierte Transaktion erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-170">When this error occurs, the application can retry the marked transaction.</span></span> <span data-ttu-id="a0d5f-171">Wenn mehrere markierte Transaktionen versuchen, gleichzeitig einen Commit auszuführen, steigt die Wahrscheinlichkeit eines Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="a0d5f-171">When multiple marked transactions try to commit concurrently, there is a higher probability of deadlock.</span></span>  
  
## <a name="recovering-to-a-marked-transaction"></a><span data-ttu-id="a0d5f-172">Wiederherstellen bis zu einer markierten Transaktion</span><span class="sxs-lookup"><span data-stu-id="a0d5f-172">Recovering to a Marked Transaction</span></span>  
 <span data-ttu-id="a0d5f-173">Informationen zum Wiederherstellen einer Datenbank, die markierte Transaktionen enthält, bis zu einer Markierung oder kurz vor einer bestimmten Markierung finden Sie unter [Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="a0d5f-173">For information about how to recover a database that contains marked transactions to or just before a particular mark, see [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d5f-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0d5f-174">See Also</span></span>  
 <span data-ttu-id="a0d5f-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a0d5f-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span></span>  
 <span data-ttu-id="a0d5f-176">[Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0d5f-176">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="a0d5f-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a0d5f-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="a0d5f-178">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0d5f-178">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="a0d5f-179">[Vollständige Datenbanksicherungen &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0d5f-179">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="a0d5f-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a0d5f-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="a0d5f-181">Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion</span><span class="sxs-lookup"><span data-stu-id="a0d5f-181">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
  
