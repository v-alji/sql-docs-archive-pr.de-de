---
title: Verschieben von Benutzerdatenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- editions [SQL Server], moving databases between
- moving full-text catalogs
- scheduled disk maintenace [SQL Server]
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- moving user databases
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: ad9a4e92-13fb-457d-996a-66ffc2d55b79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c2b82c3bec13c82aa30aebd175ef78f8136ee04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617099"
---
# <a name="move-user-databases"></a><span data-ttu-id="85b93-102">Verschieben von Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="85b93-102">Move User Databases</span></span>
  <span data-ttu-id="85b93-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]können Sie die Daten-, Protokoll- und Volltextkatalogdateien einer Benutzerdatenbank an einen neuen Speicherort verschieben, indem Sie den neuen Dateispeicherort in der FILENAME-Klausel der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung angeben.</span><span class="sxs-lookup"><span data-stu-id="85b93-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move the data, log, and full-text catalog files of a user database to a new location by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="85b93-104">Diese Methode ermöglicht das Verschieben von Datenbankdateien innerhalb derselben Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85b93-104">This method applies to moving database files within the same instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="85b93-105">Wenn Sie eine Datenbank auf eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder einen anderen Server verschieben möchten, verwenden Sie [Sicherungs- und Wiederherstellungs-](../backup-restore/back-up-and-restore-of-sql-server-databases.md) oder [Trennungs- und Anfügungsoperationen](move-a-database-using-detach-and-attach-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="85b93-105">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach operations](move-a-database-using-detach-and-attach-transact-sql.md).</span></span>  
  
## <a name="considerations"></a><span data-ttu-id="85b93-106">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="85b93-106">Considerations</span></span>  
 <span data-ttu-id="85b93-107">Wenn Sie eine Datenbank auf eine andere Serverinstanz verschieben, müssen Sie möglicherweise einen Teil oder auch alle Metadaten für die Datenbank erneut erstellen, um Benutzern und Anwendungen ein konsistentes Verhalten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="85b93-107">When you move a database onto another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all the metadata for the database.</span></span> <span data-ttu-id="85b93-108">Weitere Informationen finden Sie unter [Verwalten von Metadaten beim Bereitstellen einer Datenbank auf einer anderen Serverinstanz &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="85b93-108">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
 <span data-ttu-id="85b93-109">Einige Funktionen von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ändern die Art und Weise, wie [!INCLUDE[ssDE](../../includes/ssde-md.md)] Informationen in den Datenbankdateien speichert.</span><span class="sxs-lookup"><span data-stu-id="85b93-109">Some features of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] change the way that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores information in the database files.</span></span> <span data-ttu-id="85b93-110">Diese Funktionen sind nicht in allen Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="85b93-110">These features are restricted to specific editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="85b93-111">Eine Datenbank, die diese Funktionen enthält, kann nicht in eine Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verschoben werden, die sie nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85b93-111">A database that contains these features cannot be moved to an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that does not support them.</span></span> <span data-ttu-id="85b93-112">Verwenden Sie die dynamische Verwaltungssicht sys.dm_db_persisted_sku_features, um alle editionsspezifischen Funktionen aufzulisten, die in der aktuellen Datenbank aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="85b93-112">Use the sys.dm_db_persisted_sku_features dynamic management view to list all edition-specific features that are enabled in the current database.</span></span>  
  
 <span data-ttu-id="85b93-113">Für die Prozeduren in diesem Thema ist der logische Name der Datenbankdateien erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85b93-113">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="85b93-114">Zum Abrufen des Namens führen Sie eine Abfrage für die Namensspalte in der [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) -Katalogsicht aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-114">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="85b93-115">Ab [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]sind Volltextkataloge in die Datenbank integriert, statt im Dateisystem gespeichert.</span><span class="sxs-lookup"><span data-stu-id="85b93-115">Starting with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], full-text catalogs are integrated into the database rather than being stored in the file system.</span></span> <span data-ttu-id="85b93-116">Die Volltextkataloge werden jetzt automatisch verschoben, wenn Sie eine Datenbank verschieben.</span><span class="sxs-lookup"><span data-stu-id="85b93-116">The full-text catalogs now move automatically when you move a database.</span></span>  
  
## <a name="planned-relocation-procedure"></a><span data-ttu-id="85b93-117">Prozedur zur geplanten Verschiebung</span><span class="sxs-lookup"><span data-stu-id="85b93-117">Planned Relocation Procedure</span></span>  
 <span data-ttu-id="85b93-118">Zum Verschieben einer Daten- oder Protokolldatei im Rahmen einer geplanten Verschiebung müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="85b93-118">To move a data or log file as part of a planned relocation, follow these steps:</span></span>  
  
1.  <span data-ttu-id="85b93-119">Führen Sie die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-119">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET OFFLINE;  
    ```  
  
2.  <span data-ttu-id="85b93-120">Verschieben Sie die Datei(en) an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="85b93-120">Move the file or files to the new location.</span></span>  
  
3.  <span data-ttu-id="85b93-121">Führen Sie für jede verschobene Datei die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-121">For each file moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name, FILENAME = 'new_path\os_file_name' );  
    ```  
  
