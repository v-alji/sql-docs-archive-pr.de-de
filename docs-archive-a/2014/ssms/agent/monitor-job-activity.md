---
title: Überwachen der Auftragsaktivität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- jobs [SQL Server Agent], monitoring
- monitoring [SQL Server], jobs
- activity monitoring [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- SQL Server Agent Job Activity Monitor
- SQL Server Agent jobs, monitoring
- performance [SQL Server], jobs
- current activity
ms.assetid: 71cb432b-631d-4b8b-9965-e731b3d8266d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5088e029e90b4556c1559f8c948e8a8734762749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616334"
---
# <a name="monitor-job-activity"></a><span data-ttu-id="9359e-102">Überwachen der Auftragsaktivität</span><span class="sxs-lookup"><span data-stu-id="9359e-102">Monitor Job Activity</span></span>
  <span data-ttu-id="9359e-103">Sie können die aktuellen Aktivitäten aller definierten Aufträge auf einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] überwachen, indem Sie den Auftragsaktivitätsmonitor des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agents verwenden.</span><span class="sxs-lookup"><span data-stu-id="9359e-103">You can monitor the current activity of all defined jobs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job Activity Monitor.</span></span>  
  
## <a name="sql-server-agent-sessions"></a><span data-ttu-id="9359e-104">Sitzungen des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="9359e-104">SQL Server Agent Sessions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9359e-105">Agent erstellt jedes Mal, wenn der Dienst gestartet wird, eine neue Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9359e-105">Agent creates a new session each time the service starts.</span></span> <span data-ttu-id="9359e-106">Beim Erstellen einer neuen Sitzung wird die **sysjobactivity** -Tabelle in der **msdb** -Datenbank mit allen vorhandenen definierten Aufträgen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9359e-106">When a new session is created, the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="9359e-107">Beim Neustart des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents bleibt die letzte Auftragsaktivität in dieser Tabelle erhalten.</span><span class="sxs-lookup"><span data-stu-id="9359e-107">This table preserves the last activity for jobs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is restarted.</span></span> <span data-ttu-id="9359e-108">Jede Sitzung zeichnet die normale Auftragsaktivität des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents vom Anfang bis zum Ende des Auftrags auf.</span><span class="sxs-lookup"><span data-stu-id="9359e-108">Each session records [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent normal job activity from the start of the job to its finish.</span></span> <span data-ttu-id="9359e-109">Informationen zu diesen Sitzungen werden in der **syssessions** -Tabelle der **msdb** -Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9359e-109">Information about these sessions is stored in the **syssessions** table of the **msdb** database.</span></span>  
  
## <a name="job-activity-monitor"></a><span data-ttu-id="9359e-110">Auftragsaktivitätsmonitor</span><span class="sxs-lookup"><span data-stu-id="9359e-110">Job Activity Monitor</span></span>  
 <span data-ttu-id="9359e-111">Mit dem Auftragsaktivitätsmonitor können Sie die **sysjobactivity** -Tabelle mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9359e-111">The Job Activity Monitor allows you to view the **sysjobactivity** table by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="9359e-112">Sie können alle Aufträge auf dem Server anzeigen oder Filter definieren, um die Anzahl der angezeigten Aufträge zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="9359e-112">You can view all jobs on the server, or you can define filters to limit the number of jobs displayed.</span></span> <span data-ttu-id="9359e-113">Sie können die Auftragsinformationen auch sortieren, indem Sie auf eine Spaltenüberschrift im Raster **Agentauftragsaktivität** klicken.</span><span class="sxs-lookup"><span data-stu-id="9359e-113">You can also sort the job information by clicking on a column heading in the **Agent Job Activity** grid.</span></span> <span data-ttu-id="9359e-114">Wenn Sie beispielsweise die Spaltenüberschrift **Letzte Ausführung** auswählen, können Sie die Aufträge in der Reihenfolge anzeigen, in der sie zuletzt ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="9359e-114">For example, when you select the **Last Run** column heading, you can view the jobs in the order that they were last run.</span></span> <span data-ttu-id="9359e-115">Wenn Sie erneut auf die Spaltenüberschrift klicken, werden die Aufträge je nach ihrem letzten Ausführungsdatum so umgeschaltet, dass sie in auf- bzw. absteigender Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9359e-115">Clicking the column heading again toggles the jobs in ascending and descending order based on their last run date.</span></span>  
  
 <span data-ttu-id="9359e-116">Mit dem Auftragsaktivitätsmonitor können Sie folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9359e-116">Using the Job Activity Monitor you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="9359e-117">Starten und Beenden von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="9359e-117">Start and stop jobs.</span></span>  
  
