---
title: MSSQL_ENG014160 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3351567a31a0a0384ab8957073ab0457ef0ea7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608557"
---
# <a name="mssql_eng014160"></a><span data-ttu-id="0431a-102">MSSQL_ENG014160</span><span class="sxs-lookup"><span data-stu-id="0431a-102">MSSQL_ENG014160</span></span>
    
## <a name="message-details"></a><span data-ttu-id="0431a-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="0431a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0431a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0431a-104">Product Name</span></span>|<span data-ttu-id="0431a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0431a-105">SQL Server</span></span>|  
|<span data-ttu-id="0431a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0431a-106">Event ID</span></span>|<span data-ttu-id="0431a-107">14160</span><span class="sxs-lookup"><span data-stu-id="0431a-107">14160</span></span>|  
|<span data-ttu-id="0431a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0431a-108">Event Source</span></span>|<span data-ttu-id="0431a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0431a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0431a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0431a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="0431a-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0431a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="0431a-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0431a-112">Message Text</span></span>|<span data-ttu-id="0431a-113">Der Schwellenwert [%s:%s] für die [%s]-Veröffentlichung wurde festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0431a-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="0431a-114">Mindestens ein Abonnement für diese Veröffentlichung ist abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="0431a-114">One or more subscriptions to this publication have expired.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0431a-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0431a-115">Explanation</span></span>  
 <span data-ttu-id="0431a-116">Mit Replikationen können Sie Warnungen für verschiedene Bedingungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0431a-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="0431a-117">Dazu zählt das bevorstehende Ablaufdatum des Abonnements.</span><span class="sxs-lookup"><span data-stu-id="0431a-117">This includes imminent subscription expiration.</span></span> <span data-ttu-id="0431a-118">Abonnements können ablaufen, wenn sie nicht innerhalb einer angegebenen *Beibehaltungsdauer*synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0431a-118">Subscriptions can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="0431a-119">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="0431a-119">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="0431a-120">Wenn Sie mithilfe des Replikationsmonitors oder mit [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql)eine Warnung aktivieren, geben Sie einen Schwellenwert an, mit dem bestimmt wird, wann eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0431a-120">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="0431a-121">Wenn dieser Schwellenwert erreicht oder überschritten wird, wird im Replikationsmonitor eine Warnung angezeigt, und es wird ein Ereignis in das Windows-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0431a-121">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="0431a-122">Durch das Erreichen eines Schwellenwerts kann zudem eine SQL Server-Agent-Warnung ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0431a-122">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="0431a-123">Weitere Informationen finden Sie unter [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) und [Programmgesteuertes Überwachen der Replikation](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0431a-123">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0431a-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0431a-124">User Action</span></span>  
 <span data-ttu-id="0431a-125">Die Lösung für dieses Problem hängt von der Ursache für die Auslösung der Warnung ab:</span><span class="sxs-lookup"><span data-stu-id="0431a-125">The resolution for this issue depends on the reason the warning was raised:</span></span>  
  
-   <span data-ttu-id="0431a-126">Wenn der Schwellenwert überschritten wurde, das Abonnement jedoch noch nicht abgelaufen ist, synchronisieren Sie das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="0431a-126">If the threshold has been exceeded, but the subscription has not yet expired, synchronize the subscription.</span></span> <span data-ttu-id="0431a-127">Weitere Informationen finden Sie unter [Synchronisieren von Daten](synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="0431a-127">For more information, see [Synchronize Data](synchronize-data.md).</span></span>  
  
-   <span data-ttu-id="0431a-128">Wenn der Agent ausgeführt wurde, die Änderungen jedoch nicht ordnungsgemäß repliziert wurden, kann das Abonnement aus diesem Grund ablaufen.</span><span class="sxs-lookup"><span data-stu-id="0431a-128">If the agent has been running, but has not been replicating changes properly, this can cause the subscription to expire.</span></span> <span data-ttu-id="0431a-129">Stellen Sie für die Transaktionsreplikation sicher, dass der Verteilungs-Agent sowie der Protokolllese-Agent ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0431a-129">For transactional replication, make sure that the Distribution Agent and Log Reader Agent are running.</span></span> <span data-ttu-id="0431a-130">Stellen Sie für die Mergereplikation sicher, dass der Merge-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0431a-130">For merge replication, make sure the Merge Agent is running.</span></span> <span data-ttu-id="0431a-131">Weitere Informationen zum Starten dieser Agents finden Sie unter [Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) und [Ausführbare Konzepte für die Programmierung von Replikations-Agents](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="0431a-131">For information about how to start these agents, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="0431a-132">Wenn das Abonnement abgelaufen ist, muss es erneut initialisiert werden oder verworfen und neu erstellt werden. Dies richtet sich nach der Art des Abonnements und danach, wie lange es schon abgelaufen war.</span><span class="sxs-lookup"><span data-stu-id="0431a-132">If the subscription has expired, it must either be reinitialized or dropped and re-created, depending on the type of subscription and how long it has been expired.</span></span> <span data-ttu-id="0431a-133">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="0431a-133">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0431a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0431a-134">See Also</span></span>  
 [<span data-ttu-id="0431a-135">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="0431a-135">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
