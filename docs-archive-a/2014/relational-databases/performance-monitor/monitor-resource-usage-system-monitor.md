---
title: Überwachen der Ressourcenverwendung (Systemmonitor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], resource usage
- System Monitor [SQL Server], about Windows System Monitor
- resource usage monitoring [SQL Server]
- System Monitor [SQL Server]
- counters [SQL Server], resource usage subjects
- performance counters [SQL Server], resource usage subjects
- Windows System Monitor [SQL Server], about Windows System Monitor
- monitoring [SQL Server], server resource usage
- monitoring resource usage [SQL Server]
- Windows System Monitor [SQL Server]
- database monitoring [SQL Server], resource usage
- database performance [SQL Server], resource usage
- tuning databases [SQL Server], resource usage
- server performance [SQL Server], resource usage
ms.assetid: f2993a28-0b81-46f2-aec0-6877fe990387
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d691091a41e3161c733902824bf439b6788cc4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622043"
---
# <a name="monitor-resource-usage-system-monitor"></a><span data-ttu-id="8133f-102">Überwachen der Ressourcenverwendung (Systemmonitor)</span><span class="sxs-lookup"><span data-stu-id="8133f-102">Monitor Resource Usage (System Monitor)</span></span>
  <span data-ttu-id="8133f-103">Wenn Sie das Microsoft Windows-Serverbetriebssystem ausführen, können Sie das grafische Tool Systemmonitor verwenden, um die Leistung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu messen.</span><span class="sxs-lookup"><span data-stu-id="8133f-103">If you are running Microsoft Windows server operating system, use the System Monitor graphical tool to measure the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8133f-104">Es ist möglich, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Objekte, Leistungsindikatoren und das Verhalten anderer Objekte anzuzeigen, wie z. B. Prozessoren, Arbeitsspeicher, Cache, Threads und Prozesse.</span><span class="sxs-lookup"><span data-stu-id="8133f-104">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects, performance counters, and the behavior of other objects, such as processors, memory, cache, threads, and processes.</span></span> <span data-ttu-id="8133f-105">Jedes dieser Objekte verfügt über eine zugeordnete Gruppe von Leistungsindikatoren, durch die die Geräteverwendung, Länge von Warteschlangen, Wartezeiten sowie andere Indikatoren für den Durchsatz und die interne Auslastung ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="8133f-105">Each of these objects has an associated set of counters that measure device usage, queue lengths, delays, and other indicators of throughput and internal congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8133f-106">Der Systemmonitor wurde nach Windows NT 4.0 grundlegend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8133f-106">System Monitor replaced Performance Monitor after Windows NT 4.0.</span></span>  
  
## <a name="benefits-of-system-monitor"></a><span data-ttu-id="8133f-107">Vorteile des Systemmonitors</span><span class="sxs-lookup"><span data-stu-id="8133f-107">Benefits of System Monitor</span></span>  
 <span data-ttu-id="8133f-108">Der Systemmonitor kann dazu genutzt werden, die Leistungsindikatoren des Windows-Betriebssystems und von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gleichzeitig zu überwachen, um Zusammenhänge zwischen der Leistung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und Windows zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8133f-108">System Monitor can be useful to monitor Windows operating system and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] counters at the same time to determine any correlation between the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows.</span></span> <span data-ttu-id="8133f-109">Wenn Sie beispielsweise die Datenträger-E/A-Leistungsindikatoren von Windows und die Leistungsindikatoren des Puffer-Managers von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gleichzeitig überwachen, können Sie sich einen Überblick über das Verhalten des gesamten Systems verschaffen.</span><span class="sxs-lookup"><span data-stu-id="8133f-109">For example, monitoring the Windows disk input/output (I/O) counters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Buffer Manager counters at the same time can reveal the behavior of the entire system.</span></span>  
  
 <span data-ttu-id="8133f-110">Mit dem Systemmonitor können Sie Statistiken über die aktuelle Aktivität und Leistung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] abrufen.</span><span class="sxs-lookup"><span data-stu-id="8133f-110">System Monitor allows you to obtain statistics on current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity and performance.</span></span> <span data-ttu-id="8133f-111">Der Systemmonitor ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8133f-111">Using System Monitor, you can:</span></span>  
  
-   <span data-ttu-id="8133f-112">Gleichzeitiges Anzeigen von Daten einer beliebigen Anzahl von Computern</span><span class="sxs-lookup"><span data-stu-id="8133f-112">View data simultaneously from any number of computers.</span></span>  
  
-   <span data-ttu-id="8133f-113">Anzeigen und Ändern von Diagrammen, um die aktuelle Aktivität wiederzugeben, sowie Anzeigen von Leistungsindikatorwerten, die in der vom Benutzer definierten Häufigkeit aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="8133f-113">View and change charts to reflect current activity, and show counter values that are updated at a frequency that the user defines.</span></span>  
  
