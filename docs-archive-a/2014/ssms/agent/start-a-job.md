---
title: Starten eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], starting
- SQL Server Agent jobs, starting
- starting jobs
ms.assetid: cec9f7f7-d0a7-4239-9dc5-a69c011ebaa0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d5af895df518a915dacd953331b9139471933aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722173"
---
# <a name="start-a-job"></a><span data-ttu-id="c1bbf-102">Starten eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="c1bbf-102">Start a Job</span></span>
  <span data-ttu-id="c1bbf-103">In diesem Thema wird beschrieben, wie ein- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Auftrag in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-103">This topic describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="c1bbf-104">Ein Auftrag ist eine festgelegte Reihe von Aktionen, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausführt.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c1bbf-105">-Agent-Aufträge können auf einem lokalen oder mehreren Remoteservern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-105">Agent jobs can run on one local server or on multiple remote servers.</span></span>  
  
-   <span data-ttu-id="c1bbf-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c1bbf-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c1bbf-107">Security</span><span class="sxs-lookup"><span data-stu-id="c1bbf-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c1bbf-108">**So starten Sie einen Auftrag an mit**</span><span class="sxs-lookup"><span data-stu-id="c1bbf-108">**To start a job, using:**</span></span>  
  
     [<span data-ttu-id="c1bbf-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1bbf-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c1bbf-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1bbf-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="c1bbf-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c1bbf-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1bbf-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c1bbf-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c1bbf-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c1bbf-113">Security</span></span>  
 <span data-ttu-id="c1bbf-114">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c1bbf-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c1bbf-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1bbf-115">Using SQL Server Management Studio</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="c1bbf-116">So starten Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="c1bbf-116">To start a job</span></span>  
  
1.  <span data-ttu-id="c1bbf-117">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c1bbf-118">Erweitern Sie **SQL Server-Agent** , und erweitern Sie dann **Aufträge**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-118">Expand **SQL Server Agent,** and expand **Jobs**.</span></span> <span data-ttu-id="c1bbf-119">Führen Sie, je nachdem, wie der Auftrag gestartet werden soll, eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c1bbf-119">Depending on how you want the job to start, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c1bbf-120">Wenn Sie auf einem einzelnen Server oder einem Zielserver arbeiten oder einen lokalen Serverauftrag auf einem Masterserver ausführen, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie starten möchten, und klicken Sie dann auf **Auftrag starten**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-120">If you are working on a single server, or working on a target server, or running a local server job on a master server, right-click the job you want to start, and then click **Start Job**.</span></span>  
  
    -   <span data-ttu-id="c1bbf-121">Wenn Sie mehrere Aufträge starten möchten, klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor**, und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-121">If you want to start multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="c1bbf-122">Im Auftragsaktivitätsmonitor können Sie mehrere Aufträge auswählen. Klicken Sie dazu mit der rechten Maustaste auf die Auswahl, und klicken Sie auf **Aufträge starten**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-122">In the Job Activity Monitor you can select multiple jobs, right-click your selection, and click **Start Jobs**.</span></span>  
  
    -   <span data-ttu-id="c1bbf-123">Wenn Sie auf einem Masterserver arbeiten und alle Zielserver den Auftrag gleichzeitig ausführen sollen, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie starten möchten, klicken Sie auf **Auftrag starten**und dann auf **Auf allen Zielservern starten**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-123">If you are working on a master server and want all targeted servers to run the job simultaneously, right-click the job you want to start, click **Start Job**, and then click **Start on all targeted servers**.</span></span>  
  
    -   <span data-ttu-id="c1bbf-124">Wenn Sie auf einem Masterserver arbeiten und Zielserver für den Auftrag angeben möchten, klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie starten möchten, klicken Sie auf **Auftrag starten**und dann auf **Auf angegebenen Zielservern starten**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-124">If you are working on a master server and want to specify target servers for the job, right-click the job you want to start, click **Start Job**, and then click **Start on specific target servers**.</span></span> <span data-ttu-id="c1bbf-125">Aktivieren Sie im Dialogfeld **Downloadanweisungen bereitstellen** das Kontrollkästchen **Diese Zielserver** , und wählen Sie dann alle Zielserver aus, auf denen dieser Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-125">In the **Post Download Instructions** dialog box, select the **These target servers** check box, and then select each target server on which this job should run.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="c1bbf-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1bbf-126">Using Transact-SQL</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="c1bbf-127">So starten Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="c1bbf-127">To start a job</span></span>  
  
1.  <span data-ttu-id="c1bbf-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c1bbf-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c1bbf-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- starts a job named Weekly Sales Data Backup.    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_start_job N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="c1bbf-131">Weitere Informationen finden Sie unter [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1bbf-131">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c1bbf-132">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c1bbf-132">Using SQL Server Management Objects</span></span>  

### <a name="to-start-a-job"></a><span data-ttu-id="c1bbf-133">So starten Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="c1bbf-133">To start a job</span></span>
  
 <span data-ttu-id="c1bbf-134">Rufen Sie die `Start`-Methode der `Job`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1bbf-134">Call the `Start` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="c1bbf-135">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1bbf-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
