---
title: Replikations Abonnenten und AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/16/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover subscribers with AlwaysOn
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 0995f269-0580-43ed-b8bf-02b9ad2d7ee6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 449b5ac416f2ae86395c40a984678ed4258b3b85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618906"
---
# <a name="replication-subscribers-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="db3f0-102">Replikationsabonnenten und AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="db3f0-102">Replication Subscribers and AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="db3f0-103">Wenn für eine AlwaysOn-Verfügbarkeitsgruppe mit einer Datenbank, die einen Replikationsabonnenten darstellt, ein Failover ausgeführt wird, schlägt das Replikationsabonnement u. U. fehl.</span><span class="sxs-lookup"><span data-stu-id="db3f0-103">When an AlwaysOn availability group containing a database that is a replication subscriber fails over, the replication subscription might fail.</span></span> <span data-ttu-id="db3f0-104">Für Transaktionsreplikations-Pushabonnenten setzt der Verteilungs-Agent das Replizieren nach einem Failover automatisch fort, wenn das Abonnement mit dem Namen des Verfügbarkeitsgruppenlisteners erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db3f0-104">For transactional replication push subscribers, the distribution agent will continue to replicate automatically after a failover if the subscription was created using the AG listener name.</span></span> <span data-ttu-id="db3f0-105">Für Transaktionsreplikations-Pullabonnenten setzt der Verteilungs-Agent das Replizieren nach einem Failover automatisch fort, wenn das Abonnement mit dem Namen des Verfügbarkeitsgruppenlisteners erstellt wurde und wenn der ursprüngliche Abonnentenserver aktiv ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="db3f0-105">For transactional replication pull subscribers, the distribution agent will continue to replicate automatically after a failover, if the subscription was created using the AG listener name and the original subscriber server is up and running.</span></span> <span data-ttu-id="db3f0-106">Ursache hierfür ist, dass die Verteilungs-Agent-Aufträge nur auf dem ursprünglichen Abonnenten (primäres Replikat der Verfügbarkeitsgruppe) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="db3f0-106">This is because the distribution agent jobs only get created on the original subscriber (primary replica of the AG).</span></span> <span data-ttu-id="db3f0-107">Bei Mergeabonnenten muss der Abonnent vom Replikationsadministrator manuell neu konfiguriert werden, indem er das Abonnement neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="db3f0-107">For merge subscribers, a replication administrator must manually reconfigure the subscriber, by recreating the subscription.</span></span>  
  
## <a name="what-is-supported"></a><span data-ttu-id="db3f0-108">Unterstützte Vorgänge</span><span class="sxs-lookup"><span data-stu-id="db3f0-108">What is Supported</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="db3f0-109">-Replikation unterstützt das automatische Failover des Verlegers, das automatische Failover von Transaktionsabonnenten und das manuelle Failover von Mergeabonnenten.</span><span class="sxs-lookup"><span data-stu-id="db3f0-109">replication supports the automatic failover of the publisher, the automatic failover of transactional subscribers, and the manual failover of merge subscribers.</span></span> <span data-ttu-id="db3f0-110">Das Failover eines Verteilers zu einer Verfügbarkeitsdatenbank wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db3f0-110">The failover of a distributor on an availability database is not supported.</span></span> <span data-ttu-id="db3f0-111">AlwaysOn kann nicht mit Websync und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact-Szenarien kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="db3f0-111">AlwaysOn cannot be combined with Websync and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenarios.</span></span>  
  
 <span data-ttu-id="db3f0-112">**Failover eines Mergepullabonnements**</span><span class="sxs-lookup"><span data-stu-id="db3f0-112">**Failover of a Merge Pull Subscription**</span></span>  
  
 <span data-ttu-id="db3f0-113">Ein Pullabonnement schlägt bei einem Verfügbarkeitsgruppenfailover fehl, da der Pull-Agent die Aufträge nicht finden kann, die in der **msdb** -Datenbank der Serverinstanz gespeichert sind, von der das primäre Replikat gehostet wird. Die Datenbank ist nicht verfügbar, da ein Serverinstanzfehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="db3f0-113">A pull subscription fails upon availability group failover, because pull agent cannot find the jobs stored in the **msdb** database of the server instance that hosts the primary replica; which is not available because the server instance has failed.</span></span>  
  
 <span data-ttu-id="db3f0-114">**Failover eines Mergepushabonnements**</span><span class="sxs-lookup"><span data-stu-id="db3f0-114">**Failover of a Merge Push Subscription**</span></span>  
  
 <span data-ttu-id="db3f0-115">Ein Pushabonnement schlägt bei einem Verfügbarkeitsgruppenfailover fehl, da der Push-Agent keine Verbindung mehr mit der ursprünglichen Abonnementdatenbank auf dem ursprünglichen Abonnenten herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="db3f0-115">A push subscription fails upon availability group failover, because the push agent can no longer connect to original subscription database on original subscriber.</span></span>  
  
