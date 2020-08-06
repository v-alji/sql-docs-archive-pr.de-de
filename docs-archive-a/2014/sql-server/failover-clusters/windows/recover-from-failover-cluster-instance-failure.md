---
title: Wiederherstellen nach einem Fehler der Failoverclusterinstanz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], recovery from failure
- failover clustering [SQL Server], recovery from failure
- hardware failures [SQL Server]
- recovering failover cluster failures [SQL Server]
ms.assetid: 3d151d0c-e841-4325-8606-c094de37d7d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60db4c2e480b094c18d0a8071e947a38cdc779d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724433"
---
# <a name="recover-from-failover-cluster-instance-failure"></a><span data-ttu-id="1be1d-102">Wiederherstellen nach einem Fehler der Failoverclusterinstanz</span><span class="sxs-lookup"><span data-stu-id="1be1d-102">Recover from Failover Cluster Instance Failure</span></span>
  <span data-ttu-id="1be1d-103">In diesem Thema wird beschrieben, wie eine Wiederherstellung nach Clusterfehlern mithilfe des Failovercluster-Manager-Snap-Ins ausgeführt wird, nachdem in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]ein Failover aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1be1d-103">This topic describes how to recover from cluster failures by using the Failover Cluster Manager snap-in after a failover occurs in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1be1d-104">Das Failovercluster-Manager-Snap-In ist die Clusterverwaltungsanwendung für den WSFC (Windows Server Failover Clustering)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="1be1d-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Serer Failover Clustering (WSFC) service.</span></span>  
  
