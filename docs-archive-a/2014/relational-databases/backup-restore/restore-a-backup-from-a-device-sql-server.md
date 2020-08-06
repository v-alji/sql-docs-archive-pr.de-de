---
title: Wiederherstellung einer Sicherung von einem Gerät (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring databases [SQL Server], device restores
- backup devices [SQL Server], restoring from
- database restores [SQL Server], device restores
- devices [SQL Server]
ms.assetid: 6e139de7-7de2-4d18-9df0-beac31ba7ff1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50d7f7b8e255aea470a1065df669c0cc3169a8dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698325"
---
# <a name="restore-a-backup-from-a-device-sql-server"></a><span data-ttu-id="a8766-102">Wiederherstellung einer Sicherung von einem Medium (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a8766-102">Restore a Backup from a Device (SQL Server)</span></span>
  <span data-ttu-id="a8766-103">In diesem Thema wird beschrieben, wie Sie ein Sicherung von einem Gerät in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="a8766-103">This topic describes how to restore a backup from a device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8766-104">Informationen zur SQL Server Sicherung im Azure-BLOB-Speicherdienst finden Sie unter [SQL Server sichern und Wiederherstellen mit Azure BLOB Storage Dienst](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="a8766-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="a8766-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a8766-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a8766-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a8766-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a8766-107">Security</span><span class="sxs-lookup"><span data-stu-id="a8766-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a8766-108">**So stellen Sie eine Sicherung von einem Medium wieder her mit**</span><span class="sxs-lookup"><span data-stu-id="a8766-108">**To restore a backup from a device, using:**</span></span>  
  
     [<span data-ttu-id="a8766-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8766-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a8766-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8766-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a8766-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a8766-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a8766-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a8766-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a8766-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a8766-113">Permissions</span></span>  
 <span data-ttu-id="a8766-114">Ist die wiederherzustellende Datenbank nicht vorhanden, muss der Benutzer über CREATE DATABASE-Berechtigungen verfügen, um RESTORE ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a8766-114">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="a8766-115">Ist die Datenbank vorhanden, werden RESTORE-Berechtigungen standardmäßig den Mitgliedern der festen Serverrollen **sysadmin** und **dbcreator** sowie dem Besitzer (**dbo**) der Datenbank erteilt (für die Option FROM DATABASE_SNAPSHOT ist die Datenbank immer vorhanden).</span><span class="sxs-lookup"><span data-stu-id="a8766-115">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="a8766-116">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a8766-116">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="a8766-117">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="a8766-117">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8766-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8766-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="a8766-119">So stellen Sie eine Sicherung von einem Medium wieder her</span><span class="sxs-lookup"><span data-stu-id="a8766-119">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="a8766-120">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a8766-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a8766-121">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="a8766-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="a8766-122">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="a8766-122">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="a8766-123">Klicken Sie auf den gewünschten Wiederherstellungsvorgangstyp (**Datenbank**, **Dateien und Dateigruppen**oder **Transaktionsprotokoll**).</span><span class="sxs-lookup"><span data-stu-id="a8766-123">Click the type of restore operation you want (**Database**, **Files and Filegroups**, or **Transaction Log**).</span></span> <span data-ttu-id="a8766-124">Dadurch wird das entsprechende Wiederherstellungsdialogfeld geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a8766-124">This opens the corresponding restore dialog box.</span></span>  
  
5.  <span data-ttu-id="a8766-125">Klicken Sie auf der Seite **Allgemein** im Abschnitt **Wiederherstellungsquelle** auf **Von Medium**.</span><span class="sxs-lookup"><span data-stu-id="a8766-125">On the **General** page, in the **Restore source** section, click **From device**.</span></span>  
  
6.  <span data-ttu-id="a8766-126">Klicken Sie auf die Schaltfläche zum Durchsuchen für das Textfeld **Von Medium** , sodass das Dialogfeld **Sicherung angeben** geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="a8766-126">Click the browse button for the **From device** text box, which opens the **Specify Backup** dialog box.</span></span>  
  
7.  <span data-ttu-id="a8766-127">Wählen Sie im Textfeld **Sicherungsmedium** das entsprechende **Sicherungsmedium** aus, und klicken Sie dann auf die Schaltfläche **Hinzufügen** , um das Dialogfeld **Sicherungsmedium auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a8766-127">In the **Backup media** text box, select **Backup Device**, and click the **Add** button to open the **Select Backup Device** dialog box.</span></span>  
  
8.  <span data-ttu-id="a8766-128">Wählen Sie im Textfeld **Sicherungsmedium** das Medium aus, das Sie für den Wiederherstellungsvorgang verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a8766-128">In the **Backup device** text box, select the device you want to use for the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8766-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8766-129">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="a8766-130">So stellen Sie eine Sicherung von einem Medium wieder her</span><span class="sxs-lookup"><span data-stu-id="a8766-130">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="a8766-131">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a8766-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a8766-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a8766-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a8766-133">Geben Sie in der [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Anweisung ein logisches oder physisches Sicherungsmedium an, das für den Sicherungsvorgang verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8766-133">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify a logical or physical backup device to use for the backup operation.</span></span> <span data-ttu-id="a8766-134">In diesem Beispiel wird ein Wiederherstellungsvorgang von einer Datenträgerdatei mit dem physischen Namen `Z:\SQLServerBackups\AdventureWorks2012.bak`ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8766-134">This example restores from a disk file that has the physical name `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak' ;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8766-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8766-135">See Also</span></span>  
 <span data-ttu-id="a8766-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a8766-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="a8766-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a8766-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="a8766-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a8766-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="a8766-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a8766-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="a8766-140">[Wiederherstellen einer Datenbanksicherung unter dem einfachen Wiederherstellungsmodell &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="a8766-140">[Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span></span>  
 <span data-ttu-id="a8766-141">[Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="a8766-141">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="a8766-142">[Wiederherstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8766-142">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="a8766-143">[Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8766-143">[Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="a8766-144">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8766-144">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="a8766-145">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8766-145">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="a8766-146">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8766-146">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
