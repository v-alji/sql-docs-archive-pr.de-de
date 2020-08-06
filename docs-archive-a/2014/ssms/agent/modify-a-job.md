---
title: Ändern eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
ms.assetid: dd5e5f20-20c4-4ab9-a19a-db87577dcd43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d25830ad119a1f5f344a4dcf318c35bee5f86ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616346"
---
# <a name="modify-a-job"></a><span data-ttu-id="d0e7e-102">Ändern eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="d0e7e-102">Modify a Job</span></span>
  <span data-ttu-id="d0e7e-103">In diesem Thema wird beschrieben, wie die Eigenschaften von- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträgen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-103">This topic describes how to change the properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="d0e7e-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d0e7e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d0e7e-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d0e7e-105">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="d0e7e-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d0e7e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d0e7e-107">Security</span><span class="sxs-lookup"><span data-stu-id="d0e7e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d0e7e-108">**So ändern Sie einen Auftrag mit**</span><span class="sxs-lookup"><span data-stu-id="d0e7e-108">**To modify a job, using:**</span></span>  
  
     [<span data-ttu-id="d0e7e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0e7e-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d0e7e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0e7e-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d0e7e-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d0e7e-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0e7e-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d0e7e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d0e7e-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d0e7e-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d0e7e-114">Ein Masterauftrag für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent kann nicht gleichzeitig lokale Server und Remoteserver als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-114">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d0e7e-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d0e7e-115">Security</span></span>  
 <span data-ttu-id="d0e7e-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d0e7e-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="d0e7e-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d0e7e-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d0e7e-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0e7e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="d0e7e-119">So ändern Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="d0e7e-119">To modify a job</span></span>  
  
1.  <span data-ttu-id="d0e7e-120">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d0e7e-121">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie ändern möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d0e7e-122">Aktualisieren Sie im Dialogfeld **Auftragseigenschaften** mithilfe der entsprechenden Seiten die Eigenschaften, die Schritte, den Zeitplan, die Warnungen und die Benachrichtigungen des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-122">In the **Job Properties** dialog box, update the job's properties, steps, schedule, alerts, and notifications using the corresponding pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d0e7e-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0e7e-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="d0e7e-124">So ändern Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="d0e7e-124">To modify a job</span></span>  
  
1.  <span data-ttu-id="d0e7e-125">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von Database Engine (Datenbankmodul) her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-125">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d0e7e-126">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-126">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d0e7e-127">Verwenden Sie im Abfragefenster die folgenden gespeicherten Systemprozeduren, um einen Auftrag zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-127">In the query window, use the following system stored procedures to modify a job.</span></span>  
  
    -   <span data-ttu-id="d0e7e-128">Führen Sie [sp_update_job &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) aus, um die Attribute eines Auftrags zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-128">Execute [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) to change the attributes of a job.</span></span>  
  
    -   <span data-ttu-id="d0e7e-129">Führen Sie [sp_update_schedule &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) aus, um die Zeit Plan Details für eine Auftrags Definition zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-129">Execute [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) to change the scheduling details for a job definition.</span></span>  
  
    -   <span data-ttu-id="d0e7e-130">Führen Sie [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) aus, um neue Auftrags Schritte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-130">Execute [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) to add new job steps.</span></span>  
  
    -   <span data-ttu-id="d0e7e-131">Führen Sie [sp_update_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) aus, um bereits vorhandene Auftrags Schritte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-131">Execute [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) to change pre-existing job steps.</span></span>  
  
    -   <span data-ttu-id="d0e7e-132">Führen Sie [sp_delete_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) aus, um einen Auftrags Schritt aus einem Auftrag zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-132">Execute [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) to remove a job step from a job.</span></span>  
  
    -   <span data-ttu-id="d0e7e-133">Weitere gespeicherte Prozeduren zum Ändern von SQL Server-Agent-Masteraufträgen:</span><span class="sxs-lookup"><span data-stu-id="d0e7e-133">Additional stored procedures to modify any SQL Server Agent master job:</span></span>  
  
        -   <span data-ttu-id="d0e7e-134">Führen Sie [sp_delete_jobserver &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) aus, um einen Server zu löschen, der derzeit einem Auftrag zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-134">Execute [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) to delete a server currently associated with a job.</span></span>  
  
        -   <span data-ttu-id="d0e7e-135">Führen Sie [sp_add_jobserver &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) aus, um einen Server mit dem aktuellen Auftrag zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-135">Execute [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) to associate a server with the current job.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d0e7e-136">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d0e7e-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="d0e7e-137">**So ändern Sie einen Auftrag**</span><span class="sxs-lookup"><span data-stu-id="d0e7e-137">**To modify a job**</span></span>  
  
 <span data-ttu-id="d0e7e-138">Verwenden Sie die `Job`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0e7e-138">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="d0e7e-139">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="d0e7e-139">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
