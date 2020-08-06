---
title: Verschieben von Berichtsserver-Datenbanken auf einen anderen Computer (einheitlicher SSRS-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 44a9854d-e333-44f6-bdc7-8837b9f34416
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49fd35f57cf783b262b3c690e3047e5f479ab193
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695274"
---
# <a name="moving-the-report-server-databases-to-another-computer-ssrs-native-mode"></a><span data-ttu-id="befb0-102">Verschieben von Berichtsserver-Datenbanken auf einen anderen Computer (einheitlicher SSRS-Modus)</span><span class="sxs-lookup"><span data-stu-id="befb0-102">Moving the Report Server Databases to Another Computer (SSRS Native Mode)</span></span>
  <span data-ttu-id="befb0-103">Sie können die Berichts Server-Datenbanken, die in einer-Installation verwendet werden, in eine-Instanz verschieben, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] sich auf einem anderen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="befb0-103">You can move the report server databases that are used in an installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] to an instance that is on a different computer.</span></span> <span data-ttu-id="befb0-104">Die Datenbanken reportserver und reportservertempdb müssen gemeinsam verschoben bzw. kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="befb0-104">Both the reportserver and reportservertempdb databases must be moved or copied together.</span></span> <span data-ttu-id="befb0-105">Für eine Installation von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sind beide Datenbanken erforderlich. Die reportservertempdb-Datenbank muss namentlich der zu verschiebenden primären reportserver-Datenbank entsprechen.</span><span class="sxs-lookup"><span data-stu-id="befb0-105">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires both databases; the reportservertempdb database must be related by name to the primary reportserver database you are moving.</span></span>  
  
 <span data-ttu-id="befb0-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheitlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="befb0-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="befb0-107">Das Verschieben einer Datenbank hat keine Auswirkungen auf geplante Vorgänge, die aktuell für Berichtsserverelemente definiert sind.</span><span class="sxs-lookup"><span data-stu-id="befb0-107">Moving a database does not effect scheduled operations that are currently defined for report server items.</span></span>  
  
-   <span data-ttu-id="befb0-108">Zeitpläne werden beim ersten Neustart des Berichtsserverdiensts neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="befb0-108">Schedules will be recreated the first time that you restart the Report Server service.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="befb0-109">-Agent-Aufträge, die verwendet werden, um einen Zeitplan auszulösen, werden auf der neuen Datenbankinstanz neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="befb0-109">Agent jobs that are used to trigger a schedule will be recreated on the new database instance.</span></span> <span data-ttu-id="befb0-110">Sie müssen die Aufträge nicht auf den neuen Computer verschieben, Sie möchten jedoch möglicherweise nicht mehr benötigte Aufträge auf dem Computer löschen.</span><span class="sxs-lookup"><span data-stu-id="befb0-110">You do not have to move the jobs to the new computer, but you might want to delete jobs on the computer that will no longer be used.</span></span>  
  
-   <span data-ttu-id="befb0-111">Abonnements, zwischengespeicherte Berichte und Momentaufnahmen bleiben in der verschobenen Datenbank erhalten.</span><span class="sxs-lookup"><span data-stu-id="befb0-111">Subscriptions, cached reports, and snapshots are preserved in the moved database.</span></span> <span data-ttu-id="befb0-112">Wenn eine Momentaufnahme nach der Verschiebung der Datenbank keine aktualisierten Daten bezieht, löschen Sie die Momentaufnahmeoptionen im Berichts-Manager, und klicken Sie auf **Anwenden** , um die vorgenommenen Änderungen zu speichern. Erstellen Sie den Zeitplan neu, und klicken Sie nochmals auf **Anwenden** , um die vorgenommenen Änderungen wieder zu speichern.</span><span class="sxs-lookup"><span data-stu-id="befb0-112">If a snapshot is not picking up refreshed data after the database is moved, clear the snapshot options in Report Manager, click **Apply** to save your changes, re-create the schedule, and click **Apply** again to save your changes.</span></span>  
  
