---
title: 'Beispiel: Schrittweise Wiederherstellung einer Datenbank (einfaches Wiederherstellungsmodell) | Microsoft-Dokumentation'
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
ms.assetid: 9834b14a-4e56-4654-b190-c2a38624b6b4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69de84fa2ff3a853eb9926549ad4859d2f1ae38e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720095"
---
# <a name="example-piecemeal-restore-of-database-simple-recovery-model"></a><span data-ttu-id="4cadb-102">Beispiel: Schrittweise Wiederherstellung einer Datenbank (einfaches Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="4cadb-102">Example: Piecemeal Restore of Database (Simple Recovery Model)</span></span>
  <span data-ttu-id="4cadb-103">Mit einer schrittweisen Wiederherstellungssequenz wird eine Datenbank phasenweise auf Dateigruppenebene wiederhergestellt, beginnend mit der primären Dateigruppe und allen sekundären Dateigruppen mit Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="4cadb-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="4cadb-104">In diesem Beispiel wird die `adb` -Datenbank nach einem Notfall auf einem neuen Computer wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="4cadb-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="4cadb-105">Für die Datenbank wird das einfache Wiederherstellungsmodell verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cadb-105">The database is using the simple recovery model.</span></span> <span data-ttu-id="4cadb-106">Vor dem Notfall sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="4cadb-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="4cadb-107">Die Dateigruppen `A` und `C` weisen Lese-/Schreibzugriff auf, und die Dateigruppe `B` ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="4cadb-107">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="4cadb-108">Vor der letzten Teilsicherung ist die Dateigruppe `B` schreibgeschützt geworden. Zur letzten Teilsicherung gehören die primäre Dateigruppe und die sekundären Dateigruppen `A` und `C`mit Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="4cadb-108">Filegroup `B` became read-only before the most recent partial backup, which contains the primary filegroup and the read/write secondary filegroups, `A` and `C`.</span></span> <span data-ttu-id="4cadb-109">Nachdem die Dateigruppe `B` schreibgeschützt geworden ist, wurde eine getrennte Dateisicherung der Dateigruppe `B` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4cadb-109">After filegroup `B` became read-only, a separate file backup of filegroup `B` was taken.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="4cadb-110">Wiederherstellen von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="4cadb-110">Restore Sequences</span></span>  
  
1.  <span data-ttu-id="4cadb-111">Teilwiederherstellung der primären Dateigruppe und der Dateigruppen `A` und `C`.</span><span class="sxs-lookup"><span data-stu-id="4cadb-111">Partial restore of the primary and filegroups `A` and `C`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A',FILEGROUP='C'   
       FROM partial_backup   
       WITH PARTIAL, RECOVERY;  
  
    ```  
  
     <span data-ttu-id="4cadb-112">Die primäre Dateigruppe und die Dateigruppen `A` und `C` sind zu diesem Zeitpunkt online.</span><span class="sxs-lookup"><span data-stu-id="4cadb-112">At this point, the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="4cadb-113">Bei allen Dateien in der Dateigruppe `B` steht die Wiederherstellung aus, und die Dateigruppe ist offline.</span><span class="sxs-lookup"><span data-stu-id="4cadb-113">All files in filegroup `B` are recovery pending, and the filegroup is offline.</span></span>  
  
2.  <span data-ttu-id="4cadb-114">Onlinewiederherstellung der Dateigruppe `B`.</span><span class="sxs-lookup"><span data-stu-id="4cadb-114">Online restore of filegroup `B`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY;  
  
    ```  
  
     <span data-ttu-id="4cadb-115">Alle Dateigruppen sind nun online.</span><span class="sxs-lookup"><span data-stu-id="4cadb-115">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="4cadb-116">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="4cadb-116">Additional Examples</span></span>  
  
-   [<span data-ttu-id="4cadb-117">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="4cadb-118">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-118">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="4cadb-119">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-119">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="4cadb-120">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="4cadb-121">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-121">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="4cadb-122">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-122">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cadb-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cadb-123">See Also</span></span>  
 <span data-ttu-id="4cadb-124">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4cadb-124">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="4cadb-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cadb-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="4cadb-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cadb-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="4cadb-127">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4cadb-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
