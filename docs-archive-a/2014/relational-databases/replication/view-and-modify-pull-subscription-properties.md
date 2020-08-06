---
title: Anzeigen und Ändern der Eigenschaften von Pullabonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- modifying subscriptions
- viewing replication properties
- modifying replication properties, pull subscriptions
- pull subscriptions [SQL Server replication], modifying
- subscriptions [SQL Server replication], pull
- pull subscriptions [SQL Server replication], properties
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 1601e54f-86f0-49e8-b023-87a5d1def033
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b847a22d31bbf3ea7540c55339fe27531134125
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608506"
---
# <a name="view-and-modify-pull-subscription-properties"></a><span data-ttu-id="da7af-102">Anzeigen und Ändern der Eigenschaften von Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="da7af-102">View and Modify Pull Subscription Properties</span></span>
  <span data-ttu-id="da7af-103">In diesem Thema wird beschrieben, wie die Eigenschaften von Pullabonnements in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="da7af-103">This topic describes how to view and modify pull subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="da7af-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="da7af-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="da7af-105">**So können Sie Eigenschaften von Pullabonnements anzeigen und ändern mit:**</span><span class="sxs-lookup"><span data-stu-id="da7af-105">**To view and modify pull subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="da7af-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da7af-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="da7af-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da7af-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="da7af-108">Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="da7af-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="da7af-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da7af-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="da7af-110">Das Anzeigen der Eigenschaften von Pullabonnements vom Verleger oder Abonnenten aus ist über das Dialogfeld **Abonnementeigenschaften – \<Publisher>: \<PublicationDatabase>** möglich, das in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="da7af-110">View pull subscription properties from the Publisher or the Subscriber in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="da7af-111">Weitere Eigenschaften können vom Abonnenten aus angezeigt werden, und das Ändern der Eigenschaften ist auf dem Abonnenten möglich.</span><span class="sxs-lookup"><span data-stu-id="da7af-111">More properties are visible from the Subscriber, and properties can be modified at the Subscriber.</span></span> <span data-ttu-id="da7af-112">Das Anzeigen von Eigenschaften ist vom Verleger aus über die Registerkarte **Alle Abonnements** möglich, die im Replikationsmonitor verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="da7af-112">You can also view properties from the Publisher on the **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="da7af-113">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="da7af-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-management-studio"></a><span data-ttu-id="da7af-114">So zeigen Sie Eigenschaften von Pullabonnements vom Verleger aus in Management Studio an</span><span class="sxs-lookup"><span data-stu-id="da7af-114">To view pull subscription properties from the Publisher in Management Studio</span></span>  
  
1.  <span data-ttu-id="da7af-115">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="da7af-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="da7af-116">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="da7af-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="da7af-117">Erweitern Sie die entsprechende Veröffentlichung, klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="da7af-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="da7af-118">Zeigen Sie die Eigenschaften an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da7af-118">View properties, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-pull-subscription-properties-from-the-subscriber-in-management-studio"></a><span data-ttu-id="da7af-119">So zeigen Sie Eigenschaften von Pullabonnements vom Abonnent aus in Management Studio an und ändern sie</span><span class="sxs-lookup"><span data-stu-id="da7af-119">To view and modify pull subscription properties from the Subscriber in Management Studio</span></span>  
  
