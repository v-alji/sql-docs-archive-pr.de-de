---
title: MSSQL_ENG014150 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014150 error
ms.assetid: c3dd3109-abf3-4b38-a4e9-ef48d0235656
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c926d05be9613ff559f119484fa5e238d71d861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608564"
---
# <a name="mssql_eng014150"></a><span data-ttu-id="28890-102">MSSQL_ENG014150</span><span class="sxs-lookup"><span data-stu-id="28890-102">MSSQL_ENG014150</span></span>
    
## <a name="message-details"></a><span data-ttu-id="28890-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="28890-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28890-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="28890-104">Product Name</span></span>|<span data-ttu-id="28890-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="28890-105">SQL Server</span></span>|  
|<span data-ttu-id="28890-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="28890-106">Event ID</span></span>|<span data-ttu-id="28890-107">14150</span><span class="sxs-lookup"><span data-stu-id="28890-107">14150</span></span>|  
|<span data-ttu-id="28890-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="28890-108">Event Source</span></span>|<span data-ttu-id="28890-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="28890-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="28890-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="28890-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="28890-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="28890-111">Symbolic Name</span></span>||  
|<span data-ttu-id="28890-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="28890-112">Message Text</span></span>|<span data-ttu-id="28890-113">Replikations-%1!: %2! (Agent) erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="28890-113">Replication-%s: agent %s succeeded.</span></span> <span data-ttu-id="28890-114">%3!</span><span class="sxs-lookup"><span data-stu-id="28890-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28890-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="28890-115">Explanation</span></span>  
 <span data-ttu-id="28890-116">Mit dieser Meldung wird angegeben, dass ein Replikations-Agent erfolgreich zu Ende ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="28890-116">This message indicates that a replication agent has successfully finished running.</span></span> <span data-ttu-id="28890-117">Für die Replikation werden die folgenden Agents verwendet:</span><span class="sxs-lookup"><span data-stu-id="28890-117">Replication uses the following agents:</span></span>  
  
-   <span data-ttu-id="28890-118">Der Momentaufnahme-Agent.</span><span class="sxs-lookup"><span data-stu-id="28890-118">The Snapshot Agent.</span></span> <span data-ttu-id="28890-119">Dieser Agent wird von allen Veröffentlichungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="28890-119">This agent is used by all publications.</span></span>  
  
-   <span data-ttu-id="28890-120">Der Protokolllese-Agent.</span><span class="sxs-lookup"><span data-stu-id="28890-120">The Log Reader Agent.</span></span> <span data-ttu-id="28890-121">Dieser Agent wird von allen Transaktionsveröffentlichungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="28890-121">This agent is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="28890-122">Der Warteschlangenlese-Agent.</span><span class="sxs-lookup"><span data-stu-id="28890-122">The Queue Reader Agent.</span></span> <span data-ttu-id="28890-123">Dieser Agent wird von Transaktionsveröffentlichungen verwendet, die für Abonnements mit verzögertem Update über eine Warteschlange aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="28890-123">This agent is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="28890-124">Der Verteilungs-Agent.</span><span class="sxs-lookup"><span data-stu-id="28890-124">The Distribution Agent.</span></span> <span data-ttu-id="28890-125">Mit diesem Agent werden Abonnements für Transaktions- und Momentaufnahmeveröffentlichungen synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="28890-125">This agent synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="28890-126">Der Merge-Agent.</span><span class="sxs-lookup"><span data-stu-id="28890-126">The Merge Agent.</span></span> <span data-ttu-id="28890-127">Mit diesem Agent werden Abonnements für Mergeveröffentlichungen synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="28890-127">This agent synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="28890-128">Aufträge zur Replikationswartung.</span><span class="sxs-lookup"><span data-stu-id="28890-128">Replication maintenance jobs.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28890-129">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="28890-129">User Action</span></span>  
 <span data-ttu-id="28890-130">Der Protokolllese-Agent, der Warteschlangenlese-Agent und der Verteilungs-Agent werden normalerweise kontinuierlich ausgeführt. Die anderen Agents werden hingegen bei Bedarf oder nach einem Zeitplan ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28890-130">The Log Reader Agent, Queue Reader Agent, and Distribution Agent typically run continuously, whereas the other agents typically run on demand or on a schedule.</span></span> <span data-ttu-id="28890-131">Wenn Sie nicht erwarten, dass ein Agent zu Ende ausgeführt wurde, überprüfen Sie den Status des Agents.</span><span class="sxs-lookup"><span data-stu-id="28890-131">If you do not expect an agent to have completed a run, check the status of the agent.</span></span> <span data-ttu-id="28890-132">Weitere Informationen finden Sie unter [Monitor Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="28890-132">For more information, see [Monitor Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28890-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28890-133">See Also</span></span>  
 <span data-ttu-id="28890-134">[Verwaltung des Replikations-Agents](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="28890-134">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="28890-135">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="28890-135">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="28890-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28890-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="28890-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28890-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="28890-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28890-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="28890-139">[Warteschlangenlese-Agent der Microsoft SQL Server-Replikation](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28890-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="28890-140">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="28890-140">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
