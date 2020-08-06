---
title: Löschen ein Auftragsschrittprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: stevestein
ms.author: sstein
ms.openlocfilehash: de7c64c4d7cf461eef563ae6989e043d125c6f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618996"
---
# <a name="delete-a-job-step-log"></a><span data-ttu-id="99cbc-102">Löschen eines Auftragsschrittprotokolls</span><span class="sxs-lookup"><span data-stu-id="99cbc-102">Delete a Job Step Log</span></span>
  <span data-ttu-id="99cbc-103">In diesem Thema wird beschrieben, wie Sie ein Auftragsschrittprotokoll des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents löschen.</span><span class="sxs-lookup"><span data-stu-id="99cbc-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step log.</span></span>  
  
-   <span data-ttu-id="99cbc-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="99cbc-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="99cbc-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99cbc-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="99cbc-106">Security</span><span class="sxs-lookup"><span data-stu-id="99cbc-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="99cbc-107">**So löschen Sie ein Auftragsschrittprotokoll des SQL Server-Agents mit**</span><span class="sxs-lookup"><span data-stu-id="99cbc-107">**To delete a SQL Server Agent job step log, using:**</span></span>  
  
     [<span data-ttu-id="99cbc-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99cbc-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="99cbc-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99cbc-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="99cbc-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="99cbc-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99cbc-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="99cbc-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="99cbc-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="99cbc-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="99cbc-113">Wenn Auftragsschritte gelöscht werden, werden auch die entsprechenden Ausgabeprotokolle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="99cbc-113">When job steps are deleted their output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99cbc-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="99cbc-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99cbc-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99cbc-115">Permissions</span></span>  
 <span data-ttu-id="99cbc-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="99cbc-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="99cbc-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99cbc-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="99cbc-118">So löschen Sie ein Auftragsschrittprotokoll des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="99cbc-118">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="99cbc-119">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="99cbc-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="99cbc-120">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie ändern möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="99cbc-120">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="99cbc-121">Löschen Sie im Dialogfeld **Auftragseigenschaften** den ausgewählten Auftragsschritt.</span><span class="sxs-lookup"><span data-stu-id="99cbc-121">In the **Job Properties** dialog box, delete the selected job step.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="99cbc-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99cbc-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="99cbc-123">So löschen Sie ein Auftragsschrittprotokoll des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="99cbc-123">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="99cbc-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="99cbc-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="99cbc-125">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="99cbc-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="99cbc-126">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="99cbc-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
 <span data-ttu-id="99cbc-127">Weitere Informationen finden Sie unter [sp_delete_jobsteplog &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99cbc-127">For more information, see [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="99cbc-128">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="99cbc-128">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="99cbc-129">Verwenden Sie die `DeleteJobStepLogs`-Methoden der `Job`-Klasse in einer Programmiersprache Ihrer Wahl, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99cbc-129">Use the `DeleteJobStepLogs` methods of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="99cbc-130">Weitere Informationen finden Sie unter[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="99cbc-130">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
```powershell
# Delete all job step log files that have ID values larger than 5.  
$srv = New-Object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```
