---
title: Löschen des Auftragsverlaufsprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- clearing job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 34b9398a-c409-4040-8ea1-0deceb18f961
author: stevestein
ms.author: sstein
ms.openlocfilehash: 813c2c7c86a769eea09a093f2de999460d78ef54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622380"
---
# <a name="clear-the-job-history-log"></a><span data-ttu-id="a46d8-102">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="a46d8-102">Clear the Job History Log</span></span>
  <span data-ttu-id="a46d8-103">In diesem Thema wird beschrieben, wie der Inhalt des Auftragsverlaufs Protokolls des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agents in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="a46d8-103">This topic describes how to delete the contents of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="a46d8-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a46d8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a46d8-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a46d8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a46d8-106">Security</span><span class="sxs-lookup"><span data-stu-id="a46d8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a46d8-107">**So löschen Sie das Auftragsverlaufsprotokoll mit**</span><span class="sxs-lookup"><span data-stu-id="a46d8-107">**To clear the job history log, using:**</span></span>  
  
     [<span data-ttu-id="a46d8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a46d8-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="a46d8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a46d8-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="a46d8-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="a46d8-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a46d8-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a46d8-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a46d8-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a46d8-112">Security</span></span>  
 <span data-ttu-id="a46d8-113">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a46d8-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a46d8-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a46d8-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="a46d8-115">So löschen Sie das Auftragsverlaufsprotokoll</span><span class="sxs-lookup"><span data-stu-id="a46d8-115">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="a46d8-116">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="a46d8-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a46d8-117">Erweitern Sie **SQL Server-Agent**, und klicken Sie auf **Aufträge**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-117">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="a46d8-118">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-118">Right-click a job and click **View history**.</span></span>  
  
4.  <span data-ttu-id="a46d8-119">Wählen Sie im **Protokolldatei-Viewer**den Auftrag aus, dessen Verlauf gelöscht werden soll, und führen Sie dann einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a46d8-119">In the **Log File Viewer**, select the job for which you want to clear history, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="a46d8-120">Klicken Sie auf **Löschen**, und klicken Sie dann im Dialogfeld **Verlauf löschen** auf **Gesamten Verlauf löschen** .</span><span class="sxs-lookup"><span data-stu-id="a46d8-120">Click **Delete**, and then click **Delete all history** in the **Delete History** dialog.</span></span> <span data-ttu-id="a46d8-121">Sie können wahlweise den gesamten Auftragsverlauf löschen oder auch nur den Verlauf, der vor einem bestimmten Datum angefallen ist.</span><span class="sxs-lookup"><span data-stu-id="a46d8-121">You can delete all job history or only history that is older than a specified date.</span></span> <span data-ttu-id="a46d8-122">Soll der gesamte Auftragsverlauf gelöscht werden, klicken Sie auf **Gesamten Verlauf löschen**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-122">If you want to remove all job history, click **Delete all history**.</span></span> <span data-ttu-id="a46d8-123">Um nur ältere Einträge im Auftragsverlauf zu löschen, klicken Sie auf **Verlauf löschen vor**, und geben Sie das gewünschte Datum an.</span><span class="sxs-lookup"><span data-stu-id="a46d8-123">If you only want to remove older job history logs, click **Delete history before**, and then specify a date.</span></span>  
  
    -   <span data-ttu-id="a46d8-124">Klicken Sie auf **Auftragsstatus** , wenn Sie das Verlaufsprotokoll eines Multiserverauftrags löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="a46d8-124">Click **Job status** if you want to clear the history log of a multiserver job.</span></span> <span data-ttu-id="a46d8-125">Klicken Sie auf **Auftrag**und auf einen Auftragsnamen, und klicken Sie dann auf **Remoteauftragsverlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-125">Click **Job**, click a job name, and then click **View Remote Job History**.</span></span>  
  
5.  <span data-ttu-id="a46d8-126">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-126">Click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="a46d8-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a46d8-127">Using Transact-SQL</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="a46d8-128">So löschen Sie das Auftragsverlaufsprotokoll</span><span class="sxs-lookup"><span data-stu-id="a46d8-128">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="a46d8-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="a46d8-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a46d8-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a46d8-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a46d8-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- example removes the history for a job named NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_purge_jobhistory  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="a46d8-132">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="a46d8-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="a46d8-133">**So löschen Sie das Auftragsverlaufsprotokoll**</span><span class="sxs-lookup"><span data-stu-id="a46d8-133">**To clear the job history log**</span></span>  
  
 <span data-ttu-id="a46d8-134">Verwenden Sie die `PurgeJobHistory`-Methode der `JobServer`-Klasse in einer Programmiersprache Ihrer Wahl, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a46d8-134">Use the `PurgeJobHistory` method of the `JobServer` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="a46d8-135">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="a46d8-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
