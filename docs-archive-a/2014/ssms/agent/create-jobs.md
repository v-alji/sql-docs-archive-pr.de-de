---
title: Erstellen von Aufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: 465fb7fc-7622-4252-a178-ea51691c935b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 706b9348eed5b190f99543a74e7019dc1bde5978
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699242"
---
# <a name="create-jobs"></a><span data-ttu-id="1ef3b-102">Erstellen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="1ef3b-102">Create Jobs</span></span>
  <span data-ttu-id="1ef3b-103">Ein Auftrag besteht aus einer festgelegten Folge von Operationen, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent der Reihenfolge nach ausführt.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-103">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="1ef3b-104">Über einen Auftrag können zahlreiche Aktivitäten ausgeführt werden, u. a. das Ausführen von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts, Eingabeaufforderungsanwendungen, Microsoft ActiveX-Skripts, Integration Services-Paketen, Analysis Services-Befehlen und -abfragen bzw. Replikationstasks.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-104">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command prompt applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="1ef3b-105">Aufträge können wiederholte oder planbare Tasks ausführen, und sie können Benutzer in Form von Warnungen hinsichtlich des Auftragsstatus benachrichtigen. Dies führt zu einer deutlichen Vereinfachung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-105">Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="1ef3b-106">Um einen Auftrag erstellen zu können, muss ein Benutzer Mitglied einer der festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents oder Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-106">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="1ef3b-107">Ein Auftrag kann nur von seinem Besitzer bzw. Mitgliedern der **sysadmin** -Rolle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-107">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="1ef3b-108">Mitglieder der **sysadmin** -Rolle können anderen Benutzern den Auftragsbesitz zuweisen und sämtliche Aufträge ausführen, ungeachtet des Auftragsbesitzers.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-108">Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span> <span data-ttu-id="1ef3b-109">Weitere Informationen zu den festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1ef3b-109">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="1ef3b-110">Aufträge können so geschrieben werden, dass sie auf der lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder auf mehreren Instanzen in einem Unternehmen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-110">Jobs can be written to run on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or on multiple instances across an enterprise.</span></span> <span data-ttu-id="1ef3b-111">Zum Ausführen von Aufträgen auf mehreren Servern müssen Sie mindestens einen Masterserver und einen oder mehrere Zielserver einrichten.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-111">To run jobs on multiple servers, you must set up at least one master server and one or more target servers.</span></span> <span data-ttu-id="1ef3b-112">Weitere Informationen zu Master- und Zielservern finden Sie unter [Automatisierte Verwaltung in einem Unternehmen](automated-administration-across-an-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1ef3b-112">For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1ef3b-113">Agent zeichnet die Informationen von Aufträgen und Auftragsschritten im Auftragsverlauf auf.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-113">Agent records job and job step information in the job history.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1ef3b-114">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1ef3b-114">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ef3b-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1ef3b-115">**Description**</span></span>|<span data-ttu-id="1ef3b-116">**Thema**</span><span class="sxs-lookup"><span data-stu-id="1ef3b-116">**Topic**</span></span>|  
|<span data-ttu-id="1ef3b-117">Beschreibt, wie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-117">Describes how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="1ef3b-118">Erstellen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="1ef3b-118">Create a Job</span></span>](create-a-job.md)|  
|<span data-ttu-id="1ef3b-119">Beschreibt, wie Sie den Besitz eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrags einem anderen Benutzer neu zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-119">Describes how to reassign ownership of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>|[<span data-ttu-id="1ef3b-120">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="1ef3b-120">Give Others Ownership of a Job</span></span>](give-others-ownership-of-a-job.md)|  
|<span data-ttu-id="1ef3b-121">Beschreibt, wie Sie das Auftragsverlaufsprotokoll des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents einrichten.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-121">Describes how to set up the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="1ef3b-122">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="1ef3b-122">Set Up the Job History Log</span></span>](set-up-the-job-history-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="1ef3b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ef3b-123">See Also</span></span>  
 <span data-ttu-id="1ef3b-124">[Verwalten von Auftragsschritten](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="1ef3b-124">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="1ef3b-125">[Automatisierte Verwaltung in einem Unternehmen](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="1ef3b-125">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 <span data-ttu-id="1ef3b-126">[Erstellen und Anfügen von Zeitplänen an Aufträge](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef3b-126">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 <span data-ttu-id="1ef3b-127">[Ausführen von Aufträgen](run-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef3b-127">[Run Jobs](run-jobs.md) </span></span>  
 [<span data-ttu-id="1ef3b-128">Anzeigen oder Ändern von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="1ef3b-128">View or Modify Jobs</span></span>](view-or-modify-jobs.md)  
  
  