-   <span data-ttu-id="8133f-114">Exportieren von Daten aus Diagrammen, Protokollen, Warnungsprotokollen und Berichten in Tabellen- oder Datenbankanwendungen, um sie weiter zu bearbeiten oder zu drucken</span><span class="sxs-lookup"><span data-stu-id="8133f-114">Export data from charts, logs, alert logs, and reports to spreadsheet or database applications for further manipulation and printing.</span></span>  
  
-   <span data-ttu-id="8133f-115">Hinzufügen von Systemwarnungen, die ein Ereignis im Warnungsprotokoll einfügen und über die Sie durch das Ausgeben einer Netzwerkwarnung benachrichtigt werden können</span><span class="sxs-lookup"><span data-stu-id="8133f-115">Add system alerts that list an event in the alert log and can notify you by issuing a network alert.</span></span>  
  
-   <span data-ttu-id="8133f-116">Ausführen einer vordefinierten Anwendung, wenn ein Leistungsindikatorwert zum ersten Mal einen benutzerdefinierten Wert über- bzw. unterschreitet oder jedes Mal, wenn dies geschieht</span><span class="sxs-lookup"><span data-stu-id="8133f-116">Run a predefined application the first time or every time a counter value goes over or under a user-defined value.</span></span>  
  
-   <span data-ttu-id="8133f-117">Erstellen von Protokolldateien, die Daten über verschiedene Objekte von unterschiedlichen Computern enthalten</span><span class="sxs-lookup"><span data-stu-id="8133f-117">Create log files that contain data about various objects from different computers.</span></span>  
  
-   <span data-ttu-id="8133f-118">Anfügen von ausgewählten Abschnitten aus anderen bestehenden Protokolldateien an eine Datei, um ein Langzeitarchiv zu erstellen</span><span class="sxs-lookup"><span data-stu-id="8133f-118">Append to one file selected sections from other existing log files to form a long-term archive.</span></span>  
  
-   <span data-ttu-id="8133f-119">Anzeigen von aktuellen Aktivitätsberichten oder Erstellen von Berichten anhand bestehender Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="8133f-119">View current-activity reports, or create reports from existing log files.</span></span>  
  
-   <span data-ttu-id="8133f-120">Sichern von einzelnen Diagramm-, Warnungs-, Protokoll- oder Berichtseinstellungen oder der gesamten Einrichtung des Arbeitsbereichs für die spätere Wiederverwendung</span><span class="sxs-lookup"><span data-stu-id="8133f-120">Save individual chart, alert, log, or report settings, or the entire workspace setup for reuse.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8133f-121">Ab Windows NT 4.0 wurde der Leistungsindikator durch den Systemmonitor ersetzt.</span><span class="sxs-lookup"><span data-stu-id="8133f-121">System Monitor replaced the Performance Monitor after Windows NT 4.0.</span></span> <span data-ttu-id="8133f-122">Diese Tasks können Sie mit dem Systemmonitor oder mit dem Leistungsindikator ausführen.</span><span class="sxs-lookup"><span data-stu-id="8133f-122">You can use either the System Monitor or Performance Monitor to do these tasks.</span></span>  
  
## <a name="system-monitor-performance"></a><span data-ttu-id="8133f-123">Leistung des Systemmonitors</span><span class="sxs-lookup"><span data-stu-id="8133f-123">System Monitor Performance</span></span>  
 <span data-ttu-id="8133f-124">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und das Betriebssystem Microsoft Windows überwachen, um Leistungsprobleme näher zu untersuchen, sollten Sie sich dabei zunächst auf drei Hauptbereiche konzentrieren:</span><span class="sxs-lookup"><span data-stu-id="8133f-124">When you monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the Microsoft Windows operating system to investigate performance-related issues, concentrate your initial efforts in three main areas:</span></span>  
  
-   <span data-ttu-id="8133f-125">Datenträgeraktivität</span><span class="sxs-lookup"><span data-stu-id="8133f-125">Disk activity</span></span>  
  
-   <span data-ttu-id="8133f-126">Prozessorauslastung</span><span class="sxs-lookup"><span data-stu-id="8133f-126">Processor utilization</span></span>  
  
-   <span data-ttu-id="8133f-127">Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="8133f-127">Memory usage</span></span>  
  
 <span data-ttu-id="8133f-128">Die Überwachung eines Computers, auf dem der Systemmonitor ausgeführt wird, kann die Computerleistung geringfügig beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="8133f-128">Monitoring a computer on which System Monitor is running can affect computer performance slightly.</span></span> <span data-ttu-id="8133f-129">Sie sollten deshalb die Daten des Systemmonitors auf einem anderen Datenträger oder einem anderen Computer protokollieren, damit die Auswirkungen auf den überwachten Computer reduziert werden. Oder führen Sie den Systemmonitor von einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="8133f-129">Therefore, either log the System Monitor data to another disk (or computer) so that it reduces the effect on the computer being monitored, or run System Monitor from a remote computer.</span></span> <span data-ttu-id="8133f-130">Darüber hinaus sollten Sie nur die Leistungsindikatoren überwachen, an denen Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="8133f-130">Monitor only the counters in which you are interested.</span></span> <span data-ttu-id="8133f-131">Wenn Sie zu viele Leistungsindikatoren überwachen, wird der Überwachungsprozess um den Verwaltungsaufwand der Ressourcenverwendung erhöht und die Leistung des überwachten Computers beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="8133f-131">If you monitor too many counters, resource usage overhead is added to the monitoring process and affects the performance of the computer that is being monitored.</span></span>  
  
