---
title: Anlegen und Zuweisen von Zeitplänen zu Aufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server]
- scheduling jobs [SQL Server]
- jobs [SQL Server], scheduling
- CPU [SQL Server], idle conditions
- automatic job processing
- SQL Server Agent jobs, scheduling
- idle time [SQL Server]
ms.assetid: 079c2984-0052-4a37-a2b8-4ece56e6b6b5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ced47013b6552725e6350b113a3722b066016a6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699260"
---
# <a name="create-and-attach-schedules-to-jobs"></a><span data-ttu-id="cb22a-102">Anlegen und Zuweisen von Zeitplänen zu Aufträgen</span><span class="sxs-lookup"><span data-stu-id="cb22a-102">Create and Attach Schedules to Jobs</span></span>
  <span data-ttu-id="cb22a-103">Zeitpläne für Aufträge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents zu erstellen bedeutet, die Bedingung(en) zu definieren, durch die die Ausführung des Auftrags ohne Benutzerinteraktion gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cb22a-103">Scheduling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs means defining the condition or conditions that cause the job to begin running without user interaction.</span></span> <span data-ttu-id="cb22a-104">Sie können einen Auftrag so planen, dass er automatisch ausgeführt wird, indem Sie einen neuen Zeitplan für den Auftrag erstellen oder indem Sie dem Auftrag einen vorhandenen Zeitplan zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-104">You can schedule a job to run automatically by creating a new schedule for the job, or by attaching an existing schedule to the job.</span></span>  
  
 <span data-ttu-id="cb22a-105">Es gibt zwei Möglichkeiten, einen Zeitplan zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="cb22a-105">There are two ways to create a schedule:</span></span>  
  
-   <span data-ttu-id="cb22a-106">Erstellen Sie den Zeitplan, während Sie einen Auftrag erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-106">Create the schedule while you are creating a job.</span></span>  
  
-   <span data-ttu-id="cb22a-107">Erstellen Sie den Zeitplan im Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="cb22a-107">Create the schedule in Object Explorer.</span></span>  
  
 <span data-ttu-id="cb22a-108">Nach dem Erstellen eines Zeitplans können Sie ihn mehreren Aufträgen zuweisen, auch wenn der Zeitplan für einen bestimmten Auftrag erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb22a-108">After a schedule has been created, you can attach that schedule to multiple jobs, even if the schedule was created for a specific job.</span></span> <span data-ttu-id="cb22a-109">Sie können auch Zeitpläne von Aufträgen trennen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-109">You can also detach schedules from jobs.</span></span>  
  
 <span data-ttu-id="cb22a-110">Ein Zeitplan kann zeit- oder ereignisbasiert sein.</span><span class="sxs-lookup"><span data-stu-id="cb22a-110">A schedule can be based upon time or an event.</span></span> <span data-ttu-id="cb22a-111">Zum Beispiel können Sie einen Auftrag so planen, dass er zu den folgenden Zeitpunkten ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="cb22a-111">For example, you can schedule a job to run at the following times:</span></span>  
  
-   <span data-ttu-id="cb22a-112">Ausführung beim Start des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agents.</span><span class="sxs-lookup"><span data-stu-id="cb22a-112">Whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts.</span></span>  
  
-   <span data-ttu-id="cb22a-113">Ausführung, wenn sich die CPU-Auslastung des Computers in einem Bereich befindet, den Sie als Leerlauf definiert haben.</span><span class="sxs-lookup"><span data-stu-id="cb22a-113">Whenever CPU utilization of the computer is at a level you have defined as idle.</span></span>  
  
-   <span data-ttu-id="cb22a-114">Einmalige Ausführung zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="cb22a-114">One time, at a specific date and time.</span></span>  
  
-   <span data-ttu-id="cb22a-115">Auf der Grundlage einer Zeitplanserie.</span><span class="sxs-lookup"><span data-stu-id="cb22a-115">On a recurring schedule.</span></span>  
  
 <span data-ttu-id="cb22a-116">Als Alternative zu Auftragszeitplänen können Sie auch eine Warnung erstellen, durch die in Reaktion auf ein Ereignis ein bestimmter Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb22a-116">As an alternative to job schedules, you can also create an alert that responds to an event by running a job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb22a-117">Es kann nur jeweils eine einzige Instanz eines Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb22a-117">Only one instance of the job can be run at a time.</span></span> <span data-ttu-id="cb22a-118">Wenn Sie versuchen, einen Auftrag manuell auszuführen, der bereits im Rahmen eines Zeitplans ausgeführt wird, lehnt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Anforderung ab.</span><span class="sxs-lookup"><span data-stu-id="cb22a-118">If you try to run a job manually while it is running as scheduled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refuses the request.</span></span>  
  
 <span data-ttu-id="cb22a-119">Um zu verhindern, dass ein geplanter Auftrag ausgeführt wird, müssen Sie eine der folgendem Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="cb22a-119">To prevent a scheduled job from running, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="cb22a-120">Den Zeitplan deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb22a-120">Disable the schedule.</span></span>  
  
