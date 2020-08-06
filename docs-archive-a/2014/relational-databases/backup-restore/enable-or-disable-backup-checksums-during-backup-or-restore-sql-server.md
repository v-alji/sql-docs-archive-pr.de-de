---
title: Aktivieren oder Deaktivieren von Sicherungsprüfsummen während der Sicherung oder Wiederherstellung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup checksums [SQL Server]
- disabling checksums
- checksums [SQL Server]
ms.assetid: 6786bd1e-ad97-430a-8dfb-d4ba952d6c4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a239dcdfca689be8555117104264d66a2ac037f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726013"
---
# <a name="enable-or-disable-backup-checksums-during-backup-or-restore-sql-server"></a><span data-ttu-id="d0885-102">Aktivieren oder deaktivieren von Sicherungsprüfsummen während der Sicherung oder Wiederherstellung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d0885-102">Enable or Disable Backup Checksums During Backup or Restore (SQL Server)</span></span>
  <span data-ttu-id="d0885-103">In diesem Thema wird beschrieben, wie Sie Sicherungsprüfsummen aktivieren oder deaktivieren, wenn Sie eine Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]sichern oder wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d0885-103">This topic describes how to enable or disable backup checksums when you are backing up or restoring a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d0885-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d0885-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d0885-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d0885-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d0885-106">Security</span><span class="sxs-lookup"><span data-stu-id="d0885-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d0885-107">**So aktivieren oder deaktivieren Sie Sicherungsprüfsummen mit**</span><span class="sxs-lookup"><span data-stu-id="d0885-107">**To enable or disable backup checksums, using:**</span></span>  
  
     [<span data-ttu-id="d0885-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0885-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d0885-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0885-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0885-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d0885-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d0885-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d0885-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d0885-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d0885-112">Permissions</span></span>  
 <span data-ttu-id="d0885-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="d0885-113">BACKUP</span></span>  
 <span data-ttu-id="d0885-114">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="d0885-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="d0885-115">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="d0885-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d0885-116">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="d0885-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="d0885-117">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="d0885-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="d0885-118">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d0885-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="d0885-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="d0885-119">RESTORE</span></span>  
 <span data-ttu-id="d0885-120">Ist die wiederherzustellende Datenbank nicht vorhanden, muss der Benutzer über CREATE DATABASE-Berechtigungen verfügen, um RESTORE ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d0885-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="d0885-121">Ist die Datenbank vorhanden, werden RESTORE-Berechtigungen standardmäßig den Mitgliedern der festen Serverrollen **sysadmin** und **dbcreator** sowie dem Besitzer (**dbo**) der Datenbank erteilt (für die Option FROM DATABASE_SNAPSHOT ist die Datenbank immer vorhanden).</span><span class="sxs-lookup"><span data-stu-id="d0885-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="d0885-122">RESTORE-Berechtigungen werden Rollen erteilt, in denen Mitgliedsinformationen immer für den Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d0885-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="d0885-123">Da die Mitgliedschaft in einer festen Datenbankrolle nur bei unbeschädigten und zugänglichen Datenbanken geprüft werden kann (was beim Ausführen von RESTORE nicht immer der Fall ist), verfügen Mitglieder der festen Datenbankrolle **db_owner** nicht über RESTORE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="d0885-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d0885-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0885-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-or-disable-checksums-during-a-backup-operation"></a><span data-ttu-id="d0885-125">So aktivieren oder deaktivieren Sie Prüfsummen bei einem Sicherungsvorgang</span><span class="sxs-lookup"><span data-stu-id="d0885-125">To enable or disable checksums during a backup operation</span></span>  
  
1.  <span data-ttu-id="d0885-126">Führen Sie die Schritte aus, [um eine Datenbanksicherung zu erstellen](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d0885-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="d0885-127">Klicken Sie auf der Seite **Optionen** im Bereich **Zuverlässigkeit** auf **Vor dem Schreiben auf die Medien Prüfsumme bilden**.</span><span class="sxs-lookup"><span data-stu-id="d0885-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d0885-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0885-128">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-backup-operation"></a><span data-ttu-id="d0885-129">So aktivieren oder deaktivieren Sie Sicherungsprüfsummen bei einem Sicherungsvorgang</span><span class="sxs-lookup"><span data-stu-id="d0885-129">To enable or disable backup checksum for a backup operation</span></span>  
  
1.  <span data-ttu-id="d0885-130">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="d0885-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d0885-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d0885-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d0885-132">Geben Sie die Option WITH CHECKSUM an, um die Sicherungsprüfsummen in einer [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d0885-132">To enable backup checksums in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="d0885-133">Geben Sie die Option WITH NO_CHECKSUM an, um Sicherungsprüfsummen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d0885-133">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="d0885-134">Dies ist das Standardverhalten, außer bei einer komprimierten Sicherung.</span><span class="sxs-lookup"><span data-stu-id="d0885-134">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="d0885-135">Im folgenden Beispiel wird angegeben, dass Prüfsummen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0885-135">The following example specifies that checksums be performed.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-restore-operation"></a><span data-ttu-id="d0885-136">So aktivieren oder deaktivieren Sie Sicherungsprüfsummen bei einem Wiederherstellungsvorgang</span><span class="sxs-lookup"><span data-stu-id="d0885-136">To enable or disable backup checksum for a restore operation</span></span>  
  
1.  <span data-ttu-id="d0885-137">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="d0885-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d0885-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d0885-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d0885-139">Geben Sie die Option WITH CHECKSUM an, um die Sicherungsprüfsummen in einer [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) -Anweisung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d0885-139">To enable backup checksums in a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="d0885-140">Dies ist das Standardverhalten bei einer komprimierten Sicherung.</span><span class="sxs-lookup"><span data-stu-id="d0885-140">This is the default behavior for a compressed backup.</span></span> <span data-ttu-id="d0885-141">Geben Sie die Option WITH NO_CHECKSUM an, um Sicherungsprüfsummen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d0885-141">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="d0885-142">Dies ist das Standardverhalten, außer bei einer komprimierten Sicherung.</span><span class="sxs-lookup"><span data-stu-id="d0885-142">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="d0885-143">Im folgenden Beispiel wird angegeben, dass Sicherungsprüfsummen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0885-143">The following example specifies that backup checksums be performed.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
> [!WARNING]  
>  <span data-ttu-id="d0885-144">Wenn Sie ausdrücklich CHECKSUM für einen Wiederherstellungsvorgang anfordern und die Sicherung Sicherungsprüfsummen enthält, werden sowohl die Sicherungsprüfsummen als auch die Seitenprüfsummen wie beim Standardfall überprüft.</span><span class="sxs-lookup"><span data-stu-id="d0885-144">If you explicitly request CHECKSUM for a restore operation and if the backup contains backup checksums, backup checksums and page checksums are both verified, as in the default case.</span></span> <span data-ttu-id="d0885-145">Wenn allerdings im Sicherungssatz keine Sicherungsprüfsummen vorhanden sind, wird vom Wiederherstellungsvorgang eine entsprechende Fehlermeldung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d0885-145">However, if the backup set lacks backup checksums, the restore operation fails with a message indicating that checksums are not present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0885-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0885-146">See Also</span></span>  
 <span data-ttu-id="d0885-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="d0885-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="d0885-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="d0885-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="d0885-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="d0885-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="d0885-153">[RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0885-153">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="d0885-154">[Mögliche Medienfehler während der Sicherung und Wiederherstellung &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d0885-154">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="d0885-155">Angeben, ob ein Sicherungs- oder Wiederherstellungsvorgang fortgesetzt wird, nachdem ein Fehler festgestellt wurde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0885-155">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
  
