---
title: Anzeigen des Auftragsverlaufs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- viewing job history
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
- displaying job history
ms.assetid: 3bbd1556-abdb-48a3-b249-546eace76343
author: stevestein
ms.author: sstein
ms.openlocfilehash: e84fafdaeddb5748a8129cd5d71d667db7e5fa37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719375"
---
# <a name="view-the-job-history"></a><span data-ttu-id="c6258-102">View the Job History</span><span class="sxs-lookup"><span data-stu-id="c6258-102">View the Job History</span></span>
  <span data-ttu-id="c6258-103">In diesem Thema wird beschrieben, wie Sie das Auftragsverlaufs Protokoll des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agents in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6258-103">This topic describes how to view the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="c6258-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c6258-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6258-105">Security</span><span class="sxs-lookup"><span data-stu-id="c6258-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6258-106">**So zeigen Sie das Auftragsverlaufsprotokoll an, und zwar mit**</span><span class="sxs-lookup"><span data-stu-id="c6258-106">**To view the job history log, using:**</span></span>  
  
     [<span data-ttu-id="c6258-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6258-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c6258-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6258-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="c6258-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c6258-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6258-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c6258-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6258-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c6258-111">Security</span></span>  
 <span data-ttu-id="c6258-112">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c6258-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c6258-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6258-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="c6258-114">So zeigen Sie das Auftragsverlaufsprotokoll an</span><span class="sxs-lookup"><span data-stu-id="c6258-114">To view the job history log</span></span>  
  
1.  <span data-ttu-id="c6258-115">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="c6258-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c6258-116">Erweitern Sie **SQL Server-Agent**, und klicken Sie auf **Aufträge**.</span><span class="sxs-lookup"><span data-stu-id="c6258-116">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="c6258-117">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c6258-117">Right-click a job, and then click **View History**.</span></span>  
  
4.  <span data-ttu-id="c6258-118">Zeigen Sie im Protokolldatei-Viewer den Auftragsverlauf an.</span><span class="sxs-lookup"><span data-stu-id="c6258-118">In the Log File Viewer, view the job history.</span></span>  
  
5.  <span data-ttu-id="c6258-119">Klicken Sie auf **Aktualisieren**, um den Auftragsverlauf zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6258-119">To update the job history, click **Refresh**.</span></span> <span data-ttu-id="c6258-120">Um weniger Zeilen anzuzeigen, klicken Sie auf **Filter** , und geben Sie Filterparameter ein.</span><span class="sxs-lookup"><span data-stu-id="c6258-120">To view fewer rows, click the **Filter** button and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="c6258-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6258-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="c6258-122">So zeigen Sie das Auftragsverlaufsprotokoll an</span><span class="sxs-lookup"><span data-stu-id="c6258-122">To view the job history log</span></span>  
  
1.  <span data-ttu-id="c6258-123">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c6258-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6258-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6258-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6258-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c6258-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all job information for the NightlyBackups job.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobhistory   
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="c6258-126">Weitere Informationen finden Sie unter [sp_help_jobhistory &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6258-126">For more information, see [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c6258-127">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c6258-127">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c6258-128">**So zeigen Sie das Auftragsverlaufsprotokoll an**</span><span class="sxs-lookup"><span data-stu-id="c6258-128">**To view the job history log**</span></span>  
  
 <span data-ttu-id="c6258-129">Rufen Sie die `EnumHistory`-Methode der `Job`-Klasse in einer Programmiersprache Ihrer Wahl auf, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6258-129">Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="c6258-130">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6258-130">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
