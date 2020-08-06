---
title: Konfigurieren von Cluster-Quorum-NodeWeight-Einstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: cb3fd9a6-39a2-4e9c-9157-619bf3db9951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e469d5fc0fc030304a7cf2f1bdd894eb578aa056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617571"
---
# <a name="configure-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="9fa0b-102">Konfigurieren von Cluster-Quorum-NodeWeight-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9fa0b-102">Configure Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="9fa0b-103">In diesem Thema wird beschrieben, wie NodeWeight-Einstellungen für einen Elementknoten in einem Windows Server-Failoverclustering-Cluster konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-103">This topic describes how to configure NodeWeight settings for a member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="9fa0b-104">NodeWeight-Einstellungen werden während der Quorumabstimmung verwendet, um Notfallwiederherstellungs- und Multisubnetzszenarien für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] - und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Failoverclusterinstanzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="9fa0b-105">**Vorbereitung:**  [Voraussetzungen](#Prerequisites), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="9fa0b-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="9fa0b-106">**Anzeigen von Quorum-NodeWeight-Einstellungen mit:** [Verwenden von Powershell](#PowerShellProcedure), [Verwenden von Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="9fa0b-106">**To view quorum NodeWeight settings using:** [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
-   [<span data-ttu-id="9fa0b-107">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9fa0b-107">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9fa0b-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9fa0b-108">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9fa0b-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9fa0b-109">Prerequisites</span></span>  
 <span data-ttu-id="9fa0b-110">Diese Funktion wird nur in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] oder höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-110">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9fa0b-111">Um NodeWeight-Einstellungen zu verwenden, muss der folgende Hotfix im WSFC-Cluster für alle Server übernommen werden:</span><span class="sxs-lookup"><span data-stu-id="9fa0b-111">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="9fa0b-112">[KB2494036](https://support.microsoft.com/kb/2494036): Ein Hotfix ist verfügbar, mit dem sich ein Clusterknoten konfigurieren lässt, der keine Quorumabstimmung in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] und in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] enthält.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-112">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9fa0b-113">Ist dieser Hotfix nicht installiert, geben die Beispiele in diesem Thema leere Werte oder NULL-Werte für NodeWeight zurück.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-113">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9fa0b-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9fa0b-114">Security</span></span>  
 <span data-ttu-id="9fa0b-115">Der Benutzer muss einem Domänenkonto entsprechen, das Mitglied der lokalen Administratorgruppe an jedem Knoten des WSFC-Clusters ist.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-115">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9fa0b-116">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fa0b-116">Using Powershell</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="9fa0b-117">So konfigurieren Sie NodeWeight-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9fa0b-117">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="9fa0b-118">Starten Sie eine erhöhte Windows PowerShell mittels **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="9fa0b-119">Importieren Sie das `FailoverClusters` -Modul, um Cluster-Cmdlets zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-119">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="9fa0b-120">Verwenden Sie das `Get-ClusterNode` -Objekt, um die `NodeWeight` -Eigenschaft für jeden Knoten im Cluster festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-120">Use the `Get-ClusterNode` object to set the `NodeWeight` property for each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="9fa0b-121">Geben Sie die Clusterknoteneigenschaften in einem lesbaren Format aus.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-121">Output the cluster node properties in a readable format.</span></span>  
  
 <span data-ttu-id="9fa0b-122">Im folgenden Beispiel wird die NodeWeight-Einstellung geändert, um die Quorumabstimmung für den AlwaysOnSrv1-Knoten zu entfernen. Zudem werden die Einstellungen für alle Knoten im Cluster ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-122">The following example changes the NodeWeight setting to remove the quorum vote for the "AlwaysOnSrv1" node, and then outputs the settings for all nodes in the cluster.</span></span>
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv1"  
(Get-ClusterNode $node).NodeWeight = 0  
  
$cluster = (Get-ClusterNode $node).Cluster  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="9fa0b-123">Verwenden von Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="9fa0b-123">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fa0b-124">Das Hilfsprogramm von cluster.exe ist in der [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] -Version veraltet.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-124">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="9fa0b-125">Verwenden Sie PowerShell mit Failoverclustering für künftige Entwicklungen.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-125">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="9fa0b-126">Das Hilfsprogramm von cluster.exe wird in der nächsten Version von Windows Server entfernt.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-126">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="9fa0b-127">Weitere Informationen finden Sie unter [Zuordnen von Cluster.exe-Befehlen zu Windows PowerShell-Cmdlets für Failovercluster](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9fa0b-127">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="9fa0b-128">So konfigurieren Sie NodeWeight-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9fa0b-128">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="9fa0b-129">Starten Sie mit **Als Administrator ausführen**eine Eingabeaufforderung mit erweiterten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-129">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="9fa0b-130">Verwenden Sie **cluster.exe** , um `NodeWeight` -Werte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-130">Use **cluster.exe** to set `NodeWeight` values.</span></span>  

 <span data-ttu-id="9fa0b-131">Im folgenden Beispiel wird der NodeWeight-Wert geändert, um die Quorumabstimmung des Knotens „AlwaysOnSrv1“ im Cluster „Cluster001“ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9fa0b-131">The following example changes the NodeWeight value to remove the quorum vote of the "AlwaysOnSrv1" node in the "Cluster001" cluster.</span></span>  
  
```cmd
cluster.exe Cluster001 node AlwaysOnSrv1 /prop NodeWeight=0  
```  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9fa0b-132">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9fa0b-132">Related Content</span></span>  
  
-   <span data-ttu-id="9fa0b-133">[Anzeigen von Ereignissen und Protokollen für einen Failovercluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9fa0b-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="9fa0b-134">Get-ClusterLog-Failovercluster-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9fa0b-134">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="9fa0b-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fa0b-135">See Also</span></span>  
 <span data-ttu-id="9fa0b-136">[Wsfc-Quorum Modi und Abstimmungs Konfiguration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9fa0b-136">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="9fa0b-137">[Anzeigen von Cluster-Quorum-nodeweight-Einstellungen](view-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="9fa0b-137">[View Cluster Quorum NodeWeight Settings](view-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="9fa0b-138">[Failovercluster-Cmdlets in Windows PowerShell, aufgelistet nach Taskfokus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9fa0b-138">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
