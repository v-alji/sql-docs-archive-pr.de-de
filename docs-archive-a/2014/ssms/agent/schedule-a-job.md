---
title: Planen eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
ms.assetid: f626390a-a3df-4970-b7a7-a0529e4a109c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1077766d6853ed7c029b8eefa76515c89ad861fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699176"
---
# <a name="schedule-a-job"></a><span data-ttu-id="df84d-102">Schedule a Job</span><span class="sxs-lookup"><span data-stu-id="df84d-102">Schedule a Job</span></span>
  <span data-ttu-id="df84d-103">In diesem Thema wird beschrieben, wie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag geplant wird.</span><span class="sxs-lookup"><span data-stu-id="df84d-103">This topic describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
-   <span data-ttu-id="df84d-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="df84d-104">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="df84d-105">Security</span><span class="sxs-lookup"><span data-stu-id="df84d-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="df84d-106">**So planen Sie einen Auftrag mit**</span><span class="sxs-lookup"><span data-stu-id="df84d-106">**To schedule a job, using:**</span></span>  
  
     [<span data-ttu-id="df84d-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df84d-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="df84d-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df84d-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="df84d-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="df84d-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="df84d-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="df84d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="df84d-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="df84d-111">Security</span></span>  
 <span data-ttu-id="df84d-112">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="df84d-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="df84d-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df84d-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-and-attach-a-schedule-to-a-job"></a><span data-ttu-id="df84d-114">So erstellen Sie einen Zeitplan und weisen ihn einem Auftrag zu</span><span class="sxs-lookup"><span data-stu-id="df84d-114">To create and attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="df84d-115">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="df84d-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="df84d-116">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den zu planenden Auftrag, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="df84d-116">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="df84d-117">Wählen Sie die Seite **Zeitpläne** aus, und klicken Sie dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="df84d-117">Select the **Schedules** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="df84d-118">Geben Sie in das Feld **Name** einen Namen für den neuen Zeitplan ein.</span><span class="sxs-lookup"><span data-stu-id="df84d-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="df84d-119">Deaktivieren Sie das Kontrollkästchen **Aktiviert** , wenn der Zeitplan nicht unmittelbar nach seiner Erstellung wirksam werden soll.</span><span class="sxs-lookup"><span data-stu-id="df84d-119">Clear the **Enabled** check box if you do not want the schedule to take effect immediately following its creation.</span></span>  
  
6.  <span data-ttu-id="df84d-120">Wählen Sie für **Zeitplantyp**eine der folgenden Möglichkeiten aus:</span><span class="sxs-lookup"><span data-stu-id="df84d-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="df84d-121">Klicken Sie auf **Automatisch starten, wenn der SQL Server-Agent startet** , um den Auftrag zu starten, wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="df84d-121">Click **Start automatically when SQL Server Agent starts** to start the job when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is started.</span></span>  
  
    -   <span data-ttu-id="df84d-122">Klicken Sie auf **Starten, wenn sich die CPUs im Leerlauf befinden** , um den Auftrag zu starten, wenn die CPUs eine Leerlaufbedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="df84d-122">Click **Start whenever the CPUs become idle** to start the job when the CPUs reach an idle condition.</span></span>  
  
    -   <span data-ttu-id="df84d-123">Klicken Sie auf **Wiederholt** , wenn ein Zeitplan wiederholt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="df84d-123">Click **Recurring** if you want a schedule to run repeatedly.</span></span> <span data-ttu-id="df84d-124">Um den wiederholten Zeitplan festzulegen, vervollständigen Sie im Dialogfeld die Gruppen **Häufigkeit**, **Häufigkeit pro Tag**und **Dauer** .</span><span class="sxs-lookup"><span data-stu-id="df84d-124">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="df84d-125">Klicken Sie auf **Einmal** , wenn der Zeitplan nur einmal ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="df84d-125">Click **One time** if you want the schedule to run only once.</span></span> <span data-ttu-id="df84d-126">Um den **Einmal** -Zeitplan festzulegen, vervollständigen Sie im Dialogfeld die Gruppe **Einmalig** .</span><span class="sxs-lookup"><span data-stu-id="df84d-126">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog.</span></span>  
  
#### <a name="to-attach-a-schedule-to-a-job"></a><span data-ttu-id="df84d-127">So weisen Sie einen Zeitplan einem Auftrag zu</span><span class="sxs-lookup"><span data-stu-id="df84d-127">To attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="df84d-128">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="df84d-128">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="df84d-129">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den zu planenden Auftrag, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="df84d-129">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="df84d-130">Wählen Sie die Seite **Zeitpläne** aus, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="df84d-130">Select the **Schedules** page, and then click **Pick**.</span></span>  
  
4.  <span data-ttu-id="df84d-131">Wählen Sie den Zeitplan aus, den Sie zuweisen möchten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="df84d-131">Select the schedule that you want to attach, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="df84d-132">Doppelklicken Sie im Dialogfeld **Auftragseigenschaften** auf den zugewiesenen Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="df84d-132">In the **Job Properties** dialog box, double-click the attached schedule.</span></span>  
  
6.  <span data-ttu-id="df84d-133">Überprüfen Sie, ob das **Startdatum** ordnungsgemäß festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="df84d-133">Verify that **Start date** is set correctly.</span></span> <span data-ttu-id="df84d-134">Falls nicht, legen Sie das Datum fest, an dem der Zeitplan starten soll, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="df84d-134">If it is not, set the date when you want for the schedule to start, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="df84d-135">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="df84d-135">In the **Job Properties** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="df84d-136">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df84d-136">Using Transact-SQL</span></span>  
  
#### <a name="to-schedule-a-job"></a><span data-ttu-id="df84d-137">So planen Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="df84d-137">To schedule a job</span></span>  
  
1.  <span data-ttu-id="df84d-138">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="df84d-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="df84d-139">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="df84d-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="df84d-140">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="df84d-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    -- creates a schedule named NightlyJobs.   
    -- Jobs that use this schedule execute every day when the time on the server is 01:00.   
    EXEC sp_add_schedule  
        @schedule_name = N'NightlyJobs' ,  
        @freq_type = 4,  
        @freq_interval = 1,  
        @active_start_time = 010000 ;  
    GO  
    -- attaches the schedule to the job BackupDatabase  
    EXEC sp_attach_schedule  
       @job_name = N'BackupDatabase',  
       @schedule_name = N'NightlyJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="df84d-141">Weitere Informationen finden Sie unter [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) und [sp_attach_schedule &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="df84d-141">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) and [sp_attach_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="df84d-142">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="df84d-142">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="df84d-143">Verwenden Sie die `JobSchedule`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df84d-143">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="df84d-144">Weitere Informationen finden Sie unter[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="df84d-144">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
