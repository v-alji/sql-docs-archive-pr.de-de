---
title: Identifizieren von Engpässen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource bottlenecks [SQL Server]
- database monitoring [SQL Server], bottlenecks
- performance [SQL Server], bottlenecks
- tuning databases [SQL Server], bottlenecks
- monitoring server performance [SQL Server], bottlenecks
- monitoring performance [SQL Server], bottlenecks
- database performance [SQL Server], bottlenecks
- server performance [SQL Server], bottlenecks
- bottlenecks [SQL Server]
- identifying bottlenecks [SQL Server]
ms.assetid: db079e65-ee80-4105-aec9-f8230d0d6635
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e941b3f4a1185177cef007eb6a02a71ae1adece7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696742"
---
# <a name="identify-bottlenecks"></a><span data-ttu-id="f8beb-102">Identifizieren von Engpässen</span><span class="sxs-lookup"><span data-stu-id="f8beb-102">Identify Bottlenecks</span></span>
  <span data-ttu-id="f8beb-103">Der gleichzeitige Zugriff auf freigegebene Ressourcen verursacht Engpässe.</span><span class="sxs-lookup"><span data-stu-id="f8beb-103">Simultaneous access to shared resources causes bottlenecks.</span></span> <span data-ttu-id="f8beb-104">Im Allgemeinen entstehen Engpässe in jedem Softwaresystem und sind unvermeidlich.</span><span class="sxs-lookup"><span data-stu-id="f8beb-104">In general, bottlenecks are present in every software system and are inevitable.</span></span> <span data-ttu-id="f8beb-105">Eine überhöhte Nachfrage nach freigegebenen Ressourcen führen jedoch zu einer schlechten Antwortzeit. Dieses Situation muss identifiziert und optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="f8beb-105">However, excessive demands on shared resources cause poor response time and must be identified and tuned.</span></span>  
  
 <span data-ttu-id="f8beb-106">Mögliche Ursachen für Engpässe:</span><span class="sxs-lookup"><span data-stu-id="f8beb-106">Causes of bottlenecks include:</span></span>  
  
-   <span data-ttu-id="f8beb-107">Unzureichende Ressourcen, wodurch zusätzliche oder aktualisierte Komponenten notwendig werden.</span><span class="sxs-lookup"><span data-stu-id="f8beb-107">Insufficient resources, requiring additional or upgraded components.</span></span>  
  
-   <span data-ttu-id="f8beb-108">Ressourcen desselben Typs, auf die die Arbeitsauslastung nicht gleichmäßig verteilt wird (z. B., wenn ein Datenträger monopolisiert wird).</span><span class="sxs-lookup"><span data-stu-id="f8beb-108">Resources of the same type among which workloads are not distributed evenly; for example, one disk is being monopolized.</span></span>  
  
-   <span data-ttu-id="f8beb-109">Fehlerhaft funktionierende Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f8beb-109">Malfunctioning resources.</span></span>  
  
-   <span data-ttu-id="f8beb-110">Falsch konfigurierte Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f8beb-110">Incorrectly configured resources.</span></span>  
  
## <a name="analyzing-bottlenecks"></a><span data-ttu-id="f8beb-111">Analysieren von Engpässen</span><span class="sxs-lookup"><span data-stu-id="f8beb-111">Analyzing Bottlenecks</span></span>  
 <span data-ttu-id="f8beb-112">Sehr lange Ausführungszeiten für verschiedene Ereignisse sind Anzeichen von Engpässen, die optimiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f8beb-112">Excessive durations for various events are indicators of bottlenecks that can be tuned.</span></span>  
  
 <span data-ttu-id="f8beb-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8beb-113">For example:</span></span>  
  
-   <span data-ttu-id="f8beb-114">Eine andere Komponente verhindert, dass die Arbeitsauslastung diese Komponente erreicht, wodurch die erforderliche Zeit zum Verarbeiten der Arbeitsauslastung zunimmt.</span><span class="sxs-lookup"><span data-stu-id="f8beb-114">Some other component may prevent the load from reaching this component thereby increasing the time to complete the load.</span></span>  
  
-   <span data-ttu-id="f8beb-115">Clientanforderungen können aufgrund einer Netzwerküberlastung länger dauern.</span><span class="sxs-lookup"><span data-stu-id="f8beb-115">Client requests may take longer due to network congestion.</span></span>  
  
 <span data-ttu-id="f8beb-116">Es gibt die folgenden fünf Schlüsselbereiche, die Sie überwachen sollten, um die Serverleistung nachzuverfolgen und Engpässe zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f8beb-116">Following are five key areas to monitor when tracking server performance to identify bottlenecks.</span></span>  
  
