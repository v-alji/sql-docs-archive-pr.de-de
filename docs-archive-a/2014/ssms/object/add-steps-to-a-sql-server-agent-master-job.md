---
title: Hinzufügen von Schritten zu einem Masterauftrag für den SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9cc1e8ab-7ddc-427b-859e-203aa7e24642
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccff8d6f4faa7bef549b5a179a957ce798250dbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607525"
---
# <a name="add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="e6b9b-102">Add Steps to a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="e6b9b-102">Add Steps to a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="e6b9b-103">In diesem Thema wird beschrieben, wie Sie einem Masterauftrag für den SQL Server-Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]Schritte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-103">This topic describes how to add steps to a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e6b9b-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e6b9b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e6b9b-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e6b9b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e6b9b-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e6b9b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e6b9b-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e6b9b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e6b9b-108">**Hinzufügen von Schritten zu einem Masterauftrag für den SQL Server-Agent mit:**</span><span class="sxs-lookup"><span data-stu-id="e6b9b-108">**To add steps to a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="e6b9b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6b9b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e6b9b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6b9b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e6b9b-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e6b9b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e6b9b-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e6b9b-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e6b9b-113">Ein Masterauftrag für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent kann nicht gleichzeitig lokale Server und Remoteserver als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e6b9b-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e6b9b-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e6b9b-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e6b9b-115">Permissions</span></span>  
 <span data-ttu-id="e6b9b-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e6b9b-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="e6b9b-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](../agent/implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e6b9b-117">For detailed information, see [Implement SQL Server Agent Security](../agent/implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e6b9b-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6b9b-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="e6b9b-119">So fügen Sie einem Masterauftrag für den SQL Server-Agent Schritte hinzu</span><span class="sxs-lookup"><span data-stu-id="e6b9b-119">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="e6b9b-120">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Auftrag enthält, dem Sie Schritte hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-120">In **Object Explorer,** click the plus sign to expand the server that contains the job to which you want to add steps.</span></span>  
  
2.  <span data-ttu-id="e6b9b-121">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e6b9b-122">Klicken Sie auf das Pluszeichen, um den Ordner **Aufträge** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="e6b9b-123">Klicken Sie mit der rechten Maustaste auf den Auftrag, dem Sie Schritte hinzufügen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-123">Right-click the job to which you want to add steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e6b9b-124">Klicken Sie im Dialogfeld **Auftragseigenschaften** > _Auftragsname_ unter **Seite auswählen** auf die Option **Schritte**.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span> <span data-ttu-id="e6b9b-125">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Schritte"&#41;](../agent/job-properties-new-job-steps-page.md).</span><span class="sxs-lookup"><span data-stu-id="e6b9b-125">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](../agent/job-properties-new-job-steps-page.md).</span></span>  

6.  <span data-ttu-id="e6b9b-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e6b9b-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6b9b-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="e6b9b-128">So fügen Sie einem Masterauftrag für den SQL Server-Agent Schritte hinzu</span><span class="sxs-lookup"><span data-stu-id="e6b9b-128">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="e6b9b-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6b9b-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e6b9b-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e6b9b-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a job step that changes database access to read-only for the Sales database.   
    -- specifies 5 retry attempts, with each retry to occur after a 5 minute wait.   
    -- assumes that the Weekly Sales Data Backup job already exists  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="e6b9b-132">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6b9b-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
  