## <a name="how-to-create-transactional-subscription-in-an-alwayson-environment"></a><span data-ttu-id="db3f0-116">Erstellen eines Transaktionsabonnements in einer AlwaysOn-Umgebung</span><span class="sxs-lookup"><span data-stu-id="db3f0-116">How to Create Transactional Subscription in an AlwaysOn Environment</span></span>  
 <span data-ttu-id="db3f0-117">Führen Sie bei der Transaktionsreplikation folgende Schritte aus, um die Verfügbarkeitsgruppe eines Abonnenten zu konfigurieren und ein Failover auszuführen:</span><span class="sxs-lookup"><span data-stu-id="db3f0-117">For transactional replication, use the following steps to configure and failover a subscriber availability group:</span></span>  
  
1.  <span data-ttu-id="db3f0-118">Bevor Sie das Abonnement erstellen, fügen Sie der entsprechenden AlwaysOn-Verfügbarkeitsgruppe die Abonnentendatenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="db3f0-118">Before creating the subscription, add the subscriber database to the appropriate AlwaysOn availability group.</span></span>  
  
2.  <span data-ttu-id="db3f0-119">Fügen Sie den Verfügbarkeitsgruppenlistener des Abonnenten allen Knoten der Verfügbarkeitsgruppe als Verbindungsserver hinzu.</span><span class="sxs-lookup"><span data-stu-id="db3f0-119">Add the subscriber's availability group Listener as a linked server to all nodes of the availability group.</span></span> <span data-ttu-id="db3f0-120">Dadurch werden alle potenziellen Failoverpartner informiert, dass der Listener vorhanden und für Verbindungen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="db3f0-120">This step ensures that all potential failover partners are aware of and can connect to the listener.</span></span>  
  
