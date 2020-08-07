---
title: Wiederherstellen einer Datenbank ohne Wiederherstellung von Daten (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], recovery-only
- recovery-only scenario [SQL Server]
- restoring databases [SQL Server], recovery-only
- recovery [SQL Server], recovery-only
- database recovery [SQL Server]
- database restores [SQL Server], recovery-only
- recovery [SQL Server], without restoring data
ms.assetid: 7e8fa620-315d-4e10-a718-23fa5171c09e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 04e4f78e51adb803bb65530c0b3b903aa7f76419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620476"
---
# <a name="recover-a-database-without-restoring-data-transact-sql"></a><span data-ttu-id="c6b9c-102">Wiederherstellen einer Datenbank ohne Wiederherstellung von Daten (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6b9c-102">Recover a Database Without Restoring Data (Transact-SQL)</span></span>
  <span data-ttu-id="c6b9c-103">Normalerweise werden alle Daten in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank wiederhergestellt, bevor die Datenbank wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-103">Usually, all of the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is restored before the database is recovered.</span></span> <span data-ttu-id="c6b9c-104">Ein Wiederherstellungsvorgang kann jedoch eine Datenbank wiederherstellen, ohne dabei eine Sicherung wiederherzustellen, z. B. beim Wiederherstellen einer schreibgeschützten Datei, die mit der Datenbank konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-104">However, a restore operation can recover a database without actually restoring a backup; for example, when recovering a read-only file that is consistent with the database.</span></span> <span data-ttu-id="c6b9c-105">Dies wird als *reine Wiederherstellung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-105">This is referred to as a *recovery-only restore*.</span></span> <span data-ttu-id="c6b9c-106">Wenn Offlinedaten bereits mit der Datenbank konsistent sind und nur zur Verfügung gestellt werden müssen, stellt die reine Wiederherstellung die Datenbank wieder her und schaltet die Daten online.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-106">When offline data is already consistent with the database and needs only to be made available, a recovery-only restore operation completes the recovery of the database and bring the data online.</span></span>  
  
 <span data-ttu-id="c6b9c-107">Eine reine Wiederherstellung kann für eine ganze Datenbank oder Dateien bzw. Dateigruppen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-107">A recovery-only restore can occur for a whole database or for one or more a files or filegroups.</span></span>  
  
## <a name="recovery-only-database-restore"></a><span data-ttu-id="c6b9c-108">Reine Datenbankwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c6b9c-108">Recovery-Only Database Restore</span></span>  
 <span data-ttu-id="c6b9c-109">Eine reine Datenbankwiederherstellung kann in den folgenden Situationen hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="c6b9c-109">A recovery-only database restore can be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="c6b9c-110">Sie haben die Datenbank beim Speichern der letzten Sicherung in einer Wiederherstellungssequenz nicht wiederhergestellt und möchten jetzt die Datenbank wiederherstellen, um diese online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-110">You did not recover the database when restoring the last backup in a restore sequence, and you now want to recover the database to bring it online.</span></span>  
  