-   <span data-ttu-id="9359e-118">Anzeigen von Auftragseigenschaften</span><span class="sxs-lookup"><span data-stu-id="9359e-118">View job properties.</span></span>  
  
-   <span data-ttu-id="9359e-119">Anzeigen des Verlaufsprotokolls für einen bestimmten Auftrag</span><span class="sxs-lookup"><span data-stu-id="9359e-119">View the history for a specific job.</span></span>  
  
-   <span data-ttu-id="9359e-120">Manuelles Aktualisieren der Informationen im Raster **Agentauftragsaktivität** oder Festlegen eines automatischen Aktualisierungsintervalls durch Klicken auf **Aktualisierungseinstellungen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9359e-120">Refresh the information in the **Agent Job Activity** grid manually or set an automatic refresh interval by clicking **View refresh settings**.</span></span>  
  
 <span data-ttu-id="9359e-121">Verwenden Sie den Auftragsaktivitätsmonitor, um zu ermitteln, für welche Aufträge eine Ausführung geplant ist, oder um festzustellen, welche Aufträge derzeit ausgeführt werden bzw. im Leerlauf sind. Sie können mit dem Auftragsaktivitätsmonitor auch das Ergebnis von Aufträgen anzeigen, die während der aktuellen Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="9359e-121">Use the Job Activity Monitor when you want to find out what jobs are scheduled to run, the last outcome of jobs that have run during the current session, and to find out which jobs are currently running or idle.</span></span> <span data-ttu-id="9359e-122">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst unerwartet einen Fehler erzeugt, können Sie ermitteln, welche Aufträge zum Zeitpunkt des Fehlers ausgeführt wurden, indem Sie im Auftragsaktivitätsmonitor die vorherige Sitzung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9359e-122">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service fails unexpectedly, you can determine which jobs were in the middle of being executed by looking at the previous session in the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="9359e-123">Erweitern Sie im Objekt-Explorer von **die Option** SQL Server-Agent [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , um den Auftragsaktivitätsmonitor zu öffnen. Klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor**, und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9359e-123">To open the Job Activity Monitor, expand **SQL Server Agent** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer, right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
 <span data-ttu-id="9359e-124">Sie können Auftragsaktivitäten für die aktuelle Sitzung auch mithilfe der gespeicherten Prozedur **sp_help_jobactivity**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9359e-124">You can also view job activity for the current session by using the stored procedure **sp_help_jobactivity**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9359e-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9359e-125">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9359e-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9359e-126">**Description**</span></span>|<span data-ttu-id="9359e-127">**Thema**</span><span class="sxs-lookup"><span data-stu-id="9359e-127">**Topic**</span></span>|  
|<span data-ttu-id="9359e-128">Beschreibt, wie der Laufzeitstatus von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Aufträgen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9359e-128">Describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="9359e-129">Auftragsaktivitäten anzeigen</span><span class="sxs-lookup"><span data-stu-id="9359e-129">View Job Activity</span></span>](view-job-activity.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9359e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9359e-130">See Also</span></span>  
 <span data-ttu-id="9359e-131">[Anzeigen der Auftrags Aktivität](view-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="9359e-131">[View Job Activity](view-job-activity.md) </span></span>  
 <span data-ttu-id="9359e-132">[dbo.sysjobactivity &#40;Transact-SQL-&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9359e-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span></span>  
 <span data-ttu-id="9359e-133">[dbo.sysSitzungen &#40;Transact-SQL-&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9359e-133">[dbo.syssessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span></span>  
 [<span data-ttu-id="9359e-134">sp_help_jobactivity &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="9359e-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql)  
  
  
