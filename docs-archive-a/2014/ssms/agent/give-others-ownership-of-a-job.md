---
title: Ändern des Besitzes eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], owners
- owners [SQL Server], jobs
- SQL Server Agent jobs, owners
ms.assetid: 2ded5e9c-4251-4fb1-a047-99f13d150b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2cf03fdc9031ce9761125d95619438837f2959bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608210"
---
# <a name="give-others-ownership-of-a-job"></a><span data-ttu-id="3605a-102">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="3605a-102">Give Others Ownership of a Job</span></span>
  <span data-ttu-id="3605a-103">In diesem Thema wird beschrieben, wie der Besitz von- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträgen einem anderen Benutzer neu zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3605a-103">This topic describes how to reassign ownership of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>  
  
-   <span data-ttu-id="3605a-104">**Vorbereitungen:**  [Beschränkungen](#Restrictions), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="3605a-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3605a-105">**So ändern Sie den Besitz eines Auftrags mit:**</span><span class="sxs-lookup"><span data-stu-id="3605a-105">**To give others ownership of a job, using:**</span></span>  
  
     [<span data-ttu-id="3605a-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3605a-106">SQL Server Management Studio</span></span>](#SSMSProc2)  
  
     [<span data-ttu-id="3605a-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3605a-107">Transact-SQL</span></span>](#TsqlProc2)  
  
     [<span data-ttu-id="3605a-108">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="3605a-108">SQL Server Management Objects</span></span>](#SMOProc2)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3605a-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3605a-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3605a-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3605a-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3605a-111">Um einen Auftrag erstellen zu können, muss ein Benutzer Mitglied einer der festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents oder Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="3605a-111">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="3605a-112">Ein Auftrag kann nur von seinem Besitzer bzw. Mitgliedern der **sysadmin** -Rolle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3605a-112">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="3605a-113">Weitere Informationen zu den festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3605a-113">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="3605a-114">Den Besitzer eines Auftrags können Sie nur ändern, wenn Sie als Systemadministrator angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="3605a-114">You must be a system administrator to change the owner of a job.</span></span>  
  
 <span data-ttu-id="3605a-115">Wenn Sie einen Auftrag einem anderen Anmeldenamen zuweisen, ist nicht sichergestellt, dass die Berechtigungen des neuen Besitzers zum erfolgreichen Ausführen des Auftrags ausreichen.</span><span class="sxs-lookup"><span data-stu-id="3605a-115">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3605a-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3605a-116">Security</span></span>  
 <span data-ttu-id="3605a-117">Aus Sicherheitsgründen kann nur der Auftragsbesitzer bzw. ein Mitglied der **sysadmin** -Rolle die Definition des Auftrags ändern.</span><span class="sxs-lookup"><span data-stu-id="3605a-117">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="3605a-118">Nur Mitglieder der festen Serverrolle **sysadmin** können anderen Benutzern den Auftragsbesitz zuweisen. Zudem können sie unabhängig vom Auftragsbesitzer alle Aufträge ausführen.</span><span class="sxs-lookup"><span data-stu-id="3605a-118">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3605a-119">Wenn Sie den Auftragsbesitz einem Benutzer zuweisen, der kein Mitglied der festen Serverrolle **sysadmin** ist, und wenn in dem Auftrag Schritte ausgeführt werden, für die Proxykonten erforderlich sind (beispielsweise die [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketausführung), müssen Sie sicherstellen, dass der Benutzer auf dieses Proxykonto zugreifen kann. Andernfalls schlägt der Auftrag fehl.</span><span class="sxs-lookup"><span data-stu-id="3605a-119">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3605a-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3605a-120">Permissions</span></span>  
 <span data-ttu-id="3605a-121">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3605a-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProc2"></a> <span data-ttu-id="3605a-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3605a-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3605a-123">**So ändern Sie den Besitz eines Auftrags**</span><span class="sxs-lookup"><span data-stu-id="3605a-123">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="3605a-124">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="3605a-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3605a-125">Erweitern Sie zunächst den **SQL Server-Agent**, anschließend **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="3605a-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3605a-126">Wählen Sie aus der Liste **Besitzer** einen Anmeldenamen aus.</span><span class="sxs-lookup"><span data-stu-id="3605a-126">In the **Owner** list, select a login.</span></span> <span data-ttu-id="3605a-127">Den Besitzer eines Auftrags können Sie nur ändern, wenn Sie als Systemadministrator angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="3605a-127">You must be a system administrator to change the owner of a job.</span></span>  
  
     <span data-ttu-id="3605a-128">Wenn Sie einen Auftrag einem anderen Anmeldenamen zuweisen, ist nicht sichergestellt, dass die Berechtigungen des neuen Besitzers zum erfolgreichen Ausführen des Auftrags ausreichen.</span><span class="sxs-lookup"><span data-stu-id="3605a-128">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProc2"></a> <span data-ttu-id="3605a-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3605a-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="3605a-130">**So ändern Sie den Besitz eines Auftrags**</span><span class="sxs-lookup"><span data-stu-id="3605a-130">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="3605a-131">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von Database Engine (Datenbankmodul) her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="3605a-131">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3605a-132">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="3605a-132">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3605a-133">Geben Sie im Abfragefenster die folgenden Anweisungen ein, die die [sp_manage_jobs_by_login &#40;gespeicherte Transact-SQL&#41;-](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) System Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="3605a-133">In the query window, enter the following statements that use the [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure.</span></span> <span data-ttu-id="3605a-134">Im folgenden Beispiel erfolgt eine Neuzuweisung aller Aufträge von `danw` an `fran??oisa`.</span><span class="sxs-lookup"><span data-stu-id="3605a-134">The following example reassigns all jobs from `danw` to `fran??oisa`.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'fran??oisa' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProc2"></a><span data-ttu-id="3605a-135">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="3605a-135">Using SQL Server Management Objects</span></span>  

### <a name="to-give-others-ownership-of-a-job"></a><span data-ttu-id="3605a-136">So ändern Sie den Besitz eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="3605a-136">To give others ownership of a job</span></span>
  
1.  <span data-ttu-id="3605a-137">Rufen Sie die `Job`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3605a-137">Call the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="3605a-138">Beispielcode hierzu finden Sie unter [Planen von automatischen, administrativen Tasks im SQL Server-Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="3605a-138">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3605a-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3605a-139">See Also</span></span>  
 <span data-ttu-id="3605a-140">[Implementieren von Aufträgen](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="3605a-140">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="3605a-141">Erstellen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="3605a-141">Create Jobs</span></span>](create-jobs.md)  
