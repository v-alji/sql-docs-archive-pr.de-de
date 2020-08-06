---
title: WSFC-Clusterdienst ist offline | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp1WSFCquorum.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: d502548d-ece6-4a42-9ded-2157d33e3d21
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6e7b48f96eb09638291b1d0655d385d606b1666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701906"
---
# <a name="wsfc-cluster-service-is-offline"></a><span data-ttu-id="ce28a-102">WSFC-Clusterdienst ist offline</span><span class="sxs-lookup"><span data-stu-id="ce28a-102">WSFC cluster service is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="ce28a-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="ce28a-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce28a-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="ce28a-104">**Policy Name**</span></span>|<span data-ttu-id="ce28a-105">WSFC-Clusterstatus</span><span class="sxs-lookup"><span data-stu-id="ce28a-105">WSFC Cluster State</span></span>|  
|<span data-ttu-id="ce28a-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="ce28a-106">**Issue**</span></span>|<span data-ttu-id="ce28a-107">Der WSFC-Clusterdienst ist offline.</span><span class="sxs-lookup"><span data-stu-id="ce28a-107">WSFC cluster service is offline.</span></span>|  
|<span data-ttu-id="ce28a-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="ce28a-108">**Category**</span></span>|<span data-ttu-id="ce28a-109">**Critical** (Kritisch)</span><span class="sxs-lookup"><span data-stu-id="ce28a-109">**Critical**</span></span>|  
|<span data-ttu-id="ce28a-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="ce28a-110">**Facet**</span></span>|<span data-ttu-id="ce28a-111">SQL Server-Instanz</span><span class="sxs-lookup"><span data-stu-id="ce28a-111">Instance of SQL Server</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ce28a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce28a-112">Description</span></span>  
 <span data-ttu-id="ce28a-113">Diese Richtlinie überprüft den Status des Windows Server-Failoverclusters (WSFC).</span><span class="sxs-lookup"><span data-stu-id="ce28a-113">This policy checks the state of the Windows Server Failover Cluster (WSFC).</span></span> <span data-ttu-id="ce28a-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand und löst eine Warnung aus, wenn der WSFC-Cluster offline ist oder sich im erzwungenen Quorumstatus befindet.</span><span class="sxs-lookup"><span data-stu-id="ce28a-114">The policy is in an unhealthy state and an alert is raised when the WSFC cluster is offline or in the forced quorum state.</span></span> <span data-ttu-id="ce28a-115">Alle innerhalb dieses Clusters gehosteten Verfügbarkeitsgruppen sind offline, oder eine Notfallwiederherstellungsaktion ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce28a-115">All availability groups hosted within this cluster are offline or a disaster recovery action is required.</span></span>  
  
 <span data-ttu-id="ce28a-116">Der Richtlinienstatus ist fehlerfrei, wenn der Clusterstatus das normale Quorum aufweist.</span><span class="sxs-lookup"><span data-stu-id="ce28a-116">The policy state is healthy when the cluster state is in the normal quorum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce28a-117">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [WSFC-Clusterdienst ist offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) .</span><span class="sxs-lookup"><span data-stu-id="ce28a-117">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [WSFC cluster service is offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="ce28a-118">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="ce28a-118">Possible Causes</span></span>  
 <span data-ttu-id="ce28a-119">Dieses Problem kann von einem Clusterdienstfehler oder aufgrund des Verlusts des Quorums im Cluster verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="ce28a-119">This issue can be caused by a cluster service issue or by the loss of the quorum in the cluster.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="ce28a-120">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="ce28a-120">Possible Solution</span></span>  
 <span data-ttu-id="ce28a-121">Verwenden Sie das Clusterverwaltungstool, um den Workflow für das erzwungene Quorum oder für die Notfallwiederherstellung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ce28a-121">Use the Cluster Administrator tool to perform the forced quorum or disaster recovery workflow.</span></span> <span data-ttu-id="ce28a-122">Falls Sie das Problem nicht beheben können, indem Sie den Workflow für das erzwungene Quorum oder die Notfallwiederherstellung ausführen, sollten Sie Ihren Clusteradministrator um Unterstützung bei der Lösung dieses Problems bitten.</span><span class="sxs-lookup"><span data-stu-id="ce28a-122">If you cannot resolve the issue by performing the forced quorum or disaster recovery, contact your cluster administrator to help resolve this issue.</span></span> <span data-ttu-id="ce28a-123">Weitere Informationen finden Sie unter: [Erzwingen des Starts eines Clusters ohne Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="ce28a-123">For more information, see [Force a WSFC Cluster to Start Without a Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce28a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce28a-124">See Also</span></span>  
 <span data-ttu-id="ce28a-125">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce28a-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ce28a-126">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ce28a-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