3.  <span data-ttu-id="db3f0-121">Erstellen Sie das Abonnement mit dem Namen des Verfügbarkeitsgruppenlisteners des Abonnenten mithilfe des Skripts im Abschnitt **Erstellen eines Pushabonnements für eine Transaktionsreplikation** unten.</span><span class="sxs-lookup"><span data-stu-id="db3f0-121">Using the script in the **Creating a Transactional Replication Push Subscription** section below, create the subscription using the name of the availability group listener of the subscriber.</span></span> <span data-ttu-id="db3f0-122">Der Listenername bleibt nach einem Failover weiterhin gültig, während der tatsächliche Servername des Abonnenten von dem Knoten abhängig ist, der zum neuen primären Replikat wird.</span><span class="sxs-lookup"><span data-stu-id="db3f0-122">After a failover, the listener name will always remain valid, whereas the actual server name of the subscriber will depend on the actual node that became the new primary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="db3f0-123">Das Abonnement muss mithilfe eines [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Skripts erstellt werden, nicht mit [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db3f0-123">The subscription must be created by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script and cannot be created using [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="db3f0-124">Bei Erstellung eines Pullabonnements:</span><span class="sxs-lookup"><span data-stu-id="db3f0-124">If creating a pull subscription:</span></span>  
  
    1.  <span data-ttu-id="db3f0-125">Öffnen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]auf dem primären Abonnentenknoten die Struktur des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agents.</span><span class="sxs-lookup"><span data-stu-id="db3f0-125">In [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], on the primary subscriber node, open the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent tree.</span></span>  
  
    2.  <span data-ttu-id="db3f0-126">Suchen Sie den **Agentauftrag zur Verteilung des Pullabonnements**, und bearbeiten Sie den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="db3f0-126">Identify the **Pull Distribution Agent** job and edit the job.</span></span>  
  
    3.  <span data-ttu-id="db3f0-127">Überprüfen Sie im Schritt zum **Ausführen des Agentauftrags** den `-Publisher` -Parameter und den `-Distributor` -Parameter.</span><span class="sxs-lookup"><span data-stu-id="db3f0-127">On the **Run Agent** job step, check the `-Publisher` and `-Distributor` parameters.</span></span> <span data-ttu-id="db3f0-128">Stellen Sie sicher, dass diese Parameter den richtigen direkten Server- und Instanznamen des Verleger- und Verteilerservers enthalten.</span><span class="sxs-lookup"><span data-stu-id="db3f0-128">Make sure that these parameters contain the correct direct server and instance names of the publisher and distributor server.</span></span>  
  
    4.  <span data-ttu-id="db3f0-129">Ändern Sie den `-Subscriber` -Parameter in den Verfügbarkeitsgruppenlistener-Namen des Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="db3f0-129">Change the `-Subscriber` parameter to the subscriber's availability group listener name.</span></span>  
  
 <span data-ttu-id="db3f0-130">Wenn Sie beim Erstellen des Abonnements diese Schritte befolgen, müssen nach einem Failover keine weiteren Maßnahmen ergriffen werden.</span><span class="sxs-lookup"><span data-stu-id="db3f0-130">When you create your subscription following these steps, then you won't have to do anything after a failover.</span></span>  
  
## <a name="creating-a-transactional-replication-push-subscription"></a><span data-ttu-id="db3f0-131">Erstellen eines Pushabonnements für eine Transaktionsreplikation</span><span class="sxs-lookup"><span data-stu-id="db3f0-131">Creating a Transactional Replication Push Subscription</span></span>  
  
```  
-- commands to execute at the publisher, in the publisher database:  
use [<publisher database name>]  
EXEC sp_addsubscription @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @destination_db = N'<subscriber database name>',   
       @subscription_type = N'Push',   
       @sync_type = N'automatic', @article = N'all', @update_mode = N'read only', @subscriber_type = 0;  
GO  
  
EXEC sp_addpushsubscription_agent @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @subscriber_db = N'<subscriber database name>',   
       @job_login = null, @job_password = null, @subscriber_security_mode = 1;  
GO  
```  
  
## <a name="to-resume-the-merge-agents-after-the-availability-group-of-the-subscriber-fails-over"></a><span data-ttu-id="db3f0-132">So setzen Sie Merge-Agents nach einem Verfügbarkeitsgruppenfailover des Abonnenten fort</span><span class="sxs-lookup"><span data-stu-id="db3f0-132">To Resume the Merge Agents After the Availability Group of the Subscriber Fails Over</span></span>  
 <span data-ttu-id="db3f0-133">Bei einer Mergereplikation muss der Abonnent mithilfe folgender Schritte von einem Replikationsadministrator manuell neu konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="db3f0-133">For merge replication, a replication administrator must manually reconfigure the subscriber with the following steps:</span></span>  
  
1.  <span data-ttu-id="db3f0-134">Führen Sie `sp_subscription_cleanup` aus, um das alte Abonnement für den Abonnenten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="db3f0-134">Execute `sp_subscription_cleanup` to remove the old subscription for the subscriber.</span></span> <span data-ttu-id="db3f0-135">Führen Sie diese Aktion für das neue primäre Replikat aus (das zuvor das sekundäre Replikat war).</span><span class="sxs-lookup"><span data-stu-id="db3f0-135">Perform this action on the new primary replica (which was formerly the secondary replica).</span></span>  
  
2.  <span data-ttu-id="db3f0-136">Erstellen Sie das Abonnement neu, indem Sie ein neues Abonnement auf Grundlage einer neuen Momentaufnahme erstellen.</span><span class="sxs-lookup"><span data-stu-id="db3f0-136">Recreate the subscription by creating a new subscription, beginning with a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db3f0-137">Das aktuelle Verfahren ist für Mergereplikationsabonnenten nicht geeignet, die Mergereplikation erfolgt jedoch hauptsächlich für nicht verbundene Benutzer (Desktops, Laptops, Mobiltelefone), die keine AlwaysOn-Verfügbarkeitsgruppen auf dem Abonnenten nutzen.</span><span class="sxs-lookup"><span data-stu-id="db3f0-137">The current process is inconvenient for merge replication subscribers, however the main scenario for merge replication is disconnected users (desktops, laptops, handset devices) which will not use AlwaysOn availability groups on the subscriber.</span></span>  
  
  
