---
title: Synchronisieren von Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], about synchronization
- merge replication synchronization [SQL Server replication]
- scripts [SQL Server replication], synchronization and
- synchronization [SQL Server replication]
- snapshot replication [SQL Server], synchronization
- transactional replication, synchronization
- subscriptions [SQL Server replication], synchronizing
- on demand script execution
- replication [SQL Server], synchronization
- scripts [SQL Server replication]
ms.assetid: 724802f7-7d69-46d3-a330-bd8aa7f53114
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c92cc4d1ae8e836f169a731ecf3c37c81f3dbf10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701013"
---
# <a name="synchronize-data"></a><span data-ttu-id="74b61-102">Synchronisieren von Daten</span><span class="sxs-lookup"><span data-stu-id="74b61-102">Synchronize Data</span></span>
  <span data-ttu-id="74b61-103">Das Synchronisieren von Daten bezieht sich auf den Prozess des Weitergebens von Daten- und Schemaänderungen zwischen dem Verleger und Abonnenten, nachdem die Anfangsmomentaufnahme auf dem Abonnenten angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="74b61-103">Synchronizing data refers to the process of data and schema changes being propagated between the Publisher and Subscribers after the initial snapshot has been applied at the Subscriber.</span></span> <span data-ttu-id="74b61-104">Die Synchronisierung kann auf verschiedene Weise ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="74b61-104">Synchronization can occur:</span></span>  
  
-   <span data-ttu-id="74b61-105">Fortlaufend, was typisch für die Transaktionsreplikation ist.</span><span class="sxs-lookup"><span data-stu-id="74b61-105">Continuously, which is typical for transactional replication.</span></span>  
  
-   <span data-ttu-id="74b61-106">Bedarfsgesteuert, was typisch für die Mergereplikation ist.</span><span class="sxs-lookup"><span data-stu-id="74b61-106">On demand, which is typical for merge replication.</span></span>  
  
-   <span data-ttu-id="74b61-107">Nach einem Zeitplan, was typisch für die Momentaufnahmereplikation ist.</span><span class="sxs-lookup"><span data-stu-id="74b61-107">On a schedule, which is typical for snapshot replication.</span></span>  
  
 <span data-ttu-id="74b61-108">Wenn ein Abonnement synchronisiert wird, werden basierend auf dem verwendeten Replikationstyp verschiedene Prozesse ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="74b61-108">When a subscription is synchronized, different processes occur based on the type of replication you are using:</span></span>  
  
-   <span data-ttu-id="74b61-109">Momentaufnahmereplikation.</span><span class="sxs-lookup"><span data-stu-id="74b61-109">Snapshot replication.</span></span> <span data-ttu-id="74b61-110">Synchronisieren bedeutet, dass der Verteilungs-Agent die Momentaufnahme erneut auf dem Abonnenten anwendet, sodass Schema und Daten in der Abonnementdatenbank mit der Veröffentlichungsdatenbank übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="74b61-110">Synchronization means that the Distribution Agent reapplies the snapshot at the Subscriber so that schema and data at the subscription database is consistent with the publication database.</span></span>  
  
     <span data-ttu-id="74b61-111">Wenn Änderungen an den Daten oder dem Schema auf dem Verleger vorgenommen wurden, muss für die Weitergabe der Änderungen an den Abonnenten eine neue Momentaufnahme generiert werden.</span><span class="sxs-lookup"><span data-stu-id="74b61-111">If modifications to data or schema have been made at the Publisher, a new snapshot must be generated in order to propagate modifications to the Subscriber.</span></span>  
  
-   <span data-ttu-id="74b61-112">Transaktionsreplikation.</span><span class="sxs-lookup"><span data-stu-id="74b61-112">Transactional replication.</span></span> <span data-ttu-id="74b61-113">Synchronisieren bedeutet, dass der Verteilungs-Agent Updates, Einfügungen, Löschungen und andere Änderungen von der Verteilungsdatenbank auf den Abonnenten überträgt.</span><span class="sxs-lookup"><span data-stu-id="74b61-113">Synchronization means that the Distribution Agent transfers updates, inserts, deletes, and any other changes from the distribution database to the Subscriber.</span></span>  
  
