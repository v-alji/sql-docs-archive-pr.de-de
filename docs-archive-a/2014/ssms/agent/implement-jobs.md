---
title: Implementieren von Aufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608207"
---
# <a name="implement-jobs"></a><span data-ttu-id="b1759-102">Implementieren von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b1759-102">Implement Jobs</span></span>
  <span data-ttu-id="b1759-103">Sie können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Aufträge verwenden, um regelmäßig anfallende administrative Tasks zu automatisieren und periodisch ausführen, sodass die Effizienz der Verwaltung verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="b1759-103">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.</span></span>  
  
 <span data-ttu-id="b1759-104">Ein Auftrag besteht aus einer festgelegten Folge von Operationen, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent der Reihenfolge nach ausführt.</span><span class="sxs-lookup"><span data-stu-id="b1759-104">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="b1759-105">Ein Auftrag kann eine Reihe von Aktivitäten ausführen, z. B. das Ausführen von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts, Befehlszeilenanwendungen, Microsoft ActiveX-Skripts, Integration Services-Paketen, Analysis Services-Befehlen und -Abfragen sowie Replikationstasks.</span><span class="sxs-lookup"><span data-stu-id="b1759-105">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="b1759-106">Aufträge können wiederkehrende oder planbare Tasks ausführen, und sie können Benutzer durch Generieren von Warnungen automatisch über den Auftragsstatus informieren, sodass die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verwaltung erheblich vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="b1759-106">Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="b1759-107">Sie können einen Auftrag manuell ausführen oder ihn so konfigurieren, dass er gemäß einem Zeitplan oder als Reaktion auf Warnungen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1759-107">You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b1759-108">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b1759-108">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1759-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b1759-109">**Description**</span></span>|<span data-ttu-id="b1759-110">**Thema**</span><span class="sxs-lookup"><span data-stu-id="b1759-110">**Topic**</span></span>|  
|<span data-ttu-id="b1759-111">Enthält Informationen zum Erstellen von Aufträgen und Zuweisen des Besitz.</span><span class="sxs-lookup"><span data-stu-id="b1759-111">Contains information about creating jobs and assigning ownership.</span></span>|[<span data-ttu-id="b1759-112">Erstellen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b1759-112">Create Jobs</span></span>](create-jobs.md)|  
|<span data-ttu-id="b1759-113">Enthält Informationen zum Organisieren von Aufträgen in Kategorien.</span><span class="sxs-lookup"><span data-stu-id="b1759-113">Contains information about organizing jobs into categories.</span></span>|[<span data-ttu-id="b1759-114">Aufträge organisieren</span><span class="sxs-lookup"><span data-stu-id="b1759-114">Organize Jobs</span></span>](organize-jobs.md)|  
|<span data-ttu-id="b1759-115">Enthält Informationen zu den verschiedenen Auftragsschritten, die Sie erstellen können, und beschreibt, wie Sie diese Auftragsschritte verwalten.</span><span class="sxs-lookup"><span data-stu-id="b1759-115">Contains information about the different kinds of job steps you can create and how to manage them.</span></span>|[<span data-ttu-id="b1759-116">Verwalten von Auftragsschritten</span><span class="sxs-lookup"><span data-stu-id="b1759-116">Manage Job Steps</span></span>](manage-job-steps.md)|  
|<span data-ttu-id="b1759-117">Enthält Informationen zur Definition des Auftragsbeginns sowie der Häufigkeit der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="b1759-117">Contains information about how to define when jobs start running and how often they should run.</span></span>|[<span data-ttu-id="b1759-118">Anlegen und Zuweisen von Zeitplänen zu Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b1759-118">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)|  
|<span data-ttu-id="b1759-119">Enthält Informationen zur manuellen Ausführung von Aufträgen (ohne Zeitplan).</span><span class="sxs-lookup"><span data-stu-id="b1759-119">Contains information about manually running jobs (without a schedule).</span></span>|[<span data-ttu-id="b1759-120">Ausführen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b1759-120">Run Jobs</span></span>](run-jobs.md)|  
|<span data-ttu-id="b1759-121">Enthält Informationen zur Konfiguration des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents für die Reaktion auf Aufträge.</span><span class="sxs-lookup"><span data-stu-id="b1759-121">Contains information about how you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to jobs.</span></span> <span data-ttu-id="b1759-122">Sie können den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent z. B. so konfigurieren, dass Administratoren bei der Beendigung von Aufträgen benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1759-122">For example, you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.</span></span>|[<span data-ttu-id="b1759-123">Angeben von Auftragsantworten</span><span class="sxs-lookup"><span data-stu-id="b1759-123">Specify Job Responses</span></span>](specify-job-responses.md)|  
|<span data-ttu-id="b1759-124">Enthält Informationen zum Anzeigen vorhandener Aufträge, zum Auftragsverlauf nach der Ausführung und zum Ändern von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="b1759-124">Contains information about how to view existing jobs, their history once executes, and how to modify them.</span></span>|[<span data-ttu-id="b1759-125">Anzeigen oder Ändern von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b1759-125">View or Modify Jobs</span></span>](view-or-modify-jobs.md)|  
|<span data-ttu-id="b1759-126">Enthält Informationen zum Löschen von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="b1759-126">Contains information about how to delete jobs.</span></span>|[<span data-ttu-id="b1759-127">Löschen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="b1759-127">Delete Jobs</span></span>](delete-jobs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b1759-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1759-128">See Also</span></span>  
 [<span data-ttu-id="b1759-129">Implementieren der SQL Server-Agent-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b1759-129">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