-   [<span data-ttu-id="1be1d-105">Wiederherstellen nach einem irreparablen Fehler</span><span class="sxs-lookup"><span data-stu-id="1be1d-105">Recover from an irreparable failure</span></span>](#Scenario1)  
  
-   [<span data-ttu-id="1be1d-106">Wiederherstellen nach einem Softwarefehler</span><span class="sxs-lookup"><span data-stu-id="1be1d-106">Recover from a software failure</span></span>](#Scenario2)  
  
##  <a name="recover-from-an-irreparable-failure"></a><a name="Scenario1"></a><span data-ttu-id="1be1d-107">Wiederherstellung nach einem irreparablen Fehler</span><span class="sxs-lookup"><span data-stu-id="1be1d-107">Recover from an irreparable failure</span></span>  
 <span data-ttu-id="1be1d-108">Führen Sie zur Wiederherstellung nach einem irreparablen Fehler folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="1be1d-108">Use the following steps to recover from an irreparable failure.</span></span> <span data-ttu-id="1be1d-109">Der Hardwarefehler kann z. B. durch einen Fehler eines Datenträgercontrollers oder des Betriebssystems verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="1be1d-109">The failure could be caused, for example, by the failure of a disk controller or the operating system.</span></span> <span data-ttu-id="1be1d-110">In diesem Fall wird der Fehler durch einen Hardwarefehler in Knoten 1 eines Clusters mit zwei Knoten verursacht.</span><span class="sxs-lookup"><span data-stu-id="1be1d-110">In this case, failure is caused by hardware failure in Node 1 of a two-node cluster.</span></span>  
  
1.  <span data-ttu-id="1be1d-111">Nach dem Fehler bei Knoten 1 führt die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -FCI ein Failover auf Knoten 2 aus.</span><span class="sxs-lookup"><span data-stu-id="1be1d-111">After Node 1 fails, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="1be1d-112">Entfernen Sie Knoten 1 aus der FCI.</span><span class="sxs-lookup"><span data-stu-id="1be1d-112">Evict Node 1 from the FCI.</span></span> <span data-ttu-id="1be1d-113">Öffnen Sie hierzu in Knoten 2 das Failovercluster-Manager-Snap-In, klicken Sie mit der rechten Maustaste auf Knoten 1, klicken Sie auf **Verschiebeaktionen**und anschließend auf **Knoten entfernen**.</span><span class="sxs-lookup"><span data-stu-id="1be1d-113">To do this, from Node 2, open the Failover Cluster Manager snap-in, right-click Node1, click **Move Actions**, and then click **Evict Node**.</span></span>  
  
3.  <span data-ttu-id="1be1d-114">Überprüfen Sie, ob Knoten 1 aus der Clusterdefinition entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="1be1d-114">Verify that Node 1 has been evicted from the cluster definition.</span></span>  
  
4.  <span data-ttu-id="1be1d-115">Installieren Sie neue Hardware, um die fehlerhafte Hardware in Knoten 1 zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1be1d-115">Install new hardware to replace the failed hardware in Node 1.</span></span>  
  
5.  <span data-ttu-id="1be1d-116">Fügen Sie mithilfe des Failovercluster-Manager-Snap-Ins Knoten 1 zum vorhandenen Cluster hinzu.</span><span class="sxs-lookup"><span data-stu-id="1be1d-116">Using the Failover Cluster Manager snap-in, add Node 1 to the existing cluster.</span></span> <span data-ttu-id="1be1d-117">Weitere Informationen finden Sie unter [Vor dem Installieren des Failoverclusterings](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="1be1d-117">For more information, see [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
6.  <span data-ttu-id="1be1d-118">Stellen Sie sicher, dass die Administratorkonten für alle Clusterknoten identisch sind.</span><span class="sxs-lookup"><span data-stu-id="1be1d-118">Ensure that the administrator accounts are the same on all cluster nodes.</span></span>  
  
7.  <span data-ttu-id="1be1d-119">Führen Sie das [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Setup aus, um der FCI Knoten 1 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1be1d-119">Run [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to add Node 1 to the FCI.</span></span> <span data-ttu-id="1be1d-120">Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Knoten in einem SQL Server-Failovercluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="1be1d-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
##  <a name="recover-from-a-reparable-failure"></a><a name="Scenario2"></a><span data-ttu-id="1be1d-121">Wiederherstellen nach einem Fehler BEHEB baren Fehler</span><span class="sxs-lookup"><span data-stu-id="1be1d-121">Recover from a reparable failure</span></span>  
 <span data-ttu-id="1be1d-122">Führen Sie zur Wiederherstellung nach einem behebbaren Fehler die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="1be1d-122">Us the following steps to recover from a reparable failure.</span></span> <span data-ttu-id="1be1d-123">In diesem Fall wird der Fehler dadurch verursacht, dass Knoten 1 ausgefallen oder offline, aber nicht unwiderruflich fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="1be1d-123">In this case, failure is caused by Node 1 being down or offline but not irretrievably broken.</span></span> <span data-ttu-id="1be1d-124">Die Ursache könnte beispielsweise ein Betriebssystem- oder Hardwarefehler oder ein Fehler in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz selbst sein.</span><span class="sxs-lookup"><span data-stu-id="1be1d-124">This could be caused by an operating system failure, hardware failure, or failure in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance itself.</span></span>  
  
1.  <span data-ttu-id="1be1d-125">Nach dem Fehler bei Knoten 1 führt die FCI ein Failover auf Knoten 2 aus.</span><span class="sxs-lookup"><span data-stu-id="1be1d-125">After Node 1 fails, the FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="1be1d-126">Lösen Sie das Problem bei Knoten 1.</span><span class="sxs-lookup"><span data-stu-id="1be1d-126">Resolve the problem with Node 1.</span></span>  
  
3.  <span data-ttu-id="1be1d-127">Stellen Sie sicher, dass alle Knoten online sind und der WSFC-Dienst aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1be1d-127">Ensure that all nodes are online and the WSFC service is working.</span></span>  
  
4.  <span data-ttu-id="1be1d-128">Führen Sie für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ein Failover zum wiederhergestellten Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="1be1d-128">Fail over [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the recovered node.</span></span>  
  
  
