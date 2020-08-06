---
title: Anzeigen oder Ändern von Aufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- jobs [SQL Server Agent], viewing
- modifying jobs
- viewing jobs
- SQL Server Agent jobs, viewing
- SQL Server Agent jobs, modifying
- displaying jobs
ms.assetid: 57f649b8-190c-4304-abd7-7ca5297deab7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d0d731d25c20597be3ac84adfacd8973e4a51cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699140"
---
# <a name="view-or-modify-jobs"></a><span data-ttu-id="62d36-102">Anzeigen oder Ändern von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="62d36-102">View or Modify Jobs</span></span>
  <span data-ttu-id="62d36-103">Jeden Auftrag, den Sie erstellt haben, können Sie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d36-103">You can view any job you have created.</span></span> <span data-ttu-id="62d36-104">Nachdem Sie einen Auftrag ausgeführt haben, können Sie auch den Auftragsverlauf anzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d36-104">After you have run a job, you can also view its history.</span></span> <span data-ttu-id="62d36-105">Auf diese Weise erfahren Sie, wann der Auftrag ausgeführt wurde, den Status des Auftrags insgesamt sowie den Status jedes Auftragsschritts.</span><span class="sxs-lookup"><span data-stu-id="62d36-105">Viewing a job's history allows you to see when the job ran, the status of the job as a whole, and the status of each job step in the job.</span></span> <span data-ttu-id="62d36-106">Sie sehen, ob bei dem Auftrag in der Vergangenheit jemals ein Fehler aufgetreten ist, wann der Auftrag zuletzt erfolgreich ausgeführt wurde sowie welche Ausgabe bei jeder Ausführung des Auftrags erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="62d36-106">You can see whether the job ever failed in the past, when the job last completed successfully, and what output the job created each time the job ran.</span></span> <span data-ttu-id="62d36-107">Mitglieder der festen Serverrolle **sysadmin** können jeden Auftrag anzeigen oder ändern, unabhängig vom Besitzer.</span><span class="sxs-lookup"><span data-stu-id="62d36-107">Members of the **sysadmin** fixed server role can view or modify any job, regardless of the owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62d36-108">Ein Auftrag muss mindestens einmal ausgeführt worden sein, damit ein Auftragsverlauf vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62d36-108">A job must have been executed at least one time for there to be a job history.</span></span> <span data-ttu-id="62d36-109">Sie können die Gesamtgröße des Auftragsverlaufsprotokolls und die Größe pro Auftrag begrenzen.</span><span class="sxs-lookup"><span data-stu-id="62d36-109">You can limit the total size of the job history log and the size per job.</span></span>  
  
 <span data-ttu-id="62d36-110">Schließlich können Sie einen Auftrag an neue Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="62d36-110">Finally, you can modify a job to meet new requirements.</span></span> <span data-ttu-id="62d36-111">Sie können Folgendes ändern:</span><span class="sxs-lookup"><span data-stu-id="62d36-111">You can modify:</span></span>  
  
-   <span data-ttu-id="62d36-112">Benachrichtigungsoptionen</span><span class="sxs-lookup"><span data-stu-id="62d36-112">Response options</span></span>  
  
-   <span data-ttu-id="62d36-113">Zeitpläne</span><span class="sxs-lookup"><span data-stu-id="62d36-113">Schedules</span></span>  
  
-   <span data-ttu-id="62d36-114">Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="62d36-114">Job steps</span></span>  
  
-   <span data-ttu-id="62d36-115">Besitz</span><span class="sxs-lookup"><span data-stu-id="62d36-115">Ownership</span></span>  
  
-   <span data-ttu-id="62d36-116">Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="62d36-116">Job category</span></span>  
  
-   <span data-ttu-id="62d36-117">Zielserver (ausschließlich bei Multiserveraufträgen)</span><span class="sxs-lookup"><span data-stu-id="62d36-117">Target servers (multiserver jobs only)</span></span>  
  
 <span data-ttu-id="62d36-118">Wenn Sie Änderungen an Multiserveraufträgen vornehmen, müssen Sie die Änderungen der Downloadliste bereitstellen, damit die Zielserver den aktualisierten Auftrag herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="62d36-118">To make sure that changes to multiserver jobs take effect, you must post the changes to the download list so that target servers can download the updated job.</span></span> <span data-ttu-id="62d36-119">Um sicherzustellen, dass die Zielserver über die aktuellsten Auftragsdefinitionen verfügen, führen Sie nach dem Aktualisieren des Multiserverauftrags wie folgt eine INSERT-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="62d36-119">To ensure that target servers have the most current job definitions, post an INSERT instruction after you update the multiserver job as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="62d36-120">Weitere Informationen finden Sie unter [sp_purge_jobhistory &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62d36-120">For more information, see [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span></span>  
  
 <span data-ttu-id="62d36-121">Mitglieder der festen Serverrolle **sysadmin** können die Definition oder den Verlauf jedes Auftrags anzeigen und können jeden Auftrag ändern.</span><span class="sxs-lookup"><span data-stu-id="62d36-121">Members of the **sysadmin** fixed server role can view the definition or history of any job, and can modify any job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="62d36-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="62d36-122">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62d36-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="62d36-123">**Description**</span></span>|<span data-ttu-id="62d36-124">**Thema**</span><span class="sxs-lookup"><span data-stu-id="62d36-124">**Topic**</span></span>|  
|<span data-ttu-id="62d36-125">Beschreibt, wie [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Aufträge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="62d36-125">Describes how to view [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="62d36-126">View a Job</span><span class="sxs-lookup"><span data-stu-id="62d36-126">View a Job</span></span>](view-a-job.md)|  
|<span data-ttu-id="62d36-127">Beschreibt, wie das Auftragsverlaufsprotokoll des [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agents angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="62d36-127">Describes how to view the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="62d36-128">Anzeigen des Auftragsverlaufs</span><span class="sxs-lookup"><span data-stu-id="62d36-128">View the Job History</span></span>](view-the-job-history.md)|  
|<span data-ttu-id="62d36-129">Beschreibt, wie der Inhalt des Auftragsverlaufsprotokolls des [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agents gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="62d36-129">Describes how to delete the contents of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="62d36-130">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="62d36-130">Clear the Job History Log</span></span>](clear-the-job-history-log.md)|  
|<span data-ttu-id="62d36-131">Beschreibt, wie Größenbeschränkungen für Auftragsverlaufsprotokolle des [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agents festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="62d36-131">Describes how to set size limits for [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history logs.</span></span>|[<span data-ttu-id="62d36-132">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="62d36-132">Resize the Job History Log</span></span>](resize-the-job-history-log.md)|  
|<span data-ttu-id="62d36-133">Beschreibt, wie die Eigenschaften von [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Aufträgen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="62d36-133">Describes how to change the properties of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="62d36-134">Ändern eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="62d36-134">Modify a Job</span></span>](modify-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="62d36-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62d36-135">See Also</span></span>  
 [<span data-ttu-id="62d36-136">dbo.sysJobHistory &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="62d36-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
  
  
