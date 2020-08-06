---
title: Löschen einer Auftragskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: e96dd0461f3dace138b7822cdbaaa2fa242e2cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696369"
---
# <a name="delete-a-job-category"></a><span data-ttu-id="27326-102">Löschen einer Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="27326-102">Delete a Job Category</span></span>
  <span data-ttu-id="27326-103">In diesem Thema wird beschrieben, wie Sie eine- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Auftrags Kategorie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects löschen.</span><span class="sxs-lookup"><span data-stu-id="27326-103">This topic describes how to delete a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="27326-104">Auftragskategorien helfen Ihnen dabei, Ihre Aufträge zum einfachen Filtern und Gruppieren zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="27326-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="27326-105">Sie können z. B. alle Aufträge für die Datenbanksicherung in der Datenbankwartungskategorie organisieren.</span><span class="sxs-lookup"><span data-stu-id="27326-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span>  

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27326-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="27326-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="27326-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="27326-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="27326-108">Wenn Sie eine benutzerdefinierte Auftragskategorie löschen, werden sie von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aufgefordert, die Aufträge neu zuzuweisen, die in einer anderen Auftragskategorie zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="27326-108">When you delete a user-defined job category, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prompts you to reassign the jobs that are assigned to it to another job category.</span></span> <span data-ttu-id="27326-109">Sie können nur benutzerdefinierte Auftragskategorien löschen.</span><span class="sxs-lookup"><span data-stu-id="27326-109">You can only delete user-defined job categories.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27326-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="27326-110">Security</span></span>  
 <span data-ttu-id="27326-111">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="27326-111">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="27326-112">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27326-112">Using SQL Server Management Studio</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="27326-113">So löschen Sie eine Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="27326-113">To delete a job category</span></span>  
  
1.  <span data-ttu-id="27326-114">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie eine Auftragskategorie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="27326-114">In **Object Explorer**, click the plus sign to expand the server where you want to delete a job category.</span></span>  
  
2.  <span data-ttu-id="27326-115">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="27326-115">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="27326-116">Klicken Sie mit der rechten Maustaste auf den Ordner **Aufträge** , und wählen Sie **Auftragskategorien verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="27326-116">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="27326-117">Wählen Sie im Dialogfeld **Auftrags Kategorien verwalten**_server_name_ die zu löschende Auftrags Kategorie aus.</span><span class="sxs-lookup"><span data-stu-id="27326-117">In the **Manage Job Categories**_server_name_ dialog box, select the job category to delete.</span></span>  
  
5.  <span data-ttu-id="27326-118">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="27326-118">Click **Delete**.</span></span>  
  
6.  <span data-ttu-id="27326-119">Klicken Sie im Dialogfeld **Auftragskategorien** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="27326-119">In the **Job Categories** dialog box, click **Yes**.</span></span>  
  
7.  <span data-ttu-id="27326-120">Schließen Sie das Dialogfeld **Auftrags Kategorien verwalten**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="27326-120">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="27326-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27326-121">Using Transact-SQL</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="27326-122">So löschen Sie eine Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="27326-122">To delete a job category</span></span>  
  
1.  <span data-ttu-id="27326-123">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="27326-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="27326-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="27326-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="27326-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="27326-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
 <span data-ttu-id="27326-126">Weitere Informationen finden Sie unter [sp_delete_category &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27326-126">For more information, see [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span></span>  

  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="27326-127">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="27326-127">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-a-job-category"></a><span data-ttu-id="27326-128">So löschen Sie eine Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="27326-128">To delete a job category</span></span>
  
 <span data-ttu-id="27326-129">Rufen Sie die `JobCategory`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27326-129">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
