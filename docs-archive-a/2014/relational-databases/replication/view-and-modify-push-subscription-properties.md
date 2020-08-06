---
title: Anzeigen und Ändern der Eigenschaften von Pushabonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1506d4f83fcfb94d62efd01c4d6447048fecfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722681"
---
# <a name="view-and-modify-push-subscription-properties"></a><span data-ttu-id="b818b-102">Anzeigen und Ändern der Eigenschaften von Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="b818b-102">View and Modify Push Subscription Properties</span></span>
  <span data-ttu-id="b818b-103">In diesem Thema wird beschrieben, wie die Eigenschaften von Pushabonnements in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b818b-103">This topic describes how to view and modify push subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="b818b-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b818b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b818b-105">**So können Sie Eigenschaften von Pushabonnements anzeigen und ändern mit:**</span><span class="sxs-lookup"><span data-stu-id="b818b-105">**To view and modify push subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="b818b-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b818b-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b818b-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b818b-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b818b-108">Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="b818b-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b818b-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b818b-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b818b-110">Sie können die Eigenschaften von Pushabonnements vom Verleger an den folgenden Stellen anzeigen und ändern:</span><span class="sxs-lookup"><span data-stu-id="b818b-110">View and modify push subscription properties from the Publisher in:</span></span>  
  
-   <span data-ttu-id="b818b-111">Im Dialogfeld **Abonnementeigenschaften – \<Publisher>: \<PublicationDatabase>** , das in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b818b-111">The **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="b818b-112">Auf der Registerkarte **Alle Abonnements** , verfügbar im Replikationsmonitor.</span><span class="sxs-lookup"><span data-stu-id="b818b-112">The **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="b818b-113">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b818b-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a><span data-ttu-id="b818b-114">So zeigen Sie Eigenschaften von Pushabonnement in Management Studio an und ändern Sie die Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b818b-114">To view and modify push subscription properties in Management Studio</span></span>  
  
1.  <span data-ttu-id="b818b-115">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="b818b-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b818b-116">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="b818b-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b818b-117">Erweitern Sie die entsprechende Veröffentlichung, klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b818b-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b818b-118">Ändern Sie die Eigenschaften nach Bedarf, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b818b-118">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a><span data-ttu-id="b818b-119">So zeigen Sie Eigenschaften von Pushabonnement im Replikationsmonitor an und ändern Sie die Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b818b-119">To view and modify push subscription properties in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="b818b-120">Erweitern Sie im linken Bereich des Replikationsmonitors eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="b818b-120">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="b818b-121">Klicken Sie auf die Registerkarte **Alle Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="b818b-121">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="b818b-122">Klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b818b-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b818b-123">Ändern Sie die Eigenschaften nach Bedarf, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b818b-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b818b-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b818b-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="b818b-125">Pushabonnements können geändert und auf ihre Eigenschaften kann mithilfe gespeicherter Replikationsprozeduren programmgesteuert zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b818b-125">Push subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="b818b-126">Welche gespeicherten Prozeduren verwendet werden, hängt vom Typ der Veröffentlichung ab, zu der das Abonnement gehört.</span><span class="sxs-lookup"><span data-stu-id="b818b-126">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b818b-127">So zeigen Sie die Eigenschaften eines Pushabonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung an</span><span class="sxs-lookup"><span data-stu-id="b818b-127">To view the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b818b-128">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b818b-128">At the Publisher on the publication database, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="b818b-129">Geben Sie **@publication** , **@subscriber** und den Wert **all** für an **@article** .</span><span class="sxs-lookup"><span data-stu-id="b818b-129">Specify **@publication**, **@subscriber**, and a value of **all** for **@article**.</span></span>  
  
2.  <span data-ttu-id="b818b-130">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql)aus, und geben Sie **@subscriber**.</span><span class="sxs-lookup"><span data-stu-id="b818b-130">At the Publisher on the publication database, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b818b-131">So ändern Sie die Eigenschaften eines Pushabonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="b818b-131">To change the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b818b-132">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql)aus, und geben Sie **@subscriber** sowie Parameter für die zu ändernden Abonnenteneigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="b818b-132">At the Publisher on the publication database, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), specifying **@subscriber** and any parameters for the Subscriber properties being changed.</span></span>  
  
2.  <span data-ttu-id="b818b-133">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b818b-133">At the Publisher on the publication database, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span></span> <span data-ttu-id="b818b-134">Geben **@publication** **@subscriber** Sie,, **@destination_db** , den Wert **all** für **@article** , die zu ändernde Abonnement Eigenschaft als **@property** und den neuen Wert als **@value** .</span><span class="sxs-lookup"><span data-stu-id="b818b-134">Specify **@publication**, **@subscriber**, **@destination_db**, a value of **all** for **@article**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span> <span data-ttu-id="b818b-135">Dadurch werden die Sicherheitseinstellungen für das Pushabonnement geändert.</span><span class="sxs-lookup"><span data-stu-id="b818b-135">This changes security settings for the push subscription.</span></span>  
  
