---
title: 'Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff (vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 0dbeda81-1464-44ba-9011-914900096368
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5b99a3d97644c2a5f104173457f30fc5b3fd7188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609273"
---
# <a name="example-online-restore-of-a-read-write-file-full-recovery-model"></a><span data-ttu-id="ed503-102">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="ed503-102">Example: Online Restore of a Read-Write File (Full Recovery Model)</span></span>
  <span data-ttu-id="ed503-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken mit mehreren Dateien oder Dateigruppen im vollständigen Wiederherstellungsmodell relevant.</span><span class="sxs-lookup"><span data-stu-id="ed503-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="ed503-104">In diesem Beispiel enthält die Datenbank `adb`, für die das vollständige Wiederherstellungsmodell verwendet wird, drei Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="ed503-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="ed503-105">Die Dateigruppe `A` weist Lese-/Schreibzugriff auf, die Dateigruppen `B` und `C` sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="ed503-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="ed503-106">Zu Beginn sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="ed503-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="ed503-107">Datei `a1` in Dateigruppe `A` ist allem Anschein nach beschädigt, darum beschließt der Datenbankadministrator, die Datei wiederherzustellen; die Datenbank bleibt dabei online.</span><span class="sxs-lookup"><span data-stu-id="ed503-107">File `a1` in filegroup `A` appears to be damaged, and the database administrator decides to restore it while the database remains online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed503-108">Bei Verwendung des einfachen Wiederherstellungsmodells ist die Onlinewiederherstellung von Daten mit Lese- und Schreibzugriff nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed503-108">Under the simple recovery model, online restore of read/write data is not allowed.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="ed503-109">Wiederherstellen von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="ed503-109">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed503-110">Die Syntax für eine Onlinewiederherstellungssequenz ist dieselbe wie bei einer Offlinewiederherstellungssequenz.</span><span class="sxs-lookup"><span data-stu-id="ed503-110">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="ed503-111">Onlinewiederherstellung von Datei `a1`.</span><span class="sxs-lookup"><span data-stu-id="ed503-111">Online restore of file `a1`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILE='a1' FROM backup   
    WITH NORECOVERY;  
    ```  
  
     <span data-ttu-id="ed503-112">Datei a1 befindet sich jetzt im Wiederherstellungsstatus, und Dateigruppe A ist offline.</span><span class="sxs-lookup"><span data-stu-id="ed503-112">At this point, file a1 is in the RESTORING state, and filegroup A is offline.</span></span>  
  
2.  <span data-ttu-id="ed503-113">Nach der Wiederherstellung der Datei erstellt der Datenbankadministrator eine neue Protokollsicherung, um sicherzustellen, dass der Status der Datenbank zu dem Zeitpunkt erfasst wird, zu dem die Datei offline geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="ed503-113">After restoring the file, the database administrator takes a new log backup to make sure that the point at which the file went offline is captured.</span></span>  
  
    ```  
    BACKUP LOG adb TO log_backup3;   
    ```  
  
3.  <span data-ttu-id="ed503-114">Onlinewiederherstellung von Protokollsicherungen.</span><span class="sxs-lookup"><span data-stu-id="ed503-114">Online restore of log backups.</span></span>  
  
     <span data-ttu-id="ed503-115">Der Administrator stellt alle seit der wiederhergestellten Dateisicherung erstellten Protokollsicherungen bis zur letzten Protokollsicherung (der in Schritt 2 erstellten Sicherung*log_backup3*) wieder her.</span><span class="sxs-lookup"><span data-stu-id="ed503-115">The administrator restores all the log backups taken since the restored file backup, ending with the latest log backup (*log_backup3*, taken in step 2).</span></span> <span data-ttu-id="ed503-116">Nach dem Wiederherstellen der letzten Protokollsicherung wird die Datenbank wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="ed503-116">After the last backup is restored, the database is recovered.</span></span>  
  
    ```  
    RESTORE LOG adb FROM log_backup1 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup2 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup3 WITH NORECOVERY;  
    RESTORE LOG adb WITH RECOVERY;  
    ```  
  
     <span data-ttu-id="ed503-117">Die Datei `a1` ist jetzt online.</span><span class="sxs-lookup"><span data-stu-id="ed503-117">File `a1` is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="ed503-118">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="ed503-118">Additional Examples</span></span>  
  
-   [<span data-ttu-id="ed503-119">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-119">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ed503-120">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ed503-121">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-121">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ed503-122">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-122">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="ed503-123">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="ed503-124">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-124">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed503-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed503-125">See Also</span></span>  
 <span data-ttu-id="ed503-126">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed503-126">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="ed503-127">[Schrittweise Wiederherstellungen &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed503-127">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="ed503-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed503-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ed503-129">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed503-129">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="ed503-130">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed503-130">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="ed503-131">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed503-131">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
