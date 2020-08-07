---
title: Ausführen eines geplanten manuellen Failovers einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.manualfailover.f1
helpviewer_keywords:
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: 419f655d-3f9a-4e7d-90b9-f0bab47b3178
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c62942eaa8f4ab4472bca5c7123e5999eb069216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718745"
---
# <a name="perform-a-planned-manual-failover-of-an-availability-group-sql-server"></a><span data-ttu-id="99ddf-102">Ausführen eines geplanten manuellen Failovers einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="99ddf-102">Perform a Planned Manual Failover of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="99ddf-103">In diesem Thema wird beschrieben, wie ein manuelles Failover ohne Datenverlust (ein *geplantes manuelles Failover*) in einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)] oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99ddf-103">This topic describes how to perform a manual failover without data loss (a *planned manual failover*) on an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="99ddf-104">Eine Verfügbarkeitsgruppe führt auf der Ebene eines Verfügbarkeitsreplikats ein Failover aus.</span><span class="sxs-lookup"><span data-stu-id="99ddf-104">An availability group fails over at the level of an availability replica.</span></span> <span data-ttu-id="99ddf-105">Bei einem geplanten manuellen Failover geht wie bei jedem [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Failover ein sekundäres Replikat zur primären Rolle und gleichzeitig das frühere primäre Replikat zur sekundären Rolle über.</span><span class="sxs-lookup"><span data-stu-id="99ddf-105">A planned manual failover, like any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] failover, transitions a secondary replica to primary role and, concurrently, transitions the former primary replica to the secondary role.</span></span>  
  
 <span data-ttu-id="99ddf-106">Ein geplantes manuelles Failover, das nur unterstützt wird, wenn das primäre Replikat und das sekundäre Zielreplikat im Modus für synchrone Commits ausgeführt und gerade synchronisiert werden, behält alle Daten in den sekundären Datenbanken bei, die mit der Verfügbarkeitsgruppe im sekundären Zielreplikat verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="99ddf-106">A planned manual failover, which is supported only when the primary replica and the target secondary replica are running in synchronous-commit mode and are currently synchronized, preserves all the data in the secondary databases that are joined to the availability group on the target secondary replica.</span></span> <span data-ttu-id="99ddf-107">Sobald das frühere primäre Replikat zur sekundären Rolle übergeht, werden seine Datenbanken sekundäre Datenbanken und starten die Synchronisierung mit den neuen primären Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="99ddf-107">Once the former primary replica transitions to the secondary role, its databases become secondary databases and begin synchronizing with the new primary databases.</span></span> <span data-ttu-id="99ddf-108">Nach dem Übergang in den Status SYNCHRONIZED kann das neue sekundäre Replikat als Ziel eines künftigen geplanten manuellen Failovers dienen.</span><span class="sxs-lookup"><span data-stu-id="99ddf-108">After they all transition into the SYNCHRONIZED state, the new secondary replica becomes eligible to serve as the target of a future planned manual failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99ddf-109">Wenn das sekundäre und primäre Replikat für den automatischen Failovermodus konfiguriert sind, kann das sekundäre Replikat nach der Synchronisierung auch als Ziel für ein automatisches Failover dienen.</span><span class="sxs-lookup"><span data-stu-id="99ddf-109">If the secondary and primary replicas are both configured for automatic failover mode, once the secondary replica is synchronized, it can also serve as the target for an automatic failover.</span></span> <span data-ttu-id="99ddf-110">Weitere Informationen finden Sie unter [Verfügbarkeitsmodi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="99ddf-110">For more information, see [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99ddf-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="99ddf-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="99ddf-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99ddf-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="99ddf-113">Ein Failoverbefehl gibt einen Wert zurück, sobald das sekundäre Zielreplikat den Befehl akzeptiert hat.</span><span class="sxs-lookup"><span data-stu-id="99ddf-113">A failover command returns as soon as the target secondary replica has accepted the command.</span></span> <span data-ttu-id="99ddf-114">Die Datenbankwiederherstellung tritt jedoch asynchron auf, nachdem die Verfügbarkeitsgruppe aufgehört hat, ein Failover auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99ddf-114">However, database recovery occurs asynchronously after the availability group has finished failing over.</span></span>  
  
