---
title: Verwalten der Größe der Transaktionsprotokolldatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], size management
ms.assetid: 3a70e606-303f-47a8-96d4-2456a18d4297
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 219ba0605d60bab0b13675f7f9f7ff01cace5755
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616535"
---
# <a name="manage-the-size-of-the-transaction-log-file"></a><span data-ttu-id="4b1be-102">Verwalten der Größe der Transaktionsprotokolldatei</span><span class="sxs-lookup"><span data-stu-id="4b1be-102">Manage the Size of the Transaction Log File</span></span>
  <span data-ttu-id="4b1be-103">In einigen Fällen kann sich das physische Verkleinern oder Vergrößern der physischen Protokolldatei des Transaktionsprotokolls einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank als nützlich erweisen.</span><span class="sxs-lookup"><span data-stu-id="4b1be-103">In some cases, it can be useful to physically shrink or expand the physical log file of the transaction log of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="4b1be-104">Dieses Thema enthält Informationen zum Überwachen der Größe eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Transaktionsprotokolls, Verkleinern des Transaktionsprotokolls, Hinzufügen oder Vergrößern einer Transaktionsprotokolldatei, Optimieren der Wachstumsrate des **tempdb** -Transaktionsprotokolls und Steuern der Vergrößerung einer Transaktionsprotokolldatei.</span><span class="sxs-lookup"><span data-stu-id="4b1be-104">This topic contains information about how to monitor the size of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, shrink the transaction log, add or enlarge a transaction log file, optimize the **tempdb** transaction log growth rate, and control the growth of a transaction log file.</span></span>  
  
  
