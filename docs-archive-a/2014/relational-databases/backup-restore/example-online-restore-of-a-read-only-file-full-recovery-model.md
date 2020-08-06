---
title: 'Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei (vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation'
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
ms.assetid: 7ea2d2af-086f-48dc-9636-38dc194c7090
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f493c88d64e6ed22e44f33f1442ae581daa8ed4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726006"
---
# <a name="example-online-restore-of-a-read-only-file-full-recovery-model"></a><span data-ttu-id="abd1c-102">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei (vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="abd1c-102">Example: Online Restore of a Read-Only File (Full Recovery Model)</span></span>
  <span data-ttu-id="abd1c-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken mit mehreren Dateien oder Dateigruppen im vollständigen Wiederherstellungsmodell relevant.</span><span class="sxs-lookup"><span data-stu-id="abd1c-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="abd1c-104">In diesem Beispiel enthält die Datenbank `adb`, für die das vollständige Wiederherstellungsmodell verwendet wird, drei Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="abd1c-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="abd1c-105">Die Dateigruppe `A` weist Lese-/Schreibzugriff auf, die Dateigruppen `B` und `C` sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="abd1c-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="abd1c-106">Zu Beginn sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="abd1c-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="abd1c-107">Die schreibgeschützte Datei `b1`in der Dateigruppe `B` der Datenbank `adb` muss wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="abd1c-107">A read-only file, `b1`, in filegroup `B` of database `adb` has to be restored.</span></span> <span data-ttu-id="abd1c-108">Nachdem die Datei schreibgeschützt wurde, wurde eine Sicherung ausgeführt; daher sind keine Protokollsicherungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd1c-108">A backup was taken since the file became read-only; therefore, log backups are not required.</span></span> <span data-ttu-id="abd1c-109">Für die Dauer der Wiederherstellung ist die Dateigruppe `B` offline, der Rest der Datenbank bleibt jedoch online.</span><span class="sxs-lookup"><span data-stu-id="abd1c-109">Filegroup `B` is offline for the duration of the restore, but the remainder of the database remains online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="abd1c-110">Wiederherstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="abd1c-110">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abd1c-111">Die Syntax für eine Onlinewiederherstellungssequenz ist dieselbe wie bei einer Offlinewiederherstellungssequenz.</span><span class="sxs-lookup"><span data-stu-id="abd1c-111">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="abd1c-112">Zum Wiederherstellen der Datei befolgt der Datenbankadministrator die folgende Wiederherstellungssequenz:</span><span class="sxs-lookup"><span data-stu-id="abd1c-112">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup  
WITH RECOVERY   
```  
  
 <span data-ttu-id="abd1c-113">Die Dateigruppe B ist jetzt online.</span><span class="sxs-lookup"><span data-stu-id="abd1c-113">Filegroup B is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="abd1c-114">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="abd1c-114">Additional Examples</span></span>  
  
-   [<span data-ttu-id="abd1c-115">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-115">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="abd1c-116">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-116">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="abd1c-117">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-117">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="abd1c-118">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="abd1c-119">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="abd1c-120">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="abd1c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abd1c-121">See Also</span></span>  
 <span data-ttu-id="abd1c-122">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="abd1c-122">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="abd1c-123">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="abd1c-123">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="abd1c-124">[Dateiwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="abd1c-124">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="abd1c-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="abd1c-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