|<span data-ttu-id="f8beb-117">Mögliche Bereiche für Engpässe</span><span class="sxs-lookup"><span data-stu-id="f8beb-117">Possible bottleneck area</span></span>|<span data-ttu-id="f8beb-118">Auswirkungen auf den Server</span><span class="sxs-lookup"><span data-stu-id="f8beb-118">Effects on the server</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="f8beb-119">Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="f8beb-119">Memory usage</span></span>|<span data-ttu-id="f8beb-120">Ein für Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unzureichender Arbeitsspeicherumfang beeinträchtigt die Leistung.</span><span class="sxs-lookup"><span data-stu-id="f8beb-120">Insufficient memory allocated or available to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrades performance.</span></span> <span data-ttu-id="f8beb-121">Die Daten müssen vom Datenträger gelesen werden, anstatt direkt aus dem Datencache.</span><span class="sxs-lookup"><span data-stu-id="f8beb-121">Data must be read from the disk rather than directly from the data cache.</span></span> <span data-ttu-id="f8beb-122">Microsoft Windows-Betriebssysteme lagern zu häufig aus, indem Daten vom Datenträger hin und her übertragen werden, wenn die Seiten benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f8beb-122">Microsoft Windows operating systems perform excessive paging by swapping data to and from the disk as the pages are needed.</span></span>|  
|<span data-ttu-id="f8beb-123">CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="f8beb-123">CPU utilization</span></span>|<span data-ttu-id="f8beb-124">Eine konstant hohe CPU-Auslastungsrate kann ein Hinweis darauf sein, dass [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen optimiert werden müssen oder dass ein CPU-Upgrade erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f8beb-124">A chronically high CPU utilization rate may indicate that [!INCLUDE[tsql](../../includes/tsql-md.md)] queries need to be tuned or that a CPU upgrade is needed.</span></span>|  
|<span data-ttu-id="f8beb-125">Datenträger-E/A</span><span class="sxs-lookup"><span data-stu-id="f8beb-125">Disk input/output (I/O)</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="f8beb-126">-Abfragen können optimiert werden, um unnötige E/A zu reduzieren. Dies geschieht beispielsweise durch die Verwendung von Indizes.</span><span class="sxs-lookup"><span data-stu-id="f8beb-126">queries can be tuned to reduce unnecessary I/O; for example, by employing indexes.</span></span>|  
|<span data-ttu-id="f8beb-127">Benutzerverbindungen</span><span class="sxs-lookup"><span data-stu-id="f8beb-127">User connections</span></span>|<span data-ttu-id="f8beb-128">Möglicherweise greifen zu viele Benutzer gleichzeitig auf den Server zu, wodurch die Leistung beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8beb-128">Too many users may be accessing the server simultaneously causing performance degradation.</span></span>|  
|<span data-ttu-id="f8beb-129">Blockierende Sperren</span><span class="sxs-lookup"><span data-stu-id="f8beb-129">Blocking locks</span></span>|<span data-ttu-id="f8beb-130">Fehlerhaft entworfene Anwendungen können zu Sperren führen und behindern die Parallelität, wodurch sich längere Antwortzeiten und niedrigere Durchsatzraten für Transaktionen ergeben.</span><span class="sxs-lookup"><span data-stu-id="f8beb-130">Incorrectly designed applications can cause locks and hamper concurrency, thus causing longer response times and lower transaction throughput rates.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8beb-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8beb-131">See Also</span></span>  
 <span data-ttu-id="f8beb-132">[Überwachen der CPU-Auslastung](../performance-monitor/monitor-cpu-usage.md) </span><span class="sxs-lookup"><span data-stu-id="f8beb-132">[Monitor CPU Usage](../performance-monitor/monitor-cpu-usage.md) </span></span>  
 <span data-ttu-id="f8beb-133">[Überwachen der Datenträgerverwendung](../performance-monitor/monitor-disk-usage.md) </span><span class="sxs-lookup"><span data-stu-id="f8beb-133">[Monitor Disk Usage](../performance-monitor/monitor-disk-usage.md) </span></span>  
 <span data-ttu-id="f8beb-134">[Überwachen der Speicherauslastung](../performance-monitor/monitor-memory-usage.md) </span><span class="sxs-lookup"><span data-stu-id="f8beb-134">[Monitor Memory Usage](../performance-monitor/monitor-memory-usage.md) </span></span>  
 <span data-ttu-id="f8beb-135">[SQL Server, Allgemeine Statistik-Objekt](../performance-monitor/sql-server-general-statistics-object.md) </span><span class="sxs-lookup"><span data-stu-id="f8beb-135">[SQL Server, General Statistics Object](../performance-monitor/sql-server-general-statistics-object.md) </span></span>  
 [<span data-ttu-id="f8beb-136">SQL Server, Sperren-Objekt</span><span class="sxs-lookup"><span data-stu-id="f8beb-136">SQL Server, Locks Object</span></span>](../performance-monitor/sql-server-locks-object.md)  
  
  
