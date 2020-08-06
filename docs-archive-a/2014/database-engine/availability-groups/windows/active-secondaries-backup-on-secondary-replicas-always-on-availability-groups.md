---
title: 'Aktive sekundäre Replikate: Sicherung auf sekundären Replikaten (Always on Verfügbarkeits Gruppen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- backup priority
- backup on secondary replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], backup on secondary replicas
- active secondary replicas [SQL Server], backup on
- automated backup preference
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 82afe51b-71d1-4d5b-b20a-b57afc002405
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0cf899cdbeb1ae4ede6c9196b8eb93a9d9e54f05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701942"
---
# <a name="active-secondaries-backup-on-secondary-replicas-always-on-availability-groups"></a><span data-ttu-id="175ac-102">Aktive sekundäre Replikate: Sicherung auf sekundären Replikaten (AlwaysOn-Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="175ac-102">Active Secondaries: Backup on Secondary Replicas (Always On Availability Groups)</span></span>
  <span data-ttu-id="175ac-103">Die Funktionen für aktive sekundäre [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Replikate umfassen auch die Unterstützung von Sicherungsvorgängen auf sekundären Replikaten.</span><span class="sxs-lookup"><span data-stu-id="175ac-103">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] active secondary capabilities include support for performing backup operations on secondary replicas.</span></span> <span data-ttu-id="175ac-104">Sicherungsvorgänge können E/A und CPU (mit Sicherungskomprimierung) erheblich belasten.</span><span class="sxs-lookup"><span data-stu-id="175ac-104">Backup operations can put significant strain on I/O and CPU (with backup compression).</span></span> <span data-ttu-id="175ac-105">Durch die Auslagerung von Sicherungen auf ein sekundäres Replikat mit dem Status SYNCHRONIZED oder SYNCHRONIZING können Sie die Ressourcen auf der Serverinstanz verwenden, die das primäre Replikat für Arbeitsauslastungen erster Ebene hostet.</span><span class="sxs-lookup"><span data-stu-id="175ac-105">Offloading backups to a synchronized or synchronizing secondary replica allows you to use the resources on server instance that hosts the primary replica for your tier-1 workloads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="175ac-106">RESTORE-Anweisungen sind in den primären und sekundären Datenbanken einer Verfügbarkeitsgruppe nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="175ac-106">RESTORE statements are not allowed on either the primary or secondary databases of an availability group.</span></span>  
  
  
  
##  <a name="backup-types-supported-on-secondary-replicas"></a><a name="SupportedBuTypes"></a> <span data-ttu-id="175ac-107">Auf sekundären Replikaten unterstützte Sicherungstypen</span><span class="sxs-lookup"><span data-stu-id="175ac-107">Backup Types Supported on Secondary Replicas</span></span>  
  
-   <span data-ttu-id="175ac-108">`BACKUP DATABASE` unterstützt vollständige Kopiesicherungen von Datenbanken, Dateien oder Dateigruppen nur bei der Ausführung auf sekundären Replikaten.</span><span class="sxs-lookup"><span data-stu-id="175ac-108">`BACKUP DATABASE` supports only copy-only full backups of databases, files, or filegroups when it is executed on secondary replicas.</span></span> <span data-ttu-id="175ac-109">Beachten Sie, dass sich Kopiesicherungen nicht auf die Protokollkette auswirken bzw. kein differenzielles Bitmuster löschen.</span><span class="sxs-lookup"><span data-stu-id="175ac-109">Note that copy-only backups do not impact the log chain or clear the differential bitmap.</span></span>  
  
-   <span data-ttu-id="175ac-110">Differenzielle Sicherungen werden auf sekundären Replikaten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="175ac-110">Differential backups are not supported on secondary replicas.</span></span>  
  