-   <span data-ttu-id="c6b9c-111">Die Datenbank befindet sich im Standbymodus, und Sie möchten, dass die Datenbank aktualisierbar ist, ohne dass eine weitere Protokollsicherung angewendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-111">The database is in standby mode, and you want to make the database updatable without applying another log backup.</span></span>  
  
 <span data-ttu-id="c6b9c-112">Die [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Syntax für eine reine Datenbankwiederherstellung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c6b9c-112">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only database restore is as follows:</span></span>  
  
 <span data-ttu-id="c6b9c-113">RESTORE DATABASE *database_name* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="c6b9c-113">RESTORE DATABASE *database_name* WITH RECOVERY</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6b9c-114">Die FROM **=** \<*backup_device>\*-Klausel wird für reine Wiederherstellungsvorgänge nicht verwendet, weil keine Sicherung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-114">The FROM **=** \<*backup_device>\* clause is not used for recovery-only restores because no backup is necessary.</span></span>  
  
 <span data-ttu-id="c6b9c-115">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="c6b9c-115">**Example**</span></span>  
  
 <span data-ttu-id="c6b9c-116">Im folgenden Beispiel wird die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank ohne die zugehörigen Daten wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-116">The following example recovers the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in a restore operation without restoring data.</span></span>  
  
```  
-- Restore database using WITH RECOVERY.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY  
```  
  
## <a name="recovery-only-file-restore"></a><span data-ttu-id="c6b9c-117">Reine Dateiwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c6b9c-117">Recovery-Only File Restore</span></span>  
 <span data-ttu-id="c6b9c-118">Eine reine Dateiwiederherstellung kann in der folgenden Situation hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="c6b9c-118">A recovery-only file restore can be useful in the following situation:</span></span>  
  
 <span data-ttu-id="c6b9c-119">Eine Datenbank wird schrittweise wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-119">A database is restored piecemeal.</span></span> <span data-ttu-id="c6b9c-120">Nach Abschluss der Wiederherstellung der primären Dateigruppe sind eine oder mehrere der nicht wiederhergestellten Dateien mit dem neuen Datenbankstatus konsistent, weil sie vielleicht einige Zeit schreibgeschützt waren.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-120">After restore of the primary filegroup is complete, one or more of the unrestored files are consistent with the new database state, perhaps because it has been read-only for some time.</span></span> <span data-ttu-id="c6b9c-121">Diese Dateien müssen lediglich wiederhergestellt werden. Das Kopieren von Daten ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-121">These files only have to be recovered; data copying is unnecessary.</span></span>  
  
 <span data-ttu-id="c6b9c-122">Bei einem reinen Wiederherstellungsvorgang werden die Daten in der Offlinedateigruppe wieder online geschaltet; es erfolgt keine Datenkopierphase, kein Wiederholen (Rollforwardphase) oder Rückgängig machen (Rollbackphase).</span><span class="sxs-lookup"><span data-stu-id="c6b9c-122">A recovery-only restore operation brings the data in the offline filegroup online; no data-copy, redo, or undo phase occurs.</span></span> <span data-ttu-id="c6b9c-123">Informationen zu den Wiederherstellungsphasen finden Sie unter [Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6b9c-123">For information about the phases of restore, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
 <span data-ttu-id="c6b9c-124">Die [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Syntax für eine reine Dateiwiederherstellung lautet:</span><span class="sxs-lookup"><span data-stu-id="c6b9c-124">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only file restore is:</span></span>  
  
 <span data-ttu-id="c6b9c-125">Datenbank *database_name* {Datei **=** _logical_file_name_ wiederherstellen | Datei Gruppe **=** _logical_filegroup_name_ } [ **,**... *n* ] mit Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c6b9c-125">RESTORE DATABASE *database_name* { FILE **=**_logical_file_name_ | FILEGROUP **=**_logical_filegroup_name_ }[ **,**...*n* ] WITH RECOVERY</span></span>  
  
 <span data-ttu-id="c6b9c-126">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="c6b9c-126">**Example**</span></span>  
  
 <span data-ttu-id="c6b9c-127">Im folgenden Beispiel wird eine reine Dateiwiederherstellung der Dateien in einer sekundären Dateigruppe ( `SalesGroup2`) in der `Sales` -Datenbank veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-127">The following example illustrates a recovery-only file restore of the files in a secondary filegroup, `SalesGroup2`, in the `Sales` database.</span></span> <span data-ttu-id="c6b9c-128">Die primäre Dateigruppe wurde bereits zu Beginn der schrittweisen Wiederherstellung gespeichert, und `SalesGroup2` ist konsistent mit der wiederhergestellten primären Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-128">The primary filegroup has already been restored as the initial step of a piecemeal restore, and `SalesGroup2` is consistent with the restored primary filegroup.</span></span> <span data-ttu-id="c6b9c-129">Es ist nur eine einzige Anweisung erforderlich, um die Dateigruppe wiederherzustellen und online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="c6b9c-129">Recovering this filegroup and bringing it online requires only a single statement.</span></span>  
  
```  
RESTORE DATABASE Sales FILEGROUP=SalesGroup2 WITH RECOVERY;  
```  
  
## <a name="examples-of-completing-a-piecemeal-restore-scenario-with-a-recovery-only-restore"></a><span data-ttu-id="c6b9c-130">Beispiele zum Abschließen von schrittweisen Wiederherstellungsszenarien mit einer reinen Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c6b9c-130">Examples of Completing a Piecemeal Restore Scenario with a Recovery-Only Restore</span></span>  
 <span data-ttu-id="c6b9c-131">**Einfaches Wiederherstellungsmodell**</span><span class="sxs-lookup"><span data-stu-id="c6b9c-131">**Simple recovery model**</span></span>  
  
-   [<span data-ttu-id="c6b9c-132">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b9c-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c6b9c-133">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b9c-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
 <span data-ttu-id="c6b9c-134">**Vollständiges Wiederherstellungsmodell**</span><span class="sxs-lookup"><span data-stu-id="c6b9c-134">**Full recovery model**</span></span>  
  
-   [<span data-ttu-id="c6b9c-135">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b9c-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="c6b9c-136">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b9c-136">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
## <a name="see-also"></a><span data-ttu-id="c6b9c-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6b9c-137">See Also</span></span>  
 <span data-ttu-id="c6b9c-138">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6b9c-138">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="c6b9c-139">[Schrittweise Wiederherstellungen &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6b9c-139">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="c6b9c-140">[Dateiwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c6b9c-140">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="c6b9c-141">[Dateiwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c6b9c-141">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="c6b9c-142">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b9c-142">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
