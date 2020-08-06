---
title: Erstellen eines Analysis Services-Auftragsschritts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [Analysis Services]
ms.assetid: 03d4bb86-514b-4a55-97b9-c2c0fa08b428
author: stevestein
ms.author: sstein
ms.openlocfilehash: ed0e63c22d4cad270bcb544b03decba269e4f43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699261"
---
# <a name="create-an-analysis-services-job-step"></a><span data-ttu-id="e0fb1-102">Erstellen eines Analysis Services-Auftragsschritts</span><span class="sxs-lookup"><span data-stu-id="e0fb1-102">Create an Analysis Services Job Step</span></span>
  <span data-ttu-id="e0fb1-103">In diesem Thema wird beschrieben, wie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftragsschritte in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] erstellt und definiert werden, mit denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services-Befehle und -Abfragen durch die Verwendung von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] oder SQL Server Management Objects ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-103">This topic describes how to create and define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services commands and queries by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="e0fb1-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e0fb1-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e0fb1-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e0fb1-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e0fb1-106">Security</span><span class="sxs-lookup"><span data-stu-id="e0fb1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e0fb1-107">**So erstellen Sie einen SQL Server-Auftrag mithilfe von Analysis Services-Befehlen bzw. -Abfragen mit**</span><span class="sxs-lookup"><span data-stu-id="e0fb1-107">**To create a SQL Server job steps using Analysis Services commands and/or queries, with:**</span></span>  
  
     [<span data-ttu-id="e0fb1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e0fb1-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e0fb1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0fb1-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e0fb1-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e0fb1-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e0fb1-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e0fb1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e0fb1-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e0fb1-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e0fb1-113">Wenn beim Auftragsschritt ein Analysis Services-Befehl verwendet wird, muss die Befehlsanweisung eine **Execute** -Methode von XML for Analysis Services sein.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-113">If the job step uses an Analysis Services command, the command statement must be an XML for Analysis Services **Execute** method.</span></span> <span data-ttu-id="e0fb1-114">Die Anweisung enthält möglicherweise keinen vollständigen SOAP-Umschlag (Simple Object Access Protocol) oder eine **Discover** -Methode von XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-114">The statement may not contain a complete Simple Object Access Protocol (SOAP) envelope or an XML for Analysis **Discover** method.</span></span> <span data-ttu-id="e0fb1-115">Während [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vollständige SOAP-Umschläge und die **Discover** -Methode unterstützt, ist das bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftragsschritten nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-115">While [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] supports complete SOAP envelopes and the **Discover** method, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps do not.</span></span> <span data-ttu-id="e0fb1-116">Weitere Informationen zu XML for Analysis Services finden Sie unter [Übersicht über XMLA for Analysis (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-116">For more information about XML for Analysis Services, see [XML for Analysis Overview (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span></span>  
  
-   <span data-ttu-id="e0fb1-117">Wenn beim Auftragsschritt ein Analysis Services-Abfrage verwendet wird, muss die Abfrageanweisung eine MDX-Abfrage (Multidimensional Expressions, mehrdimensionale Ausdrücke) sein.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-117">If the job step uses an Analysis Services query, the query statement must be a multidimensional expressions (MDX) query.</span></span> <span data-ttu-id="e0fb1-118">Weitere Informationen zu MDX finden Sie unter [Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-118">For more information about MDX, see [MDX Query Fundamentals &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e0fb1-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e0fb1-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e0fb1-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e0fb1-120">Permissions</span></span>  
  
-   <span data-ttu-id="e0fb1-121">Um einen Auftragsschritt auszuführen, der das Analysis Services-Subsystem verwendet, muss ein Benutzer Mitglied der festen Serverrolle **sysadmin** sein oder Zugriff auf ein gültiges Proxykonto haben, das für die Verwendung dieses Subsystems definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-121">To run a job step that uses the Analysis Services subsystem, a user must be a member of the **sysadmin** fixed server role or have access to a valid proxy account defined to use this subsystem.</span></span> <span data-ttu-id="e0fb1-122">Darüber hinaus muss es sich bei dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstkonto oder Proxy um einen Analysis Services-Administrator und ein gültiges Windows-Domänenkonto handeln.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-122">In addition, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account or the proxy must be an Analysis Services administrator and a valid Windows domain account.</span></span>  
  
-   <span data-ttu-id="e0fb1-123">Nur Mitglieder der festen Serverrolle **sysadmin** sind berechtigt, die Ausgabe eines Auftragsschritts in eine Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-123">Only members of the **sysadmin** fixed server role can write job step output to a file.</span></span> <span data-ttu-id="e0fb1-124">Wenn der Auftragsschritt von Benutzern ausgeführt wird, die in der **msdb** -Datenbank Mitglied der **SQLAgentUserRole** -Datenbankrolle sind, können die Ausgabedaten nur in eine Tabelle geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-124">If the job step is run by users who are members of the **SQLAgentUserRole** database role in the **msdb** database, then the output can be written only to a table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e0fb1-125">-Agent schreibt die Ausgabedaten des Auftragsschritts in der **SQLAgentUserRole** -Datenbank in die **SQLAgentUserRole** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-125">Agent writes job step output to the **sysjobstepslog** table in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="e0fb1-126">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-126">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e0fb1-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e0fb1-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="e0fb1-128">So erstellen Sie einen Auftragsschritt für den Analysis Services-Befehl</span><span class="sxs-lookup"><span data-stu-id="e0fb1-128">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="e0fb1-129">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-129">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e0fb1-130">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-130">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="e0fb1-131">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-131">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="e0fb1-132">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Registerkarte **Schritte** , und klicken Sie dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-132">In the **Job Properties** dialog box, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e0fb1-133">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-133">In the **New Job Step** dialog box, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="e0fb1-134">Klicken Sie in der Liste **Typ** auf **SQL Server Analysis Services-Befehl**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-134">In the **Type** list, click **SQL Server Analysis Services Command**.</span></span>  
  
6.  <span data-ttu-id="e0fb1-135">Wählen Sie in der Liste **Ausführen als** einen Proxy aus, der für die Verwendung des Analysis Services-Befehlssubsystems definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-135">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Command subsystem.</span></span> <span data-ttu-id="e0fb1-136">Ein Benutzer, der Mitglied der festen Serverrolle **sysadmin** ist, kann zur Ausführung dieses Auftragsschritts auch **SQL-Agent-Dienstkonto** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-136">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="e0fb1-137">Wählen Sie den **Server** aus, auf dem der Auftragsschritt ausgeführt wird, oder geben Sie den Servernamen ein.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-137">Select the **Server** where the job step will run, or type the server name.</span></span>  
  
8.  <span data-ttu-id="e0fb1-138">Geben Sie im Feld **Befehl** die auszuführende Anweisung ein, oder klicken Sie auf **Öffnen** , um eine Anweisung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-138">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="e0fb1-139">Klicken Sie auf die Seite **Erweitert** , um die Optionen für diesen Auftragsschritt zu definieren. Legen Sie beispielsweise fest, welche Aktion der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausführen soll, wenn der Auftragsschritt erfolgreich ausgeführt wird oder fehlschlägt, wie viele Versuche zur Ausführung des Auftragsschritts unternommen werden sollen und wohin die Ausgabe des Auftragsschritts geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-139">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="e0fb1-140">So erstellen Sie einen Auftragsschritt für die Analysis Services-Abfrage</span><span class="sxs-lookup"><span data-stu-id="e0fb1-140">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="e0fb1-141">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-141">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e0fb1-142">Erweitern Sie **SQL Server-Agent**, erstellen Sie einen neuen Auftrag, oder klicken Sie mit der rechten Maustaste auf einen vorhandenen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-142">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="e0fb1-143">Weitere Informationen zum Erstellen eines Auftrags finden Sie unter [Erstellen von Aufträgen](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-143">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="e0fb1-144">Klicken Sie im Dialogfeld **Auftragseigenschaften** auf die Seite **Schritte** und dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-144">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e0fb1-145">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen für den Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-145">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="e0fb1-146">Klicken Sie in der Liste **Typ** auf **SQL Server Analysis Services-Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-146">In the **Type** list, click **SQL Server Analysis Services Query**.</span></span>  
  
6.  <span data-ttu-id="e0fb1-147">Wählen Sie in der Liste **Ausführen als** einen Proxy aus, der für die Verwendung des Analysis Services-Abfragesubsystems definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-147">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Query subsystem.</span></span> <span data-ttu-id="e0fb1-148">Ein Benutzer, der Mitglied der festen Serverrolle **sysadmin** ist, kann zur Ausführung dieses Auftragsschritts auch **SQL-Agent-Dienstkonto** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-148">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="e0fb1-149">Wählen Sie einen Wert unter **Server** und **Datenbank** für die Ausführung des Auftragsschritts aus, oder geben Sie den Server- bzw. Datenbanknamen ein.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-149">Select the **Server** and the **Database** where the job step will run, or type the server or database name.</span></span>  
  
8.  <span data-ttu-id="e0fb1-150">Geben Sie im Feld **Befehl** die auszuführende Anweisung ein, oder klicken Sie auf **Öffnen** , um eine Anweisung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-150">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="e0fb1-151">Klicken Sie auf die Seite **Erweitert** , um die Optionen für diesen Auftragsschritt zu definieren. Legen Sie beispielsweise fest, welche Aktion der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausführen soll, wenn der Auftragsschritt erfolgreich ausgeführt wird oder fehlschlägt, wie viele Versuche zur Ausführung des Auftragsschritts unternommen werden sollen und wohin die Ausgabe des Auftragsschritts geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-151">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e0fb1-152">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0fb1-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="e0fb1-153">So erstellen Sie einen Auftragsschritt für den Analysis Services-Befehl</span><span class="sxs-lookup"><span data-stu-id="e0fb1-153">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="e0fb1-154">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e0fb1-155">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e0fb1-156">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-156">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses XMLA to create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database ',  
        @subsystem = N'ANALYSISCOMMAND',  
        @command = N' <Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
        <ParentObject>  
            <DatabaseID>AdventureWorks2012</DatabaseID>  
        </ParentObject>  
        <ObjectDefinition>  
            <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
                <ID>AdventureWorks2012</ID>  
                <Name>Adventure Works 2012</Name>  
                <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorks2012;Integrated Security=True</ConnectionString>  
                <ImpersonationInfo>  
                    <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
                </ImpersonationInfo>  
                <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
                <Timeout>PT0S</Timeout>  
            </DataSource>  
        </ObjectDefinition>  
    </Create>', ;  
    GO  
    ```  
  
 <span data-ttu-id="e0fb1-157">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-157">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="e0fb1-158">So erstellen Sie einen Auftragsschritt für die Analysis Services-Abfrage</span><span class="sxs-lookup"><span data-stu-id="e0fb1-158">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="e0fb1-159">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-159">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e0fb1-160">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-160">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e0fb1-161">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-161">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses MDX to return data  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Returns the Internet sales amount by state',  
        @subsystem = N'ANALYSISQUERY',  
        @command = N' SELECT  
       [Measures].[Internet Sales Amount] ON COLUMNS,  
       [Customer].[State-Province].Members ON ROWS  
    FROM [AdventureWorks2012]',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="e0fb1-162">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-162">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e0fb1-163">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e0fb1-163">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e0fb1-164">**So erstellen Sie einen PowerShell-Skript-Auftragsschritt**</span><span class="sxs-lookup"><span data-stu-id="e0fb1-164">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="e0fb1-165">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. XMLA oder MDX.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-165">Use the `JobStep` class by using a programming language that you choose, such as XMLA or MDX.</span></span> <span data-ttu-id="e0fb1-166">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="e0fb1-166">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
