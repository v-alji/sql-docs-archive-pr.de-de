---
title: Erzwingen des Starts eines WSFC-Clusters ohne Quorum | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: 4a121375-7424-4444-b876-baefa8fe9015
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6f2110b706de015d0c7b19475b335908c118267
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617559"
---
# <a name="force-a-wsfc-cluster-to-start-without-a-quorum"></a><span data-ttu-id="7ed43-102">Erzwingen des Starts eines Clusters ohne Quorum</span><span class="sxs-lookup"><span data-stu-id="7ed43-102">Force a WSFC Cluster to Start Without a Quorum</span></span>
  <span data-ttu-id="7ed43-103">In diesem Thema wird beschrieben, wie der Start eines Windows Server-Failoverclustering-Clusterknotens ohne Quorum erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="7ed43-103">This topic describes how to force a Windows Server Failover Clustering (WSFC) cluster node to start without a quorum.</span></span>  <span data-ttu-id="7ed43-104">Dies ist möglicherweise für die Notfallwiederherstellung sowie in Multisubnetzszenarien erforderlich, um Daten wiederherzustellen die hohe Verfügbarkeit für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] - und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Failoverclusterinstanzen wieder vollständig einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="7ed43-104">This may be required in disaster recovery and multi-subnet scenarios to recover data and fully re-establish high-availability for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="7ed43-105">**Vorbereitungen:**  [Empfehlungen](#Recommendations), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="7ed43-105">**Before you start:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="7ed43-106">**So erzwingen Sie den Start eines Clusters ohne Quorum:**  [Verwenden des Failovercluster-Managers](#FailoverClusterManagerProcedure), [Verwenden von PowerShell](#PowerShellProcedure), [Verwenden von Net.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="7ed43-106">**To force a cluster to start without a quorum using:**  [Using Failover Cluster Manager](#FailoverClusterManagerProcedure), [Using Powershell](#PowerShellProcedure), [Using Net.exe](#CommandPromptProcedure)</span></span>  
  
-   <span data-ttu-id="7ed43-107">**Nachverfolgung:**  [Nachverfolgung: Nach dem Erzwingen des Clusterstarts ohne ein Quorum](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7ed43-107">**Follow up:**  [Follow Up: After Forcing Cluster to Start without a Quorum](#FollowUp)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7ed43-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7ed43-108">Before You Start</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="7ed43-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="7ed43-109">Recommendations</span></span>  
 <span data-ttu-id="7ed43-110">Ohne anderslautende Angaben sind die in diesem Thema beschriebenen Prozeduren anwendbar, wenn sie von einem beliebigen Knoten im WSFC-Cluster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7ed43-110">Except where explicitly directed, the procedures in this topic should work if you execute them from any node in the WSFC cluster.</span></span>  <span data-ttu-id="7ed43-111">Sie erzielen jedoch u. U. bessere Ergebnisse und vermeiden Netzwerkprobleme, indem Sie diese Schritte von dem Knoten ausführen, von dem aus der Start ohne Quorum erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ed43-111">However, you may obtain better results, and avoid networking issues, by executing these steps from the node that you intend to force to start without a quorum.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7ed43-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7ed43-112">Security</span></span>  
 <span data-ttu-id="7ed43-113">Der Benutzer muss einem Domänenkonto entsprechen, das Mitglied der lokalen Administratorgruppe an jedem Knoten des WSFC-Clusters ist.</span><span class="sxs-lookup"><span data-stu-id="7ed43-113">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-failover-cluster-manager"></a><a name="FailoverClusterManagerProcedure"></a><span data-ttu-id="7ed43-114">Verwenden von Failovercluster-Manager</span><span class="sxs-lookup"><span data-stu-id="7ed43-114">Using Failover Cluster Manager</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="7ed43-115">So erzwingen Sie den Start eines Clusters ohne Quorum</span><span class="sxs-lookup"><span data-stu-id="7ed43-115">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="7ed43-116">Öffnen Sie einen Failovercluster-Manager, und stellen Sie eine Verbindung mit dem gewünschten Clusterknoten her, um dessen Onlineschaltung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7ed43-116">Open a Failover Cluster Manager and connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="7ed43-117">Klicken Sie im **Aktions** Bereich auf **Cluster Start erzwingen**, und klicken Sie dann auf **Ja-eigenen Cluster starten**.</span><span class="sxs-lookup"><span data-stu-id="7ed43-117">In the **Actions** pane, click **Force Cluster Start**, and then click **Yes - Force my cluster to start**.</span></span>  
  
3.  <span data-ttu-id="7ed43-118">Klicken Sie im linken Bereich in der Struktur **Failovercluster-Manager** auf den Clusternamen.</span><span class="sxs-lookup"><span data-stu-id="7ed43-118">In the left pane, in the **Failover Cluster Manager** tree, click the cluster name.</span></span>  
  
4.  <span data-ttu-id="7ed43-119">Stellen Sie im Zusammenfassungsbereich sicher, dass für **Quorumkonfiguration** als aktueller Wert  **Warnung: Der Cluster wird im Status "ForceQuorum" ausgeführt**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7ed43-119">In the summary pane, confirm that the current **Quorum Configuration** value is:  **Warning: Cluster is running in ForceQuorum state**.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a><span data-ttu-id="7ed43-120">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ed43-120">Using Powershell</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="7ed43-121">So erzwingen Sie den Start eines Clusters ohne Quorum</span><span class="sxs-lookup"><span data-stu-id="7ed43-121">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="7ed43-122">Starten Sie eine erhöhte Windows PowerShell mittels **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7ed43-122">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="7ed43-123">Importieren Sie das `FailoverClusters` -Modul, um Cluster-Cmdlets zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ed43-123">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="7ed43-124">Stellen Sie mithilfe von `Stop-ClusterNode` sicher, dass der Clusterdienst beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7ed43-124">Use `Stop-ClusterNode` to make sure that the cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="7ed43-125">Verwenden Sie `Start-ClusterNode` mit `-FixQuorum` , um den Start des Clusterdiensts zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7ed43-125">Use `Start-ClusterNode` with `-FixQuorum` to force the cluster service to start.</span></span>  
  
5.  <span data-ttu-id="7ed43-126">Verwenden Sie `Get-ClusterNode` mit `-Propery NodeWieght = 1` , um den Wert festzulegen, mit dem gewährleistet wird, dass der Knoten ein Abstimmungselement des Quorums ist.</span><span class="sxs-lookup"><span data-stu-id="7ed43-126">Use `Get-ClusterNode` with `-Propery NodeWieght = 1` to set the value the guarantees that the node is a voting member of the quorum.</span></span>  
  
6.  <span data-ttu-id="7ed43-127">Geben Sie die Clusterknoteneigenschaften in einem lesbaren Format aus.</span><span class="sxs-lookup"><span data-stu-id="7ed43-127">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="7ed43-128">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="7ed43-128">Example (Powershell)</span></span>  
 <span data-ttu-id="7ed43-129">Im folgenden Beispiel wird der Start des AlwaysOnSrv02-Knotenclusterdiensts ohne Quorum erzwungen. Dabei wird `NodeWeight = 1`festgelegt, und anschließend wird der Clusterknotenstatus vom neu erzwungenen Knoten aus aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7ed43-129">The following example forces the AlwaysOnSrv02 node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv02"  
Stop-ClusterNode -Name $node  
Start-ClusterNode -Name $node -FixQuorum  
  
(Get-ClusterNode $node).NodeWeight = 1  
  
$nodes = Get-ClusterNode -Cluster $node  
$nodes | Format-Table -property NodeName, State, NodeWeight
```  
  
##  <a name="using-netexe"></a><a name="CommandPromptProcedure"></a><span data-ttu-id="7ed43-130">Verwenden von Net.exe</span><span class="sxs-lookup"><span data-stu-id="7ed43-130">Using Net.exe</span></span>  
  
### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="7ed43-131">So erzwingen Sie den Start eines Clusters ohne Quorum</span><span class="sxs-lookup"><span data-stu-id="7ed43-131">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="7ed43-132">Stellen Sie mittels Remotedesktop eine Verbindung mit dem gewünschten Clusterknoten her, um dessen Onlineschaltung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7ed43-132">Use Remote Desktop to connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="7ed43-133">Starten Sie mit **Als Administrator ausführen**eine Eingabeaufforderung mit erweiterten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="7ed43-133">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
3.  <span data-ttu-id="7ed43-134">Stellen Sie mithilfe von **net.exe** sicher, dass der lokale Clusterdienst beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7ed43-134">Use **net.exe** to make sure that the local cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="7ed43-135">Verwenden Sie **net.exe** mit `/forcequorum` , um den Start des lokalen Clusterdiensts zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7ed43-135">Use **net.exe** with `/forcequorum` to force the local cluster service to start.</span></span>  
  
### <a name="example-netexe"></a><span data-ttu-id="7ed43-136">Beispiel (Net.exe)</span><span class="sxs-lookup"><span data-stu-id="7ed43-136">Example (Net.exe)</span></span>  
 <span data-ttu-id="7ed43-137">Im folgenden Beispiel wird der Start eines Knotenclusterdiensts ohne Quorum erzwungen. Dabei wird `NodeWeight = 1`festgelegt, und anschließend wird der Clusterknotenstatus vom neu erzwungenen Knoten aus aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7ed43-137">The following example forces a node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```cmd
net.exe stop clussvc  
net.exe start clussvc /forcequorum  
```  
  
##  <a name="follow-up-after-forcing-cluster-to-start-without-a-quorum"></a><a name="FollowUp"></a><span data-ttu-id="7ed43-138">Nachverfolgung: nach dem Erzwingen des Cluster Starts ohne ein Quorum</span><span class="sxs-lookup"><span data-stu-id="7ed43-138">Follow Up: After Forcing Cluster to Start without a Quorum</span></span>  
  
-   <span data-ttu-id="7ed43-139">NodeWeight-Werte sind neu zu bewerten und zu konfigurieren, um vor der erneuten Onlineschaltung anderer Knoten ein neues Quorum korrekt erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="7ed43-139">You must re-evaluate and reconfigure NodeWeight values to correctly construct a new quorum before bringing other nodes back online.</span></span> <span data-ttu-id="7ed43-140">Andernfalls wird für den Cluster u. U. wieder der Offlinemodus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ed43-140">Otherwise, the cluster may go back offline again.</span></span>  
  
     <span data-ttu-id="7ed43-141">Weitere Informationen finden Sie unter [WSFC-Quorummodi und Abstimmungskonfiguration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ed43-141">For more information, see [WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="7ed43-142">Die Prozeduren in diesem Thema stellen nur einen Schritt zur erneuten Onlineschaltung des WSFC-Clusters dar, wenn ein unvorhergesehener Quorumfehler auftreten sollte.</span><span class="sxs-lookup"><span data-stu-id="7ed43-142">The procedures in this topic are only one step in bringing the WSFC cluster back online if an un-planned quorum failure were to occur.</span></span>  <span data-ttu-id="7ed43-143">Sie möchten möglicherweise weitere Maßnahmen ergreifen, um zu verhindern, dass andere WSFC-Clusterknoten die neue Quorumkonfiguration stören.</span><span class="sxs-lookup"><span data-stu-id="7ed43-143">You may also want to take additional steps to prevent other WSFC cluster nodes from interfering with the new quorum configuration.</span></span>  
  
-   <span data-ttu-id="7ed43-144">Andere [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Funktionen, wie [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], die Datenbankspiegelung und der Protokollversand, erfordern u. U. zudem weitere Aktionen zur Datenwiederherstellung und vollständigen erneuten Einrichtung der hohen Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="7ed43-144">Other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features such as [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], database mirroring, and log shipping may also require subsequent actions to recover data and to fully re-establish high-availability.</span></span>  
  
     <span data-ttu-id="7ed43-145">**Weitere Informationen finden Sie unter:**</span><span class="sxs-lookup"><span data-stu-id="7ed43-145">**For more information:**</span></span>  
  
     [<span data-ttu-id="7ed43-146">Ausführen eines erzwungenen manuellen Failovers einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ed43-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](../../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
     [<span data-ttu-id="7ed43-147">Erzwingen des Diensts in einer Datenbank-Spiegelungssitzung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ed43-147">Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](../../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
  
     [<span data-ttu-id="7ed43-148">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ed43-148">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](../../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="7ed43-149">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="7ed43-149">Related Content</span></span>  
  
-   <span data-ttu-id="7ed43-150">[Anzeigen von Ereignissen und Protokollen für einen Failovercluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="7ed43-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span></span>  
  
-   [<span data-ttu-id="7ed43-151">Get-ClusterLog-Failovercluster-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7ed43-151">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="7ed43-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ed43-152">See Also</span></span>  
 <span data-ttu-id="7ed43-153">[Wsfc-Notfall Wiederherstellung durch erzwungenes Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ed43-153">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 <span data-ttu-id="7ed43-154">[Konfigurieren von Cluster-Quorum-nodeweight-Einstellungen](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7ed43-154">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="7ed43-155">[Failovercluster-Cmdlets in Windows PowerShell, aufgelistet nach Taskfokus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7ed43-155">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
