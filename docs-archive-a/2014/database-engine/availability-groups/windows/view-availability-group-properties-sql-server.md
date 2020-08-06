---
title: Anzeigen von Verfügbarkeitsgruppeneigenschaften (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server]
ms.assetid: 61243c87-bd62-4510-863f-2a8f347caf1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b7d1f57a9bd29b6c65160ec9a163bc77dfca48b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616181"
---
# <a name="view-availability-group-properties-sql-server"></a><span data-ttu-id="d6c27-102">Anzeigen von Verfügbarkeitsgruppeneigenschaften (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d6c27-102">View Availability Group Properties (SQL Server)</span></span>
  <span data-ttu-id="d6c27-103">In diesem Thema wird beschrieben, wie die Eigenschaften einer Verfügbarkeitsgruppe für eine AlwaysOn-Verfügbarkeitsgruppe unter Verwendung von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6c27-103">This topic describes how to view the properties of an availability group for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  

  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d6c27-104">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6c27-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d6c27-105">**So zeigen Sie die Eigenschaften einer Verfügbarkeitsgruppe an und ändern sie**</span><span class="sxs-lookup"><span data-stu-id="d6c27-105">**To view and change the properties an availability group**</span></span>  
  
1.  <span data-ttu-id="d6c27-106">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="d6c27-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d6c27-107">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="d6c27-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="d6c27-108">Klicken Sie mit der rechten Maustaste auf die Verfügbarkeitsgruppe, deren Eigenschaften Sie anzeigen möchten, und wählen Sie den Befehl **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="d6c27-108">Right-click the availability group whose properties you want to view, and select the **Properties** command.</span></span>  
  