-   <span data-ttu-id="cb22a-121">Den Auftrag deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb22a-121">Disable the job.</span></span>  
  
-   <span data-ttu-id="cb22a-122">Den Zeitplan von dem Auftrag trennen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-122">Detach the schedule from the job.</span></span>  
  
-   <span data-ttu-id="cb22a-123">Den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst beenden.</span><span class="sxs-lookup"><span data-stu-id="cb22a-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
-   <span data-ttu-id="cb22a-124">Den Zeitplan löschen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-124">Delete the schedule.</span></span>  
  
 <span data-ttu-id="cb22a-125">Wenn der Zeitplan nicht aktiviert ist, kann der Auftrag dennoch als Reaktion auf eine Warnung oder durch einen Benutzer manuell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb22a-125">If the schedule is not enabled, the job can still run in response to an alert or when a user runs the job manually.</span></span> <span data-ttu-id="cb22a-126">Wenn der Auftragszeitplan nicht aktiviert ist, ist der Zeitplan auch für keinen der anderen Aufträge aktiviert, die ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb22a-126">When a job schedule is not enabled, the schedule is not enabled for any job that uses the schedule.</span></span>  
  
 <span data-ttu-id="cb22a-127">Ein deaktivierter Zeitplan muss explizit erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="cb22a-127">You must explicitly re-enable a schedule that has been disabled.</span></span> <span data-ttu-id="cb22a-128">Beim Bearbeiten eines Zeitplans wird dieser nicht automatisch erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cb22a-128">Editing the schedule does not automatically re-enable the schedule.</span></span>  
  
## <a name="scheduling-start-dates"></a><span data-ttu-id="cb22a-129">Planen von Startdaten</span><span class="sxs-lookup"><span data-stu-id="cb22a-129">Scheduling Start Dates</span></span>  
 <span data-ttu-id="cb22a-130">Das Startdatum eines Zeitplans muss größer als oder gleich 19900101 sein.</span><span class="sxs-lookup"><span data-stu-id="cb22a-130">The start date of a schedule must be greater than or equal to 19900101.</span></span>  
  
 <span data-ttu-id="cb22a-131">Wenn Sie einem Auftrag einen Zeitplan zuweisen, überprüfen Sie das Startdatum, das der Zeitplan für das erstmalige Ausführen des Auftrags verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb22a-131">When you are attaching a schedule to a job, you should review the start date that the schedule uses to run the job for the first time.</span></span> <span data-ttu-id="cb22a-132">Das Startdatum hängt von dem Tag und der Uhrzeit ab, zu denen Sie den Zeitplan dem Auftrag zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-132">The start date depends upon the day and time when you attach the schedule to the job.</span></span> <span data-ttu-id="cb22a-133">Sie erstellen z. B. einen Zeitplan, der an jedem zweiten Montag um 8:00 Uhr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb22a-133">For example, you create a schedule that runs every other Monday at 8:00 A.M.</span></span> <span data-ttu-id="cb22a-134">Wenn Sie einen Auftrag am</span><span class="sxs-lookup"><span data-stu-id="cb22a-134">If you create a job at 10:00 A.M.</span></span> <span data-ttu-id="cb22a-135">Montag, 3. März 2008, um 10:00 Uhr erstellen, ist das Startdatum Montag, 17. März 2008.</span><span class="sxs-lookup"><span data-stu-id="cb22a-135">on Monday, March 3, 2008, the schedule start date is Monday, March 17, 2008.</span></span> <span data-ttu-id="cb22a-136">Wenn Sie einen weiteren Auftrag am Dienstag, dem 4. März 2008 erstellen, ist das Startdatum Montag, der 10. März 2008.</span><span class="sxs-lookup"><span data-stu-id="cb22a-136">If you create another job on Tuesday, March 4, 2008, the schedule start date is Monday, March 10, 2008.</span></span>  
  
 <span data-ttu-id="cb22a-137">Sie können das Startdatum des Zeitplans ändern, nachdem Sie den Zeitplan einem Auftrag zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="cb22a-137">You can change the schedule start date after you attach the schedule to a job.</span></span>  
  
