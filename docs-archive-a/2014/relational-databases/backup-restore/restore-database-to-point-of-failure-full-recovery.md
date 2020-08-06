---
title: Wiederherstellen einer Datenbank bis zum Fehler Zeitpunkt im vollständigen Wiederherstellungs Modell (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- point of failure [SQL Server]
- restoring databases [SQL Server], point of failure
- database restores [SQL Server], point of failure
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95b73660ebb44f4daffe6eaefd873699cfbbd8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617124"
---
# <a name="restore-a-database-to-the-point-of-failure-under-the-full-recovery-model-transact-sql"></a><span data-ttu-id="8283a-102">Wiederherstellen einer Datenbank bis zum Fehlerzeitpunkt im vollständigen Wiederherstellungsmodell (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8283a-102">Restore a Database to the Point of Failure Under the Full Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="8283a-103">In diesem Thema wird erläutert, wie Sie den Status vor dem Fehler wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="8283a-103">This topic explains how to restore to the point of failure.</span></span> <span data-ttu-id="8283a-104">Dieses Thema ist nur für Datenbanken relevant, von denen das vollständige oder massenprotokollierte Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8283a-104">The topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
### <a name="to-restore-to-the-point-of-failure"></a><span data-ttu-id="8283a-105">So stellen Sie den Status vor dem Fehler wieder her</span><span class="sxs-lookup"><span data-stu-id="8283a-105">To restore to the point of failure</span></span>  
  
1.  <span data-ttu-id="8283a-106">Sichern Sie das Protokollfragment, indem Sie die folgende einfache [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="8283a-106">Back up the tail of the log by running the following basic [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  <span data-ttu-id="8283a-107">Stellen Sie eine vollständige Datenbanksicherung wieder her, indem Sie folgende einfache [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) -Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="8283a-107">Restore a full database backup by running the following basic [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  <span data-ttu-id="8283a-108">Stellen Sie optional eine differenzielle Datenbanksicherung wieder her, indem Sie folgende einfache RESTORE DATABASE-Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="8283a-108">Optionally, restore a differential database backup by running the following basic RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  <span data-ttu-id="8283a-109">Wenden Sie jedes Transaktionsprotokoll an, einschließlich der von Ihnen in Schritt 1 erstellten Sicherung des Protokollfragments. Geben Sie dazu WITH NORECOVERY in der RESTORE LOG-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="8283a-109">Apply each transaction log, including the tail-log backup you created in step 1, by specifying WITH NORECOVERY in the RESTORE LOG statement:</span></span>  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  <span data-ttu-id="8283a-110">Stellen Sie die Datenbank wieder her, indem Sie folgende RESTORE DATABASE-Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="8283a-110">Recover the database by running the following RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## <a name="example"></a><span data-ttu-id="8283a-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8283a-111">Example</span></span>  
 <span data-ttu-id="8283a-112">Bevor Sie das Beispiel ausführen können, sind folgende Vorbereitungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="8283a-112">Before you can run the example, you must complete the following preparations:</span></span>  
  
1.  <span data-ttu-id="8283a-113">Das Standardwiederherstellungsmodell der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank ist das einfache Wiederherstellungsmodell.</span><span class="sxs-lookup"><span data-stu-id="8283a-113">The default recovery model of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is the simple recovery model.</span></span> <span data-ttu-id="8283a-114">Da dieses Wiederherstellungsmodell nicht die Wiederherstellung bis zum Zeitpunkt des Fehlers unterstützt, müssen Sie für [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] die Verwendung des vollständigen Wiederherstellungsmodells festlegen, indem Sie folgende [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="8283a-114">Because this recovery model does not support restoring to the point of a failure, set [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] to use the full recovery model by running the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  <span data-ttu-id="8283a-115">Erstellen Sie eine vollständige Datenbanksicherung der Datenbank, indem Sie folgende BACKUP-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="8283a-115">Create a full database back of the database by using the following BACKUP statement:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  <span data-ttu-id="8283a-116">Erstellen Sie eine routinemäßige Protokollsicherung:</span><span class="sxs-lookup"><span data-stu-id="8283a-116">Create a routine log backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 <span data-ttu-id="8283a-117">Im folgenden Beispiel werden die zuvor erstellten Sicherungen wiederhergestellt, nachdem eine Protokollfragmentsicherung der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8283a-117">The following example restores the backups that are created previously, after creating a tail-log backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="8283a-118">(Für diesen Schritt wird vorausgesetzt, dass der Zugriff auf den Protokolldatenträger möglich ist.)</span><span class="sxs-lookup"><span data-stu-id="8283a-118">(This step assumes that the log disk can be accessed.)</span></span>  
  
 <span data-ttu-id="8283a-119">Zunächst wird im Beispiel eine Protokollfragmentsicherung der Datenbank erstellt, wobei das aktive Protokoll erfasst und die Datenbank im Wiederherstellungszustand belassen wird.</span><span class="sxs-lookup"><span data-stu-id="8283a-119">First, the example creates a tail-log backup of the database that captures the active log and leaves the database in the Restoring state.</span></span> <span data-ttu-id="8283a-120">Dann wird im Beispiel die Datenbanksicherung wiederhergestellt, die zuvor erstellte routinemäßige Protokollsicherung angewendet und die Protokollfragmentsicherung angewendet.</span><span class="sxs-lookup"><span data-stu-id="8283a-120">Then, the example restores the database backup, applies the routine log backup created previously, and applies the tail-log backup.</span></span> <span data-ttu-id="8283a-121">Abschließend wird die Datenbank in einem separaten Schritt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="8283a-121">Finally, the example recovers the database in a separate step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8283a-122">Das Standardverhalten besteht in der Wiederherstellung einer Datenbank als Bestandteil der Anweisung, mit der die endgültige Sicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8283a-122">The default behavior is to recover a database as part of the statement that restores the final backup.</span></span>  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8283a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8283a-123">See Also</span></span>  
 <span data-ttu-id="8283a-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8283a-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="8283a-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8283a-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
