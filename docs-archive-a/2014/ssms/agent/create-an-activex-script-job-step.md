---
title: Erstellen eines ActiveX-Skript-Auftragsschritts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ActiveX scripting jobs [SQL Server]
- job steps [Analysis Services]
ms.assetid: e6c46c6b-2d61-4571-bc8e-a831cd6e6302
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6604ba75af7acdd5bd2521433e8310c74150ce8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695262"
---
# <a name="create-an-activex-script-job-step"></a><span data-ttu-id="d4417-102">Create an ActiveX Script Job Step</span><span class="sxs-lookup"><span data-stu-id="d4417-102">Create an ActiveX Script Job Step</span></span>
  <span data-ttu-id="d4417-103">In diesem Thema wird beschrieben, wie Sie einen- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Auftrags Schritt in erstellen und definieren [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , der ein ActiveX-Skript mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects ausführt.</span><span class="sxs-lookup"><span data-stu-id="d4417-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that executes an ActiveX script by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="d4417-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d4417-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d4417-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d4417-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d4417-106">Security</span><span class="sxs-lookup"><span data-stu-id="d4417-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d4417-107">**So erstellen Sie einen Transact-SQL-Auftragsschritt mit**</span><span class="sxs-lookup"><span data-stu-id="d4417-107">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="d4417-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d4417-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d4417-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d4417-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d4417-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d4417-110">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="d4417-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d4417-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d4417-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d4417-112">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d4417-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d4417-113">Security</span></span>  
 <span data-ttu-id="d4417-114">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d4417-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d4417-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d4417-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="d4417-116">So erstellen Sie einen ActiveX-Skript-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="d4417-116">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="d4417-117">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d4417-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d4417-118">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d4417-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="d4417-119">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d4417-119">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="d4417-120">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d4417-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="d4417-121">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="d4417-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="d4417-122">Klicken Sie in der Liste **Typ** auf **ActiveX-Skript**.</span><span class="sxs-lookup"><span data-stu-id="d4417-122">In the **Type** list, click **ActiveX Script**.</span></span>  
  
6.  <span data-ttu-id="d4417-123">Wählen Sie in der Liste **Ausführen als** das Proxykonto mit den Anmeldeinformationen für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="d4417-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="d4417-124">Wählen Sie die **Sprache** aus, in der das Skript geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="d4417-124">Select the **Language** in which the script was written.</span></span> <span data-ttu-id="d4417-125">Klicken Sie alternativ auf **Andere** , und geben Sie dann den Namen der [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX-Skriptsprache ein, in der das Skript geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d4417-125">Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.</span></span>  
  
8.  <span data-ttu-id="d4417-126">Geben Sie im Feld **Befehl** die Skriptsyntax ein, die für den Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4417-126">In the **Command** box, enter the script syntax that will be executed for the job step.</span></span> <span data-ttu-id="d4417-127">Klicken Sie alternativ auf **Öffnen** , und wählen Sie eine Datei aus, die die Skriptsyntax enthält.</span><span class="sxs-lookup"><span data-stu-id="d4417-127">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
9. <span data-ttu-id="d4417-128">Klicken Sie auf die Seite **Erweitert** , um die folgenden Optionen für den Auftragsschritt festzulegen: welche Aktion bei der erfolgreichen oder fehlerhaften Ausführung des Auftragsschrittes jeweils auszuführen ist, wie oft der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent versuchen soll, den Auftragsschritt auszuführen, und wie viele Wiederholungsversuche unternommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4417-128">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d4417-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d4417-129">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="d4417-130">So erstellen Sie einen ActiveX-Skript-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="d4417-130">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="d4417-131">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d4417-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d4417-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d4417-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d4417-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4417-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="d4417-134">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d4417-134">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d4417-135">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d4417-135">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="d4417-136">**So erstellen Sie einen ActiveX-Skript-Auftragsschritt**</span><span class="sxs-lookup"><span data-stu-id="d4417-136">**To create an ActiveX Script job step**</span></span>  
  
 <span data-ttu-id="d4417-137">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4417-137">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
