---
title: MSSQL_ENG014165 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014165 error
ms.assetid: 7bb07672-310c-4f51-ae76-c55e7c8d51ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ac0d9c0bad79b13676296e4a041f0141d134c75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718010"
---
# <a name="mssql_eng014165"></a><span data-ttu-id="66ba0-102">MSSQL_ENG014165</span><span class="sxs-lookup"><span data-stu-id="66ba0-102">MSSQL_ENG014165</span></span>
    
## <a name="message-details"></a><span data-ttu-id="66ba0-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="66ba0-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66ba0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="66ba0-104">Product Name</span></span>|<span data-ttu-id="66ba0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66ba0-105">SQL Server</span></span>|  
|<span data-ttu-id="66ba0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="66ba0-106">Event ID</span></span>|<span data-ttu-id="66ba0-107">14165</span><span class="sxs-lookup"><span data-stu-id="66ba0-107">14165</span></span>|  
|<span data-ttu-id="66ba0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="66ba0-108">Event Source</span></span>|<span data-ttu-id="66ba0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="66ba0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="66ba0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="66ba0-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="66ba0-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="66ba0-111">Symbolic Name</span></span>||  
|<span data-ttu-id="66ba0-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="66ba0-112">Message Text</span></span>|<span data-ttu-id="66ba0-113">Der Schwellenwert [%s:%s] für die [%s]-Veröffentlichung wurde festgelegt.</span><span class="sxs-lookup"><span data-stu-id="66ba0-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="66ba0-114">Stellen Sie sicher, dass der Merge-Agent ausgeführt wird und die erwartete Anforderung erfüllen kann.</span><span class="sxs-lookup"><span data-stu-id="66ba0-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66ba0-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="66ba0-115">Explanation</span></span>  
 <span data-ttu-id="66ba0-116">Mit Replikationen können Sie Warnungen für verschiedene Bedingungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="66ba0-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="66ba0-117">Hierzu zählen Fehler beim Verarbeiten einer ausreichenden Anzahl von Zeilen beim Synchronisieren von Änderungen zwischen einem Mergeverleger und einem Mergeabonnenten.</span><span class="sxs-lookup"><span data-stu-id="66ba0-117">This includes failure to process a sufficient number of rows when synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="66ba0-118">Für LAN-Verbindungen und DFÜ-Verbindungen sind möglicherweise unterschiedliche Zeiten angegeben.</span><span class="sxs-lookup"><span data-stu-id="66ba0-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="66ba0-119">Wenn Sie mithilfe des Replikationsmonitors oder mit [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql)eine Warnung aktivieren, geben Sie einen Schwellenwert an, mit dem bestimmt wird, wann eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="66ba0-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="66ba0-120">Wenn dieser Schwellenwert erreicht oder überschritten wird, wird im Replikationsmonitor eine Warnung angezeigt, und es wird ein Ereignis in das Windows-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="66ba0-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="66ba0-121">Durch das Erreichen eines Schwellenwerts kann zudem eine SQL Server-Agent-Warnung ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="66ba0-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="66ba0-122">Weitere Informationen finden Sie unter [Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) und [Programmgesteuertes Überwachen der Replikation](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="66ba0-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66ba0-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="66ba0-123">User Action</span></span>  
 <span data-ttu-id="66ba0-124">Wenn für ein Abonnement der Schwellenwert für die Zeilenverarbeitung nicht eingehalten wird, müssen Sie ermitteln, ob im System ein Leistungsproblem vorliegt oder ob der Schwellenwert angepasst werden muss.</span><span class="sxs-lookup"><span data-stu-id="66ba0-124">If a subscription is not meeting a row processing threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="66ba0-125">Entwickeln Sie nach dem Konfigurieren der Replikation Grundwerte für die Leistung, mit denen Sie bestimmen können, wie die Replikation sich mit einer Arbeitsauslastung verhält, die typisch für Ihre Anwendungen und Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="66ba0-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="66ba0-126">Nehmen Sie die Anzahl der verarbeiteten Zeilen in diese Grundwerte auf, damit Sie einen entsprechenden Schwellenwert festlegen können.</span><span class="sxs-lookup"><span data-stu-id="66ba0-126">Include number of rows processed in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="66ba0-127">Wenn der Schwellenwert angemessen ist, jedoch überschritten wird, müssen Sie ermitteln, wo sich der Leistungsengpass im System befindet.</span><span class="sxs-lookup"><span data-stu-id="66ba0-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="66ba0-128">Weitere Informationen zum Überwachen der Replikationsleistung und zur entsprechenden Problembehandlung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="66ba0-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   <span data-ttu-id="66ba0-129">[Überwachen der Leistung mit dem Replikationsmonitor](monitor/monitor-performance-with-replication-monitor.md) (insbesondere der Abschnitt „Anzeigen von Details zur Synchronisierungsleistung bei der Mergereplikation“)</span><span class="sxs-lookup"><span data-stu-id="66ba0-129">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (especially the section "Viewing Detailed Synchronization Performance for Merge Replication")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ba0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66ba0-130">See Also</span></span>  
 [<span data-ttu-id="66ba0-131">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="66ba0-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
