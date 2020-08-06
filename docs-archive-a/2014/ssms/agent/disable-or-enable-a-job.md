---
title: Deaktivieren oder Aktivieren eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- stopping jobs
- disabling jobs
- SQL Server Agent jobs, disabling
- jobs [SQL Server Agent], disabling
ms.assetid: 5041261f-0c32-4d4a-8bee-59a6c16200dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42fe7cbeed1e2ff3f93b1afef52b165a7d660ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608223"
---
# <a name="disable-or-enable-a-job"></a><span data-ttu-id="76e72-102">Deaktivieren oder Aktivieren eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="76e72-102">Disable or Enable a Job</span></span>
  <span data-ttu-id="76e72-103">In diesem Thema wird beschrieben, wie Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="76e72-103">This topic describes how to disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="76e72-104">Beim Deaktivieren eines Auftrags wird dieser nicht gelöscht, und kann gegebenenfalls wieder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="76e72-104">When you disable a job, it is not deleted and can be enabled again when necessary.</span></span>  
  
 <span data-ttu-id="76e72-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="76e72-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="76e72-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="76e72-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="76e72-107">Security</span><span class="sxs-lookup"><span data-stu-id="76e72-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="76e72-108">**So aktivieren oder deaktivieren Sie einen Auftrag mit**</span><span class="sxs-lookup"><span data-stu-id="76e72-108">**To disable or enable a job, using:**</span></span>  
  
     [<span data-ttu-id="76e72-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="76e72-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="76e72-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="76e72-110">Transact-SQL</span></span>](#TSQL)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="76e72-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="76e72-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="76e72-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="76e72-112">Security</span></span>  
 <span data-ttu-id="76e72-113">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="76e72-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="76e72-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="76e72-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="76e72-115">So aktivieren oder deaktivieren Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="76e72-115">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="76e72-116">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="76e72-116">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="76e72-117">Erweitern Sie **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="76e72-117">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="76e72-118">Erweitern Sie **Aufträge**, und klicken Sie dann mit der rechten Maustaste auf den Auftrag, den Sie deaktivieren bzw. aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="76e72-118">Expand **Jobs**, and then right-click the job that you want to disable or enable.</span></span>  
  
4.  <span data-ttu-id="76e72-119">Klicken Sie auf **Deaktivieren**, um einen Auftrag zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="76e72-119">To disable a job, click **Disable**.</span></span> <span data-ttu-id="76e72-120">Klicken Sie auf **Aktivieren**, um einen Auftrag zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76e72-120">To enable a job, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="76e72-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="76e72-121">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="76e72-122">So aktivieren oder deaktivieren Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="76e72-122">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="76e72-123">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="76e72-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="76e72-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="76e72-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="76e72-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="76e72-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the name, description, and enables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="76e72-126">Weitere Informationen finden Sie unter [sp_update_job &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="76e72-126">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
