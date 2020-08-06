---
title: Festlegen des Ablaufdatums für Abonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc0ecb449af64b88cf3ded032c78c2e399dd4234
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618648"
---
# <a name="set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="b3af3-102">Festlegen des Ablaufdatums für Abonnements</span><span class="sxs-lookup"><span data-stu-id="b3af3-102">Set the Expiration Period for Subscriptions</span></span>
  <span data-ttu-id="b3af3-103">In diesem Thema wird beschrieben, wie der Ablaufzeitraum für Abonnements in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b3af3-103">This topic describes how to set the expiration period for subscriptions in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b3af3-104">Der Ablaufzeitraum für Abonnements bestimmt den Zeitraum, bevor ein Abonnement abläuft und entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b3af3-104">The expiration period for subscriptions determines the period of time before a subscription expires and is removed.</span></span> <span data-ttu-id="b3af3-105">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="b3af3-105">For more information, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="b3af3-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b3af3-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b3af3-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b3af3-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b3af3-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b3af3-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="b3af3-109">**So legen Sie das Ablaufdatum für Abonnements fest mit:**</span><span class="sxs-lookup"><span data-stu-id="b3af3-109">**To set the expiration period for subscriptions, using:**</span></span>  
  
     [<span data-ttu-id="b3af3-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b3af3-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b3af3-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b3af3-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b3af3-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b3af3-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b3af3-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b3af3-113">Recommendations</span></span>  
  
-   <span data-ttu-id="b3af3-114">Das Abonnementablaufdatum wird auch als *Beibehaltungsdauer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b3af3-114">The subscription expiration period is also referred to as the *publication retention period*.</span></span> <span data-ttu-id="b3af3-115">Der Cleanup von Mergereplikationsmetadaten wird durch diese Einstellung bestimmt:</span><span class="sxs-lookup"><span data-stu-id="b3af3-115">Cleanup of merge replication metadata is dependent on this setting:</span></span>  
  
    -   <span data-ttu-id="b3af3-116">Die Replikation kann der Cleanup von Metadaten aus den Veröffentlichungs- und Abonnementdatenbanken erst ausführen, wenn das Ablaufdatum erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="b3af3-116">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="b3af3-117">Geben Sie keinen zu hohen Wert für die Beibehaltungsdauer an, da dies zu einer Beeinträchtigung der Replikationsleistung führen kann.</span><span class="sxs-lookup"><span data-stu-id="b3af3-117">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="b3af3-118">Es wird empfohlen, eine niedrigere Einstellung zu verwenden, wenn Sie zuverlässig einschätzen können, dass alle Abonnenten innerhalb dieser Zeitspanne regelmäßig synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b3af3-118">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
         <span data-ttu-id="b3af3-119">Die Beibehaltungsdauer für Mergeveröffentlichungen weist eine 24-stündige Kulanzfrist auf, um Abonnenten in unterschiedlichen Zeitzonen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b3af3-119">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="b3af3-120">Wenn Sie beispielsweise eine Beibehaltungsdauer von einem Tag festgelegt haben, beträgt die tatsächliche Beibehaltungsdauer 48 Stunden.</span><span class="sxs-lookup"><span data-stu-id="b3af3-120">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
    -   <span data-ttu-id="b3af3-121">Es ist möglich, anzugeben, dass Abonnements nie ablaufen. Es wird jedoch nachdrücklich empfohlen, diesen Wert nicht zu verwenden, da sonst kein Cleanup der Metadaten ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3af3-121">It is possible to specify that subscriptions never expire, but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b3af3-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b3af3-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b3af3-123">Geben Sie auf der Seite **Allgemein** das Ablaufdatum von Abonnements im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-123">Set the expiration period for subscriptions on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="b3af3-124">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b3af3-124">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="b3af3-125">So legen Sie das Ablaufdatum für Abonnements fest</span><span class="sxs-lookup"><span data-stu-id="b3af3-125">To set the expiration period for subscriptions</span></span>  
  
1.  <span data-ttu-id="b3af3-126">Geben Sie im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** auf der Seite **Allgemein** im Bereich **Ablaufdatum für das Abonnement** an, ob Abonnements ablaufen sollen.</span><span class="sxs-lookup"><span data-stu-id="b3af3-126">In the **Subscription expiration** section on the **General** page of the **Publication Properties - \<Publication>** dialog box, specify whether subscriptions should expire.</span></span>  
  
2.  <span data-ttu-id="b3af3-127">Falls dies der Fall ist, geben Sie die Dauer an, nach der Abonnements ablaufen sollen.</span><span class="sxs-lookup"><span data-stu-id="b3af3-127">If they should expire, specify an expiration time period.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b3af3-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b3af3-128">Using Transact-SQL</span></span>  
 <span data-ttu-id="b3af3-129">Sie können gespeicherte Replikationsprozeduren dazu verwenden, diesen Wert festzulegen, wenn eine Veröffentlichung erstellt wird, und diesen Wert zu einem späteren Zeitpunkt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b3af3-129">You can use replication stored procedures to either set this value when a publication is created or modify this value at a later time.</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b3af3-130">So legen Sie den Ablaufzeitraum eines Abonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung fest</span><span class="sxs-lookup"><span data-stu-id="b3af3-130">To set the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b3af3-131">Führen Sie auf dem Verleger [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b3af3-131">At the Publisher, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span> <span data-ttu-id="b3af3-132">Geben Sie für **\@retention** den gewünschten Ablaufzeitraum für das Abonnement in Stunden an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-132">Specify the desired subscription expiration period, in hours, for **\@retention**.</span></span> <span data-ttu-id="b3af3-133">Der Standardablaufzeitraum beträgt 336 Stunden.</span><span class="sxs-lookup"><span data-stu-id="b3af3-133">The default expiration period is 336 hours.</span></span> <span data-ttu-id="b3af3-134">Weitere Informationen finden Sie unter [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="b3af3-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="b3af3-135">So legen Sie den Ablaufzeitraum eines Abonnements für eine Mergeveröffentlichung fest</span><span class="sxs-lookup"><span data-stu-id="b3af3-135">To set the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b3af3-136">Führen Sie auf dem Verleger [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b3af3-136">At the Publisher, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span> <span data-ttu-id="b3af3-137">Geben Sie für **\@retention** den gewünschten Wert für den Ablaufzeitraum des Abonnements an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-137">Specify the desired value for the subscription expiration period for **\@retention**.</span></span> <span data-ttu-id="b3af3-138">Geben Sie für **\@retention_period_unit** die Einheiten an, in denen der Ablaufzeitraum ausgedrückt wird. Es stehen die folgenden Werte zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="b3af3-138">Specify the units in which the expiration period is expressed for **\@retention_period_unit**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="b3af3-139">**1** = Woche</span><span class="sxs-lookup"><span data-stu-id="b3af3-139">**1** = week</span></span>  
  
    -   <span data-ttu-id="b3af3-140">**2** = Monat</span><span class="sxs-lookup"><span data-stu-id="b3af3-140">**2** = month</span></span>  
  
    -   <span data-ttu-id="b3af3-141">**3** = Jahr</span><span class="sxs-lookup"><span data-stu-id="b3af3-141">**3** = year</span></span>  
  
     <span data-ttu-id="b3af3-142">Der Standardablaufzeitraum beträgt 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="b3af3-142">The default expiration period is 14 days.</span></span> <span data-ttu-id="b3af3-143">Weitere Informationen finden Sie unter [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="b3af3-143">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b3af3-144">So ändern Sie den Ablaufzeitraum eines Abonnements für eine Momentaufnahme- oder eine Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="b3af3-144">To change the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b3af3-145">Führen Sie auf dem Verleger [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b3af3-145">At the Publisher, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span> <span data-ttu-id="b3af3-146">Geben Sie **retention** für **\@property** und den neuen Abonnementablaufzeitraum in Stunden für **\@value** an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-146">Specify **retention** for **\@property** and the new subscription expiration period, in hours, for **\@value**.</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="b3af3-147">So ändern Sie den Ablaufzeitraum eines Abonnements für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="b3af3-147">To change the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="b3af3-148">Führen Sie auf dem Verleger [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql) aus, und geben Sie dazu **\@publication** und **\@publisher** an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-148">At the Publisher, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying **\@publication** and **\@publisher**.</span></span> <span data-ttu-id="b3af3-149">Der Wert von **retention_period_unit** im Resultset ist einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="b3af3-149">Note the value of **retention_period_unit** in the result set, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="b3af3-150">**0** = Tag</span><span class="sxs-lookup"><span data-stu-id="b3af3-150">**0** = day</span></span>  
  
    -   <span data-ttu-id="b3af3-151">**1** = Woche</span><span class="sxs-lookup"><span data-stu-id="b3af3-151">**1** = week</span></span>  
  
    -   <span data-ttu-id="b3af3-152">**2** = Monat</span><span class="sxs-lookup"><span data-stu-id="b3af3-152">**2** = month</span></span>  
  
    -   <span data-ttu-id="b3af3-153">**3** = Jahr</span><span class="sxs-lookup"><span data-stu-id="b3af3-153">**3** = year</span></span>  
  
2.  <span data-ttu-id="b3af3-154">Führen Sie auf dem Verleger [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b3af3-154">At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="b3af3-155">Geben Sie **retention** für **\@property** und den neuen Abonnementablaufzeitraum als Text, der auf der Einheit für die Beibehaltungsdauer aus Schritt 1 basiert, für **\@value** an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-155">Specify **retention** for **\@property** and the new subscription expiration period, as text based on the retention period unit from step 1, for **\@value**.</span></span>  
  
3.  <span data-ttu-id="b3af3-156">(Optional) Führen Sie auf dem Verleger [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b3af3-156">(Optional) At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="b3af3-157">Geben Sie **retention_period_unit** für **\@property** und eine neue Einheit für den Abonnementablaufzeitraum für **\@value** an.</span><span class="sxs-lookup"><span data-stu-id="b3af3-157">Specify **retention_period_unit** for **\@property** and a new unit for the subscription expiration period for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3af3-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3af3-158">See Also</span></span>  
 <span data-ttu-id="b3af3-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="b3af3-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="b3af3-160">Abonnementablauf und -deaktivierung</span><span class="sxs-lookup"><span data-stu-id="b3af3-160">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
