---
title: Ändern der Ziel Server, die einem SQL Server-Agent Master Auftrag zugeordnet sind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 176e73b6-08aa-48ec-b349-e84b431e65cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6b7b5ab114366cdafe40b7a70f523fef43eb11d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622369"
---
# <a name="modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="ea2b2-102">Ändern der einem Masterauftrag für den SQL Server-Agent zugewiesenen Zielserver</span><span class="sxs-lookup"><span data-stu-id="ea2b2-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="ea2b2-103">In diesem Thema wird beschrieben, wie Sie die Zielserver, die einem Masterauftrag für den SQL Server-Agent zugewiesen sind, mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-103">This topic describes how to modify the target server(s) associated with a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ea2b2-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ea2b2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ea2b2-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ea2b2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ea2b2-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ea2b2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ea2b2-107">Security</span><span class="sxs-lookup"><span data-stu-id="ea2b2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ea2b2-108">**Ändern der Zielserver, die einem Masterauftrag für den SQL Server-Agent zugewiesen sind, mit:**</span><span class="sxs-lookup"><span data-stu-id="ea2b2-108">**To modify the target server(s) associated with a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="ea2b2-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea2b2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ea2b2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ea2b2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ea2b2-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ea2b2-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ea2b2-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ea2b2-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ea2b2-113">Ein Masterauftrag für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent kann nicht gleichzeitig lokale Server und Remoteserver als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ea2b2-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ea2b2-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ea2b2-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ea2b2-115">Permissions</span></span>  
 <span data-ttu-id="ea2b2-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ea2b2-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="ea2b2-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ea2b2-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ea2b2-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea2b2-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="ea2b2-119">So ändern Sie die Zielserver, die einem Masterauftrag für den SQL Server-Agent zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="ea2b2-119">To modify the target server(s) associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="ea2b2-120">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Auftrag mit dem zu ändernden Zielserver enthält.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify the target server.</span></span>  
  
2.  <span data-ttu-id="ea2b2-121">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ea2b2-122">Klicken Sie auf das Pluszeichen, um den Ordner **Aufträge** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="ea2b2-123">Klicken Sie mit der rechten Maustaste auf den Auftrag, dessen Zielserver Sie ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-123">Right-click the job where you want to modify the target server and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ea2b2-124">Wählen Sie im Dialogfeld **Auftrags Eigenschaften-**_job_name_ unter **Seite auswählen**die Option **Ziele**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Targets**.</span></span> <span data-ttu-id="ea2b2-125">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Ziele"&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="ea2b2-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
6.  <span data-ttu-id="ea2b2-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ea2b2-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ea2b2-127">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-target-server-currently-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="ea2b2-128">So löschen Sie einen Zielserver, der derzeit einem Masterauftrag für den SQL Server-Agent zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="ea2b2-128">To delete a target server currently associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="ea2b2-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ea2b2-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ea2b2-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes the server SEATTLE2 from processing the Weekly Sales Backupsjob   
    -- assumes that the Weekly Sales Backups job exists  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="ea2b2-132">Weitere Informationen finden Sie unter [sp_delete_jobserver &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea2b2-132">For more information, see [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span></span>  
  
#### <a name="to-associate-a-target-server-with-the-current-sql-server-agent-master-job"></a><span data-ttu-id="ea2b2-133">So weisen Sie dem aktuellen Masterauftrag für den SQL Server-Agent einen Zielserver zu</span><span class="sxs-lookup"><span data-stu-id="ea2b2-133">To associate a target server with the current SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="ea2b2-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ea2b2-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ea2b2-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2   
    -- assumes that the Weekly Sales Backups job already exists and that   
    -- SEATTLE2 is registered as a target server for the current instance  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="ea2b2-137">Weitere Informationen finden Sie unter [sp_add_jobserver &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea2b2-137">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
  
