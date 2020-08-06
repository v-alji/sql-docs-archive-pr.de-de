---
title: Dateiwiederherstellungen (einfaches Wiederherstellungsmodell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- simple recovery model [SQL Server]
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- Transact-SQL restore sequence
- restoring files [SQL Server], simple recovery model
- file restores [SQL Server], simple recovery model
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: b6d07386-7c6f-4cc6-be32-93289adbd3d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ed48f48f531e727de5d6e1403ef47f5399f874d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699830"
---
# <a name="file-restores-simple-recovery-model"></a><span data-ttu-id="7ac0e-102">Dateiwiederherstellungen (einfaches Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="7ac0e-102">File Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="7ac0e-103">Dieses Thema betrifft nur Datenbanken, die auf dem einfachen Wiederherstellungsmodell basieren und mindestens eine schreibgeschützte sekundäre Dateigruppe enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-103">This topic is relevant only for simple-model databases that contain at least one read-only secondary filegroup.</span></span>  
  
 <span data-ttu-id="7ac0e-104">Das Ziel einer Dateiwiederherstellung besteht darin, eine oder mehrere beschädigte Dateien wiederherzustellen, ohne dabei die gesamte Datenbank wiederherstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="7ac0e-105">Beim einfachen Wiederherstellungsmodell werden Dateisicherungen nur für schreibgeschützte Dateien unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-105">Under the simple recovery model, file backups are supported only for read-only files.</span></span> <span data-ttu-id="7ac0e-106">Die primäre Dateigruppe und die sekundären Dateigruppen mit Lese-/Schreibzugriff werden immer zusammen wiederhergestellt (durch Wiederherstellen einer Datenbank- oder Teilsicherung).</span><span class="sxs-lookup"><span data-stu-id="7ac0e-106">The primary filegroup and read/write secondary filegroups are always restored together, by restoring a database or partial backup.</span></span>  
  
 <span data-ttu-id="7ac0e-107">Für die Dateiwiederherstellung sind folgende Szenarien möglich:</span><span class="sxs-lookup"><span data-stu-id="7ac0e-107">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="7ac0e-108">Offlinedateiwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="7ac0e-108">Offline file restore</span></span>  
  
     <span data-ttu-id="7ac0e-109">Bei einer *Offlinedateiwiederherstellung*ist die Datenbank offline, während die beschädigten Dateien oder Dateigruppen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-109">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="7ac0e-110">Am Ende der Wiederherstellungssequenz wird die Datenbank wieder online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-110">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="7ac0e-111">Offlinewiederherstellungen werden von allen Editionen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-111">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="7ac0e-112">Onlinedateiwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="7ac0e-112">Online file restore</span></span>  
  
     <span data-ttu-id="7ac0e-113">Bei einer *Onlinedateiwiederherstellung*bleibt die Datenbank online, wenn die Datenbank während einer Dateiwiederherstellung online ist.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-113">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="7ac0e-114">Dateigruppen, in denen eine Datei wiederhergestellt wird, sind während des Wiederherstellungsvorgangs jedoch offline.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-114">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="7ac0e-115">Sobald die Dateien einer Offlinedateigruppe wiederhergestellt sind, wird die Dateigruppe automatisch wieder online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-115">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="7ac0e-116">Informationen zur Unterstützung von Onlinewiederherstellungen von Seiten und Dateien finden Sie unter [Von den SQL Server 2014-Editionen unterstützte Funktionen](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7ac0e-116">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="7ac0e-117">Weitere Informationen zur Onlinewiederherstellung finden Sie unter [Onlinewiederherstellung &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ac0e-117">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="7ac0e-118">Wenn Sie möchten, dass die Datenbank für eine Dateiwiederherstellung offline ist, können Sie die Datenbank vor dem Starten der Wiederherstellungssequenz offline schalten, indem Sie die folgende [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)-Anweisung ausführen: ALTER DATABASE *Datenbankname* SET OFFLINE</span><span class="sxs-lookup"><span data-stu-id="7ac0e-118">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  

  
##  <a name="overview-of-file-and-filegroup-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="7ac0e-119">Übersicht über Datei- und Dateigruppenwiederherstellung mit dem einfachen Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="7ac0e-119">Overview of File and Filegroup Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="7ac0e-120">Ein Dateiwiederherstellungsszenario besteht aus einer einzelnen Wiederherstellungssequenz, bei der die geeigneten Daten kopiert, ein Rollforward ausgeführt und die Daten anschließend wiederhergestellt werden:</span><span class="sxs-lookup"><span data-stu-id="7ac0e-120">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data as follows:</span></span>  
  
1.  <span data-ttu-id="7ac0e-121">Jede beschädigte Datei wird von der letzten Dateisicherung wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-121">Restore each damaged file from its most recent file backup.</span></span>  
  
2.  <span data-ttu-id="7ac0e-122">Für jede wiederhergestellte Datei wird die letzte differenzielle Dateisicherung und dann die Datenbank wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-122">Restore the most recent differential file backup for each restored file and recover the database.</span></span>  
  
### <a name="transact-sql-steps-for-file-restore-sequence-simple-recovery-model"></a><span data-ttu-id="7ac0e-123">Transact-SQL-Schritte für die Dateiwiederherstellungssequenz (einfaches Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="7ac0e-123">Transact-SQL Steps for File Restore Sequence (Simple Recovery Model)</span></span>  
 <span data-ttu-id="7ac0e-124">In diesem Abschnitt werden die grundlegenden [!INCLUDE[tsql](../../../includes/tsql-md.md)]-[RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)-Optionen für eine einfache Dateiwiederherstellungssequenz erläutert.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-124">This section shows the essential [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a simple file-restore sequence.</span></span> <span data-ttu-id="7ac0e-125">Hierfür unwichtige Syntax und Informationen werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-125">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="7ac0e-126">Die Wiederherstellungssequenz enthält nur zwei [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-126">The restore sequence contains only two [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7ac0e-127">Mit der ersten Anweisung wird unter Verwendung von WITH NORECOVERY eine sekundäre Datei (Datei `A`) wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="7ac0e-127">The first statement restores a secondary file, file `A`, which is restored using WITH NORECOVERY.</span></span> <span data-ttu-id="7ac0e-128">Im zweiten Vorgang werden unter Verwendung von WITH RECOVERY zwei weitere Dateien ( `B` und `C` ) von einem anderen Sicherungsmedium wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="7ac0e-128">The second operation restores two other files, `B` and `C` which are restored using WITH RECOVERY from a different backup device:</span></span>  
  
1.  <span data-ttu-id="7ac0e-129">RESTORE DATABASE *Datenbank* FILE **=** _Name_von_Datei_A_</span><span class="sxs-lookup"><span data-stu-id="7ac0e-129">RESTORE DATABASE *database* FILE **=**_name_of_file_A_</span></span>  
  
     <span data-ttu-id="7ac0e-130">FROM *Dateisicherung_von_Datei_A*</span><span class="sxs-lookup"><span data-stu-id="7ac0e-130">FROM *file_backup_of_file_A*</span></span>  
  
     <span data-ttu-id="7ac0e-131">WITH NORECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="7ac0e-131">WITH NORECOVERY **;**</span></span>  
  
2.  <span data-ttu-id="7ac0e-132">RESTORE DATABASE *Datenbank* FILE **=** _Name_von_Datei_B_ **,** _Name_von_Datei_C_</span><span class="sxs-lookup"><span data-stu-id="7ac0e-132">RESTORE DATABASE *database* FILE **=**_name_of_file_B_**,**_name_of_file_C_</span></span>  
  
     <span data-ttu-id="7ac0e-133">FROM *Dateisicherung_der_Dateien_B_und_C*</span><span class="sxs-lookup"><span data-stu-id="7ac0e-133">FROM *file_backup_of_files_B_and_C*</span></span>  
  
     <span data-ttu-id="7ac0e-134">WITH RECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="7ac0e-134">WITH RECOVERY **;**</span></span>  
  
### <a name="examples"></a><span data-ttu-id="7ac0e-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7ac0e-135">Examples</span></span>  
  
-   [<span data-ttu-id="7ac0e-136">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac0e-136">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="7ac0e-137">Beispiel: Offlinewiederherstellung der primären Dateigruppe und einer weiteren Dateigruppe &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac0e-137">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7ac0e-138">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="7ac0e-138">Related Tasks</span></span>  
 <span data-ttu-id="7ac0e-139">**So stellen Sie Dateien und Dateigruppen wieder her**</span><span class="sxs-lookup"><span data-stu-id="7ac0e-139">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="7ac0e-140">Wiederherstellen von Dateien und Dateigruppen über vorhandene Dateien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac0e-140">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="7ac0e-141">Wiederherstellen von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac0e-141">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="7ac0e-142">Wiederherstellen von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac0e-142">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="7ac0e-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="7ac0e-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="7ac0e-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ac0e-144">See Also</span></span>  
 <span data-ttu-id="7ac0e-145">[Sicherung und Wiederherstellung: Interoperabilität und gleichzeitige Verwendung &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-145">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="7ac0e-146">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-146">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="7ac0e-147">[Vollständige Dateisicherungen &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-147">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="7ac0e-148">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="7ac0e-149">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-149">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="7ac0e-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="7ac0e-151">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="7ac0e-151">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="7ac0e-152">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac0e-152">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
