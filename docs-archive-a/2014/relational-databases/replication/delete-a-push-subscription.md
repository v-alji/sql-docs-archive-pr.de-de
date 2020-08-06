---
title: Löschen eines Pushabonnements |Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing subscriptions
- push subscriptions [SQL Server replication], deleting
- deleting subscriptions
- subscriptions [SQL Server replication], push
ms.assetid: 3c4847e2-aed9-4488-b45d-8164422bdb10
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 912958e00d117f51c5dc95c0dc1247d278acb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609132"
---
# <a name="delete-a-push-subscription"></a><span data-ttu-id="013e4-102">Löschen eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="013e4-102">Delete a Push Subscription</span></span>
  <span data-ttu-id="013e4-103">In diesem Thema wird beschrieben, wie ein Pushabonnement in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="013e4-103">This topic describes how to delete a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="013e4-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="013e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="013e4-105">**So löschen Sie ein Pushabonnement mit:**</span><span class="sxs-lookup"><span data-stu-id="013e4-105">**To delete a push subscription, using:**</span></span>  
  
     [<span data-ttu-id="013e4-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="013e4-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="013e4-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="013e4-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="013e4-108">Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="013e4-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="013e4-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="013e4-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="013e4-110">Ein Pushabonnement wird beim Verleger (im Ordner **Lokale Veröffentlichungen** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) oder beim Abonnenten (im Ordner **Lokale Abonnements** ) gelöscht.</span><span class="sxs-lookup"><span data-stu-id="013e4-110">Delete a push subscription at the Publisher (from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) or the Subscriber (from the **Local Subscriptions** folder).</span></span> <span data-ttu-id="013e4-111">Beim Löschen eines Abonnements werden keine Objekte oder Daten aus dem Abonnement entfernt, diese müssen manuell entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="013e4-111">Deleting a subscription does not remove objects or data from the subscription; they must be removed manually.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-publisher"></a><span data-ttu-id="013e4-112">So löschen Sie ein Pushabonnement beim Verleger</span><span class="sxs-lookup"><span data-stu-id="013e4-112">To delete a push subscription at the Publisher</span></span>  
  
1.  <span data-ttu-id="013e4-113">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="013e4-113">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="013e4-114">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="013e4-114">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="013e4-115">Erweitern Sie die Veröffentlichung, der das zu löschende Abonnement zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="013e4-115">Expand the publication associated with the subscription you want to delete.</span></span>  
  
4.  <span data-ttu-id="013e4-116">Klicken Sie mit der rechten Maustaste auf das Abonnement, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="013e4-116">Right-click the subscription, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="013e4-117">Wählen Sie im Bestätigungsdialogfeld aus, ob zum Löschen der Abonnementinformationen eine Verbindung mit dem Abonnenten hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="013e4-117">In the confirmation dialog box, select whether to connect to the Subscriber to delete subscription information.</span></span> <span data-ttu-id="013e4-118">Wenn Sie das Kontrollkästchen **Verbindung mit Abonnenten herstellen** deaktivieren, sollten Sie später eine Verbindung mit dem Abonnenten herstellen, um die Informationen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="013e4-118">If you clear the **Connect to Subscriber** checkbox, you should connect to the Subscriber later to delete the information.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-subscriber"></a><span data-ttu-id="013e4-119">So löschen Sie ein Pushabonnement auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="013e4-119">To delete a push subscription at the Subscriber</span></span>  
  
1.  <span data-ttu-id="013e4-120">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="013e4-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="013e4-121">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="013e4-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="013e4-122">Klicken Sie mit der rechten Maustaste auf das Abonnement, das Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="013e4-122">Right-click the subscription you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="013e4-123">Wählen Sie im Bestätigungsdialogfeld aus, ob zum Löschen der Abonnementinformationen eine Verbindung mit dem Verleger hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="013e4-123">In the confirmation dialog box, select whether to connect to the Publisher to delete subscription information.</span></span> <span data-ttu-id="013e4-124">Wenn Sie das Kontrollkästchen **Verbindung mit Verleger herstellen** deaktivieren, müssen Sie zum Löschen der Informationen später eine Verbindung mit dem Verleger herstellen.</span><span class="sxs-lookup"><span data-stu-id="013e4-124">If you clear the **Connect to Publisher** check box, you should connect to the Publisher later to delete the information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="013e4-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="013e4-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="013e4-126">Pushabonnements können mithilfe von gespeicherten Replikationsprozeduren programmgesteuert gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="013e4-126">Push subscriptions can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="013e4-127">Welche gespeicherten Prozeduren verwendet werden, hängt vom Typ der Veröffentlichung ab, zu der das Abonnement gehört.</span><span class="sxs-lookup"><span data-stu-id="013e4-127">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="013e4-128">So löschen Sie ein Pushabonnement für eine Momentaufnahme- oder Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="013e4-128">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="013e4-129">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="013e4-129">At the Publisher on the publication database, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span> <span data-ttu-id="013e4-130">Geben Sie **@publication** und an **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="013e4-130">Specify **@publication** and **@subscriber**.</span></span> <span data-ttu-id="013e4-131">Geben Sie für **@article** den Wert **@article**.</span><span class="sxs-lookup"><span data-stu-id="013e4-131">Specify a value of **all** for **@article**.</span></span> <span data-ttu-id="013e4-132">(Optional) Wenn auf den Verteiler nicht zugegriffen werden kann, geben Sie den Wert **1** den Wert **@ignore_distributor** an, um das Abonnement ohne die damit verbundenen Objekte auf dem Verteiler zu löschen.</span><span class="sxs-lookup"><span data-stu-id="013e4-132">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="013e4-133">Führen Sie auf dem Abonnenten für die Abonnementdatenbank [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) aus, um Replikationsmetadaten aus der Abonnementdatenbank zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="013e4-133">At the Subscriber on the subscription database, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="013e4-134">So löschen Sie ein Pushabonnement für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="013e4-134">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="013e4-135">Führen Sie auf dem Verleger [sp_dropmergesubscription &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql)aus, und geben Sie dabei **@publication** und an **@subscriber** **@subscriber_db** .</span><span class="sxs-lookup"><span data-stu-id="013e4-135">At the Publisher, execute [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specifying **@publication**, **@subscriber** and **@subscriber_db**.</span></span> <span data-ttu-id="013e4-136">(Optional) Wenn auf den Verteiler nicht zugegriffen werden kann, geben Sie den Wert **1** den Wert **@ignore_distributor** an, um das Abonnement ohne die damit verbundenen Objekte auf dem Verteiler zu löschen.</span><span class="sxs-lookup"><span data-stu-id="013e4-136">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="013e4-137">Führen Sie auf dem Abonnenten für die Abonnementdatenbank [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="013e4-137">At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span></span> <span data-ttu-id="013e4-138">Geben Sie **@publisher** , **@publisher_db** und an **@publication** .</span><span class="sxs-lookup"><span data-stu-id="013e4-138">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="013e4-139">Damit werden Mergemetadaten aus der Abonnementdatenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="013e4-139">This removes merge metadata from the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="013e4-140">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="013e4-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="013e4-141">Im folgenden Beispiel wird ein neues Pushabonnement für eine Transaktionsveröffentlichung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="013e4-141">This example deletes a push subscription to a transactional publication.</span></span>  
  
 [!code-sql[HowTo#sp_droptransubscription](../../snippets/tsql/SQL15/replication/howto/tsql/droptranpullsub.sql#sp_droptransubscription)]  
  
 <span data-ttu-id="013e4-142">Im folgenden Beispiel wird ein neues Pushabonnement für eine Mergeveröffentlichung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="013e4-142">This example deletes a push subscription to a merge publication.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergesubscription](../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepullsub.sql#sp_dropmergesubscription)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="013e4-143">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="013e4-143">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="013e4-144">Die RMO-Klassen, mit denen Sie ein Pushabonnement löschen, hängen vom Typ der Veröffentlichung ab, für die das Pushabonnement abonniert wird.</span><span class="sxs-lookup"><span data-stu-id="013e4-144">The RMO classes that you use to delete a push subscription depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="013e4-145">So löschen Sie ein Pushabonnement für eine Momentaufnahme- oder Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="013e4-145">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="013e4-146">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="013e4-146">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="013e4-147">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransSubscription>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="013e4-147">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="013e4-148">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>und <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="013e4-148">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="013e4-149">Legen Sie <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="013e4-149">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="013e4-150">Überprüfen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> -Eigenschaft, um festzustellen, ob das Abonnement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="013e4-150">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="013e4-151">Wenn der Wert dieser Eigenschaft `false` ist, wurden entweder die Abonnementeigenschaften in Schritt 2 falsch definiert, oder das Abonnement ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="013e4-151">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="013e4-152">Rufen Sie die <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="013e4-152">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="013e4-153">So löschen Sie ein Pushabonnement für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="013e4-153">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="013e4-154">Erstellen Sie eine Verbindung mit dem Abonnenten, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="013e4-154">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="013e4-155">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergeSubscription>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="013e4-155">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="013e4-156">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>und <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="013e4-156">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="013e4-157">Legen Sie <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="013e4-157">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="013e4-158">Überprüfen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> -Eigenschaft, um festzustellen, ob das Abonnement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="013e4-158">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="013e4-159">Wenn der Wert dieser Eigenschaft `false` ist, wurden entweder die Abonnementeigenschaften in Schritt 2 falsch definiert, oder das Abonnement ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="013e4-159">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="013e4-160">Rufen Sie die <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="013e4-160">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="013e4-161">Beispiele (RMO)</span><span class="sxs-lookup"><span data-stu-id="013e4-161">Examples (RMO)</span></span>  
 <span data-ttu-id="013e4-162">Sie können Pushabonnements mithilfe von Replikationsverwaltungsobjekten (RMO) programmgesteuert löschen.</span><span class="sxs-lookup"><span data-stu-id="013e4-162">You can delete push subscriptions programmatically by using Replication Management Objects (RMO).</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="013e4-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="013e4-163">See Also</span></span>  
 <span data-ttu-id="013e4-164">[Abonnieren von Veröffentlichungen](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="013e4-164">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="013e4-165">Bewährte Methoden für die Replikationssicherheit</span><span class="sxs-lookup"><span data-stu-id="013e4-165">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
