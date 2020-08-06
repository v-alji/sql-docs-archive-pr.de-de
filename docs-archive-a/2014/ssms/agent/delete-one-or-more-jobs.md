---
title: Löschen eines oder mehrerer Aufträge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 436625f9ad629a6b0e574aa046059f4e7e9c2bf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609014"
---
# <a name="delete-one-or-more-jobs"></a><span data-ttu-id="0174c-102">Löschen eines oder mehrerer Aufträge</span><span class="sxs-lookup"><span data-stu-id="0174c-102">Delete One or More Jobs</span></span>
  <span data-ttu-id="0174c-103">In diesem Thema wird beschrieben, wie- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträge in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0174c-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0174c-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0174c-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0174c-105">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0174c-105">Security</span></span>  
 <span data-ttu-id="0174c-106">Sie können nur Aufträge löschen, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0174c-106">Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.</span></span>  
  
 
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="0174c-107">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0174c-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="0174c-108">So löschen Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="0174c-108">To delete a job</span></span>  
  
1.  <span data-ttu-id="0174c-109">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="0174c-109">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0174c-110">Erweitern Sie **SQL Server-Agent**, und erweitern Sie **Aufträge**. Klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0174c-110">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="0174c-111">Bestätigen Sie im Dialogfeld **Objekt löschen** , dass der Auftrag tatsächlich gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0174c-111">In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.</span></span>  
  
4.  <span data-ttu-id="0174c-112">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0174c-112">Click **OK**.</span></span>  
  
#### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="0174c-113">So löschen Sie mehrere Aufträge</span><span class="sxs-lookup"><span data-stu-id="0174c-113">To delete multiple jobs</span></span>  
  
1.  <span data-ttu-id="0174c-114">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="0174c-114">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0174c-115">Erweitern Sie **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="0174c-115">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="0174c-116">Klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor**, und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0174c-116">Right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="0174c-117">Wählen Sie im Auftragsaktivitätsmonitor die Aufträge aus, die Sie löschen möchten. Klicken Sie mit der rechten Maustaste auf die Auswahl, und klicken Sie auf **Aufträge löschen**.</span><span class="sxs-lookup"><span data-stu-id="0174c-117">In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="0174c-118">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0174c-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="0174c-119">So löschen Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="0174c-119">To delete a job</span></span>  
  
1.  <span data-ttu-id="0174c-120">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="0174c-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0174c-121">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="0174c-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0174c-122">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0174c-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="0174c-123">Weitere Informationen finden Sie unter [sp_delete_job &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0174c-123">For more information, see [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="0174c-124">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0174c-124">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="0174c-125">So löschen Sie mehrere Aufträge</span><span class="sxs-lookup"><span data-stu-id="0174c-125">To delete multiple jobs</span></span>
  
 <span data-ttu-id="0174c-126">Verwenden Sie die `JobCollection`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0174c-126">Use the `JobCollection` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="0174c-127">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="0174c-127">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
