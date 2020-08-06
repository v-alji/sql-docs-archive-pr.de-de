---
title: Ändern des HADR-Clusterkontexts der Serverinstanz (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- Availability replicas [SQL Server], change WSFC cluster context
ms.assetid: ecd99f91-b9a2-4737-994e-507065a12f80
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbc29fa2ebaaf2bbc9e577b5bd303e8a0dd0ec4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724997"
---
# <a name="change-the-hadr-cluster-context-of-server-instance-sql-server"></a><span data-ttu-id="9965b-102">Ändern des HADR-Clusterkontexts der Serverinstanz (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9965b-102">Change the HADR Cluster Context of Server Instance (SQL Server)</span></span>
  <span data-ttu-id="9965b-103">In diesem Thema wird beschrieben, wie der HADR-Clusterkontext einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mit [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] und höheren Versionen gewechselt wird.</span><span class="sxs-lookup"><span data-stu-id="9965b-103">This topic describes how to switch the HADR cluster context of an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="9965b-104">Der *HADR-Clusterkontext* bestimmt, welcher Windows Server Failover Clustering-Cluster (WSFC) die Metadaten für von der Serverinstanz gehostete Verfügbarkeitsreplikate verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9965b-104">The *HADR cluster context* determines which Windows Server Failover Clustering (WSFC) cluster manages the metadata for availability replicas hosted by the server instance.</span></span>  
  
 <span data-ttu-id="9965b-105">Wechseln Sie den HADR-Clusterkontext nur während einer clusterübergreifenden Migration von [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] zu einer Instanz von [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] auf einem neuen WSFC-Cluster.</span><span class="sxs-lookup"><span data-stu-id="9965b-105">Switch the HADR cluster context only during a cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] to an instance of [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] on a new WSFC cluster.</span></span> <span data-ttu-id="9965b-106">Die Kreuzclustermigration von [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] unterstützt ein Betriebssystemupgrade auf [!INCLUDE[win8](../../../includes/win8-md.md)] oder [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] mit minimalen Ausfallzeiten der Verfügbarkeitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9965b-106">Cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supports OS upgrade to [!INCLUDE[win8](../../../includes/win8-md.md)] or [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] with minimal downtime of availability groups.</span></span> <span data-ttu-id="9965b-107">Weitere Informationen finden Sie unter [Clusterübergreifende Migration von AlwaysOn-Verfügbarkeitsgruppen für Betriebssystemupgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="9965b-107">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9965b-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9965b-108">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9965b-109">Wechseln Sie den HADR-Clusterkontext nur während der clusterübergreifenden Migration von [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="9965b-109">Switch the HADR cluster context only during cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deployments.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9965b-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9965b-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9965b-111">Sie können mit dem HADR-Clusterkontext nur vom lokalen WSFC-Cluster zu einem Remotecluster und dann zurück vom Remotecluster zum lokalen Cluster wechseln.</span><span class="sxs-lookup"><span data-stu-id="9965b-111">You can switch the HADR cluster context only from the local WSFC cluster to a remote cluster and then back from the remote cluster to the local cluster.</span></span> <span data-ttu-id="9965b-112">Sie können den HADR-Clusterkontext nicht von einem Remotecluster zu einem anderen Remotecluster umschalten.</span><span class="sxs-lookup"><span data-stu-id="9965b-112">You cannot switch the HADR cluster context from one remote cluster to another remote cluster.</span></span>  
  
-   <span data-ttu-id="9965b-113">Der HADR-Clusterkontext kann nur dann zu einem Remotecluster umgeschaltet werden, wenn die Instanz von SQL-Server keine Verfügbarkeitsreplikate hostet.</span><span class="sxs-lookup"><span data-stu-id="9965b-113">The HADR cluster context can be switched to a remote cluster only when the instance of SQL Server is not hosting any availability replicas.</span></span>  
  
