---
title: Synchronisieren eines Pushabonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], push subscriptions
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], synchronizing
ms.assetid: 0cfa7ae5-91d3-4a4f-9edf-a852d45783b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fb2f7bd961748272d6cd67e3412b09d9370a6f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701025"
---
# <a name="synchronize-a-push-subscription"></a><span data-ttu-id="3f9a4-102">Synchronisieren eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="3f9a4-102">Synchronize a Push Subscription</span></span>
  <span data-ttu-id="3f9a4-103">In diesem Thema wird beschrieben, wie ein Pushabonnement in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [Replikations-Agents](agents/replication-agents-overview.md)oder Replikationsverwaltungsobjekten (RMO) synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-103">This topic describes how to synchronize a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3f9a4-104">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f9a4-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3f9a4-105">Abonnements werden durch den Verteilungs-Agent (für Momentaufnahme- und Transaktionsveröffentlichungen) oder durch den Merge-Agent (für Mergeveröffentlichungen) synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="3f9a4-106">Agents können kontinuierlich, bei Bedarf oder nach einem Zeitplan ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="3f9a4-107">Weitere Informationen zum Angeben von Synchronisierungszeitplänen finden Sie unter [Angeben von Synchronisierungszeitplänen](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="3f9a4-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="3f9a4-108">Die bedarfsgesteuerte Synchronisierung eines Abonnements kann über die Ordner **Lokale Veröffentlichungen** und **Lokale Abonnements** in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] und über die Registerkarte **Alle Abonnements** im Replikationsmonitor erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-108">Synchronize a subscription on demand from the **Local Publications** and **Local Subscriptions** folders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and the **All Subscriptions** tab in Replication Monitor.</span></span> <span data-ttu-id="3f9a4-109">Abonnements von Oracle-Veröffentlichungen können vom Abonnenten nicht bedarfsgesteuert synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-109">Subscriptions to Oracle publications cannot be synchronized on demand from the Subscriber.</span></span> <span data-ttu-id="3f9a4-110">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3f9a4-110">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-publisher"></a><span data-ttu-id="3f9a4-111">So führen Sie die bedarfsgesteuerte Synchronisierung eines Pushabonnements in Management Studio durch (auf dem Verleger)</span><span class="sxs-lookup"><span data-stu-id="3f9a4-111">To synchronize a push subscription on demand in Management Studio (at the Publisher)</span></span>  
  
1.  <span data-ttu-id="3f9a4-112">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="3f9a4-113">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="3f9a4-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="3f9a4-114">Erweitern Sie die Veröffentlichung, für die Abonnements synchronisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-114">Expand the publication for which you want to synchronize subscriptions.</span></span>  
  
4.  <span data-ttu-id="3f9a4-115">Klicken Sie mit der rechten Maustaste auf das zu synchronisierende Abonnement, und klicken Sie dann auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-115">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="3f9a4-116">Klicken Sie im Dialogfeld **Synchronisierungsstatus anzeigen - \<Subscriber>:\<SubscriptionDatabase>** auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-116">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="3f9a4-117">Nach Abschluss der Synchronisierung wird die Meldung **Synchronisierung abgeschlossen** eingeblendet.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-117">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="3f9a4-118">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-118">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-subscriber"></a><span data-ttu-id="3f9a4-119">So führen Sie die bedarfsgesteuerte Synchronisierung eines Pushabonnements in Management Studio durch (auf dem Abonnenten)</span><span class="sxs-lookup"><span data-stu-id="3f9a4-119">To synchronize a push subscription on demand in Management Studio (at the Subscriber)</span></span>  
  