1.  <span data-ttu-id="da7af-120">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="da7af-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="da7af-121">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="da7af-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="da7af-122">Klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="da7af-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="da7af-123">Ändern Sie die Eigenschaften nach Bedarf, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da7af-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-replication-monitor"></a><span data-ttu-id="da7af-124">So zeigen Sie Eigenschaften von Pullabonnements vom Verleger aus im Replikationsmonitor an</span><span class="sxs-lookup"><span data-stu-id="da7af-124">To view pull subscription properties from the Publisher in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="da7af-125">Erweitern Sie im linken Bereich des Replikationsmonitors eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="da7af-125">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="da7af-126">Klicken Sie auf die Registerkarte **Alle Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="da7af-126">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="da7af-127">Klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="da7af-127">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="da7af-128">Zeigen Sie die Eigenschaften an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da7af-128">View properties, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="da7af-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da7af-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="da7af-130">Pullabonnements können geändert und auf ihre Eigenschaften kann mithilfe gespeicherter Replikationsprozeduren programmgesteuert zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="da7af-130">Pull subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="da7af-131">Welche gespeicherten Prozeduren verwendet werden, hängt vom Typ der Veröffentlichung ab, zu der das Abonnement gehört.</span><span class="sxs-lookup"><span data-stu-id="da7af-131">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="da7af-132">So zeigen Sie die Eigenschaften eines Pullabonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung an</span><span class="sxs-lookup"><span data-stu-id="da7af-132">To view the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="da7af-133">Führen Sie auf dem Abonnenten [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-133">At the Subscriber, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span></span> <span data-ttu-id="da7af-134">Geben Sie **@publisher** , **@publisher_db** und an **@publication** .</span><span class="sxs-lookup"><span data-stu-id="da7af-134">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="da7af-135">Dadurch werden Informationen über das Abonnement zurückgegeben, das in Systemtabellen beim Abonnenten gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="da7af-135">This returns information about the subscription that is stored in system tables at the Subscriber.</span></span>  
  
2.  <span data-ttu-id="da7af-136">Führen Sie auf dem Abonnenten [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-136">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="da7af-137">Geben Sie **@publisher** , **@publisher_db** , **@publication** und einen der folgenden Werte für an **@publication_type** :</span><span class="sxs-lookup"><span data-stu-id="da7af-137">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@publication_type**:</span></span>  
  
    -   <span data-ttu-id="da7af-138">**0** &ndash; Das Abonnement gehört zu einer Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="da7af-138">**0** - Subscription belongs to a transactional publication.</span></span>  
  
    -   <span data-ttu-id="da7af-139">**1** &ndash; Das Abonnement gehört zu einer Momentaufnahmeveröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="da7af-139">**1** - Subscription belongs to a snapshot publication.</span></span>  
  
3.  <span data-ttu-id="da7af-140">Führen Sie auf dem Verleger [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-140">At the Publisher, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="da7af-141">Geben Sie **@publication** und an **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="da7af-141">Specify **@publication** and **@subscriber**.</span></span>  
  
4.  <span data-ttu-id="da7af-142">Führen Sie [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql)auf dem Verleger aus, und geben Sie an **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="da7af-142">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="da7af-143">Dadurch werden Informationen zu dem Abonnenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da7af-143">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="da7af-144">So ändern Sie die Eigenschaften eines Pullabonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="da7af-144">To change the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="da7af-145">Führen Sie auf dem Abonnenten [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql)aus, **@publisher** und geben Sie dabei, **@publisher_db** , **@publication** , den Wert **0** (transaktional) oder **1** (Momentaufnahme) für **@publication_type** , die zu ändernde Abonnement Eigenschaft als **@property** und den neuen Wert als **@value** .</span><span class="sxs-lookup"><span data-stu-id="da7af-145">At the Subscriber, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specifying **@publisher**, **@publisher_db**, **@publication**, a value of either **0** (transactional) or **1** (snapshot) for **@publication_type**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
2.  <span data-ttu-id="da7af-146">(Optional) Führen Sie auf dem Abonnenten für die Abonnementdatenbank [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-146">(Optional) At the Subscriber on the subscription database, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span></span> <span data-ttu-id="da7af-147">Geben Sie die ID des Verteilungs-Agent Auftrags für **@jobid** und die folgenden DTS-Paket Eigenschaften (Data Transformation Services) an:</span><span class="sxs-lookup"><span data-stu-id="da7af-147">Specify the ID of the Distribution Agent job for **@jobid**, and the following Data Transformation Services (DTS) package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="da7af-148">Dadurch werden die DTS-Paketeigenschaften eines Abonnements geändert.</span><span class="sxs-lookup"><span data-stu-id="da7af-148">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da7af-149">Die Auftrag-ID erhalten Sie, wenn Sie [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql)ausführen.</span><span class="sxs-lookup"><span data-stu-id="da7af-149">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="da7af-150">So zeigen Sie die Eigenschaften eines Pullabonnements für eine Mergeveröffentlichung an</span><span class="sxs-lookup"><span data-stu-id="da7af-150">To view the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="da7af-151">Führen Sie auf dem Abonnenten [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-151">At the Subscriber, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="da7af-152">Geben Sie **@publisher** , **@publisher_db** und an **@publication** .</span><span class="sxs-lookup"><span data-stu-id="da7af-152">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span>  
  
2.  <span data-ttu-id="da7af-153">Führen Sie auf dem Abonnenten [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-153">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="da7af-154">Geben Sie **@publisher** , **@publisher_db** , und den **@publication** Wert 2 für an **@publication_type** .</span><span class="sxs-lookup"><span data-stu-id="da7af-154">Specify **@publisher**, **@publisher_db**, **@publication**, and a value of 2 for **@publication_type**.</span></span>  
  
3.  <span data-ttu-id="da7af-155">Führen Sie auf dem Verleger [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) aus, um Abonnementinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="da7af-155">At the Publisher, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) to display subscription information.</span></span> <span data-ttu-id="da7af-156">Zum Zurückgeben von Informationen zu einem bestimmten Abonnement müssen Sie **@publication** , **@subscriber** und den Wert **Pull** für angeben **@subscription_type** .</span><span class="sxs-lookup"><span data-stu-id="da7af-156">To return information on a specific subscription, you must specify **@publication**, **@subscriber**, and a value of **pull** for **@subscription_type**.</span></span>  
  
4.  <span data-ttu-id="da7af-157">Führen Sie [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql)auf dem Verleger aus, und geben Sie an **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="da7af-157">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="da7af-158">Dadurch werden Informationen zu dem Abonnenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da7af-158">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="da7af-159">So ändern Sie die Eigenschaften eines Pullabonnements für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="da7af-159">To change the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="da7af-160">Führen Sie auf dem Abonnenten [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="da7af-160">At the Subscriber, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span></span> <span data-ttu-id="da7af-161">Geben **@publication** **@publisher** Sie,, **@publisher_db** , die zu ändernde Abonnement Eigenschaft als **@property** und den neuen Wert als **@value** .</span><span class="sxs-lookup"><span data-stu-id="da7af-161">Specify **@publication**, **@publisher**, **@publisher_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="da7af-162">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="da7af-162">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="da7af-163">Die RMO-Klassen, mit denen Sie die Eigenschaften von Pullabonnements anzeigen oder ändern, hängen vom Typ der Veröffentlichung ab, für die das Pullabonnement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="da7af-163">The RMO classes you use to view or modify pull subscription properties depend on the type of publication to which the pull subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="da7af-164">So zeigen Sie die Eigenschaften eines Pullabonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="da7af-164">To view or modify properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="da7af-165">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="da7af-165">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="da7af-166">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransPullSubscription>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="da7af-166">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="da7af-167">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>und <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="da7af-167">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="da7af-168">Legen Sie die Verbindung aus Schritt 1 für die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="da7af-168">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="da7af-169">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da7af-169">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="da7af-170">Wenn diese Methode `false` zurückgibt, wurden entweder die Abonnementeigenschaften in Schritt 3 falsch definiert, oder das Abonnement ist auf dem Server nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="da7af-170">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="da7af-171">(Optional) Zum Ändern der Eigenschaften legen Sie einen neuen Wert für eine der <xref:Microsoft.SqlServer.Replication.TransPullSubscription> -Eigenschaften fest, die definiert werden können, und rufen Sie dann die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="da7af-171">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="da7af-172">(Optional) Um die neuen Einstellungen anzuzeigen, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> -Methode auf, um die Eigenschaften für den Artikel erneut zu laden.</span><span class="sxs-lookup"><span data-stu-id="da7af-172">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="da7af-173">Trennen Sie alle Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="da7af-173">Close all connections.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="da7af-174">So zeigen Sie die Eigenschaften eines Pullabonnements für eine Mergeveröffentlichung an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="da7af-174">To view or modify properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="da7af-175">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="da7af-175">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="da7af-176">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergePullSubscription>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="da7af-176">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="da7af-177">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>und <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="da7af-177">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="da7af-178">Legen Sie die Verbindung aus Schritt 1 für die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="da7af-178">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="da7af-179">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf, um die Eigenschaften des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da7af-179">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="da7af-180">Wenn diese Methode `false` zurückgibt, wurden entweder die Abonnementeigenschaften in Schritt 3 falsch definiert, oder das Abonnement ist auf dem Server nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="da7af-180">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="da7af-181">(Optional) Zum Ändern der Eigenschaften legen Sie einen neuen Wert für eine der <xref:Microsoft.SqlServer.Replication.MergePullSubscription> -Eigenschaften fest, die definiert werden können, und rufen Sie dann die <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="da7af-181">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="da7af-182">(Optional) Um die neuen Einstellungen anzuzeigen, rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> -Methode auf, um die Eigenschaften für den Artikel erneut zu laden.</span><span class="sxs-lookup"><span data-stu-id="da7af-182">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="da7af-183">Trennen Sie alle Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="da7af-183">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7af-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da7af-184">See Also</span></span>  
 <span data-ttu-id="da7af-185">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="da7af-185">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="da7af-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="da7af-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="da7af-187">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="da7af-187">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
