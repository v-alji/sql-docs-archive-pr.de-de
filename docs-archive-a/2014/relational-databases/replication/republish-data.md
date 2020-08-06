---
title: Erneutes Veröffentlichen von Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- republishing data
- publishing [SQL Server replication], Subscribers
- Subscribers [SQL Server replication], republishing data
ms.assetid: a1485cf4-b1c4-49e9-ab06-8ccfaad998f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1e4213266121b3bf55bf2857e15f71f1e94e301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608518"
---
# <a name="republish-data"></a><span data-ttu-id="303d9-102">Erneutes Veröffentlichen von Daten</span><span class="sxs-lookup"><span data-stu-id="303d9-102">Republish Data</span></span>
  <span data-ttu-id="303d9-103">In einem Wiederveröffentlichungsmodell sendet der Verleger Daten an einen Abonnenten, der diese wiederum für eine beliebige Anzahl von Abonnenten erneut veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="303d9-103">In a republishing model, the Publisher sends data to a Subscriber, which then republishes the data to any number of other Subscribers.</span></span> <span data-ttu-id="303d9-104">Dies ist hilfreich, wenn ein Verleger Daten an Abonnenten über eine langsame oder teure Kommunikationsverbindung senden muss.</span><span class="sxs-lookup"><span data-stu-id="303d9-104">This is useful when a Publisher must send data to Subscribers over a slow or expensive communications link.</span></span> <span data-ttu-id="303d9-105">Falls es eine Reihe von Abonnenten am äußersten Ende dieser Verbindung gibt, kann das Verwenden eines Neuverlegers einen Großteil der Verteilungslast auf diese Seite der Verbindung auslagern.</span><span class="sxs-lookup"><span data-stu-id="303d9-105">If there are a number of Subscribers on the far side of that link, using a republisher shifts the bulk of the distribution load to that side of the link.</span></span>  
  
 <span data-ttu-id="303d9-106">Das Wiederveröffentlichen von Daten umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="303d9-106">Republishing data involves the following steps:</span></span>  
  
1.  <span data-ttu-id="303d9-107">Erstellen einer Veröffentlichung auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="303d9-107">Create a publication at the Publisher.</span></span>  
  
2.  <span data-ttu-id="303d9-108">Erstellen eines Abonnements für die Veröffentlichung für den Wiederveröffentlichungsabonnenten.</span><span class="sxs-lookup"><span data-stu-id="303d9-108">Create a subscription to the publication for the republishing Subscriber.</span></span>  
  
3.  <span data-ttu-id="303d9-109">Initialisieren Sie das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="303d9-109">Initialize the subscription.</span></span> <span data-ttu-id="303d9-110">Das Abonnement muss initialisiert werden, bevor die Veröffentlichung auf dem Wiederveröffentlichungsabonnenten erstellt wird, sonst schlägt die Replikation fehl.</span><span class="sxs-lookup"><span data-stu-id="303d9-110">The subscription must be initialized before the publication is created at the republishing Subscriber, or replication will fail.</span></span>  
  
4.  <span data-ttu-id="303d9-111">Erstellen einer Veröffentlichung in der Abonnementdatenbank auf dem Wiederveröffentlichungsabonnenten.</span><span class="sxs-lookup"><span data-stu-id="303d9-111">Create a publication in the subscription database at the republishing Subscriber.</span></span>  
  
5.  <span data-ttu-id="303d9-112">Erstellen von Abonnements für die Veröffentlichung auf dem Wiederveröffentlichungsabonnenten für die andern Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="303d9-112">Create subscriptions to the publication at the republishing Subscriber for the other Subscribers.</span></span>  
  