-   <span data-ttu-id="befb0-113">Temporäre Berichts- und Benutzersitzungsdaten, die in reportservertempdb gespeichert sind, bleiben beim Verschieben dieser Datenbank persistent.</span><span class="sxs-lookup"><span data-stu-id="befb0-113">Temporary report and user session data that is stored in reportservertempdb are persisted when you move that database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="befb0-114">bietet verschiedene Vorgehensweisen zum Verschieben von Datenbanken (einschließlich Sichern und Wiederherstellen, Anfügen und Trennen sowie Kopieren).</span><span class="sxs-lookup"><span data-stu-id="befb0-114">provides several approaches for moving databases, including backup and restore, attach and detach, and copy.</span></span> <span data-ttu-id="befb0-115">Nicht alle Vorgehensweisen sind zum Verschieben einer vorhandenen Datenbank in eine neue Serverinstanz geeignet.</span><span class="sxs-lookup"><span data-stu-id="befb0-115">Not all approaches are appropriate for relocating an existing database to a new server instance.</span></span> <span data-ttu-id="befb0-116">Die zum Verschieben der Berichtsserver-Datenbank zu verwendende Vorgehensweise ist je nach Verfügbarkeitsanforderungen Ihres Systems unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="befb0-116">The approach that you should use to move the report server database will vary depending on your system availability requirements.</span></span> <span data-ttu-id="befb0-117">Die einfachste Möglichkeit zum Verschieben der Berichtsserver-Datenbanken besteht darin, sie anzufügen und zu trennen.</span><span class="sxs-lookup"><span data-stu-id="befb0-117">The easiest way to move the report server databases is to attach and detach them.</span></span> <span data-ttu-id="befb0-118">Bei dieser Vorgehensweise muss der Berichtsserver jedoch offline geschaltet werden, während Sie die Datenbank trennen.</span><span class="sxs-lookup"><span data-stu-id="befb0-118">However, this approach requires that you take the report server offline while you detach the database.</span></span> <span data-ttu-id="befb0-119">Sicherungen und Wiederherstellungen sind jedoch besser geeignet, wenn Sie Störungen des Diensts vermeiden möchten. Sie müssen für diese Vorgänge jedoch [!INCLUDE[tsql](../../includes/tsql-md.md)] -Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="befb0-119">Backup and restore is a better choice if you want to minimize service disruptions, but you must run [!INCLUDE[tsql](../../includes/tsql-md.md)] commands to perform the operations.</span></span> <span data-ttu-id="befb0-120">Das Kopieren der Datenbank wird nicht empfohlen (insbesondere nicht mithilfe des Assistenten zum Kopieren von Datenbanken), da hierbei Berechtigungseinstellungen in der Datenbank verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="befb0-120">Copying the database is not recommended (specifically, by using the Copy Database Wizard); it does not preserve permission settings in the database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="befb0-121">Die in diesem Thema vorgestellten Schritte sind geeignet, wenn das Verschieben der Berichtsserver-Datenbank die einzige Änderung ist, die Sie an der vorhandenen Installation vornehmen.</span><span class="sxs-lookup"><span data-stu-id="befb0-121">The steps provided in this topic are recommended when relocating the report server database is the only change you are making to the existing installation.</span></span> <span data-ttu-id="befb0-122">Wenn eine vollständige [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Installation migriert wird (d.h. wenn die Datenbank verschoben und die Identität des Berichtsserver-Windows-Diensts, der die Datenbank verwendet, geändert wird), müssen die Verbindung neu konfiguriert und der Verschlüsselungsschlüssel zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="befb0-122">Migrating an entire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation (that is, moving the database and changing the identity of the Report Server Windows service that uses the database) requires connection reconfiguration and an encryption key reset.</span></span>  
  
## <a name="detaching-and-attaching-the-report-server-databases"></a><span data-ttu-id="befb0-123">Trennen und Anfügen der Berichtsserver-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="befb0-123">Detaching and Attaching the Report Server Databases</span></span>  
 <span data-ttu-id="befb0-124">Wenn Sie den Berichtsserver offline schalten können, können Sie die Datenbanken trennen, um sie in die gewünschte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="befb0-124">If you can take the report server offline, you can detach the databases to move them to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="befb0-125">Bei dieser Vorgehensweise bleiben die Berechtigungen in den Datenbanken erhalten.</span><span class="sxs-lookup"><span data-stu-id="befb0-125">This approach preserves permissions in the databases.</span></span> <span data-ttu-id="befb0-126">Wenn Sie eine [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Datenbank verwenden, müssen Sie sie in eine andere [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Instanz verschieben.</span><span class="sxs-lookup"><span data-stu-id="befb0-126">If you are using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, you must move it to another [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span> <span data-ttu-id="befb0-127">Nachdem Sie die Datenbanken verschoben haben, müssen Sie die Verbindung des Berichtsservers mit der Berichtsserver-Datenbank erneut konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="befb0-127">After you move the databases, you must reconfigure the report server connection to the report server database.</span></span> <span data-ttu-id="befb0-128">Wenn Sie eine Bereitstellung für dezentrales Skalieren ausführen, müssen Sie die Verbindung der Berichtsserver-Datenbank für jeden Berichtsserver in der Bereitstellung erneut konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="befb0-128">If you are running a scale-out deployment, you must reconfigure the report server database connection for each report server in the deployment.</span></span>  
  
 <span data-ttu-id="befb0-129">Führen Sie folgende Schritte aus, um die Datenbanken zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="befb0-129">Use the following steps to move the databases:</span></span>  
  
1.  <span data-ttu-id="befb0-130">Sichern Sie die Verschlüsselungsschlüssel für die zu verschiebende Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="befb0-130">Backup the encryption keys for the report server database you want to move.</span></span> <span data-ttu-id="befb0-131">Mit dem [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool können Sie die Schlüssel sichern.</span><span class="sxs-lookup"><span data-stu-id="befb0-131">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool backup the keys.</span></span>  
  
2.  <span data-ttu-id="befb0-132">Beenden Sie den Berichtsserverdienst.</span><span class="sxs-lookup"><span data-stu-id="befb0-132">Stop the Report Server service.</span></span> <span data-ttu-id="befb0-133">Mit dem [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool können Sie den Dienst beenden.</span><span class="sxs-lookup"><span data-stu-id="befb0-133">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to stop the service.</span></span>  
  
3.  <span data-ttu-id="befb0-134">Starten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] und öffnen Sie eine Verbindung mit der- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instanz, die die Berichts Server-Datenbanken hostet.</span><span class="sxs-lookup"><span data-stu-id="befb0-134">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and open a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server databases.</span></span>  
  
4.  <span data-ttu-id="befb0-135">Klicken Sie mit der rechten Maustaste auf die Berichtsserver-Datenbank, zeigen Sie auf „Tasks“, und klicken Sie auf **Trennen**.</span><span class="sxs-lookup"><span data-stu-id="befb0-135">Right-click the report server database, point to Tasks, and click **Detach**.</span></span> <span data-ttu-id="befb0-136">Wiederholen Sie diesen Schritt für die temporäre Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="befb0-136">Repeat this step for the report server temporary database.</span></span>  
  
5.  <span data-ttu-id="befb0-137">Kopieren oder verschieben Sie die MDF- und LDF-Dateien in den Datenordner der gewünschten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="befb0-137">Copy or move the .mdf and .ldf files to the Data folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="befb0-138">Da Sie zwei Datenbanken verschieben, müssen Sie sicherstellen, dass Sie alle vier Dateien verschieben bzw. kopieren.</span><span class="sxs-lookup"><span data-stu-id="befb0-138">Because you are moving two databases, make sure that you move or copy all four files.</span></span>  
  
6.  <span data-ttu-id="befb0-139">Öffnen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit der neuen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, die als Host für die Berichtsserver-Datenbanken fungiert.</span><span class="sxs-lookup"><span data-stu-id="befb0-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a connection to the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that will host the report server databases.</span></span>  
  
7.  <span data-ttu-id="befb0-140">Klicken Sie mit der rechten Maustaste auf den Knoten „Datenbanken“, und klicken Sie anschließend auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="befb0-140">Right-click the Databases node, and then click **Attach**.</span></span>  
  
8.  <span data-ttu-id="befb0-141">Klicken Sie auf **Hinzufügen** , um die anzufügenden MDF- und LDF-Dateien der Berichtsserver-Datenbank auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="befb0-141">Click **Add** to select the report server database .mdf and .ldf files that you want to attach.</span></span> <span data-ttu-id="befb0-142">Wiederholen Sie diesen Schritt für die temporäre Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="befb0-142">Repeat this step for the report server temporary database.</span></span>  
  
9. <span data-ttu-id="befb0-143">Überprüfen Sie nach dem Anfügen der Datenbanken, ob `RSExecRole` eine Daten Bank Rolle in der Berichts Server-Datenbank und in der temporären Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="befb0-143">After the databases are attached, verify that the `RSExecRole` is a database role in the report server database and temporary database.</span></span> <span data-ttu-id="befb0-144">`RSExecRole`muss über die Berechtigungen SELECT, INSERT, Update, DELETE und Reference für die Berichts Server-Datenbanktabellen und die EXECUTE-Berechtigung für die gespeicherten Prozeduren verfügen.</span><span class="sxs-lookup"><span data-stu-id="befb0-144">`RSExecRole` must have select, insert, update, delete, and reference permissions on the report server database tables, and execute permissions on the stored procedures.</span></span> <span data-ttu-id="befb0-145">Weitere Informationen finden Sie unter [Erstellen der Rolle RSExecRole](../security/create-the-rsexecrole.md).</span><span class="sxs-lookup"><span data-stu-id="befb0-145">For more information, see [Create the RSExecRole](../security/create-the-rsexecrole.md).</span></span>  
  
10. <span data-ttu-id="befb0-146">Starten Sie das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool, und stellen Sie eine Verbindung mit dem Berichtsserver her.</span><span class="sxs-lookup"><span data-stu-id="befb0-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and open a connection to the report server.</span></span>  
  
11. <span data-ttu-id="befb0-147">Wählen Sie auf der Datenbankseite die neue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz aus, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="befb0-147">On the Database page, select the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then click **Connect**.</span></span>  
  
12. <span data-ttu-id="befb0-148">Wählen Sie die soeben verschobene Berichtsserver-Datenbank aus, und klicken Sie anschließend auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="befb0-148">Select the report server database that you just moved, and then click **Apply**.</span></span>  
  
13. <span data-ttu-id="befb0-149">Klicken Sie auf der Seite Verschlüsselungsschlüssel auf Wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="befb0-149">On the Encryption Keys page, click Restore.</span></span> <span data-ttu-id="befb0-150">Gibt die Datei an, die eine Sicherungskopie der Schlüssel und des Kennworts zum Entsperren der Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="befb0-150">Specify the file that contains the backup copy of the keys and the password to unlock the file.</span></span>  
  
14. <span data-ttu-id="befb0-151">Starten Sie den Berichtsserverdienst neu.</span><span class="sxs-lookup"><span data-stu-id="befb0-151">Restart the Report Server service.</span></span>  
  
## <a name="backing-up-and-restoring-the-report-server-databases"></a><span data-ttu-id="befb0-152">Sichern und Wiederherstellen der Berichtsserver-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="befb0-152">Backing Up and Restoring the Report Server Databases</span></span>  
 <span data-ttu-id="befb0-153">Wenn Sie den Berichtsserver nicht offline schalten können, können Sie die Berichtsserver-Datenbanken durch Sichern und Wiederherstellen verschieben.</span><span class="sxs-lookup"><span data-stu-id="befb0-153">If you cannot take the report server offline, you can use backup and restore to relocate the report server databases.</span></span> <span data-ttu-id="befb0-154">Sie müssen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen zum Sichern und Wiederherstellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="befb0-154">You must use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to do the backup and restore.</span></span> <span data-ttu-id="befb0-155">Nach dem Wiederherstellen der Datenbanken müssen Sie den Berichtsserver so konfigurieren, dass die Datenbank in der neuen Serverinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="befb0-155">After you restore the databases, you must configure the report server to use the database on the new server instance.</span></span> <span data-ttu-id="befb0-156">Weitere Informationen finden Sie in den Anweisungen am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="befb0-156">For more information, see the instructions at the end of this topic.</span></span>  
  
### <a name="using-backup-and-copy_only-to-backup-the-report-server-databases"></a><span data-ttu-id="befb0-157">Verwenden von BACKUP und COPY_ONLY zum Sichern der Berichtsserver-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="befb0-157">Using BACKUP and COPY_ONLY to Backup the Report Server Databases</span></span>  
 <span data-ttu-id="befb0-158">Legen Sie beim Sichern der Datenbanken das COPY_ONLY-Argument fest.</span><span class="sxs-lookup"><span data-stu-id="befb0-158">When backing up the databases, set the COPY_ONLY argument.</span></span> <span data-ttu-id="befb0-159">Achten Sie unbedingt darauf, dass Sie beide Datenbanken und Protokolldateien sichern.</span><span class="sxs-lookup"><span data-stu-id="befb0-159">Be sure to back up both of the databases and log files.</span></span>  
  
```  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServer  
   SET RECOVERY FULL  
  
-- If the ReportServerData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerData',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerData.bak'  
  
-- Create a logical backup device, ReportServerLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerLog.bak'  
  
-- Back up the full ReportServer database.  
BACKUP DATABASE ReportServer  
   TO ReportServerData  
   WITH COPY_ONLY  
  
-- Back up the ReportServer log.  
BACKUP LOG ReportServer  
   TO ReportServerLog  
   WITH COPY_ONLY  
  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServerTempdb  
   SET RECOVERY FULL  
  
-- If the ReportServerTempDBData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBData',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBData.bak'  
  
-- Create a logical backup device, ReportServerTempDBLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBLog.bak'  
  
-- Back up the full ReportServerTempDB database.  
BACKUP DATABASE ReportServerTempDB  
   TO ReportServerTempDBData  
   WITH COPY_ONLY  
  
-- Back up the ReportServerTempDB log.  
BACKUP LOG ReportServerTempDB  
   TO ReportServerTempDBLog  
   WITH COPY_ONLY  
```  
  
### <a name="using-restore-and-move-to-relocate-the-report-server-databases"></a><span data-ttu-id="befb0-160">Verwenden von RESTORE und MOVE zum Verschieben der Berichtsserver-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="befb0-160">Using RESTORE and MOVE to Relocate the Report Server Databases</span></span>  
 <span data-ttu-id="befb0-161">Stellen Sie beim Wiederherstellen der Datenbanken sicher, dass Sie das MOVE-Argument einschließen, damit Sie einen Pfad angeben können.</span><span class="sxs-lookup"><span data-stu-id="befb0-161">When restoring the databases, be sure to include the MOVE argument so that you can specify a path.</span></span> <span data-ttu-id="befb0-162">Mithilfe des NORECOVERY-Arguments wird die erste Wiederherstellung ausgeführt. Dadurch verbleibt die Datenbank im RESTORING-Status, und Sie haben Zeit, die Protokollsicherungen zu überprüfen und zu bestimmen, welche Sicherung wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="befb0-162">Use the NORECOVERY argument to perform the initial restore; this keeps the database in a RESTORING state, giving you time to review log backups to determine which one to restore.</span></span> <span data-ttu-id="befb0-163">Im letzten Schritt wird der RESTORE-Vorgang mit dem RECOVERY-Argument wiederholt.</span><span class="sxs-lookup"><span data-stu-id="befb0-163">The final step repeats the RESTORE operation with the RECOVERY argument.</span></span>  
  
 <span data-ttu-id="befb0-164">Das MOVE-Argument verwendet den logischen Namen der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="befb0-164">The MOVE argument uses the logical name of the data file.</span></span> <span data-ttu-id="befb0-165">Führen Sie die folgende Anweisung aus, um den logischen Namen zu ermitteln: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="befb0-165">To find the logical name, execute the following statement: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="befb0-166">Im folgenden Beispiel ist das FILE-Argument enthalten, sodass Sie die Dateiposition der wiederherzustellenden Protokolldatei angeben können.</span><span class="sxs-lookup"><span data-stu-id="befb0-166">The following examples include the FILE argument so that you can specify the file position of the log file to restore.</span></span> <span data-ttu-id="befb0-167">Führen Sie die folgende Anweisung aus, um die Dateiposition zu ermitteln: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="befb0-167">To find the file position, execute the following statement: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="befb0-168">Beim Wiederherstellen der Datenbank- und Protokolldateien sollten Sie jeden RESTORE-Vorgang separat ausführen.</span><span class="sxs-lookup"><span data-stu-id="befb0-168">When restoring the database and log files, you should run each RESTORE operation separately.</span></span>  
  
```  
-- Restore the report server database and move to new instance folder   
RESTORE DATABASE ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore the report server log file to new instance folder   
RESTORE LOG ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore and move the report server temporary database  
RESTORE DATABASE ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Restore the temporary database log file to new instance folder   
RESTORE LOG ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServer  
   WITH RECOVERY  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServerTempDB  
   WITH RECOVERY  
GO  
```  
  
### <a name="how-to-configure-the-report-server-database-connection"></a><span data-ttu-id="befb0-169">Konfigurieren der Berichtsserver-Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="befb0-169">How to Configure the Report Server Database Connection</span></span>  
  
1.  <span data-ttu-id="befb0-170">Starten Sie den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurations-Manager, und stellen Sie eine Verbindung mit dem Berichtsserver her.</span><span class="sxs-lookup"><span data-stu-id="befb0-170">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and open a connection to the report server.</span></span>  
  
2.  <span data-ttu-id="befb0-171">Doppelklicken Sie auf der Seite Datenbank auf **Datenbank ändern**.</span><span class="sxs-lookup"><span data-stu-id="befb0-171">On the Database page, click **Change Database**.</span></span> <span data-ttu-id="befb0-172">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="befb0-172">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="befb0-173">Sie können auch auf **Wählen Sie eine vorhandene Berichtsserver-Datenbank aus**klicken.</span><span class="sxs-lookup"><span data-stu-id="befb0-173">Click **Choose an existing report server database**.</span></span> <span data-ttu-id="befb0-174">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="befb0-174">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="befb0-175">Wählen Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die nun als Host für die Berichtsserver-Datenbank fungiert, und klicken Sie auf **Verbindung testen**.</span><span class="sxs-lookup"><span data-stu-id="befb0-175">Select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that now hosts the report server database and click **Test Connection**.</span></span> <span data-ttu-id="befb0-176">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="befb0-176">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="befb0-177">Wählen Sie unter "Datenbankname" die gewünschte Berichtsserver-Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="befb0-177">In Database Name, select the report server database that you want to use.</span></span> <span data-ttu-id="befb0-178">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="befb0-178">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="befb0-179">Geben Sie unter Anmeldeinformationen die Anmeldeinformationen an, die der Berichtsserver zur Herstellung der Verbindung mit der Berichtsserver-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="befb0-179">In Credentials, specify the credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="befb0-180">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="befb0-180">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="befb0-181">Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="befb0-181">Click **Next** and then **Finish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="befb0-182">Für eine [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installation muss die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz die `RSExecRole`-Rolle beinhalten.</span><span class="sxs-lookup"><span data-stu-id="befb0-182">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance include the `RSExecRole` role.</span></span> <span data-ttu-id="befb0-183">Wenn Sie die Berichtsserver-Datenbankverbindung über das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool festlegen, werden Rollen erstellt und Anmelderegistrierungen sowie Rollenzuweisungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="befb0-183">Role creation, login registration, and role assignments occur when you set the report server database connection through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="befb0-184">Wenn Sie zum Konfigurieren der Verbindung alternative Vorgehensweisen verwenden (insbesondere das Befehlszeilen-Hilfsprogramm rsconfig.exe), ist der Berichtsserver nicht betriebsbereit.</span><span class="sxs-lookup"><span data-stu-id="befb0-184">If you use alternate approaches (specifically, if you use the rsconfig.exe command prompt utility) to configure the connection, the report server will not be in a working state.</span></span> <span data-ttu-id="befb0-185">Sie müssen möglicherweise WMI-Code schreiben, um den Berichtsserver verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="befb0-185">You might have to write WMI code to make the report server available.</span></span> <span data-ttu-id="befb0-186">Weitere Informationen finden Sie unter [Zugreifen auf den Reporting Services-WMI-Anbieter](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="befb0-186">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befb0-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="befb0-187">See Also</span></span>  
 <span data-ttu-id="befb0-188">[Erstellen der Rolle "RSExecRole"](../security/create-the-rsexecrole.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-188">[Create the RSExecRole](../security/create-the-rsexecrole.md) </span></span>  
 <span data-ttu-id="befb0-189">[Starten und Beenden des Berichtsserverdiensts](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-189">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 <span data-ttu-id="befb0-190">[Konfigurieren einer Verbindung mit der Berichts Server-Datenbank &#40;SSRS-Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-190">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="befb0-191">[Konfigurieren des Kontos für die unbeaufsichtigte Ausführung &#40;SSRS-Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-191">[Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="befb0-192">[Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-192">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="befb0-193">[rsconfig-Hilfsprogramm &#40;SSRS-&#41;](../tools/rsconfig-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-193">[rsconfig Utility &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span></span>  
 <span data-ttu-id="befb0-194">[Konfigurieren und Verwalten von Verschlüsselungsschlüsseln &#40;SSRS-Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span><span class="sxs-lookup"><span data-stu-id="befb0-194">[Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span></span>  
 [<span data-ttu-id="befb0-195">Berichtsserver-Datenbank &#40;einheitlicher SSRS-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="befb0-195">Report Server Database &#40;SSRS Native Mode&#41;</span></span>](report-server-database-ssrs-native-mode.md)  
  
  
