---
title: Anzeigen eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], viewing
- viewing jobs
- SQL Server Agent jobs, viewing
- displaying jobs
ms.assetid: d2241a3f-dbcf-433c-b7bc-f96bdf0eac8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 26406aaf2ba0ac4809eb7ac2c84799469d0468d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630478"
---
# <a name="view-a-job"></a><span data-ttu-id="cc453-102">View a Job</span><span class="sxs-lookup"><span data-stu-id="cc453-102">View a Job</span></span>
  <span data-ttu-id="cc453-103">In diesem Thema wird beschrieben, wie [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sie-Agent-Aufträge in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder anzeigen können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc453-103">This topic describes how to view [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="cc453-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="cc453-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cc453-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="cc453-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cc453-106">Security</span><span class="sxs-lookup"><span data-stu-id="cc453-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cc453-107">**So zeigen Sie einen Auftrag an mit**</span><span class="sxs-lookup"><span data-stu-id="cc453-107">**To view a job, using:**</span></span>  
  
     [<span data-ttu-id="cc453-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc453-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="cc453-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc453-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="cc453-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cc453-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cc453-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="cc453-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cc453-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cc453-112">Security</span></span>  
 <span data-ttu-id="cc453-113">Sie können nur die Aufträge anzeigen, die Sie besitzen, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="cc453-113">You can only view jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="cc453-114">Mitglieder dieser Rolle können alle Aufträge anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc453-114">Members of this role can view all jobs.</span></span> <span data-ttu-id="cc453-115">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="cc453-115">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="cc453-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc453-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="cc453-117">So zeigen Sie einen Auftrag an</span><span class="sxs-lookup"><span data-stu-id="cc453-117">To view a job</span></span>  
  
1.  <span data-ttu-id="cc453-118">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="cc453-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cc453-119">Erweitern Sie **SQL Server-Agent**, und klicken Sie auf **Aufträge**.</span><span class="sxs-lookup"><span data-stu-id="cc453-119">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="cc453-120">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cc453-120">Right-click a job, and then click **Properties**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="cc453-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc453-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="cc453-122">So zeigen Sie einen Auftrag an</span><span class="sxs-lookup"><span data-stu-id="cc453-122">To view a job</span></span>  
  
1.  <span data-ttu-id="cc453-123">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="cc453-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc453-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="cc453-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cc453-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc453-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all aspects of the information for the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_job  
        @job_name = N'NightlyBackups',  
        @job_aspect = N'ALL' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="cc453-126">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cc453-126">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="cc453-127">**So zeigen Sie einen Auftrag an**</span><span class="sxs-lookup"><span data-stu-id="cc453-127">**To view a job**</span></span>  
  
 <span data-ttu-id="cc453-128">Verwenden Sie die `Job`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc453-128">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="cc453-129">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc453-129">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
