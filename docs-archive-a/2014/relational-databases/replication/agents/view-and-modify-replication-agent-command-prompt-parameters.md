---
title: Anzeigen und Ändern von Befehlszeilen Parametern des Replikations-Agents (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], command prompt parameters
ms.assetid: 45f2e781-c21d-4b44-8992-89f60fb3d022
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 752f674c21bb66c7b64e399e30e4917512431195
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609149"
---
# <a name="view-and-modify-replication-agent-command-prompt-parameters-sql-server-management-studio"></a><span data-ttu-id="8c8f7-102">Anzeigen und Ändern von Befehlszeilenparametern des Replikations-Agents (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8c8f7-102">View and Modify Replication Agent Command Prompt Parameters (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8c8f7-103">Replikations-Agents sind ausführbare Dateien, die Befehlszeilenparameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-103">Replication agents are executables that accept command line parameters.</span></span> <span data-ttu-id="8c8f7-104">Standardmäßig werden Agents unter Auftragsschritten des [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Agents ausgeführt. Deshalb können diese Parameter im Dialogfeld **Auftragseigenschaften – \<Job>** angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-104">By default, agents run under [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job steps, so these parameters can be viewed and modified using the **Job Properties - \<Job>** dialog box.</span></span> <span data-ttu-id="8c8f7-105">Dieses Dialogfeld steht über den Ordner **Aufträge** in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] sowie über die Registerkarte **Agents** im Replikationsmonitor zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-105">This dialog box is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="8c8f7-106">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8c8f7-106">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c8f7-107">Die Änderungen der Agentparameter treten in Kraft, wenn der Agent das nächste Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-107">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="8c8f7-108">Wenn der Agent ständig ausgeführt wird, müssen Sie den Agent beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-108">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
 <span data-ttu-id="8c8f7-109">Parameter können zwar direkt geändert werden, aber es ist eher üblich, sie über ein Agentprofil zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-109">Although parameters can be modified directly, it is more common to modify them through an agent profile.</span></span> <span data-ttu-id="8c8f7-110">Weitere Informationen finden Sie unter [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8c8f7-110">For more information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="8c8f7-111">Wenn Sie über den Ordner **Aufträge** auf Agentaufträge zugreifen, ermitteln Sie mithilfe der folgenden Tabelle den Namen des Agentauftrags und die jeweils für den Agent verfügbaren Parameter.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-111">If you access agent jobs from the **Jobs** folder, use the following table to determine the agent job name and the parameters available for each agent.</span></span>  
  