## <a name="system-monitor-tasks"></a><span data-ttu-id="8133f-132">Tasks des Systemmonitors</span><span class="sxs-lookup"><span data-stu-id="8133f-132">System Monitor Tasks</span></span>  
  
|<span data-ttu-id="8133f-133">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8133f-133">Task Description</span></span>|<span data-ttu-id="8133f-134">Thema</span><span class="sxs-lookup"><span data-stu-id="8133f-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8133f-135">Beschreibt die Verwendung des Systemmonitors und erläutert den Leistungsaufwand beim Einsatz des Systemmonitors.</span><span class="sxs-lookup"><span data-stu-id="8133f-135">Describes when to use System Monitor and discusses performance overhead when you use System Monitor.</span></span>|[<span data-ttu-id="8133f-136">Ausführen des Systemmonitors</span><span class="sxs-lookup"><span data-stu-id="8133f-136">Run System Monitor</span></span>](run-system-monitor.md)|  
|<span data-ttu-id="8133f-137">Beschreibt die Überwachung der Leistungsindikatoren eines Datenträgers zur Ermittlung der Datenträgeraktivität und der Menge von E/A, die von den SQL Server-Komponenten generiert wird.</span><span class="sxs-lookup"><span data-stu-id="8133f-137">Describes how to monitor disk counters to determine disk activity and the amount of I/O generated by their SQL Server components.</span></span>|[<span data-ttu-id="8133f-138">Überwachen der Datenträgerverwendung</span><span class="sxs-lookup"><span data-stu-id="8133f-138">Monitor Disk Usage</span></span>](monitor-disk-usage.md)|  
|<span data-ttu-id="8133f-139">Beschreibt die Überwachung einer Instanz von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zur Feststellung, ob sich die CPU-Nutzungsraten im Normalbereich bewegen.</span><span class="sxs-lookup"><span data-stu-id="8133f-139">Describes how to monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to determine whether CPU usage rates are within normal ranges.</span></span>|[<span data-ttu-id="8133f-140">Überwachen der CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="8133f-140">Monitor CPU Usage</span></span>](monitor-cpu-usage.md)|  
|<span data-ttu-id="8133f-141">Beschreibt die Überwachung einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zur Bestätigung einer Speicherauslastung im normalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="8133f-141">Describes how to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to confirm that memory usage is within typical ranges.</span></span>|[<span data-ttu-id="8133f-142">Überwachen der Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="8133f-142">Monitor Memory Usage</span></span>](monitor-memory-usage.md)|  
|<span data-ttu-id="8133f-143">Beschreibt das Erstellen einer Warnung, die ausgelöst wird, sobald ein Schwellenwert für einen Leistungsindikator des Systemmonitors erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="8133f-143">Describes how to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span>|[<span data-ttu-id="8133f-144">Erstellen einer SQL Server-Datenbankwarnung</span><span class="sxs-lookup"><span data-stu-id="8133f-144">Create a SQL Server Database Alert</span></span>](create-a-sql-server-database-alert.md)|  
|<span data-ttu-id="8133f-145">Beschreibt das Erstellen von Diagrammen, Warnungen, Protokollen und Berichten für die Überwachung einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8133f-145">Describes how to you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="8133f-146">Erstellen von Diagrammen, Warnungen, Protokollen und Berichten</span><span class="sxs-lookup"><span data-stu-id="8133f-146">Create Charts, Alerts, Logs, and Reports</span></span>](create-charts-alerts-logs-and-reports.md)|  
|<span data-ttu-id="8133f-147">Führt Objekte und Leistungsindikatoren auf, die der Systemmonitor zur Überwachung der Aktivität von Computern, die eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausführen, nutzt.</span><span class="sxs-lookup"><span data-stu-id="8133f-147">Lists objects and counters that System Monitor uses to monitor activity in computers running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="8133f-148">Verwenden von SQL Server-Objekten</span><span class="sxs-lookup"><span data-stu-id="8133f-148">Use SQL Server Objects</span></span>](use-sql-server-objects.md)|  
|<span data-ttu-id="8133f-149">Enthält eine Liste der Objekte und Leistungsindikatoren, die vom Systemmonitor zur Überwachung von In-Memory OLTP-Aktivitäten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8133f-149">Lists objects and counters that System Monitor uses to monitor In-Memory OLTP activity.</span></span>|[<span data-ttu-id="8133f-150">XTP-&#40;in-Memory-OLTP&#41; Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="8133f-150">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)|  
  
  
