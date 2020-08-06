---
title: 'Beispiel: Offline Wiederherstellung der primären und einer anderen Datei Gruppe (vollständiges Wiederherstellungs Modell) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f845927fdd74fba476139fccbf9a5fa112d434e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621520"
---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a><span data-ttu-id="18001-102">Beispiel: Offlinewiederherstellung der primären Dateigruppe und einer weiteren Dateigruppe (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="18001-102">Example: Offline Restore of Primary and One Other Filegroup (Full Recovery Model)</span></span>
  <span data-ttu-id="18001-103">Dieses Thema ist nur für Datenbanken relevant, in denen mehrere Dateigruppen enthalten sind und für die das vollständige Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="18001-103">This topic is relevant only for databases under the full recovery model that contain multiple filegroups.</span></span>  
  
 <span data-ttu-id="18001-104">In diesem Beispiel sind in der Datenbank `adb` drei Dateigruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="18001-104">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="18001-105">Die Dateigruppen `A` und `C` weisen Lese-/Schreibzugriff auf, und die Dateigruppe `B` ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="18001-105">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="18001-106">Die primäre Dateigruppe und die Dateigruppe `B` sind beschädigt, die Dateigruppen `A` und `C` sind jedoch intakt.</span><span class="sxs-lookup"><span data-stu-id="18001-106">The primary filegroup and filegroup `B` are damaged, but filegroups `A` and `C` are intact.</span></span> <span data-ttu-id="18001-107">Vor dem Notfall waren alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="18001-107">Before the disaster, all the filegroups were online.</span></span>  
  
 <span data-ttu-id="18001-108">Der Datenbankadministrator entscheidet sich, die primäre Dateigruppe und Dateigruppe `B`wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="18001-108">The database administrator decides to restore and recover the primary filegroup and filegroup `B`.</span></span> <span data-ttu-id="18001-109">Für die Datenbank wird das vollständige Wiederherstellungsmodell verwendet, weshalb vor dem Beginn der Wiederherstellung eine Protokollfragmentsicherung der Datenbank erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="18001-109">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="18001-110">Wenn die Datenbank online geschaltet wird, werden die Dateigruppen `A` und `C` automatisch online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="18001-110">When the database comes on line, Filegroups `A` and `C` are automatically brought online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18001-111">Die Offlinewiederherstellungssequenz verfügt über weniger Schritte als die Onlinewiederherstellung einer schreibgeschützten Datei.</span><span class="sxs-lookup"><span data-stu-id="18001-111">The offline restore sequence has fewer steps than an online restore of a read-only file.</span></span> <span data-ttu-id="18001-112">Ein Beispiel finden Sie unter [Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;Vollständiges Wiederherstellungsmodell&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="18001-112">For an example, see [Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span></span> <span data-ttu-id="18001-113">Die gesamte Datenbank ist jedoch für die Dauer der Wiederherstellungssequenz offline.</span><span class="sxs-lookup"><span data-stu-id="18001-113">However, the whole database is offline for the duration of the sequence.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="18001-114">Sicherung des Protokollfragments</span><span class="sxs-lookup"><span data-stu-id="18001-114">Tail-Log Backup</span></span>  
 <span data-ttu-id="18001-115">Vor dem Wiederherstellen der Datenbank muss der Datenbankadministrator das Protokollfragment sichern.</span><span class="sxs-lookup"><span data-stu-id="18001-115">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="18001-116">Weil die Datenbank beschädigt ist, muss zum Erstellen der Sicherung des Protokollfragments die NO_TRUNCATE-Option verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="18001-116">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="18001-117">Bei der Sicherung des Protokollfragments handelt es sich um die letzte Sicherung im Rahmen der folgenden Wiederherstellungssequenzen.</span><span class="sxs-lookup"><span data-stu-id="18001-117">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="18001-118">Wiederherstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="18001-118">Restore Sequence</span></span>  
 <span data-ttu-id="18001-119">Zum Wiederherstellen der primären Dateigruppe und der Dateigruppe `B`verwendet der Datenbankadministrator die Wiederherstellungssequenz ohne die Option PARTIAL folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="18001-119">To restore the primary filegroup and filegroup `B`, the database administrator uses a restore sequence without the PARTIAL option, as follows:</span></span>  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 <span data-ttu-id="18001-120">Die nicht wiederhergestellten Dateien werden automatisch online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="18001-120">The files that are not restored are automatically brought online.</span></span> <span data-ttu-id="18001-121">Alle Dateigruppen sind jetzt online.</span><span class="sxs-lookup"><span data-stu-id="18001-121">All the filegroups are now online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18001-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18001-122">See Also</span></span>  
 <span data-ttu-id="18001-123">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="18001-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="18001-124">[Schrittweise Wiederherstellungen &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="18001-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="18001-125">[Dateiwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="18001-125">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="18001-126">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="18001-126">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="18001-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18001-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
