---
title: Abonnieren von Veröffentlichungen | Microsoft Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.conc.subtopubs.f1
helpviewer_keywords:
- subscriptions [SQL Server replication], about subscriptions
- pull subscriptions [SQL Server replication]
- subscriptions [SQL Server replication]
- push subscriptions [SQL Server replication], about push subscriptions
- merge replication subscribing [SQL Server replication]
- merge replication subscribing [SQL Server replication], about subscribing
- publications [SQL Server replication], subscribing
- push subscriptions [SQL Server replication]
- pull subscriptions [SQL Server replication], about pull subscriptions
- snapshot replication [SQL Server], subscribing
- transactional replication, subscribing
ms.assetid: 088ee30a-05ab-47c4-92ed-316b93e12445
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c565aae26c6d549eb67043168797d5fb059c8e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608511"
---
# <a name="subscribe-to-publications"></a><span data-ttu-id="ac811-102">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="ac811-102">Subscribe to Publications</span></span>
  <span data-ttu-id="ac811-103">Bei einem Abonnement handelt es sich um eine Anforderung einer Kopie von Daten und Datenbankobjekten in einer Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="ac811-103">A subscription is a request for a copy of the data and database objects in a publication.</span></span> <span data-ttu-id="ac811-104">Mit einem Abonnement wird definiert, welche Veröffentlichung empfangen wird und wo und wann sie empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="ac811-104">A subscription defines which publication will be received, and where and when it will be received.</span></span> <span data-ttu-id="ac811-105">Bei der Planung von Abonnements sollten Sie berücksichtigen, wo die Agentverarbeitung stattfinden soll.</span><span class="sxs-lookup"><span data-stu-id="ac811-105">When planning for subscriptions, consider where you want agent processing to occur.</span></span> <span data-ttu-id="ac811-106">Durch den ausgewählten Abonnementtyp wird gesteuert, wo der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac811-106">The type of subscription you choose controls where the agent runs.</span></span> <span data-ttu-id="ac811-107">Bei einem Pushabonnement wird der Merge-Agent oder der Verteilungs-Agent auf dem Verteiler ausgeführt, während die Agents bei Pullabonnements auf den Abonnenten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ac811-107">With a push subscription, the Merge Agent or Distribution Agent runs at the Distributor, whereas with a pull subscription, agents run at the Subscribers.</span></span> <span data-ttu-id="ac811-108">Nach der Erstellung eines Abonnements kann der zugehörige Abonnementtyp nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ac811-108">After a subscription is created, it cannot be changed from one type to another.</span></span>  
  
|<span data-ttu-id="ac811-109">Subscription</span><span class="sxs-lookup"><span data-stu-id="ac811-109">Subscription</span></span>|<span data-ttu-id="ac811-110">Merkmale</span><span class="sxs-lookup"><span data-stu-id="ac811-110">Characteristics</span></span>|<span data-ttu-id="ac811-111">Verwendung</span><span class="sxs-lookup"><span data-stu-id="ac811-111">Use When</span></span>|  
|------------------|---------------------|--------------|  
|<span data-ttu-id="ac811-112">Pushabonnement</span><span class="sxs-lookup"><span data-stu-id="ac811-112">Push Subscription</span></span>|<span data-ttu-id="ac811-113">Bei einem Pushabonnement gibt der Verleger Änderungen an einen Abonnenten weiter, ohne dass ein Abonnent dies angefordert hat.</span><span class="sxs-lookup"><span data-stu-id="ac811-113">With a push subscription, the Publisher propagates changes to a Subscriber without a request from the Subscriber.</span></span> <span data-ttu-id="ac811-114">Änderungen können bei Bedarf, kontinuierlich oder auf einen Zeitplan basierend per Push an den Abonnenten weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ac811-114">Changes can be pushed to Subscribers on demand, continuously, or on a scheduled basis.</span></span> <span data-ttu-id="ac811-115">Der Verteilungs-Agent oder der Merge-Agent wird auf dem Verteiler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac811-115">The Distribution Agent or Merge Agent runs at the Distributor.</span></span>|<span data-ttu-id="ac811-116">Daten werden normalerweise kontinuierlich oder im Rahmen eines sich regelmäßig wiederholenden Zeitplans synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="ac811-116">Data will typically be synchronized continuously or on a frequently recurring schedule.</span></span><br /><br /> <span data-ttu-id="ac811-117">Veröffentlichungen erfordern Bewegungen von Daten nahezu in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="ac811-117">Publications require near real-time movement of data.</span></span><br /><br /> <span data-ttu-id="ac811-118">Der höhere Prozessoroverhead auf einem Verteiler wirkt sich nicht auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="ac811-118">The higher processor overhead at the Distributor does not affect performance.</span></span><br /><br /> <span data-ttu-id="ac811-119">Wird am häufigsten mit Momentaufnahme- und Transaktionsreplikationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac811-119">Most often used with snapshot and transactional replication.</span></span>|  
|<span data-ttu-id="ac811-120">Pullabonnement</span><span class="sxs-lookup"><span data-stu-id="ac811-120">Pull Subscription</span></span>|<span data-ttu-id="ac811-121">Bei einem Pullabonnement fordert der Abonnent die auf dem Verleger vorgenommene Änderungen an.</span><span class="sxs-lookup"><span data-stu-id="ac811-121">With a pull subscription, the Subscriber requests changes made at the Publisher.</span></span> <span data-ttu-id="ac811-122">Mithilfe von Pullabonnements können Benutzer auf dem Abonnenten bestimmen, wann die Datenänderungen synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ac811-122">Pull subscriptions allow the user at the Subscriber to determine when the data changes are synchronized.</span></span> <span data-ttu-id="ac811-123">Der Verteilungs-Agent oder der Merge-Agent wird auf dem Abonnenten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac811-123">The Distribution Agent or the Merge Agent runs at the Subscriber.</span></span>|<span data-ttu-id="ac811-124">Daten werden normalerweise bei Bedarf oder im Rahmen eines Zeitplans synchronisiert anstatt kontinuierlich.</span><span class="sxs-lookup"><span data-stu-id="ac811-124">Data will typically be synchronized on demand or on a schedule rather than continuously.</span></span><br /><br /> <span data-ttu-id="ac811-125">Die Veröffentlichung verfügt über eine hohe Anzahl an Abonnenten, und bzw. oder es wäre zu ressourcenintensiv, alle Agents auf dem Verteiler auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ac811-125">The publication has a large number of Subscribers, and/or it would be too resource-intensive to run all the agents at the Distributor.</span></span><br /><br /> <span data-ttu-id="ac811-126">Abonnenten sind unabhängig, getrennt und bzw. oder mobil.</span><span class="sxs-lookup"><span data-stu-id="ac811-126">Subscribers are autonomous, disconnected, and/or mobile.</span></span> <span data-ttu-id="ac811-127">Die Abonnenten bestimmen, wann eine Verbindung hergestellt wird und Synchronisierungsänderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ac811-127">Subscribers will determine when they will connect and synchronize changes.</span></span><br /><br /> <span data-ttu-id="ac811-128">Wird am häufigsten für Mergereplikationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac811-128">Most often used with merge replication.</span></span>|  
  
