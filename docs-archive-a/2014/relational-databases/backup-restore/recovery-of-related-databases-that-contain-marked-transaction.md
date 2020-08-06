---
title: Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], marks
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- transactions [SQL Server], recovering to a mark
- database recovery [SQL Server]
- marked transactions [SQL Server], restoring
- database restores [SQL Server], point in time
ms.assetid: 77a0d9c0-978a-4891-8b0d-a4256c81c3f8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b968322f92c7a135adb5fd0733b5774e7562bc39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721521"
---
# <a name="recovery-of-related--databases-that-contain-marked-transaction"></a><span data-ttu-id="2f254-102">Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion</span><span class="sxs-lookup"><span data-stu-id="2f254-102">Recovery of Related  Databases That Contain Marked Transaction</span></span>
  <span data-ttu-id="2f254-103">Dieses Thema ist nur für Datenbanken relevant, die markierte Transaktionen enthalten und von denen das vollständige oder massenprotokollierte Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f254-103">This topic is relevant only for databases that contain marked transactions and that use the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="2f254-104">Weitere Informationen zu den Anforderungen für die Wiederherstellung bis zu einem bestimmten Wiederherstellungspunkt finden Sie unter [Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="2f254-104">For information about the requirements for restoring to a specific recovery point, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2f254-105">wird das Einfügen benannter Markierungen in das Transaktionsprotokoll unterstützt, um die Wiederherstellung bis zu einer bestimmten Markierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2f254-105">supports inserting named marks into the transaction log to allow recovery to that specific mark.</span></span> <span data-ttu-id="2f254-106">Protokollmarkierungen sind transaktionsspezifisch und werden nur eingefügt, wenn für die zugehörige Transaktion ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f254-106">Log marks are transaction specific and are inserted only if their associated transaction commits.</span></span> <span data-ttu-id="2f254-107">Demzufolge können Sie Markierungen mit bestimmten Daten verknüpfen und die Wiederherstellung bis zu einem bestimmten Punkt vornehmen, der diese Daten ein- oder ausschließt.</span><span class="sxs-lookup"><span data-stu-id="2f254-107">As a result, marks can be tied to specific work, and you can recover to a point that includes or excludes this work.</span></span>  
  
 <span data-ttu-id="2f254-108">Beachten Sie Folgendes, bevor Sie benannte Markierungen in das Transaktionsprotokoll einfügen:</span><span class="sxs-lookup"><span data-stu-id="2f254-108">Before you insert named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="2f254-109">Transaktionsmarkierungen belegen Protokollspeicherplatz und sollten deshalb nur für Transaktionen verwendet werden, die eine wichtige Rolle bei der Wiederherstellungsstrategie für die Datenbank spielen.</span><span class="sxs-lookup"><span data-stu-id="2f254-109">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="2f254-110">Nachdem für eine markierte Transaktion ein Commit ausgeführt wurde, wird in die [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) -Tabelle in **msdb**eine Zeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2f254-110">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="2f254-111">Wenn sich eine markierte Transaktion über mehrere Datenbanken auf demselben Datenbankserver oder auf verschiedenen Servern erstreckt, müssen die Markierungen in den Protokollen aller betroffenen Datenbanken aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="2f254-111">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span> <span data-ttu-id="2f254-112">Weitere Informationen finden Sie unter [Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen &#40;vollständiges Wiederherstellungsmodell&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="2f254-112">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f254-113">Informationen zum Markieren von Transaktionen finden Sie unter [Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen &#40;vollständiges Wiederherstellungsmodell&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="2f254-113">For information about how to mark transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-inserting-named-marks-into-a-transaction-log"></a><span data-ttu-id="2f254-114">Transact-SQL-Syntax für das Einfügen benannter Markierungen in ein Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="2f254-114">Transact-SQL Syntax for Inserting Named Marks into a Transaction Log</span></span>  
 <span data-ttu-id="2f254-115">Verwenden Sie die [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) -Anweisung und die WITH MARK [*description*]-Klausel, um Markierungen in die Transaktionsprotokolle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="2f254-115">To insert marks into the transaction logs, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="2f254-116">Die Markierung erhält denselben Namen wie die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="2f254-116">The mark is named the same as the transaction.</span></span> <span data-ttu-id="2f254-117">Der optionale *description* -Parameter stellt eine Textbeschreibung der Markierung dar und nicht den Namen der Markierung.</span><span class="sxs-lookup"><span data-stu-id="2f254-117">The optional *description* is a textual description of the mark, not the mark name.</span></span> <span data-ttu-id="2f254-118">Beispielsweise lautet der Name der Transaktion und der Markierung, die in der folgenden `BEGIN TRANSACTION` -Anweisung erstellt werden, jeweils `Tx1`:</span><span class="sxs-lookup"><span data-stu-id="2f254-118">For example, the name of both the transaction and the mark that is created in the following `BEGIN TRANSACTION` statement is `Tx1`:</span></span>  
  
```wmimof  
BEGIN TRANSACTION Tx1 WITH MARK 'not the mark name, just a description'    
```  
  
 <span data-ttu-id="2f254-119">Mit dem Transaktionsprotokoll werden der Markierungsname (Transaktionsname), die Beschreibung, die Datenbank, der Benutzer, `datetime`-Informationen und die Protokollfolgenummer (LSN, Log Sequence Number) aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2f254-119">The transaction log records the mark name (transaction name), description, database, user, `datetime` information, and the log sequence number (LSN).</span></span> <span data-ttu-id="2f254-120">Die `datetime`-Informationen werden zusammen mit dem Markierungsnamen für die eindeutige Identifizierung der Markierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f254-120">The `datetime` information is used with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="2f254-121">Informationen zum Einfügen einer Markierung in eine Transaktion, die mehrere Datenbanken umfasst, finden Sie unter [Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen &#40;vollständiges Wiederherstellungsmodell&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="2f254-121">For information about how to insert a mark into a transaction that spans multiple databases, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-recovering-to-a-mark"></a><span data-ttu-id="2f254-122">Transact-SQL-Syntax für das Wiederherstellen bis zu einer Markierung</span><span class="sxs-lookup"><span data-stu-id="2f254-122">Transact-SQL Syntax for Recovering to a Mark</span></span>  
 <span data-ttu-id="2f254-123">Wenn Sie das Ziel einer markierten Transaktion mithilfe einer[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)-Anweisung festlegen, können Sie eine der folgenden Klauseln verwenden, um ein Anhalten bei oder unmittelbar vor der Markierung zu bewirken:</span><span class="sxs-lookup"><span data-stu-id="2f254-123">When you target a marked transaction by using a[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)statement, you can use one the following clauses to stop at or immediately before the mark:</span></span>  
  
-   <span data-ttu-id="2f254-124">Verwenden Sie die WITH STOPATMARK = **' *`<mark_name>`* '** -Klausel, um anzugeben, dass die markierte Transaktion der Wiederherstellungspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="2f254-124">Use the WITH STOPATMARK = **'*`<mark_name>`*'** clause to specify that the marked transaction is the recovery point.</span></span>  
  
     <span data-ttu-id="2f254-125">STOPATMARK führt ein Rollforward bis zur Markierung aus und schließt die markierte Transaktion in das Rollforward ein.</span><span class="sxs-lookup"><span data-stu-id="2f254-125">STOPATMARK rolls forward to the mark and includes the marked transaction in the roll forward.</span></span>  
  
-   <span data-ttu-id="2f254-126">Verwenden Sie die with STOPBEFOREMARK = **' *`<mark_name>`* '** -Klausel, um anzugeben, dass der Protokolldaten Satz unmittelbar vor der Markierung der Wiederherstellungspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="2f254-126">Use the WITH STOPBEFOREMARK = **'*`<mark_name>`*'** clause to specify that the log record that is immediately before the mark is the recovery point.</span></span>  
  
     <span data-ttu-id="2f254-127">STOPBEFOREMARK führt ein Rollforward bis zur Markierung aus und schließt die markierte Transaktion aus dem Rollforward aus.</span><span class="sxs-lookup"><span data-stu-id="2f254-127">STOPBEFOREMARK rolls forward to the mark and excludes marked the transaction from the roll forward.</span></span>  
  
 <span data-ttu-id="2f254-128">Die Optionen STOPATMARK und STOPBEFOREMARK unterstützen beide eine optionale AFTER *datetime* -Klausel.</span><span class="sxs-lookup"><span data-stu-id="2f254-128">The STOPATMARK and STOPBEFOREMARK options both support an optional AFTER *datetime* clause.</span></span> <span data-ttu-id="2f254-129">Wenn *datetime* verwendet wird, müssen die Markierungsnamen nicht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2f254-129">When *datetime* is used, mark names do not have to be unique.</span></span>  
  
 <span data-ttu-id="2f254-130">Wenn AFTER *datetime* nicht angegeben ist, wird der Rollforward bei der ersten Markierung mit dem angegebenen Namen beendet.</span><span class="sxs-lookup"><span data-stu-id="2f254-130">If AFTER *datetime* is omitted, roll forward stops at the first mark that has the specified name.</span></span> <span data-ttu-id="2f254-131">Wenn AFTER *datetime* angegeben ist, wird der Rollforward bei der ersten Markierung beendet, die den angegebenen Namen genau um oder nach *datetime*aufweist.</span><span class="sxs-lookup"><span data-stu-id="2f254-131">If AFTER *datetime* is specified, roll forward stops at the first mark that has the specified name, exactly at or after *datetime*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f254-132">Wie bei jedem Wiederherstellungsvorgang bis zu einem bestimmten Zeitpunkt ist das Wiederherstellen bis zu einer Markierung nicht zulässig in Zeiten, in denen für die Datenbank massenprotokollierte Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f254-132">As in all point-in-time restore operations, recovering to a mark is disallowed when the database is undergoing operations that are bulk-logged.</span></span>  
  
 <span data-ttu-id="2f254-133">**So führen Sie eine Wiederherstellung bis zu einer markierten Transaktion aus**</span><span class="sxs-lookup"><span data-stu-id="2f254-133">**To restore to a marked transaction**</span></span>  
  
 [<span data-ttu-id="2f254-134">Wiederherstellen einer Datenbank bis zu einer markierten Transaktion &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2f254-134">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
 [<span data-ttu-id="2f254-135">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f254-135">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
### <a name="preparing-the-log-backups"></a><span data-ttu-id="2f254-136">Vorbereiten der Protokollsicherungen</span><span class="sxs-lookup"><span data-stu-id="2f254-136">Preparing the Log Backups</span></span>  
 <span data-ttu-id="2f254-137">Die folgende Sicherungsstrategie für diese verbundenen Datenbanken wäre in diesem Beispiel angemessen:</span><span class="sxs-lookup"><span data-stu-id="2f254-137">For this example, an appropriate backup strategy for these related databases would be the following:</span></span>  
  
1.  <span data-ttu-id="2f254-138">Verwenden Sie für beide Datenbanken das vollständige Wiederherstellungsmodell.</span><span class="sxs-lookup"><span data-stu-id="2f254-138">Use the full recovery model for both databases.</span></span>  
  
2.  <span data-ttu-id="2f254-139">Erstellen Sie eine vollständige Sicherung jeder einzelnen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2f254-139">Create a full backup of each database.</span></span>  
  
     <span data-ttu-id="2f254-140">Die Datenbanken können nacheinander oder gleichzeitig gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="2f254-140">The databases can be backed up sequentially or simultaneously.</span></span>  
  
3.  <span data-ttu-id="2f254-141">Markieren Sie vor dem Sichern des Transaktionsprotokolls eine Transaktion, die in allen Datenbanken ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f254-141">Before backing up the transaction log, mark a transaction that executes in all databases.</span></span> <span data-ttu-id="2f254-142">Informationen zum Erstellen der markierten Transaktionen finden Sie unter [Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen &#40;vollständiges Wiederherstellungsmodell&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="2f254-142">For information about how to create the marked transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
4.  <span data-ttu-id="2f254-143">Sichern Sie das Transaktionsprotokoll für jede Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2f254-143">Back up the transaction log on each database.</span></span>  
  
### <a name="recovering-the-database-to-a-marked-transaction"></a><span data-ttu-id="2f254-144">Wiederherstellen der Datenbank bis zu einer markierten Transaktion</span><span class="sxs-lookup"><span data-stu-id="2f254-144">Recovering the Database to a Marked Transaction</span></span>  
 <span data-ttu-id="2f254-145">**So stellen Sie die Sicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="2f254-145">**To restore the backup**</span></span>  
  
1.  <span data-ttu-id="2f254-146">Erstellen Sie nach Möglichkeit [Sicherungen des Protokollfragments](tail-log-backups-sql-server.md) der unbeschädigten Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2f254-146">Create [tail-log backups](tail-log-backups-sql-server.md) of the undamaged databases, if possible.</span></span>  
  
2.  <span data-ttu-id="2f254-147">Stellen Sie die letzte vollständige Datenbanksicherung jeder Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="2f254-147">Restore the most recent full database backup of each database.</span></span>  
  
3.  <span data-ttu-id="2f254-148">Identifizieren Sie die letzte verfügbare markierte Transaktion in allen Transaktionsprotokollsicherungen.</span><span class="sxs-lookup"><span data-stu-id="2f254-148">Identify the most recent marked transaction that is available in all of the transaction log backups.</span></span> <span data-ttu-id="2f254-149">Diese Informationen werden in der **logmarkhistory** -Tabelle in der **msdb** -Datenbank auf dem entsprechenden Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2f254-149">This information is stored in the **logmarkhistory** table in the **msdb** database on each server.</span></span>  
  
4.  <span data-ttu-id="2f254-150">Identifizieren Sie die Protokollsicherungen für alle verbundenen Datenbanken, die diese Markierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="2f254-150">Identify the log backups for all related databases that contain this mark.</span></span>  
  
5.  <span data-ttu-id="2f254-151">Stellen Sie jede Protokollsicherung bis zur markierten Transaktion wieder her.</span><span class="sxs-lookup"><span data-stu-id="2f254-151">Restore each log backup, stopping at the marked transaction.</span></span>  
  
6.  <span data-ttu-id="2f254-152">Stellen Sie jede Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="2f254-152">Recover each database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f254-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f254-153">See Also</span></span>  
 <span data-ttu-id="2f254-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f254-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="2f254-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f254-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="2f254-156">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f254-156">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="2f254-157">[Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen &#40;vollständiges Wiederherstellungsmodell&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span><span class="sxs-lookup"><span data-stu-id="2f254-157">[Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span></span>  
 <span data-ttu-id="2f254-158">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f254-158">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="2f254-159">[Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="2f254-159">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="2f254-160">Planen und Ausführen von Wiederherstellungssequenzen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="2f254-160">Plan and Perform Restore Sequences &#40;Full Recovery Model&#41;</span></span>](plan-and-perform-restore-sequences-full-recovery-model.md)  
  
  
