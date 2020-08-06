---
title: Anzeigen von Cluster-Quorum-NodeWeight-Einstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef2176d4916e8affbb9ef89c9b26499289c520ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617556"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="c138b-102">Anzeigen von Cluster-Quorum-NodeWeight-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c138b-102">View Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="c138b-103">In diesem Thema wird beschrieben, wie NodeWeight-Einstellungen für jeden Elementknoten in einem Windows Server-Failoverclustering-Cluster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c138b-103">This topic describes how to view NodeWeight settings for each member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="c138b-104">NodeWeight-Einstellungen werden während der Quorumabstimmung verwendet, um Notfallwiederherstellungs- und Multisubnetzszenarien für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] - und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Failoverclusterinstanzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c138b-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="c138b-105">**Vorbereitung:**  [Voraussetzungen](#Prerequisites), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="c138b-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="c138b-106">**Anzeigen von Quorum-NodeWeight-Einstellungen mit:** [Transact-SQL](#TsqlProcedure), [PowerShell](#PowerShellProcedure), [Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="c138b-106">**To view quorum NodeWeight settings using:** [Using Transact-SQL](#TsqlProcedure), [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c138b-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c138b-107">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c138b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c138b-108">Prerequisites</span></span>  
 <span data-ttu-id="c138b-109">Diese Funktion wird nur in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] oder höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c138b-109">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c138b-110">Um NodeWeight-Einstellungen zu verwenden, muss der folgende Hotfix im WSFC-Cluster für alle Server übernommen werden:</span><span class="sxs-lookup"><span data-stu-id="c138b-110">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="c138b-111">[KB2494036](https://support.microsoft.com/kb/2494036): Ein Hotfix ist verfügbar, mit dem sich ein Clusterknoten konfigurieren lässt, der keine Quorumabstimmung in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] und in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] enthält.</span><span class="sxs-lookup"><span data-stu-id="c138b-111">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="c138b-112">Ist dieser Hotfix nicht installiert, geben die Beispiele in diesem Thema leere Werte oder NULL-Werte für NodeWeight zurück.</span><span class="sxs-lookup"><span data-stu-id="c138b-112">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c138b-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c138b-113">Security</span></span>  
 <span data-ttu-id="c138b-114">Der Benutzer muss einem Domänenkonto entsprechen, das Mitglied der lokalen Administratorgruppe an jedem Knoten des WSFC-Clusters ist.</span><span class="sxs-lookup"><span data-stu-id="c138b-114">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c138b-115">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c138b-115">Using Transact-SQL</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="c138b-116">So zeigen Sie NodeWeight-Einstellungen an</span><span class="sxs-lookup"><span data-stu-id="c138b-116">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="c138b-117">Stellen Sie im Cluster eine Verbindung mit einer beliebigen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c138b-117">Connect to any [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the cluster.</span></span>  
  
2.  <span data-ttu-id="c138b-118">Fragen Sie die Sicht "[sys].[dm_hadr_cluster_members]" ab.</span><span class="sxs-lookup"><span data-stu-id="c138b-118">Query the [sys].[dm_hadr_cluster_members] view.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="c138b-119">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c138b-119">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c138b-120">Im folgenden Beispiel wird eine Systemansicht zur Rückgabe von Werten für alle Knoten im betreffenden Cluster der Instanz abgefragt.</span><span class="sxs-lookup"><span data-stu-id="c138b-120">The following example queries a system view to return values for all of the nodes in that instance's cluster.</span></span>  
  
```sql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c138b-121">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c138b-121">Using Powershell</span></span>  
  
### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="c138b-122">So zeigen Sie NodeWeight-Einstellungen an</span><span class="sxs-lookup"><span data-stu-id="c138b-122">To view NodeWeight settings</span></span>
  
1.  <span data-ttu-id="c138b-123">Starten Sie eine erhöhte Windows PowerShell mittels **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c138b-123">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="c138b-124">Importieren Sie das `FailoverClusters` -Modul, um Cluster-Cmdlets zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c138b-124">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="c138b-125">Verwenden Sie das `Get-ClusterNode` -Objekt, um eine Auflistung von Clusterknotenobjekten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c138b-125">Use the `Get-ClusterNode` object to return a collection of cluster node objects.</span></span>  
  
4.  <span data-ttu-id="c138b-126">Geben Sie die Clusterknoteneigenschaften in einem lesbaren Format aus.</span><span class="sxs-lookup"><span data-stu-id="c138b-126">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="c138b-127">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c138b-127">Example (Powershell)</span></span>  
 <span data-ttu-id="c138b-128">Im folgenden Beispiel werden einige der Knoteneigenschaften für den Cluster „Cluster001“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c138b-128">The following example output some of the node properties for the cluster called "Cluster001".</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -Property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="c138b-129">Verwenden von Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="c138b-129">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c138b-130">Das Hilfsprogramm von cluster.exe ist in der [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] -Version veraltet.</span><span class="sxs-lookup"><span data-stu-id="c138b-130">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="c138b-131">Verwenden Sie PowerShell mit Failoverclustering für künftige Entwicklungen.</span><span class="sxs-lookup"><span data-stu-id="c138b-131">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="c138b-132">Das Hilfsprogramm von cluster.exe wird in der nächsten Version von Windows Server entfernt.</span><span class="sxs-lookup"><span data-stu-id="c138b-132">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="c138b-133">Weitere Informationen finden Sie unter [Zuordnen von Cluster.exe-Befehlen zu Windows PowerShell-Cmdlets für Failovercluster](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c138b-133">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="c138b-134">So zeigen Sie NodeWeight-Einstellungen an</span><span class="sxs-lookup"><span data-stu-id="c138b-134">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="c138b-135">Starten Sie mit **Als Administrator ausführen**eine Eingabeaufforderung mit erweiterten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="c138b-135">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="c138b-136">Verwenden Sie **cluster.exe** , um Knotenstatus- und NodeWeight-Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c138b-136">Use **cluster.exe** to return node status and NodeWeight values</span></span>  
  
### <a name="example-clusterexe"></a><span data-ttu-id="c138b-137">Beispiel (Cluster.exe)</span><span class="sxs-lookup"><span data-stu-id="c138b-137">Example (Cluster.exe)</span></span>  
 <span data-ttu-id="c138b-138">Im folgenden Beispiel werden einige der Knoteneigenschaften für den Cluster „Cluster001“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c138b-138">The following example outputs some of the node properties for the cluster called "Cluster001".</span></span>  
  
```cmd
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="c138b-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c138b-139">See Also</span></span>  
 <span data-ttu-id="c138b-140">[WSFC-Quorummodi und Abstimmungskonfiguration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c138b-140">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="c138b-141">[Konfigurieren von Cluster-Quorum-NodeWeight-Einstellungen](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="c138b-141">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="c138b-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c138b-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span></span>  
 <span data-ttu-id="c138b-143">[Failovercluster-Cmdlets in Windows PowerShell, aufgelistet nach Taskfokus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c138b-143">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
