---
title: 'Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen (Vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation'
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
ms.assetid: bced4b54-e819-472b-b784-c72e14e72a0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b3cb1a5ea33a5016c99fdf1f5a7f4e892c045b59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725998"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-full-recovery-model"></a><span data-ttu-id="ec9c9-102">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen (Vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="ec9c9-102">Example: Piecemeal Restore of Only Some Filegroups (Full Recovery Model)</span></span>
  <span data-ttu-id="ec9c9-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken mit mehreren Dateien oder Dateigruppen im vollständigen Wiederherstellungsmodell relevant.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="ec9c9-104">Mit einer schrittweisen Wiederherstellungssequenz wird eine Datenbank phasenweise auf Dateigruppenebene wiederhergestellt, beginnend mit der primären Dateigruppe und allen sekundären Dateigruppen mit Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="ec9c9-105">In diesem Beispiel enthält die Datenbank `adb`, für die das vollständige Wiederherstellungsmodell verwendet wird, drei Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-105">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="ec9c9-106">Die Dateigruppe `A` weist Lese-/Schreibzugriff auf, die Dateigruppen `B` und `C` sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="ec9c9-107">Zu Beginn sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="ec9c9-108">Die primäre Dateigruppe und die Dateigruppe `B` der `adb` -Datenbank scheinen beschädigt zu sein.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-108">The primary and filegroup `B` of database `adb` appear to be damaged.</span></span> <span data-ttu-id="ec9c9-109">Die primäre Dateigruppe ist ziemlich klein und kann schnell wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-109">The primary filegroup is fairly small and can be restored quickly.</span></span> <span data-ttu-id="ec9c9-110">Der Datenbankadministrator beschließt, sie mithilfe einer schrittweisen Wiederherstellungssequenz wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-110">The database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="ec9c9-111">Zunächst werden die primäre Dateigruppe und die nachfolgenden Transaktionsprotokolle wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-111">First, the primary filegroup and the subsequent transaction logs are restored the database is recovered.</span></span>  
  
 <span data-ttu-id="ec9c9-112">In den intakten Dateigruppen `A` und `C` sind wichtige Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-112">The intact filegroups `A` and `C` contain critical data.</span></span> <span data-ttu-id="ec9c9-113">Deshalb werden sie anschließend wiederhergestellt, um sie so schnell wie möglich online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-113">Therefore, they will be recovered next to bring them online as quickly as possible.</span></span> <span data-ttu-id="ec9c9-114">Schließlich wird die beschädigte sekundäre Dateigruppe `B`wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-114">Finally, the damaged secondary filegroup, `B`, is restored and recovered.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="ec9c9-115">Wiederherstellungssequenzen</span><span class="sxs-lookup"><span data-stu-id="ec9c9-115">Restore Sequences:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec9c9-116">Die Syntax für eine Onlinewiederherstellungssequenz ist dieselbe wie bei einer Offlinewiederherstellungssequenz.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-116">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="ec9c9-117">Erstellen Sie eine Sicherung des Protokollfragments der `adb`-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-117">Create a tail log backup of database `adb`.</span></span> <span data-ttu-id="ec9c9-118">Dieser Schritt ist entscheidend dafür, dass die intakten Dateigruppen `A` und `C` mit dem Wiederherstellungspunkt der Datenbank übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-118">This step is essential to make the intact filegroups `A` and `C` current with the recovery point of the database.</span></span>  
  
    ```  
    BACKUP LOG adb TO tailLogBackup WITH NORECOVERY  
    ```  
  
2.  <span data-ttu-id="ec9c9-119">Teilweise Wiederherstellung der primären Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-119">Partial restore of the primary filegroup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup   
    WITH PARTIAL, NORECOVERY  
    RESTORE LOG adb FROM backup1 WITH NORECOVERY  
    RESTORE LOG adb FROM backup2 WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="ec9c9-120">Die primäre Dateigruppe ist zu diesem Zeitpunkt online.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-120">At this point the primary is online.</span></span> <span data-ttu-id="ec9c9-121">Für Dateien in den Dateigruppen `A`, `B`und `C` steht die Wiederherstellung aus, und die Dateigruppen sind offline.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-121">Files in filegroups `A`, `B`, and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
3.  <span data-ttu-id="ec9c9-122">Onlinewiederherstellung der Dateigruppen `A` und `C`.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-122">Online restore of filegroups `A` and `C`.</span></span>  
  
     <span data-ttu-id="ec9c9-123">Da die Daten unbeschädigt sind, müssen diese Dateigruppen nicht anhand einer Sicherung wiederhergestellt werden. Sie müssen jedoch wiederhergestellt werden, damit sie online geschaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-123">Because their data is undamaged, these filegroups do not have to be restored from a backup, but they do have to be recovered to bring them online.</span></span>  
  
     <span data-ttu-id="ec9c9-124">Der Datenbankadministrator stellt `A` und `C` sofort wieder her.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-124">The database administrator recovers `A` and `C` immediately.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A', FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="ec9c9-125">Die primäre Dateigruppe und die Dateigruppen `A` und `C` sind zu diesem Zeitpunkt online.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-125">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="ec9c9-126">Für die Dateien in der Dateigruppe `B` steht weiterhin die Wiederherstellung aus; die Dateigruppe ist offline.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-126">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span>  
  
4.  <span data-ttu-id="ec9c9-127">Onlinewiederherstellung der Dateigruppe `B`.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-127">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="ec9c9-128">Die Dateien in der Dateigruppe `B` werden zu einem beliebigen späteren Zeitpunkt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-128">Files in filegroup `B` are restored any time thereafter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec9c9-129">Die Sicherung von Dateigruppe `B` wurde erstellt, nachdem die Dateigruppe als schreibgeschützt gekennzeichnet wurde. Deshalb muss für diese Dateien kein Rollforward ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-129">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, these files do not have to be rolled forward.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="ec9c9-130">Alle Dateigruppen sind nun online.</span><span class="sxs-lookup"><span data-stu-id="ec9c9-130">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="ec9c9-131">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="ec9c9-131">Additional Examples</span></span>  
  
-   [<span data-ttu-id="ec9c9-132">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ec9c9-133">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ec9c9-134">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-134">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ec9c9-135">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="ec9c9-136">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-136">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="ec9c9-137">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-137">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec9c9-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec9c9-138">See Also</span></span>  
 <span data-ttu-id="ec9c9-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec9c9-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ec9c9-140">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec9c9-140">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="ec9c9-141">[Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec9c9-141">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ec9c9-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec9c9-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="ec9c9-143">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec9c9-143">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
