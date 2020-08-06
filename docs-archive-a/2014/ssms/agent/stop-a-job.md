---
title: Beenden eines Auftrags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
ms.assetid: 4249328a-24d8-4284-9d1d-7d04ed90e3d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78986e85dd8ee808f5fb621182d903a94bbc5eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695246"
---
# <a name="stop-a-job"></a><span data-ttu-id="ad40b-102">Stop a Job</span><span class="sxs-lookup"><span data-stu-id="ad40b-102">Stop a Job</span></span>
  <span data-ttu-id="ad40b-103">In diesem Thema wird beschrieben, wie ein-Agent-Auftrag beendet wird [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad40b-103">This topic describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="ad40b-104">Ein Auftrag ist eine festgelegte Reihe von Aktionen, die der SQL Server-Agent ausführt.</span><span class="sxs-lookup"><span data-stu-id="ad40b-104">A job is a specified series of actions that SQL Server Agent performs.</span></span>  
  
-   <span data-ttu-id="ad40b-105">Vorbereitungen **:** ,</span><span class="sxs-lookup"><span data-stu-id="ad40b-105">**Before you begin:**  ,</span></span>  
  
     [<span data-ttu-id="ad40b-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ad40b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ad40b-107">Security</span><span class="sxs-lookup"><span data-stu-id="ad40b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad40b-108">**So halten Sie einen Auftrag an mit**</span><span class="sxs-lookup"><span data-stu-id="ad40b-108">**To stop a job, using:**</span></span>  
  
     [<span data-ttu-id="ad40b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad40b-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="ad40b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad40b-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="ad40b-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ad40b-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad40b-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ad40b-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ad40b-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ad40b-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ad40b-114">Wenn ein Auftrag aktuell einen Schritt des Typs **CmdExec** oder **PowerShell**ausführt, wird der ausgeführte Prozess (z. B. Programm.exe) vorzeitig beendet.</span><span class="sxs-lookup"><span data-stu-id="ad40b-114">If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, MyProgram.exe) is forced to end prematurely.</span></span> <span data-ttu-id="ad40b-115">Dies kann zu unvorhersehbarem Verhalten führen, so werden z.&nbsp;B. Dateien, die vom Prozess verwendet werden, geöffnet bleiben.</span><span class="sxs-lookup"><span data-stu-id="ad40b-115">This can cause unpredictable behavior, such as files that are being used by the process being held open.</span></span>  
  
-   <span data-ttu-id="ad40b-116">Bei einem Multiserverauftrag wird eine STOP-Anweisung für den Auftrag an alle Zielserver des Auftrags gesendet.</span><span class="sxs-lookup"><span data-stu-id="ad40b-116">For a multiserver job, a STOP instruction for the job is posted to all target servers of the job.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad40b-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad40b-117">Security</span></span>  
 <span data-ttu-id="ad40b-118">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ad40b-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ad40b-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad40b-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-stop-a-job"></a><span data-ttu-id="ad40b-120">So beenden Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="ad40b-120">To stop a job</span></span>  
  
1.  <span data-ttu-id="ad40b-121">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="ad40b-121">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ad40b-122">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den zu beendenden Auftrag, und klicken Sie dann auf **Auftrag beenden**.</span><span class="sxs-lookup"><span data-stu-id="ad40b-122">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then click **Stop Job**.</span></span>  
  
3.  <span data-ttu-id="ad40b-123">Wenn Sie mehrere Aufträge beenden möchten, klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor**, und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ad40b-123">If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="ad40b-124">Wählen Sie im Auftragsaktivitätsmonitor die Aufträge aus, die beendet werden sollen, klicken Sie mit der rechten Maustaste auf Ihre Auswahl, und klicken Sie dann auf **Aufträge beenden**.</span><span class="sxs-lookup"><span data-stu-id="ad40b-124">In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then click **Stop Jobs**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="ad40b-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad40b-125">Using Transact-SQL</span></span>  
  
### <a name="to-stop-a-job"></a><span data-ttu-id="ad40b-126">So beenden Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="ad40b-126">To stop a job</span></span>  
  
1.  <span data-ttu-id="ad40b-127">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ad40b-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad40b-128">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ad40b-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ad40b-129">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ad40b-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- stops a job named Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_stop_job  
        N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="ad40b-130">Weitere Informationen finden Sie unter [sp_stop_job &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad40b-130">For more information, see [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="ad40b-131">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ad40b-131">Using SQL Server Management Objects</span></span>  

### <a name="to-stop-a-job"></a><span data-ttu-id="ad40b-132">So beenden Sie einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="ad40b-132">To stop a job</span></span>
  
 <span data-ttu-id="ad40b-133">Rufen Sie die `Stop`-Methode der `Job`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad40b-133">Call the `Stop` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="ad40b-134">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad40b-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