## <a name="merge-replication-subscription-types"></a><span data-ttu-id="ac811-129">Abonnementtypen für Mergereplikationen</span><span class="sxs-lookup"><span data-stu-id="ac811-129">Merge Replication Subscription Types</span></span>  
 <span data-ttu-id="ac811-130">Für alle Replikationstypen sind Push- und Pullabonnements zulässig.</span><span class="sxs-lookup"><span data-stu-id="ac811-130">All replication types allow push and pull subscriptions.</span></span> <span data-ttu-id="ac811-131">Bei Mergereplikationen werden zur Unterscheidung von Abonnements zwei zusätzliche Begriffe verwendet: Client- und Serverabonnements.</span><span class="sxs-lookup"><span data-stu-id="ac811-131">Merge replication uses two additional terms to distinguish subscriptions: client subscriptions and server subscriptions.</span></span> <span data-ttu-id="ac811-132">Mit Push- und Pullabonnements können sowohl Client- als auch Serverabonnements verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac811-132">Both client and server subscription types can be used with push and pull subscriptions.</span></span> <span data-ttu-id="ac811-133">Clientabonnements sind für die meisten Abonnenten geeignet, während Serverabonnements in der Regel für Abonnenten verwendet werden, die Daten auf anderen Abonnenten erneut veröffentlichten.</span><span class="sxs-lookup"><span data-stu-id="ac811-133">Client subscriptions are appropriate for most Subscribers, whereas server subscriptions are typically used for Subscribers that republish data to other Subscribers.</span></span> <span data-ttu-id="ac811-134">Die Auswahl des Abonnements hat Auswirkungen auf die Konfliktlösung.</span><span class="sxs-lookup"><span data-stu-id="ac811-134">Subscription choice also affects conflict resolution.</span></span>  
  
## <a name="non-sql-server-subscribers"></a><span data-ttu-id="ac811-135">Nicht-SQL Server-Abonnenten</span><span class="sxs-lookup"><span data-stu-id="ac811-135">Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="ac811-136">Oracle und IBM DB2 können mithilfe von Pushabonnements Momentaufnahme- und Transaktionsveröffentlichungen abonnieren.</span><span class="sxs-lookup"><span data-stu-id="ac811-136">Oracle and IBM DB2 can subscribe to snapshot and transactional publications using push subscriptions.</span></span> <span data-ttu-id="ac811-137">Weitere Informationen finden Sie unter [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="ac811-137">For more information, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="ac811-138">Erstellen von Abonnements</span><span class="sxs-lookup"><span data-stu-id="ac811-138">Creating Subscriptions</span></span>  
 <span data-ttu-id="ac811-139">Zum Erstellen eines Abonnements geben Sie folgende Informationen an:</span><span class="sxs-lookup"><span data-stu-id="ac811-139">To create a subscription, you supply the following information:</span></span>  
  
