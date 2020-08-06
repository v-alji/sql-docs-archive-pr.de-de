---
title: Geben Sie an, ob ein Sicherungs-oder Wiederherstellungs Vorgang fortgesetzt oder angehalten wird, nachdem ein Fehler (SQL Server) Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], backups
- backing up databases [SQL Server], errors
- backups [SQL Server], errors
- database backups [SQL Server], errors
ms.assetid: 042be17a-b9b0-4629-b6bb-b87a8bc6c316
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 87cccec6f7eea18f2750d3b0be81b577b0eb170a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621519"
---
# <a name="specify-whether-a-backup-or-restore-operation-continues-or-stops-after-encountering-an-error-sql-server"></a><span data-ttu-id="c6484-102">Angeben, ob ein Sicherungs- oder Wiederherstellungsvorgang fortgesetzt wird, nachdem ein Fehler festgestellt wurde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c6484-102">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error (SQL Server)</span></span>
  <span data-ttu-id="c6484-103">In diesem Thema wird beschrieben, wie Sie bestimmen können, ob ein Sicherungs- oder Wiederherstellungsvorgang entweder fortgesetzt oder angehalten werden soll, nachdem ein Fehler in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]festgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c6484-103">This topic describes how to specify whether a backup or restore operation continues or stops after encountering an error in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c6484-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c6484-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6484-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c6484-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6484-106">Security</span><span class="sxs-lookup"><span data-stu-id="c6484-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6484-107">**So bestimmen Sie, ob ein Sicherungs- oder Wiederherstellungsvorgang fortgesetzt wird, nachdem ein Fehler festgestellt wurde, mit**</span><span class="sxs-lookup"><span data-stu-id="c6484-107">**To specify whether a backup or restore operation continues after encountering an error, using:**</span></span>  
  
     [<span data-ttu-id="c6484-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6484-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6484-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6484-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6484-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c6484-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6484-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c6484-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6484-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c6484-112">Permissions</span></span>  
 <span data-ttu-id="c6484-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="c6484-113">BACKUP</span></span>  
 <span data-ttu-id="c6484-114">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="c6484-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="c6484-115">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="c6484-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c6484-116">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="c6484-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="c6484-117">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="c6484-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="c6484-118">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c6484-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="c6484-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="c6484-119">RESTORE</span></span>  
 <span data-ttu-id="c6484-120">Ist die wiederherzustellende Datenbank nicht vorhanden, muss der Benutzer über CREATE DATABASE-Berechtigungen verfügen, um RESTORE ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="c6484-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="c6484-121">Ist die Datenbank vorhanden, werden RESTORE-Berechtigungen standardmäßig den Mitgliedern der festen Serverrollen **sysadmin** und **dbcreator** sowie dem Besitzer (**dbo**) der Datenbank erteilt (für die Option FROM DATABASE_SNAPSHOT ist die Datenbank immer vorhanden).</span><span class="sxs-lookup"><span data-stu-id="c6484-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="c6484-122">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c6484-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="c6484-123">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="c6484-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6484-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6484-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-whether-backup-continues-or-stops-after-an-error-is-encountered"></a><span data-ttu-id="c6484-125">So bestimmen Sie, ob eine Sicherung fortgesetzt oder angehalten werden soll, nachdem ein Fehler gefunden wurde</span><span class="sxs-lookup"><span data-stu-id="c6484-125">To specify whether backup continues or stops after an error is encountered</span></span>  
  
1.  <span data-ttu-id="c6484-126">Führen Sie die Schritte aus, [um eine Datenbanksicherung zu erstellen](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6484-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="c6484-127">Klicken Sie auf der Seite **Optionen** im Bereich **Zuverlässigkeit** auf **Vor dem Schreiben auf die Medien Prüfsumme bilden** und dann auf **Bei Fehler fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="c6484-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media** and **Continue on error**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6484-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6484-128">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-whether-a-backup-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="c6484-129">So bestimmen Sie, ob ein Sicherungsvorgang fortgesetzt oder angehalten wird, nachdem ein Fehler festgestellt wurde</span><span class="sxs-lookup"><span data-stu-id="c6484-129">To specify whether a backup operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="c6484-130">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="c6484-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6484-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6484-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6484-132">Geben Sie in der [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung die Option CONTINUE_AFTER ERROR an, um fortzufahren, oder geben Sie die Option STOP_ON_ERROR an, um den Vorgang anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="c6484-132">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="c6484-133">Das Standardverhalten besteht, den Vorgang anzuhalten, wenn ein Fehler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c6484-133">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="c6484-134">In diesem Beispiel wird der Sicherungsvorgang angewiesen, den Vorgang fortzusetzen, obwohl ein Fehler gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="c6484-134">This example instructs the backup operation to continue despite encountering an error.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
#### <a name="to-specify-whether-a-restore-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="c6484-135">So bestimmen Sie, ob ein Wiederherstellungsvorgang fortgesetzt oder angehalten wird, nachdem ein Fehler festgestellt wurde</span><span class="sxs-lookup"><span data-stu-id="c6484-135">To specify whether a restore operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="c6484-136">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="c6484-136">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6484-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6484-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6484-138">Geben Sie in der [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Anweisung die Option CONTINUE_AFTER ERROR an, um fortzufahren, oder geben Sie die Option STOP_ON_ERROR an, um den Vorgang anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="c6484-138">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="c6484-139">Das Standardverhalten besteht, den Vorgang anzuhalten, wenn ein Fehler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c6484-139">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="c6484-140">In diesem Beispiel wird der Wiederherstellungsvorgang angewiesen, den Vorgang fortzusetzen, obwohl ein Fehler gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="c6484-140">This example instructs the restore operation to continue despite encountering an error.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'   
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6484-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6484-141">See Also</span></span>  
 <span data-ttu-id="c6484-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="c6484-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="c6484-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="c6484-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="c6484-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c6484-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="c6484-148">[RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6484-148">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="c6484-149">[Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6484-149">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="c6484-150">Aktivieren oder deaktivieren von Sicherungsprüfsummen während der Sicherung oder Wiederherstellung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c6484-150">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
  
