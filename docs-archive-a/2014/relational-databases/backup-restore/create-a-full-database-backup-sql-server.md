---
title: Erstellen einer vollständigen Datenbanksicherung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], full backups
- backing up databases [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- database backups [SQL Server], SQL Server Management Studio
ms.assetid: 586561fc-dfbb-4842-84f8-204a9100a534
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f406464680a1669133dc87bdfb231c644d33fbdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724777"
---
# <a name="create-a-full-database-backup-sql-server"></a><span data-ttu-id="eb7f5-102">Erstellen einer vollständigen Datenbanksicherung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eb7f5-102">Create a Full Database Backup (SQL Server)</span></span>
  <span data-ttu-id="eb7f5-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder PowerShell eine vollständige Datenbanksicherung erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-103">This topic describes how to create a full database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb7f5-104">Informationen zur SQL Server Sicherung im Azure-BLOB-Speicherdienst finden Sie unter [SQL Server sichern und Wiederherstellen mit Azure BLOB Storage Dienst](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="eb7f5-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eb7f5-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eb7f5-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="eb7f5-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="eb7f5-109">Security</span><span class="sxs-lookup"><span data-stu-id="eb7f5-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eb7f5-110">**Erstellen einer vollständigen Datenbanksicherung mit:**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-110">**To create a full database backup, using:**</span></span>  
  
     [<span data-ttu-id="eb7f5-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb7f5-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eb7f5-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb7f5-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="eb7f5-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb7f5-113">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="eb7f5-114">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="eb7f5-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eb7f5-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="eb7f5-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="eb7f5-117">Die BACKUP-Anweisung ist nicht in einer expliziten oder implizierten Transaktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="eb7f5-118">Sicherungen, die mit aktuelleren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellt werden, können in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-118">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="eb7f5-119">Weitere Informationen finden Sie unter [Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-119">For more information, see [Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="eb7f5-120">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-120">Recommendations</span></span>  
  
-   <span data-ttu-id="eb7f5-121">Wenn eine Datenbank größer wird, ist zum Abschließen von vollständigen Datenbanksicherungen jedoch mehr Zeit und mehr Speicherplatz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-121">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="eb7f5-122">Deshalb können Sie bei einer großen Datenbank eine vollständige Datenbanksicherung durch mehrere *differenzielle Datenbanksicherungen*ergänzen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-122">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="eb7f5-123">Weitere Informationen finden Sie unter [Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-123">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="eb7f5-124">Ein Schätzwert der Größe einer vollständigen Datenbanksicherung kann mithilfe der gespeicherten Systemprozedur [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-124">You can estimate the size of a full database backup by using the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure.</span></span>  
  
-   <span data-ttu-id="eb7f5-125">Standardmäßig wird bei jedem erfolgreichen Sicherungsvorgang dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll und dem Systemereignisprotokoll ein Eintrag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-125">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="eb7f5-126">Wenn Sie das Protokoll regelmäßig sichern, kann die Anzahl dieser Erfolgsmeldungen schnell ansteigen, d. h., es entstehen sehr große Fehlerprotokolle, die das Suchen nach anderen Meldungen erschweren können.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-126">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="eb7f5-127">In solchen Fällen können Sie diese Protokolleinträge mithilfe des Ablaufverfolgungsflags 3226 unterdrücken, wenn keines der Skripts von diesen Einträgen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-127">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="eb7f5-128">Weitere Informationen finden Sie unter [Ablaufverfolgungsflags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-128">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eb7f5-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="eb7f5-129">Security</span></span>  
 <span data-ttu-id="eb7f5-130">Bei einer Datenbanksicherung ist TRUSTWORTHY auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-130">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="eb7f5-131">Weitere Informationen zum Festlegen von TRUSTWORTHY auf ON finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-131">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="eb7f5-132">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] werden die Optionen `PASSWORD` und `MEDIAPASSWORD` nicht mehr für die Erstellung von Sicherungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-132">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] the `PASSWORD` and `MEDIAPASSWORD` options are discontinued for creating backups.</span></span> <span data-ttu-id="eb7f5-133">Sie können jedoch immer noch mit Kennwörtern erstellte Sicherungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-133">You can still restore backups created with passwords.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eb7f5-134">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-134">Permissions</span></span>  
 <span data-ttu-id="eb7f5-135">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-135">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="eb7f5-136">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-136">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="eb7f5-137">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-137">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="eb7f5-138">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-138">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="eb7f5-139">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-139">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eb7f5-140">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb7f5-140">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb7f5-141"> Wenn Sie mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Sicherungstask angeben, können Sie das entsprechende [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Skript generieren, indem Sie auf die Schaltfläche **Skript** klicken und ein Ziel für das Skript auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-141">When you specify a back up task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span></span>  
  
#### <a name="to-back-up-a-database"></a><span data-ttu-id="eb7f5-142">So sichern Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="eb7f5-142">To back up a database</span></span>  
  
1.  <span data-ttu-id="eb7f5-143">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-143">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="eb7f5-144">Erweitern Sie den Ordner **Datenbanken**, und wählen Sie dann je nach Datenbank entweder eine Benutzerdatenbank aus, oder erweitern Sie die Option **Systemdatenbanken** , um eine Systemdatenbank auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-144">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="eb7f5-145">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-145">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="eb7f5-146">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-146">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="eb7f5-147">`Database`Überprüfen Sie im Listenfeld den Datenbanknamen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-147">In the `Database` list box, verify the database name.</span></span> <span data-ttu-id="eb7f5-148">Sie können optional eine andere Datenbank aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-148">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="eb7f5-149">Eine Datenbanksicherung kann für jedes Wiederherstellungsmodell ausgeführt werden (**FULL**, **BULK_LOGGED**, oder **SIMPLE**).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-149">You can perform a database backup for any recovery model (**FULL**, **BULK_LOGGED**, or **SIMPLE**).</span></span>  
  
6.  <span data-ttu-id="eb7f5-150">Wählen Sie im Listenfeld **Sicherungstyp** die Option **Vollständig**aus.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-150">In the **Backup type** list box, select **Full**.</span></span>  
  
     <span data-ttu-id="eb7f5-151">Beachten Sie, dass Sie nach dem Erstellen einer vollständigen Datenbanksicherung eine differenzielle Datenbanksicherung ausführen können. Weitere Informationen finden Sie unter [Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md):</span><span class="sxs-lookup"><span data-stu-id="eb7f5-151">Note that after creating a full database backup, you can create a differential database backup; for more information, see [Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span></span>  
  
7.  <span data-ttu-id="eb7f5-152">Sie können optional auch **Kopiesicherung** auswählen, um eine Kopiesicherung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-152">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="eb7f5-153">Eine *Kopiesicherung* ist eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherung, die unabhängig von der Sequenz von herkömmlichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherungen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-153">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="eb7f5-154">Weitere Informationen finden Sie unter [Kopiesicherungen &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-154">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb7f5-155">Wenn die Option **Differenziell** aktiviert ist, können Sie keine Kopiesicherung erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-155">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="eb7f5-156">Klicken Sie für **Sicherungs Komponente**auf `Database` .</span><span class="sxs-lookup"><span data-stu-id="eb7f5-156">For **Backup component**, click `Database`.</span></span>  
  
9. <span data-ttu-id="eb7f5-157">Akzeptieren Sie entweder den im Textfeld **Name** vorgeschlagenen Standardnamen für den Sicherungssatz, oder geben Sie einen anderen Namen für den Sicherungssatz ein.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-157">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
10. <span data-ttu-id="eb7f5-158">Geben Sie optional in das Textfeld **Beschreibung** eine Beschreibung des Sicherungssatzes ein.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-158">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
11. <span data-ttu-id="eb7f5-159">Wählen Sie den Sicherungszieltyp aus, indem Sie auf **Datenträger**, **Band** oder **URL**klicken.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-159">Choose the type of backup destination by clicking **Disk**, **Tape** or **URL**.</span></span> <span data-ttu-id="eb7f5-160">Klicken Sie auf **Hinzufügen**, um die Pfade von bis zu 64 Datenträgern oder Bandlaufwerken, die einen einzelnen Mediensatz enthalten, auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-160">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="eb7f5-161">Die ausgewählten Pfade werden im Listenfeld **Sichern auf** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-161">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="eb7f5-162">Um einen Sicherungsziel zu entfernen, wählen Sie ihn aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-162">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="eb7f5-163">Zum Anzeigen des Inhalts eines Sicherungsziels wählen Sie es aus, und klicken Sie auf **Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-163">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="eb7f5-164">Klicken Sie im Bereich **Seite auswählen** auf **Medienoptionen** , um die Medienoptionen anzuzeigen oder auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-164">To view or select the media options, click **Media Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="eb7f5-165">Wählen Sie eine Option von **Medium überschreiben** aus, indem Sie auf eine der folgenden Optionen klicken:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-165">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="eb7f5-166">**Auf vorhandenen Mediensatz sichern**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-166">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="eb7f5-167">Klicken Sie bei dieser Option entweder auf **An vorhandenen Sicherungssatz anfügen** oder auf **Alle vorhandenen Sicherungssätze überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-167">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="eb7f5-168">Weitere Informationen finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md):</span><span class="sxs-lookup"><span data-stu-id="eb7f5-168">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="eb7f5-169">Sie können bei Bedarf das Kontrollkästchen **Mediensatznamen und Ablaufzeit des Sicherungssatzes überprüfen** aktivieren, damit beim Sicherungsvorgang das Datum und die Uhrzeit überprüft werden, an dem bzw. zu der der Mediensatz und der Sicherungssatz ablaufen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-169">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="eb7f5-170">Geben Sie optional einen Namen im Textfeld **Mediensatzname** ein.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-170">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="eb7f5-171">Wenn kein Name angegeben wurde, wird ein Mediensatz mit leerem Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-171">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="eb7f5-172">Wenn Sie einen Mediensatznamen angeben, wird überprüft, ob der tatsächliche Name des Mediums (Band oder Datenträger) mit dem eingegebenen Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-172">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="eb7f5-173">Diese Option ist deaktiviert, wenn Sie **URL** auf der Seite **Allgemein** als Sicherungsziel ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-173">This option is disabled if you selected **URL** as the backup destination in the **General** page.</span></span> <span data-ttu-id="eb7f5-174">Weitere Informationen finden Sie unter [Datenbank sichern &#40;Seite 'Medienoptionen'&#41;](back-up-database-media-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-174">For more information, see [Back Up Database &#40;Media Options Page&#41;](back-up-database-media-options-page.md)</span></span>  
        >   
        >  <span data-ttu-id="eb7f5-175">Wenn Sie die Verschlüsselung verwenden möchten, sollten Sie diese Option nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-175">If you plan to use encryption, do not select this option.</span></span> <span data-ttu-id="eb7f5-176">Wenn Sie diese Option aktivieren, werden die Verschlüsselungsoptionen auf der Seite **Sicherungsoptionen** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-176">If you select this option, the encryption options in the **Backup Options** page will be disabled.</span></span> <span data-ttu-id="eb7f5-177">Die Verschlüsselung wird nicht unterstützt, wenn Sie Sicherungen an den vorhandenen Sicherungssatz anfügen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-177">Encryption is not supported when appending to the existing backup set.</span></span>  
  
    -   <span data-ttu-id="eb7f5-178">**Auf neuen Mediensatz sichern und alle vorhandenen Sicherungssätze löschen**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-178">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="eb7f5-179">Geben Sie bei dieser Option einen Namen in das Textfeld **Name für neuen Mediensatz** und optional eine Beschreibung des Mediensatzes in das Textfeld **Beschreibung für neuen Mediensatz** ein.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-179">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="eb7f5-180">Diese Option ist deaktiviert, wenn Sie auf der Seite **Allgemein** die Option **URL** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-180">This option is disabled if you selected **URL** in the **General** page.</span></span> <span data-ttu-id="eb7f5-181">Diese Aktionen werden bei der Sicherung im Azure-Speicher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-181">These actions are not supported when backing up to Azure storage.</span></span>  
  
14. <span data-ttu-id="eb7f5-182">Überprüfen Sie im Abschnitt **Zuverlässigkeit** optional Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-182">In the **Reliability** section, optionally check:</span></span>  
  
    -   <span data-ttu-id="eb7f5-183">**Sicherung nach dem Abschluss überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-183">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="eb7f5-184">**Vor dem Schreiben auf die Medien Prüfsumme bilden**, und optional **Bei Prüfsummenfehler fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-184">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="eb7f5-185">Weitere Informationen finden Sie unter [Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-185">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="eb7f5-186">Wenn Sie auf ein Bandlaufwerk sichern (gemäß der Konfiguration im Abschnitt **Ziel** der Seite **Allgemein** ), ist die Option **Band nach dem Sichern entladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-186">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="eb7f5-187">Wenn Sie auf diese Option klicken, wird die Option **Band vor dem Entladen zurückspulen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-187">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb7f5-188">Die Optionen im Abschnitt **Transaktionsprotokoll** sind inaktiv, es sei denn, Sie sichern ein Transaktionsprotokoll (wie im Abschnitt **Sicherungstyp** der Seite **Allgemein** angegeben).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-188">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
16. <span data-ttu-id="eb7f5-189">Klicken Sie im Bereich **Seite auswählen** auf **Sicherungsoptionen** , um die Sicherungsoptionen anzuzeigen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-189">To view or select the backup options, click **Backup Options** in the **Select a page** pane.</span></span>  
  
17. <span data-ttu-id="eb7f5-190">Geben Sie an, wann der Sicherungssatz abläuft und überschrieben werden kann, ohne die Überprüfung der Ablaufdaten explizit auszulassen:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-190">Specify when the backup set will expire and can be overwritten without explicitly skipping verification of the expiration data:</span></span>  
  
    -   <span data-ttu-id="eb7f5-191">Wenn der Sicherungssatz nach einer bestimmten Anzahl von Tagen ablaufen soll, klicken Sie auf **Nach** (die Standardoption), und geben Sie an, nach wie vielen Tagen der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-191">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="eb7f5-192">Dieser Wert kann zwischen 0 und 99999 Tagen liegen. Ein Wert von 0 Tagen bedeutet, dass der Sicherungssatz nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-192">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="eb7f5-193">Der Standardwert wird mit der Option **Standardbeibehaltung für Sicherungsmedien (in Tagen)** im Dialogfeld **Servereigenschaften** (Seite "Datenbankeinstellungen") festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-193">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (Database Settings Page).</span></span> <span data-ttu-id="eb7f5-194">Klicken Sie hierzu mit der rechten Maustaste auf den Servernamen im Objekt-Explorer, und wählen Sie Eigenschaften aus. Wählen Sie anschließend die Seite **Datenbankeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-194">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="eb7f5-195">Zum Speichern des Sicherungssatzes an einem bestimmten Datum klicken Sie auf **Am**. Geben Sie das Datum ein, an dem der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-195">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
         <span data-ttu-id="eb7f5-196">Weitere Informationen zum Ablaufdatum von Sicherungen finden Sie unter [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="eb7f5-196">For more information about backup expiration dates, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
18. [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="eb7f5-197">und höheren Versionen wird die [Sicherungskomprimierung](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-197">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="eb7f5-198">Ob eine Sicherung standardmäßig komprimiert wird, ist abhängig vom Wert der Serverkonfigurationsoption **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="eb7f5-198">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="eb7f5-199">Sie können jedoch unabhängig von der aktuellen Standardeinstellung auf Serverebene eine Sicherung komprimieren, indem Sie die Option **Sicherung komprimieren**aktivieren, oder die Komprimierung verhindern, indem Sie die Option **Sicherung nicht komprimieren**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-199">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="eb7f5-200">**So zeigen Sie die aktuelle Standardeinstellung für die Sicherungskomprimierung an oder ändern sie**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-200">**To view or change the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="eb7f5-201">Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="eb7f5-201">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
19. <span data-ttu-id="eb7f5-202">Geben Sie an, ob die Sicherung verschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-202">Specify whether to use encryption for the backup.</span></span> <span data-ttu-id="eb7f5-203">Wählen Sie einen Verschlüsselungsalgorithmus für den Verschlüsselungsschritt aus, und geben Sie ein Zertifikat oder einen asymmetrischen Schlüssel aus der Liste der vorhandenen Zertifikate und asymmetrischen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-203">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="eb7f5-204">Die Verschlüsselung wird in SQL Server 2014 und höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-204">Encryption is supported in SQL Server 2014 or later.</span></span> <span data-ttu-id="eb7f5-205">Weitere Informationen zu den Verschlüsselungsoptionen finden Sie unter [Datenbank sichern &#40;Seite 'Sicherungsoptionen'&#41;](back-up-database-backup-options-page.md):</span><span class="sxs-lookup"><span data-stu-id="eb7f5-205">For more details on the Encryption options, see [Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb7f5-206">Alternativ können Sie den Wartungsplanungs-Assistenten zum Erstellen von Datenbanksicherungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-206">Alternatively, you can use the Maintenance Plan Wizard to create database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eb7f5-207">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb7f5-207">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-full-database-backup"></a><span data-ttu-id="eb7f5-208">So erstellen Sie eine vollständige Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="eb7f5-208">To create a full database backup</span></span>  
  
1.  <span data-ttu-id="eb7f5-209">Führen Sie die BACKUP DATABASE-Anweisung aus, um die vollständige Datenbanksicherung zu erstellen, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-209">Execute the BACKUP DATABASE statement to create the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="eb7f5-210">Den Namen der zu sichernden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-210">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="eb7f5-211">Das Sicherungsmedium, auf das die vollständige Datenbanksicherung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-211">The backup device where the full database backup is written.</span></span>  
  
     <span data-ttu-id="eb7f5-212">Die grundlegende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Syntax zum Erstellen einer vollständigen Datenbanksicherung lautet:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-212">The basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for a full database backup is:</span></span>  
  
     <span data-ttu-id="eb7f5-213">BACKUP DATABASE *database*</span><span class="sxs-lookup"><span data-stu-id="eb7f5-213">BACKUP DATABASE *database*</span></span>  
  
     <span data-ttu-id="eb7f5-214">TO *backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="eb7f5-214">TO *backup_device* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="eb7f5-215">[ WITH *mit_Optionen* [ **,** ...*o* ] ] ;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-215">[ WITH *with_options* [ **,**...*o* ] ] ;</span></span>  
  
    |<span data-ttu-id="eb7f5-216">Option</span><span class="sxs-lookup"><span data-stu-id="eb7f5-216">Option</span></span>|<span data-ttu-id="eb7f5-217">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb7f5-217">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="eb7f5-218">*database*</span><span class="sxs-lookup"><span data-stu-id="eb7f5-218">*database*</span></span>|<span data-ttu-id="eb7f5-219">Die Datenbank, für die eine Sicherungskopie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-219">Is the database that is to be backed up.</span></span>|  
    |<span data-ttu-id="eb7f5-220">*Sicherungsmedium* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="eb7f5-220">*backup_device* [ **,**...*n* ]</span></span>|<span data-ttu-id="eb7f5-221">Gibt eine Liste an, die zwischen 1 und 64 Sicherungsmedien für den Sicherungsvorgang enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-221">Specifies a list of from 1 to 64 backup devices to use for the backup operation.</span></span> <span data-ttu-id="eb7f5-222">Sie können ein physisches Sicherungsmedium angeben oder ein entsprechendes logisches Sicherungsmedium, sofern es bereits definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-222">You can specify a physical backup device, or you can specify a corresponding logical backup device, if already defined.</span></span> <span data-ttu-id="eb7f5-223">Geben Sie das physische Sicherungsmedium mithilfe der Option DISK oder TAPE an:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-223">To specify a physical backup device, use the DISK or TAPE option:</span></span><br /><br /> <span data-ttu-id="eb7f5-224">{ DISK &#124; TAPE } **=** _physischer_Sicherungsmediumname_</span><span class="sxs-lookup"><span data-stu-id="eb7f5-224">{ DISK &#124; TAPE } **=**_physical_backup_device_name_</span></span><br /><br /> <span data-ttu-id="eb7f5-225">Weitere Informationen finden Sie unter [Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md)aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-225">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>|  
    |<span data-ttu-id="eb7f5-226">WITH *with_options* [ **,** ...*o* ]</span><span class="sxs-lookup"><span data-stu-id="eb7f5-226">WITH *with_options* [ **,**...*o* ]</span></span>|<span data-ttu-id="eb7f5-227">Optional geben Sie eine oder mehrere zusätzliche Optionen an, *o*.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-227">Optionally, specifies one or more additional options, *o*.</span></span> <span data-ttu-id="eb7f5-228">Weitere Informationen zu einigen der grundlegenden Optionen finden Sie unter Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-228">For information about some of the basic with options, see step 2.</span></span>|  
  
2.  <span data-ttu-id="eb7f5-229">Geben Sie optional eine oder mehrere WITH-Optionen an.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-229">Optionally, specify one or more WITH options.</span></span> <span data-ttu-id="eb7f5-230">Einige der grundlegenden WITH-Optionen werden hier beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-230">A few basic WITH options are described here.</span></span> <span data-ttu-id="eb7f5-231">Weitere Informationen zu allen WITH-Optionen finden Sie unter [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb7f5-231">For information about all the WITH options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
    -   <span data-ttu-id="eb7f5-232">Grundlegender Sicherungssatz von WITH-Optionen:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-232">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="eb7f5-233">{ COMPRESSION | NO_COMPRESSION }</span><span class="sxs-lookup"><span data-stu-id="eb7f5-233">{ COMPRESSION | NO_COMPRESSION }</span></span>  
         <span data-ttu-id="eb7f5-234">Nur in [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] und höher verfügbar. Gibt an, ob für diese Sicherung eine [Sicherungskomprimierung](backup-compression-sql-server.md) verwendet wird, wodurch die Standardeinstellung auf Serverebene überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-234">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] and later only, specifies whether [backup compression](backup-compression-sql-server.md) is performed on this backup, overriding the server-level default.</span></span>  
  
         <span data-ttu-id="eb7f5-235">VERSCHLÜSSELUNG (ALGORITHMUS, SERVERZERTIFIKAT | ASYMMETRISCHER SCHLÜSSEL)</span><span class="sxs-lookup"><span data-stu-id="eb7f5-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span></span>  
         <span data-ttu-id="eb7f5-236">Nur in SQL Server 2014 und höheren Versionen geben Sie den zu verwendenden Verschlüsselungsalgorithmus und das Zertifikat oder den asymmetrischen Schlüssel an, die die Sicherheit bei der Verschlüsselung erhöhen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-236">In SQL Server 2014 or later only, specify the encryption algorithm to use, and the Certificate or Asymmetric key to use to secure the encryption.</span></span>  
  
         <span data-ttu-id="eb7f5-237">Beschreibung **=** { **' *`text`* '**  |  **@** _text_variable_ }</span><span class="sxs-lookup"><span data-stu-id="eb7f5-237">DESCRIPTION **=** { **'*`text`*'** | **@**_text_variable_ }</span></span>  
         <span data-ttu-id="eb7f5-238">Gibt den Text an, mit dem der Sicherungssatz beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-238">Specifies the free-form text that describes the backup set.</span></span> <span data-ttu-id="eb7f5-239">Die Zeichenfolge kann maximal 255 Zeichen haben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-239">The string can have a maximum of 255 characters.</span></span>  
  
         <span data-ttu-id="eb7f5-240">Name **=** { *backup_set_name*  |  **@** _backup_set_name_var_ }</span><span class="sxs-lookup"><span data-stu-id="eb7f5-240">NAME **=** { *backup_set_name* | **@**_backup_set_name_var_ }</span></span>  
         <span data-ttu-id="eb7f5-241">Gibt den Namen des Sicherungssatzes an.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-241">Specifies the name of the backup set.</span></span> <span data-ttu-id="eb7f5-242">Namen können maximal 128 Zeichen haben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-242">Names can have a maximum of 128 characters.</span></span> <span data-ttu-id="eb7f5-243">Wird NAME nicht angegeben, erhält der Sicherungssatz einen leeren Namen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-243">If NAME is not specified, it is blank.</span></span>  
  
    -   <span data-ttu-id="eb7f5-244">Grundlegender Sicherungssatz von WITH-Optionen:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-244">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="eb7f5-245">Standardmäßig fügt BACKUP die Sicherung einem vorhandenen Mediensatz an, wobei vorhandene Sicherungssätze beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-245">By default, BACKUP appends the backup to an existing media set, preserving existing backup sets.</span></span> <span data-ttu-id="eb7f5-246">Verwenden Sie die NOINIT-Option, um dies explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-246">To explicitly specify this, use the NOINIT option.</span></span> <span data-ttu-id="eb7f5-247">Informationen über das Anfügen an vorhandene Sicherungssätze finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md):</span><span class="sxs-lookup"><span data-stu-id="eb7f5-247">For information about appending to existing backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="eb7f5-248">Verwenden Sie alternativ die FORMAT-Option, um die Sicherungsmedien zu formatieren:</span><span class="sxs-lookup"><span data-stu-id="eb7f5-248">Alternatively, to format the backup media, use the FORMAT option:</span></span>  
  
         <span data-ttu-id="eb7f5-249">Format [ **,** MEDIANAME **=** { *media_name*  |  **@** _media_name_variable_ }] [ **,** mediadeabo **=** { *Text*  |  **@** _text_variable_ }]</span><span class="sxs-lookup"><span data-stu-id="eb7f5-249">FORMAT [ **,** MEDIANAME**=** { *media_name* | **@**_media_name_variable_ } ] [ **,** MEDIADESCRIPTION **=** { *text* | **@**_text_variable_ } ]</span></span>  
         <span data-ttu-id="eb7f5-250">Verwenden Sie die FORMAT-Klausel, wenn Sie das Medium das erste Mal einsetzen oder alle vorhandenen Daten überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-250">Use the FORMAT clause when you are using media for the first time or you want to overwrite all existing data.</span></span> <span data-ttu-id="eb7f5-251">Weisen Sie den neuen Medien optional einen Mediennamen und eine Beschreibung zu.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-251">Optionally, assign the new media a media name and description.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="eb7f5-252">Gehen Sie mit den FORMAT- und INIT-Klauseln der BACKUP-Anweisung äußerst vorsichtig um, denn sie zerstören alle zuvor auf dem Sicherungsmedium gespeicherten Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-252">Use extreme caution when you are using the FORMAT clause of the BACKUP statement because this destroys any backups that were previously stored on the backup media.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="eb7f5-253">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eb7f5-253">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-backing-up-to-a-disk-device"></a><span data-ttu-id="eb7f5-254">A.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-254">A.</span></span> <span data-ttu-id="eb7f5-255">Sichern auf ein Datenträgermedium</span><span class="sxs-lookup"><span data-stu-id="eb7f5-255">Backing up to a disk device</span></span>  
 <span data-ttu-id="eb7f5-256">In diesem Beispiel wird die gesamte [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank auf dem Datenträger gesichert, wobei mithilfe von `FORMAT` ein neuer Mediensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-256">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to disk, by using `FORMAT` to create a new media set.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH FORMAT,  
      MEDIANAME = 'Z_SQLServerBackups',  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="b-backing-up-to-a-tape-device"></a><span data-ttu-id="eb7f5-257">B.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-257">B.</span></span> <span data-ttu-id="eb7f5-258">Sichern auf ein Bandmedium</span><span class="sxs-lookup"><span data-stu-id="eb7f5-258">Backing up to a tape device</span></span>  
 <span data-ttu-id="eb7f5-259">Im folgenden Beispiel wird die gesamte [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Datenbank auf Band gesichert, wobei die Sicherung an vorherige Sicherungen angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-259">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]database to tape, appending the backup to the previous backups.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO TAPE = '\\.\Tape0'  
   WITH NOINIT,  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="c-backing-up-to-a-logical-tape-device"></a><span data-ttu-id="eb7f5-260">C.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-260">C.</span></span> <span data-ttu-id="eb7f5-261">Sichern auf ein logisches Bandmedium</span><span class="sxs-lookup"><span data-stu-id="eb7f5-261">Backing up to a logical tape device</span></span>  
 <span data-ttu-id="eb7f5-262">Im folgenden Beispiel wird ein logisches Sicherungsmedium für ein Bandlaufwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-262">The following example creates a logical backup device for a tape drive.</span></span> <span data-ttu-id="eb7f5-263">Im Beispiel wird dann die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank vollständig auf diesem Medium gesichert.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-263">The example then backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to that device.</span></span>  
  
```sql  
-- Create a logical backup device,   
-- AdventureWorks2012_Bak_Tape, for tape device \\.\tape0.  
USE master;  
GO  
EXEC sp_addumpdevice 'tape', 'AdventureWorks2012_Bak_Tape', '\\.\tape0'; USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO AdventureWorks2012_Bak_Tape  
   WITH FORMAT,  
      MEDIANAME = 'AdventureWorks2012_Bak_Tape',  
      MEDIADESCRIPTION = '\\.\tape0',   
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="eb7f5-264">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb7f5-264">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="eb7f5-265">Verwenden Sie das `Backup-SqlDatabase`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-265">Use the `Backup-SqlDatabase` cmdlet.</span></span> <span data-ttu-id="eb7f5-266">Um explizit anzugeben, dass es sich um eine vollständige Datenbanksicherung handelt, geben Sie den **-Backup Action-** Parameter mit dem Standardwert an `Database` .</span><span class="sxs-lookup"><span data-stu-id="eb7f5-266">To explicitly indicate that this is a full database backup, specify the **-BackupAction**  parameter with its default value, `Database`.</span></span> <span data-ttu-id="eb7f5-267">Dieser Parameter ist bei vollständigen Datenbanksicherungen optional.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-267">This parameter is optional for full database backups.</span></span>  
  
     <span data-ttu-id="eb7f5-268">Im folgenden Beispiel wird eine vollständige Datenbanksicherung der `MyDB` -Datenbank am standardmäßigen Sicherungsspeicherort der Serverinstanz `Computer\Instance`erstellt.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-268">The following example creates a full database backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span> <span data-ttu-id="eb7f5-269">Optional wird im Beispiel `-BackupAction Database` angegeben.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-269">Optionally, this example specifies `-BackupAction Database`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Database  
    ```  
  
 <span data-ttu-id="eb7f5-270">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-270">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="eb7f5-271">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="eb7f5-271">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="eb7f5-272">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="eb7f5-272">Related Tasks</span></span>  
  
-   [<span data-ttu-id="eb7f5-273">Erstellen einer vollständigen Datenbanksicherung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eb7f5-273">Back Up a Database (SQL Server)</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="eb7f5-274">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-274">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="eb7f5-275">Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-275">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="eb7f5-276">Wiederherstellen einer Datenbanksicherung unter dem einfachen Wiederherstellungsmodell &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-276">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="eb7f5-277">Wiederherstellen einer Datenbank bis zum Fehlerzeitpunkt im vollständigen Wiederherstellungsmodell &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-277">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="eb7f5-278">Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-278">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="eb7f5-279">Verwenden des Wartungsplanungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="eb7f5-279">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb7f5-280">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb7f5-280">See Also</span></span>  
 <span data-ttu-id="eb7f5-281">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-281">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="eb7f5-282">[Transaktionsprotokollsicherungen &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-282">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="eb7f5-283">[Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-283">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="eb7f5-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="eb7f5-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="eb7f5-286">[Datenbank sichern &#40;Seite Allgemein&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-286">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="eb7f5-287">[Datenbank sichern &#40;Seite 'Sicherungsoptionen'&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-287">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="eb7f5-288">[Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb7f5-288">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="eb7f5-289">Vollständige Datenbanksicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb7f5-289">Full Database Backups &#40;SQL Server&#41;</span></span>](full-database-backups-sql-server.md)  