-   <span data-ttu-id="175ac-111">**BACKUP LOG** unterstützt nur reguläre Protokollsicherungen (die COPY_ONLY-Option wird für Protokollsicherungen auf sekundären Replikaten nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="175ac-111">**BACKUP LOG** supports only regular log backups (the COPY_ONLY option is not supported for log backups on secondary replicas).</span></span>  
  
     <span data-ttu-id="175ac-112">Bei sämtlichen Protokollsicherungen von Replikaten (primär oder sekundär) wird ungeachtet ihres Verfügbarkeitsmodus (mit synchronem Commit oder mit asynchronem Commit) eine konsistente Protokollkette sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="175ac-112">A consistent log chain is ensured across log backups taken on any of the replicas (primary or secondary), irrespective of their availability mode (synchronous-commit or asynchronous-commit).</span></span>  
  
-   <span data-ttu-id="175ac-113">Zum Sichern einer sekundären Datenbank muss ein sekundäres Replikat mit dem primären Replikat kommunizieren können und den Status `SYNCHRONIZED` oder `SYNCHRONIZING` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="175ac-113">To back up a secondary database, a secondary replica must be able to communicate with the primary replica and must be `SYNCHRONIZED` or `SYNCHRONIZING`.</span></span>  
  
##  <a name="configuring-where-backup-jobs-run"></a><a name="WhereBuJobsRun"></a><span data-ttu-id="175ac-114">Konfigurieren, wo Sicherungsaufträge ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="175ac-114">Configuring Where Backup Jobs Run</span></span>  
 <span data-ttu-id="175ac-115">Das Ausführen von Sicherungen auf einem sekundären Replikat zum Auslagern der Sicherungsarbeitsauslastung vom primären Produktionsserver ist ein großer Vorteil.</span><span class="sxs-lookup"><span data-stu-id="175ac-115">Performing backups on a secondary replica to offload the backup workload from the primary production server is a great benefit.</span></span> <span data-ttu-id="175ac-116">Durch die Ausführung von Sicherungen auf sekundären Replikaten wird es jedoch wesentlich komplexer, den Ausführungsort von Sicherungsaufträgen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="175ac-116">However, performing backups on secondary replicas introduce significant complexity to the process of determining where backup jobs should run.</span></span> <span data-ttu-id="175ac-117">Um diesen Vorgang zu vereinfachen, konfigurieren Sie den Ausführungsort von Sicherungsaufträgen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="175ac-117">To address this, configure where backup jobs run as follows:</span></span>  
  
1.  <span data-ttu-id="175ac-118">Konfigurieren Sie die Verfügbarkeitsgruppe, um anzugeben, welche Verfügbarkeitsreplikate am Ort, an dem Sie Sicherungen wünschen, ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="175ac-118">Configure the availability group to specify which availability replicas where you would prefer backups to be performed.</span></span> <span data-ttu-id="175ac-119">Weitere Informationen finden Sie unter den Parametern *AUTOMATED_BACKUP_PREFERENCE* und *BACKUP_PRIORITY* in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) oder [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql)aufweisen.</span><span class="sxs-lookup"><span data-stu-id="175ac-119">For more information, see *AUTOMATED_BACKUP_PREFERENCE* and *BACKUP_PRIORITY* parameters in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) or [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
2.  <span data-ttu-id="175ac-120">Erstellen Sie skriptbasierte Sicherungsaufträge für jede Verfügbarkeitsdatenbank auf jeder Serverinstanz, die ein Verfügbarkeitsreplikat hostet, das für das Ausführen von Sicherungen infrage kommt.</span><span class="sxs-lookup"><span data-stu-id="175ac-120">Create scripted backup jobs for every availability database on every server instance that hosts an availability replica that is a candidate for performing backups.</span></span> <span data-ttu-id="175ac-121">Weitere Informationen finden Sie im Abschnitt „Nachverfolgung: Nach dem Konfigurieren einer Sicherung auf sekundären Replikaten“ von [Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md)aufweisen.</span><span class="sxs-lookup"><span data-stu-id="175ac-121">For more information, see the "Follow Up: After Configuring Backup on Secondary Replicas" section of [Configure Backup on Availability Replicas &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="175ac-122">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="175ac-122">Related Tasks</span></span>  
 <span data-ttu-id="175ac-123">**So konfigurieren Sie die Sicherung auf sekundären Replikaten**</span><span class="sxs-lookup"><span data-stu-id="175ac-123">**To configure backup on secondary replicas**</span></span>  
  
-   [<span data-ttu-id="175ac-124">Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="175ac-124">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="175ac-125">**So bestimmen Sie, ob es sich beim aktuellen Replikat um ein bevorzugtes Sicherungsreplikat handelt**</span><span class="sxs-lookup"><span data-stu-id="175ac-125">**To determine whether the current replica is the preferred backup replica**</span></span>  
  
-   [<span data-ttu-id="175ac-126">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="175ac-126">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
  
 <span data-ttu-id="175ac-127">**So erstellen Sie einen Sicherungsauftrag**</span><span class="sxs-lookup"><span data-stu-id="175ac-127">**To create a backup job**</span></span>  
  
-   [<span data-ttu-id="175ac-128">Verwenden des Wartungsplanungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="175ac-128">Use the Maintenance Plan Wizard</span></span>](../../../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
-   [<span data-ttu-id="175ac-129">Implementieren von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="175ac-129">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="175ac-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="175ac-130">See Also</span></span>  
 <span data-ttu-id="175ac-131">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="175ac-131">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="175ac-132">[Kopiesicherungen &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="175ac-132">[Copy-Only Backups &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="175ac-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="175ac-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span></span>  
 [<span data-ttu-id="175ac-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="175ac-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
