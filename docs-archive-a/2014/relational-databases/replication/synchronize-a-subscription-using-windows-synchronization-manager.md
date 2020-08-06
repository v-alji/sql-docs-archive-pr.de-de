---
title: Synchronisieren eines Abonnements mit der Synchronisierungs Verwaltung von Windows (Synchronisierungs Verwaltung von Windows) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], Windows Synchronization Manager
- Windows Synchronization Manager
ms.assetid: 80f15dd6-e84d-4f96-9866-5b34ea531f1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bb31c344f91c68b04e03dd218f22b09bec44830b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701024"
---
# <a name="synchronize-a-subscription-using-windows-synchronization-manager-windows-synchronization-manager"></a><span data-ttu-id="6be33-102">Synchronisieren eines Abonnements mithilfe der Synchronisierungsverwaltung von Windows (Synchronisierungsverwaltung von Windows)</span><span class="sxs-lookup"><span data-stu-id="6be33-102">Synchronize a Subscription Using Windows Synchronization Manager (Windows Synchronization Manager)</span></span>
  <span data-ttu-id="6be33-103">Die Synchronisierungsverwaltung von Windows[!INCLUDE[msCoName](../../includes/msconame-md.md)] kann nur zum Synchronisieren von Abonnements für Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Veröffentlichungen verwendet werden, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf demselben Computer ausgeführt wird wie die Synchronisierungsverwaltung. (Die Synchronisierungsverwaltung kann auch zum Synchronisieren von Offlinedateien und Webseiten verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="6be33-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager can only be used to synchronize subscriptions to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publications if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running on the same computer as Synchronization Manager (it can also be used to synchronize offline files and Web pages).</span></span> <span data-ttu-id="6be33-104">So verwenden Sie die Synchronisierungsverwaltung:</span><span class="sxs-lookup"><span data-stu-id="6be33-104">To use Synchronization Manager:</span></span>  
  
1.  <span data-ttu-id="6be33-105">Aktivieren Sie die Synchronisierung von Pullabonnements mithilfe der Windows-Synchronisierungsverwaltung im Dialogfeld **Abonnementeigenschaften - \<Subscriber>:\<SubscriptionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="6be33-105">Enable the synchronization of pull subscriptions with Windows Synchronization Manager in the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box.</span></span> <span data-ttu-id="6be33-106">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [Anzeigen und Ändern der Eigenschaften von Pullabonnements](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6be33-106">For more information about accessing this dialog box, see [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
2.  <span data-ttu-id="6be33-107">Greifen Sie über das Menü **Start** von Windows auf die Synchronisierungsverwaltung zu.</span><span class="sxs-lookup"><span data-stu-id="6be33-107">Access Synchronization Manager through the **Start** menu in Windows.</span></span>  
  
 <span data-ttu-id="6be33-108">Die Synchronisierungsverwaltung ermöglicht Ihnen die Verwendung des interaktiven Konfliktlösers für Mergeabonnements.</span><span class="sxs-lookup"><span data-stu-id="6be33-108">Synchronization Manager allows you to use the Interactive Resolver for merge subscriptions.</span></span> <span data-ttu-id="6be33-109">In der Regel werden Konflikte, die bei der Synchronisierung entdeckt werden, automatisch gelöst. Wenn der interaktive Konfliktlöser aktiviert ist, können Konflikte jedoch während der Synchronisierung von einem Benutzer gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="6be33-109">Typically, conflicts detected during synchronization are resolved automatically, but if interactive resolution is enabled, conflicts can be resolved by a user during synchronization.</span></span> <span data-ttu-id="6be33-110">Wenn die Synchronisierung nicht im Rahmen der Synchronisierungsverwaltung von Windows erfolgt (sondern als geplante Synchronisierung oder als bedarfsgesteuerte Synchronisierung in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder des Replikationsmonitors), werden Konflikte ohne Benutzereingriff automatisch gemäß dem Konfliktlöser gelöst, der für den Artikel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6be33-110">If a synchronization is performed outside of Windows Synchronization Manager (as a scheduled synchronization or an on demand synchronization in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Replication Monitor), conflicts are resolved automatically without user intervention, according to the resolver specified for the article.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6be33-111">Ab [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] und [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)]sind 64-Bit-Versionen der Synchronisierungsverwaltung von Windows nicht in der Lage, 32-Bit-Abonnements zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="6be33-111">Beginning with [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] and [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-bit versions of the Windows Synchronization Manager cannot detect 32-bit subscriptions.</span></span>  
  
### <a name="to-enable-the-synchronization-of-pull-subscriptions-with-windows-synchronization-manager"></a><span data-ttu-id="6be33-112">So aktivieren Sie die Synchronisierung von Pullabonnements mithilfe der Synchronisierungsverwaltung von Windows</span><span class="sxs-lookup"><span data-stu-id="6be33-112">To enable the synchronization of pull subscriptions with Windows Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="6be33-113">Wählen Sie auf der Seite **Allgemein** im Dialogfeld **Abonnementeigenschaften - \<Subscriber>: \<SubscriptionDatabase>** für die Option **Synchronisierungsverwaltung von Windows verwenden** den Wert **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6be33-113">On the **General** page of the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select a value of **Enable** for the **Use Windows Synchronization Manager** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-synchronize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="6be33-114">So synchronisieren Sie ein Pullabonnement mit der Synchronisierungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6be33-114">To synchronize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="6be33-115">Starten Sie die Synchronisierungsverwaltung mithilfe einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="6be33-115">Launch Synchronization Manager using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="6be33-116">Klicken Sie in Internet Explorer auf das Menü **Extras**und anschließend auf **Synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="6be33-116">In Internet Explorer, click **Tools**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="6be33-117">Klicken Sie auf **Start**, zeigen Sie auf **Programme** oder **Alle Programme**, zeigen Sie auf **Zubehör**, und klicken Sie dann auf **Synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="6be33-117">Click **Start**, point to **Programs** or **All Programs**, point to **Accessories**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="6be33-118">Klicken Sie auf **Start**und anschließend auf **Ausführen**</span><span class="sxs-lookup"><span data-stu-id="6be33-118">Click **Start**, and then click **Run.**</span></span> <span data-ttu-id="6be33-119">Geben Sie im Dialogfeld **Ausführen** `mobsync.exe` das Feld **Öffnen** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6be33-119">In the **Run** dialog box, type `mobsync.exe` in the **Open** field, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="6be33-120">Wählen Sie im Dialogfeld **Zu synchronisierende Objekte** die Abonnements aus, die Sie synchronisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6be33-120">In the **Items to Synchronize** dialog box, select the subscriptions to synchronize.</span></span> <span data-ttu-id="6be33-121">Die Abonnements werden unter den auf dem Computer installierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6be33-121">Subscriptions are listed under the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
3.  <span data-ttu-id="6be33-122">Klicken Sie auf **Synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="6be33-122">Click **Synchronize**.</span></span>  
  
### <a name="to-reinitialize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="6be33-123">So initialisieren Sie ein Pullabonnement mit der Synchronisierungsverwaltung erneut</span><span class="sxs-lookup"><span data-stu-id="6be33-123">To reinitialize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="6be33-124">Wählen Sie im Dialogfeld **Zu synchronisierende Objekte** ein Abonnement aus, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6be33-124">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6be33-125">Klicken Sie im Dialogfeld **SQL Server-Abonnementeigenschaften** auf **Abonnement erneut initialisieren**.</span><span class="sxs-lookup"><span data-stu-id="6be33-125">In the **SQL Server Subscription Properties** dialog box, click **Reinitialize Subscription**.</span></span>  
  
3.  <span data-ttu-id="6be33-126">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6be33-126">Click **Yes**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="6be33-127">Beim nächsten Synchronisieren des Abonnements wird standardmäßig eine neue Momentaufnahme auf die Abonnementdatenbank angewendet.</span><span class="sxs-lookup"><span data-stu-id="6be33-127">The next time the subscription is synchronized, by default a new snapshot is applied to the subscription database.</span></span> <span data-ttu-id="6be33-128">Weitere Informationen finden Sie unter [Erneutes Initialisieren von Abonnements](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6be33-128">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6be33-129">Bei der Mergereplikation können ausstehende Änderungen auf den Verleger hochgeladen werden, bevor die Momentaufnahme angewendet wird. Diese Option ist jedoch nicht in der Synchronisierungsverwaltung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6be33-129">Merge replication allows any outstanding changes to be uploaded to the Publisher before the snapshot is applied, but this option is not available from Synchronization Manager.</span></span> <span data-ttu-id="6be33-130">Synchronisieren Sie zum Hochladen von Änderungen das Abonnement, bevor Sie es erneut initialisieren.</span><span class="sxs-lookup"><span data-stu-id="6be33-130">To upload changes, synchronize the subscription before reinitializing it.</span></span>  
  
### <a name="to-set-properties-for-a-pull-subscription-in-synchronization-manager"></a><span data-ttu-id="6be33-131">So legen Sie Eigenschaften für ein Pullabonnement in der Synchronisierungsverwaltung fest</span><span class="sxs-lookup"><span data-stu-id="6be33-131">To set properties for a pull subscription in Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="6be33-132">Wählen Sie im Dialogfeld **Zu synchronisierende Objekte** ein Abonnement aus, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6be33-132">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6be33-133">Sie können Eigenschaften auf den folgenden Registerkarten anzeigen und ändern:</span><span class="sxs-lookup"><span data-stu-id="6be33-133">View and modify properties on the following tabs:</span></span>  
  
    -   <span data-ttu-id="6be33-134">**Identifikation**</span><span class="sxs-lookup"><span data-stu-id="6be33-134">**Identification**</span></span>  
  
    -   <span data-ttu-id="6be33-135">**Abonnentenanmeldung**, **Verteileranmeldung**und **Verlegeranmeldung** (nur für die Mergereplikation)</span><span class="sxs-lookup"><span data-stu-id="6be33-135">**Subscriber Login**, **Distributor Login**, and **Publisher Login** (for merge replication only)</span></span>  
  
    -   <span data-ttu-id="6be33-136">**Webserverinformationen** (für Mergeabonnements auf Abonnenten, auf denen SQL Server 2005 oder höher ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="6be33-136">**Web Server Information** (for merge subscriptions on Subscribers running SQL Server 2005 or later)</span></span>  
  
    -   <span data-ttu-id="6be33-137">**Andere**</span><span class="sxs-lookup"><span data-stu-id="6be33-137">**Other**</span></span>  
  
     <span data-ttu-id="6be33-138">Die Verwendung der Windows-Authentifizierung wird für alle Verbindungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="6be33-138">It is recommended to use Windows Authentication for all connections.</span></span> <span data-ttu-id="6be33-139">Informationen zu den Berechtigungen, die der Verteilungs-Agent und der Merge-Agent benötigen, finden Sie unter [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="6be33-139">For information about the permissions required by the Distribution Agent and the Merge Agent, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-pull-subscription-from-synchronization-manager"></a><span data-ttu-id="6be33-140">So entfernen Sie ein Pullabonnement aus der Synchronisierungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6be33-140">To remove a pull subscription from Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="6be33-141">Wählen Sie im Dialogfeld **Zu synchronisierende Objekte** ein Abonnement aus, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6be33-141">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6be33-142">Klicken Sie im Dialogfeld **SQL Server-Abonnementeigenschaften** auf **Abonnement entfernen**.</span><span class="sxs-lookup"><span data-stu-id="6be33-142">In the **SQL Server Subscription Properties** dialog box, click **Remove Subscription**.</span></span>  
  
3.  <span data-ttu-id="6be33-143">Wählen Sie im Dialogfeld **Abonnement entfernen** eine Option aus.</span><span class="sxs-lookup"><span data-stu-id="6be33-143">Select an option in the **Remove Subscription** dialog box.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-interactive-resolver"></a><span data-ttu-id="6be33-144">So verwenden Sie den interaktiven Konfliktlöser</span><span class="sxs-lookup"><span data-stu-id="6be33-144">To use the Interactive Resolver</span></span>  
  
1.  <span data-ttu-id="6be33-145">Aktivieren Sie die Verwendung des interaktiven Konfliktlösers für den Artikel und das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="6be33-145">Enable the article and subscription to use interactive resolution.</span></span> <span data-ttu-id="6be33-146">Weitere Informationen finden Sie unter [Angeben von interaktiver Konfliktauflösung von Mergeartikeln](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span><span class="sxs-lookup"><span data-stu-id="6be33-146">For more information, see [Specify Interactive Conflict Resolution for Merge Articles](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span></span>
  
2.  <span data-ttu-id="6be33-147">Mit dem Beginn der Synchronisierung des Abonnements in der Synchronisierungsverwaltung wird der interaktive Konfliktlöser automatisch gestartet, wenn der interaktive Konfliktlöser aktiviert ist und bei einem oder mehreren Artikeln Konflikte bestehen.</span><span class="sxs-lookup"><span data-stu-id="6be33-147">After the subscription begins synchronizing in Synchronization Manager, the Interactive Resolver launches automatically if interactive conflict resolution is enabled and there are conflicts for one or more articles.</span></span> <span data-ttu-id="6be33-148">Der interaktive Konfliktlöser zeigt die Konflikte jeweils nacheinander an und schlägt eine Lösung für jeden Konflikt vor (basierend auf dem bei der Erstellung der Veröffentlichung und des Abonnements angegebenen Konfliktlösers).</span><span class="sxs-lookup"><span data-stu-id="6be33-148">The Interactive Resolver displays conflicts one at a time, with a suggested resolution for each conflict (based on the resolver specified when the publication and subscription were created).</span></span>  
  
3.  <span data-ttu-id="6be33-149">Sie können die im interaktiven Konfliktlöser angezeigten Spalten auch beliebig bearbeiten und dann auf eine der folgenden Schaltflächen klicken, um den Konflikt zu lösen:</span><span class="sxs-lookup"><span data-stu-id="6be33-149">Optionally edit any of the columns displayed in the Interactive Resolver, and then click one of the following buttons to resolve the conflict:</span></span>  
  
    -   <span data-ttu-id="6be33-150">**Vorschläge akzeptieren**</span><span class="sxs-lookup"><span data-stu-id="6be33-150">**Accept Suggested**</span></span>  
  
    -   <span data-ttu-id="6be33-151">**Verleger akzeptieren**</span><span class="sxs-lookup"><span data-stu-id="6be33-151">**Accept Publisher**</span></span>  
  
    -   <span data-ttu-id="6be33-152">**Abonnenten akzeptieren**</span><span class="sxs-lookup"><span data-stu-id="6be33-152">**Accept Subscriber**</span></span>  
  
    -   <span data-ttu-id="6be33-153">**Alle automatisch lösen** (alle aktuellen Konflikte werden ohne weitere Eingaben gelöst)</span><span class="sxs-lookup"><span data-stu-id="6be33-153">**Resolve All Automatically** (all current conflicts are resolved without further input)</span></span>  
  
     <span data-ttu-id="6be33-154">Die ausgewählte Zeile wird dann auf den Verleger und/oder Abonnenten angewendet. Bei folgenden Synchronisierungen wird die Zeile an andere Knoten der Topologie weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="6be33-154">The selected row is then applied to the Publisher and/or Subscriber; it is propagated to other nodes in the topology during subsequent synchronizations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6be33-155">Bearbeitungen werden nur dann angewendet, wenn sie zur Zeile gehören, die für die Lösung ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="6be33-155">Edits are only applied if they are part of the row that is chosen for resolution.</span></span> <span data-ttu-id="6be33-156">Wenn Sie z. B. Bearbeitungen unter **Verleger**vornehmen und dann auf **Abonnenten akzeptieren**klicken, werden die Bearbeitungen verworfen.</span><span class="sxs-lookup"><span data-stu-id="6be33-156">For example, if you make edits under **Publisher**, and then click **Accept Subscriber**, the edits are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be33-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6be33-157">See Also</span></span>  
 [<span data-ttu-id="6be33-158">Interactive Conflict Resolution</span><span class="sxs-lookup"><span data-stu-id="6be33-158">Interactive Conflict Resolution</span></span>](merge/advanced-merge-replication-conflict-interactive-resolution.md)  
  
