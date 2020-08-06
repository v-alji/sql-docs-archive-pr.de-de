---
title: 'Beispiel: Schrittweise Wiederherstellung einer Datenbank (vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- piecemeal restores [SQL Server], full recovery model
- restore sequences [SQL Server], piecemeal
ms.assetid: 0a84892d-2f7a-4e77-b2d0-d68b95595210
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfccccdbdc0c4fb3b189ee0a9fa3aeaf426578b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720098"
---
# <a name="example-piecemeal-restore-of-database-full-recovery-model"></a><span data-ttu-id="3104a-102">Beispiel: Schrittweise Wiederherstellung einer Datenbank (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="3104a-102">Example: Piecemeal Restore of Database (Full Recovery Model)</span></span>
  <span data-ttu-id="3104a-103">Bei einer schrittweisen Wiederherstellungssequenz wird die Datenbank auf Dateigruppenebene stufenweise wiederhergestellt, wobei mit den primären Dateigruppen sowie mit den sekundären Dateigruppen mit Lese- und Schreibberechtigung begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="3104a-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read-write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="3104a-104">In diesem Beispiel wird die `adb` -Datenbank nach einem Notfall auf einem neuen Computer wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="3104a-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="3104a-105">Für die Datenbank wird das vollständige Wiederherstellungsmodell verwendet, weshalb vor dem Beginn der Wiederherstellung eine Protokollfragmentsicherung der Datenbank erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="3104a-105">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="3104a-106">Vor dem Notfall sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="3104a-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="3104a-107">Dateigruppe `B` ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="3104a-107">Filegroup `B` is read-only.</span></span> <span data-ttu-id="3104a-108">Alle sekundären Dateigruppen müssen wiederhergestellt werden, aber sie werden in der Reihenfolge ihrer Wichtigkeit wiederhergestellt: `A` (höchste Wichtigkeit), `C`und schließlich `B`.</span><span class="sxs-lookup"><span data-stu-id="3104a-108">All of the secondary filegroups must be restored, but they are restored in order of importance: `A` (highest), `C`, and lastly `B`.</span></span> <span data-ttu-id="3104a-109">In diesem Beispiel gibt es vier Protokollsicherungen, darunter die Protokollfragmentsicherung.</span><span class="sxs-lookup"><span data-stu-id="3104a-109">In this example, there are four log backups, including the tail-log backup.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="3104a-110">Sicherung des Protokollfragments</span><span class="sxs-lookup"><span data-stu-id="3104a-110">Tail-Log Backup</span></span>  
 <span data-ttu-id="3104a-111">Vor dem Wiederherstellen der Datenbank muss der Datenbankadministrator das Protokollfragment sichern.</span><span class="sxs-lookup"><span data-stu-id="3104a-111">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="3104a-112">Weil die Datenbank beschädigt ist, muss zum Erstellen der Sicherung des Protokollfragments die NO_TRUNCATE-Option verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3104a-112">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="3104a-113">Bei der Sicherung des Protokollfragments handelt es sich um die letzte Sicherung im Rahmen der folgenden Wiederherstellungssequenzen.</span><span class="sxs-lookup"><span data-stu-id="3104a-113">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="3104a-114">Wiederherstellen von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="3104a-114">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3104a-115">Die Syntax für eine Onlinewiederherstellungssequenz ist dieselbe wie bei einer Offlinewiederherstellungssequenz.</span><span class="sxs-lookup"><span data-stu-id="3104a-115">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="3104a-116">Teilweise Wiederherstellung der primären und sekundären Dateigruppe `A`.</span><span class="sxs-lookup"><span data-stu-id="3104a-116">Partial restore of the primary and secondary filegroup `A`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
       WITH PARTIAL, NORECOVERY  
    RESTORE DATABASE adb FILEGROUP='A' FROM backup2   
       WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
