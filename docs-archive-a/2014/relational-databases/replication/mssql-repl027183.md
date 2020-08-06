---
title: MSSQL_REPL027183 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027183 error
ms.assetid: 52c271ac-1a0e-43d5-85d4-35886d1efd32
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4484318cd6ec6ff4f0b201be69dc9b7544dd2c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725474"
---
# <a name="mssql_repl027183"></a><span data-ttu-id="0ead2-102">MSSQL_REPL027183</span><span class="sxs-lookup"><span data-stu-id="0ead2-102">MSSQL_REPL027183</span></span>
    
## <a name="message-details"></a><span data-ttu-id="0ead2-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="0ead2-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ead2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0ead2-104">Product Name</span></span>|<span data-ttu-id="0ead2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ead2-105">SQL Server</span></span>|  
|<span data-ttu-id="0ead2-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0ead2-106">Event ID</span></span>|<span data-ttu-id="0ead2-107">27183</span><span class="sxs-lookup"><span data-stu-id="0ead2-107">27183</span></span>|  
|<span data-ttu-id="0ead2-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0ead2-108">Event Source</span></span>|<span data-ttu-id="0ead2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ead2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ead2-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0ead2-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="0ead2-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0ead2-111">Symbolic Name</span></span>||  
|<span data-ttu-id="0ead2-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0ead2-112">Message Text</span></span>|<span data-ttu-id="0ead2-113">Vom Mergeprozess konnten Änderungen in Artikeln mit parametrisierten Zeilenfiltern nicht aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="0ead2-113">The merge process failed to enumerate changes in articles with parameterized row filters.</span></span> <span data-ttu-id="0ead2-114">Falls dieser Fehler weiterhin auftritt, erhöhen Sie das Abfragetimeout für diesen Prozess, reduzieren Sie die Beibehaltungsdauer für die Veröffentlichung, und verbessern Sie die Indizes für veröffentlichte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="0ead2-114">If this failure continues, increase the query timeout for this process, reduce the retention period for the publication, and improve indexes on published tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ead2-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0ead2-115">Explanation</span></span>  
 <span data-ttu-id="0ead2-116">Dieser Fehler wird ausgelöst, wenn bei der Verarbeitung von Änderungen in einer gefilterten Veröffentlichung ein Merge-Agent-Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="0ead2-116">This error is raised if a Merge Agent timeout occurs while processing changes in a filtered publication.</span></span> <span data-ttu-id="0ead2-117">Das Timeout kann durch eines der folgenden Probleme verursacht werden:</span><span class="sxs-lookup"><span data-stu-id="0ead2-117">The timeout might be caused by one of the following issues:</span></span>  
  
-   <span data-ttu-id="0ead2-118">Die Optimierung für vorausberechnete Partitionen wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ead2-118">Not using the precomputed partitions optimization.</span></span>  
  
-   <span data-ttu-id="0ead2-119">In den beim Filtern verwendeten Spalten liegt eine Indexfragmentierung vor.</span><span class="sxs-lookup"><span data-stu-id="0ead2-119">Index fragmentation on columns used for filtering.</span></span>  
  
-   <span data-ttu-id="0ead2-120">Es sind umfangreiche Tabellen mit Mergemetadaten vorhanden, beispielsweise **MSmerge_tombstone**, **MSmerge_contents**und **MSmerge_genhistory**.</span><span class="sxs-lookup"><span data-stu-id="0ead2-120">Large merge metadata tables, such as **MSmerge_tombstone**, **MSmerge_contents**, and **MSmerge_genhistory**.</span></span>  
  
-   <span data-ttu-id="0ead2-121">Es sind gefilterte Tabellen, die nicht über einen eindeutigen Schlüssel verknüpft sind, und Joinsfilter mit einer großen Anzahl an Tabellen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0ead2-121">Filtered tables that are not joined on a unique key and join filters that involve a large number of tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ead2-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0ead2-122">User Action</span></span>  
 <span data-ttu-id="0ead2-123">So lösen Sie das Problem:</span><span class="sxs-lookup"><span data-stu-id="0ead2-123">To resolve the issue:</span></span>  
  
