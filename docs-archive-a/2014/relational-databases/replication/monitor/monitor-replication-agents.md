---
title: Überwachen der Replikations-Agents | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615937"
---
# <a name="monitor-replication-agents"></a><span data-ttu-id="9b64e-102">Überwachen der Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="9b64e-102">Monitor Replication Agents</span></span>
  <span data-ttu-id="9b64e-103">Der Replikationsmonitor von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] bietet einen systemischen Überblick über die Replikationsaktivität und erleichtert gleichzeitig die Suche nach Informationen zu einem bestimmten Agent.</span><span class="sxs-lookup"><span data-stu-id="9b64e-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor provides a systemic view of replication activity, but also makes it straightforward to find information on a specific agent.</span></span> <span data-ttu-id="9b64e-104">Die folgende Liste enthält alle Agents, die Registerkarten im Replikationsmonitor, auf denen die Agents zu finden sind, und einen Verweis darauf, wo Sie Informationen zum Zugreifen auf die jeweilige Registerkarte finden:</span><span class="sxs-lookup"><span data-stu-id="9b64e-104">The following list includes each agent, the tabs in the Replication Monitor on which it can be found, and a link to a topic that explains how to access these tabs:</span></span>  
  
-   <span data-ttu-id="9b64e-105">Die folgenden Agents sind Veröffentlichungen im Replikationsmonitor zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="9b64e-105">The following agents are associated with publications in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="9b64e-106">Momentaufnahme-Agent</span><span class="sxs-lookup"><span data-stu-id="9b64e-106">Snapshot Agent</span></span>  
  
    -   <span data-ttu-id="9b64e-107">Protokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="9b64e-107">Log Reader Agent</span></span>  
  
    -   <span data-ttu-id="9b64e-108">Warteschlangenlese-Agent</span><span class="sxs-lookup"><span data-stu-id="9b64e-108">Queue Reader Agent</span></span>  
  
     <span data-ttu-id="9b64e-109">Auf die Informationen und Aufgaben zu diesen Agents können Sie über die folgenden Registerkarten zugreifen: **Agents** (verfügbar für jeden Verleger und jede Veröffentlichung) und **Warnungen** (verfügbar für jede Veröffentlichung).</span><span class="sxs-lookup"><span data-stu-id="9b64e-109">Access information and tasks associated with these agents through the following tabs: **Agents** (available for each Publisher and publication) and **Warnings** (available for each publication).</span></span> <span data-ttu-id="9b64e-110">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9b64e-110">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="9b64e-111">Die folgenden Agents sind Abonnements im Replikationsmonitor zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="9b64e-111">The following agents are associated with subscriptions in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="9b64e-112">Verteilungs-Agent</span><span class="sxs-lookup"><span data-stu-id="9b64e-112">Distribution Agent</span></span>  
  
    -   <span data-ttu-id="9b64e-113">Merge-Agent</span><span class="sxs-lookup"><span data-stu-id="9b64e-113">Merge Agent</span></span>  
  
     <span data-ttu-id="9b64e-114">Auf die Informationen und Aufgaben zu diesen Agents können Sie über die folgenden Registerkarten zugreifen: **Überwachungsliste für Abonnements** (verfügbar für jeden Verleger) oder **Alle Abonnements** (verfügbar für jede Veröffentlichung).</span><span class="sxs-lookup"><span data-stu-id="9b64e-114">Access information and tasks associated with these agents through the following tabs: **Subscription Watch List** (available for each Publisher) or the **All Subscriptions** tab (available for each publication).</span></span> <span data-ttu-id="9b64e-115">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9b64e-115">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a><span data-ttu-id="9b64e-116">Überwachen der Replikations-Agents mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b64e-116">Using SQL Server Management Studio to Monitor Replication Agents</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="9b64e-117">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] stellt die folgenden Dialogfelder zum Überwachen von Replikations-Agents bereit:</span><span class="sxs-lookup"><span data-stu-id="9b64e-117">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] provides the following dialog boxes for monitoring replication agents:</span></span>  
  
-   <span data-ttu-id="9b64e-118">**Status des Momentaufnahme-Agents anzeigen** (bei allen Veröffentlichungen)</span><span class="sxs-lookup"><span data-stu-id="9b64e-118">**View Snapshot Agent Status** (for all publications)</span></span>  
  
-   <span data-ttu-id="9b64e-119">**Status des Protokolllese-Agents anzeigen** (bei allen Transaktionsveröffentlichungen)</span><span class="sxs-lookup"><span data-stu-id="9b64e-119">**View Log Reader Agent Status** (for all transactional publications)</span></span>  
  
-   <span data-ttu-id="9b64e-120">**Synchronisierungsstatus anzeigen** (bei allen Abonnements; von diesem Dialogfeld aus können Sie auf den Verteilungs-Agent und den Merge-Agent zugreifen)</span><span class="sxs-lookup"><span data-stu-id="9b64e-120">**View Synchronization Status** (for all subscriptions; this dialog box allows access to the Distribution Agent and the Merge Agent)</span></span>  
  
 <span data-ttu-id="9b64e-121">Der Replikationsmonitor stellt darüber hinaus zusätzliche Informationen zu den einzelnen Agents bereit und bietet außerdem die Möglichkeit der Überwachung des Warteschlangenlese-Agents, sofern dieser verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b64e-121">Replication Monitor provides additional information about each agent and provides monitoring for the Queue Reader Agent, if it is used.</span></span> <span data-ttu-id="9b64e-122">Weitere Informationen finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9b64e-122">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a><span data-ttu-id="9b64e-123">So überwachen Sie den Momentaufnahme-Agent und den Protokokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="9b64e-123">To monitor the Snapshot Agent and Log Reader Agent</span></span>  
  