-   <span data-ttu-id="99ddf-115">Datenbankübergreifende Konsistenz zwischen Datenbanken innerhalb der Verfügbarkeitsgruppe wird beim Failover nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="99ddf-115">Cross-database consistency across databases within the availability group is not maintained on failover.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99ddf-116">Datenbankübergreifende Transaktionen und verteilte Transaktionen werden von [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99ddf-116">Cross-database transactions and distributed transactions are not supported by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="99ddf-117">Weitere Informationen finden Sie unter [Datenbankübergreifende Transaktionen nicht unterstützt für Datenbankspiegelungs- oder AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="99ddf-117">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="99ddf-118">Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99ddf-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="99ddf-119">Das sekundäre Zielreplikat und das primäre Replikat müssen im Verfügbarkeitsmodus für synchrone Commits ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="99ddf-119">The target secondary replica and the primary replica must both be running in synchronous-commit availability mode.</span></span>  
  
-   <span data-ttu-id="99ddf-120">Das sekundäre Zielreplikat muss gerade mit dem primären Replikat synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="99ddf-120">The target secondary replica must currently be synchronized with the primary replica.</span></span> <span data-ttu-id="99ddf-121">Dies erfordert, dass alle sekundären Datenbanken auf diesem sekundären Replikat mit der Verfügbarkeitsgruppe verknüpft und mit ihren entsprechenden primären Datenbanken synchronisiert sein müssen (das heißt, die lokalen sekundären Datenbanken müssen den Status SYNCHRONIZED aufweisen).</span><span class="sxs-lookup"><span data-stu-id="99ddf-121">This requires that all the secondary databases on this secondary replica must have been joined to the availability group and be synchronized with their corresponding primary databases (that is, the local secondary databases must be SYNCHRONIZED).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="99ddf-122">Um die Failoverbereitschaft eines sekundären Replikats zu ermitteln, fragen Sie die **is_failover_ready** -Spalte in der dynamischen Verwaltungssicht [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) ab, oder überprüfen Sie die Spalte **Failoverbereitschaft** des [AlwaysOn-Gruppendashboards](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="99ddf-122">To determine the failover readiness of an secondary replica, query the **is_failover_ready** column in the [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) dynamic management view, or look at the **Failover Readiness** column of the [AlwaysOn Group Dashboard](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="99ddf-123">Dieser Task wird nur für das sekundäre Zielreplikat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99ddf-123">This task is supported only on the target secondary replica.</span></span> <span data-ttu-id="99ddf-124">Sie müssen mit der Serverinstanz verbunden sein, auf der das sekundäre Zielreplikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="99ddf-124">You must be connected to the server instance that hosts the target secondary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99ddf-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="99ddf-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99ddf-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99ddf-126">Permissions</span></span>  
 <span data-ttu-id="99ddf-127">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="99ddf-127">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="99ddf-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99ddf-128">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="99ddf-129">**So führen Sie manuell ein Failover für eine Verfügbarkeitsgruppe aus**</span><span class="sxs-lookup"><span data-stu-id="99ddf-129">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="99ddf-130">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Serverinstanz her, die ein sekundäres Replikat der Verfügbarkeitsgruppe hostet, für die ein Failover ausgeführt werden muss, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="99ddf-130">In Object Explorer, connect to a server instance that hosts a secondary replica of the availability group that needs to be failed over, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="99ddf-131">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="99ddf-131">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="99ddf-132">Klicken Sie mit der rechten Maustaste auf die Verfügbarkeitsgruppe, für die ein Failover ausgeführt werden soll, und wählen Sie den Befehl **Failover** aus.</span><span class="sxs-lookup"><span data-stu-id="99ddf-132">Right-click the availability group to be failed over, and select the **Failover** command.</span></span>  
  
4.  <span data-ttu-id="99ddf-133">Dadurch wird der Assistent für das Failover von Verfügbarkeitsgruppen gestartet.</span><span class="sxs-lookup"><span data-stu-id="99ddf-133">This launches the Failover Availability Group Wizard.</span></span> <span data-ttu-id="99ddf-134">Weitere Informationen finden Sie unter [Verwenden des Assistenten für Failover-Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99ddf-134">For more information, see [Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="99ddf-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99ddf-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="99ddf-136">**So führen Sie manuell ein Failover für eine Verfügbarkeitsgruppe aus**</span><span class="sxs-lookup"><span data-stu-id="99ddf-136">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="99ddf-137">Stellen Sie eine Verbindung mit der Serverinstanz her, die das sekundäre Zielreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="99ddf-137">Connect to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="99ddf-138">Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="99ddf-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="99ddf-139">ALTER AVAILABILITY GROUP *Gruppenname* FAILOVER</span><span class="sxs-lookup"><span data-stu-id="99ddf-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span></span>  
  
     <span data-ttu-id="99ddf-140">Dabei ist *Gruppenname* der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="99ddf-140">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="99ddf-141">Im folgenden Beispiel wird manuell ein Failover der *MyAg* -Verfügbarkeitsgruppe zum verbundenen sekundären Replikat ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="99ddf-141">The following example manually fails over the *MyAg* availability group to the connected secondary replica.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAg FAILOVER;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="99ddf-142">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="99ddf-142">Using PowerShell</span></span>  
 <span data-ttu-id="99ddf-143">**So führen Sie manuell ein Failover für eine Verfügbarkeitsgruppe aus**</span><span class="sxs-lookup"><span data-stu-id="99ddf-143">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="99ddf-144">Ändern Sie das Verzeichnis (`cd`) in die Serverinstanz, die das sekundäre Zielreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="99ddf-144">Change directory (`cd`) to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="99ddf-145">Verwenden Sie das `Switch-SqlAvailabilityGroup`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99ddf-145">Use the `Switch-SqlAvailabilityGroup` cmdlet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="99ddf-146">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="99ddf-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="99ddf-147">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="99ddf-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
     <span data-ttu-id="99ddf-148">Im folgenden Beispiel wird manuell ein Failover der *myag* -Verfügbarkeits Gruppe zum sekundären Replikat mit dem angegebenen Pfad ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="99ddf-148">The following example manually fails over the *MyAg* availability group to the secondary replica with the specified path.</span></span>  
  
    ```powershell
    Switch-SqlAvailabilityGroup -Path SQLSERVER:\Sql\SecondaryServer\InstanceName\AvailabilityGroups\MyAg  
    ```  
  
 <span data-ttu-id="99ddf-149">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="99ddf-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="99ddf-150">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="99ddf-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="99ddf-151">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="99ddf-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="follow-up-after-manually-failing-over-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="99ddf-152">Nachverfolgung: nach dem manuellen Ausführen eines Failovers für eine Verfügbarkeits Gruppe</span><span class="sxs-lookup"><span data-stu-id="99ddf-152">Follow Up: After Manually Failing Over an Availability Group</span></span>  
 <span data-ttu-id="99ddf-153">Wenn Sie ein Failover außerhalb des [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] der Verfügbarkeitsgruppe ausgeführt haben, passen Sie die Quorumabstimmungen der WSFC-Knoten an die Konfiguration der neuen Verfügbarkeitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="99ddf-153">If you failed over outside of the [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] of the availability group, adjust the quorum votes of the WSFC nodes to reflect your new availability group configuration.</span></span> <span data-ttu-id="99ddf-154">Weitere Informationen finden Sie unter [Windows Server-Failoverclustering &#40;wsfc-&#41; mit SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="99ddf-154">For more information, see [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ddf-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99ddf-155">See Also</span></span>  
 <span data-ttu-id="99ddf-156">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="99ddf-156">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="99ddf-157">[Failover-und Failovermodi &#40;AlwaysOn-Verfügbarkeitsgruppen&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="99ddf-157">[Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="99ddf-158">Ausführen eines erzwungenen manuellen Failovers einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99ddf-158">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
