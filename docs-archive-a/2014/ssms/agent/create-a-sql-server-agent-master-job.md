---
title: Erstellen eines Masterauftrags für den SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], master jobs
- jobs [SQL Server Agent], creating
- master SQL Server Agent job [SQL Server]
ms.assetid: c12ab23f-d7ee-43a5-8cd2-0a9121292bcd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a6503caec3f153878e360ee29ce09a5c099ade5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700563"
---
# <a name="create-a-sql-server-agent-master-job"></a><span data-ttu-id="a57ad-102">Erstellen eines Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="a57ad-102">Create a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="a57ad-103">In diesem Thema wird beschrieben, wie Sie einen Master- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Auftrag in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder erstellen können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a57ad-103">This topic describes how to create a master [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a57ad-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a57ad-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a57ad-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a57ad-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a57ad-106">Änderungen an Masteraufträgen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent müssen an alle beteiligten Zielserver weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a57ad-106">Changes to master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs must be propagated to all involved target servers.</span></span> <span data-ttu-id="a57ad-107">Da Zielserver einen Auftrag erst herunterladen, wenn diese Ziele angegeben werden, empfiehlt [!INCLUDE[msCoName](../../includes/msconame-md.md)] , alle Auftragsschritte und -zeitpläne für einen bestimmten Auftrag abzuschließen, bevor Sie Zielserver angeben.</span><span class="sxs-lookup"><span data-stu-id="a57ad-107">Because target servers do not initially download a job until those targets are specified, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you complete all job steps and job schedules for a particular job before you specify any target servers.</span></span> <span data-ttu-id="a57ad-108">Andernfalls müssen Sie manuell anfordern, die veränderten Aufträge erneut von den Zielservern heruntergeladen werden, und zwar entweder indem Sie die gespeicherte Prozedur **sp_post_msx_operation** ausführen oder indem Sie den Auftrag mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="a57ad-108">Otherwise, you must manual request that the target servers download the modified job again, either by executing the **sp_post_msx_operation** stored procedure or modifying the job using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a57ad-109">Weitere Informationen finden Sie unter [sp_post_msx_operation &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) oder [Ändern eines Auftrags](modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="a57ad-109">For more information, see [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) or [Modify a Job](modify-a-job.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a57ad-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a57ad-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a57ad-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a57ad-111">Permissions</span></span>  
 <span data-ttu-id="a57ad-112">Verteilte Aufträge mit Schritten, die einem Proxy zugeordnet sind, werden im Kontext des Proxykontos auf dem Zielserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a57ad-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="a57ad-113">Stellen Sie sicher, dass die folgenden Bedingungen erfüllt sind, da andernfalls einem Proxy zugeordnete Auftragsschritte nicht vom Masterserver auf den Zielserver heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="a57ad-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="a57ad-114">Der Registrierungs Unterschlüssel **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \SQL Server agent\allowprotoadedjobstomatchproxyname** (REG_DWORD) ist auf 1 (true) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a57ad-114">The registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="a57ad-115">Dieser Unterschlüssel ist standardmäßig auf 0 (false) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a57ad-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="a57ad-116">Auf dem Zielserver ist ein Proxykonto vorhanden, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a57ad-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="a57ad-117">Falls bei Auftragsschritten, die Proxykonten verwenden, beim Herunterladen vom Masterserver auf den Zielserver ein Fehler auftritt, können Sie die **error_message** -Spalte in der **sysdownloadlist** -Tabelle der **msdb** -Datenbank auf die folgenden Fehlermeldungen überprüfen:</span><span class="sxs-lookup"><span data-stu-id="a57ad-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="a57ad-118">"Für den Auftragsschritt ist ein Proxykonto erforderlich, das Proxyabgleichen ist auf dem Zielserver aber deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="a57ad-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span> <span data-ttu-id="a57ad-119">Um diesen Fehler zu beheben, legen Sie den Registrierungsunterschlüssel **AllowDownloadedJobsToMatchProxyName** auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="a57ad-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="a57ad-120">"Proxy nicht gefunden."</span><span class="sxs-lookup"><span data-stu-id="a57ad-120">"Proxy not found."</span></span> <span data-ttu-id="a57ad-121">Um diesen Fehler zu beheben, stellen Sie sicher, dass auf dem Zielserver ein Proxykonto vorhanden ist, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a57ad-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a57ad-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a57ad-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="a57ad-123">So erstellen Sie einen Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="a57ad-123">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="a57ad-124">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, auf dem Sie den SQL Server-Agent-Auftrag erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a57ad-124">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="a57ad-125">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a57ad-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a57ad-126">Klicken Sie mit der rechten Maustaste auf den Ordner **Aufträge**, und wählen Sie dann **Neuer Auftrag**aus.</span><span class="sxs-lookup"><span data-stu-id="a57ad-126">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="a57ad-127">Ändern Sie im Dialogfeld **Neuer Auftrag** auf der Seite **Allgemein** die allgemeinen Eigenschaften des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="a57ad-127">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="a57ad-128">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften und neue Aufträge &#40;Seite "Allgemein"&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="a57ad-128">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="a57ad-129">Organisieren Sie die Auftragsschritte auf der Seite **Schritte** .</span><span class="sxs-lookup"><span data-stu-id="a57ad-129">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="a57ad-130">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Schritte"&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="a57ad-130">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="a57ad-131">Organisieren Sie auf der Seite **Zeitpläne** Zeitpläne für den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a57ad-131">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="a57ad-132">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Zeitpläne"&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="a57ad-132">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="a57ad-133">Organisieren Sie auf der Seite **Warnungen** die Warnungen für den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a57ad-133">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="a57ad-134">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Warnungen"&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="a57ad-134">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="a57ad-135">Legen Sie auf der Seite **Benachrichtigungen** die Aktionen für den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent fest, die bei Abschluss des Auftrags auszuführen sind.</span><span class="sxs-lookup"><span data-stu-id="a57ad-135">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="a57ad-136">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Benachrichtigungen"&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="a57ad-136">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="a57ad-137">Verwalten Sie auf der Seite **Ziele** die Zielserver für den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a57ad-137">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="a57ad-138">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Ziele"&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="a57ad-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="a57ad-139">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a57ad-139">When finished, click **OK**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a57ad-140">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a57ad-140">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="a57ad-141">So erstellen Sie einen Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="a57ad-141">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="a57ad-142">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="a57ad-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a57ad-143">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a57ad-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a57ad-144">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a57ad-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- Adds a new job executed by the SQLServerAgent service called 'Weekly Sales Data Backup'  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    -- Adds a step (operation) to the 'Weekly Sales Data Backup' job.  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    -- Creates a schedule called RunOnce  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    -- Sets the 'RunOnce' schedule to the "Weekly Sales Data Backup' Job  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2  
    -- assumes that SEATTLE2 is registered as a target server for the current instance.  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="a57ad-145">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="a57ad-145">For more information, see:</span></span>  
  
-   [<span data-ttu-id="a57ad-146">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a57ad-146">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="a57ad-147">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a57ad-147">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="a57ad-148">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a57ad-148">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="a57ad-149">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a57ad-149">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="a57ad-150">sp_add_jobserver &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="a57ad-150">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  

  
  
