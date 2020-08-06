---
title: Erstellen einer Auftragskategorie | Microsoft-Dokumentation
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
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f6daeeca6253861e8a9dcbb72faa2bd55eb2761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720803"
---
# <a name="create-a-job-category"></a><span data-ttu-id="1113c-102">Erstellen einer Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="1113c-102">Create a Job Category</span></span>
  <span data-ttu-id="1113c-103">In diesem Thema wird beschrieben, wie Sie eine Auftragskategorie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects erstellen können.</span><span class="sxs-lookup"><span data-stu-id="1113c-103">This topic describes how to create a job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1113c-104">Agent stellt integrierte Auftragskategorien bereit, denen Aufträge zugewiesen werden können. Sie können auch eine Auftragskategorie erstellen und diesen Aufträge zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1113c-104">Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it.</span></span> <span data-ttu-id="1113c-105">Auftragskategorien helfen Ihnen dabei, Ihre Aufträge zum einfachen Filtern und Gruppieren zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="1113c-105">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="1113c-106">Sie können z. B. alle Aufträge für die Datenbanksicherung in der Datenbankwartungskategorie organisieren.</span><span class="sxs-lookup"><span data-stu-id="1113c-106">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="1113c-107">Sie können zudem eigene Auftragskategorien erstellen.</span><span class="sxs-lookup"><span data-stu-id="1113c-107">You can also create your own job categories.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1113c-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1113c-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1113c-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1113c-109">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1113c-110">Multiserverkategorien sind nur auf einem Masterserver vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1113c-110">Multiserver categories exist only on a master server.</span></span> <span data-ttu-id="1113c-111">Auf einem Masterserver ist nur eine Standardauftragskategorie verfügbar: [**Nicht kategorisiert (Multiserver)**].</span><span class="sxs-lookup"><span data-stu-id="1113c-111">There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**].</span></span> <span data-ttu-id="1113c-112">Beim Herunterladen eines Multiserverauftrags wird seine Kategorie auf dem Zielserver in **Aufträge vom MSX** geändert.</span><span class="sxs-lookup"><span data-stu-id="1113c-112">When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1113c-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1113c-113">Security</span></span>  
 <span data-ttu-id="1113c-114">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="1113c-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1113c-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1113c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="1113c-116">So erstellen Sie eine Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="1113c-116">To create a job category</span></span>  
  
1.  <span data-ttu-id="1113c-117">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie eine Auftragskategorie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1113c-117">In **Object Explorer**, click the plus sign to expand the server where you want to create a job category.</span></span>  
  
2.  <span data-ttu-id="1113c-118">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1113c-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="1113c-119">Klicken Sie mit der rechten Maustaste auf den Ordner **Aufträge** , und wählen Sie **Auftragskategorien verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="1113c-119">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="1113c-120">Klicken Sie im Dialogfeld **Auftrags Kategorien verwalten**_server_name_ auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1113c-120">In the **Manage Job Categories**_server_name_ dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="1113c-121">Geben Sie im neuen Dialogfeld **Name** einen Namen für die neue Auftragskategorie ein.</span><span class="sxs-lookup"><span data-stu-id="1113c-121">In the new dialog box, in the **Name** box, enter a name for the new job category.</span></span>  
  
6.  <span data-ttu-id="1113c-122">Aktivieren Sie das Kontrollkästchen **Alle Aufträge anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="1113c-122">Select the **Show all jobs** check box.</span></span> <span data-ttu-id="1113c-123">Wählen Sie für die neue Kategorie mindestens einen Auftrag aus, indem Sie die Kontrollkästchen der entsprechenden Aufträge aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1113c-123">Select one or more jobs for the new category by checking the boxes corresponding to the jobs.</span></span>  
  
7.  <span data-ttu-id="1113c-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1113c-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="1113c-125">Klicken Sie im Dialogfeld **Auftrags Kategorien verwalten**_server_name_ auf **Aktualisieren** , um sicherzustellen, dass die neue Auftrags Kategorie aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="1113c-125">In the **Manage Job Categories**_server_name_ dialog box, click **Refresh** to ensure that the new job category is active.</span></span> <span data-ttu-id="1113c-126">Schließen Sie das Dialogfeld, wenn alles normal aussieht.</span><span class="sxs-lookup"><span data-stu-id="1113c-126">If everything looks as expected, close this dialog box.</span></span>  
  
 <span data-ttu-id="1113c-127">Weitere Informationen zu diesen Dialogfeldern finden Sie unter [Auftrags Kategorien: Verwalten von Auftrags Kategorien](job-categories-manage-job-categories.md) und [Auftrags Kategorien Eigenschaften und neuer Auftrags Kategorie](job-categories-properties-new-job-category.md).</span><span class="sxs-lookup"><span data-stu-id="1113c-127">For more information on these dialog boxes, see [Job Categories: Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties and New Job Category](job-categories-properties-new-job-category.md).</span></span>  

##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="1113c-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1113c-128">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="1113c-129">So erstellen Sie eine Auftragskategorie</span><span class="sxs-lookup"><span data-stu-id="1113c-129">To create a job category</span></span>  
  
1.  <span data-ttu-id="1113c-130">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="1113c-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1113c-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1113c-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1113c-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1113c-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="1113c-133">Weitere Informationen finden Sie unter [sp_add_category &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1113c-133">For more information, see [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="1113c-134">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="1113c-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="1113c-135">**So erstellen Sie eine Auftragskategorie**</span><span class="sxs-lookup"><span data-stu-id="1113c-135">**To create a job category**</span></span>  
  
 <span data-ttu-id="1113c-136">Rufen Sie die `JobCategory`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1113c-136">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="1113c-137">Beispielcode hierzu finden Sie unter [Planen von automatischen, administrativen Tasks im SQL Server-Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="1113c-137">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
