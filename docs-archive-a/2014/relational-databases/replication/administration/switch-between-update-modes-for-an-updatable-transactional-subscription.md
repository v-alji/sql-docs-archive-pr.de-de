---
title: Umschalten zwischen Updatemodi für ein aktualisierbares Transaktionsabonnement | Microsoft Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, update modes
- subscriptions [SQL Server replication], updatable
ms.assetid: ab5ebab1-7ee4-41f4-999b-b4f0c420c921
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c31814d1e2ab6fac64ffcde883f3cac2439828a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630635"
---
# <a name="switch-between-update-modes-for-an-updatable-transactional-subscription"></a><span data-ttu-id="2dc21-102">Umschalten zwischen Updatemodi für ein aktualisierbares Transaktionsabonnement</span><span class="sxs-lookup"><span data-stu-id="2dc21-102">Switch Between Update Modes for an Updatable Transactional Subscription</span></span>
  <span data-ttu-id="2dc21-103">In diesem Thema wird beschrieben, wie zwischen Updatemodi für ein aktualisierbares Transaktionsabonnement in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]umgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="2dc21-103">This topic describes how to switch between update modes for an updatable transaction subscription in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2dc21-104">Geben Sie im Assistenten für neue Abonnements den Modus für aktualisierbare Abonnements an.</span><span class="sxs-lookup"><span data-stu-id="2dc21-104">Specify the mode for updatable subscriptions using the New Subscription Wizard.</span></span> <span data-ttu-id="2dc21-105">Weitere Informationen zum Festlegen des Modus bei der Verwendung dieses Assistenten finden Sie unter [Anzeigen und Ändern der Eigenschaften von Pullabonnements](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2dc21-105">For information about setting the mode when using this wizard, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2dc21-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2dc21-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2dc21-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2dc21-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2dc21-108">Sie können jederzeit ein Failover vom sofortigen Aktualisieren zum verzögerten Aktualisieren ausführen.</span><span class="sxs-lookup"><span data-stu-id="2dc21-108">You can fail over from immediate to queued updating at any time.</span></span> <span data-ttu-id="2dc21-109">Danach können Sie erst wieder zum sofortigen Aktualisieren wechseln, wenn der Abonnent und der Verleger verbunden sind und der Warteschlangenlese-Agent alle ausstehenden Nachrichten in der Warteschlange auf den Verleger angewendet hat.</span><span class="sxs-lookup"><span data-stu-id="2dc21-109">After you do, however, you cannot return to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2dc21-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="2dc21-110">Recommendations</span></span>  
  
-   <span data-ttu-id="2dc21-111">Wenn ein Abonnement mit Aktualisierung mit einer Transaktionsveröffentlichung ein Failover von einem Aktualisierungsmodus zu einem anderen unterstützt, können Sie programmgesteuert den Aktualisierungsmodus wechseln, um Situationen zu bewältigen, in denen sich die Verbindung für eine kurze Zeitdauer ändert.</span><span class="sxs-lookup"><span data-stu-id="2dc21-111">When an updating subscription to a transactional publication supports failover from one updating mode to another, you can programmatically switch update modes to handle situations when connectivity changes for a short period of time.</span></span> <span data-ttu-id="2dc21-112">Der Updatemodus kann mithilfe gespeicherter Replikationsprozeduren programm- und bedarfsgesteuert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2dc21-112">The update mode can be set programmatically and on demand using replication stored procedures.</span></span> <span data-ttu-id="2dc21-113">Weitere Informationen finden Sie unter [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="2dc21-113">For more information, see [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2dc21-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2dc21-114">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2dc21-115">Damit der Updatemodus nach dem Erstellen des Abonnements geändert werden kann, muss beim Erstellen des Abonnements die **update_mode** -Eigenschaft auf **failover** (ermöglicht das Umschalten vom sofortigen Update auf das verzögerte Update) oder auf **queued failover** (ermöglicht das Umschalten vom verzögerten Update auf das sofortige Update) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2dc21-115">To change the update mode after the subscription is created, the **update_mode** property must be set to **failover** (which allows a switch from immediate updating to queued updating) or **queued failover** (which allows a switch from queued updating to immediate updating) when the subscription is created.</span></span> <span data-ttu-id="2dc21-116">Diese Eigenschaften werden im Assistenten für neue Abonnements automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2dc21-116">These properties are set automatically in the New Subscription Wizard.</span></span>  
  