1.  <span data-ttu-id="9b64e-124">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="9b64e-124">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9b64e-125">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="9b64e-125">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="9b64e-126">Klicken Sie mit der rechten Maustaste auf eine Veröffentlichung, und klicken Sie dann auf **Status des Protokolllese-Agents anzeigen** bzw. **Status des Momentaufnahme-Agents anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9b64e-126">Right-click a publication, and then click **View Log Reader Agent Status** or **View Snapshot Agent Status**.</span></span>  
  
4.  <span data-ttu-id="9b64e-127">Führen Sie im Dialogfeld **Status des Protokolllese-Agents anzeigen** bzw. **Status des Momentaufnahme-Agents anzeigen** einen oder mehrere der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9b64e-127">In the **View Log Reader Agent Status** or **View Snapshot Agent Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="9b64e-128">Zeigen Sie den Agentstatus an.</span><span class="sxs-lookup"><span data-stu-id="9b64e-128">View agent status.</span></span>  
  
    -   <span data-ttu-id="9b64e-129">Starten oder beenden Sie den Agent bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="9b64e-129">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="9b64e-130">Klicken Sie auf **Überwachen** , um den **Replikationsmonitor**zu starten.</span><span class="sxs-lookup"><span data-stu-id="9b64e-130">Click **Monitor** to launch **Replication Monitor**.</span></span>  
  
5.  <span data-ttu-id="9b64e-131">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9b64e-131">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a><span data-ttu-id="9b64e-132">So überwachen Sie den Verteilungs-Agent und den Merge-Agent (vom Verleger aus)</span><span class="sxs-lookup"><span data-stu-id="9b64e-132">To monitor the Distribution Agent and Merge Agent (from the Publisher)</span></span>  
  
1.  <span data-ttu-id="9b64e-133">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="9b64e-133">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9b64e-134">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="9b64e-134">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="9b64e-135">Erweitern Sie die Veröffentlichung für das Abonnement, das überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b64e-135">Expand the publication for the subscription you want to monitor.</span></span>  
  
4.  <span data-ttu-id="9b64e-136">Klicken Sie mit der rechten Maustaste auf das Abonnement, und klicken Sie dann auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9b64e-136">Right-click the subscription, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="9b64e-137">Führen Sie im Dialogfeld **Synchronisierungsstatus anzeigen** einen oder mehrere der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9b64e-137">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="9b64e-138">Zeigen Sie den Agentstatus an.</span><span class="sxs-lookup"><span data-stu-id="9b64e-138">View agent status.</span></span>  
  
    -   <span data-ttu-id="9b64e-139">Starten oder beenden Sie den Agent bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="9b64e-139">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="9b64e-140">Klicken Sie bei Pushabonnements auf **Überwachen** , um den **Replikationsmonitor**zu starten.</span><span class="sxs-lookup"><span data-stu-id="9b64e-140">For push subscriptions, click **Monitor** to launch **Replication Monitor**.</span></span>  
  
    -   <span data-ttu-id="9b64e-141">Klicken Sie bei Pullabonnements auf **Auftragsverlauf anzeigen** , um den **Protokolldatei-Viewer**zu starten, in dem das Ergebnis aus dem Agentprotokoll angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9b64e-141">For pull subscriptions, click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
6.  <span data-ttu-id="9b64e-142">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9b64e-142">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a><span data-ttu-id="9b64e-143">So überwachen Sie den Verteilungs-Agent und den Merge-Agent (vom Abonnenten aus)</span><span class="sxs-lookup"><span data-stu-id="9b64e-143">To monitor the Distribution Agent and Merge Agent (from the Subscriber)</span></span>  
  
1.  <span data-ttu-id="9b64e-144">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="9b64e-144">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9b64e-145">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="9b64e-145">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="9b64e-146">Klicken Sie mit der rechten Maustaste auf das zu überwachende Abonnement, und klicken Sie dann auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9b64e-146">Right-click the subscription you want to monitor, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="9b64e-147">Führen Sie im Dialogfeld **Synchronisierungsstatus anzeigen** einen oder mehrere der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9b64e-147">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="9b64e-148">Zeigen Sie den Agentstatus an.</span><span class="sxs-lookup"><span data-stu-id="9b64e-148">View agent status.</span></span>  
  
    -   <span data-ttu-id="9b64e-149">Starten oder beenden Sie den Agent bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="9b64e-149">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="9b64e-150">Klicken Sie auf **Auftragsverlauf anzeigen** , um den **Protokolldatei-Viewer**zu starten, in dem das Ergebnis aus dem Agentprotokoll angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9b64e-150">Click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
5.  <span data-ttu-id="9b64e-151">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9b64e-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b64e-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b64e-152">See Also</span></span>  
 <span data-ttu-id="9b64e-153">[Überwachen der Replikation](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9b64e-153">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="9b64e-154">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="9b64e-154">Replication Agents Overview</span></span>](../agents/replication-agents-overview.md)  
  
  
