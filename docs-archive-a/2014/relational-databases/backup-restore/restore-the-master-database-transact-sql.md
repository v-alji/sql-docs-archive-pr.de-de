---
title: Wiederherstellen der Hauptdatenbank (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], restoring
ms.assetid: c83d802c-e84e-4458-b3ca-173d9ba32f73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c9cb078b7af60fc5e060bcb144fc9cbaee8ecf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620456"
---
# <a name="restore-the-master-database-transact-sql"></a><span data-ttu-id="f90d0-102">Wiederherstellen der master-Datenbank (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f90d0-102">Restore the master Database (Transact-SQL)</span></span>
  <span data-ttu-id="f90d0-103">In diesem Thema erfahren Sie, wie Sie die **master** -Datenbank von einer vollständigen Datenbanksicherung wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f90d0-103">This topic explains how to restore the **master** database from a full database backup.</span></span>  
  
### <a name="to-restore-the-master-database"></a><span data-ttu-id="f90d0-104">So stellen Sie die master-Datenbank wieder her</span><span class="sxs-lookup"><span data-stu-id="f90d0-104">To restore the master database</span></span>  
  
1.  <span data-ttu-id="f90d0-105">Starten Sie die Serverinstanz im Einzelbenutzermodus.</span><span class="sxs-lookup"><span data-stu-id="f90d0-105">Start the server instance in single-user mode.</span></span>  
  
     <span data-ttu-id="f90d0-106">Informationen zum Angeben des Startparameters für Einzelbenutzer ( **-m**) finden Sie unter [Konfigurieren von Serverstartoptionen &#40;SQL Server-Konfigurations-Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="f90d0-106">For information about how to specify the single-user startup parameter (**-m**), see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
2.  <span data-ttu-id="f90d0-107">Verwenden Sie zum Wiederherstellen einer vollständigen Sicherung der **master**-Datenbank die folgende [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung:</span><span class="sxs-lookup"><span data-stu-id="f90d0-107">To restore a full database backup of **master**, use the following [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="f90d0-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span><span class="sxs-lookup"><span data-stu-id="f90d0-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span></span>  
  
     <span data-ttu-id="f90d0-109">Die REPLACE-Option weist [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] an, die angegebene Datenbank wiederherzustellen, selbst wenn eine Datenbank mit dem gleichen Namen bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f90d0-109">The REPLACE option instructs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to restore the specified database even when a database of the same name already exists.</span></span> <span data-ttu-id="f90d0-110">Die vorhandene Datenbank wird ggf. gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f90d0-110">The existing database, if any, is deleted.</span></span> <span data-ttu-id="f90d0-111">Für den Einzelbenutzermodus empfiehlt sich die Eingabe der RESTORE DATABASE-Anweisung im [Hilfsprogramm sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="f90d0-111">In single-user mode, we recommend that you enter the RESTORE DATABASE statement in the [sqlcmd utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="f90d0-112">Weitere Informationen finden Sie unter [Verwenden des Hilfsprogramms sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="f90d0-112">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f90d0-113">Nach der Wiederherstellung von **master** wird die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] heruntergefahren, und der **sqlcmd** -Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="f90d0-113">After **master** is restored, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] shuts down and terminates the **sqlcmd** process.</span></span> <span data-ttu-id="f90d0-114">Vor dem Neustarten der Serverinstanz muss der Einzelbenutzer-Startparameter entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f90d0-114">Before you restart the server instance, remove the single-user startup parameter.</span></span> <span data-ttu-id="f90d0-115">Weitere Informationen finden Sie unter [Konfigurieren von Serverstartoptionen &#40;SQL Server-Konfigurations-Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="f90d0-115">For more information, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
3.  <span data-ttu-id="f90d0-116">Starten Sie die Serverinstanz neu, und setzen Sie andere Wiederherstellungsschritte, z. B. das Wiederherstellen von anderen Datenbanken, das Anfügen von Datenbanken und das Korrigieren von Benutzerkonflikten, fort.</span><span class="sxs-lookup"><span data-stu-id="f90d0-116">Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, and correcting user mismatches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90d0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f90d0-117">Example</span></span>  
 <span data-ttu-id="f90d0-118">Im folgenden Beispiel wird die `master` -Datenbank auf der Standardserverinstanz wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f90d0-118">The following example restores the `master` database on the default server instance.</span></span> <span data-ttu-id="f90d0-119">In diesem Beispiel wird vorausgesetzt, dass die Serverinstanz bereits im Einzelbenutzermodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f90d0-119">The example assumes that the server instance is already running in single-user mode.</span></span> <span data-ttu-id="f90d0-120">Im Beispiel wird `sqlcmd` gestartet, und es wird eine `RESTORE DATABASE` -Anweisung ausgeführt, mit der eine vollständige Datenbanksicherung der `master` -Datenbank vom Datenträgermedium wiederhergestellt wird: `Z:\SQLServerBackups\master.bak`.</span><span class="sxs-lookup"><span data-stu-id="f90d0-120">The example starts `sqlcmd` and executes a `RESTORE DATABASE` statement that restores a full database backup of `master` from a disk device: `Z:\SQLServerBackups\master.bak`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f90d0-121">Bei einer benannten Instanz muss der **sqlcmd**-Befehl die Option **-S** _\<ComputerName>_ \\ *\<InstanceName>* angeben.</span><span class="sxs-lookup"><span data-stu-id="f90d0-121">For a named instance, the **sqlcmd** command must specify the **-S**_\<ComputerName>_\\*\<InstanceName>* option.</span></span>  
  
```  
  
      C:\> sqlcmd  
1> RESTORE DATABASE master FROM DISK = 'Z:\SQLServerBackups\master.bak' WITH REPLACE;  
2> GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f90d0-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f90d0-122">See Also</span></span>  
 <span data-ttu-id="f90d0-123">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-123">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="f90d0-124">[Vollständige Datenbankwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-124">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="f90d0-125">[Problembehandlung bei verwaisten Benutzern &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-125">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 <span data-ttu-id="f90d0-126">[Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-126">[Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="f90d0-127">[Neuerstellen von Systemdatenbanken](../databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-127">[Rebuild System Databases](../databases/system-databases.md) </span></span>  
 <span data-ttu-id="f90d0-128">[Startoptionen für den Datenbank-Engine-Dienst](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-128">[Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span></span>  
 <span data-ttu-id="f90d0-129">[SQL Server-Konfigurations-Manager](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="f90d0-130">[Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f90d0-130">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="f90d0-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f90d0-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="f90d0-132">Starten von SQL Server im Einzelbenutzermodus</span><span class="sxs-lookup"><span data-stu-id="f90d0-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