2.  <span data-ttu-id="3104a-117">Onlinewiederherstellung der Dateigruppe `C`.</span><span class="sxs-lookup"><span data-stu-id="3104a-117">Online restore of filegroup `C`.</span></span>  
  
     <span data-ttu-id="3104a-118">Jetzt sind die primäre Dateigruppe und die sekundäre Dateigruppe `A` online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3104a-118">At this point, the primary filegroup and secondary filegroup `A` are online.</span></span> <span data-ttu-id="3104a-119">Für die Dateien in den Dateigruppen `B` und `C` steht die Wiederherstellung noch aus, d. h., die Dateigruppen sind noch offline.</span><span class="sxs-lookup"><span data-stu-id="3104a-119">All the files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
     <span data-ttu-id="3104a-120">In Meldungen aus der letzten `RESTORE LOG` -Anweisung (in Schritt 1) wird darauf hingewiesen, dass Rollbacks für Transaktionen mit Dateigruppe `C` verzögert werden, da die Dateigruppe nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3104a-120">Messages from the last `RESTORE LOG` statement in step 1 indicate that rollback of transactions that involve filegroup `C` was deferred, because this filegroup is not available.</span></span> <span data-ttu-id="3104a-121">Normale Vorgänge können zwar fortgesetzt werden, allerdings werden durch die Transaktionen Sperren eingerichtet, und Protokollkürzungen sind erst nach Abschluss des Rollbacks möglich.</span><span class="sxs-lookup"><span data-stu-id="3104a-121">Regular operations can continue, but locks are held by these transactions and log truncation will not occur until the rollback can complete.</span></span>  
  
     <span data-ttu-id="3104a-122">In der zweiten Wiederherstellungssequenz stellt der Administrator die Dateigruppe `C`wieder her:</span><span class="sxs-lookup"><span data-stu-id="3104a-122">In the second restore sequence, the database administrator restores filegroup `C`:</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' FROM backup2a WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="3104a-123">Die primäre Dateigruppe und die Dateigruppen `A` und `C` sind zu diesem Zeitpunkt online.</span><span class="sxs-lookup"><span data-stu-id="3104a-123">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="3104a-124">Für die Dateien in der Dateigruppe `B` steht weiterhin die Wiederherstellung aus; die Dateigruppe ist offline.</span><span class="sxs-lookup"><span data-stu-id="3104a-124">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span> <span data-ttu-id="3104a-125">Die verzögerten Transaktionen wurden aufgelöst, und die Protokollkürzungen werden vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="3104a-125">Deferred transactions have been resolved, and log truncation occurs.</span></span>  
  
3.  <span data-ttu-id="3104a-126">Onlinewiederherstellung der Dateigruppe `B`.</span><span class="sxs-lookup"><span data-stu-id="3104a-126">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="3104a-127">In der dritten Wiederherstellungssequenz stellt der Administrator die Dateigruppe `B`wieder her:</span><span class="sxs-lookup"><span data-stu-id="3104a-127">In the third restore sequence, the database administrator restores filegroup `B`.</span></span> <span data-ttu-id="3104a-128">Die Sicherung von Dateigruppe `B` wurde erstellt, nachdem die Dateigruppe schreibgeschützt wurde. Deshalb muss für diese Dateien bei der Wiederherstellung kein Rollforward ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3104a-128">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, it does not have to be rolled forward during recovery.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup2b WITH RECOVERY  
    ```  
  
     <span data-ttu-id="3104a-129">Alle Dateigruppen sind nun online.</span><span class="sxs-lookup"><span data-stu-id="3104a-129">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="3104a-130">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="3104a-130">Additional Examples</span></span>  
  
-   [<span data-ttu-id="3104a-131">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-131">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="3104a-132">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-132">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="3104a-133">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-133">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="3104a-134">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-134">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="3104a-135">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-135">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="3104a-136">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-136">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="3104a-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3104a-137">See Also</span></span>  
 <span data-ttu-id="3104a-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3104a-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="3104a-139">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3104a-139">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="3104a-140">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3104a-140">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="3104a-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3104a-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="3104a-142">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3104a-142">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