-   <span data-ttu-id="9965b-114">Ein Remote-HADR-Clusterkontext kann jederzeit zurück zum lokalen Cluster wechseln.</span><span class="sxs-lookup"><span data-stu-id="9965b-114">A remote HADR cluster context can be switched back to the local cluster at any time.</span></span> <span data-ttu-id="9965b-115">Der Kontext kann jedoch nicht erneut gewechselt werden, solange die Serverinstanz Verfügbarkeitsreplikate hostet.</span><span class="sxs-lookup"><span data-stu-id="9965b-115">However, the context cannot be switched again as long as the server instance is hosting any availability replicas.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9965b-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9965b-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="9965b-117">Die Serverinstanz, auf der Sie den HADR-Clusterkontext ändern, muss [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] oder höher (ab Enterprise Edition) ausführen.</span><span class="sxs-lookup"><span data-stu-id="9965b-117">The server instance on which you change the HADR cluster context must be running [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="9965b-118">Die Serverinstanzen muss für AlwaysOn aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="9965b-118">The server instance must be enabled for AlwaysOn.</span></span> <span data-ttu-id="9965b-119">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren von AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9965b-119">For more information, see [Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="9965b-120">Damit eine Serverinstanz von einem lokalen Clusterkontext auf einen Remotecluster umgeschaltet werden kann, darf sie keine Verfügbarkeitsreplikate hosten.</span><span class="sxs-lookup"><span data-stu-id="9965b-120">To be eligible to be switched from the local cluster context to a remote cluster cluster, a server instance cannot be hosting any availability replicas.</span></span> <span data-ttu-id="9965b-121">Die [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) -Katalogsicht sollte keine Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9965b-121">The [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) catalog view should not return any rows.</span></span>  
  
     <span data-ttu-id="9965b-122">Wenn auf der Serverinstanz Verfügbarkeitsreplikate vorhanden sind, bevor Sie den HADR-Clusterkontext ändern können, müssen Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="9965b-122">If any availability replicas exist on the server instance, before you can change the HADR cluster context, you must do one of the following:</span></span>  
  
    |<span data-ttu-id="9965b-123">Replikatrolle</span><span class="sxs-lookup"><span data-stu-id="9965b-123">Replica Role</span></span>|<span data-ttu-id="9965b-124">Aktion</span><span class="sxs-lookup"><span data-stu-id="9965b-124">Action</span></span>|<span data-ttu-id="9965b-125">Link</span><span class="sxs-lookup"><span data-stu-id="9965b-125">Link</span></span>|  
    |------------------|------------|----------|  
    |<span data-ttu-id="9965b-126">Primär</span><span class="sxs-lookup"><span data-stu-id="9965b-126">Primary</span></span>|<span data-ttu-id="9965b-127">Schaltet die Verfügbarkeitsgruppe offline.</span><span class="sxs-lookup"><span data-stu-id="9965b-127">Take the availability group offline.</span></span>|[<span data-ttu-id="9965b-128">Offlineschalten einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-128">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)|  
    |<span data-ttu-id="9965b-129">Secondary</span><span class="sxs-lookup"><span data-stu-id="9965b-129">Secondary</span></span>|<span data-ttu-id="9965b-130">Entfernen des Replikats aus der Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="9965b-130">Remove the replica from its availability group</span></span>|[<span data-ttu-id="9965b-131">Entfernen einer sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-131">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)|  
  
-   <span data-ttu-id="9965b-132">Bevor Sie von einem Remotecluster zum lokalen Cluster wechseln können, müssen alle Replikate mit synchronem Commit SYNCHRONIZED sein.</span><span class="sxs-lookup"><span data-stu-id="9965b-132">Before you can switch from a remote cluster to the local cluster, all synchronous-commit replicas must be SYNCHRONIZED.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9965b-133">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="9965b-133">Recommendations</span></span>  
  
-   <span data-ttu-id="9965b-134">Es wird empfohlen, dass Sie den vollständigen Domänennamen angeben.</span><span class="sxs-lookup"><span data-stu-id="9965b-134">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="9965b-135">Der Grund hierfür ist, dass ALTER SERVER CONFIGURATION die Ziel-IP-Adresse eines Kurznamens mithilfe einer DNS-Auflösung sucht.</span><span class="sxs-lookup"><span data-stu-id="9965b-135">This is because to find the target IP address of a short name, ALTER SERVER CONFIGURATION uses DNS resolution.</span></span> <span data-ttu-id="9965b-136">In einigen Fällen, abhängig von der DNS-Suchreihenfolge, kann die Verwendung eines Kurznamens Verwirrung verursachen.</span><span class="sxs-lookup"><span data-stu-id="9965b-136">Under some situations, depending on the DNS searching order, using a short name could cause confusion.</span></span> <span data-ttu-id="9965b-137">Betrachten Sie zum Beispiel den folgenden Befehl, der für einen Knoten in der Domäne `abc` ausgeführt wird: (`node1.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="9965b-137">For example, consider the following command, which is executed on a node in the `abc` domain, (`node1.abc.com`).</span></span> <span data-ttu-id="9965b-138">Der vorgesehene Zielcluster ist der `CLUS01` -Cluster in der Domäne `xyz` (`clus01.xyz.com`).</span><span class="sxs-lookup"><span data-stu-id="9965b-138">The intended destination cluster is the `CLUS01` cluster in the `xyz` domain (`clus01.xyz.com`).</span></span> <span data-ttu-id="9965b-139">Die lokale Domäne hostet jedoch auch einen Cluster mit dem Namen `CLUS01` (`clus01.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="9965b-139">However, the local  domain hosts also hosts a cluster named `CLUS01` (`clus01.abc.com`).</span></span>  
  
     <span data-ttu-id="9965b-140">Wenn der Kurzname des Zielclusters, `CLUS01`, angegeben wird, kann die DNS-Namensauflösung die IP-Adresse des falschen Clusters, `clus01.abc.com`, zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9965b-140">If the short name of the target cluster, `CLUS01`, were specified, DNS name resolution could return the IP address of the wrong cluster, `clus01.abc.com`.</span></span> <span data-ttu-id="9965b-141">Um derartige Verwirrungen zu vermeiden, geben Sie den vollständigen Namen des Zielclusters an, wie im folgende Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9965b-141">To avoid such confusion, specify the full name of the target cluster, as in the following example:</span></span>  
  
    ```  
    ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com'  
    ```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9965b-142">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9965b-142">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9965b-143">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9965b-143">Permissions</span></span>  
  
-   <span data-ttu-id="9965b-144">**SQL Server-Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="9965b-144">**SQL Server login**</span></span>  
  
     <span data-ttu-id="9965b-145">Erfordert die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="9965b-145">Requires CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="9965b-146">**SQL Server Dienst Konto**</span><span class="sxs-lookup"><span data-stu-id="9965b-146">**SQL Server service account**</span></span>  
  
     <span data-ttu-id="9965b-147">Das [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienstkonto der Serverinstanz muss über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="9965b-147">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account of the server instance must have:</span></span>  
  
    -   <span data-ttu-id="9965b-148">Berechtigung zum Öffnen des WSFC-Zielclusters.</span><span class="sxs-lookup"><span data-stu-id="9965b-148">Permission to open the destination WSFC cluster.</span></span>  
  
    -   <span data-ttu-id="9965b-149">Remote-WSFC-Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="9965b-149">Remote WSFC read-write access.</span></span>  
  
 
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9965b-150">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9965b-150">Using Transact-SQL</span></span>  
 <span data-ttu-id="9965b-151">**So ändern Sie den WSFC-Clusterkontext eines Verfügbarkeitsreplikats**</span><span class="sxs-lookup"><span data-stu-id="9965b-151">**To change the WSFC cluster context of an availability replica**</span></span>  
  
1.  <span data-ttu-id="9965b-152">Stellen Sie eine Verbindung mit der Serverinstanz her, die entweder das primäre Replikat oder ein sekundäres Replikat der Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="9965b-152">Connect to the server instance that hosts either the primary replica or a secondary replica of the availability group.</span></span>  
  
2.  <span data-ttu-id="9965b-153">Verwenden Sie die SET HADR CLUSTER CONTEXT-Klausel der [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) -Anweisung, wie nachfolgend aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="9965b-153">Use the SET HADR CLUSTER CONTEXT clause of the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="9965b-154">Alter Server Configuration Set HADR-Cluster Kontext **=** { **' *`windows_cluster`* '** | Nah</span><span class="sxs-lookup"><span data-stu-id="9965b-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **'*`windows_cluster`*'** | LOCAL }</span></span>  
  
     <span data-ttu-id="9965b-155">Erläuterungen:</span><span class="sxs-lookup"><span data-stu-id="9965b-155">where,</span></span>  
  
     <span data-ttu-id="9965b-156">*Windows-Cluster*</span><span class="sxs-lookup"><span data-stu-id="9965b-156">*windows_cluster*</span></span>  
     <span data-ttu-id="9965b-157">Der Clusterobjektname (CON) eines WSFC-Clusters.</span><span class="sxs-lookup"><span data-stu-id="9965b-157">The cluster object name (CON) of a WSFC cluster.</span></span> <span data-ttu-id="9965b-158">Sie können entweder den Kurznamen oder den vollständigen Domänennamen angeben.</span><span class="sxs-lookup"><span data-stu-id="9965b-158">You can specify either the short name or the full domain name.</span></span> <span data-ttu-id="9965b-159">Es wird empfohlen, dass Sie den vollständigen Domänennamen angeben.</span><span class="sxs-lookup"><span data-stu-id="9965b-159">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="9965b-160">Weitere Informationen finden Sie weiter oben in diesem Thema unter [Empfehlungen](#Recommendations).</span><span class="sxs-lookup"><span data-stu-id="9965b-160">For more information, see [Recommendations](#Recommendations), earlier in this topic.</span></span>  
  
     <span data-ttu-id="9965b-161">LOCAL</span><span class="sxs-lookup"><span data-stu-id="9965b-161">LOCAL</span></span>  
     <span data-ttu-id="9965b-162">Der lokale WSFC-Cluster.</span><span class="sxs-lookup"><span data-stu-id="9965b-162">The local WSFC cluster.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="9965b-163">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9965b-163">Examples</span></span>  
 <span data-ttu-id="9965b-164">Im folgenden Beispiel wird der HADR-Clusterkontext in einen anderen Cluster geändert.</span><span class="sxs-lookup"><span data-stu-id="9965b-164">The following example changes the HADR cluster context to a different cluster.</span></span> <span data-ttu-id="9965b-165">Im Beispiel wird der vollständige Clusterobjektname, `clus01`, angegeben, um den Ziel-WSFC-Cluster `clus01.xyz.com`anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9965b-165">To identify the destination WSFC cluster, `clus01`, the example specifies the full cluster object name, `clus01.xyz.com`.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
 <span data-ttu-id="9965b-166">Im folgenden Beispiel wird der HADR-Clusterkontext in den lokalen WSFC-Cluster geändert.</span><span class="sxs-lookup"><span data-stu-id="9965b-166">The following example changes the HADR cluster context to the local WSFC cluster.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = LOCAL;  
```  
  

  
##  <a name="follow-up-after-switching-the-cluster-context-of-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="9965b-167">Nachverfolgung: Nach dem Wechseln des Clusterkontexts eines Verfügbarkeitsreplikats</span><span class="sxs-lookup"><span data-stu-id="9965b-167">Follow Up: After Switching the Cluster Context of an Availability Replica</span></span>  
 <span data-ttu-id="9965b-168">Der neue HADR-Clusterkontext wird sofort wirksam, ohne die Serverinstanz neu starten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="9965b-168">The new HADR cluster context takes effect immediately, without restarting the server instance.</span></span> <span data-ttu-id="9965b-169">Die Einstellung für den HADR-Clusterkontext ist eine persistente Einstellung auf Instanzebene, die unverändert bleibt, wenn die Serverinstanz neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="9965b-169">The HADR cluster context setting is a persistent instance-level setting that remains unchanged if the server instance restarts.</span></span>  
  
 <span data-ttu-id="9965b-170">Bestätigen Sie den neuen HADR-Clusterkontext, indem Sie die dynamische Verwaltungssicht [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) wie folgt abfragen:</span><span class="sxs-lookup"><span data-stu-id="9965b-170">Confirm the new HADR cluster context by querying the [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) dynamic management view, as follows:</span></span>  
  
```  
SELECT cluster_name FROM sys.dm_hadr_cluster  
```  
  
 <span data-ttu-id="9965b-171">Diese Abfrage sollte den Namen des Clusters zurückgeben, auf den Sie den HADR-Clusterkontext festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="9965b-171">This query should return the name of the cluster to which you set the HADR cluster context.</span></span>  
  
 <span data-ttu-id="9965b-172">Wenn der HADR-Clusterkontext zu einem neuen Cluster gewechselt wird:</span><span class="sxs-lookup"><span data-stu-id="9965b-172">When the HADR cluster context is switched to a new cluster:</span></span>  
  
-   <span data-ttu-id="9965b-173">Die Metadaten werden für alle Verfügbarkeitsreplikate bereinigt, die gerade von der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="9965b-173">The metadata is cleaned up for any availability replicas that are currently hosted by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9965b-174">Alle Datenbanken, die zuvor zu einem Verfügbarkeitsreplikat gehörten, befinden sich jetzt im Status RESTORING.</span><span class="sxs-lookup"><span data-stu-id="9965b-174">All the databases that previously belonged to an availability replica are now in the RESTORING state.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9965b-175">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9965b-175">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9965b-176">Entfernen eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-176">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="9965b-177">Offlineschalten einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-177">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
-   [<span data-ttu-id="9965b-178">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9965b-179">Entfernen einer sekundären Replikats aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-179">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9965b-180">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-180">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="9965b-181">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-181">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
 
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9965b-182">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9965b-182">Related Content</span></span>  
  
-   <span data-ttu-id="9965b-183">[Technische Artikel zu SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9965b-183">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="9965b-184">SQL Server AlwaysOn-Teamblog: Der offizielle SQL Server AlwaysOn-Teamblog</span><span class="sxs-lookup"><span data-stu-id="9965b-184">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="9965b-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9965b-185">See Also</span></span>  
 <span data-ttu-id="9965b-186">[AlwaysOn-Verfügbarkeitsgruppen (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server-Failoverclustering &#40;wsfc-&#41; mit SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9965b-186">[AlwaysOn Availability Groups (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="9965b-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9965b-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-server-configuration-transact-sql)  
  
  