##  <a name="monitor-log-space-use"></a><a name="MonitorSpaceUse"></a><span data-ttu-id="4b1be-105">Überwachen des Protokoll Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="4b1be-105">Monitor Log Space Use</span></span>  
 <span data-ttu-id="4b1be-106">Der Protokollspeicherplatz kann mit DBCC SQLPERF (LOGSPACE) überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="4b1be-106">You can monitor log space use by using DBCC SQLPERF (LOGSPACE).</span></span> <span data-ttu-id="4b1be-107">Dieser Befehl gibt Informationen zum derzeit belegten Protokollspeicherplatz zurück und zeigt an, wann das Transaktionsprotokoll abgeschnitten werden muss.</span><span class="sxs-lookup"><span data-stu-id="4b1be-107">This command returns information about the amount of log space currently used and indicates when the transaction log is in need of truncation.</span></span> <span data-ttu-id="4b1be-108">Weitere Informationen finden Sie unter [DBCC SQLPERF &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-sqlperf-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b1be-108">For more information, see [DBCC SQLPERF &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-sqlperf-transact-sql).</span></span> <span data-ttu-id="4b1be-109">Informationen zur aktuellen Größe einer Protokolldatei, ihrer maximalen Größe sowie der für die Datei festgelegten automatischen Vergrößerungsoption können Sie auch den Spalten **size**, **max_size**, and **growth** für die betreffende Protokolldatei in **sys.database_files** entnehmen.</span><span class="sxs-lookup"><span data-stu-id="4b1be-109">For information about the current size of a log file, its maximum size, and the autogrow option for the file, you can also use the **size**, **max_size**, and **growth** columns for that log file in **sys.database_files**.</span></span> <span data-ttu-id="4b1be-110">Weitere Informationen finden Sie unter [sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b1be-110">For more information, see [sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b1be-111">Vermeiden Sie das Überlasten des Protokolldatenträgers.</span><span class="sxs-lookup"><span data-stu-id="4b1be-111">We recommend that you avoid overloading the log disk.</span></span>  
  
  
##  <a name="shrink-the-size-of-the-log-file"></a><a name="ShrinkSize"></a><span data-ttu-id="4b1be-112">Verkleinert die Größe der Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="4b1be-112">Shrink the Size of the Log File</span></span>  
 <span data-ttu-id="4b1be-113">Sie müssen zum Reduzieren der physischen Größe einer physischen Protokolldatei die Protokolldatei verkleinern.</span><span class="sxs-lookup"><span data-stu-id="4b1be-113">To reduce the physical size of a physical log file, you must shrink the log file.</span></span> <span data-ttu-id="4b1be-114">Dies ist nützlich, wenn Sie wissen, dass eine Transaktionsprotokolldatei nicht verwendeten und nicht benötigten Speicherplatz enthält.</span><span class="sxs-lookup"><span data-stu-id="4b1be-114">This is useful if you know that a transaction log file contains unused space that you will not be needing.</span></span> <span data-ttu-id="4b1be-115">Das Verkleinern einer Protokolldatei kann nur stattfinden, wenn die Datenbank online und mindestens eine virtuelle Protokolldatei frei ist.</span><span class="sxs-lookup"><span data-stu-id="4b1be-115">Shrinking a log file can occur only while the database is online and, also, at least one virtual log file is free.</span></span> <span data-ttu-id="4b1be-116">In einigen Fällen ist eine Verkleinerung des Protokolls möglicherweise erst nach der nächsten Protokollkürzung möglich.</span><span class="sxs-lookup"><span data-stu-id="4b1be-116">In some cases, shrinking the log may not be possible until after the next log truncation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b1be-117">Faktoren, wie z. B. lang andauernde Transaktionen, die virtuelle Protokolldateien über einen längeren Zeitraum hinweg aktiv halten, können die Protokollverkleinerung einschränken oder sogar gänzlich verhindern.</span><span class="sxs-lookup"><span data-stu-id="4b1be-117">Factors, such as a long-running transaction, that keep virtual log files active for an extended period can restrict log shrinkage or even prevent the log from shrinking at all.</span></span> <span data-ttu-id="4b1be-118">Informationen zu Faktoren, die eine Protokollkürzung verzögern können, finden Sie unter [Das Transaktionsprotokoll &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4b1be-118">For information about factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
 <span data-ttu-id="4b1be-119">Beim Verkleinern einer Protokolldatei werden virtuelle Protokolldateien entfernt, die keinen Teil des logischen Protokolls enthalten (d. h. *inaktive virtuelle Protokolldateien*).</span><span class="sxs-lookup"><span data-stu-id="4b1be-119">Shrinking a log file removes one or more virtual log files that do not hold any part of the logical log (that is, *inactive virtual log files*).</span></span> <span data-ttu-id="4b1be-120">Beim Verkleinern einer Transaktionsprotokolldatei werden ausreichend viele inaktive, virtuelle Protokolldateien vom Ende der Protokolldatei entfernt, um das Protokoll in etwa auf die Zielgröße zu verkleinern.</span><span class="sxs-lookup"><span data-stu-id="4b1be-120">When a transaction log file is shrunk, enough inactive virtual log files are removed from the end of the log file to reduce the log to approximately the target size.</span></span>  
  
 <span data-ttu-id="4b1be-121">**So verkleinern Sie eine Protokolldatei (ohne die Datenbankdateien zu verkleinern)**</span><span class="sxs-lookup"><span data-stu-id="4b1be-121">**To shrink a log file (without shrinking database files)**</span></span>  
  
-   [<span data-ttu-id="4b1be-122">DBCC SHRINKFILE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b1be-122">DBCC SHRINKFILE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql)  
  
-   [<span data-ttu-id="4b1be-123">Verkleinern einer Datei</span><span class="sxs-lookup"><span data-stu-id="4b1be-123">Shrink a File</span></span>](../databases/shrink-a-file.md)  
  
 <span data-ttu-id="4b1be-124">**So überwachen Sie Protokollverkleinerungsereignisse**</span><span class="sxs-lookup"><span data-stu-id="4b1be-124">**To monitor log-file shrink events**</span></span>  
  
-   <span data-ttu-id="4b1be-125">[Log File Auto Shrink Event Class](../event-classes/log-file-auto-shrink-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="4b1be-125">[Log File Auto Shrink Event Class](../event-classes/log-file-auto-shrink-event-class.md).</span></span>  
  
 `To monitor log space`  
  
-   [<span data-ttu-id="4b1be-126">DBCC SQLPERF &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4b1be-126">DBCC SQLPERF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-sqlperf-transact-sql)  
  
-   <span data-ttu-id="4b1be-127">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) (Informationen finden Sie in den Spalten **size**, **max_size** und **growth** für die Protokolldateien.)</span><span class="sxs-lookup"><span data-stu-id="4b1be-127">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) (See the **size**, **max_size**, and **growth** columns for the log file or files.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b1be-128">Für das Verkleinern von Datenbank- und Protokolldateien kann eine automatische Ausführung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4b1be-128">Shrinking database and log files can be set to occur automatically.</span></span> <span data-ttu-id="4b1be-129">Es wird jedoch von einer automatischen Verkleinerung abgeraten, und die `autoshrink`-Datenbankeigenschaft ist in den Standardeinstellungen auf FALSE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4b1be-129">However, we recommend against automatic shrinking, and the `autoshrink` database property is set to FALSE by default.</span></span> <span data-ttu-id="4b1be-130">Wenn `autoshrink` auf TRUE festgelegt ist, wird die Größe einer Datei nur dann automatisch verkleinert, wenn mehr als 25 Prozent des Speicherplatzes ungenutzt sind.</span><span class="sxs-lookup"><span data-stu-id="4b1be-130">If `autoshrink` is set to TRUE, automatic shrinking reduces the size of a file only when more than 25 percent of its space is unused.</span></span> <span data-ttu-id="4b1be-131">Die Datei wird entweder auf eine Größe verkleinert, bei der 25 Prozent der Datei aus nicht verwendetem Speicherplatz bestehen, oder auf die ursprüngliche Dateigröße, je nachdem, welcher Wert größer ist.</span><span class="sxs-lookup"><span data-stu-id="4b1be-131">The file is shrunk either to the size at which only 25 percent of the file is unused space or to the original size of the file, whichever is larger.</span></span> <span data-ttu-id="4b1be-132">Weitere Informationen zum Ändern der Einstellung der `autoshrink` -Eigenschaft finden Sie unter [anzeigen oder Ändern der Eigenschaften einer Datenbank](../databases/view-or-change-the-properties-of-a-database.md): Verwenden Sie die **Automatisches Verkleinern** -Eigenschaft auf der **options** Seite oder [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)-verwenden Sie die AUTO_SHRINK-Option.</span><span class="sxs-lookup"><span data-stu-id="4b1be-132">For information about changing the setting of the `autoshrink` property, see [View or Change the Properties of a Database](../databases/view-or-change-the-properties-of-a-database.md)-use the **Auto Shrink** property on the **Options** page-or [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)-use the AUTO_SHRINK option.</span></span>  
  
  
##  <a name="add-or-enlarge-a-log-file"></a><a name="AddOrEnlarge"></a><span data-ttu-id="4b1be-133">Hinzufügen oder Vergrößern einer Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="4b1be-133">Add or Enlarge a Log File</span></span>  
 <span data-ttu-id="4b1be-134">Alternativ können Sie auch Speicherplatz schaffen, indem Sie entweder die vorhandene Protokolldatei vergrößern (sofern der Speicherplatz dies zulässt) oder der Datenbank eine neue Protokolldatei hinzufügen, wofür normalerweise ein anderer Datenträger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b1be-134">Alternatively, you can gain space by enlarging the existing log file (if disk space permits) or by adding a log file to the database, typically on a different disk.</span></span>  
  
-   <span data-ttu-id="4b1be-135">Sie können der Datenbank eine Protokolldatei hinzufügen, indem Sie die ADD LOG FILE-Klausel der ALTER DATABASE-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b1be-135">To add a log file to the database, use the ADD LOG FILE clause of the ALTER DATABASE statement.</span></span> <span data-ttu-id="4b1be-136">Durch das Hinzufügen einer Protokolldatei kann das Protokoll vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="4b1be-136">Adding a log file allows the log to grow.</span></span>  
  
-   <span data-ttu-id="4b1be-137">Sie können die Protokolldatei vergrößern, indem Sie die MODIFY FILE-Klausel der ALTER DATABASE-Anweisung verwenden und die SIZE- und MAXSIZE-Syntax angeben.</span><span class="sxs-lookup"><span data-stu-id="4b1be-137">To enlarge the log file, use the MODIFY FILE clause of the ALTER DATABASE statement, specifying the SIZE and MAXSIZE syntax.</span></span> <span data-ttu-id="4b1be-138">Weitere Informationen zu dieser Einstellung finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b1be-138">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
  
##  <a name="optimize-the-size-of-the-tempdb-transaction-log"></a><a name="tempdbOptimize"></a><span data-ttu-id="4b1be-139">Optimieren der Größe des tempdb-Transaktions Protokolls</span><span class="sxs-lookup"><span data-stu-id="4b1be-139">Optimize the Size of the tempdb Transaction Log</span></span>  
 <span data-ttu-id="4b1be-140">Beim Neustarten einer Serverinstanz wird das Transaktionsprotokoll der **tempdb** -Datenbank auf seine ursprüngliche Größe (vor einer automatischen Größenerweiterung) zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4b1be-140">Restarting a server instance resizes the transaction log of the **tempdb** database to its original, pre-autogrow size.</span></span> <span data-ttu-id="4b1be-141">Dies kann eine Leistungsminderung des **tempdb** -Transaktionsprotokolls zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="4b1be-141">This can reduce the performance of the **tempdb** transaction log.</span></span> <span data-ttu-id="4b1be-142">Der damit verbundene Verwaltungsaufwand lässt sich vermeiden, indem Sie nach dem Starten oder erneuten Starten der Serverinstanz die Größe des **tempdb** -Transaktionsprotokolls erhöhen.</span><span class="sxs-lookup"><span data-stu-id="4b1be-142">You can avoid this overhead by increasing the size of the **tempdb** transaction log after starting or restarting the server instance.</span></span> <span data-ttu-id="4b1be-143">Weitere Informationen finden Sie unter [tempdb Database](../databases/tempdb-database.md).</span><span class="sxs-lookup"><span data-stu-id="4b1be-143">For more information, see [tempdb Database](../databases/tempdb-database.md).</span></span>  
  
  
##  <a name="control-the-growth-of-a-transaction-log-file"></a><a name="ControlGrowth"></a><span data-ttu-id="4b1be-144">Steuern der Vergrößerung einer Transaktionsprotokoll Datei</span><span class="sxs-lookup"><span data-stu-id="4b1be-144">Control the Growth of a Transaction Log File</span></span>  
 <span data-ttu-id="4b1be-145">Sie können die [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)-Anweisung verwenden, um die Vergrößerung einer Transaktionsprotokolldatei zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4b1be-145">You can use the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement to manage the growth of a transaction log file.</span></span> <span data-ttu-id="4b1be-146">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b1be-146">Note the following:</span></span>  
  
-   <span data-ttu-id="4b1be-147">Verwenden Sie die Option SIZE, um die aktuelle Dateigröße in KB-, MB-, GB- und TB-Einheiten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4b1be-147">To change the current file size in KB, MB, GB, and TB units, use the SIZE option.</span></span>  
  
-   <span data-ttu-id="4b1be-148">Verwenden Sie die Option FILEGROWTH, um die Vergrößerungsschrittweite zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4b1be-148">To change the growth increment, use the FILEGROWTH option.</span></span> <span data-ttu-id="4b1be-149">Der Wert 0 gibt an, dass die automatische Vergrößerung deaktiviert und kein zusätzlicher Speicherplatz zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="4b1be-149">A value of 0 indicates that automatic growth is set to off and no additional space is permitted.</span></span> <span data-ttu-id="4b1be-150">Die Einstellung der kleinen automatischen Vergrößerungsschrittweite einer Protokolldatei kann ebenfalls die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="4b1be-150">A small autogrowth increment on a log file can reduce performance.</span></span> <span data-ttu-id="4b1be-151">Die Schrittweite für die Dateivergrößerung sollte für eine Protokolldatei stets groß genug sein, um häufige Erweiterungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4b1be-151">The file growth increment on a log file should be sufficiently large to avoid frequent expansion.</span></span> <span data-ttu-id="4b1be-152">Die standardmäßige Vergrößerungsschrittweite von 10 Prozent ist hierfür im Allgemeinen gut geeignet.</span><span class="sxs-lookup"><span data-stu-id="4b1be-152">The default growth increment of 10 percent is generally suitable.</span></span>  
  
     <span data-ttu-id="4b1be-153">Informationen zum Ändern der Eigenschaft für die Datei Vergrößerung in einer Protokolldatei finden Sie unter [ALTER DATABASE &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b1be-153">For information on changing the file-growth property on a log file, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="4b1be-154">Verwenden Sie die Option MAXSIZE, um die maximale Größe einer Protokolldatei in KB-, MB-, GB- und TB-Einheiten zu steuern oder die Vergrößerung auf UNLIMITED festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4b1be-154">To control the maximum the size of a log file in KB, MB, GB, and TB units or to set growth to UNLIMITED, use the MAXSIZE option.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="4b1be-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b1be-155">See Also</span></span>  
 <span data-ttu-id="4b1be-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4b1be-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="4b1be-157">Problembehandlung bei vollen Transaktionsprotokollen &#40;SQL Server-Fehler 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="4b1be-157">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
  