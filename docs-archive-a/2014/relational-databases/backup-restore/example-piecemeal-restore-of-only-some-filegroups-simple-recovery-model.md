---
title: 'Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen (einfaches Wiederherstellungsmodell) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8254ac96a269b6fb433759e5a649bf9df1b7feac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725997"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a><span data-ttu-id="a97ff-102">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen (einfaches Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="a97ff-102">Example: Piecemeal Restore of Only Some Filegroups (Simple Recovery Model)</span></span>
  <span data-ttu-id="a97ff-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken relevant, für die ein einfaches Wiederherstellungsmodell mit einer schreibgeschützten Dateigruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a97ff-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span>  
  
 <span data-ttu-id="a97ff-104">Mit einer schrittweisen Wiederherstellungssequenz wird eine Datenbank phasenweise auf Dateigruppenebene wiederhergestellt, beginnend mit der primären Dateigruppe und allen sekundären Dateigruppen mit Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="a97ff-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="a97ff-105">In diesem Beispiel sind in der Datenbank `adb`, für die das einfache Wiederherstellungsmodell verwendet wird, drei Dateigruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a97ff-105">In this example, a database named `adb`, which uses the simple recovery model, contains three filegroups.</span></span> <span data-ttu-id="a97ff-106">Die Dateigruppe `A` weist Lese-/Schreibzugriff auf, die Dateigruppen `B` und `C` sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="a97ff-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="a97ff-107">Zu Beginn sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="a97ff-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="a97ff-108">Die primäre Dateigruppe und die Dateigruppe `B` der `adb` -Datenbank scheinen beschädigt zu sein. Der Datenbankadministrator beschließt, sie mithilfe einer schrittweisen Wiederherstellungssequenz wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a97ff-108">The primary and filegroup `B` of database `adb` appear to be damaged; therefore, the database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="a97ff-109">Beim einfachen Wiederherstellungsmodell müssen alle Dateigruppen mit Lese-/Schreibzugriff von derselben Teilsicherung wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a97ff-109">Under the simple recovery model, all read/write filegroups must be restored from the same partial backup.</span></span> <span data-ttu-id="a97ff-110">Obwohl die Dateigruppe `A` intakt ist, muss sie mit der primären Dateigruppe wiederhergestellt werden, um sicherzustellen, dass beide konsistent sind (die Datenbank wird bis zu dem Zeitpunkt wiederhergestellt, der zum Ende der letzten Teilsicherung definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="a97ff-110">Although filegroup `A` is intact, it must be restored with the primary filegroup to make sure that they are consistent (the database will be restored to the point in time defined by the end of the last partial backup).</span></span> <span data-ttu-id="a97ff-111">Die Dateigruppe `C` ist intakt, muss jedoch wiederhergestellt werden, damit sie online geschaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a97ff-111">Filegroup `C` is intact, but it must be recovered to bring it online.</span></span> <span data-ttu-id="a97ff-112">Die Dateigruppe `B`ist zwar beschädigt, es sind darin jedoch keine so wichtigen Daten wie in Dateigruppe `C`enthalten. Deshalb wird die Dateigruppe `B` zuletzt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a97ff-112">Filegroup `B`, although damaged, contains less critical data than Filegroup `C`; therefore, `B` will be restored last.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="a97ff-113">Wiederherstellen von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="a97ff-113">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97ff-114">Die Syntax für eine Onlinewiederherstellungssequenz ist dieselbe wie bei einer Offlinewiederherstellungssequenz.</span><span class="sxs-lookup"><span data-stu-id="a97ff-114">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="a97ff-115">Teilwiederherstellung der primären Dateigruppe und der Dateigruppe `A` von einer Teilsicherung.</span><span class="sxs-lookup"><span data-stu-id="a97ff-115">Partial restore of the primary and filegroup `A` from a partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     <span data-ttu-id="a97ff-116">Die primäre Dateigruppe und die Dateigruppe `A` sind zu diesem Zeitpunkt online.</span><span class="sxs-lookup"><span data-stu-id="a97ff-116">At this point the primary filegroup and filegroup `A` are online.</span></span> <span data-ttu-id="a97ff-117">Für Dateien in den Dateigruppen `B` und `C` steht die Wiederherstellung aus, und die Dateigruppen sind offline.</span><span class="sxs-lookup"><span data-stu-id="a97ff-117">Files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
2.  <span data-ttu-id="a97ff-118">Onlinewiederherstellung der Dateigruppe `C`.</span><span class="sxs-lookup"><span data-stu-id="a97ff-118">Online recovery of filegroup `C`.</span></span>  
  
     <span data-ttu-id="a97ff-119">Dateigruppe `C` ist konsistent, weil die Teilsicherung, die weiter oben wiederhergestellt wurde, nach dem Kennzeichnen der Dateigruppe `C` als schreibgeschützt erstellt wurde, obwohl für die Datenbank ein früherer Status wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a97ff-119">Filegroup `C` is consistent because the partial backup that was restored above was taken after filegroup `C` became read-only, although the database was taken back in time by the restore.</span></span> <span data-ttu-id="a97ff-120">Der Datenbankadministrator stellt die Dateigruppe `C`wieder her, ohne die Sicherung wiederherzustellen, um sie online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="a97ff-120">The database administrator recovers the filegroup `C`, without restoring it, to bring it online.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="a97ff-121">Die primäre Dateigruppe und die Dateigruppen `A` und `C` sind zu diesem Zeitpunkt online.</span><span class="sxs-lookup"><span data-stu-id="a97ff-121">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="a97ff-122">Für die Dateien in der Dateigruppe B steht weiterhin die Wiederherstellung aus, wobei die Dateigruppe offline ist.</span><span class="sxs-lookup"><span data-stu-id="a97ff-122">Files in filegroupB remain recovery pending, with the filegroup offline.</span></span>  
  
3.  <span data-ttu-id="a97ff-123">Onlinewiederherstellung der Dateigruppe `B.`</span><span class="sxs-lookup"><span data-stu-id="a97ff-123">Online restore of filegroup `B.`</span></span>  
  
     <span data-ttu-id="a97ff-124">Dateien in der Dateigruppe `B` müssen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a97ff-124">Files in filegroup `B` must be restored.</span></span> <span data-ttu-id="a97ff-125">Der Datenbankadministrator stellt die Sicherung von Dateigruppe `B` wieder her, die erstellt wurde, nachdem die Dateigruppe `B` als schreibgeschützt gekennzeichnet und bevor die Teilsicherung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a97ff-125">The database administrator restores the backup of filegroup `B` taken after filegroup `B` became read-only and before the partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     <span data-ttu-id="a97ff-126">Alle Dateigruppen sind nun online.</span><span class="sxs-lookup"><span data-stu-id="a97ff-126">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="a97ff-127">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="a97ff-127">Additional Examples</span></span>  
  
-   [<span data-ttu-id="a97ff-128">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-128">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a97ff-129">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-129">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a97ff-130">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-130">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="a97ff-131">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-131">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="a97ff-132">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-132">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="a97ff-133">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-133">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="a97ff-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a97ff-134">See Also</span></span>  
 <span data-ttu-id="a97ff-135">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a97ff-135">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="a97ff-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a97ff-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="a97ff-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a97ff-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="a97ff-138">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a97ff-138">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
