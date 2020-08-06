---
title: Starten und Beenden eines Replikations-Agents (SQL Server Management Studio) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], stopping
- agents [SQL Server replication], starting
ms.assetid: 97977c4a-8c7c-4a22-9480-69aa812bd1e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40e329e0f04e8a54a2d5a40c30aff418da2cd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609150"
---
# <a name="start-and-stop-a-replication-agent-sql-server-management-studio"></a><span data-ttu-id="c9e4b-102">Starten und Beenden eines Replikations-Agents (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c9e4b-102">Start and Stop a Replication Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c9e4b-103">Starten oder beenden Sie Agents in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder im Replikationsmonitor über den Ordner **Aufträge** oder den Ordner **Replikation**.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-103">Start and stop agents from the **Jobs** folder and the **Replication** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from Replication Monitor.</span></span> <span data-ttu-id="c9e4b-104">Starten oder beenden Sie die folgenden Agents und Aufträge:</span><span class="sxs-lookup"><span data-stu-id="c9e4b-104">Start and stop the following agents and jobs:</span></span>  
  
-   <span data-ttu-id="c9e4b-105">Momentaufnahme-Agent, der von allen Veröffentlichungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-105">The Snapshot Agent, which is used by all publications.</span></span>  
  
-   <span data-ttu-id="c9e4b-106">Protokolllese-Agent, der von allen Transaktionsveröffentlichungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-106">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="c9e4b-107">Warteschlangenlese-Agent, der von Transaktionsveröffentlichungen verwendet wird, die für Abonnements mit verzögertem Update über eine Warteschlange aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-107">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="c9e4b-108">Verteilungs-Agent, der Abonnements für Transaktions- und Momentaufnahmeveröffentlichungen synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-108">The Distribution Agent, which synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="c9e4b-109">Merge-Agent, der Abonnements für Mergeveröffentlichungen synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-109">The Merge Agent, which synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="c9e4b-110">Aufträge zur Replikationswartung.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-110">Replication maintenance jobs.</span></span>  
  
 <span data-ttu-id="c9e4b-111">Weitere Informationen zum Starten des Merge-Agents und des Verteilungs-Agents finden Sie unter [Synchronisieren eines Pushabonnements](../synchronize-a-push-subscription.md) und [Synchronisieren eines Pullabonnements](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c9e4b-111">For more information about starting the Merge Agent and the Distribution Agent, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span> <span data-ttu-id="c9e4b-112">Weitere Informationen zu Wartungsaufträgen finden Sie unter [Ausführen von Aufträgen zur Replikationswartung &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="c9e4b-112">For more information about maintenance jobs, see [Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span></span>  
  
 <span data-ttu-id="c9e4b-113">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c9e4b-113">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-or-log-reader-agent-from-management-studio"></a><span data-ttu-id="c9e4b-114">So starten oder beenden Sie einen Momentaufnahme-Agent oder Protokolllese-Agent in Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9e4b-114">To start and stop a Snapshot Agent or Log Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="c9e4b-115">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten und den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="c9e4b-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node and the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="c9e4b-116">Erweitern Sie den Ordner **Lokale Veröffentlichungen** , und klicken Sie mit der rechten Maustaste auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-116">Expand the **Local Publications** folder, and then right-click a publication.</span></span>  
  
3.  <span data-ttu-id="c9e4b-117">Klicken Sie auf **Status des Momentaufnahme-Agents anzeigen** oder **Status des Protokolllese-Agents anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-117">Click **View Snapshot Agent Status** or **View Log Reader Agent Status**.</span></span>  
  
4.  <span data-ttu-id="c9e4b-118">Klicken Sie auf **Starten** oder **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-118">Click **Start** or **Stop**.</span></span>  
  
### <a name="to-start-and-stop-a-queue-reader-agent-from-management-studio"></a><span data-ttu-id="c9e4b-119">So starten oder beenden Sie einen Warteschlangenlese-Agent in Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9e4b-119">To start and stop a Queue Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="c9e4b-120">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verteiler her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-120">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="c9e4b-121">Erweitern Sie den Ordner **SQL Server-Agent** und anschließend den Ordner **Aufträge** .</span><span class="sxs-lookup"><span data-stu-id="c9e4b-121">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="c9e4b-122">Klicken Sie mit der rechten Maustaste auf den Auftrag für den Agent, und klicken Sie dann auf **Auftrag starten** oder **Auftrag beenden**.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-122">Right-click the job for the agent, and then click **Start Job** or **Stop Job**.</span></span> <span data-ttu-id="c9e4b-123">Der Name des Auftrags für den Warteschlangenlese-Agent hat das Format **[\<Distributor>].\<integer>** .</span><span class="sxs-lookup"><span data-stu-id="c9e4b-123">The name of the job for the Queue Reader Agent is in the form **[\<Distributor>].\<integer>**.</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-log-reader-agent-or-queue-reader-agent-from-replication-monitor"></a><span data-ttu-id="c9e4b-124">So starten oder beenden Sie einen Momentaufnahme-Agent, Protokolllese-Agent oder Warteschlangenlese-Agent im Replikations-Monitor</span><span class="sxs-lookup"><span data-stu-id="c9e4b-124">To start and stop a Snapshot Agent, Log Reader Agent, or Queue Reader Agent from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="c9e4b-125">Erweitern Sie im linken Bereich eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-125">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="c9e4b-126">Klicken Sie auf die Registerkarte **Agents** .</span><span class="sxs-lookup"><span data-stu-id="c9e4b-126">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="c9e4b-127">Klicken Sie mit der rechten Maustaste auf einen Agent, und klicken Sie dann auf **Agent starten** oder **Agent beenden**.</span><span class="sxs-lookup"><span data-stu-id="c9e4b-127">Right-click an agent, and then click **Start Agent** or **Stop Agent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e4b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9e4b-128">See Also</span></span>  
 <span data-ttu-id="c9e4b-129">[Überwachen der Replikation](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="c9e4b-129">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 <span data-ttu-id="c9e4b-130">[Ausführbare Konzepte für den Replikations-Agent](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c9e4b-130">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="c9e4b-131">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="c9e4b-131">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
