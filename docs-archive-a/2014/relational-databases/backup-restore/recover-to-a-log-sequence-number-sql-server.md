---
title: Wiederherstellen zu einer Protokollfolgenummer (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log sequence numbers [SQL Server]
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- LSNs
- database recovery [SQL Server]
- database restores [SQL Server], point in time
ms.assetid: f7b3de5b-198d-448d-8c71-1cdd9239676c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4df55c3468fc009d86cffd58a837d6935f5ce14b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620472"
---
# <a name="recover-to-a-log-sequence-number-sql-server"></a><span data-ttu-id="a6f1d-102">Wiederherstellen zu einer Protokollfolgenummer (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a6f1d-102">Recover to a Log Sequence Number (SQL Server)</span></span>
  <span data-ttu-id="a6f1d-103">Dieses Thema ist nur für Datenbanken relevant, die das vollständige oder das massenprotokollierte Wiederherstellungsmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-103">This topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="a6f1d-104">Sie können eine Protokollfolgenummer (Log Sequence Number, LSN) zum Definieren des Wiederherstellungspunkts für einen Wiederherstellungsvorgang verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-104">You can use a log sequence number (LSN) to define the recovery point for a restore operation.</span></span> <span data-ttu-id="a6f1d-105">Hierbei handelt es sich jedoch um eine auf Anbieter von Tools zugeschnittene Funktion, die nur in speziellen Fällen nutzbringend anzuwenden ist.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-105">However, this is a specialized feature that is intended for tools vendors and is unlikely to be generally useful.</span></span>  
  
##  <a name="overview-of-log-sequence-numbers"></a><a name="LSNs"></a> <span data-ttu-id="a6f1d-106">Übersicht der Protokollfolgenummern</span><span class="sxs-lookup"><span data-stu-id="a6f1d-106">Overview of Log Sequence Numbers</span></span>  
 <span data-ttu-id="a6f1d-107">Mit LSNs wird intern während einer RESTORE-Sequenz der Zeitpunkt nachverfolgt, bis zu dem Daten wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-107">LSNs are used internally during a RESTORE sequence to track the point in time to which data has been restored.</span></span> <span data-ttu-id="a6f1d-108">Wenn eine Sicherung wiederhergestellt wird, werden die Daten bis zu der LSN wiederhergestellt, die dem Zeitpunkt entspricht, an dem die Sicherung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-108">When a backup is restored, the data is restored to the LSN corresponding to the point in time at which the backup was taken.</span></span> <span data-ttu-id="a6f1d-109">Durch differenzielle Sicherungen und Protokollsicherungen wird ein späterer Status der Datenbank wiederhergestellt, was wiederum einer höheren LSN entspricht.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-109">Differential and log backups advance the restored database to a later time, which corresponds to a higher LSN.</span></span>  
  
 <span data-ttu-id="a6f1d-110">Jeder Datensatz im Transaktionsprotokoll wird eindeutig durch eine Protokollfolgenummer (Log Sequence Number, LSN) identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-110">Every record in the transaction log is uniquely identified by a log sequence number (LSN).</span></span> <span data-ttu-id="a6f1d-111">LSNs halten sich an eine bestimmte Reihenfolge. Wenn LSN2 größer als LSN1 ist, erfolgte die durch den Protokolldatensatz von LSN2 beschriebene Änderung nach der durch den Protokolldatensatz von LSN1 beschriebenen Änderung.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-111">LSNs are ordered such that if LSN2 is greater than LSN1, the change described by the log record referred to by LSN2 occurred after the change described by the log record LSN.</span></span>  
  
 <span data-ttu-id="a6f1d-112">Die LSN eines Protokolldatensatzes, bei dem ein wichtiges Ereignis aufgetreten ist, kann zum Erstellen richtiger Wiederherstellungssequenzen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-112">The LSN of a log record at which a significant event occurred can be useful for constructing correct restore sequences.</span></span> <span data-ttu-id="a6f1d-113">Da LSNs geordnet sind, können Sie auf Gleichheit und Ungleichheit (d. h., **\<**, **>** **=** ,) verglichen werden **\<=**, **>=** .</span><span class="sxs-lookup"><span data-stu-id="a6f1d-113">Because LSNs are ordered, they can be compared for equality and inequality (that is, **\<**, **>**, **=**, **\<=**, **>=**).</span></span> <span data-ttu-id="a6f1d-114">Solche Vergleiche sind beim Erstellen von Wiederherstellungssequenzen hilfreich.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-114">Such comparisons are useful when constructing restore sequences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6f1d-115">LSNs sind Werte vom Datentyp `numeric`(25,0).</span><span class="sxs-lookup"><span data-stu-id="a6f1d-115">LSNs are values of data type `numeric`(25,0).</span></span> <span data-ttu-id="a6f1d-116">Arithmetische Operationen (z. B. Addition oder Subtraktion) sind ohne Bedeutung und dürfen für LSNs nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-116">Arithmetic operations (for example, addition or subtraction) are not meaningful and must not be used with LSNs.</span></span>  
  

  
## <a name="viewing-lsns-used-by-backup-and-restore"></a><span data-ttu-id="a6f1d-117">Anzeigen von LSNs, die von der Sicherung und Wiederherstellung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="a6f1d-117">Viewing LSNs Used by Backup and Restore</span></span>  
 <span data-ttu-id="a6f1d-118">Die LSN eines Protokolldatensatzes, bei dem ein bestimmtes Sicherungs- und Wiederherstellungsereignis aufgetreten ist, kann mithilfe der folgenden Methoden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a6f1d-118">The LSN of a log record at which a given backup and restore event occurred is viewable using one or more of the following:</span></span>  
  
-   [<span data-ttu-id="a6f1d-119">backupset</span><span class="sxs-lookup"><span data-stu-id="a6f1d-119">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
-   [<span data-ttu-id="a6f1d-120">backupfile</span><span class="sxs-lookup"><span data-stu-id="a6f1d-120">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)  
  
-   <span data-ttu-id="a6f1d-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="a6f1d-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span></span>  
  
-   [<span data-ttu-id="a6f1d-122">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="a6f1d-122">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="a6f1d-123">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="a6f1d-123">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="a6f1d-124">LSNs werden auch in manchen Meldungstexten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-124">LSNs also appear in some message texts.</span></span>  
  
## <a name="transact-sql-syntax-for-restoring-to-an-lsn"></a><span data-ttu-id="a6f1d-125">Transact-SQL-Syntax für die Wiederherstellung bis zu einer LSN</span><span class="sxs-lookup"><span data-stu-id="a6f1d-125">Transact-SQL Syntax for Restoring to an LSN</span></span>  
 <span data-ttu-id="a6f1d-126">Mithilfe einer [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Anweisung können Sie an oder direkt vor der LSN stoppen, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a6f1d-126">By using a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, you can stop at or immediately before the LSN, as follows:</span></span>  
  
-   <span data-ttu-id="a6f1d-127">Verwenden Sie die Klausel „WITH STOPATMARK **='** lsn: _<lsn_number>_ **'** “, bei der „lsn: *\<lsnNumber>* “ eine Zeichenfolge ist, die festlegt, dass der Protokolldatensatz, der die festgelegte Protokollfolgenummer (LSN) enthält, der Wiederherstellungspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-127">Use the WITH STOPATMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record that contains the specified LSN is the recovery point.</span></span>  
  
     <span data-ttu-id="a6f1d-128">Von STOPATMARK wird ein Rollforward zur LSN ausgeführt und dieser Protokolldatensatz im Rollforward eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-128">STOPATMARK roll forwards to the LSN and includes that log record in the roll forward.</span></span>  
  
-   <span data-ttu-id="a6f1d-129">Verwenden Sie die Klausel „WITH STOPBEFOREMARK **='** lsn: _<lsn_number>_ **'** “, bei der „lsn; *\<lsnNumber>* “ eine Zeichenfolge ist, die festlegt, dass der Protokolldatensatz unmittelbar vor dem Protokolldatensatz mit der festgelegten LSN der Wiederherstellungspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-129">Use the WITH STOPBEFOREMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record immediately before the log record that contains the specified LSN number is the recovery point.</span></span>  
  
     <span data-ttu-id="a6f1d-130">Von STOPBEFOREMARK wird ein Rollforward bis zur LSN ausgeführt und dieser Protokolldatensatz aus dem Rollforward ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-130">STOPBEFOREMARK rolls forward to the LSN and excludes that log record from the roll forward.</span></span>  
  
 <span data-ttu-id="a6f1d-131">Typischerweise wird eine bestimmte Transaktion zum Einschließen oder Ausschließen ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-131">Typically, a specific transaction is selected to be included or excluded.</span></span> <span data-ttu-id="a6f1d-132">Praktisch handelt es sich bei dem angegebenen Protokolldatensatz um einen Transaktionscommitdatensatz, wobei diese Angabe nicht zwingend erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-132">Although not required, in practice, the specified log record is a transaction-commit record.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a6f1d-133">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a6f1d-133">Examples</span></span>  
 <span data-ttu-id="a6f1d-134">In diesem Beispiel wird davon ausgegangen, dass die `AdventureWorks` -Datenbank so geändert wurde, dass das vollständige Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6f1d-134">The following example assumes that the `AdventureWorks` database has been changed to use the full recovery model.</span></span>  
  
```  
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a6f1d-135">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="a6f1d-135">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a6f1d-136">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-136">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="a6f1d-137">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-137">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="a6f1d-138">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-138">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="a6f1d-139">Wiederherstellen einer Datenbank bis zum Fehlerzeitpunkt im vollständigen Wiederherstellungsmodell &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-139">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="a6f1d-140">Wiederherstellen einer Datenbank bis zu einer markierten Transaktion &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-140">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a6f1d-141">Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-141">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6f1d-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6f1d-142">See Also</span></span>  
 <span data-ttu-id="a6f1d-143">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6f1d-143">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="a6f1d-144">[Das Transaktionsprotokoll &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6f1d-144">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="a6f1d-145">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a6f1d-145">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
