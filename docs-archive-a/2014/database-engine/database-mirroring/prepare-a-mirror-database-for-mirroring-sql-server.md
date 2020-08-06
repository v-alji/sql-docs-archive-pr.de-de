---
title: Vorbereiten einer Spiegeldatenbank auf die Spiegelung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], preparing for mirroring
- logins [SQL Server], database mirroring
- mirror database [SQL Server]
ms.assetid: 8676f9d8-c451-419b-b934-786997d46c2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf46b4f6fd8e7af55e1930ef6063c4754673fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701846"
---
# <a name="prepare-a-mirror-database-for-mirroring-sql-server"></a><span data-ttu-id="907a7-102">Vorbereiten einer Spiegeldatenbank auf die Spiegelung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="907a7-102">Prepare a Mirror Database for Mirroring (SQL Server)</span></span>
  <span data-ttu-id="907a7-103">Eine Datenbank-Spiegelungssitzung kann erst beginnen, nachdem der Datenbankbesitzer oder Systemadministrator sichergestellt hat, dass die Spiegeldatenbank erstellt und auf die Spiegelung vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="907a7-103">Before a database mirroring session can start, the database owner or system administrator must make sure that the mirror database has been created and is ready for mirroring.</span></span> <span data-ttu-id="907a7-104">Zum Erstellen einer neuen Spiegeldatenbank sind zumindest eine vollständige Sicherung der Prinzipaldatenbank sowie eine nachfolgende Protokollsicherung erforderlich, wobei beide auf der Spiegelserverinstanz mithilfe von WITH NORECOVERY wiederhergestellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="907a7-104">Creating a new mirror database minimally requires taking a full backup of the principal database and a subsequent log backup and restoring them both onto the mirror server instance, using WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="907a7-105">In diesem Thema wird beschrieben, wie Sie eine Spiegeldatenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-105">This topic describes how to prepare a mirror database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="907a7-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="907a7-106">Before You Begin</span></span>  
  
###  <a name="requirements"></a><a name="Requirements"></a> <span data-ttu-id="907a7-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="907a7-107">Requirements</span></span>  
  