|<span data-ttu-id="8c8f7-112">Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-112">Agent</span></span>|<span data-ttu-id="8c8f7-113">Auftragsname</span><span class="sxs-lookup"><span data-stu-id="8c8f7-113">Job name</span></span>|<span data-ttu-id="8c8f7-114">Eine Liste der Parameter finden Sie unter...</span><span class="sxs-lookup"><span data-stu-id="8c8f7-114">For a list of parameters, see...</span></span>|  
|-----------|--------------|------------------------------------|  
|<span data-ttu-id="8c8f7-115">Momentaufnahme-Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-115">Snapshot Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<integer>**|[<span data-ttu-id="8c8f7-116">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-116">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="8c8f7-117">Momentaufnahme-Agent für eine Mergeveröffentlichungspartition</span><span class="sxs-lookup"><span data-stu-id="8c8f7-117">Snapshot Agent for a merge publication partition</span></span>|<span data-ttu-id="8c8f7-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span><span class="sxs-lookup"><span data-stu-id="8c8f7-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span></span>|[<span data-ttu-id="8c8f7-119">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-119">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="8c8f7-120">Protokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-120">Log Reader Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<integer>**|[<span data-ttu-id="8c8f7-121">Replikationsprotokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-121">Replication Log Reader Agent</span></span>](replication-log-reader-agent.md)|  
|<span data-ttu-id="8c8f7-122">Merge-Agent für Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="8c8f7-122">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|[<span data-ttu-id="8c8f7-123">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-123">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="8c8f7-124">Merge-Agent für Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="8c8f7-124">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="8c8f7-125">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-125">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="8c8f7-126">Verteilungs-Agent für Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="8c8f7-126">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="8c8f7-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8c8f7-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|[<span data-ttu-id="8c8f7-128">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-128">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="8c8f7-129">Verteilungs-Agent für Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="8c8f7-129">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="8c8f7-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8c8f7-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|[<span data-ttu-id="8c8f7-131">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-131">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="8c8f7-132">Verteilungs-Agent für Pushabonnements für Nicht-SQL Server-Abonnenten</span><span class="sxs-lookup"><span data-stu-id="8c8f7-132">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="8c8f7-133">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-133">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="8c8f7-134">Warteschlangenlese-Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-134">Queue Reader Agent</span></span>|<span data-ttu-id="8c8f7-135">**[\<Distributor>].\<integer>**</span><span class="sxs-lookup"><span data-stu-id="8c8f7-135">**[\<Distributor>].\<integer>**</span></span>|[<span data-ttu-id="8c8f7-136">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="8c8f7-136">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)|  
  
 <span data-ttu-id="8c8f7-137"><sup>1</sup> Für Pushabonnements für Oracle-Veröffentlichungen lautet der Name \*\*\<Publisher>-\<Publisher**> und nicht **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="8c8f7-137"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="8c8f7-138"><sup>2</sup> Für Pullabonnements für Oracle-Veröffentlichungen lautet der Name \*\*\<Publisher>-\<DistributionDatabase**> und nicht **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="8c8f7-138"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
### <a name="to-view-and-modify-replication-agent-command-line-parameters-from-management-studio"></a><span data-ttu-id="8c8f7-139">So zeigen Sie Befehlszeilenparameter des Replikations-Agents in SQL Server Management Studio an und ändern Sie die Parameter</span><span class="sxs-lookup"><span data-stu-id="8c8f7-139">To view and modify replication agent command line parameters from Management Studio</span></span>  
  
1.  <span data-ttu-id="8c8f7-140">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem entsprechenden Computer her, und erweitern Sie dann den Serverknoten:</span><span class="sxs-lookup"><span data-stu-id="8c8f7-140">Connect to the appropriate computer in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="8c8f7-141">Beim Verteilungs-Agent und Merge-Agent für Pullabonnements stellen Sie eine Verbindung mit dem Abonnenten her.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-141">For the Distribution Agent and Merge Agent for pull subscriptions, connect to the Subscriber.</span></span>  
  
    -   <span data-ttu-id="8c8f7-142">Bei allen anderen Agents stellen Sie eine Verbindung mit dem Verteiler her.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-142">For all other agents, connect to the Distributor.</span></span>  
  
2.  <span data-ttu-id="8c8f7-143">Erweitern Sie den Ordner **SQL Server-Agent** und anschließend den Ordner **Aufträge** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-143">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="8c8f7-144">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-144">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8c8f7-145">Wählen Sie im Dialogfeld **Auftragseigenschaften – \<Job>** auf der Seite **Schritte** den Schritt **Agent ausführen** aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-145">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="8c8f7-146">Bearbeiten Sie im Dialogfeld **Auftragsschritt-Eigenschaften - Führt den Agent aus** das Feld **Befehl** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-146">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="8c8f7-147">Klicken Sie in beiden Dialogfeldern auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-147">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-distribution-agent-and-merge-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="8c8f7-148">So zeigen Sie Befehlszeilenparameter des Verteilungs- und des Merge-Agents in Replikationsmonitor an und ändern Sie die Parameter</span><span class="sxs-lookup"><span data-stu-id="8c8f7-148">To view and modify Distribution Agent and Merge Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="8c8f7-149">Erweitern Sie im linken Bereich des Replikationsmonitors eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-149">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="8c8f7-150">Klicken Sie auf die Registerkarte **Alle Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-150">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="8c8f7-151">Klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-151">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="8c8f7-152">Klicken Sie im Fenster \*\* \< SubscriptionName> Abonnement\*\* auf **Aktion**, und klicken Sie dann auf \*\* \<AgentName> Auftrags Eigenschaften\*\*.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-152">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="8c8f7-153">Wählen Sie im Dialogfeld **Auftragseigenschaften – \<Job>** auf der Seite **Schritte** den Schritt **Agent ausführen** aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-153">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="8c8f7-154">Bearbeiten Sie im Dialogfeld **Auftragsschritt-Eigenschaften - Führt den Agent aus** das Feld **Befehl** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-154">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
7.  <span data-ttu-id="8c8f7-155">Klicken Sie in beiden Dialogfeldern auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-155">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-snapshot-agent-log-reader-agent-and-queue-reader-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="8c8f7-156">So zeigen Sie Befehlszeilenparameter des Momentaufnahme-, des Protolllese- und des Warteschlangenlese-Agents im Replikationsmonitor an und ändern Sie die Parameter</span><span class="sxs-lookup"><span data-stu-id="8c8f7-156">To view and modify Snapshot Agent, Log Reader Agent, and Queue Reader Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="8c8f7-157">Erweitern Sie im linken Bereich des Replikationsmonitors eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-157">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="8c8f7-158">Klicken Sie auf die Registerkarte **Agents** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-158">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="8c8f7-159">Klicken Sie mit der rechten Maustaste auf einen Agent im Raster, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-159">Right-click an agent in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8c8f7-160">Wählen Sie im Dialogfeld **Auftragseigenschaften – \<Job>** auf der Seite **Schritte** den Schritt **Agent ausführen** aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8c8f7-160">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="8c8f7-161">Bearbeiten Sie im Dialogfeld **Auftragsschritt-Eigenschaften - Führt den Agent aus** das Feld **Befehl** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-161">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="8c8f7-162">Klicken Sie in beiden Dialogfeldern auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="8c8f7-162">Click **OK** on both dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8f7-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c8f7-163">See Also</span></span>  
 <span data-ttu-id="8c8f7-164">[Verwaltung des Replikations-Agents](replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="8c8f7-164">[Replication Agent Administration](replication-agent-administration.md) </span></span>  
 <span data-ttu-id="8c8f7-165">[Ausführbare Konzepte für den Replikations-Agent](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="8c8f7-165">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="8c8f7-166">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="8c8f7-166">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
