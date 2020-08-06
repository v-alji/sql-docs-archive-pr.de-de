---
title: Übersicht über den Replikationsmonitor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: rothja
ms.author: jroth
ms.openlocfilehash: df2760e4ce04c95f38ceb9dfe9fa9f79c4c467f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718004"
---
# <a name="monitoring-replication"></a><span data-ttu-id="35d67-102">Überwachen (Replikation)</span><span class="sxs-lookup"><span data-stu-id="35d67-102">Monitoring (Replication)</span></span>
  <span data-ttu-id="35d67-103">Die Überwachung einer Replikationstopologie ist ein wichtiger Aspekt bei der Bereitstellung der Replikation.</span><span class="sxs-lookup"><span data-stu-id="35d67-103">Monitoring a replication topology is an important aspect of deploying replication.</span></span> <span data-ttu-id="35d67-104">Da die Replikationsaktivität verteilt ist, ist es außerordentlich wichtig, die Aktivität und den Status auf allen an der Replikation beteiligten Computern nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="35d67-104">Because replication activity is distributed, it is essential to track activity and status across all computers involved in replication.</span></span> <span data-ttu-id="35d67-105">Zum Überwachen der Replikation stehen die folgenden Tools zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="35d67-105">The following tools can be used to monitor replication:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)]<span data-ttu-id="35d67-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]Replikations Monitor</span><span class="sxs-lookup"><span data-stu-id="35d67-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor</span></span>  
  
     <span data-ttu-id="35d67-107">Der Replikationsmonitor ist das wichtigste Tool für die Überwachung der Replikation. Es bietet eine verlegerfokussierte Sicht auf die gesamte Replikationsaktivität.</span><span class="sxs-lookup"><span data-stu-id="35d67-107">Replication Monitor is the most important tool for monitoring replication, presenting a Publisher-focused view of all replication activity.</span></span> <span data-ttu-id="35d67-108">Weitere Informationen finden Sie unter [Überwachen der Leistung mit dem Replikations Monitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="35d67-108">For more information, see [Monitor performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] <span data-ttu-id="35d67-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d67-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span></span>  
  
     [!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] <span data-ttu-id="35d67-110">bietet Zugriff auf den Replikationsmonitor.</span><span class="sxs-lookup"><span data-stu-id="35d67-110">provides access to Replication Monitor.</span></span> <span data-ttu-id="35d67-111">Darüber hinaus können Sie über dieses Tool den aktuellen Status und die letzte Meldung anzeigen lassen, die von den folgenden Agents protokolliert wurde, sowie die Agents starten und beenden: Protokolllese-Agent, Momentaufnahmen-Agent, Merge-Agent bzw. Verteilungs-Agent.</span><span class="sxs-lookup"><span data-stu-id="35d67-111">It also allows you to view the current status and last message logged by the following agents and allows you start and stop each agent: Log Reader Agent, Snapshot Agent, Merge Agent, and Distribution Agent.</span></span> <span data-ttu-id="35d67-112">Weitere Informationen finden Sie unter [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span><span class="sxs-lookup"><span data-stu-id="35d67-112">For more information, see [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="35d67-113">und Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="35d67-113">and Replication Management Objects (RMO)</span></span>  
  
     <span data-ttu-id="35d67-114">Dank beider Schnittstellen können Sie alle Replikationstypen vom Verteiler aus überwachen.</span><span class="sxs-lookup"><span data-stu-id="35d67-114">Both interfaces allow you to monitor all types of replication from the Distributor.</span></span> <span data-ttu-id="35d67-115">Bei Mergereplikationen haben Sie außerdem die Möglichkeit, die Replikation vom Abonnenten aus zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="35d67-115">Merge replication also provides the ability to monitor replication from the Subscriber.</span></span>  
  
-   <span data-ttu-id="35d67-116">Warnungen für Replikations-Agentereignisse</span><span class="sxs-lookup"><span data-stu-id="35d67-116">Alerts for replication agent events</span></span>  
  
     <span data-ttu-id="35d67-117">Die Replikation bietet eine Reihe vordefinierter Warnungen für Replikations-Agentereignisse. Darüber hinaus können Sie bei Bedarf auch zusätzliche Warnungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="35d67-117">Replication provides a number of predefined alerts for replication agent events, and you can create additional alerts if necessary.</span></span> <span data-ttu-id="35d67-118">Warnungen können verwendet werden, um eine automatische Antwort auf ein Ereignis auszulösen und/oder einen Administrator zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="35d67-118">Alerts can be used to trigger an automated response to an event and/or notify an administrator.</span></span> <span data-ttu-id="35d67-119">Weitere Informationen finden Sie unter [Verwenden von Warnungen für Replikations-Agentereignisse](agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="35d67-119">For more information, see [Use Alerts for Replication Agent Events](agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
-   <span data-ttu-id="35d67-120">Systemmonitor</span><span class="sxs-lookup"><span data-stu-id="35d67-120">System Monitor</span></span>  
  
     <span data-ttu-id="35d67-121">Mit dem Systemmonitor kann die Leistung überwacht werden. Er stellt eine Reihe von Zählern für die Replikation bereit.</span><span class="sxs-lookup"><span data-stu-id="35d67-121">System Monitor can be useful for monitoring performance, providing a number of counters for replication.</span></span> <span data-ttu-id="35d67-122">Weitere Informationen finden Sie unter [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="35d67-122">For more information, see [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d67-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35d67-123">See Also</span></span>  
 <span data-ttu-id="35d67-124">[Häufig gestellte Fragen für Replikationsadministratoren](administration/frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="35d67-124">[Replication Administration FAQ](administration/frequently-asked-questions-for-replication-administrators.md) </span></span>  
 [<span data-ttu-id="35d67-125">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="35d67-125">Best Practices for Replication Administration</span></span>](administration/best-practices-for-replication-administration.md)   

  
  
