---
title: Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.configsecondarydbs.f1
- sql12.swb.availabilitygroup.preparedbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 9f2feb3c-ea9b-4992-8202-2aeed4f9a6dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3da3f7332bdabce65785b2844157dd4639389254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616188"
---
# <a name="manually-prepare-a-secondary-database-for-an-availability-group-sql-server"></a><span data-ttu-id="78ded-102">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="78ded-102">Manually Prepare a Secondary Database for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="78ded-103">In diesem Thema wird erläutert, wie eine sekundäre Datenbank für eine AlwaysOn-Verfügbarkeitsgruppe in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell vorbereitet wird.</span><span class="sxs-lookup"><span data-stu-id="78ded-103">This topic describes how to prepare a secondary database for an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="78ded-104">Die Vorbereitung einer sekundären Datenbank erfordert zwei Schritte: (1) das Wiederherstellen einer aktuellen Datenbanksicherung der primären Datenbank und nachfolgender Protokollsicherungen auf allen Serverinstanzen, auf denen das sekundäre Replikat gehostet wird, mit RESTORE WITH NORECOVERY und (2) das Verknüpfen der wiederhergestellten Datenbank mit der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="78ded-104">Preparing a secondary database requires two steps: (1) restoring a recent database backup of the primary database and subsequent log backups onto each server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY, and (2) joining the restored database to the availability group.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="78ded-105">Wenn Sie eine vorhandene Protokollversandkonfiguration haben, können Sie möglicherweise die primäre Datenbank für den Protokollversand zusammen mit einer oder mehreren sekundären Datenbanken in eine primäre AlwaysOn-Datenbank und eine oder mehrere sekundäre AlwaysOn-Datenbanken konvertieren.</span><span class="sxs-lookup"><span data-stu-id="78ded-105">If you have an existing log shipping configuration, you might be able to convert the log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and one or more AlwaysOn secondary databases.</span></span> <span data-ttu-id="78ded-106">Weitere Informationen finden Sie unter [Voraussetzungen für das Migrieren vom Protokoll Versand zu AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="78ded-106">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="78ded-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="78ded-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78ded-108">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="78ded-108">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="78ded-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="78ded-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="78ded-110">Security</span><span class="sxs-lookup"><span data-stu-id="78ded-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78ded-111">**So bereiten Sie eine sekundäre Datenbank vor mit:**</span><span class="sxs-lookup"><span data-stu-id="78ded-111">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="78ded-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78ded-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78ded-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78ded-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="78ded-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="78ded-114">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="78ded-115">Verwandte Sicherungs- und Wiederherstellungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="78ded-115">Related Backup and Restore Tasks</span></span>](#RelatedTasks)  
  
