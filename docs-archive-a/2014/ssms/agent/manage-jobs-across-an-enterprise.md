---
title: Verwalten von Aufträgen über ein gesamtes Unternehmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 385435302b2e987c86afb17eaebf90e91bc93e56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616349"
---
# <a name="manage-jobs-across-an-enterprise"></a><span data-ttu-id="a0bdd-102">Verwalten von Aufträgen über ein gesamtes Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a0bdd-102">Manage Jobs Across an Enterprise</span></span>
  <span data-ttu-id="a0bdd-103">Wenn Sie Änderungen an den Definitionen von Multiserveraufträgen außerhalb von vornehmen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , müssen Sie die Änderungen an der Download Liste veröffentlichen, damit die Zielserver den aktualisierten Auftrag erneut herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="a0bdd-103">If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must post the changes to the download list so that target servers can download the updated job again.</span></span> <span data-ttu-id="a0bdd-104">Um sicherzustellen, dass die Zielserver über aktuelle Auftragsdefinitionen verfügen, führen Sie nach dem Aktualisieren des Multiserverauftrags eine INSERT-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="a0bdd-104">To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="a0bdd-105">Um Zielserver darüber zu benachrichtigen, dass ein Multiserverauftrag geändert wurde, müssen Sie den vorherigen Befehl aufrufen, nachdem Sie eine der folgenden Prozeduren verwendet haben:</span><span class="sxs-lookup"><span data-stu-id="a0bdd-105">To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:</span></span>  
  
-   [<span data-ttu-id="a0bdd-106">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a0bdd-106">sp_add_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-107">sp_update_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a0bdd-107">sp_update_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-108">sp_delete_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a0bdd-108">sp_delete_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-109">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0bdd-109">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-110">sp_detach_schedule &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="a0bdd-110">sp_detach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0bdd-111">Es ist nicht notwendig, **sp_post_msx_operation** aufzurufen, nachdem Sie **sp_update_job** oder **sp_delete_job**aufgerufen haben, da diese gespeicherten Prozeduren automatisch die notwendigen Änderungen der Downloadliste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a0bdd-111">It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.</span></span>  
  
 <span data-ttu-id="a0bdd-112">Mithilfe der folgenden Tasks werden häufig Aufträge über ein gesamtes Unternehmen hinweg verwaltet:</span><span class="sxs-lookup"><span data-stu-id="a0bdd-112">The following are common tasks for managing jobs across an enterprise:</span></span>  
  
 <span data-ttu-id="a0bdd-113">**So überprüfen Sie den Status eines Zielservers**</span><span class="sxs-lookup"><span data-stu-id="a0bdd-113">**To check the status of a target server**</span></span>  
  
-   [<span data-ttu-id="a0bdd-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bdd-114">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-115">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="a0bdd-115">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="a0bdd-116">**So wechseln Sie die Zielserver für einen Auftrag**</span><span class="sxs-lookup"><span data-stu-id="a0bdd-116">**To change the target servers for a job**</span></span>  
  
-   [<span data-ttu-id="a0bdd-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0bdd-117">SQL Server Management Studio</span></span>](modify-the-target-servers-for-a-job.md)  
  
-   [<span data-ttu-id="a0bdd-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bdd-118">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-119">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="a0bdd-119">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="a0bdd-120">**So ändern Sie den Speicherort eines Zielservers**</span><span class="sxs-lookup"><span data-stu-id="a0bdd-120">**To change the location of a target server**</span></span>  
  
-   [<span data-ttu-id="a0bdd-121">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0bdd-121">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="a0bdd-122">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bdd-122">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [<span data-ttu-id="a0bdd-123">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="a0bdd-123">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="a0bdd-124">**So synchronisieren Sie die Uhren der Zielserver**</span><span class="sxs-lookup"><span data-stu-id="a0bdd-124">**To synchronize target server clocks**</span></span>  
  
-   [<span data-ttu-id="a0bdd-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0bdd-125">SQL Server Management Studio</span></span>](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a0bdd-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bdd-126">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
 <span data-ttu-id="a0bdd-127">**So erzwingen Sie, dass ein Zielserver den Masterserver abruft**</span><span class="sxs-lookup"><span data-stu-id="a0bdd-127">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="a0bdd-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0bdd-128">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="a0bdd-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bdd-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="a0bdd-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0bdd-130">See Also</span></span>  
 [<span data-ttu-id="a0bdd-131">Verwalten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="a0bdd-131">Manage Events</span></span>](manage-events.md)  
  
  