-   <span data-ttu-id="ac811-140">Der Name der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="ac811-140">The name of the publication.</span></span>  
  
-   <span data-ttu-id="ac811-141">Den Namen des Abonnenten und der Abonnementdatenbank.</span><span class="sxs-lookup"><span data-stu-id="ac811-141">The name of the Subscriber and the subscription database.</span></span>  
  
-   <span data-ttu-id="ac811-142">Ob der Verteilungs-Agent oder der Merge-Agent auf dem Verteiler bzw. Abonnenten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac811-142">Whether the Distribution Agent or Merge Agent runs at the Distributor or at the Subscriber.</span></span>  
  
-   <span data-ttu-id="ac811-143">Ob der Verteilungs-Agent oder Merge-Agent kontinuierlich, auf einem Zeitplan basierend oder nur bei Bedarf ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac811-143">Whether the Distribution Agent or Merge Agent runs continuously, on a scheduled basis, or on demand only.</span></span>  
  
-   <span data-ttu-id="ac811-144">Ob der Momentaufnahme-Agent eine aktualisierte Anfangsmomentaufnahme für das Abonnement erstellen und der Verteilungs-Agent oder Merge-Agent diese Momentaufnahme auf dem Abonnenten anwenden soll.</span><span class="sxs-lookup"><span data-stu-id="ac811-144">Whether the Snapshot Agent should create an initial snapshot for the subscription and whether the Distribution Agent or Merge Agent should apply that snapshot at the Subscriber.</span></span>  
  
-   <span data-ttu-id="ac811-145">Die Konten, unter denen der Verteilungs-Agent oder der Merge-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac811-145">Accounts under which the Distribution Agent or Merge Agent will run.</span></span>  
  
-   <span data-ttu-id="ac811-146">Bei Mergereplikationen den Abonnementtyp: Server oder Client.</span><span class="sxs-lookup"><span data-stu-id="ac811-146">For merge replication, the type of subscription: server or client.</span></span>  
  
 <span data-ttu-id="ac811-147">**So erstellen Sie ein Pushabonnement**</span><span class="sxs-lookup"><span data-stu-id="ac811-147">**To create a push subscription**</span></span>  
  
 [<span data-ttu-id="ac811-148">Erstellen eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="ac811-148">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
 <span data-ttu-id="ac811-149">**So können Sie Eigenschaften von Pushabonnements anzeigen und ändern**</span><span class="sxs-lookup"><span data-stu-id="ac811-149">**To view or modify push subscription properties**</span></span>  
  
 [<span data-ttu-id="ac811-150">Anzeigen und Ändern der Eigenschaften von Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="ac811-150">View and Modify Push Subscription Properties</span></span>](view-and-modify-push-subscription-properties.md)  
  
 <span data-ttu-id="ac811-151">**So löschen Sie ein Pushabonnement**</span><span class="sxs-lookup"><span data-stu-id="ac811-151">**To delete a push subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="ac811-152">: [Löschen eines Pushabonnements](delete-a-push-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="ac811-152">: [Delete a Push Subscription](delete-a-push-subscription.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac811-153">Durch das Löschen eines Abonnements werden veröffentlichte Objekte nicht vom Abonnenten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ac811-153">Deleting a subscription does not remove published objects from the Subscriber.</span></span>  
  
 <span data-ttu-id="ac811-154">**So erstellen Sie ein Pullabonnement**</span><span class="sxs-lookup"><span data-stu-id="ac811-154">**To create a pull subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="ac811-155">: [Erstellen eines Pullabonnements](create-a-pull-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="ac811-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span></span>  
  
 <span data-ttu-id="ac811-156">**So können Sie Eigenschaften von Pullabonnements anzeigen und ändern**</span><span class="sxs-lookup"><span data-stu-id="ac811-156">**To view or modify pull subscription properties**</span></span>  
  
 [<span data-ttu-id="ac811-157">Anzeigen und Ändern der Eigenschaften von Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="ac811-157">View and Modify Pull Subscription Properties</span></span>](view-and-modify-pull-subscription-properties.md)  
  
 <span data-ttu-id="ac811-158">**So löschen Sie ein Pullabonnement**</span><span class="sxs-lookup"><span data-stu-id="ac811-158">**To delete a pull subscription**</span></span>  
  
 [<span data-ttu-id="ac811-159">Löschen eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="ac811-159">Delete a Pull Subscription</span></span>](delete-a-pull-subscription.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac811-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac811-160">See Also</span></span>  
 <span data-ttu-id="ac811-161">[Sichern des Abonnenten](security/secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="ac811-161">[Secure the Subscriber](security/secure-the-subscriber.md) </span></span>  
 [<span data-ttu-id="ac811-162">Abonnementablauf und -deaktivierung</span><span class="sxs-lookup"><span data-stu-id="ac811-162">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