-   <span data-ttu-id="78ded-116">**Nachverfolgung:** [Nach dem Vorbereiten einer sekundären Datenbank](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="78ded-116">**Follow Up:** [After Preparing a Secondary Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78ded-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="78ded-117">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="78ded-118">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="78ded-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="78ded-119">Stellen Sie sicher, dass das System, auf dem die Datenbank gespeichert werden soll, einen Datenträger mit ausreichend Speicherplatz für die sekundären Datenbanken besitzt.</span><span class="sxs-lookup"><span data-stu-id="78ded-119">Make sure that the system where you plan to place database possesses a disk drive with sufficient space for the secondary databases.</span></span>  
  
-   <span data-ttu-id="78ded-120">Der Name der sekundären Datenbank muss dem Namen der primären Datenbank entsprechen.</span><span class="sxs-lookup"><span data-stu-id="78ded-120">The name of the secondary database must be the same as the name of the primary database.</span></span>  
  
-   <span data-ttu-id="78ded-121">Verwenden Sie RESTORE WITH NORECOVERY für jeden Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="78ded-121">Use RESTORE WITH NORECOVERY for every restore operation.</span></span>  
  
-   <span data-ttu-id="78ded-122">Wenn sich die sekundäre Datenbank unter einem anderen Dateipfad (einschließlich des Laufwerkbuchstabens) als die primäre Datenbank befinden muss, muss vom Wiederherstellungsbefehl auch die WITH MOVE-Option für alle Datenbankdateien verwendet werden, um für sie den Pfad der sekundären Datenbank anzugeben.</span><span class="sxs-lookup"><span data-stu-id="78ded-122">If the secondary database needs to reside on a different file path (including the drive letter) than the primary database, the restore command must also use the WITH MOVE option for each of the database files to specify them to the path of the secondary database.</span></span>  
  
-   <span data-ttu-id="78ded-123">Wenn Sie die Datenbank dateigruppenweise wiederherstellen, stellen Sie sicher, dass Sie die vollständige Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-123">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
-   <span data-ttu-id="78ded-124">Nach dem Wiederherstellen der Datenbank müssen Sie alle seit der letzten wiederhergestellten Datensicherung erstellten Protokollsicherungen wiederherstellen (WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="78ded-124">After restoring the database, you must restore (WITH NORECOVERY) every log backup created since the last restored data backup.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="78ded-125">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="78ded-125">Recommendations</span></span>  
  
-   <span data-ttu-id="78ded-126">Bei eigenständigen Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]sollte der Dateipfad (einschließlich des Laufwerkbuchstabens) einer sekundären Datenbank nach Möglichkeit mit dem Pfad der entsprechenden primären Datenbank übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="78ded-126">On stand-alone instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], we recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span> <span data-ttu-id="78ded-127">Grund: Wenn beim Erstellen einer sekundären Datenbank die Datenbankdateien verschoben werden, tritt beim späteren Hinzufügen einer Datei auf der sekundären Datenbank möglicherweise ein Fehler auf und bewirkt, dass die sekundäre Datenbank angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="78ded-127">This is because if you move the database files when creating a secondary database, a later add-file operation might fail on the secondary database and cause the secondary database to be suspended.</span></span>  
  
-   <span data-ttu-id="78ded-128">Vor dem Vorbereiten der sekundären Datenbanken sollten Sie unbedingt geplante Protokollsicherungen auf den Datenbanken in der Verfügbarkeitsgruppe anhalten, bis die Initialisierung sekundärer Replikate abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="78ded-128">Before preparing your secondary databases, we strongly recommend that you suspend scheduled log backups on the databases in the availability group until the initialization of secondary replicas has completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78ded-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="78ded-129">Security</span></span>  
 <span data-ttu-id="78ded-130">Wenn eine Datenbank gesichert wird, wird die [Eigenschaft vertrauenswürdige Datenbank](../../../relational-databases/security/trustworthy-database-property.md) auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="78ded-130">When a database is backed up, the [TRUSTWORTHY database property](../../../relational-databases/security/trustworthy-database-property.md) is set to OFF.</span></span> <span data-ttu-id="78ded-131">Deshalb ist TRUSTWORTHY bei einer neu wiederhergestellten Datenbank immer auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="78ded-131">Therefore, TRUSTWORTHY is always OFF on a newly restored database.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78ded-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="78ded-132">Permissions</span></span>  
 <span data-ttu-id="78ded-133">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="78ded-133">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span> <span data-ttu-id="78ded-134">Weitere Informationen finden Sie unter [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78ded-134">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="78ded-135">Wenn die Datenbank, die wiederhergestellt wird, auf der Serverinstanz nicht vorhanden ist, erfordert die RESTORE-Anweisung CREATE DATABASE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="78ded-135">When the database being restored does not exist on the server instance, the RESTORE statement requires CREATE DATABASE permissions.</span></span> <span data-ttu-id="78ded-136">Weitere Informationen finden Sie unter [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="78ded-136">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78ded-137">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78ded-137">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78ded-138"> Wenn die Sicherungs- und Wiederherstellungsdateipfade zwischen der Serverinstanz, auf der das primäre Replikat gehostet wird, und jeder Instanz identisch sind, auf der ein sekundäres Replikat gehostet wird, können Sie sekundäre Datenbanken mithilfe des [Assistenten für neue Verfügbarkeitsgruppen](use-the-availability-group-wizard-sql-server-management-studio.md), des [Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)oder des [Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen](availability-group-add-database-to-group-wizard.md)erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-138">If the backup and restore file paths are identical between the server instance that hosts the primary replica and every instance that hosts a secondary replica, you should be able create secondary databases by using [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md).</span></span>  
  
 <span data-ttu-id="78ded-139">**So bereiten Sie eine sekundäre Datenbank vor**</span><span class="sxs-lookup"><span data-stu-id="78ded-139">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="78ded-140">Wenn Sie noch keine aktuelle Sicherung der primären Datenbank besitzen, erstellen Sie neue vollständige oder differenzielle Datenbanksicherung.</span><span class="sxs-lookup"><span data-stu-id="78ded-140">Unless you already have a recent database backup of the primary database, create a new full or differential database backup.</span></span> <span data-ttu-id="78ded-141">Es wird empfohlen, diese Sicherung und nachfolgende Protokollsicherungen auf der empfohlenen Netzwerkfreigabe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="78ded-141">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="78ded-142">Erstellen Sie mindestens eine neue Protokollsicherung der primären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="78ded-142">Create at least one new log backup of the primary database.</span></span>  
  
3.  <span data-ttu-id="78ded-143">Stellen Sie auf der Serverinstanz, die das sekundäre Replikat hostet, die vollständige Datenbanksicherung der primären (und optional eine differenzielle Sicherung) und anschließend nachfolgende Protokollsicherungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="78ded-143">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by any subsequent log backups.</span></span>  
  
     <span data-ttu-id="78ded-144">Aktivieren Sie auf der Seite **RESTORE DATABASE-Optionen** die Option **Datenbank nicht betriebsbereit belassen und kein Rollback für Transaktionen ohne Commit ausführen. Zusätzliche Transaktionsprotokolle können wiederhergestellt werden. (RESTORE WITH NORECOVERY)**.</span><span class="sxs-lookup"><span data-stu-id="78ded-144">On the **RESTORE DATABASEOptions** page, select **Leave the database non-operational, and do not roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**.</span></span>  
  
     <span data-ttu-id="78ded-145">Wenn sich die Dateipfade der primären Datenbank und der sekundären Datenbank unterscheiden, z. B. wenn sich die primäre Datenbank auf Laufwerk F: befindet, bei der Serverinstanz, die das sekundäre Replikat hostet, jedoch das Laufwerk F: fehlt, schließen Sie die MOVE-Option in die WITH-Klausel ein.</span><span class="sxs-lookup"><span data-stu-id="78ded-145">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
4.  <span data-ttu-id="78ded-146">Um die Konfiguration der sekundären Datenbank abzuschließen, müssen Sie die sekundäre Datenbank mit der Verfügbarkeitsgruppe verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="78ded-146">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="78ded-147">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="78ded-147">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78ded-148"> Informationen zum Ausführen dieser Sicherungs- und Wiederherstellungsoptionen finden Sie weiter unten in diesem Abschnitt unter [Verwandte Sicherungs- und Wiederherstellungsaufgaben](#RelatedTasks)</span><span class="sxs-lookup"><span data-stu-id="78ded-148">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this section.</span></span>  
  
###  <a name="related-backup-and-restore-tasks"></a><a name="RelatedTasks"></a><span data-ttu-id="78ded-149">Verwandte Sicherungs-und Wiederherstellungs Aufgaben</span><span class="sxs-lookup"><span data-stu-id="78ded-149">Related Backup and Restore Tasks</span></span>  
 <span data-ttu-id="78ded-150">**So erstellen Sie eine Datenbanksicherung**</span><span class="sxs-lookup"><span data-stu-id="78ded-150">**To create a database backup**</span></span>  
  
-   [<span data-ttu-id="78ded-151">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-151">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="78ded-152">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-152">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="78ded-153">**So erstellen Sie eine Protokollsicherung**</span><span class="sxs-lookup"><span data-stu-id="78ded-153">**To create a log backup**</span></span>  
  
-   [<span data-ttu-id="78ded-154">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-154">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
 <span data-ttu-id="78ded-155">**So stellen Sie Sicherungen wieder her**</span><span class="sxs-lookup"><span data-stu-id="78ded-155">**To restore backups**</span></span>  
  
-   [<span data-ttu-id="78ded-156">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-156">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="78ded-157">Wiederherstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-157">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="78ded-158">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-158">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="78ded-159">Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-159">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78ded-160">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78ded-160">Using Transact-SQL</span></span>  
 <span data-ttu-id="78ded-161">**So bereiten Sie eine sekundäre Datenbank vor**</span><span class="sxs-lookup"><span data-stu-id="78ded-161">**To prepare a secondary database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78ded-162">Ein Beispiel für diese Prozedur finden Sie weiter oben in diesem Thema [Beispiel (Transact-SQL)](#ExampleTsql).</span><span class="sxs-lookup"><span data-stu-id="78ded-162">For an example of this procedure, see [Example (Transact-SQL)](#ExampleTsql), earlier in this topic.</span></span>  
  
1.  <span data-ttu-id="78ded-163">Wenn Sie keine aktuelle vollständige Sicherung der primären Datenbank besitzen, stellen Sie eine Verbindung mit der Serverinstanz her, die das primäre Replikat hostet, und erstellen Sie eine vollständige Datenbanksicherung.</span><span class="sxs-lookup"><span data-stu-id="78ded-163">Unless you have a recent full backup of the primary database, connect to the server instance that hosts the primary replica and create a full database backup.</span></span> <span data-ttu-id="78ded-164">Es wird empfohlen, diese Sicherung und nachfolgende Protokollsicherungen auf der empfohlenen Netzwerkfreigabe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="78ded-164">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="78ded-165">Stellen Sie auf der Serverinstanz, die das sekundäre Replikat hostet, die vollständige Datenbanksicherung der primären (und optional eine differenzielle Sicherung) und anschließend alle nachfolgenden Protokollsicherungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="78ded-165">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by all subsequent log backups.</span></span> <span data-ttu-id="78ded-166">Verwenden Sie WITH NORECOVERY für jeden Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="78ded-166">Use WITH NORECOVERY for every restore operation.</span></span>  
  
     <span data-ttu-id="78ded-167">Wenn sich die Dateipfade der primären Datenbank und der sekundären Datenbank unterscheiden, z. B. wenn sich die primäre Datenbank auf Laufwerk F: befindet, bei der Serverinstanz, die das sekundäre Replikat hostet, jedoch das Laufwerk F: fehlt, schließen Sie die MOVE-Option in die WITH-Klausel ein.</span><span class="sxs-lookup"><span data-stu-id="78ded-167">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
3.  <span data-ttu-id="78ded-168">Wurden seit der erforderlichen Protokollsicherung zusätzliche Protokollsicherungen in der primären Datenbank vorgenommen, müssen Sie diese ebenfalls auf die Serverinstanz kopieren, die das sekundäre Replikat hostet, und alle Protokollsicherungen auf die sekundäre Datenbank anwenden, beginnend mit der frühesten und mithilfe von RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="78ded-168">If any log backups have been taken on the primary database since the required log backup, you must also copy these to the server instance that hosts the secondary replica and apply each of those log backups to the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78ded-169">Eine Protokollsicherung ist nicht vorhanden, wenn die primäre Datenbank erst kürzlich erstellt wurde und bisher keine Protokollsicherung vorgenommen wurde oder wenn das Wiederherstellungsmodell soeben von SIMPLE in FULL geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="78ded-169">A log backup would not exist if the primary database has just been created and no log backup has been taken yet or if the recovery model has just been changed from simple to full.</span></span>  
  
4.  <span data-ttu-id="78ded-170">Um die Konfiguration der sekundären Datenbank abzuschließen, müssen Sie die sekundäre Datenbank mit der Verfügbarkeitsgruppe verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="78ded-170">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="78ded-171">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="78ded-171">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78ded-172"> Informationen zum Ausführen dieser Sicherungs- und Wiederherstellungsoptionen finden Sie weiter unten in diesem Thema unter [Verwandte Sicherungs- und Wiederherstellungsaufgaben](#RelatedTasks)</span><span class="sxs-lookup"><span data-stu-id="78ded-172">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this topic.</span></span>  
  
###  <a name="transact-sql-example"></a><a name="ExampleTsql"></a><span data-ttu-id="78ded-173">Transact-SQL-Beispiel</span><span class="sxs-lookup"><span data-stu-id="78ded-173">Transact-SQL Example</span></span>  
 <span data-ttu-id="78ded-174">Im folgenden Beispiel wird eine sekundäre Datenbank vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="78ded-174">The following example prepares a secondary database.</span></span> <span data-ttu-id="78ded-175">In diesem Beispiel wird die [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] -Beispieldatenbank verwendet, in der standardmäßig das einfache Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78ded-175">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="78ded-176">Damit die [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] -Datenbank verwendet werden kann, ändern Sie sie so, dass das vollständige Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78ded-176">To use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```sql
    USE master;  
    GO  
    ALTER DATABASE MyDB1   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="78ded-177">Nach dem Ändern des Wiederherstellungsmodells der Datenbank von SIMPLE in FULL erstellen Sie eine vollständige Sicherung, die zum Erstellen der sekundären Datenbank verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="78ded-177">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the secondary database.</span></span> <span data-ttu-id="78ded-178">Da das Wiederherstellungsmodell soeben geändert wurde, wird die Option WITH FORMAT angegeben, um einen neuen Mediensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-178">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="78ded-179">Dies ist hilfreich, um die Sicherungen unter dem vollständigen Wiederherstellungsmodell von vorherigen Sicherungen zu trennen, die unter dem einfachen Wiederherstellungsmodell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="78ded-179">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="78ded-180">Im Rahmen dieses Beispiels wird die Sicherungsdatei (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) auf dem gleichen Laufwerk wie die Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="78ded-180">For the purpose of this example, the backup file (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78ded-181">Bei einer Produktionsdatenbank sollten Sie die Sicherung stets auf einem separaten Medium erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-181">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="78ded-182">Erstellen Sie auf der Serverinstanz, die das primäre Replikat (`INSTANCE01`) hostet, folgendermaßen eine vollständige Sicherung der primären Datenbank:</span><span class="sxs-lookup"><span data-stu-id="78ded-182">On the server instance that hosts the primary replica (`INSTANCE01`), create a full backup of the primary database as follows:</span></span>  
  
    ```sql
    BACKUP DATABASE MyDB1   
        TO DISK = 'C:\MyDB1.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="78ded-183">Kopieren Sie die vollständige Sicherung auf die Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="78ded-183">Copy the full backup to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="78ded-184">Stellen Sie mit RESTORE WITH NORECOVERY die vollständige Sicherung auf der Serverinstanz wieder her, auf der das sekundäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="78ded-184">Restore the full backup, using RESTORE WITH NORECOVERY, onto the server instance that hosts the secondary replica.</span></span> <span data-ttu-id="78ded-185">Der Wiederherstellungsbefehl hängt davon ab, ob die Pfade der primären und sekundären Datenbanken identisch sind.</span><span class="sxs-lookup"><span data-stu-id="78ded-185">The restore command depends on whether the paths of primary and secondary databases are identical.</span></span>  
  
    -   <span data-ttu-id="78ded-186">**Wenn die Pfade identisch sind, führen Sie Folgendes aus:**</span><span class="sxs-lookup"><span data-stu-id="78ded-186">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="78ded-187">Stellen Sie folgendermaßen die vollständige Sicherung auf dem Computer wieder her, der das sekundäre Replikat hostet:</span><span class="sxs-lookup"><span data-stu-id="78ded-187">On the computer that hosts the secondary replica, restore the full backup as follows:</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1   
            FROM DISK = 'C:\MyDB1.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="78ded-188">**Wenn die Pfade unterschiedlich sind, führen Sie Folgendes aus:**</span><span class="sxs-lookup"><span data-stu-id="78ded-188">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="78ded-189">Wenn sich der Pfad der sekundären Datenbank vom Pfad der primären Datenbank unterscheidet (z. B. wenn die Laufwerkbuchstaben unterschiedlich sind), ist es für das Erstellen der sekundären Datenbank erforderlich, dass der Wiederherstellungsvorgang eine MOVE-Klausel einschließt.</span><span class="sxs-lookup"><span data-stu-id="78ded-189">If the path of the secondary database differs from the path of the primary database (for instance, their drive letters differ), creating the secondary database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="78ded-190">Wenn die Pfadnamen der primären und sekundären Datenbank unterschiedlich sind, können Sie keine Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="78ded-190">If the path names of the primary and secondary databases differ, you cannot add a file.</span></span> <span data-ttu-id="78ded-191">Der Grund hierfür besteht darin, dass die Serverinstanz des sekundären Replikats beim Empfangen des Protokolls für das Hinzufügen einer Datei versucht, die neue Datei unter demselben Pfad abzulegen, der von der primären Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78ded-191">This is because on receiving the log for the add file operation, the server instance of the secondary replica attempts to place the new file in the same path as used by the primary database.</span></span>  
  
         <span data-ttu-id="78ded-192">Der folgende Befehl stellt z. B. eine Sicherung einer primären Datenbank wieder her, die sich im Datenverzeichnis der Standardinstanz von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)](C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA) befindet.</span><span class="sxs-lookup"><span data-stu-id="78ded-192">For example, the following command restores a backup of a primary database that resides in the data directory of the default instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span></span> <span data-ttu-id="78ded-193">Bei der Datenbankwiederherstellung muss die Datenbank in das Datenverzeichnis einer Remoteinstanz von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] (*AlwaysOn1*) verschoben werden, die das sekundäre Replikat auf einem anderen Clusterknoten hostet.</span><span class="sxs-lookup"><span data-stu-id="78ded-193">The restore database operation must move the database to the data directory of a remote instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named  (*AlwaysOn1*), which hosts the secondary replica on another cluster node.</span></span> <span data-ttu-id="78ded-194">Dort werden die Daten und-Protokolldateien im Verzeichnis *C:\Programme\Microsoft SQL Server\MSSQL12. ALWAYSON1\MSSQL\DATA* wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="78ded-194">There, the data and log files are restored to the *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* directory .</span></span> <span data-ttu-id="78ded-195">Der Wiederherstellungsvorgang verwendet WITH NORECOVERY, um die sekundäre Datenbank in der wiederhergestellten Datenbank zu belassen.</span><span class="sxs-lookup"><span data-stu-id="78ded-195">The restore operation uses WITH NORECOVERY, to leave the secondary database in the restoring database.</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1  
          FROM DISK='C:\MyDB1.bak'  
         WITH NORECOVERY,   
            MOVE 'MyDB1_Data' TO   
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.mdf',   
            MOVE 'MyDB1_Log' TO  
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="78ded-196">Nach dem Wiederherstellen der vollständigen Sicherung müssen Sie eine Protokollsicherung für die primäre Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-196">After you restore the full backup, you must create a log backup on the primary database.</span></span> <span data-ttu-id="78ded-197">Beispielsweise wird das Protokoll mit der folgenden [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung in der Sicherungsdatei *E:\MyDB1_log.bak*gesichert:</span><span class="sxs-lookup"><span data-stu-id="78ded-197">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement backs up the log to the a backup file named *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    BACKUP LOG MyDB1   
      TO DISK = 'E:\MyDB1_log.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="78ded-198">Sie können die Datenbank erst mit dem sekundären Replikat verknüpfen, nachdem Sie die erforderliche Protokollsicherung (und alle nachfolgenden Protokollsicherungen) angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="78ded-198">Before you can join the database to the secondary replica, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="78ded-199">So wird beispielsweise mit der folgenden [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung das erste Protokoll von *C:\MyDB1.bak*wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="78ded-199">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores the first log from *C:\MyDB1.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="78ded-200">Wenn weitere Protokollsicherungen erfolgen, bevor die Datenbank mit dem sekundären Replikat verknüpft wird, müssen Sie mit RESTORE WITH NORECOVERY auch alle Protokollsicherungen nacheinander auf der Serverinstanz wiederherstellen, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="78ded-200">If any additional log backups occur before the database joins the secondary replica, you must also restore all of those log backups, in sequence, to the server instance that hosts the secondary replica using RESTORE WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="78ded-201">So werden beispielsweise mit der folgenden [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung zwei zusätzliche Protokolle von *E:\MyDB1_log.bak*wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="78ded-201">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores two additional logs from *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="78ded-202">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="78ded-202">Using PowerShell</span></span>  
 <span data-ttu-id="78ded-203">**So bereiten Sie eine sekundäre Datenbank vor**</span><span class="sxs-lookup"><span data-stu-id="78ded-203">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="78ded-204">Wenn Sie eine aktuelle Sicherung der primären Datenbank erstellen müssen, ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="78ded-204">If you need to create a recent backup of the primary database, change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="78ded-205">Verwenden Sie das `Backup-SqlDatabase`-Cmdlet, um alle Sicherungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-205">Use the `Backup-SqlDatabase` cmdlet to create each of the backups.</span></span>  
  
3.  <span data-ttu-id="78ded-206">Ändern Sie das Verzeichnis (`cd`) in die Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="78ded-206">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="78ded-207">Stellen Sie die Datenbank und die Protokollsicherungen aller primären Datenbanken mit dem `restore-SqlDatabase`-Cmdlet wieder her, und geben Sie dabei den Wiederherstellungsparameter `NoRecovery` an.</span><span class="sxs-lookup"><span data-stu-id="78ded-207">To restore the database and log backups of each primary database, use the `restore-SqlDatabase` cmdlet, specifying the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="78ded-208">Wenn sich die Dateipfade zwischen den Computern unterscheiden, die das primäre Replikat und das sekundäre Zielreplikat hosten, verwenden Sie ebenfalls den Wiederherstellungsparameter `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="78ded-208">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78ded-209">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="78ded-209">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="78ded-210">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="78ded-210">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
5.  <span data-ttu-id="78ded-211">Um die Konfiguration der sekundären Datenbank abzuschließen, müssen Sie sie mit der Verfügbarkeitsgruppe verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="78ded-211">To complete configuration of the secondary database, you need to join it to the availability group.</span></span> <span data-ttu-id="78ded-212">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="78ded-212">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="78ded-213">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="78ded-213">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="78ded-214">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="78ded-214">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="sample-backup-and-restore-script-and-command"></a><a name="ExamplePSscript"></a> <span data-ttu-id="78ded-215">Beispiele für Sicherung, Wiederherstellungsskript und Befehl</span><span class="sxs-lookup"><span data-stu-id="78ded-215">Sample Backup and Restore Script and Command</span></span>  
 <span data-ttu-id="78ded-216">Mit den folgenden PowerShell-Befehlen werden eine vollständige Datenbanksicherung und ein Transaktionsprotokoll auf einer Netzwerkfreigabe gesichert und diese Sicherungen von dieser Freigabe wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="78ded-216">The following PowerShell commands back up a full database backup and transaction log to a network share and restore those backups from that share.</span></span> <span data-ttu-id="78ded-217">In diesem Beispiel wird davon ausgegangen, dass der Dateipfad, unter dem die Datenbank wiederhergestellt wird, mit dem Dateipfad identisch ist, unter dem die Datenbank gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="78ded-217">This example assumes that the file path to which the database is restored is the same as the file path on which the database was backed up.</span></span>  
  
```powershell
# Create database backup  
Backup-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -ServerInstance "SourceMachine\Instance"  
# Create log backup  
Backup-SqlDatabase -Database "MyDB1" -BackupAction "Log" -BackupFile "\\share\backups\MyDB1.trn" -ServerInstance "SourceMachine\Instance"  
# Restore database backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -NoRecovery -ServerInstance "DestinationMachine\Instance"  
# Restore log backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.trn" -RestoreAction "Log" -NoRecovery -ServerInstance "DestinationMachine\Instance"
```  
  
##  <a name="follow-up-after-preparing-a-secondary-database"></a><a name="FollowUp"></a> <span data-ttu-id="78ded-218">Nachverfolgung: Nach dem Vorbereiten einer sekundären Datenbank</span><span class="sxs-lookup"><span data-stu-id="78ded-218">Follow Up: After Preparing a Secondary Database</span></span>  
 <span data-ttu-id="78ded-219">Um die Konfiguration der sekundären Datenbank abzuschließen, müssen Sie die neu wiederhergestellte Datenbank mit der Verfügbarkeitsgruppe verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="78ded-219">To complete configuration of the secondary database, join the newly restored database to the availability group.</span></span> <span data-ttu-id="78ded-220">Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ded-220">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ded-221">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78ded-221">See Also</span></span>  
 <span data-ttu-id="78ded-222">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="78ded-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="78ded-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78ded-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="78ded-224">[RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78ded-224">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="78ded-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78ded-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="78ded-226">Problembehandlung bei einem fehlgeschlagenen Vorgang zum Hinzufügen einer Datei &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;</span><span class="sxs-lookup"><span data-stu-id="78ded-226">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