4.  <span data-ttu-id="d6c27-109">Verwenden Sie im Dialogfeld **Eigenschaften der Verfügbarkeitsgruppe** die Seiten **Allgemein** und **Sicherungseinstellungen** , um Eigenschaften der ausgewählten Verfügbarkeitsgruppe anzuzeigen und in einigen Fällen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d6c27-109">In the **Availability Group Properties** dialog box, use the **General** and **Backup Preferences** pages to view and, in some cases, change properties of the selected availability group.</span></span> <span data-ttu-id="d6c27-110">Weitere Informationen finden Sie unter [Eigenschaften der Verfügbarkeitsgruppe: Neue Verfügbarkeitsgruppe &#40;Seite „Allgemein“&#41;](availability-group-properties-new-availability-group-general-page.md) und [Eigenschaften der Verfügbarkeitsgruppe: Neue Verfügbarkeitsgruppe &#40;Seite „Sicherungseinstellungen“&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6c27-110">For more information, see [Availability Group Properties and New Availability Group &#40;General Page&#41;](availability-group-properties-new-availability-group-general-page.md) and [Availability Group Properties: New Availability Group &#40;Backup Preferences Page&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span></span>  
  
     <span data-ttu-id="d6c27-111">Verwenden Sie die Seite **Berechtigungen** , um die aktuellen Anmeldungen, Rollen und der Verfügbarkeitsgruppe zugeordneten expliziten Berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6c27-111">Use the **Permissions** page to view the current logins, roles, and explicit permissions associated with the availability group.</span></span> <span data-ttu-id="d6c27-112">Weitere Informationen finden Sie unter [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6c27-112">For more information, see [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d6c27-113">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6c27-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="d6c27-114">**So zeigen Sie die Eigenschaften und den Status einer Verfügbarkeitsgruppe an**</span><span class="sxs-lookup"><span data-stu-id="d6c27-114">**To view the properties and state of an availability group**</span></span>  
  
 <span data-ttu-id="d6c27-115">Verwenden Sie zum Abfragen der Eigenschaften und des Status der Verfügbarkeitsgruppen, für die die Serverinstanz ein Verfügbarkeitsreplikat hostet, die folgenden Sichten:</span><span class="sxs-lookup"><span data-stu-id="d6c27-115">To query the properties and states of the availability groups for which the server instance hosts an availability replica, use the following views:</span></span>  
  
 [<span data-ttu-id="d6c27-116">sys.availability_groups</span><span class="sxs-lookup"><span data-stu-id="d6c27-116">sys.availability_groups</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-transact-sql)  
 <span data-ttu-id="d6c27-117">Gibt eine Zeile für jede Verfügbarkeitsgruppe zurück, für die die lokale Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ein Verfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="d6c27-117">Returns a row for each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span> <span data-ttu-id="d6c27-118">Jede Zeile enthält eine zwischengespeicherte Kopie der Metadaten der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d6c27-118">Each row contains a cached copy of the availability group metadata.</span></span>  
  
 <span data-ttu-id="d6c27-119">**Spaltennamen:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="d6c27-119">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="d6c27-120">sys.availability_groups_cluster</span><span class="sxs-lookup"><span data-stu-id="d6c27-120">sys.availability_groups_cluster</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-cluster-transact-sql)  
 <span data-ttu-id="d6c27-121">Gibt eine Zeile für jede Verfügbarkeitsgruppe im WSFC-Cluster zurück.</span><span class="sxs-lookup"><span data-stu-id="d6c27-121">Returns a row for each availability group in the WSFC cluster.</span></span> <span data-ttu-id="d6c27-122">Jede Zeile enthält die Verfügbarkeitsgruppenmetadaten vom WSFC-Cluster (Windows Server-Failoverclustering).</span><span class="sxs-lookup"><span data-stu-id="d6c27-122">Each row contains the availability group metadata from the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="d6c27-123">**Spaltennamen:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="d6c27-123">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="d6c27-124">sys.dm_hadr_availability_group_states</span><span class="sxs-lookup"><span data-stu-id="d6c27-124">sys.dm_hadr_availability_group_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-group-states-transact-sql)  
 <span data-ttu-id="d6c27-125">Gibt eine Zeile für jede Verfügbarkeitsgruppe zurück, die ein Verfügbarkeitsreplikat in der lokalen Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]besitzt.</span><span class="sxs-lookup"><span data-stu-id="d6c27-125">Returns a row for each availability group that possesses an availability replica on the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d6c27-126">In jede Zeile werden die Statuswerte angezeigt, die den Zustand einer angegebenen Verfügbarkeitsgruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="d6c27-126">Each row displays the states that define the health of a given availability group.</span></span>  
  
 <span data-ttu-id="d6c27-127">**Spaltennamen:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span><span class="sxs-lookup"><span data-stu-id="d6c27-127">**Column names:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d6c27-128">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d6c27-128">Related Tasks</span></span>  
 <span data-ttu-id="d6c27-129">**So zeigen Sie Informationen zu Verfügbarkeitsgruppen an**</span><span class="sxs-lookup"><span data-stu-id="d6c27-129">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="d6c27-130">Anzeigen von Verfügbarkeitsreplikateigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-130">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-131">Anzeigen von Eigenschaften des Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-131">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-132">AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-132">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="d6c27-133">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-133">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="d6c27-134">Überwachen von Verfügbarkeitsgruppen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-134">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="d6c27-135">**So konfigurieren Sie eine vorhandene Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="d6c27-135">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="d6c27-136">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-136">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-137">Entfernen einer sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-137">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-138">Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-138">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="d6c27-139">Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-139">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-140">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-140">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-141">Entfernen eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-141">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-142">Entfernen einer primären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-142">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-143">Entfernen einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-143">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="d6c27-144">**So führen Sie manuell ein Failover für eine Verfügbarkeitsgruppe aus**</span><span class="sxs-lookup"><span data-stu-id="d6c27-144">**To manually fail over an availability group**</span></span>  
  
-   [<span data-ttu-id="d6c27-145">Ausführen eines geplanten manuellen Failovers einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-145">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="d6c27-146">Ausführen eines erzwungenen manuellen Failovers einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="d6c27-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6c27-147">See Also</span></span>  
 <span data-ttu-id="d6c27-148">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [Überwachen von Verfügbarkeits Gruppen &#40;von Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn-Richtlinien für Betriebsprobleme mit AlwaysOn-Verfügbarkeitsgruppen](always-on-policies-for-operational-issues-always-on-availability.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6c27-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md)</span></span> 
  
  
