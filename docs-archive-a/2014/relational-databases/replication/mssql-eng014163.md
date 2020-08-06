---
title: MSSQL_ENG014163 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014163 error
ms.assetid: b53dd463-ba36-421e-9745-67c7387e68dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b407d64b56d8d829d691b54917baae5bf3adbccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616493"
---
# <a name="mssql_eng014163"></a><span data-ttu-id="b629e-102">MSSQL_ENG014163</span><span class="sxs-lookup"><span data-stu-id="b629e-102">MSSQL_ENG014163</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b629e-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="b629e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b629e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b629e-104">Product Name</span></span>|<span data-ttu-id="b629e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b629e-105">SQL Server</span></span>|  
|<span data-ttu-id="b629e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b629e-106">Event ID</span></span>|<span data-ttu-id="b629e-107">14163</span><span class="sxs-lookup"><span data-stu-id="b629e-107">14163</span></span>|  
|<span data-ttu-id="b629e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b629e-108">Event Source</span></span>|<span data-ttu-id="b629e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b629e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b629e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b629e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b629e-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b629e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b629e-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b629e-112">Message Text</span></span>|<span data-ttu-id="b629e-113">Der Schwellenwert [%s:%s] für die [%s]-Veröffentlichung wurde festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b629e-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="b629e-114">Stellen Sie sicher, dass der Merge-Agent ausgeführt wird und die erwartete Anforderung erfüllen kann.</span><span class="sxs-lookup"><span data-stu-id="b629e-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b629e-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b629e-115">Explanation</span></span>  
 <span data-ttu-id="b629e-116">Mit Replikationen können Sie Warnungen für verschiedene Bedingungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b629e-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="b629e-117">Dazu zählt das Überschreiten einer angegebenen Zeitdauer zum Synchronisieren der Änderungen zwischen einem Mergeverleger und -abonnenten.</span><span class="sxs-lookup"><span data-stu-id="b629e-117">This includes exceeding a specified length of time for synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="b629e-118">Für LAN-Verbindungen und DFÜ-Verbindungen sind möglicherweise unterschiedliche Zeiten angegeben.</span><span class="sxs-lookup"><span data-stu-id="b629e-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="b629e-119">Wenn Sie mithilfe des Replikationsmonitors oder mit [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql)eine Warnung aktivieren, geben Sie einen Schwellenwert an, mit dem bestimmt wird, wann eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b629e-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="b629e-120">Wenn dieser Schwellenwert erreicht oder überschritten wird, wird im Replikationsmonitor eine Warnung angezeigt, und es wird ein Ereignis in das Windows-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b629e-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="b629e-121">Durch das Erreichen eines Schwellenwerts kann zudem eine SQL Server-Agent-Warnung ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b629e-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="b629e-122">Weitere Informationen finden Sie unter [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) und [Programmgesteuertes Überwachen der Replikation](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b629e-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b629e-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b629e-123">User Action</span></span>  
 <span data-ttu-id="b629e-124">Wenn für ein Abonnement der Schwellenwert einer Dauer überschritten wird, müssen Sie ermitteln, ob im System ein Leistungsproblem vorliegt oder ob der Schwellenwert angepasst werden muss.</span><span class="sxs-lookup"><span data-stu-id="b629e-124">If a subscription exceeds a duration threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="b629e-125">Entwickeln Sie nach dem Konfigurieren der Replikation Grundwerte für die Leistung, mit denen Sie bestimmen können, wie die Replikation sich mit einer Arbeitsauslastung verhält, die typisch für Ihre Anwendungen und Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="b629e-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="b629e-126">Nehmen Sie die Dauer der Synchronisierung in diese Grundwerte auf, damit Sie einen entsprechenden Schwellenwert festlegen können.</span><span class="sxs-lookup"><span data-stu-id="b629e-126">Include duration of synchronization in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="b629e-127">Wenn der Schwellenwert angemessen ist, jedoch überschritten wird, müssen Sie ermitteln, wo sich der Leistungsengpass im System befindet.</span><span class="sxs-lookup"><span data-stu-id="b629e-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="b629e-128">Weitere Informationen zum Überwachen der Replikationsleistung und zur entsprechenden Problembehandlung finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b629e-128">For more information about how to monitor and troubleshoot replication performance, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b629e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b629e-129">See Also</span></span>  
 [<span data-ttu-id="b629e-130">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="b629e-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
