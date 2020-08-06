---
title: Erstellen eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: b35af2b6-6594-40d1-9861-4d5dd906048c
author: stevestein
ms.author: sstein
ms.openlocfilehash: de74f032924fbb0b6643bd8f3d482481ffb1f983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608222"
---
# <a name="create-a-job"></a><span data-ttu-id="b686c-102">Erstellen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="b686c-102">Create a Job</span></span>
  <span data-ttu-id="b686c-103">In diesem Thema wird beschrieben, wie Sie eine SQL Server-Agent-Auftragskategorie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects (SMO) erstellen können.</span><span class="sxs-lookup"><span data-stu-id="b686c-103">This topic describes how to create a SQL Server Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="b686c-104">Informationen zum Hinzufügen von Auftragsschritten, Zeitplänen, Warnungen und Benachrichtigungen, die an Benutzer gesendet werden können, finden Sie in den Links im Abschnitt "Siehe auch".</span><span class="sxs-lookup"><span data-stu-id="b686c-104">To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to topics in the See Also section.</span></span>  
  
-   <span data-ttu-id="b686c-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b686c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b686c-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b686c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b686c-107">Security</span><span class="sxs-lookup"><span data-stu-id="b686c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b686c-108">**So erstellen Sie einen Auftrag Sicht mit**</span><span class="sxs-lookup"><span data-stu-id="b686c-108">**To create a job, using:**</span></span>  
  
     <span data-ttu-id="b686c-109">[SQL Server Management Studio](#SSMSProcedure),</span><span class="sxs-lookup"><span data-stu-id="b686c-109">[SQL Server Management Studio](#SSMSProcedure),</span></span>  
  
     [<span data-ttu-id="b686c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b686c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b686c-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="b686c-111">SQL Server Management Objects</span></span>](#SMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b686c-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b686c-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b686c-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b686c-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b686c-114">Um einen Auftrag erstellen zu können, muss ein Benutzer Mitglied einer der festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents oder Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="b686c-114">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="b686c-115">Ein Auftrag kann nur von seinem Besitzer bzw. Mitgliedern der **sysadmin** -Rolle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b686c-115">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="b686c-116">Weitere Informationen zu den festen Datenbankrollen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b686c-116">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
-   <span data-ttu-id="b686c-117">Wenn Sie einen Auftrag einem anderen Anmeldenamen zuweisen, ist nicht sichergestellt, dass die Berechtigungen des neuen Besitzers zum erfolgreichen Ausführen des Auftrags ausreichen.</span><span class="sxs-lookup"><span data-stu-id="b686c-117">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
-   <span data-ttu-id="b686c-118">Lokale Aufträge werden vom lokalen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="b686c-118">Local jobs are cached by the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="b686c-119">Aus diesem Grund erzwingen alle Änderungen implizit das erneute Zwischenspeichern des Auftrags durch den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent.</span><span class="sxs-lookup"><span data-stu-id="b686c-119">Therefore, any modifications implicitly force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to re-cache the job.</span></span> <span data-ttu-id="b686c-120">Da der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent den Auftrag erst zwischenspeichert, wenn **sp_add_jobserver** aufgerufen wird, ist es effizienter, **sp_add_jobserver** zuletzt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b686c-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not cache the job until **sp_add_jobserver** is called, it is more efficient to call **sp_add_jobserver** last.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b686c-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b686c-121">Security</span></span>  
  
-   <span data-ttu-id="b686c-122">Den Besitzer eines Auftrags können Sie nur ändern, wenn Sie als Systemadministrator angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="b686c-122">You must be a system administrator to change the owner of a job.</span></span>  
  
-   <span data-ttu-id="b686c-123">Aus Sicherheitsgründen kann nur der Auftragsbesitzer bzw. ein Mitglied der **sysadmin** -Rolle die Definition des Auftrags ändern.</span><span class="sxs-lookup"><span data-stu-id="b686c-123">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="b686c-124">Nur Mitglieder der festen Serverrolle **sysadmin** können anderen Benutzern den Auftragsbesitz zuweisen. Zudem können sie unabhängig vom Auftragsbesitzer alle Aufträge ausführen.</span><span class="sxs-lookup"><span data-stu-id="b686c-124">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b686c-125">Wenn Sie den Auftragsbesitz einem Benutzer zuweisen, der kein Mitglied der festen Serverrolle **sysadmin** ist, und wenn in dem Auftrag Schritte ausgeführt werden, für die Proxykonten erforderlich sind (beispielsweise die [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketausführung), müssen Sie sicherstellen, dass der Benutzer auf dieses Proxykonto zugreifen kann. Andernfalls schlägt der Auftrag fehl.</span><span class="sxs-lookup"><span data-stu-id="b686c-125">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b686c-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b686c-126">Permissions</span></span>  
 <span data-ttu-id="b686c-127">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="b686c-127">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b686c-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b686c-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="b686c-129">So erstellen Sie einen Auftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="b686c-129">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="b686c-130">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie den SQL Server-Agent-Auftrag erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b686c-130">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="b686c-131">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b686c-131">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b686c-132">Klicken Sie mit der rechten Maustaste auf den Ordner **Aufträge**, und wählen Sie dann **Neuer Auftrag**aus.</span><span class="sxs-lookup"><span data-stu-id="b686c-132">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="b686c-133">Ändern Sie im Dialogfeld **Neuer Auftrag** auf der Seite **Allgemein** die allgemeinen Eigenschaften des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="b686c-133">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="b686c-134">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften und neue Aufträge &#40;Seite "Allgemein"&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="b686c-134">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="b686c-135">Organisieren Sie die Auftragsschritte auf der Seite **Schritte** .</span><span class="sxs-lookup"><span data-stu-id="b686c-135">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="b686c-136">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Schritte"&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="b686c-136">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="b686c-137">Organisieren Sie auf der Seite **Zeitpläne** Zeitpläne für den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="b686c-137">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="b686c-138">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Zeitpläne"&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="b686c-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="b686c-139">Organisieren Sie auf der Seite **Warnungen** die Warnungen für den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="b686c-139">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="b686c-140">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Warnungen"&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="b686c-140">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="b686c-141">Legen Sie auf der Seite **Benachrichtigungen** die Aktionen für den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent fest, die bei Abschluss des Auftrags auszuführen sind.</span><span class="sxs-lookup"><span data-stu-id="b686c-141">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="b686c-142">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Benachrichtigungen"&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="b686c-142">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="b686c-143">Verwalten Sie auf der Seite **Ziele** die Zielserver für den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="b686c-143">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="b686c-144">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Ziele"&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="b686c-144">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="b686c-145">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b686c-145">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b686c-146">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b686c-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="b686c-147">So erstellen Sie einen Auftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="b686c-147">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="b686c-148">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="b686c-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b686c-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b686c-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b686c-150">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b686c-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backup';  
    GO  
    ```  
  
 <span data-ttu-id="b686c-151">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="b686c-151">For more information, see:</span></span>  
  
-   [<span data-ttu-id="b686c-152">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b686c-152">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="b686c-153">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b686c-153">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="b686c-154">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b686c-154">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="b686c-155">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b686c-155">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="b686c-156">sp_add_jobserver &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="b686c-156">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProcedure"></a><span data-ttu-id="b686c-157">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="b686c-157">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="b686c-158">**So erstellen Sie einen Auftrag für den SQL Server-Agent**</span><span class="sxs-lookup"><span data-stu-id="b686c-158">**To create a SQL Server Agent job**</span></span>  
  
 <span data-ttu-id="b686c-159">Rufen Sie die `Create`-Methode der `Job`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b686c-159">Call the `Create` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="b686c-160">Beispielcode hierzu finden Sie unter [Planen von automatischen, administrativen Tasks im SQL Server-Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="b686c-160">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
##  <a name="SSMSProc2"></a>  
