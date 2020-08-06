---
title: Erstellen eines Transact-SQL-Auftragsschritts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
author: stevestein
ms.author: sstein
ms.openlocfilehash: b83ee944d2ca5c10ff1b77f3e6e6da6054b5c99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722210"
---
# <a name="create-a-transact-sql-job-step"></a><span data-ttu-id="e9925-102">Erstellen eines Transact-SQL-Auftragsschritts</span><span class="sxs-lookup"><span data-stu-id="e9925-102">Create a Transact-SQL Job Step</span></span>
  <span data-ttu-id="e9925-103">In diesem Thema wird beschrieben, wie Sie einen-Agent-Auftrags Schritt erstellen, mit dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] Skripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9925-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="e9925-104">Diese Auftragsschrittskripts können gespeicherte Prozeduren und erweiterte gespeicherte Prozeduren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e9925-104">These job step scripts may call stored procedures and extended stored procedures.</span></span> <span data-ttu-id="e9925-105">Ein einzelner [!INCLUDE[tsql](../../includes/tsql-md.md)] -Auftragsschritt kann mehrere Batches und eingebettete GO-Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9925-105">A single [!INCLUDE[tsql](../../includes/tsql-md.md)] job step can contain multiple batches and embedded GO commands.</span></span> <span data-ttu-id="e9925-106">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e9925-106">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
 <span data-ttu-id="e9925-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e9925-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e9925-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e9925-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e9925-109">Security</span><span class="sxs-lookup"><span data-stu-id="e9925-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e9925-110">**So erstellen Sie einen Transact-SQL-Auftragsschritt mit**</span><span class="sxs-lookup"><span data-stu-id="e9925-110">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="e9925-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9925-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e9925-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9925-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e9925-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e9925-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e9925-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e9925-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e9925-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e9925-115">Security</span></span>  
 <span data-ttu-id="e9925-116">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e9925-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e9925-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9925-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="e9925-118">So erstellen Sie einen Transact-SQL-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="e9925-118">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="e9925-119">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="e9925-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e9925-120">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e9925-120">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e9925-121">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e9925-121">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e9925-122">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="e9925-122">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="e9925-123">Klicken Sie in der Liste **Typ** auf **Transact-SQL-Skript (TSQL)**.</span><span class="sxs-lookup"><span data-stu-id="e9925-123">In the **Type** list, click **Transact-SQL Script (TSQL)**.</span></span>  
  
6.  <span data-ttu-id="e9925-124">Geben Sie im Feld **Befehl** die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Befehlsbatches ein, oder klicken Sie auf **Öffnen** , um eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Datei auszuwählen, die als Befehl verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9925-124">In the **Command** box, type the [!INCLUDE[tsql](../../includes/tsql-md.md)] command batches, or click **Open** to select a [!INCLUDE[tsql](../../includes/tsql-md.md)] file to use as the command.</span></span>  
  
7.  <span data-ttu-id="e9925-125">Klicken Sie auf **Analysieren** , um die Syntax zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e9925-125">Click **Parse** to check your syntax.</span></span>  
  
8.  <span data-ttu-id="e9925-126">Wenn die Syntax richtig ist, wird die Meldung "Analyse erfolgreich" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9925-126">The message "Parse succeeded" is displayed when your syntax is correct.</span></span> <span data-ttu-id="e9925-127">Wenn ein Fehler gefunden wird, müssen Sie die Syntax korrigieren, bevor Sie den Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="e9925-127">If an error is found, correct the syntax before continuing.</span></span>  
  
9. <span data-ttu-id="e9925-128">Klicken Sie auf die Seite **Erweitert** , um Optionen für Auftragsschritte festzulegen, z.&nbsp;B. welche Aktion ausgeführt werden soll, wenn ein Auftragsschritt erfolgreich ausgeführt wird oder einen Fehler erzeugt, wie häufig der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent versuchen soll, den Auftragsschritt auszuführen, und in welche Datei oder Tabelle der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Auftragsschrittausgabe schreiben soll.</span><span class="sxs-lookup"><span data-stu-id="e9925-128">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file or table where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="e9925-129">Nur Mitglieder der festen Serverrolle **sysadmin** können die Auftragsschrittausgabe in eine Betriebssystemdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="e9925-129">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span> <span data-ttu-id="e9925-130">Alle Benutzer des SQL Server-Agents können die Ausgabe in einer Tabelle protokollieren.</span><span class="sxs-lookup"><span data-stu-id="e9925-130">All SQL Server Agent users can log output to a table.</span></span>  
  
10. <span data-ttu-id="e9925-131">Wenn Sie ein Mitglied der festen Serverrolle **sysadmin** sind und diesen Auftragsschritt unter einem anderen SQL-Anmeldenamen ausführen möchten, wählen Sie den SQL-Anmeldenamen in der Liste **Ausführen als Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="e9925-131">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e9925-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9925-132">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="e9925-133">So erstellen Sie einen Transact-SQL-Auftragsschritt</span><span class="sxs-lookup"><span data-stu-id="e9925-133">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="e9925-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e9925-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9925-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e9925-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e9925-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e9925-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses Transact-SQL  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="e9925-137">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9925-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e9925-138">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e9925-138">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e9925-139">**So erstellen Sie einen Transact-SQL-Auftragsschritt**</span><span class="sxs-lookup"><span data-stu-id="e9925-139">**To create a Transact-SQL job step**</span></span>  
  
 <span data-ttu-id="e9925-140">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9925-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