## <a name="cpu-idle-schedules"></a><span data-ttu-id="cb22a-138">CPU-Leerlauf-Zeitpläne</span><span class="sxs-lookup"><span data-stu-id="cb22a-138">CPU Idle Schedules</span></span>  
 <span data-ttu-id="cb22a-139">Zur maximalen Nutzung der CPU-Ressourcen können Sie eine CPU-Leerlaufbedingung für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent definieren.</span><span class="sxs-lookup"><span data-stu-id="cb22a-139">To maximize CPU resources, you can define a CPU idle condition for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cb22a-140">Agent verwendet die CPU-Leerlaufbedingung, um den optimalen Zeitpunkt für die Ausführung von Aufträgen festzustellen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-140">Agent uses the CPU idle condition setting to determine the best time to run jobs.</span></span> <span data-ttu-id="cb22a-141">So können Sie beispielsweise einen Zeitplan für einen Auftrag zur Neuerstellung von Indizes erstellen, der während der CPU-Leerlaufzeit und zu Zeiten mit geringer Produktion eintritt.</span><span class="sxs-lookup"><span data-stu-id="cb22a-141">For example, you can schedule a job to rebuild indexes during CPU idle time and slow production periods.</span></span>  
  
 <span data-ttu-id="cb22a-142">Bevor Sie Aufträge definieren, die während der CPU-Leerlaufzeit ausgeführt werden sollen, müssen Sie die CPU-Auslastung während der normalen Verarbeitung ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cb22a-142">Before you define jobs to run during CPU idle time, determine the load on the CPU during normal processing.</span></span> <span data-ttu-id="cb22a-143">Dazu können Sie mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] oder mit dem Systemmonitor den Serververkehr überwachen und Statistiken erfassen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-143">To do this, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor server traffic and collect statistics.</span></span> <span data-ttu-id="cb22a-144">Anschließend können Sie die zusammengestellten Informationen zum Festlegen des Prozentwertes und der Dauer der CPU-Leerlaufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb22a-144">You can then use the information you gather to set the CPU idle time percentage and duration.</span></span>  
  
 <span data-ttu-id="cb22a-145">Definieren Sie die CPU-Leerlaufbedingung als Prozentwert, unter den die CPU-Nutzung für eine bestimmte Dauer absinken muss.</span><span class="sxs-lookup"><span data-stu-id="cb22a-145">Define the CPU idle condition as a percentage below which CPU usage must remain for a specified time.</span></span> <span data-ttu-id="cb22a-146">Legen Sie dann die Zeitdauer fest.</span><span class="sxs-lookup"><span data-stu-id="cb22a-146">Next, set the amount of time.</span></span> <span data-ttu-id="cb22a-147">Wenn die CPU-Nutzung für die angegebene Zeitdauer unter den angegebenen Prozentwert abfällt, startet der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent alle Aufträge mit CPU-Leerlaufzeitplänen.</span><span class="sxs-lookup"><span data-stu-id="cb22a-147">When the CPU usage is below the specified percentage for the specified amount of time, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts all jobs that have a CPU idle time schedule.</span></span> <span data-ttu-id="cb22a-148">Weitere Informationen zur Verwendung von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] oder des System Monitors zur Überwachung der CPU-Auslastung finden Sie unter [Überwachen der CPU-Auslastung](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span><span class="sxs-lookup"><span data-stu-id="cb22a-148">For more information on using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor CPU usage, see [Monitor CPU Usage](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="cb22a-149">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="cb22a-149">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb22a-150">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cb22a-150">**Description**</span></span>|<span data-ttu-id="cb22a-151">**Thema**</span><span class="sxs-lookup"><span data-stu-id="cb22a-151">**Topic**</span></span>|  
|<span data-ttu-id="cb22a-152">Beschreibt, wie ein Zeitplan für einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cb22a-152">Describes how to create a schedule for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="cb22a-153">Erstellen eines Zeitplans</span><span class="sxs-lookup"><span data-stu-id="cb22a-153">Create a Schedule</span></span>](create-a-schedule.md)|  
|<span data-ttu-id="cb22a-154">Beschreibt, wie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag geplant wird.</span><span class="sxs-lookup"><span data-stu-id="cb22a-154">Describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="cb22a-155">Planen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="cb22a-155">Schedule a Job</span></span>](schedule-a-job.md)|  
|<span data-ttu-id="cb22a-156">Erläutert, wie die CPU-Leerlaufbedingung für den Server definiert wird.</span><span class="sxs-lookup"><span data-stu-id="cb22a-156">Explains how to define the CPU idle condition for your server.</span></span>|[<span data-ttu-id="cb22a-157">Festlegen der Leerlaufzeit und Leerlaufdauer der CPU &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cb22a-157">Set CPU Idle Time and Duration &#40;SQL Server Management Studio&#41;</span></span>](set-cpu-idle-time-and-duration-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="cb22a-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb22a-158">See Also</span></span>  
 <span data-ttu-id="cb22a-159">[sp_help_jobschedule &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cb22a-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span></span>  
 [<span data-ttu-id="cb22a-160">dbo.sysjobzeitpläne &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="cb22a-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobschedules-transact-sql)  
  
  
