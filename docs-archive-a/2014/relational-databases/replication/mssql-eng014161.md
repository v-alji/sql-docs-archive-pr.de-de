---
title: MSSQL_ENG014161 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014161 error
ms.assetid: 4b983e76-bb77-43c5-b44b-19919d3da619
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8cf85181e444385e1a3908761ba71414b68cf3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607667"
---
# <a name="mssql_eng014161"></a><span data-ttu-id="5ce95-102">MSSQL_ENG014161</span><span class="sxs-lookup"><span data-stu-id="5ce95-102">MSSQL_ENG014161</span></span>
    
## <a name="message-details"></a><span data-ttu-id="5ce95-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="5ce95-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ce95-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5ce95-104">Product Name</span></span>|<span data-ttu-id="5ce95-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5ce95-105">SQL Server</span></span>|  
|<span data-ttu-id="5ce95-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5ce95-106">Event ID</span></span>|<span data-ttu-id="5ce95-107">14161</span><span class="sxs-lookup"><span data-stu-id="5ce95-107">14161</span></span>|  
|<span data-ttu-id="5ce95-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5ce95-108">Event Source</span></span>|<span data-ttu-id="5ce95-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5ce95-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5ce95-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5ce95-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="5ce95-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5ce95-111">Symbolic Name</span></span>||  
|<span data-ttu-id="5ce95-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5ce95-112">Message Text</span></span>|<span data-ttu-id="5ce95-113">Der Schwellenwert [%s:%s] für die [%s]-Veröffentlichung wurde festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5ce95-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="5ce95-114">Stellen Sie sicher, dass der Protokolllese-Agent und der Verteilungs-Agent ausgeführt werden und die Latenzzeitanforderung erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="5ce95-114">Make sure that the logreader and distribution agents are running and can match the latency requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5ce95-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5ce95-115">Explanation</span></span>  
 <span data-ttu-id="5ce95-116">Mit Replikationen können Sie Warnungen für verschiedene Bedingungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ce95-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="5ce95-117">Dies schließt das Überschreiten einer angegebenen Latenzzeit für Transaktionsabonnements ein.</span><span class="sxs-lookup"><span data-stu-id="5ce95-117">This includes exceeding a specified latency for transactional subscriptions.</span></span> <span data-ttu-id="5ce95-118">Bei der Latenzzeit handelt es sich um die Zeitspanne zwischen dem Ausführen des Commit für eine Datenänderung auf dem Verleger und dem Ausführen des Commit für die entsprechende Änderung auf dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="5ce95-118">Latency is the period of time that elapses between a data change being committed at the Publisher and the corresponding change being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="5ce95-119">Wenn Sie mithilfe des Replikationsmonitors oder mit [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql)eine Warnung aktivieren, geben Sie einen Schwellenwert an, mit dem bestimmt wird, wann eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5ce95-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="5ce95-120">Wenn dieser Schwellenwert erreicht oder überschritten wird, wird im Replikationsmonitor eine Warnung angezeigt, und es wird ein Ereignis in das Windows-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ce95-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="5ce95-121">Durch das Erreichen eines Schwellenwerts kann zudem eine SQL Server-Agent-Warnung ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5ce95-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="5ce95-122">Weitere Informationen finden Sie unter [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) und [Programmgesteuertes Überwachen der Replikation](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="5ce95-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5ce95-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5ce95-123">User Action</span></span>  
 <span data-ttu-id="5ce95-124">Wenn für ein Abonnement der Schwellenwert einer Latenzzeit überschritten wird, müssen Sie ermitteln, ob im System ein Leistungsproblem vorliegt oder ob der Schwellenwert angepasst werden muss.</span><span class="sxs-lookup"><span data-stu-id="5ce95-124">If a subscription exceeds a latency threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="5ce95-125">Entwickeln Sie nach dem Konfigurieren der Replikation Grundwerte für die Leistung, mit denen Sie bestimmen können, wie die Replikation sich mit einer Arbeitsauslastung verhält, die typisch für Ihre Anwendungen und Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="5ce95-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="5ce95-126">Nehmen Sie die Latenzzeit in diese Grundwerte auf, damit Sie einen entsprechenden Schwellenwert festlegen können.</span><span class="sxs-lookup"><span data-stu-id="5ce95-126">Include latency in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="5ce95-127">Wenn der Schwellenwert angemessen ist, jedoch überschritten wird, müssen Sie ermitteln, wo sich der Leistungsengpass im System befindet.</span><span class="sxs-lookup"><span data-stu-id="5ce95-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="5ce95-128">Weitere Informationen zum Überwachen der Replikationsleistung und zur entsprechenden Problembehandlung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5ce95-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5ce95-129">Messen der Latenzzeit und Überprüfen der Verbindungen bei Transaktionsreplikationen</span><span class="sxs-lookup"><span data-stu-id="5ce95-129">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
-   [<span data-ttu-id="5ce95-130">Überwachen der Leistung mit dem Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="5ce95-130">Monitor Performance with Replication Monitor</span></span>](monitor/monitor-performance-with-replication-monitor.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ce95-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ce95-131">See Also</span></span>  
 [<span data-ttu-id="5ce95-132">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="5ce95-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
