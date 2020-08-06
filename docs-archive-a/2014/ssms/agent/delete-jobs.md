---
title: Löschen von Aufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: stevestein
ms.author: sstein
ms.openlocfilehash: f66387a1334f91c29b8edddad293d76064430b39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722201"
---
# <a name="delete-jobs"></a><span data-ttu-id="8809e-102">Löschen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="8809e-102">Delete Jobs</span></span>
  <span data-ttu-id="8809e-103">Ein Auftrag besteht aus einer festgelegten Folge von Operationen, die der SQL Server-Agent der Reihenfolge nach ausführt.</span><span class="sxs-lookup"><span data-stu-id="8809e-103">A job is a specified series of operations performed sequentially by SQL Server Agent.</span></span> <span data-ttu-id="8809e-104">Standardmäßig werden Aufträge nicht gelöscht, wenn die Ausführung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8809e-104">By default, jobs are not deleted when execution finishes.</span></span> <span data-ttu-id="8809e-105">Sie können einen oder mehrere [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agentaufträge unabhängig davon löschen, ob der Auftrag erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8809e-105">You can delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs regardless of success or failure of the job.</span></span> <span data-ttu-id="8809e-106">Außerdem können Sie den [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zum automatischen Löschen von Aufträgen konfigurieren, wenn diese erfolgreich sind, einen Fehler erzeugen oder abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8809e-106">You can also configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>  
  
 <span data-ttu-id="8809e-107">Standardmäßig können Mitglieder der festen Server Rolle **sysadmin** die [sp_delete_job &#40;gespeicherten Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) -System Prozedur ausführen, um einen Auftrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8809e-107">By default, members of the **sysadmin** fixed server role can execute the [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) system stored procedure to delete a job.</span></span> <span data-ttu-id="8809e-108">Andere Benutzer müssen Mitglieder der festen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Datenbankrollen in der **msdb** -Datenbank sein:</span><span class="sxs-lookup"><span data-stu-id="8809e-108">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="8809e-109">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="8809e-109">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="8809e-110">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="8809e-110">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="8809e-111">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="8809e-111">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="8809e-112">Weitere Informationen zu den Berechtigungen dieser Rollen finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8809e-112">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="8809e-113">Nur Mitglieder der festen Serverrolle **sysadmin** können **sp_delete_job** ausführen, um einen beliebigen Auftrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8809e-113">Members of the **sysadmin** fixed server role can execute **sp_delete_job** to delete any job.</span></span> <span data-ttu-id="8809e-114">Ein Benutzer, der kein Mitglied der festen Serverrolle **sysadmin** ist, kann nur Aufträge löschen, deren Besitzer er ist.</span><span class="sxs-lookup"><span data-stu-id="8809e-114">A user that is not a member of the **sysadmin** fixed server role can only delete jobs owned by that user.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8809e-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8809e-115">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8809e-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8809e-116">**Description**</span></span>|<span data-ttu-id="8809e-117">**Thema**</span><span class="sxs-lookup"><span data-stu-id="8809e-117">**Topic**</span></span>|  
|<span data-ttu-id="8809e-118">Es wird beschrieben, wie Sie einen oder mehrere [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agentaufträge löschen.</span><span class="sxs-lookup"><span data-stu-id="8809e-118">Describes how to delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="8809e-119">Löschen eines oder mehrerer Aufträge</span><span class="sxs-lookup"><span data-stu-id="8809e-119">Delete One or More Jobs</span></span>](delete-one-or-more-jobs.md)|  
|<span data-ttu-id="8809e-120">Es wird die Vorgehensweise zum Konfigurieren des [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents für das automatische Löschen von Aufträgen beschrieben, wenn diese erfolgreich sind, einen Fehler erzeugen oder abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8809e-120">Describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>|[<span data-ttu-id="8809e-121">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="8809e-121">Automatically Delete a Job</span></span>](automatically-delete-a-job.md)|  
  
  