#### <a name="to-set-the-updating-mode-for-a-push-subscription"></a><span data-ttu-id="2dc21-117">So legen Sie den Update für ein Pushabonnement fest</span><span class="sxs-lookup"><span data-stu-id="2dc21-117">To set the updating mode for a push subscription</span></span>  
  
1.  <span data-ttu-id="2dc21-118">Stellen Sie in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="2dc21-118">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="2dc21-119">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="2dc21-119">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="2dc21-120">Klicken Sie mit der rechten Maustaste auf das Abonnement, für das Sie den Updatemodus festlegen möchten, und klicken Sie dann auf **Updatemethode festlegen**.</span><span class="sxs-lookup"><span data-stu-id="2dc21-120">Right-click the subscription for which you want to set the update mode, and then click **Set Update Method**.</span></span>  
  
4.  <span data-ttu-id="2dc21-121">Wählen Sie im Dialogfeld **Updatemethode festlegen - \<Subscriber>: \<SubscriptionDatabase>** die Option **Sofortiges Aktualisieren** oder **Verzögertes Aktualisieren über eine Warteschlange** aus.</span><span class="sxs-lookup"><span data-stu-id="2dc21-121">In the **Set Update Method - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select **Immediate updating** or **Queued updating**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-set-the-updating-mode-for-a-pull-subscription"></a><span data-ttu-id="2dc21-122">So legen Sie den Updatemodus für ein Pullabonnement fest</span><span class="sxs-lookup"><span data-stu-id="2dc21-122">To set the updating mode for a pull subscription</span></span>  
  
1.  <span data-ttu-id="2dc21-123">Wählen Sie im Dialogfeld **Abonnementeigenschaften - \<Publisher>: \<PublicationDatabase>** für die Option **Updatemethode für Abonnent** den Wert **Änderungen sofort replizieren** oder **Änderungen in Warteschlange einreihen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dc21-123">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, select a value of **Immediately replicate changes** or **Queue changes** for the **Subscriber update method** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="2dc21-124">Weitere Informationen zum Zugreifen auf das Dialogfeld **Abonnementeigenschaften - \<Publisher>: \<PublicationDatabase>** finden Sie unter [Anzeigen und Ändern der Eigenschaften von Pullabonnements](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2dc21-124">For more information about accessing the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2dc21-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2dc21-125">Using Transact-SQL</span></span>  
  
#### <a name="to-switch-between-update-modes"></a><span data-ttu-id="2dc21-126">So wechseln Sie den Updatemodus</span><span class="sxs-lookup"><span data-stu-id="2dc21-126">To switch between update modes</span></span>  
  
1.  <span data-ttu-id="2dc21-127">Stellen Sie sicher, dass die Veröffentlichung das Failover unterstützt, indem Sie bei Pullabonnements [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) und bei Pushabonnements [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) ausführen.</span><span class="sxs-lookup"><span data-stu-id="2dc21-127">Verify that the subscription supports failover by executing [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) for a pull subscription or [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) for a push subscription.</span></span> <span data-ttu-id="2dc21-128">Wenn der Wert des **Updatemodus** im Resultset **3** oder **4**ist, wird das Failover unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2dc21-128">If the value of **update mode** in the result set is **3** or **4**, failover is supported.</span></span>  
  
2.  <span data-ttu-id="2dc21-129">Führen Sie auf dem Abonnenten für die Abonnementdatenbank [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="2dc21-129">At the Subscriber on the subscription database, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span></span> <span data-ttu-id="2dc21-130">Geben Sie **@publisher** , **@publisher_db** , **@publication** und einen der folgenden Werte für an **@failover_mode** :</span><span class="sxs-lookup"><span data-stu-id="2dc21-130">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@failover_mode**:</span></span>  
  
    -   <span data-ttu-id="2dc21-131">**queued** - Failover zum verzögerten Aktualisieren, wenn die Verbindung vorübergehend unterbrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="2dc21-131">**queued** - fail over to queued updating when connectivity has been temporarily lost.</span></span>  
  
    -   <span data-ttu-id="2dc21-132">**immediate** - Failover zum sofortigen Aktualisieren, wenn die Verbindung wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2dc21-132">**immediate** - fail over to immediate updating when connectivity has been restored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc21-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2dc21-133">See Also</span></span>  
 [<span data-ttu-id="2dc21-134">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="2dc21-134">Updatable Subscriptions for Transactional Replication</span></span>](../transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
