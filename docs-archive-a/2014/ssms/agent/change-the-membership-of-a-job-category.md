---
title: Ändern der Mitgliedschaft einer Auftragskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- members [SQL Server], job categories
ms.assetid: 6a18f7f0-eb50-485f-a9c7-df31ae0f994e
author: stevestein
ms.author: sstein
ms.openlocfilehash: d9ed0db394f63594937ad923734b07fed8050955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622384"
---
# <a name="change-the-membership-of-a-job-category"></a><span data-ttu-id="d8711-102">Change the Membership of a Job Category</span><span class="sxs-lookup"><span data-stu-id="d8711-102">Change the Membership of a Job Category</span></span>
  <span data-ttu-id="d8711-103">In diesem Thema wird beschrieben, wie Sie die Mitgliedschaft der Auftragskategorie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder SQL Server Management Objects ändern können.</span><span class="sxs-lookup"><span data-stu-id="d8711-103">This topic describes how to change the membership of the job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="d8711-104">Auftragskategorien helfen Ihnen dabei, Ihre Aufträge zum einfachen Filtern und Gruppieren zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="d8711-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="d8711-105">Sie können eigene Auftragskategorien erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8711-105">You can create your own job categories.</span></span> <span data-ttu-id="d8711-106">Zudem können Sie die Mitgliedschaft von Microsoft SQL Server-Agent-Aufträgen in Auftragskategorien ändern.</span><span class="sxs-lookup"><span data-stu-id="d8711-106">You can also change Microsoft SQL Server Agent jobs membership in job categories.</span></span>  
  
 <span data-ttu-id="d8711-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d8711-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8711-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d8711-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8711-109">Security</span><span class="sxs-lookup"><span data-stu-id="d8711-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d8711-110">**So ändern Sie die Mitgliedschaft einer Auftragskategorie mit**</span><span class="sxs-lookup"><span data-stu-id="d8711-110">**To change the membership of a job category, using:**</span></span>  
  
     [<span data-ttu-id="d8711-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8711-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d8711-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8711-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d8711-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d8711-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8711-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d8711-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8711-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d8711-115">Security</span></span>  
 <span data-ttu-id="d8711-116">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d8711-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d8711-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8711-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="d8711-118">So ändern Sie die Mitgliedschaft einer Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="d8711-118">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="d8711-119">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie eine Auftragskategorie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d8711-119">In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.</span></span>  
  
2.  <span data-ttu-id="d8711-120">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d8711-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d8711-121">Klicken Sie mit der rechten Maustaste auf den Ordner **Aufträge** , und wählen Sie **Auftragskategorien verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="d8711-121">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="d8711-122">Wählen Sie im Dialogfeld **Auftragskategorien verwalten -**_Servername_ die Auftragskategorie aus, die Sie bearbeiten möchten, und klicken Sie dann auf **Aufträge anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d8711-122">In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.</span></span>  
  
5.  <span data-ttu-id="d8711-123">Aktivieren Sie das Kontrollkästchen **Alle Aufträge anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="d8711-123">Select the **Show all jobs** check box.</span></span>  
  
6.  <span data-ttu-id="d8711-124">Um der Kategorie einen Auftrag hinzuzufügen, aktivieren Sie im Hauptraster in der **Select** -Spalte das Kontrollkästchen, das dem Auftrag entspricht.</span><span class="sxs-lookup"><span data-stu-id="d8711-124">To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job.</span></span> <span data-ttu-id="d8711-125">Um einen Auftrag aus der Kategorie zu entfernen, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="d8711-125">To remove a job from the category, clear the box.</span></span> <span data-ttu-id="d8711-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8711-126">When finished, click **OK**.</span></span>  
  
7.  <span data-ttu-id="d8711-127">Schließen Sie das Dialogfeld **Auftrags Kategorien verwalten**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="d8711-127">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d8711-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8711-128">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="d8711-129">So ändern Sie die Mitgliedschaft einer Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="d8711-129">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="d8711-130">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d8711-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8711-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d8711-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8711-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d8711-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="d8711-133">Weitere Informationen finden Sie unter [sp_update_job &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8711-133">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d8711-134">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d8711-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="d8711-135">**So ändern Sie die Mitgliedschaft einer Auftragskategorie**</span><span class="sxs-lookup"><span data-stu-id="d8711-135">**To change the membership of a job category**</span></span>  
  
 <span data-ttu-id="d8711-136">Verwenden Sie die `JobCategory`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8711-136">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