1.  <span data-ttu-id="3f9a4-120">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="3f9a4-121">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="3f9a4-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="3f9a4-122">Klicken Sie mit der rechten Maustaste auf das zu synchronisierende Abonnement, und klicken Sie dann auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-122">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="3f9a4-123">Es wird gemeldet, dass eine Verbindung mit dem Verteiler hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-123">A message is displayed about establishing a connection to the Distributor.</span></span> <span data-ttu-id="3f9a4-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-124">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3f9a4-125">Klicken Sie im Dialogfeld **Synchronisierungsstatus anzeigen - \<Subscriber>:\<SubscriptionDatabase>** auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-125">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="3f9a4-126">Nach Abschluss der Synchronisierung wird die Meldung **Synchronisierung abgeschlossen** eingeblendet.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-126">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="3f9a4-127">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-127">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-replication-monitor"></a><span data-ttu-id="3f9a4-128">So führen Sie die bedarfsgesteuerte Synchronisierung eines Pushabonnements im Replikationsmonitor durch</span><span class="sxs-lookup"><span data-stu-id="3f9a4-128">To synchronize a push subscription on demand in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="3f9a4-129">Erweitern Sie im Replikationsmonitor im linken Bereich eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-129">In Replication Monitor, expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="3f9a4-130">Klicken Sie auf die Registerkarte **Alle Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="3f9a4-130">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="3f9a4-131">Klicken Sie mit der rechten Maustaste auf das Abonnement, das Sie synchronisieren möchten, und klicken Sie dann auf **Synchronisierung starten**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-131">Right-click the subscription you want to synchronize, and then click **Start Synchronizing**.</span></span>  
  
4.  <span data-ttu-id="3f9a4-132">Wenn Sie den Status der Synchronisierung anzeigen möchten, klicken Sie mit der rechten Maustaste auf das Abonnement, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-132">To view synchronization progress, right-click the subscription, and then click **View Details**.</span></span>  
  
##  <a name="using-replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="3f9a4-133">Verwenden von Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="3f9a4-133">Using Replication Agents</span></span>  
 <span data-ttu-id="3f9a4-134">Pushabonnements können programmgesteuert oder bei Bedarf synchronisiert werden, indem die entsprechende ausführbare Datei für den Replikations-Agent an der Eingabeaufforderung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-134">Push subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="3f9a4-135">Welche ausführbare Datei für den Replikations-Agent ausgeführt wird, hängt vom Typ der Veröffentlichung ab, zu der die Pushveröffentlichung gehört.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-135">The replication agent executable file that is invoked will depend on the type of publication to which the push subscription belongs.</span></span>  
  
#### <a name="to-start-the-distribution-agent-to-synchronize-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="3f9a4-136">So starten Sie den Verteilungs-Agent, um ein Pushabonnement für eine Transaktionsveröffentlichung zu synchronisieren</span><span class="sxs-lookup"><span data-stu-id="3f9a4-136">To start the Distribution Agent to synchronize a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="3f9a4-137">Führen Sie auf dem Verteiler an der Eingabeaufforderung oder in einer Batchdatei **distrib.exe**aus.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-137">From the command prompt or in a batch file at the Distributor, execute **distrib.exe**.</span></span> <span data-ttu-id="3f9a4-138">Geben Sie die folgenden Befehlszeilenargumente an:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-138">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="3f9a4-139">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-139">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="3f9a4-140">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-140">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="3f9a4-141">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-141">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="3f9a4-142">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-142">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="3f9a4-143">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-143">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="3f9a4-144">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-144">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="3f9a4-145">Wenn Sie die SQL Server-Authentifizierung verwenden, müssen Sie auch die folgenden Argumente angeben:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-145">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="3f9a4-146">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-146">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="3f9a4-147">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-147">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="3f9a4-148">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-148">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="3f9a4-149">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-149">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="3f9a4-150">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-150">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="3f9a4-151">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-151">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="3f9a4-152">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-152">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="3f9a4-153">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-153">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="3f9a4-154">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-154">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
#### <a name="to-start-the-merge-agent-to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="3f9a4-155">So starten Sie den Merge-Agent, um ein Pushabonnement für eine Mergeveröffentlichung zu synchronisieren</span><span class="sxs-lookup"><span data-stu-id="3f9a4-155">To start the Merge Agent to synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="3f9a4-156">Führen Sie auf dem Verteiler an der Eingabeaufforderung oder in einer Batchdatei **replmerg.exe**aus.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-156">From the command prompt or in a batch file at the Distributor, execute **replmerg.exe**.</span></span> <span data-ttu-id="3f9a4-157">Geben Sie die folgenden Befehlszeilenargumente an:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-157">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="3f9a4-158">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-158">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="3f9a4-159">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-159">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="3f9a4-160">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-160">**-Publication**</span></span>  
  
    -   <span data-ttu-id="3f9a4-161">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-161">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="3f9a4-162">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-162">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="3f9a4-163">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-163">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="3f9a4-164">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-164">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="3f9a4-165">Wenn Sie die SQL Server-Authentifizierung verwenden, müssen Sie auch die folgenden Argumente angeben:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-165">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="3f9a4-166">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-166">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="3f9a4-167">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-167">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="3f9a4-168">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-168">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="3f9a4-169">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-169">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="3f9a4-170">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-170">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="3f9a4-171">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-171">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="3f9a4-172">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-172">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="3f9a4-173">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-173">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="3f9a4-174">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="3f9a4-174">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="3f9a4-175">Beispiele (Replikations-Agents)</span><span class="sxs-lookup"><span data-stu-id="3f9a4-175">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="3f9a4-176">Im folgenden Beispiel wird der Verteilungs-Agent gestartet, um ein Pushabonnement zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-176">The following example starts the Distribution Agent to synchronize a push subscription.</span></span>  
  
 