-   <span data-ttu-id="0ead2-124">Setzen Sie den Wert des **-QueryTimeOut** -Parameters für den Merge-Agent herauf, damit die Verarbeitung fortgesetzt werden kann und Sie sich der eigentlichen Ursache des Fehlers widmen können.</span><span class="sxs-lookup"><span data-stu-id="0ead2-124">Increase the value of the **-QueryTimeOut** parameter for the Merge Agent to allow processing to continue while you address the underlying issues causing the error.</span></span> <span data-ttu-id="0ead2-125">Agentparameter können in den Agentprofilen und in der Befehlszeile angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0ead2-125">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="0ead2-126">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="0ead2-126">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="0ead2-127">Arbeiten mit Replikations-Agent-Profilen</span><span class="sxs-lookup"><span data-stu-id="0ead2-127">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="0ead2-128">Anzeigen und Ändern von Befehlszeilenparametern des Replikations-Agents &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0ead2-128">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="0ead2-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md)zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0ead2-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="0ead2-130">Verwenden Sie, sofern möglich, die Optimierung für vorausberechnete Partitionen.</span><span class="sxs-lookup"><span data-stu-id="0ead2-130">Use the precomputed partitions optimization if possible.</span></span> <span data-ttu-id="0ead2-131">Diese Optimierung wird standardmäßig verwendet, wenn mehrere Veröffentlichungsanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="0ead2-131">This optimization is used by default if a number of publication requirements are met.</span></span> <span data-ttu-id="0ead2-132">Weitere Informationen zu diesen Anforderungen finden Sie unter [Optimieren der Leistung parametrisierter Filter mithilfe vorausberechneter Partitionen](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="0ead2-132">For more information about these requirements, see [Optimize Parameterized Filter Performance with Precomputed Partitions](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span></span> <span data-ttu-id="0ead2-133">Wenn die Veröffentlichung diese Anforderungen nicht erfüllt, sollten Sie einen erneuten Entwurf der Veröffentlichung in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="0ead2-133">If the publication does not meet these requirements, consider redesigning the publication.</span></span>  
  
-   <span data-ttu-id="0ead2-134">Geben Sie die kürzestmögliche Einstellung für die Beibehaltungsdauer der Veröffentlichung an, da die Replikation keinen Cleanup der Metadaten in den Veröffentlichungs- und den Abonnementdatenbanken ausführen kann, bevor die Beibehaltungsdauer erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="0ead2-134">Specify the lowest setting possible for the publication retention period, because replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="0ead2-135">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="0ead2-135">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="0ead2-136">Als Teil der Wartung für die Mergereplikation überprüfen Sie gelegentlich die Vergrößerung der Systemtabellen, die mit der Mergereplikation verbunden sind: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**und **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="0ead2-136">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="0ead2-137">Führen Sie eine regelmäßige Neuindizierung dieser Tabellen durch.</span><span class="sxs-lookup"><span data-stu-id="0ead2-137">Periodically re-index these tables.</span></span> <span data-ttu-id="0ead2-138">Weitere Informationen finden Sie unter [Neuorganisieren und Neuerstellen von Indizes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="0ead2-138">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="0ead2-139">Stellen Sie sicher, dass die zum Filtern verwendeten Spalten richtig indiziert sind, und erstellen Sie die entsprechenden Indizes gegebenenfalls erneut.</span><span class="sxs-lookup"><span data-stu-id="0ead2-139">Ensure that columns used for filtering are properly indexed and rebuild such indexes if necessary.</span></span> <span data-ttu-id="0ead2-140">Weitere Informationen finden Sie unter [Neuorganisieren und Neuerstellen von Indizes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="0ead2-140">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="0ead2-141">Legen Sie für Joinsfilter, die auf eindeutigen Spalten basieren, die **join_unique_key** -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="0ead2-141">Set the **join_unique_key** property for join filters that are based on unique columns.</span></span> <span data-ttu-id="0ead2-142">Weitere Informationen finden Sie unter [Join Filters](merge/join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="0ead2-142">For more information, see [Join Filters](merge/join-filters.md).</span></span>  
  
-   <span data-ttu-id="0ead2-143">Begrenzen Sie die Anzahl der Tabellen in der Joinsfilterhierarchie.</span><span class="sxs-lookup"><span data-stu-id="0ead2-143">Limit the number of tables in the join filter hierarchy.</span></span> <span data-ttu-id="0ead2-144">Wenn Sie Joinsfilter für fünf oder mehr Tabellen erstellen, sollten Sie andere Lösungen in Betracht ziehen: Kleinere Tabellen, Tabellen, die nicht geändert werden, oder Tabellen, bei denen es sich primär um Nachschlagetabellen handelt, sollten in diesem Fall nicht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="0ead2-144">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="0ead2-145">Verwenden Sie Joinsfilter nur zwischen Tabellen, für die eine Partitionierung auf Abonnements erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="0ead2-145">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="0ead2-146">Nehmen Sie zwischen Synchronisierungen weniger Änderungen an gefilterten Tabellen vor, oder führen Sie den Merge-Agent häufiger aus.</span><span class="sxs-lookup"><span data-stu-id="0ead2-146">Make a smaller number of changes on filtered tables between synchronizations, or run the Merge Agent more frequently.</span></span> <span data-ttu-id="0ead2-147">Weitere Informationen zum Angeben von Synchronisierungszeitplänen finden Sie unter [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="0ead2-147">For more information about setting synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ead2-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ead2-148">See Also</span></span>  
 [<span data-ttu-id="0ead2-149">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="0ead2-149">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
