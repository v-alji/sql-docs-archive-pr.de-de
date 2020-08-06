---
title: Synchronisieren eines Pullabonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- pull subscriptions [SQL Server replication], synchronizing
- synchronization [SQL Server replication], pull subscriptions
- subscriptions [SQL Server replication], pull
ms.assetid: 3ca24b23-fdc3-408e-8208-a2ace48fc8e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 826622cd17862c0535e60c01baab756af2b2996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618646"
---
# <a name="synchronize-a-pull-subscription"></a><span data-ttu-id="36d9b-102">Synchronisieren eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="36d9b-102">Synchronize a Pull Subscription</span></span>
  <span data-ttu-id="36d9b-103">In diesem Thema wird beschrieben, wie ein Pullabonnement in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [Replikations-Agents](agents/replication-agents-overview.md)oder Replikationsverwaltungsobjekten (RMO) synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-103">This topic describes how to synchronize a pull subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="36d9b-104">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="36d9b-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="36d9b-105">Abonnements werden durch den Verteilungs-Agent (für Momentaufnahme- und Transaktionsveröffentlichungen) oder durch den Merge-Agent (für Mergeveröffentlichungen) synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="36d9b-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="36d9b-106">Agents können kontinuierlich, bei Bedarf oder nach einem Zeitplan ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="36d9b-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="36d9b-107">Weitere Informationen zum Angeben von Synchronisierungszeitplänen finden Sie unter [Angeben von Synchronisierungszeitplänen](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="36d9b-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="36d9b-108">Eine bedarfsgesteuerte Synchronisierung eines Abonnements kann im Ordner **Lokale Abonnements** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="36d9b-108">Synchronize a subscription on demand from the **Local Subscriptions** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-on-demand-in-management-studio"></a><span data-ttu-id="36d9b-109">So führen Sie die bedarfsgesteuerte Synchronisierung eines Pullabonnements in Management Studio aus</span><span class="sxs-lookup"><span data-stu-id="36d9b-109">To synchronize a pull subscription on demand in Management Studio</span></span>  
  
1.  <span data-ttu-id="36d9b-110">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="36d9b-110">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="36d9b-111">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="36d9b-111">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="36d9b-112">Klicken Sie mit der rechten Maustaste auf das zu synchronisierende Abonnement, und klicken Sie dann auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="36d9b-112">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="36d9b-113">Klicken Sie im Dialogfeld **Synchronisierungsstatus anzeigen - \<Subscriber>:\<SubscriptionDatabase>** auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="36d9b-113">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="36d9b-114">Nach Abschluss der Synchronisierung wird die Meldung **Synchronisierung abgeschlossen** eingeblendet.</span><span class="sxs-lookup"><span data-stu-id="36d9b-114">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
5.  <span data-ttu-id="36d9b-115">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="36d9b-115">Click **Close**.</span></span>  
  
##  <a name="replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="36d9b-116">Replication Agents</span><span class="sxs-lookup"><span data-stu-id="36d9b-116">Replication Agents</span></span>  
 <span data-ttu-id="36d9b-117">Pullabonnements können programmgesteuert oder nach Bedarf synchronisiert werden, indem die entsprechende ausführbare Datei für den Replikations-Agent an der Eingabeaufforderung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-117">Pull subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="36d9b-118">Welche ausführbare Datei für den Replikations-Agent aufgerufen wird, hängt vom Typ der Veröffentlichung ab, zu der das Pullabonnement gehört.</span><span class="sxs-lookup"><span data-stu-id="36d9b-118">The replication agent executable file that is invoked will depend on the type of publication to which the pull subscription belongs.</span></span> <span data-ttu-id="36d9b-119">Weitere Informationen finden Sie unter [Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="36d9b-119">For more information, see [Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36d9b-120">Replikations-Agents stellen die Verbindung zum lokalen Server anhand der Anmeldeinformationen für die Windows-Authentifizierung des Benutzers her, der den Agenten von der Eingabeaufforderung aus aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="36d9b-120">Replication agents connect to the local server using the Windows Authentication credentials of the user who started the agent from the command prompt.</span></span> <span data-ttu-id="36d9b-121">Diese Windows-Anmeldeinformationen werden auch verwendet, wenn mithilfe der integrierten Windows-Authentifizierung eine Verbindung zu Remoteservern hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-121">These Windows credentials are also used when connecting to remote servers using Windows Integrated Authentication.</span></span>  
  
#### <a name="to-start-the-distribution-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="36d9b-122">So starten Sie den Verteilungs-Agent von der Eingabeaufforderung oder einer Batchdatei aus</span><span class="sxs-lookup"><span data-stu-id="36d9b-122">To start the distribution agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="36d9b-123">Starten Sie den [Replikationsverteilungs-Agent](agents/replication-distribution-agent.md) von der Eingabeaufforderung oder einer Batchdatei aus, indem Sie **distrib.exe**ausführen. Geben Sie dazu die folgenden Befehlszeilenargumente an:</span><span class="sxs-lookup"><span data-stu-id="36d9b-123">From the command prompt or in a batch file, start the [Replication Distribution Agent](agents/replication-distribution-agent.md) by running **distrib.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="36d9b-124">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="36d9b-124">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="36d9b-125">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="36d9b-125">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="36d9b-126">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="36d9b-126">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="36d9b-127">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-127">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="36d9b-128">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="36d9b-128">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="36d9b-129">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="36d9b-129">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="36d9b-130">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-130">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="36d9b-131">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-131">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="36d9b-132">Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwenden, müssen Sie zudem die folgenden Argumente angeben:</span><span class="sxs-lookup"><span data-stu-id="36d9b-132">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="36d9b-133">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="36d9b-133">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="36d9b-134">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="36d9b-134">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="36d9b-135">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="36d9b-135">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="36d9b-136">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="36d9b-136">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="36d9b-137">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="36d9b-137">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="36d9b-138">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="36d9b-138">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="36d9b-139">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="36d9b-139">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="36d9b-140">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="36d9b-140">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="36d9b-141">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="36d9b-141">**-SubscriberSecurityMode** = **0**</span></span>  
  
#### <a name="to-start-the-merge-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="36d9b-142">So starten Sie den Merge-Agent von der Eingabeaufforderung oder einer Batchdatei aus</span><span class="sxs-lookup"><span data-stu-id="36d9b-142">To start the merge agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="36d9b-143">Starten Sie den [Replikationsmerge-Agent](agents/replication-merge-agent.md) von der Eingabeaufforderung oder einer Batchdatei aus, indem Sie **replmerg.exe**ausführen. Geben Sie dazu die folgenden Befehlszeilenargumente an:</span><span class="sxs-lookup"><span data-stu-id="36d9b-143">From the command prompt or in a batch file, start the [Replication Merge Agent](agents/replication-merge-agent.md) by running **replmerg.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="36d9b-144">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="36d9b-144">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="36d9b-145">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="36d9b-145">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="36d9b-146">**-PublisherSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-146">**-PublisherSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="36d9b-147">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="36d9b-147">**-Publication**</span></span>  
  
    -   <span data-ttu-id="36d9b-148">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="36d9b-148">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="36d9b-149">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-149">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="36d9b-150">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="36d9b-150">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="36d9b-151">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-151">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="36d9b-152">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="36d9b-152">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="36d9b-153">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="36d9b-153">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="36d9b-154">Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwenden, müssen Sie zudem die folgenden Argumente angeben:</span><span class="sxs-lookup"><span data-stu-id="36d9b-154">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="36d9b-155">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="36d9b-155">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="36d9b-156">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="36d9b-156">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="36d9b-157">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="36d9b-157">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="36d9b-158">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="36d9b-158">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="36d9b-159">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="36d9b-159">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="36d9b-160">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="36d9b-160">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="36d9b-161">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="36d9b-161">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="36d9b-162">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="36d9b-162">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="36d9b-163">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="36d9b-163">**-SubscriberSecurityMode** = **0**</span></span>  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="36d9b-164">Beispiele (Replikations-Agents)</span><span class="sxs-lookup"><span data-stu-id="36d9b-164">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="36d9b-165">Im folgenden Beispiel wird der Verteilungs-Agent gestartet, um ein Pullabonnement zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="36d9b-165">The following example starts the Distribution Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="36d9b-166">Alle Verbindungen werden mithilfe der Windows-Authentifizierung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="36d9b-166">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_synctranpullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/synctranpullsub_10.bat)]  
  
 <span data-ttu-id="36d9b-167">Im folgenden Beispiel wird der Merge-Agent gestartet, um ein Pullabonnement zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="36d9b-167">The following example starts the Merge Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="36d9b-168">Alle Verbindungen werden mithilfe der Windows-Authentifizierung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="36d9b-168">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_syncmergepullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/syncmergepullsub_10.bat)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="36d9b-169">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="36d9b-169">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="36d9b-170">Sie können Pullabonnements mit Replikationsverwaltungsobjekten (RMO) und dem Zugriff von verwaltetem Code auf Funktionen des Replikations-Agent programmgesteuert synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="36d9b-170">You can synchronize pull subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="36d9b-171">Die Klassen für die Synchronisierung eines Pullabonnements richten sich nach dem Typ der Veröffentlichung, zu der das Abonnement gehört.</span><span class="sxs-lookup"><span data-stu-id="36d9b-171">The classes you use to synchronize a pull subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36d9b-172">Starten Sie den Agent asynchron, wenn Sie eine Synchronisierung starten möchten, die autonom ausgeführt wird, ohne sich auf die Anwendung auszuwirken.</span><span class="sxs-lookup"><span data-stu-id="36d9b-172">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="36d9b-173">Wenn Sie während der Synchronisierung das Ergebnis der Synchronisierung überwachen und Rückrufe vom Agent empfangen möchten (z. B. über eine Statusanzeige), müssen Sie den Agent synchron starten.</span><span class="sxs-lookup"><span data-stu-id="36d9b-173">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="36d9b-174">Für [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] -Abonnenten müssen Sie den Agent synchron starten.</span><span class="sxs-lookup"><span data-stu-id="36d9b-174">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="36d9b-175">So synchronisieren Sie ein Pullabonnement für eine Momentaufnahme- oder Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="36d9b-175">To synchronize a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="36d9b-176">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="36d9b-176">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="36d9b-177">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransPullSubscription> -Klasse, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="36d9b-177">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="36d9b-178">Den Namen der Abonnementdatenbank für <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-178">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-179">Den Namen der Veröffentlichung, zu der das Abonnement gehört, für <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-179">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-180">Den Namen der Veröffentlichungsdatenbank für <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-180">The name of the publication database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-181">Den Namen des Verlegers für <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-181">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-182">Die in Schritt 1 erstellte Verbindung für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-182">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="36d9b-183">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die restlichen Abonnementeigenschaften abzurufen.</span><span class="sxs-lookup"><span data-stu-id="36d9b-183">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="36d9b-184">Überprüfen Sie, ob das Abonnement vorhanden ist, wenn diese Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="36d9b-184">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="36d9b-185">Starten Sie den Verteilungs-Agent auf eine der folgenden Arten auf dem Abonnenten:</span><span class="sxs-lookup"><span data-stu-id="36d9b-185">Start the Distribution Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="36d9b-186">Rufen Sie die <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> -Methode für die <xref:Microsoft.SqlServer.Replication.TransPullSubscription> -Instanz aus Schritt 2 auf.</span><span class="sxs-lookup"><span data-stu-id="36d9b-186">Call the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransPullSubscription> from step 2.</span></span> <span data-ttu-id="36d9b-187">Diese Methode startet den Verteilungs-Agent asynchron, und die Steuerung wird sofort an die Anwendung zurückgegeben, während der Agentauftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-187">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="36d9b-188">Sie können diese Methode für [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)]-Abonnenten nicht aufrufen. Diese Methode kann ebenfalls nicht aufgerufen werden, wenn das Abonnement mit dem Wert `false` für <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (dem Standard) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="36d9b-188">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="36d9b-189">Rufen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> -Klasse von der <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> -Eigenschaft ab, und rufen Sie die <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="36d9b-189">Get an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="36d9b-190">Diese Methode startet den Agent synchron, und die Steuerung bleibt beim ausgeführten Agentauftrag.</span><span class="sxs-lookup"><span data-stu-id="36d9b-190">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="36d9b-191">Während der synchronen Ausführung können Sie das <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> -Ereignis verarbeiten, während der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-191">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="36d9b-192">Wenn Sie beim Erstellen des Pullabonnements `false` den Wert für <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (die Standardeinstellung) angegeben haben, müssen Sie auch <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A> und optional sowie angeben, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> da die Metadaten des Agentauftrags, die für das Abonnement verfügbar sind, in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql)nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="36d9b-192">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A>, and optionally <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> and <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="36d9b-193">So synchronisieren Sie ein Pullabonnement mit einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="36d9b-193">To synchronize a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="36d9b-194">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="36d9b-194">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="36d9b-195">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergePullSubscription> -Klasse, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="36d9b-195">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="36d9b-196">Den Namen der Abonnementdatenbank für <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-196">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-197">Den Namen der Veröffentlichung, zu der das Abonnement gehört, für <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-197">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-198">Den Namen der veröffentlichten Datenbank für <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-198">The name of the published database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-199">Den Namen des Verlegers für <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-199">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="36d9b-200">Die in Schritt 1 erstellte Verbindung für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="36d9b-200">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="36d9b-201">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die restlichen Abonnementeigenschaften abzurufen.</span><span class="sxs-lookup"><span data-stu-id="36d9b-201">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="36d9b-202">Überprüfen Sie, ob das Abonnement vorhanden ist, wenn diese Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="36d9b-202">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="36d9b-203">Starten Sie den Merge-Agent auf eine der folgenden Arten auf dem Abonnenten:</span><span class="sxs-lookup"><span data-stu-id="36d9b-203">Start the Merge Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="36d9b-204">Rufen Sie die <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> -Methode für die <xref:Microsoft.SqlServer.Replication.MergePullSubscription> -Instanz aus Schritt 2 auf.</span><span class="sxs-lookup"><span data-stu-id="36d9b-204">Call the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergePullSubscription> from step 2.</span></span> <span data-ttu-id="36d9b-205">Diese Methode startet den Merge-Agent asynchron, und die Steuerung wird sofort an die Anwendung zurückgegeben, während der Agentauftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-205">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="36d9b-206">Sie können diese Methode für [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)]-Abonnenten nicht aufrufen. Diese Methode kann ebenfalls nicht aufgerufen werden, wenn das Abonnement mit dem Wert `false` für <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (dem Standard) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="36d9b-206">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="36d9b-207">Rufen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> -Klasse von der <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> -Eigenschaft ab, und rufen Sie die <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="36d9b-207">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="36d9b-208">Diese Methode startet den Merge-Agent synchron, und die Steuerung bleibt beim ausgeführten Agentauftrag.</span><span class="sxs-lookup"><span data-stu-id="36d9b-208">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="36d9b-209">Während der synchronen Ausführung können Sie das <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> -Ereignis verarbeiten, während der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-209">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="36d9b-210">Wenn Sie beim Erstellen des Pullabonnements `false` den Wert für <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (die Standardeinstellung) angegeben haben, müssen Sie auch <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A> und optional <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A> , und angeben, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> da die Metadaten des Agentauftrags für das Abonnement in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql)nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="36d9b-210">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A>, and optionally <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A>, and <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="36d9b-211">Beispiele (RMO)</span><span class="sxs-lookup"><span data-stu-id="36d9b-211">Examples (RMO)</span></span>  
 <span data-ttu-id="36d9b-212">In diesem Beispiel wird ein Pullabonnement mit einer Transaktionsveröffentlichung synchronisiert, wobei der Agent asynchron mit dem Agentauftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-212">This example synchronizes a pull subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub_withjob)]  
  
 <span data-ttu-id="36d9b-213">In diesem Beispiel wird ein Pullabonnement mit einer Transaktionsveröffentlichung synchronisiert, wobei der Agent synchron gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-213">This example synchronizes a pull subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub)]  
  
 <span data-ttu-id="36d9b-214">In diesem Beispiel wird ein Pullabonnement mit einer Mergeveröffentlichung synchronisiert, wobei der Agent asynchron mit dem Agentauftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-214">This example synchronizes a pull subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_withjob)]  
  
 <span data-ttu-id="36d9b-215">In diesem Beispiel wird ein Pullabonnement mit einer Mergeveröffentlichung synchronisiert, wobei der Agent synchron gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-215">This example synchronizes a pull subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub)]  
  
 <span data-ttu-id="36d9b-216">In diesem Beispiel wird ein Pullabonnement mit einer Mergeveröffentlichung synchronisiert, wobei die Websynchronisierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36d9b-216">This example synchronizes a pull subscription to a merge publication using Web synchronization.</span></span> <span data-ttu-id="36d9b-217">Das Abonnement wurde ohne den Agentauftrag und zugehörige Abonnementmetadaten erstellt, sodass der Agent synchron gestartet werden muss. Außerdem werden zusätzliche Abonnementinformationen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="36d9b-217">The subscription was created without the agent job and related subscription metadata, so the agent must be started synchronously and additional subscription information is supplied.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_NoJobWebSync](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_nojobwebsync)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_NoJobWebSync](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_nojobwebsync)]  
  
## <a name="see-also"></a><span data-ttu-id="36d9b-218">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36d9b-218">See Also</span></span>  
 <span data-ttu-id="36d9b-219">[Synchronisieren von Daten](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="36d9b-219">[Synchronize Data](synchronize-data.md) </span></span>  
 <span data-ttu-id="36d9b-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="36d9b-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="36d9b-221">Bewährte Methoden für die Replikationssicherheit</span><span class="sxs-lookup"><span data-stu-id="36d9b-221">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
