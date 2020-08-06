---
title: Erstellen eines PowerShell-Skript-Auftragsschritts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4232cdfa584fdcc2e13786ecc9bd00f0c6fe7066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617359"
---
# <a name="create-a-powershell-script-job-step"></a><span data-ttu-id="c9929-102">Create a PowerShell Script Job Step</span><span class="sxs-lookup"><span data-stu-id="c9929-102">Create a PowerShell Script Job Step</span></span>
  <span data-ttu-id="c9929-103">In diesem Thema wird beschrieben, wie Sie einen Auftragsschritt des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents erstellen und definieren, der in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ein PowerShell-Skript ausführt.</span><span class="sxs-lookup"><span data-stu-id="c9929-103">This topic describes how to create and define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c9929-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c9929-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c9929-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c9929-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c9929-106">Security</span><span class="sxs-lookup"><span data-stu-id="c9929-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c9929-107">**So erstellen Sie einen PowerShell-Skript-Auftragsschritt mit**</span><span class="sxs-lookup"><span data-stu-id="c9929-107">**To create a PowerShell Script job step, using:**</span></span>  
  
     [<span data-ttu-id="c9929-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9929-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c9929-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9929-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="c9929-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c9929-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9929-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c9929-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9929-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c9929-112">Security</span></span>  
 <span data-ttu-id="c9929-113">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c9929-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c9929-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9929-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="c9929-115">So erstellen Sie einen PowerShell-Skript-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="c9929-115">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="c9929-116">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="c9929-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c9929-117">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c9929-117">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="c9929-118">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="c9929-118">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="c9929-119">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="c9929-119">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="c9929-120">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="c9929-120">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="c9929-121">Klicken Sie in der Liste **Typ** auf **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c9929-121">In the **Type** list, click **PowerShell**.</span></span>  
  
6.  <span data-ttu-id="c9929-122">Wählen Sie in der Liste **Ausführen als** das Proxykonto mit den Anmeldeinformationen für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="c9929-122">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="c9929-123">Geben Sie im Feld **Befehl** die PowerShell-Skriptsyntax ein, die für den Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9929-123">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="c9929-124">Klicken Sie alternativ auf **Öffnen** , und wählen Sie eine Datei aus, die die Skriptsyntax enthält.</span><span class="sxs-lookup"><span data-stu-id="c9929-124">Alternately, click **Open** and select a file containing the script syntax.</span></span> <span data-ttu-id="c9929-125">Ein Beispiel für ein PowerShell-Skript finden Sie unten unter **Verwendung von Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="c9929-125">For an example of a PowerShell script, see **Using Transact-SQL** below.</span></span>  
  
8.  <span data-ttu-id="c9929-126">Klicken Sie auf die Seite **Erweitert** , um die folgenden Optionen für den Auftragsschritt festzulegen: welche Aktion bei der erfolgreichen oder fehlerhaften Ausführung des Auftragsschrittes jeweils auszuführen ist, wie oft der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent versuchen soll, den Auftragsschritt auszuführen, und wie viele Wiederholungsversuche unternommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c9929-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="c9929-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9929-127">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="c9929-128">So erstellen Sie einen PowerShell-Skript-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="c9929-128">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="c9929-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c9929-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c9929-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c9929-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c9929-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c9929-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a PowerShell job step that finds the processes that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="c9929-132">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9929-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c9929-133">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c9929-133">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c9929-134">**So erstellen Sie einen PowerShell-Skript-Auftragsschritt**</span><span class="sxs-lookup"><span data-stu-id="c9929-134">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="c9929-135">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9929-135">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
