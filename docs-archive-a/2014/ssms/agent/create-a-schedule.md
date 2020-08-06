---
title: Erstellen eines Zeitplans | Microsoft-Dokumentation
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
- schedules [SQL Server], jobs
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac71a61163dceb06697b61ef24fce2117d57cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621321"
---
# <a name="create-a-schedule"></a><span data-ttu-id="cd210-102">Create a Schedule</span><span class="sxs-lookup"><span data-stu-id="cd210-102">Create a Schedule</span></span>
  <span data-ttu-id="cd210-103">Sie können einen Zeitplan für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Aufträge in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder SQL Server Management Objects erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd210-103">You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="cd210-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="cd210-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cd210-105">Security</span><span class="sxs-lookup"><span data-stu-id="cd210-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cd210-106">**So erstellen Sie einen Zeitplan mit**</span><span class="sxs-lookup"><span data-stu-id="cd210-106">**To create a schedule, using:**</span></span>  
  
     [<span data-ttu-id="cd210-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd210-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="cd210-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd210-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="cd210-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cd210-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cd210-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="cd210-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cd210-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd210-111">Security</span></span>  
 <span data-ttu-id="cd210-112">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="cd210-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="cd210-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd210-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="cd210-114">So erstellen Sie einen Zeitplan</span><span class="sxs-lookup"><span data-stu-id="cd210-114">To create a schedule</span></span>  
  
1.  <span data-ttu-id="cd210-115">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="cd210-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cd210-116">Erweitern Sie **SQL Server-Agent**, klicken Sie mit der rechten Maustaste auf **Aufträge**, und wählen Sie dann **Zeitpläne verwalten**.</span><span class="sxs-lookup"><span data-stu-id="cd210-116">Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.</span></span>  
  
3.  <span data-ttu-id="cd210-117">Klicken Sie im Dialogfeld **Zeitpläne verwalten** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="cd210-117">In the **Manage Schedules** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="cd210-118">Geben Sie in das Feld **Name** einen Namen für den neuen Zeitplan ein.</span><span class="sxs-lookup"><span data-stu-id="cd210-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="cd210-119">Wenn der Zeitplan nicht unmittelbar nach seiner Erstellung wirksam werden soll, deaktivieren Sie das Kontrollkästchen **Aktiviert** .</span><span class="sxs-lookup"><span data-stu-id="cd210-119">If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="cd210-120">Wählen Sie für **Zeitplantyp**eine der folgenden Möglichkeiten aus:</span><span class="sxs-lookup"><span data-stu-id="cd210-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="cd210-121">Um den Auftrag zu starten, wenn die CPUs eine Leerlaufbedingung erfüllen, klicken Sie auf **Starten, wenn sich die CPUs im Leerlauf befinden**.</span><span class="sxs-lookup"><span data-stu-id="cd210-121">To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.</span></span>  
  
    -   <span data-ttu-id="cd210-122">Klicken Sie auf **Wiederholt**, wenn ein Zeitplan wiederholt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd210-122">If you want a schedule to run repeatedly, click **Recurring**.</span></span> <span data-ttu-id="cd210-123">Um den wiederholten Zeitplan festzulegen, vervollständigen Sie im Dialogfeld die Gruppen **Häufigkeit**, **Häufigkeit pro Tag**und **Dauer** .</span><span class="sxs-lookup"><span data-stu-id="cd210-123">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="cd210-124">Wenn der Zeitplan nur einmal ausgeführt werden soll, klicken Sie auf **Einmal**.</span><span class="sxs-lookup"><span data-stu-id="cd210-124">If you want the schedule to run only one time, click **One time**.</span></span> <span data-ttu-id="cd210-125">Um den **einmaligen** Zeitplan festzulegen, vervollständigen Sie im Dialogfeld die Gruppe **Einmalig** .</span><span class="sxs-lookup"><span data-stu-id="cd210-125">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="cd210-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd210-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="cd210-127">So erstellen Sie einen Zeitplan</span><span class="sxs-lookup"><span data-stu-id="cd210-127">To create a schedule</span></span>  
  
1.  <span data-ttu-id="cd210-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="cd210-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cd210-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="cd210-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cd210-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cd210-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
 <span data-ttu-id="cd210-131">Weitere Informationen finden Sie unter [sp_add_schedule &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd210-131">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="cd210-132">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cd210-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="cd210-133">**So erstellen Sie einen Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="cd210-133">**To create a schedule**</span></span>  
  
 <span data-ttu-id="cd210-134">Verwenden Sie die `JobSchedule`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd210-134">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="cd210-135">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd210-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