3.  <span data-ttu-id="b818b-136">(Optional) Um die Paketeigenschaften der Data Transformation Services (Datentransformationsdienste, DTS) zu ändern, führen Sie [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) auf dem Abonnenten für die Abonnementdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="b818b-136">(Optional) To change the Data Transformation Services (DTS) package properties of a subscription, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="b818b-137">Geben Sie die ID des Verteilungs-Agent Auftrags für **@jobid** und die folgenden DTS-Paket Eigenschaften an:</span><span class="sxs-lookup"><span data-stu-id="b818b-137">Specify the ID of the Distribution Agent job for **@jobid** and the following DTS package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="b818b-138">Dadurch werden die DTS-Paketeigenschaften eines Abonnements geändert.</span><span class="sxs-lookup"><span data-stu-id="b818b-138">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b818b-139">Die Auftrag-ID erhalten Sie, wenn Sie [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql)ausführen.</span><span class="sxs-lookup"><span data-stu-id="b818b-139">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="b818b-140">So zeigen Sie die Eigenschaften eines Pushabonnements für eine Mergeveröffentlichung an</span><span class="sxs-lookup"><span data-stu-id="b818b-140">To view the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b818b-141">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b818b-141">At the Publisher on the publication database, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span></span> <span data-ttu-id="b818b-142">Geben Sie **@publication** und an **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="b818b-142">Specify **@publication** and **@subscriber**.</span></span>  
  
2.  <span data-ttu-id="b818b-143">Führen Sie [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql)auf dem Verleger aus, und geben Sie an **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="b818b-143">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="b818b-144">So ändern Sie die Eigenschaften eines Pushabonnements für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="b818b-144">To change the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b818b-145">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b818b-145">At the Publisher on the publication database, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span></span> <span data-ttu-id="b818b-146">Geben **@publication** **@subscriber** Sie,, **@subscriber_db** , die zu ändernde Abonnement Eigenschaft als **@property** und den neuen Wert als **@value** .</span><span class="sxs-lookup"><span data-stu-id="b818b-146">Specify **@publication**, **@subscriber**, **@subscriber_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="b818b-147">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b818b-147">Example (Transact-SQL)</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="b818b-148">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="b818b-148">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="b818b-149">Die RMO-Klassen, mit denen Sie die Eigenschaften von Pushabonnements anzeigen oder ändern, hängen vom Typ der Veröffentlichung ab, für die das Pushabonnement abonniert wird.</span><span class="sxs-lookup"><span data-stu-id="b818b-149">The RMO classes you use to view or modify push subscription properties depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b818b-150">So zeigen Sie die Eigenschaften eines Pushabonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="b818b-150">To view or modify properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b818b-151">Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="b818b-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="b818b-152">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransSubscription>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b818b-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="b818b-153">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>und <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="b818b-153">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b818b-154">Legen Sie <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für die Einstellung der <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="b818b-154">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="b818b-155">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b818b-155">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="b818b-156">Wenn diese Methode `false` zurückgibt, wurden entweder die Abonnementeigenschaften in Schritt 3 falsch definiert, oder das Abonnement ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b818b-156">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="b818b-157">(Optional) Zum Ändern der Eigenschaften legen Sie einen neuen Wert für eine der <xref:Microsoft.SqlServer.Replication.TransSubscription> -Eigenschaften fest, die definiert werden können, und rufen Sie dann die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="b818b-157">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="b818b-158">(Optional) Um die neuen Einstellungen anzuzeigen, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> -Methode auf, um die Eigenschaften für das Abonnement erneut zu laden.</span><span class="sxs-lookup"><span data-stu-id="b818b-158">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="b818b-159">So zeigen Sie die Eigenschaften eines Pushabonnements für eine Mergeveröffentlichung an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="b818b-159">To view or modify properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b818b-160">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="b818b-160">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="b818b-161">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergeSubscription>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b818b-161">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="b818b-162">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>und <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="b818b-162">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b818b-163">Legen Sie <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für die Einstellung der <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="b818b-163">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="b818b-164">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b818b-164">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="b818b-165">Wenn diese Methode `false` zurückgibt, wurden entweder die Abonnementeigenschaften in Schritt 3 falsch definiert, oder das Abonnement ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b818b-165">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="b818b-166">(Optional) Zum Ändern der Eigenschaften legen Sie einen neuen Wert für eine der <xref:Microsoft.SqlServer.Replication.MergeSubscription> -Eigenschaften fest, die definiert werden können, und rufen Sie dann die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="b818b-166">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="b818b-167">(Optional) Um die neuen Einstellungen anzuzeigen, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> -Methode auf, um die Eigenschaften für das Abonnement erneut zu laden.</span><span class="sxs-lookup"><span data-stu-id="b818b-167">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b818b-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b818b-168">See Also</span></span>  
 <span data-ttu-id="b818b-169">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="b818b-169">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="b818b-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="b818b-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="b818b-171">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="b818b-171">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