-   <span data-ttu-id="74b61-114">Mergereplikation.</span><span class="sxs-lookup"><span data-stu-id="74b61-114">Merge replication.</span></span> <span data-ttu-id="74b61-115">Synchronisieren bedeutet, dass der Merge-Agent Änderungen vom Abonnenten auf den Verleger hochlädt und dann die Änderungen vom Verleger auf den Abonnenten herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="74b61-115">Synchronization means that the Merge Agent uploads changes from the Subscriber to the Publisher and then downloads changes from the Publisher to the Subscriber.</span></span> <span data-ttu-id="74b61-116">Eventuelle Konflikte werden erkannt und gelöst.</span><span class="sxs-lookup"><span data-stu-id="74b61-116">Conflicts, if any, are detected and resolved.</span></span> <span data-ttu-id="74b61-117">Die Daten werden konvergiert, sodass der Verleger und die Abonnenten schließlich die gleichen Datenwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="74b61-117">Data is converged, and the Publisher and all Subscribers eventually end up with the same data values.</span></span> <span data-ttu-id="74b61-118">Wenn Konflikte erkannt und gelöst wurden, bedeutet das, dass Arbeiten, die einige der Benutzer ausgeführt haben, so geändert worden sind, dass der Konflikt entsprechend der von Ihnen definierten Richtlinien gelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="74b61-118">If conflicts were detected and resolved, work that was committed by some of the users is changed to resolve the conflict according to policies you define.</span></span>  
  
 <span data-ttu-id="74b61-119">Durch Momentaufnahmeveröffentlichungen wird das Schema auf dem Abonnenten bei jeder Synchronisierung vollständig aktualisiert, sodass alle Schemaänderungen auf den Abonnenten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74b61-119">Snapshot publications completely refresh the schema at the Subscriber every time synchronization occurs, so all schema changes are applied to the Subscriber.</span></span> <span data-ttu-id="74b61-120">Auch die Transaktions- und die Mergereplikation unterstützen die häufigsten Schemaänderungen.</span><span class="sxs-lookup"><span data-stu-id="74b61-120">Transactional replication and merge replication also support the most common schema changes.</span></span> <span data-ttu-id="74b61-121">Weitere Informationen finden Sie unter [Vornehmen von Schemaänderungen in Veröffentlichungsdatenbanken](publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="74b61-121">For more information, see [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
 <span data-ttu-id="74b61-122">Informationen zum Synchronisieren eines Pushabonnements finden Sie unter [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="74b61-122">To synchronize a push subscription, see [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="74b61-123">Informationen zum Synchronisieren eines Pullabonnements finden Sie unter [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="74b61-123">To synchronize a pull subscription, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="74b61-124">Informationen zum Festlegen von Synchronisierungszeitplänen finden Sie unter [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="74b61-124">To set synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="74b61-125">**So zeigen Sie Synchronisierungskonflikte an und lösen Sie die Konflikte**</span><span class="sxs-lookup"><span data-stu-id="74b61-125">**To view and resolve synchronization conflicts**</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="74b61-126">: [Anzeigen und Lösen von Datenkonflikten für Mergeveröffentlichungen &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="74b61-126">: [View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="74b61-127">: [Anzeigen von Datenkonflikten für Transaktionsveröffentlichungen &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="74b61-127">: [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span></span>  
  
## <a name="executing-code-during-synchronization"></a><span data-ttu-id="74b61-128">Ausführen von Code während der Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="74b61-128">Executing Code During Synchronization</span></span>  
 <span data-ttu-id="74b61-129">Die Replikation unterstützt zwei Methoden zum Ausführen von Code während der Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="74b61-129">Replication supports two methods of executing code during synchronization</span></span>  
  
-   <span data-ttu-id="74b61-130">Das bedarfsgesteuerte Ausführen von Skripts wird für die Transaktions- und die Mergereplikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74b61-130">On demand script execution is supported for transactional replication and merge replication.</span></span> <span data-ttu-id="74b61-131">Beim bedarfsgesteuerten Ausführen von Skripts können Sie angeben, dass ein SQL-Skript während der Synchronisierung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74b61-131">Using on demand script execution you can specify a SQL script to run during synchronization.</span></span> <span data-ttu-id="74b61-132">Das Skript wird auf den Abonnenten kopiert und mithilfe von **sqlcmd** am Anfang des Synchronisierungsvorgangs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74b61-132">The script is copied to the Subscriber and executed using **sqlcmd** at the beginning of the synchronization process.</span></span> <span data-ttu-id="74b61-133">Das Skript hat keinen Zugriff auf die replizierten Änderungen, wenn diese auf den Abonnenten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="74b61-133">The script does not have access to the replicated changes as they are applied to the Subscriber.</span></span> <span data-ttu-id="74b61-134">Weitere Informationen finden Sie unter [Ausführen von Skripts während der Synchronisierung &#40;Replikationsprogrammierung mit Transact-SQL&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="74b61-134">For more information, see [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="74b61-135">Geschäftslogikhandler werden für die Mergereplikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74b61-135">Business logic handlers are supported for merge replication.</span></span> <span data-ttu-id="74b61-136">Das Geschäftslogikhandler-Framework ermöglicht es Ihnen, eine verwaltete Codeassembly zu schreiben, die während der Mergesynchronisierung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="74b61-136">Using the business logic handler framework you can write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="74b61-137">Die Assembly enthält Geschäftslogik, die auf viele Bedingungen während der Synchronisierung reagieren kann: Datenänderungen, Konflikte und Fehler.</span><span class="sxs-lookup"><span data-stu-id="74b61-137">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="74b61-138">Weitere Informationen finden Sie unter [Ausführen von Geschäftslogik während der Mergesynchronisierung](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="74b61-138">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b61-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74b61-139">See Also</span></span>  
 [<span data-ttu-id="74b61-140">Erkennen und Auflösen von Konflikten bei der Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="74b61-140">Detect and Resolve Merge Replication Conflicts</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
