---
title: Ändern von Schritten von einem Masterauftrag für den SQL Server-Agent |Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 8f1a0ee6-49ff-4080-94ca-d661daeff2a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a9defc17b5b39ab8a322b6da29960eb9968c2e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622385"
---
# <a name="change-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="3f108-102">Change Steps of a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="3f108-102">Change Steps of a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="3f108-103">In diesem Thema wird beschrieben, wie Sie die Schritte in einem Masterauftrag für den SQL Server-Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="3f108-103">This topic describes how to make changes to the steps of a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3f108-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3f108-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3f108-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3f108-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3f108-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3f108-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3f108-107">Security</span><span class="sxs-lookup"><span data-stu-id="3f108-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3f108-108">**Ändern der Schritte in einem Masterauftrag für den SQL Server-Agent mit:**</span><span class="sxs-lookup"><span data-stu-id="3f108-108">**To make changes to the steps of a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="3f108-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f108-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3f108-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f108-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3f108-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3f108-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3f108-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3f108-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3f108-113">Ein Masterauftrag für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent kann nicht gleichzeitig lokale Server und Remoteserver als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="3f108-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3f108-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3f108-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3f108-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3f108-115">Permissions</span></span>  
 <span data-ttu-id="3f108-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3f108-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="3f108-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3f108-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3f108-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f108-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="3f108-119">So ändern Sie die Schritte in einem Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="3f108-119">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="3f108-120">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Auftrag mit den zu ändernden Schritten enthält.</span><span class="sxs-lookup"><span data-stu-id="3f108-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify steps.</span></span>  
  
2.  <span data-ttu-id="3f108-121">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3f108-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3f108-122">Klicken Sie auf das Pluszeichen, um den Ordner **Aufträge** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3f108-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="3f108-123">Klicken Sie mit der rechten Maustaste auf den Auftrag, dessen Schritte Sie ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="3f108-123">Right-click the job where you want to modify steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="3f108-124">Wählen Sie im Dialogfeld **Auftrags Eigenschaften-**_job_name_ unter **Seite auswählen**die Option **Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="3f108-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="3f108-125">Klicken Sie auf **Bearbeiten** , um das Dialogfeld **Auftrags Schritt-Eigenschaften-**_job_step_name_ zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3f108-125">Click **Edit** to open the **Job Step Properties -**_job_step_name_ dialog box.</span></span> <span data-ttu-id="3f108-126">Weitere Informationen zu den verfügbaren Optionen in diesem Dialogfeld finden Sie unter [Auftrags Schritt-Eigenschaften: neuer Auftrags Schritt &#40;Seite "Allgemein"&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) und [Auftrags Schritt-Eigenschaften: neuer Auftrags Schritt &#40;erweiterte Seite&#41;](job-step-properties-new-job-step-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="3f108-126">For more information on the available options in this dialog box, see [Job Step Properties: New Job Step &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) and [Job Step Properties: New Job Step &#40;Advanced Page&#41;](job-step-properties-new-job-step-advanced-page.md).</span></span>  
  
7.  <span data-ttu-id="3f108-127">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f108-127">When finished, click **OK**.</span></span>  
  
8.  <span data-ttu-id="3f108-128">Klicken Sie im Dialogfeld **Auftrags Eigenschaften-**_job_name_ auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f108-128">In the **Job Properties -**_job_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3f108-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f108-129">Using Transact-SQL</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="3f108-130">So ändern Sie die Schritte in einem Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="3f108-130">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="3f108-131">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="3f108-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3f108-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="3f108-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3f108-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3f108-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the number of retry attempts for the first step of the Weekly Sales Data Backup job.   
    -- After running this example, the number of retry attempts is 10   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1,  
        @retry_attempts = 10 ;  
    GO  
    ```  
  
 <span data-ttu-id="3f108-134">Weitere Informationen finden Sie unter [sp_update_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f108-134">For more information, see [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span></span>  
  
  