-   <span data-ttu-id="907a7-108">Die Prinzipalserver- und Spiegelserverinstanz müssen unter derselben Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="907a7-108">The principal and mirror server instances must be running on the same version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="907a7-109">Obwohl der Spiegelserver eine höhere SQL Server-Version aufweisen darf, wird diese Konfiguration nur für einen sorgfältig geplanten Upgradeprozess empfohlen.</span><span class="sxs-lookup"><span data-stu-id="907a7-109">While it is possible for the mirror server to have a higher version of SQL Server, this configuration is only recommended during a carefully planned upgrade process.</span></span> <span data-ttu-id="907a7-110">In einer solchen Konfiguration laufen Sie Gefahr, ein automatisches Failover auszuführen, bei dem die Datenverschiebung automatisch angehalten wird, da Daten nicht zu einer niedrigeren SQL Server-Version verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="907a7-110">In such a configuration, you run the risk of an automatic failover, in which data movement is automatically suspended because data cannot move to a lower version of SQL Server.</span></span> <span data-ttu-id="907a7-111">Weitere Informationen finden Sie unter [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span><span class="sxs-lookup"><span data-stu-id="907a7-111">For more information, see [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span></span>  
  
-   <span data-ttu-id="907a7-112">Die Prinzipalserver- und Spiegelserverinstanz müssen unter derselben Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="907a7-112">The principal and mirror server instances must be running on the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="907a7-113">Informationen zur unterstützten Datenbankspiegelung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] finden Sie unter [Von den SQL Server 2014-Editionen unterstützte Funktionen](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="907a7-113">For information about support for database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="907a7-114">Für die Datenbank muss das vollständige Wiederherstellungsmodell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="907a7-114">The database must use the full recovery model.</span></span>  
  
     <span data-ttu-id="907a7-115">Weitere Informationen finden Sie unter [Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) oder [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) und [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="907a7-115">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) and [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="907a7-116">Der Name der Spiegeldatenbank muss mit dem Namen der Prinzipaldatenbank übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="907a7-116">The name of the mirror database must be the same as the name of the principal database.</span></span>  
  
-   <span data-ttu-id="907a7-117">Damit die Spiegelung funktionsfähig ist, muss sich die Spiegeldatenbank im Wiederherstellungsstatus befinden.</span><span class="sxs-lookup"><span data-stu-id="907a7-117">The mirror database must be in the RESTORING state for mirroring to work.</span></span> <span data-ttu-id="907a7-118">Beim Vorbereiten einer Spiegeldatenbank müssen Sie für jeden Wiederherstellungsvorgang RESTORE WITH NORECOVERY verwenden.</span><span class="sxs-lookup"><span data-stu-id="907a7-118">When preparing a mirror database, you must use RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="907a7-119">Stellen Sie mindestens die vollständige Sicherung der Prinzipaldatenbank mit WITH NORECOVERY wieder her, und zwar gefolgt von allen nachfolgenden Protokollsicherungen.</span><span class="sxs-lookup"><span data-stu-id="907a7-119">Minimally, you will need to restore WITH NORECOVERY a full backup of the principal database, followed by all subsequent log backups.</span></span>  
  
-   <span data-ttu-id="907a7-120">Stellen Sie sicher, dass das System, auf dem die Spiegeldatenbank erstellt werden soll, ein Laufwerk mit ausreichend Speicherplatz für die Spiegeldatenbank besitzen muss.</span><span class="sxs-lookup"><span data-stu-id="907a7-120">The system where you plan to create the mirror database must possesses a disk drive with sufficient space to hold the mirror database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="907a7-121">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="907a7-121">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="907a7-122">Die **master**-, **msdb**-, **temp**- oder **model** -Systemdatenbanken können nicht gespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="907a7-122">You cannot mirror the **master**, **msdb**, **temp**, or **model** system databases.</span></span>  
  
-   <span data-ttu-id="907a7-123">Eine Datenbank, die zu einem [AlwaysOn-Verfügbarkeitsgruppen gehört (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md), kann nicht gespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="907a7-123">You cannot mirror a database that belongs to an [AlwaysOn Availability Groups (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="907a7-124">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="907a7-124">Recommendations</span></span>  
  
-   <span data-ttu-id="907a7-125">Verwenden Sie entweder die letzte vollständige Datenbanksicherung oder eine aktuelle differenzielle Datenbanksicherung der Prinzipaldatenbank.</span><span class="sxs-lookup"><span data-stu-id="907a7-125">Use a very recent full database backup or a recent differential database backup of the principal database.</span></span>  
  
-   <span data-ttu-id="907a7-126">Wenn eine sehr häufige Ausführung eines Protokollsicherungsauftrags in der Prinzipaldatenbank geplant ist, müssen Sie möglicherweise den Sicherungsauftrag deaktivieren, bis die Spiegelung beginnt.</span><span class="sxs-lookup"><span data-stu-id="907a7-126">If a log backup job is scheduled to run very frequently on the principal database, you might have to disable the backup job until mirroring has started.</span></span>  
  
-   <span data-ttu-id="907a7-127">Wenn möglich sollte der Pfad (einschließlich des Laufwerkbuchstabens) der Spiegeldatenbank mit dem Pfad der Prinzipaldatenbank identisch sein.</span><span class="sxs-lookup"><span data-stu-id="907a7-127">If possible, the path (including the drive letter) of the mirror database should be identical to the path of the principal database.</span></span>  
  
     <span data-ttu-id="907a7-128">Wenn sich die Pfade unterscheiden müssen, weil sich beispielsweise die Prinzipaldatenbank auf Laufwerk 'F': befindet, auf dem Spiegelsystem jedoch kein Laufwerk F: vorhanden ist, müssen Sie die MOVE-Option in die RESTORE-Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="907a7-128">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE STATEMENT.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="907a7-129">Damit eine Datei während einer Spiegelungssitzung hinzugefügt werden kann, ohne dass sich dies auf die Sitzung auswirkt, muss der Pfad der Datei auf beiden Servern vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="907a7-129">Adding a file during a mirroring session without impacting the session requires that the path of the file exists on both servers.</span></span> <span data-ttu-id="907a7-130">Wenn Sie die Datenbankdateien bei der Erstellung der Spiegeldatenbank verschieben, kann bei einem später durchgeführten Vorgang zum Hinzufügen einer Datei in der Spiegeldatenbank ein Fehler auftreten oder die Spiegelung wird möglicherweise angehalten.</span><span class="sxs-lookup"><span data-stu-id="907a7-130">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span> <span data-ttu-id="907a7-131">Informationen zum Umgang mit einem fehlerhaften Dateierstellungsvorgang finden Sie unter [Problembehandlung für die Datenbankspiegelungskonfiguration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="907a7-131">For information about dealing with a failed create-file operation, see [Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="907a7-132">Hat die Prinzipaldatenbank mindestens einen Volltextkatalog, sollten Sie [Datenbankspiegelung und Volltextkataloge &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="907a7-132">If the principal database has any full-text catalogs, we recommend that you see [Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span></span>  
  
-   <span data-ttu-id="907a7-133">Bei einer Produktionsdatenbank erstellen Sie die Sicherung stets auf einem separaten Medium.</span><span class="sxs-lookup"><span data-stu-id="907a7-133">For a production database, always back up to a separate device.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="907a7-134">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="907a7-134">Security</span></span>  
 <span data-ttu-id="907a7-135">TRUSTWORTHY wird beim Sichern einer Datenbank auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="907a7-135">TRUSTWORTHY is set to OFF when a database is backed up.</span></span> <span data-ttu-id="907a7-136">Deshalb ist TRUSTWORTHY bei einer neuen Spiegeldatenbank immer OFF.</span><span class="sxs-lookup"><span data-stu-id="907a7-136">Therefore, TRUSTWORTHY is always OFF on a new mirror database.</span></span> <span data-ttu-id="907a7-137">Muss die Datenbank nach einem Failover vertrauenswürdig sein, sind zusätzliche Installationsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="907a7-137">If the database needs to be trustworthy after a failover, additional setup steps are necessary.</span></span> <span data-ttu-id="907a7-138">Weitere Informationen finden Sie unter [Einrichten der TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-138">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
 <span data-ttu-id="907a7-139">Informationen zum Aktivieren der automatischen Verschlüsselung des Datenbank-Hauptschlüssels einer Spiegeldatenbank finden Sie unter [Einrichten einer verschlüsselten Spiegeldatenbank](set-up-an-encrypted-mirror-database.md).</span><span class="sxs-lookup"><span data-stu-id="907a7-139">For information about enabling automatic decryption of the database master key of a mirror database, see [Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="907a7-140">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="907a7-140">Permissions</span></span>  
 <span data-ttu-id="907a7-141">Datenbankbesitzer oder Systemadministrator.</span><span class="sxs-lookup"><span data-stu-id="907a7-141">Database owner or system administrator.</span></span>  
  
##  <a name="to-prepare-an-existing-mirror-database-to-restart-mirroring"></a><a name="PrepareToRestartMirroring"></a> <span data-ttu-id="907a7-142">So bereiten Sie eine vorhandene Spiegeldatenbank auf das erneute Starten der Spiegelung vor</span><span class="sxs-lookup"><span data-stu-id="907a7-142">To Prepare an Existing Mirror Database to Restart Mirroring</span></span>  
 <span data-ttu-id="907a7-143">Wenn die Spiegelung entfernt wurde und die Spiegeldatenbank sich weiterhin im RECOVERING-Status befindet, können Sie die Spiegelung erneut starten.</span><span class="sxs-lookup"><span data-stu-id="907a7-143">If mirroring has been removed and the mirror database is still in the RECOVERING state, you can restart mirroring.</span></span>  
  
1.  <span data-ttu-id="907a7-144">Erstellen Sie mindestens eine Protokollsicherung auf der Prinzipaldatenbank.</span><span class="sxs-lookup"><span data-stu-id="907a7-144">Take at least one log backup on the principal database.</span></span> <span data-ttu-id="907a7-145">Weitere Informationen finden Sie unter [Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)bezeichnet) gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="907a7-145">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="907a7-146">Verwenden Sie auf der Spiegeldatenbank RESTORE WITH NORECOVERY, um alle Protokollsicherungen wiederherzustellen, die seit dem Entfernen der Spiegelung auf der Prinzipaldatenbank erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="907a7-146">On the mirror database, use RESTORE WITH NORECOVERY to restore all log backups taken on the principal database since mirroring was removed.</span></span> <span data-ttu-id="907a7-147">Weitere Informationen finden Sie unter [Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-147">For more information, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
##  <a name="to-prepare-a-new-mirror-database"></a><a name="CombinedProcedure"></a> <span data-ttu-id="907a7-148">So bereiten Sie eine neue Spiegeldatenbank vor</span><span class="sxs-lookup"><span data-stu-id="907a7-148">To Prepare a New Mirror Database</span></span>  
 <span data-ttu-id="907a7-149">**So bereiten Sie eine Spiegeldatenbank vor**</span><span class="sxs-lookup"><span data-stu-id="907a7-149">**To prepare a mirror database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="907a7-150">Ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Beispiel für diese Prozedur finden Sie weiter unten in diesem Abschnitt unter [Beispiel (Transact-SQL)](#TsqlExample).</span><span class="sxs-lookup"><span data-stu-id="907a7-150">For a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="907a7-151">Stellen Sie eine Verbindung mit einer Prinzipalserverinstanz her.</span><span class="sxs-lookup"><span data-stu-id="907a7-151">Connect to principal server instance.</span></span>  
  
2.  <span data-ttu-id="907a7-152">Erstellen Sie entweder eine vollständige Datenbanksicherung oder eine differenzielle Datenbanksicherung der Prinzipaldatenbank.</span><span class="sxs-lookup"><span data-stu-id="907a7-152">Create either a full database backup or a differential database backup of the principal database.</span></span>  
  
    -   [<span data-ttu-id="907a7-153">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-153">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
    -   <span data-ttu-id="907a7-154">[Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="907a7-154">[Create a Differential Database Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="907a7-155">In der Regel müssen Sie mindestens eine Protokollsicherung auf der Prinzipaldatenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-155">Typically, you need to take at least one log backup on the principal database.</span></span> <span data-ttu-id="907a7-156">Eine Protokollsicherung ist jedoch möglicherweise nicht erforderlich, wenn die Datenbank erst kürzlich erstellt wurde und bisher keine Protokollsicherung vorgenommen wurde oder wenn das Wiederherstellungsmodell soeben von SIMPLE in FULL geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="907a7-156">However, a log backup might be unnecessary, if the database has just been created and no log backup has been taken yet, or if the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
    -   [<span data-ttu-id="907a7-157">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-157">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
4.  <span data-ttu-id="907a7-158">Sofern sich die Sicherungen nicht auf einem Netzlaufwerk befinden, auf das von beiden Systemen zugegriffen werden kann, kopieren Sie die Datenbank- und Protokollsicherungen in das System, von dem die Spiegelserverinstanz gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="907a7-158">Unless the backups are on a network drive that is accessible from both systems, copy the database and log backups to the system that will host the mirror server instance.</span></span>  
  
5.  <span data-ttu-id="907a7-159">Stellen Sie eine Verbindung zur Spiegelserverinstanz her.</span><span class="sxs-lookup"><span data-stu-id="907a7-159">Connect to mirror server instance.</span></span>  
  
6.  <span data-ttu-id="907a7-160">Erstellen Sie mit RESTORE WITH NORECOVERY die Spiegeldatenbank, indem Sie die vollständige Datenbanksicherung und optional die letzte differenzielle Datenbanksicherung auf der Spiegelserverinstanz wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-160">Using RESTORE WITH NORECOVERY, create the mirror database by restoring the full database backup and, optionally, the most recent differential database backup, onto the mirror server instance.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="907a7-161">Wenn Sie die Datenbank dateigruppenweise wiederherstellen, stellen Sie sicher, dass Sie die vollständige Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-161">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
    -   [<span data-ttu-id="907a7-162">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-162">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
    -   <span data-ttu-id="907a7-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) und [RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql)vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
7.  <span data-ttu-id="907a7-164">Wenden Sie unter Angabe von RESTORE WITH NORECOVERY alle ausstehenden Protokollsicherungen auf die Spiegeldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="907a7-164">Using RESTORE WITH NORECOVERY, apply any outstanding log backup or backups to the mirror database.</span></span>  
  
    -   [<span data-ttu-id="907a7-165">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-165">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="907a7-166">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="907a7-166">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="907a7-167">Bevor Sie eine Datenbank-Spiegelungssitzung starten können, müssen Sie die Spiegeldatenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-167">Before you can start a database mirroring session, you must create the mirror database.</span></span> <span data-ttu-id="907a7-168">Dies sollte vor dem Starten der Spiegelungssitzung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="907a7-168">You should do this just before starting the mirroring session.</span></span>  
  
 <span data-ttu-id="907a7-169">In diesem Beispiel wird die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank verwendet, in der standardmäßig das einfache Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="907a7-169">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="907a7-170">Damit die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank für die Datenbankspiegelung verwendet werden kann, ändern Sie sie so, dass das vollständige Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="907a7-170">To use database mirroring with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="907a7-171">Nach dem Ändern des Wiederherstellungsmodells der Datenbank von SIMPLE in FULL erstellen Sie eine vollständige Sicherung, die zum Erstellen der Spiegeldatenbank verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="907a7-171">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the mirror database.</span></span> <span data-ttu-id="907a7-172">Da das Wiederherstellungsmodell soeben geändert wurde, wird die Option WITH FORMAT angegeben, um einen neuen Mediensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-172">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="907a7-173">Dies ist hilfreich, um die Sicherungen unter dem vollständigen Wiederherstellungsmodell von vorherigen Sicherungen zu trennen, die unter dem einfachen Wiederherstellungsmodell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="907a7-173">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="907a7-174">Im Rahmen dieses Beispiels wird die Sicherungsdatei (`C:\AdventureWorks.bak`) auf dem gleichen Laufwerk wie die Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="907a7-174">For the purpose of this example, the backup file (`C:\AdventureWorks.bak`) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="907a7-175">Bei einer Produktionsdatenbank sollten Sie die Sicherung stets auf einem separaten Medium erstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-175">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="907a7-176">Erstellen Sie auf der Prinzipalserverinstanz (auf `PARTNERHOST1`) folgendermaßen eine vollständige Sicherung der Prinzipaldatenbank:</span><span class="sxs-lookup"><span data-stu-id="907a7-176">On the principal server instance (on `PARTNERHOST1`), create a full backup of the principal database as follows:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="907a7-177">Kopieren Sie die vollständige Sicherung auf den Spiegelserver.</span><span class="sxs-lookup"><span data-stu-id="907a7-177">Copy the full backup to the mirror server.</span></span>  
  
4.  <span data-ttu-id="907a7-178">Stellen Sie die vollständige Sicherung mit der Option RESTORE WITH NORECOVERY auf der Spiegelserverinstanz wieder her.</span><span class="sxs-lookup"><span data-stu-id="907a7-178">Using RESTORE WITH NORECOVERY, restore the full backup onto the mirror server instance.</span></span> <span data-ttu-id="907a7-179">Der Wiederherstellungsbefehl hängt davon ab, ob die Pfade der Prinzipal- und Spiegeldatenbanken identisch sind.</span><span class="sxs-lookup"><span data-stu-id="907a7-179">The restore command depends on whether the paths of principal and mirror databases are identical.</span></span>  
  
    -   <span data-ttu-id="907a7-180">**Wenn die Pfade identisch sind, führen Sie Folgendes aus:**</span><span class="sxs-lookup"><span data-stu-id="907a7-180">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="907a7-181">Stellen Sie auf der Spiegelserverinstanz (auf `PARTNERHOST5`) folgendermaßen die vollständige Sicherung wieder her:</span><span class="sxs-lookup"><span data-stu-id="907a7-181">On the mirror server instance (on `PARTNERHOST5`), restore the full backup as follows:</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks   
            FROM DISK = 'C:\AdventureWorks.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="907a7-182">**Wenn die Pfade unterschiedlich sind, führen Sie Folgendes aus:**</span><span class="sxs-lookup"><span data-stu-id="907a7-182">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="907a7-183">Wenn sich der Pfad der Spiegeldatenbank vom Pfad der Prinzipaldatenbank unterscheidet (z. B. wenn die Laufwerkbuchstaben unterschiedlich sind), ist es für das Erstellen der Spiegeldatenbank erforderlich, dass der Wiederherstellungsvorgang eine MOVE-Klausel einschließt.</span><span class="sxs-lookup"><span data-stu-id="907a7-183">If the path of the mirror database differs from the path of the principal database (for instance, their drive letters differ), creating the mirror database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="907a7-184">Wenn die Pfadnamen der Prinzipal- und Spiegeldatenbanken unterschiedlich sind, können Sie keine Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="907a7-184">If the path names of the principal and mirror databases differ, you cannot add a file.</span></span> <span data-ttu-id="907a7-185">Der Grund hierfür besteht darin, dass die Spiegelserverinstanz beim Empfangen des Protokolls für das Hinzufügen einer Datei versucht, die neue Datei an dem Speicherort abzulegen, der von der Prinzipaldatenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="907a7-185">This is because on receiving the log for the add file operation, the mirror server instance attempts to place the new file in the location used by the principal database.</span></span>  
  
         <span data-ttu-id="907a7-186">So wird beispielsweise über den folgenden Befehl eine Sicherung einer Prinzipaldatenbank, die sich in „C:\Programme\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\“ befindet, an einem anderen Speicherort (D:\Programme\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`) erstellt, in dem sich die Spiegeldatenbank befinden soll.</span><span class="sxs-lookup"><span data-stu-id="907a7-186">For example, the following command restores a backup of a principal database residing in C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ to a different location, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, where the mirror database is to reside.</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks  
           FROM DISK='C:\AdventureWorks.bak'  
           WITH NORECOVERY,   
              MOVE 'AdventureWorks_Data' TO   
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Data.mdf',   
              MOVE 'AdventureWorks_Log' TO  
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Log.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="907a7-187">Nach dem Erstellen der vollständigen Sicherung müssen Sie eine Protokollsicherung in der Prinzipaldatenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-187">After you create the full backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="907a7-188">Über die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wird beispielsweise das Protokoll in derselben Datei gesichert, die auch bei der vorhergehenden vollständigen Sicherung verwendet wurde:</span><span class="sxs-lookup"><span data-stu-id="907a7-188">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding full backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="907a7-189">Sie können erst mit der Spiegelung beginnen, nachdem Sie die erforderliche Protokollsicherung (und alle nachfolgenden Protokollsicherungen) angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="907a7-189">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="907a7-190">So wird beispielsweise mit der folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung das erste Protokoll von `C:\AdventureWorks.bak`wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="907a7-190">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="907a7-191">Werden zusätzliche Protokollsicherungen vor dem Beginn der Spiegelung vorgenommen, müssen Sie auch all diese Protokollsicherungen nacheinander mithilfe von WITH NORECOVERY auf dem Spiegelserver wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="907a7-191">If any additional log backups occur before you start mirroring, you must also restore all of those log backups, in sequence, to the mirror server using WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="907a7-192">So werden beispielsweise mit der folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung zwei zusätzliche Protokolle von `C:\AdventureWorks.bak`wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="907a7-192">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores two additional logs from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
 <span data-ttu-id="907a7-193">Ein vollständiges Beispiel für das Einrichten von Datenbankspiegelung, Anzeigen der Sicherheitseinrichtung, Vorbereiten der Spiegeldatenbank, Einrichten der Partner und Hinzufügen eines Zeugen finden Sie unter [Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md)vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-193">For a complete example of setting up database mirroring, showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-preparing-a-mirror-database"></a><a name="FollowUp"></a><span data-ttu-id="907a7-194">Nächster Schritt: Nach der Vorbereitung einer Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="907a7-194">Follow Up: After Preparing a Mirror Database</span></span>  
  
1.  <span data-ttu-id="907a7-195">Wenn seit dem letzten RESTORE LOG-Vorgang Protokollsicherungen vorgenommen wurden, müssen Sie jede zusätzliche Protokollsicherung mit RESTORE WITH NORECOVERY manuell anwenden.</span><span class="sxs-lookup"><span data-stu-id="907a7-195">If any additional log backups have been taken since your most recent RESTORE LOG operation, you must manually apply every additional log backup, using RESTORE WITH NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="907a7-196">Starten Sie die Spiegelungssitzung.</span><span class="sxs-lookup"><span data-stu-id="907a7-196">Start the mirroring session.</span></span> <span data-ttu-id="907a7-197">Weitere Informationen finden Sie unter [Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) oder [Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md)vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-197">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) or [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="907a7-198">Wenn Sie den Sicherungsauftrag für die Prinzipaldatenbank deaktiviert haben, aktivieren Sie den Auftrag erneut.</span><span class="sxs-lookup"><span data-stu-id="907a7-198">If you disabled the backup job on the principal database, reenable the job.</span></span>  
  
4.  <span data-ttu-id="907a7-199">Muss die Datenbank nach einem Failover vertrauenswürdig sein, sind zusätzliche Installationsschritte nach dem Beginn der Spiegelung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="907a7-199">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span> <span data-ttu-id="907a7-200">Weitere Informationen finden Sie unter [Einrichten der TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="907a7-200">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="907a7-201">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="907a7-201">Related Tasks</span></span>  
  
-   [<span data-ttu-id="907a7-202">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-202">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="907a7-203">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-203">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="907a7-204">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-204">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="907a7-205">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-205">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="907a7-206">Einrichten einer verschlüsselten Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="907a7-206">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
-   [<span data-ttu-id="907a7-207">Einrichten der TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-207">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="907a7-208">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="907a7-208">See Also</span></span>  
 <span data-ttu-id="907a7-209">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="907a7-209">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="907a7-210">[Transport Sicherheit für Daten Bank Spiegelung und AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="907a7-210">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="907a7-211">[Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="907a7-211">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="907a7-212">[Sichern und Wiederherstellen von Volltextkatalogen und Indizes](../../relational-databases/indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="907a7-212">[Back Up and Restore Full-Text Catalogs and Indexes](../../relational-databases/indexes/indexes.md) </span></span>  
 <span data-ttu-id="907a7-213">[Datenbankspiegelung und Volltextkataloge (SQL Server)](database-mirroring-and-full-text-catalogs-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="907a7-213">[Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span></span>  
 <span data-ttu-id="907a7-214">[Datenbankspiegelung und Replikation (SQL Server)](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="907a7-214">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="907a7-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="907a7-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="907a7-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="907a7-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="907a7-217">RESTORE-Argumente &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="907a7-217">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)  
  
  
