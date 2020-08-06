---
title: Anzeigen von Verfügbarkeitsreplikateigenschaften (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- ', policies'
ms.assetid: 14fed3c4-8ecc-4e1c-931d-a7ec1e9f9e90
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ca7b0508907b4d86c9ee627438a3f18e1b01fdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701912"
---
# <a name="view-availability-replica-properties-sql-server"></a><span data-ttu-id="8f957-102">Anzeigen von Verfügbarkeitsreplikateigenschaften (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8f957-102">View Availability Replica Properties (SQL Server)</span></span>
  <span data-ttu-id="8f957-103">In diesem Thema wird beschrieben, wie die Eigenschaften eines Verfügbarkeitsreplikats für eine AlwaysOn-Verfügbarkeitsgruppe unter Verwendung von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8f957-103">This topic describes how to view the properties of an availability replica for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8f957-104">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f957-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8f957-105">**So zeigen Sie die Eigenschaften eines Verfügbarkeitsreplikats an und ändern sie**</span><span class="sxs-lookup"><span data-stu-id="8f957-105">**To view and change properties an availability replica**</span></span>  
  
1.  <span data-ttu-id="8f957-106">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="8f957-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8f957-107">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="8f957-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="8f957-108">Erweitern Sie die Verfügbarkeitsgruppe, zu der das Verfügbarkeitsreplikat gehört, und erweitern Sie den Knoten **Verfügbarkeitsreplikate** .</span><span class="sxs-lookup"><span data-stu-id="8f957-108">Expand the availability group to which the availability replica belongs, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="8f957-109">Klicken Sie mit der rechten Maustaste auf das Verfügbarkeitsreplikat, dessen Eigenschaften Sie anzeigen möchten, und wählen Sie den Befehl **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="8f957-109">Right-click the availability replica whose properties you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="8f957-110">Verwenden Sie im Dialogfeld **Eigenschaften des Verfügbarkeitsreplikats** die Seite **Allgemein** , um die Eigenschaften dieses Replikats anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8f957-110">In the **Availability Replica Properties** dialog box, use the **General** page to view the properties of this replica.</span></span> <span data-ttu-id="8f957-111">Wenn eine Verbindung mit dem primären Replikat hergestellt wurde, können Sie die folgenden Eigenschaften ändern: Verfügbarkeitsmodus, Failovermodus, Verbindungszugriff für die primäre Rolle, Lesezugriff für die sekundäre Rolle (lesbares sekundäres Replikat) und Wert des Sitzungstimeouts.</span><span class="sxs-lookup"><span data-stu-id="8f957-111">If you are connected to the primary replica, you can change the following properties: availability mode, failover mode, connection access for the primary role, read-access for the secondary role (readable-secondary), and the session-timeout value.</span></span> <span data-ttu-id="8f957-112">Weitere Informationen finden Sie unter [Eigenschaften des Verfügbarkeits Replikats &#40;Seite "Allgemein"&#41;](availability-replica-properties-general-page.md).</span><span class="sxs-lookup"><span data-stu-id="8f957-112">For more information, see  [Availability Replica Properties &#40;General Page&#41;](availability-replica-properties-general-page.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8f957-113">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f957-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="8f957-114">**So zeigen Sie die Eigenschaften und den Status von Verfügbarkeitsreplikaten an**</span><span class="sxs-lookup"><span data-stu-id="8f957-114">**To view properties and states of availability replicas**</span></span>  
  
 <span data-ttu-id="8f957-115">Um die Eigenschaften und den Status von Verfügbarkeitsreplikaten anzuzeigen, verwenden Sie die folgenden Sichten und die folgende Systemfunktion:</span><span class="sxs-lookup"><span data-stu-id="8f957-115">To view the properties and states of availability replicas, use the following views and system function:</span></span>  
  
 [<span data-ttu-id="8f957-116">sys.availability_replicas</span><span class="sxs-lookup"><span data-stu-id="8f957-116">sys.availability_replicas</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql)  
 <span data-ttu-id="8f957-117">Gibt eine Zeile für jedes Verfügbarkeitsreplikat in jeder Verfügbarkeitsgruppe zurück, für die die lokale Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ein Verfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="8f957-117">Returns a row for every availability replica in each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span>  
  
 <span data-ttu-id="8f957-118">**Spaltennamen:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span><span class="sxs-lookup"><span data-stu-id="8f957-118">**Column names:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span></span>  
  
 [<span data-ttu-id="8f957-119">sys.availability_read_only_routing_lists</span><span class="sxs-lookup"><span data-stu-id="8f957-119">sys.availability_read_only_routing_lists</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
 <span data-ttu-id="8f957-120">Gibt eine Zeile für die schreibgeschützte Routingliste aller Verfügbarkeitsreplikate zurück, die zu einer AlwaysOn-Verfügbarkeitsgruppe im WSFC-Failovercluster gehören.</span><span class="sxs-lookup"><span data-stu-id="8f957-120">Returns a row for the read only routing list of each availability replica in an AlwaysOn availability group in the WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="8f957-121">**Spaltennamen:** replica_id, routing_priority, read_only_replica_id</span><span class="sxs-lookup"><span data-stu-id="8f957-121">**Column names:** replica_id, routing_priority, read_only_replica_id</span></span>  
  
 [<span data-ttu-id="8f957-122">sys.dm_hadr_availability_replica_cluster_nodes</span><span class="sxs-lookup"><span data-stu-id="8f957-122">sys.dm_hadr_availability_replica_cluster_nodes</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-nodes-transact-sql)  
 <span data-ttu-id="8f957-123">Gibt eine Zeile für jedes Verfügbarkeitsreplikat (unabhängig vom Joinzustand) der AlwaysOn-Verfügbarkeitsgruppen im WSFC-Cluster (Windows Server Failover Clustering) zurück.</span><span class="sxs-lookup"><span data-stu-id="8f957-123">Returns a row for every availability replica (regardless of join state) of the AlwaysOn availability groups in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="8f957-124">**Spaltennamen:** group_name, replica_server_name, node_name</span><span class="sxs-lookup"><span data-stu-id="8f957-124">**Column names:** group_name, replica_server_name, node_name</span></span>  
  
 [<span data-ttu-id="8f957-125">sys.dm_hadr_availability_replica_cluster_states</span><span class="sxs-lookup"><span data-stu-id="8f957-125">sys.dm_hadr_availability_replica_cluster_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-states-transact-sql)  
 <span data-ttu-id="8f957-126">Gibt eine Zeile für jedes Replikat (unabhängig vom Joinzustand) aller AlwaysOn-Verfügbarkeitsgruppen (unabhängig von Replikatspeicherort) im WSFC-Cluster (Windows Server-Failoverclustering) zurück.</span><span class="sxs-lookup"><span data-stu-id="8f957-126">Returns a row for each replica (regardless of join state) of all AlwaysOn availability groups (regardless of replica location) in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="8f957-127">**Spaltennamen:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span><span class="sxs-lookup"><span data-stu-id="8f957-127">**Column names:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span></span>  
  
 [<span data-ttu-id="8f957-128">sys.dm_hadr_availability_replica_states</span><span class="sxs-lookup"><span data-stu-id="8f957-128">sys.dm_hadr_availability_replica_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql)  
 <span data-ttu-id="8f957-129">Gibt eine Zeile mit dem Status jedes lokalen Verfügbarkeitsreplikats und eine Zeile für jedes Remoteverfügbarkeitsreplikat in derselben Verfügbarkeitsgruppe zurück.</span><span class="sxs-lookup"><span data-stu-id="8f957-129">Returns a row showing the state of each local availability replica and a row for each remote availability replica in the same availability group.</span></span>  
  
 <span data-ttu-id="8f957-130">**Spaltennamen:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description und last_connect_error_timestamp</span><span class="sxs-lookup"><span data-stu-id="8f957-130">**Column names:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description, and last_connect_error_timestamp</span></span>  
  
 [<span data-ttu-id="8f957-131">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="8f957-131">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
 <span data-ttu-id="8f957-132">Bestimmt, ob das aktuelle Replikat das bevorzugte Sicherungsreplikat ist.</span><span class="sxs-lookup"><span data-stu-id="8f957-132">Determines whether the current replica is the preferred backup replica.</span></span> <span data-ttu-id="8f957-133">Gibt 1 zurück, wenn die Datenbank auf der aktuellen Serverinstanz das bevorzugte Replikat ist.</span><span class="sxs-lookup"><span data-stu-id="8f957-133">Returns 1 if the database on the current server instance is the preferred replica.</span></span> <span data-ttu-id="8f957-134">Andernfalls wird 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f957-134">Otherwise, it returns 0.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f957-135">Weitere Informationen zu Leistungsindikatoren für Verfügbarkeitsreplikate (das **SQLServer:Verfügbarkeitsreplikat**  -Leistungsobjekt) finden Sie unter [SQL Server, Verfügbarkeitsreplikat](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="8f957-135">For information about performance counters for availability replicas (the **SQLServer:Availability Replica**  performance object), see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="8f957-136">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="8f957-136">Related Tasks</span></span>  
 <span data-ttu-id="8f957-137">**So zeigen Sie Informationen zu Verfügbarkeitsgruppen an**</span><span class="sxs-lookup"><span data-stu-id="8f957-137">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="8f957-138">Anzeigen von Verfügbarkeitsgruppeneigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-138">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="8f957-139">Anzeigen von Eigenschaften des Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-139">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="8f957-140">AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-140">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="8f957-141">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="8f957-142">Überwachen von Verfügbarkeitsgruppen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-142">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="8f957-143">**So verwalten Sie Verfügbarkeitsreplikate**</span><span class="sxs-lookup"><span data-stu-id="8f957-143">**To manage availability replicas**</span></span>  
  
-   [<span data-ttu-id="8f957-144">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-144">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="8f957-145">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-145">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="8f957-146">Konfigurieren des schreibgeschützten Zugriffs auf ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-146">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="8f957-147">Ändern des Verfügbarkeitsmodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-147">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="8f957-148">Ändern des Failovermodus eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-148">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="8f957-149">Ändern des Sitzungstimeouts für ein Verfügbarkeitsreplikat &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-149">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="8f957-150">Entfernen einer sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-150">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="8f957-151">**So verwalten Sie eine Verfügbarkeitsdatenbank**</span><span class="sxs-lookup"><span data-stu-id="8f957-151">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="8f957-152">Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-152">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="8f957-153">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-153">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="8f957-154">Anhalten einer Verfügbarkeitsdatenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-154">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="8f957-155">Fortsetzen einer Verfügbarkeitsdatenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-155">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="8f957-156">Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-156">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="8f957-157">Entfernen einer primären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-157">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="8f957-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f957-158">See Also</span></span>  
 <span data-ttu-id="8f957-159">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8f957-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="8f957-160">[Überwachen von Verfügbarkeits Gruppen &#40;Transact-SQL-&#41;](monitor-availability-groups-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="8f957-160">[Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span></span>  
 <span data-ttu-id="8f957-161">[AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="8f957-161">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 [<span data-ttu-id="8f957-162">Verwaltung einer Verfügbarkeits Gruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f957-162">Administration of an Availability Group &#40;SQL Server&#41;</span></span>](administration-of-an-availability-group-sql-server.md)  
  
  
