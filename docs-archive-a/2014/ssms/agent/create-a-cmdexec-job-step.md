---
title: Erstellen eines CmdExec-Auftragsschritts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CmdExec jobs
ms.assetid: b48da5b4-6fe7-4eb7-bade-dc7d697c6d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c557b8ea4228d27b73d361c50aac62232d1e00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617357"
---
# <a name="create-a-cmdexec-job-step"></a><span data-ttu-id="5c0e7-102">Create a CmdExec Job Step</span><span class="sxs-lookup"><span data-stu-id="5c0e7-102">Create a CmdExec Job Step</span></span>
  <span data-ttu-id="5c0e7-103">In diesem Thema wird beschrieben, wie Sie einen- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Auftrags Schritt in, der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ein ausführbares Programm oder einen Betriebssystem Befehl verwendet, mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects erstellen und definieren.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that uses an executable program or operating system command by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="5c0e7-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5c0e7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5c0e7-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5c0e7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c0e7-106">Security</span><span class="sxs-lookup"><span data-stu-id="5c0e7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c0e7-107">**So erstellen Sie einen CmdExec-Auftragsschritt mit**</span><span class="sxs-lookup"><span data-stu-id="5c0e7-107">**To create a CmdExec job step, using:**</span></span>  
  
     [<span data-ttu-id="5c0e7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c0e7-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5c0e7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c0e7-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="5c0e7-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5c0e7-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c0e7-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5c0e7-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c0e7-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5c0e7-112">Security</span></span>  
 <span data-ttu-id="5c0e7-113">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** CmdExec-Auftragsschritte erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-113">By default, only members of the **sysadmin** fixed server role can create CmdExec job steps.</span></span> <span data-ttu-id="5c0e7-114">Diese Aufträge werden im Kontext des Kontos des SQL Server-Agent-Dienstes ausgeführt, außer der **sysadmin** -Benutzer erstellt ein Proxykonto.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-114">These job steps run under the context of the SQL Server Agent service account unless the **sysadmin** user creates a proxy account.</span></span> <span data-ttu-id="5c0e7-115">Benutzer, die keine Mitglieder der **sysadmin** -Rolle sind, können CmdExec-Auftragsschritte erstellen, wenn sie Zugriff auf ein CmdExec-Proxykonto haben.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-115">Users who are not members of the **sysadmin** role can create CmdExec job steps if they have access to a CmdExec proxy account.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5c0e7-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5c0e7-116">Permissions</span></span>  
 <span data-ttu-id="5c0e7-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5c0e7-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5c0e7-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c0e7-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="5c0e7-119">So erstellen Sie einen CmdExec-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="5c0e7-119">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="5c0e7-120">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5c0e7-121">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-121">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5c0e7-122">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-122">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="5c0e7-123">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-123">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="5c0e7-124">Wählen Sie in der Liste **Typ** den Eintrag **Betriebssystem (CmdExec)** aus.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-124">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
6.  <span data-ttu-id="5c0e7-125">Wählen Sie in der Liste **Ausführen als** das Proxykonto mit den Anmeldeinformationen für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-125">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="5c0e7-126">Standardmäßig werden CmdExec-Auftragsschritte im Kontext des Kontos des SQL Server-Agent-Dienstes ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-126">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
7.  <span data-ttu-id="5c0e7-127">Geben Sie in das Feld **Prozessexitcode eines erfolgreichen Befehls** einen Wert zwischen 0 und 999999 ein.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-127">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
8.  <span data-ttu-id="5c0e7-128">Geben Sie in das Feld **Befehl** den Betriebssystembefehl oder das ausführbare Programm ein.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-128">In the **Command** box, enter the operating system command or executable program.</span></span> <span data-ttu-id="5c0e7-129">Ein Beispiel finden Sie unter "Verwendung von Transact-SQL".</span><span class="sxs-lookup"><span data-stu-id="5c0e7-129">See "Using Transact T-SQL for an example.</span></span>  
  
9. <span data-ttu-id="5c0e7-130">Klicken Sie auf die Seite **Erweitert** , um Optionen für Auftragsschritte festzulegen, z. B. welche Aktion bei der erfolgreichen oder fehlerhaften Ausführung des Auftragsschrittes jeweils auszuführen ist, wie oft der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent versuchen soll, den Auftragsschritt auszuführen, und in welche Datei der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Auftragsschrittausgabe schreiben soll.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-130">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="5c0e7-131">Nur Mitglieder der festen Serverrolle **sysadmin** können die Auftragsschrittausgabe in eine Betriebssystemdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-131">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5c0e7-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c0e7-132">Using Transact-SQL</span></span>  
  
### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="5c0e7-133">So erstellen Sie einen CmdExec-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="5c0e7-133">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="5c0e7-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c0e7-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c0e7-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses CmdExec  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'CMDEXEC',  
        @command = C:\clickme_scripts\SQL11\PostBOLReorg GetHsX.exe',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="5c0e7-137">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="5c0e7-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="5c0e7-138">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5c0e7-138">Using SQL Server Management Objects</span></span>  

### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="5c0e7-139">So erstellen Sie einen CmdExec-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="5c0e7-139">To create a CmdExec job step</span></span>
  
 <span data-ttu-id="5c0e7-140">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c0e7-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
