---
title: Schrittweise Wiederherstellung von Datenbanken mit speicheroptimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 732c9721-8dd4-481d-8ff9-1feaaa63f84f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed23f08d40e23b1d43c1b642f4089fe77646b675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722813"
---
# <a name="piecemeal-restore-of-databases-with-memory-optimized-tables"></a><span data-ttu-id="4220d-102">Schrittweise Wiederherstellung von Datenbanken mit speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="4220d-102">Piecemeal Restore of Databases With Memory-Optimized Tables</span></span>
  <span data-ttu-id="4220d-103">Die schrittweise Wiederherstellung wird für Datenbanken mit speicheroptimierten Tabellen unterstützt, allerdings mit der im Folgenden beschriebenen Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="4220d-103">Piecemeal restore is supported on databases with memory-optimized tables except for one restriction described below.</span></span> <span data-ttu-id="4220d-104">Weitere Informationen zur schrittweisen Sicherung und Wiederherstellung finden Sie unter [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) und [Schrittweise Wiederherstellungen &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4220d-104">For more information about piecemeal backup and restore, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [Piecemeal Restores &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span></span>  
  
 <span data-ttu-id="4220d-105">Eine speicheroptimierte Dateigruppe muss zusammen mit der primären Dateigruppe gesichert und wiederhergestellt werden:</span><span class="sxs-lookup"><span data-stu-id="4220d-105">A memory-optimized filegroup must be backed up and restored together with the primary filegroup:</span></span>  
  
-   <span data-ttu-id="4220d-106">Wenn Sie die primäre Dateigruppe sichern (oder wiederherstellen), müssen Sie die speicheroptimierte Dateigruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="4220d-106">If you back up (or restore) the primary filegroup you must specify the memory-optimized filegroup.</span></span>  
  
-   <span data-ttu-id="4220d-107">Wenn Sie die speicheroptimierte Dateigruppe sichern (oder wiederherstellen), müssen Sie die primäre Dateigruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="4220d-107">If you backup (or restore) the memory-optimized filegroup you must specify the primary filegroup.</span></span>  
  
 <span data-ttu-id="4220d-108">Wichtige Szenarien für die schrittweise Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="4220d-108">Key scenarios for piecemeal backup and restore are,</span></span>  
  
-   <span data-ttu-id="4220d-109">Mithilfe der schrittweisen Sicherung lässt sich die Größe der Sicherung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="4220d-109">Piecemeal backup allows you to reduce the size of backup.</span></span> <span data-ttu-id="4220d-110">Einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="4220d-110">Some examples:</span></span>  
  
    -   <span data-ttu-id="4220d-111">Konfigurieren Sie die Datenbanksicherung für unterschiedliche Uhrzeiten oder Tage, um die Auswirkungen auf die Arbeitsauslastung zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="4220d-111">Configure the database backup to occur at different times or days to minimize the impact on the workload.</span></span> <span data-ttu-id="4220d-112">Ein Beispiel hierfür ist eine sehr umfangreiche Datenbank (größer als 1 TB), bei der eine vollständige Datenbanksicherung nicht innerhalb des für die Datenbankwartung vorgesehenen Zeitraums abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4220d-112">One example is a very large database (greater than 1 TB) where a full database backup cannot complete in the time allocated for database maintenance.</span></span> <span data-ttu-id="4220d-113">In diesem Fall können Sie die schrittweise Sicherung verwenden, um die vollständige Datenbank in mehreren schrittweisen Sicherungen zu sichern.</span><span class="sxs-lookup"><span data-stu-id="4220d-113">In that situation, you can use piecemeal backup to backup the full database in multiple piecemeal backups.</span></span>  
  
    -   <span data-ttu-id="4220d-114">Wenn eine Dateigruppe als schreibgeschützt gekennzeichnet ist, erfordert sie keine Transaktionsprotokollsicherung, nachdem sie als schreibgeschützt gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="4220d-114">If a filegroup is marked read-only, it does not require a transaction log backup after it was marked read-only.</span></span> <span data-ttu-id="4220d-115">Nachdem Sie die Dateigruppe als schreibgeschützt gekennzeichnet haben, können Sie sie optional nur einmal sichern.</span><span class="sxs-lookup"><span data-stu-id="4220d-115">You can choose to back up the filegroup only once after marking it read-only.</span></span>  
  
-   <span data-ttu-id="4220d-116">Schrittweise Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="4220d-116">Piecemeal restore.</span></span>  
  
    -   <span data-ttu-id="4220d-117">Das Ziel einer schrittweisen Wiederherstellung besteht darin, die wichtigen Datenbankinhalte online zu schalten, ohne darauf zu warten, dass alle Daten wiederhergestellt sind.</span><span class="sxs-lookup"><span data-stu-id="4220d-117">The goal of a piecemeal restore is to bring the critical parts of database online without waiting for all the data.</span></span> <span data-ttu-id="4220d-118">Ein Beispiel ist eine Datenbank mit partitionierten Daten, bei der ältere Partitionen nur selten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4220d-118">One example is if a database has partitioned data, such that older partitions are only used rarely.</span></span> <span data-ttu-id="4220d-119">Diese Partitionen können dann jeweils nur bei Bedarf wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4220d-119">You can restore them only on an as-needed basis.</span></span> <span data-ttu-id="4220d-120">Ähnliches gilt für Dateigruppen, die beispielsweise Vergangenheitsdaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="4220d-120">Similar for filegroups that contain, for example, historical data.</span></span>  
  
    -   <span data-ttu-id="4220d-121">Mithilfe der Seitenreparatur können Sie eine Seitenbeschädigung beheben, indem Sie die jeweilige Seite wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="4220d-121">Using page repair, you can fix page corruption by specifically restoring the page.</span></span> <span data-ttu-id="4220d-122">Weitere Informationen finden Sie unter [Wiederherstellung von Seiten &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4220d-122">For more information, see [Restore Pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span></span>  
  
## <a name="samples"></a><span data-ttu-id="4220d-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4220d-123">Samples</span></span>  
 <span data-ttu-id="4220d-124">In den Beispielen wird das folgende Schema verwendet:</span><span class="sxs-lookup"><span data-stu-id="4220d-124">The examples use the following schema:</span></span>  
  
```  
CREATE DATABASE imoltp  
ON PRIMARY (name = imoltp_primary1, filename = 'c:\data\imoltp_data1.mdf')  
LOG ON (name = imoltp_log, filename = 'c:\data\imoltp_log.ldf')  
GO  
  
ALTER DATABASE imoltp ADD FILE (name = imoltp_primary2, filename = 'c:\data\imoltp_data2.ndf')  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_secondary  
ALTER DATABASE imoltp ADD FILE (name = imoltp_secondary, filename = 'c:\data\imoltp_secondary.ndf') TO FILEGROUP imoltp_secondary  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod CONTAINS MEMORY_OPTIMIZED_DATA   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod1', filename='c:\data\imoltp_mod1') TO FILEGROUP imoltp_mod   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod2', filename='c:\data\imoltp_mod2') TO FILEGROUP imoltp_mod   
GO  
```  
  
### <a name="backup"></a><span data-ttu-id="4220d-125">Backup</span><span class="sxs-lookup"><span data-stu-id="4220d-125">Backup</span></span>  
 <span data-ttu-id="4220d-126">Dieses Beispiel veranschaulicht, wie die primäre Dateigruppe und die speicheroptimierte Dateigruppe gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="4220d-126">This sample shows how to backup the primary filegroup and the memory-optimized filegroup.</span></span> <span data-ttu-id="4220d-127">Sie müssen die primäre und speicheroptimierte Dateigruppe zusammen angeben.</span><span class="sxs-lookup"><span data-stu-id="4220d-127">You must specify both primary and memory-optimized filegroup together.</span></span>  
  
```  
backup database imoltp filegroup='primary', filegroup='imoltp_mod' to disk='c:\data\imoltp.dmp' with init  
```  
  
 <span data-ttu-id="4220d-128">Das folgende Beispiel veranschaulicht, dass eine Dateigruppensicherung, die keine primäre und speicheroptimierte Dateigruppe umfasst, ähnlich wie bei Datenbanken ohne speicheroptimierte Tabellen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4220d-128">The following sample shows that a back up of filegroup(s) other than primary and memory-optimized filegroup works similar to the databases without memory-optimized tables.</span></span> <span data-ttu-id="4220d-129">Mit dem folgenden Befehl wird die sekundäre Dateigruppe gesichert.</span><span class="sxs-lookup"><span data-stu-id="4220d-129">The following command backups up the secondary filegroup</span></span>  
  
```  
backup database imoltp filegroup='imoltp_secondary' to disk='c:\data\imoltp_secondary.dmp' with init  
```  
  
### <a name="restore"></a><span data-ttu-id="4220d-130">Restore</span><span class="sxs-lookup"><span data-stu-id="4220d-130">Restore</span></span>  
 <span data-ttu-id="4220d-131">Im folgenden Beispiel wird gezeigt, wie die primäre Dateigruppe und speicheroptimierte Dateigruppe zusammen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4220d-131">The following sample shows how to restore the primary filegroup and memory-optimized filegroup together.</span></span>  
  
```  
restore database imoltp filegroup = 'primary', filegroup = 'imoltp_mod'   
from disk='c:\data\imoltp.dmp' with partial, norecovery  
  
--restore the transaction log  
 RESTORE LOG [imoltp] FROM DISK = N'c:\data\imoltp_log.dmp' WITH  FILE = 1,  NOUNLOAD,  STATS = 10  
GO  
```  
  
 <span data-ttu-id="4220d-132">Das nächste Beispiel veranschaulicht, dass eine Dateigruppenwiederherstellung, die keine primäre und speicheroptimierte Dateigruppe umfasst, ähnlich wie bei Datenbanken ohne speicheroptimierte Tabellen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4220d-132">The next sample shows that restoring filegroup(s) other than the primary and memory-optimized filegroup works similar to the databases without memory-optimized tables</span></span>  
  
```  
RESTORE DATABASE [imoltp] FILE = N'imoltp_secondary'   
FROM  DISK = N'c:\data\imoltp_secondary.dmp' WITH  FILE = 1,  RECOVERY,  NOUNLOAD,  STATS = 10  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4220d-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4220d-133">See Also</span></span>  
 [<span data-ttu-id="4220d-134">Sichern und Wiederherstellen speicheroptimierter Tabellen</span><span class="sxs-lookup"><span data-stu-id="4220d-134">Backup, Restore, and Recovery of Memory-Optimized Tables</span></span>](../../database-engine/backup-restore-and-recovery-of-memory-optimized-tables.md)  
  
  