6.  <span data-ttu-id="303d9-113">Initialisieren der Abonnements.</span><span class="sxs-lookup"><span data-stu-id="303d9-113">Initialize the subscriptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="303d9-114">Wenn Sie die Mergereplikation in einer Wiederveröffentlichungstopologie verwenden, müssen alle Wiederveröffentlichungsabonnenten Serverabonnements verwenden.</span><span class="sxs-lookup"><span data-stu-id="303d9-114">If you use merge replication in a republishing topology, all republishing Subscribers must use server subscriptions.</span></span> <span data-ttu-id="303d9-115">Weitere Informationen zu Abonnementtypen finden Sie unter [Abonnieren von Veröffentlichungen](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="303d9-115">For more information about subscription types, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
 <span data-ttu-id="303d9-116">In der folgenden Abbildung fungieren sowohl der Verleger als auch der Neuverleger als ihre eigenen lokalen Verteiler.</span><span class="sxs-lookup"><span data-stu-id="303d9-116">In the following illustration, both the Publisher and the republisher are acting as their own local Distributors.</span></span> <span data-ttu-id="303d9-117">Falls beide zum Verwenden eines Remoteverteilers eingerichtet würden, müssten sich alle Verteiler auf derselben Seite der langsamen oder teuren Kommunikationsverbindung wie ihr Verleger befinden.</span><span class="sxs-lookup"><span data-stu-id="303d9-117">If each were set up to use a remote Distributor, each Distributor would need to be on the same side of the slow or expensive communications link as its Publisher.</span></span> <span data-ttu-id="303d9-118">Verleger müssen mit Remoteverteilern über zuverlässige, sehr schnelle Kommunikationsverbindungen verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="303d9-118">Publishers must be connected to remote Distributors by reliable, high-speed communications links.</span></span>  
  
 <span data-ttu-id="303d9-119">![Wiederveröffentlichen von Daten](media/repl-06a.gif "Wiederveröffentlichen von Daten")</span><span class="sxs-lookup"><span data-stu-id="303d9-119">![Republishing data](media/repl-06a.gif "Republishing data")</span></span>  
  
 <span data-ttu-id="303d9-120">Jeder Server kann als Verleger und als Abonnent fungieren.</span><span class="sxs-lookup"><span data-stu-id="303d9-120">Any server can act as both a Publisher and Subscriber.</span></span> <span data-ttu-id="303d9-121">Nehmen Sie das folgende Diagramm als Beispiel. Es enthält die Veröffentlichung einer Tabelle in London, die an vier verschiedene Städte in den USA verteilt werden muss: Chicago, New York, San Diego und Seattle.</span><span class="sxs-lookup"><span data-stu-id="303d9-121">For example, consider the following diagram in which a publication of a table exists in London and must be distributed to four different cities in the United States: Chicago, New York, San Diego, and Seattle.</span></span> <span data-ttu-id="303d9-122">Der Server in New York wird ausgewählt, die aus London stammende veröffentlichte Tabelle zu abonnieren, da der Standort in New York die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="303d9-122">The server in New York is chosen to subscribe to the published table originating in London, because the New York site meets these conditions:</span></span>  
  
-   <span data-ttu-id="303d9-123">Die Netzwerkverbindung zurück nach London ist relativ zuverlässig.</span><span class="sxs-lookup"><span data-stu-id="303d9-123">The network link back to London is relatively reliable.</span></span>  
  
-   <span data-ttu-id="303d9-124">Die Kosten für die Kommunikation zwischen London und New York sind annehmbar.</span><span class="sxs-lookup"><span data-stu-id="303d9-124">The London-to-New York communication costs are acceptable.</span></span>  
  
-   <span data-ttu-id="303d9-125">Es gibt gute Netzwerk-Kommunikationsverbindungen von New York zu allen anderen Abonnentenstandorten in den USA.</span><span class="sxs-lookup"><span data-stu-id="303d9-125">There are good network communications lines from New York to all other Subscriber sites in the United States.</span></span>  
  
     <span data-ttu-id="303d9-126">![Wiederveröffentlichen von Daten für verteilte Standorte](media/repl-06.gif "Wiederveröffentlichen von Daten für verteilte Standorte")</span><span class="sxs-lookup"><span data-stu-id="303d9-126">![Republishing data to dispersed locations](media/repl-06.gif "Republishing data to dispersed locations")</span></span>  
  
 <span data-ttu-id="303d9-127">Die Replikation unterstützt die in der folgenden Tabelle aufgeführten Wiederveröffentlichungsszenarios.</span><span class="sxs-lookup"><span data-stu-id="303d9-127">Replication supports the republishing scenarios shown in the following table.</span></span>  
  
|<span data-ttu-id="303d9-128">Herausgeber</span><span class="sxs-lookup"><span data-stu-id="303d9-128">Publisher</span></span>|<span data-ttu-id="303d9-129">Veröffentlichungsabonnent</span><span class="sxs-lookup"><span data-stu-id="303d9-129">Publishing Subscriber</span></span>|<span data-ttu-id="303d9-130">Subscriber</span><span class="sxs-lookup"><span data-stu-id="303d9-130">Subscriber</span></span>|  
|---------------|---------------------------|----------------|  
|<span data-ttu-id="303d9-131">Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-131">Transactional publication</span></span>|<span data-ttu-id="303d9-132">Transaktionsabonnement/Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-132">Transactional subscription/transactional publication</span></span>|<span data-ttu-id="303d9-133">Transaktionsabonnement</span><span class="sxs-lookup"><span data-stu-id="303d9-133">Transactional subscription</span></span>|  
|<span data-ttu-id="303d9-134">Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-134">Transactional publication</span></span>|<span data-ttu-id="303d9-135">Transaktions Abonnement/Mergeveröffentlichung<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="303d9-135">Transactional subscription/merge publication<sup>1</sup></span></span>|<span data-ttu-id="303d9-136">Mergeabonnement</span><span class="sxs-lookup"><span data-stu-id="303d9-136">Merge subscription</span></span>|  
|<span data-ttu-id="303d9-137">Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-137">Merge publication</span></span>|<span data-ttu-id="303d9-138">Mergeabonnement/Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-138">Merge subscription/merge publication</span></span>|<span data-ttu-id="303d9-139">Mergeabonnement</span><span class="sxs-lookup"><span data-stu-id="303d9-139">Merge subscription</span></span>|  
|<span data-ttu-id="303d9-140">Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-140">Merge publication</span></span>|<span data-ttu-id="303d9-141">Mergeabonnement/Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="303d9-141">Merge subscription/transactional publication</span></span>|<span data-ttu-id="303d9-142">Transaktionsabonnement</span><span class="sxs-lookup"><span data-stu-id="303d9-142">Transactional subscription</span></span>|  
  
 <span data-ttu-id="303d9-143"><sup>1</sup> Sie sollten die- `@published_in_tran_pub` Eigenschaft für die Mergeveröffentlichung festlegen.</span><span class="sxs-lookup"><span data-stu-id="303d9-143"><sup>1</sup>You should set the `@published_in_tran_pub` property on the merge publication.</span></span> <span data-ttu-id="303d9-144">Standardmäßig wird bei der Transaktionsreplikation erwartet, dass Tabellen auf dem Abonnenten als schreibgeschützt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="303d9-144">By default, transactional replication expects tables at the Subscriber to be treated as read-only.</span></span> <span data-ttu-id="303d9-145">Wenn bei der Mergereplikation Datenänderungen an einer Tabelle in einem Transaktionsabonnement vorgenommen werden, kann eine Nichtkonvergenz von Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="303d9-145">If merge replication makes data changes to a table in a transactional subscription, non-convergence of data can occur.</span></span> <span data-ttu-id="303d9-146">Es empfiehlt sich, solche Tabellen in der Mergeveröffentlichung nur als herunterladbar anzugeben, um dieses Risiko zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="303d9-146">To avoid this risk, we recommend that any such table be specified as download-only in the merge publication.</span></span> <span data-ttu-id="303d9-147">Dadurch wird verhindert, dass ein Mergeabonnent Datenänderungen in die Tabelle hochlädt.</span><span class="sxs-lookup"><span data-stu-id="303d9-147">This prevents a merge Subscriber from uploading data changes to the table.</span></span> <span data-ttu-id="303d9-148">Weitere Informationen finden Sie unter [Optimieren der Leistung der Mergereplikation durch nur herunterladbare Artikel](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span><span class="sxs-lookup"><span data-stu-id="303d9-148">For more information, see [Optimize Merge Replication Performance with Download-Only Articles](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303d9-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="303d9-149">See Also</span></span>  
 <span data-ttu-id="303d9-150">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="303d9-150">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="303d9-151">[Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="303d9-151">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="303d9-152">[Abonnieren von Veröffentlichungen](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="303d9-152">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="303d9-153">[Initialize a Subscription](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="303d9-153">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="303d9-154">Synchronisieren von Daten</span><span class="sxs-lookup"><span data-stu-id="303d9-154">Synchronize Data</span></span>](synchronize-data.md)  
  
  