```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksProductsTran  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4
```
  
 <span data-ttu-id="3f9a4-177">Im folgenden Beispiel wird der Merge-Agent gestartet, um ein Pushabonnement zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-177">The following example starts the Merge Agent to synchronize a push subscription.</span></span>  

```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksSalesOrdersMerge  
  
REM -- Start the Merge Agent.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher %Publisher%   
-Subscriber  %Subscriber%  -Distributor %Publisher% -PublisherDB  %PublicationDB%   
-SubscriberDB %SubscriptionDB% -Publication %Publication% -PublisherSecurityMode 1   
-OutputVerboseLevel 3  -Output -SubscriberSecurityMode 1  -SubscriptionType 0   
-DistributorSecurityMode 1
```
  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="3f9a4-178">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="3f9a4-178">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="3f9a4-179">Sie können Pushabonnements mit Replikationsverwaltungsobjekten (RMO) und dem Zugriff von verwaltetem Code auf Funktionen des Replikations-Agents programmgesteuert synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-179">You can synchronize push subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="3f9a4-180">Welche Klassen für die Synchronisierung eines Pushabonnements verwendet werden, hängt vom Typ der Veröffentlichung ab, zu der das Abonnement gehört.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-180">The classes that you use to synchronize a push subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f9a4-181">Starten Sie den Agent asynchron, wenn Sie eine Synchronisierung starten möchten, die autonom ausgeführt wird, ohne sich auf die Anwendung auszuwirken.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-181">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="3f9a4-182">Wenn Sie während der Synchronisierung das Ergebnis der Synchronisierung überwachen und Rückrufe vom Agent empfangen möchten (z. B. über eine Statusanzeige), müssen Sie den Agent synchron starten.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-182">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, if you want to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="3f9a4-183">Für [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] -Abonnenten müssen Sie den Agent synchron starten.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-183">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="3f9a4-184">So synchronisieren Sie ein Pushabonnement für eine Momentaufnahme- oder Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="3f9a4-184">To synchronize a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="3f9a4-185">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-185">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="3f9a4-186">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransSubscription> -Klasse, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-186">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class and set the following properties:</span></span>  
  
    -   <span data-ttu-id="3f9a4-187">Den Namen der Veröffentlichungsdatenbank für <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-187">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-188">Den Namen der Veröffentlichung, zu der das Abonnement gehört, für <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-188">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-189">Den Namen der Abonnementdatenbank für <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-189">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-190">Den Namen des Abonnenten für <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-190">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-191">Die in Schritt 1 erstellte Verbindung für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-191">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="3f9a4-192">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die restlichen Abonnementeigenschaften abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-192">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="3f9a4-193">Überprüfen Sie, ob das Abonnement vorhanden ist, wenn diese Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-193">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="3f9a4-194">Starten Sie den Verteilungs-Agent auf eine der folgenden Arten auf dem Verteiler:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-194">Start the Distribution Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="3f9a4-195">Rufen Sie die <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> -Methode für die <xref:Microsoft.SqlServer.Replication.TransSubscription> -Instanz aus Schritt 2 auf.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-195">Call the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransSubscription> from step 2.</span></span> <span data-ttu-id="3f9a4-196">Diese Methode startet den Verteilungs-Agent asynchron, und die Steuerung wird sofort an die Anwendung zurückgegeben, während der Agentauftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-196">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="3f9a4-197">Sie können diese Methode nicht aufrufen, wenn das Abonnement mit dem Wert `false` für <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A> erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-197">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-198">Rufen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> -Klasse von der <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> -Eigenschaft ab, und rufen Sie die <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-198">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="3f9a4-199">Diese Methode startet den Agent synchron, und die Steuerung bleibt beim ausgeführten Agentauftrag.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-199">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="3f9a4-200">Während der synchronen Ausführung können Sie das <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> -Ereignis verarbeiten, während der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-200">During synchronous execution you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="3f9a4-201">So synchronisieren Sie ein Pushabonnement mit einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="3f9a4-201">To synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="3f9a4-202">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-202">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="3f9a4-203">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergeSubscription> -Klasse, und legen Sie die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="3f9a4-204">Den Namen der Veröffentlichungsdatenbank für <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-204">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-205">Den Namen der Veröffentlichung, zu der das Abonnement gehört, für <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-205">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-206">Den Namen der Abonnementdatenbank für <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-206">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-207">Den Namen des Abonnenten für <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-207">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-208">Die in Schritt 1 erstellte Verbindung für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-208">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="3f9a4-209">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die restlichen Abonnementeigenschaften abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-209">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="3f9a4-210">Überprüfen Sie, ob das Abonnement vorhanden ist, wenn diese Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-210">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="3f9a4-211">Starten Sie den Merge-Agent auf eine der folgenden Arten auf dem Verteiler:</span><span class="sxs-lookup"><span data-stu-id="3f9a4-211">Start the Merge Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="3f9a4-212">Rufen Sie die <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> -Methode für die <xref:Microsoft.SqlServer.Replication.MergeSubscription> -Instanz aus Schritt 2 auf.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-212">Call the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergeSubscription> from step 2.</span></span> <span data-ttu-id="3f9a4-213">Diese Methode startet den Merge-Agent asynchron, und die Steuerung wird sofort an die Anwendung zurückgegeben, während der Agentauftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-213">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="3f9a4-214">Sie können diese Methode nicht aufrufen, wenn das Abonnement mit dem Wert `false` für <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A> erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-214">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="3f9a4-215">Rufen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> -Klasse von der <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> -Eigenschaft ab, und rufen Sie die <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-215">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="3f9a4-216">Diese Methode startet den Merge-Agent synchron, und die Steuerung bleibt beim ausgeführten Agentauftrag.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-216">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="3f9a4-217">Während der synchronen Ausführung können Sie das <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> -Ereignis verarbeiten, während der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-217">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="3f9a4-218">Beispiele (RMO)</span><span class="sxs-lookup"><span data-stu-id="3f9a4-218">Examples (RMO)</span></span>  
 <span data-ttu-id="3f9a4-219">In diesem Beispiel wird ein Pushabonnement mit einer Transaktionsveröffentlichung synchronisiert, wobei der Agent mit dem Agentauftrag asynchron gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-219">This example synchronizes a push subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub_withjob)]  
  
 <span data-ttu-id="3f9a4-220">In diesem Beispiel wird ein Pushabonnement mit einer Transaktionsveröffentlichung synchronisiert, wobei der Agent synchron gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-220">This example synchronizes a push subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub)]  
  
 <span data-ttu-id="3f9a4-221">In diesem Beispiel wird ein Pushabonnement mit einer Mergeveröffentlichung synchronisiert, wobei der Agent asynchron mit dem Agentauftrag gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-221">This example synchronizes a push subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub_withjob)]  
  
 <span data-ttu-id="3f9a4-222">In diesem Beispiel wird ein Pushabonnement mit einer Mergeveröffentlichung synchronisiert, wobei der Agent synchron gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3f9a4-222">This example synchronizes a push subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="3f9a4-223">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f9a4-223">See Also</span></span>  
 <span data-ttu-id="3f9a4-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="3f9a4-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="3f9a4-225">[Synchronisieren von Daten](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="3f9a4-225">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="3f9a4-226">Bewährte Methoden für die Replikationssicherheit</span><span class="sxs-lookup"><span data-stu-id="3f9a4-226">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
