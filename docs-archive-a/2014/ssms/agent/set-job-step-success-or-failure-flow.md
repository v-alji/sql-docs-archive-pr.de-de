---
title: Festlegen der Vorgehensweise nach Erfolg oder Fehlschlagen eines Auftragsschrittes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, action flow logic
- successful jobs [SQL Server]
- failed jobs [SQL Server]
- jobs [SQL Server Agent], action flow logic
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: fddc5820676cb231b6f0cd5f7151e24d8eceaefa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726414"
---
# <a name="set-job-step-success-or-failure-flow"></a><span data-ttu-id="3ef40-102">Set Job Step Success or Failure Flow</span><span class="sxs-lookup"><span data-stu-id="3ef40-102">Set Job Step Success or Failure Flow</span></span>
  <span data-ttu-id="3ef40-103">Beim Erstellen von- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträgen können Sie angeben, welche Aktion durchgeführt werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] soll, wenn während der Auftragsausführung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3ef40-103">When creating [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take if a failure occurs during job execution.</span></span> <span data-ttu-id="3ef40-104">Bestimmen Sie die Aktion, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nach Erfolg oder Fehlschlagen eines Auftragsschrittes ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ef40-104">Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take upon the success or failure of each job step.</span></span> <span data-ttu-id="3ef40-105">Verwenden Sie anschließend die folgende Prozedur, um mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents die Logik der Vorgehensweise für die Auftragsschrittaktion zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3ef40-105">Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="3ef40-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3ef40-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3ef40-107">Security</span><span class="sxs-lookup"><span data-stu-id="3ef40-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3ef40-108">**So legen Sie die Vorgehensweise nach Erfolg oder einem Fehler eines Auftragsschritts fest, und zwar mit**</span><span class="sxs-lookup"><span data-stu-id="3ef40-108">**To set job step success or failure flow, using:**</span></span>  
  
     [<span data-ttu-id="3ef40-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ef40-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="3ef40-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ef40-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="3ef40-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="3ef40-111">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="3ef40-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3ef40-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3ef40-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3ef40-113">Security</span></span>  
 <span data-ttu-id="3ef40-114">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3ef40-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="3ef40-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ef40-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="3ef40-116">So legen Sie die Vorgehensweise nach Erfolg oder Fehlschlagen eines Auftragsschrittes fest</span><span class="sxs-lookup"><span data-stu-id="3ef40-116">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="3ef40-117">Erweitern Sie in **Objekt-Explorer**den Eintrag **SQL Server-Agent**, und erweitern Sie anschließend **Aufträge**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-117">In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
2.  <span data-ttu-id="3ef40-118">Klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-118">Right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3ef40-119">Wählen Sie die Seite **Schritte** aus, und klicken Sie erst auf einen Schritt und dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-119">Select the **Steps** page, click a step, and then click **Edit**.</span></span>  
  
4.  <span data-ttu-id="3ef40-120">Wählen Sie im Dialogfeld **Auftragsschritt-Eigenschaften** die Seite **Erweitert** aus.</span><span class="sxs-lookup"><span data-stu-id="3ef40-120">In the **Job Step Properties** dialog box, select the **Advanced** page.</span></span>  
  
5.  <span data-ttu-id="3ef40-121">Wählen Sie im Dialogfeld **Aktion bei Erfolg**auf die Aktion, die nach erfolgreicher Durchführung des Auftragsschrittes ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ef40-121">In the **On success action**list, click the action to perform if the job step completes successfully.</span></span>  
  
6.  <span data-ttu-id="3ef40-122">Geben Sie im Feld **Wiederholungsversuche** mit einer Zahl zwischen 0 und 9999 an, wie oft der Auftragsschritt wiederholt werden soll, bevor er als fehlgeschlagen gilt.</span><span class="sxs-lookup"><span data-stu-id="3ef40-122">In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed.</span></span> <span data-ttu-id="3ef40-123">Wenn Sie im Feld **Wiederholungsversuche** einen Wert größer 0 eingegeben haben, geben Sie im Feld **Wiederholungsintervall (Min)** die Anzahl von Minuten zwischen 1 und 9999 ein, die verstreichen müssen, bevor der Auftragsschritt erneut versucht wird.</span><span class="sxs-lookup"><span data-stu-id="3ef40-123">If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.</span></span>  
  
7.  <span data-ttu-id="3ef40-124">Klicken Sie in der Liste **Aktion bei Fehler** auf die Aktion, die nach einem fehlgeschlagenen Auftragsschritt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ef40-124">In the **On failure action** list, click the action to perform if the job step fails.</span></span>  
  
8.  <span data-ttu-id="3ef40-125">Wenn es sich bei dem Auftrag um ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript handelt, können Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="3ef40-125">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="3ef40-126">Geben Sie im Feld **Ausgabedatei** den Namen der Ausgabedatei ein, in die die Skriptausgabe geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ef40-126">In the **Output file** box, enter the name of an output file to which the script output will be written.</span></span> <span data-ttu-id="3ef40-127">Diese Datei wird standardmäßig bei jeder Ausführung des Auftragsschrittes überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ef40-127">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="3ef40-128">Wenn Sie nicht möchten, dass die Ausgabedatei überschrieben wird, aktivieren Sie **Ausgabe an vorhandene Datei anfügen**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-128">If you do not want the output file overwritten, check **Append output to existing file**.</span></span>  
  
    -   <span data-ttu-id="3ef40-129">Aktivieren Sie **In Tabelle protokollieren** , wenn der Auftragsschritt in einer Datenbanktabelle protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ef40-129">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="3ef40-130">Standardmäßig wird der Tabelleninhalt bei jeder Ausführung des Auftragsschrittes überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ef40-130">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="3ef40-131">Wenn der Tabelleninhalt nicht überschrieben werden soll, aktivieren Sie **Ausgabe an vorhandenen Eintrag in Tabelle anfügen**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-131">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="3ef40-132">Nachdem der Auftragsschritt ausgeführt wurde, können Sie den Inhalt dieser Tabelle anzeigen, indem Sie auf **Anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="3ef40-132">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="3ef40-133">Aktivieren Sie **Schrittausgabe in Verlauf einschließen** , wenn die Ausgabe in den Schrittverlauf eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ef40-133">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="3ef40-134">Die Ausgabe wird nur angezeigt, wenn keine Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="3ef40-134">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="3ef40-135">Es kann auch vorkommen, dass die Ausgabe abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="3ef40-135">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="3ef40-136">Wenn die Liste **Als Benutzer ausführen** verfügbar ist, wählen Sie daraus das Proxykonto mit den Benutzerinformationen aus, das für den Auftrag verwendet werden wird.</span><span class="sxs-lookup"><span data-stu-id="3ef40-136">If the **Run as user** list is available, select the proxy account with the credentials that the job will use.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="3ef40-137">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ef40-137">Using Transact-SQL</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="3ef40-138">So legen Sie die Vorgehensweise nach Erfolg oder Fehlschlagen eines Auftragsschrittes fest</span><span class="sxs-lookup"><span data-stu-id="3ef40-138">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="3ef40-139">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="3ef40-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ef40-140">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3ef40-141">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3ef40-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
 <span data-ttu-id="3ef40-142">Weitere Informationen finden Sie unter [sp_add_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3ef40-142">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="3ef40-143">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="3ef40-143">Using SQL Server Management Objects</span></span>  

### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="3ef40-144">So legen Sie die Vorgehensweise nach Erfolg oder Fehlschlagen eines Auftragsschrittes fest</span><span class="sxs-lookup"><span data-stu-id="3ef40-144">To set job step success or failure flow</span></span>
  
 <span data-ttu-id="3ef40-145">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef40-145">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="3ef40-146">Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="3ef40-146">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
