---
title: Zuweisen eines Auftrags zu einer Auftragskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], assigning
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- SQL Server Agent jobs, assigning
- assigning job to category
ms.assetid: a9ea65a2-1d73-4582-a335-63adeb450cb6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 208ff6722a9c18fd4dd0d061575f0d496af27810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622387"
---
# <a name="assign-a-job-to-a-job-category"></a><span data-ttu-id="dd7f7-102">Zuweisen eines Auftrags zu einer Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="dd7f7-102">Assign a Job to a Job Category</span></span>
  <span data-ttu-id="dd7f7-103">In diesem Thema wird beschrieben, wie- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträge Auftrags Kategorien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to job categories in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="dd7f7-104">Auftragskategorien helfen Ihnen dabei, Ihre Aufträge zum einfachen Filtern und Gruppieren zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="dd7f7-105">Sie können z. B. alle Aufträge für die Datenbanksicherung in der Datenbankwartungskategorie organisieren.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="dd7f7-106">Sie können Aufträge integrierten Auftragskategorien zuweisen, oder Sie erstellen eine benutzerdefinierte Auftragskategorie und weisen ihr dann Aufträge zu.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-106">You can assign jobs to built-in job categories, or you can create a user-defined job category and then assign jobs to that.</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dd7f7-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="dd7f7-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dd7f7-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dd7f7-108">Security</span></span>  
 <span data-ttu-id="dd7f7-109">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="dd7f7-109">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="dd7f7-110">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd7f7-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="dd7f7-111">So weisen Sie einen Auftrag einer Auftragskategorie zu</span><span class="sxs-lookup"><span data-stu-id="dd7f7-111">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="dd7f7-112">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie einer Auftragskategorie einen Auftrag hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-112">In **Object Explorer**, click the plus sign to expand the server where you want to assign a job to a job category.</span></span>  
  
2.  <span data-ttu-id="dd7f7-113">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-113">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="dd7f7-114">Klicken Sie auf das Pluszeichen, um den Ordner **Aufträge** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-114">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="dd7f7-115">Klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie bearbeiten möchten, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-115">Right-click the job you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="dd7f7-116">Wählen Sie im Dialogfeld **Auftrags Eigenschaften-**_job_name_ in der Liste **Kategorie** die Auftrags Kategorie aus, die Sie dem Auftrag zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-116">In the **Job Properties -**_job_name_ dialog box, in the **Category** list, select the job category you want to assign to the job.</span></span>  
  
6.  <span data-ttu-id="dd7f7-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-117">Click **OK**.</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="dd7f7-118">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd7f7-118">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="dd7f7-119">So weisen Sie einen Auftrag einer Auftragskategorie zu</span><span class="sxs-lookup"><span data-stu-id="dd7f7-119">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="dd7f7-120">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd7f7-121">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dd7f7-122">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="dd7f7-123">Weitere Informationen finden Sie unter [sp_update_job &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dd7f7-123">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="dd7f7-124">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="dd7f7-124">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="dd7f7-125">**So weisen Sie einen Auftrag einer Auftragskategorie zu**</span><span class="sxs-lookup"><span data-stu-id="dd7f7-125">**To assign a job to a job category**</span></span>  
  
 <span data-ttu-id="dd7f7-126">Verwenden Sie die `JobCategory`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd7f7-126">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
  
  