4.  <span data-ttu-id="85b93-122">Führen Sie die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-122">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET ONLINE;  
    ```  
  
5.  <span data-ttu-id="85b93-123">Überprüfen Sie die Dateiänderung durch Ausführen der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="85b93-123">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="relocation-for-scheduled-disk-maintenance"></a><span data-ttu-id="85b93-124">Verschiebung aufgrund planmäßiger Datenträgerwartung</span><span class="sxs-lookup"><span data-stu-id="85b93-124">Relocation for Scheduled Disk Maintenance</span></span>  
 <span data-ttu-id="85b93-125">Zum Verschieben einer Datei im Rahmen eines planmäßigen Datenträgerwartungsprozesses müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="85b93-125">To relocate a file as part of a scheduled disk maintenance process, follow these steps:</span></span>  
  
1.  <span data-ttu-id="85b93-126">Führen Sie für jede zu verschiebende Datei die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-126">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
2.  <span data-ttu-id="85b93-127">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , oder fahren Sie das System für die Wartungsarbeiten herunter.</span><span class="sxs-lookup"><span data-stu-id="85b93-127">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="85b93-128">Weitere Informationen finden Sie unter [Starten, Beenden, Anhalten, Fortsetzen und Neustarten von SQL Server-Diensten](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="85b93-128">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="85b93-129">Verschieben Sie die Datei(en) an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="85b93-129">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="85b93-130">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder den Server neu.</span><span class="sxs-lookup"><span data-stu-id="85b93-130">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="85b93-131">Weitere Informationen finden Sie unter [Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="85b93-131">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span></span>  
  
5.  <span data-ttu-id="85b93-132">Überprüfen Sie die Dateiänderung durch Ausführen der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="85b93-132">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="failure-recovery-procedure"></a><span data-ttu-id="85b93-133">Prozedur zur Wiederherstellung nach Fehlern</span><span class="sxs-lookup"><span data-stu-id="85b93-133">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="85b93-134">Wenn eine Datei aufgrund eines Hardwarefehlers verschoben werden muss, müssen Sie die folgenden Schritte ausführen, um die Datei an einen neuen Speicherort zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="85b93-134">If a file must be moved because of a hardware failure, use the following steps to relocate the file to a new location.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="85b93-135">Wenn die Datenbank nicht gestartet werden kann, d. h., wenn sie als fehlerverdächtig eingestuft wurde oder sich in einem nicht wiederhergestellten Status befindet, können nur Mitglieder der festen Rolle sysadmin die Datei verschieben.</span><span class="sxs-lookup"><span data-stu-id="85b93-135">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="85b93-136">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , wenn sie gestartet ist.</span><span class="sxs-lookup"><span data-stu-id="85b93-136">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="85b93-137">Starten Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz im ausschließlichen Wiederherstellungsmodus der master-Datenbank durch Eingeben der folgenden Befehle an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="85b93-137">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span>  
  
    -   <span data-ttu-id="85b93-138">Führen Sie für die Standardinstanz (MSSQLSERVER) den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-138">For the default (MSSQLSERVER) instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="85b93-139">Führen Sie für eine benannte Instanz den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="85b93-139">For a named instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="85b93-140">Weitere Informationen finden Sie unter [Starten, Beenden, Anhalten, Fortsetzen und Neustarten von SQL Server-Diensten](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="85b93-140">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="85b93-141">Verwenden Sie für jede zu verschiebende Datei die **sqlcmd** -Befehle oder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , um die folgende Anweisung auszuführen:</span><span class="sxs-lookup"><span data-stu-id="85b93-141">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
     <span data-ttu-id="85b93-142">Weitere Informationen zum Verwenden des **sqlcmd** -Hilfsprogramms finden Sie unter [Verwenden des Hilfsprogramms „sqlcmd“](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="85b93-142">For more information about how to use the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="85b93-143">Starten Sie das Hilfsprogramm **sqlcmd** oder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85b93-143">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="85b93-144">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85b93-144">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="85b93-145">Verschieben Sie die Datei(en) an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="85b93-145">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="85b93-146">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85b93-146">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="85b93-147">Führen Sie z. B. folgenden Befehl aus: `NET START MSSQLSERVER`</span><span class="sxs-lookup"><span data-stu-id="85b93-147">For example, run: `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="85b93-148">Überprüfen Sie die Dateiänderung durch Ausführen der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="85b93-148">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="examples"></a><span data-ttu-id="85b93-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="85b93-149">Examples</span></span>  
 <span data-ttu-id="85b93-150">Im folgenden Beispiel wird die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Protokolldatei im Rahmen einer geplanten Verschiebung an einen neuen Speicherort verschoben.</span><span class="sxs-lookup"><span data-stu-id="85b93-150">The following example moves the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] log file to a new location as part of a planned relocation.</span></span>  
  
```  
USE master;  
GO  
-- Return the logical file name.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
GO  
ALTER DATABASE AdventureWorks2012 SET OFFLINE;  
GO  
-- Physically move the file to a new location.  
-- In the following statement, modify the path specified in FILENAME to  
-- the new location of the file on your server.  
ALTER DATABASE AdventureWorks2012   
    MODIFY FILE ( NAME = AdventureWorks2012_Log,   
                  FILENAME = 'C:\NewLoc\AdventureWorks2012_Log.ldf');  
GO  
ALTER DATABASE AdventureWorks2012 SET ONLINE;  
GO  
--Verify the new location.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
```  
  
## <a name="see-also"></a><span data-ttu-id="85b93-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85b93-151">See Also</span></span>  
 <span data-ttu-id="85b93-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85b93-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="85b93-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85b93-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="85b93-154">[Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85b93-154">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="85b93-155">[Verschieben von Systemdatenbanken](system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="85b93-155">[Move System Databases](system-databases.md) </span></span>  
 <span data-ttu-id="85b93-156">[Verschieben von Datenbankdateien](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="85b93-156">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="85b93-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85b93-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="85b93-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85b93-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="85b93-159">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="85b93-159">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
