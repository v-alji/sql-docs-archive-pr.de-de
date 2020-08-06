---
title: Erstellen eines Auftrags des SQL Server-Agents zum Archivieren von Datenbank-E-Mail-Nachrichten und Ereignisprotokollen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- archiving mail messages and attachments [SQL Server]
- removing mail messages and attachements
- Database Mail [SQL Server], archiving
- saving mail messages and attachments
ms.assetid: 8f8f0fba-f750-4533-9b76-a9cdbcdc3b14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b958b280c358a8aeb752600dee1c2aee31d14db1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616099"
---
# <a name="create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs"></a><span data-ttu-id="a61d7-102">Erstellen eines Auftrags des SQL Server-Agents zum Archivieren von Datenbank-E-Mail-Nachrichten und Ereignisprotokollen</span><span class="sxs-lookup"><span data-stu-id="a61d7-102">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>
  <span data-ttu-id="a61d7-103">Kopien von Datenbank-E-Mail-Nachrichten und deren Anlagen werden zusammen mit dem Datenbank-E-Mail-Ereignisprotokoll in **msdb** -Tabellen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a61d7-103">Copies of Database Mail messages and their attachments are retained in **msdb** tables along with the Database Mail event log.</span></span> <span data-ttu-id="a61d7-104">Sie sollten die Größe der Tabellen regelmäßig reduzieren und Nachrichten und Ereignisse archivieren, die nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a61d7-104">Periodically you might want to reduce the size of the tables and archive messages and events that are no longer needed.</span></span> <span data-ttu-id="a61d7-105">Die folgenden Prozeduren erstellen einen Auftrag des SQL Server-Agents, um diesen Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="a61d7-105">The following procedures create a SQL Server Agent job to automate the process.</span></span>  
  
-   <span data-ttu-id="a61d7-106">**Vorbereitungen:**  , [Voraussetzungen](#Prerequisites), [Empfehlungen](#Recommendations), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="a61d7-106">**Before you begin:**  , [Prerequisites](#Prerequisites), [Recommendations](#Recommendations), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="a61d7-107">**Archivieren von Datenbank-E-Mail-Nachrichten und -Protokollen mithilfe von:**  [SQL Server-Agent](#Process_Overview)</span><span class="sxs-lookup"><span data-stu-id="a61d7-107">**To Archive Database Mail messages and logs using :**  [SQL Server Agent](#Process_Overview)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a61d7-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a61d7-108">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a61d7-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a61d7-109">Prerequisites</span></span>  
 <span data-ttu-id="a61d7-110">Die neuen Tabellen zum Speichern der Archivdaten können sich in einer speziellen Archivdatenbank befinden.</span><span class="sxs-lookup"><span data-stu-id="a61d7-110">The new tables to store the archive data might be located in a special archive database.</span></span> <span data-ttu-id="a61d7-111">Alternativ können die Zeilen in eine Textdatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="a61d7-111">Alternatively the rows could be exported to a text file.</span></span>  
 
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a61d7-112">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="a61d7-112">Recommendations</span></span>  
 <span data-ttu-id="a61d7-113">Für die Verwendung in einer Produktionsumgebung sollten Sie eine zusätzliche Fehlerprüfung einfügen und eine E-Mail-Nachricht an Operatoren senden, wenn beim Auftrag ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="a61d7-113">In your production environment, you might want to add additional error checking and send an e-mail message to operators if the job fails.</span></span>  
  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a61d7-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a61d7-114">Permissions</span></span>  
 <span data-ttu-id="a61d7-115">Sie müssen Mitglied der festen Serverrolle **sysadmin** sein, um die in diesem Thema beschriebenen gespeicherten Prozeduren auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a61d7-115">You must be a member of the **sysadmin** fixed server role to execute the stored procedures described in this topic.</span></span>  
  
  
###  <a name="overview-of-the-process"></a><a name="Process_Overview"></a> <span data-ttu-id="a61d7-116">Übersicht über den Prozess</span><span class="sxs-lookup"><span data-stu-id="a61d7-116">Overview of the Process</span></span>  
  
-   <span data-ttu-id="a61d7-117">Die erste Prozedur erstellt den Auftrag "Datenbank-E-Mail archivieren" in den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="a61d7-117">The first procedure creates a job named Archive Database Mail with the following steps.</span></span>  
  
    1.  <span data-ttu-id="a61d7-118">Kopieren Sie alle Nachrichten aus den Datenbank-E-Mail-Tabellen in eine neue Tabelle, die nach dem vorhergehenden Monat im Format **DBMailArchive_** _Jahr_Monat_ benannt wird.</span><span class="sxs-lookup"><span data-stu-id="a61d7-118">Copy all messages from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_**_<year_month>_.</span></span>  
  
    2.  <span data-ttu-id="a61d7-119">Kopieren Sie die zu den im ersten Schritt kopierten Nachrichten gehörenden Anlagen aus den Datenbank-E-Mail-Tabellen in eine neue Tabelle, die nach dem vorhergehenden Monat im Format **DBMailArchive_Attachments_** _Jahr_Monat_ benannt wird.</span><span class="sxs-lookup"><span data-stu-id="a61d7-119">Copy the attachments related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Attachments_**_<year_month>_.</span></span>  
  
    3.  <span data-ttu-id="a61d7-120">Kopieren Sie die zu den im ersten Schritt kopierten Nachrichten gehörenden Ereignisse aus dem Datenbank-E-Mail-Ereignisprotokoll aus den Datenbank-E-Mail-Tabellen in eine neue Tabelle, die nach dem vorhergehenden Monat im Format **DBMailArchive_Log_** _Jahr_Monat_ benannt wird.</span><span class="sxs-lookup"><span data-stu-id="a61d7-120">Copy the events from the Database Mail event log that are related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Log_**_<year_month>_.</span></span>  
  
    4.  <span data-ttu-id="a61d7-121">Löschen Sie die Datensätze der übertragenen E-Mail-Elemente aus den Datenbank-E-Mail-Tabellen.</span><span class="sxs-lookup"><span data-stu-id="a61d7-121">Delete the records of the transferred mail items from the Database Mail tables.</span></span>  
  
    5.  <span data-ttu-id="a61d7-122">Löschen Sie die zu den übertragenen E-Mail-Elementen gehörenden Ereignisse aus dem Datenbank-E-Mail-Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a61d7-122">Delete the events related to the transferred mail items from the Database Mail event log.</span></span>  
  
-   <span data-ttu-id="a61d7-123">Planen Sie die regelmäßige Ausführung des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="a61d7-123">Schedule the job to run periodically.</span></span>  
 
  
## <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="a61d7-124">So erstellen Sie einen Auftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="a61d7-124">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="a61d7-125">Erweitern Sie im Objekt-Explorer den Knoten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent, klicken Sie mit der rechten Maustaste auf **Aufträge**, und klicken Sie dann auf **Neuer Auftrag**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-125">In Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, and then click **New Job**.</span></span>  
  
2.  <span data-ttu-id="a61d7-126">Geben Sie im Dialogfeld **Neuer Auftrag** im Feld **Name** den Namen **Datenbank-E-Mail archivieren**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-126">In the **New Job** dialog box, in the **Name** box, type **Archive Database Mail**.</span></span>  
  
3.  <span data-ttu-id="a61d7-127">Bestätigen Sie im Feld **Besitzer** , dass der Besitzer Mitglied der festen Serverrolle **sysadmin** ist.</span><span class="sxs-lookup"><span data-stu-id="a61d7-127">In the **Owner** box, confirm that the owner is a member of the **sysadmin** fixed server role.</span></span>  
  
4.  <span data-ttu-id="a61d7-128">Klicken Sie im Feld **Kategorie** auf **Datenbankwartung**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-128">In the **Category** box, click the **Database Maintenance**.</span></span>  
  
5.  <span data-ttu-id="a61d7-129">Geben Sie im Feld **Beschreibung** als Beschreibung **Datenbank-E-Mail-Nachrichten archivieren**ein, und klicken Sie dann auf **Schritte**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-129">In the **Description** box, type **Archive Database Mail messages**, and then click **Steps**.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-messages"></a><span data-ttu-id="a61d7-130">So erstellen Sie einen Schritt zum Archivieren der Datenbank-E-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a61d7-130">To create a step to archive the Database Mail messages</span></span>  
  
1.  <span data-ttu-id="a61d7-131">Klicken Sie auf der Seite **Schritte** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-131">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="a61d7-132">Geben Sie im Feld **Schrittname** den Namen **Datenbank-E-Mail-Elemente kopieren**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-132">In the **Step name** box, type **Copy Database Mail Items**.</span></span>  
  
3.  <span data-ttu-id="a61d7-133">Klicken Sie im Feld **Typ** auf **Transact-SQL-Skript (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="a61d7-133">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="a61d7-134">Klicken Sie im Feld **Datenbank** auf **msdb**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-134">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="a61d7-135">Geben Sie im Feld **Befehl** die folgende Anweisung zum Erstellen einer Tabelle ein, die nach dem vorhergehenden Monat benannt wird und Zeilen enthält, die aus der Zeit vor Beginn des aktuellen Monats stammen:</span><span class="sxs-lookup"><span data-stu-id="a61d7-135">In the **Command** box, type the following statement to create a table named after the previous month, containing rows older than the start of the current month:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_' + @LastMonth + '] FROM sysmail_allitems WHERE send_request_date < ''' + @CopyDate +'''';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="a61d7-136">Klicken Sie auf **OK** , um den Schritt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-136">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-attachments"></a><span data-ttu-id="a61d7-137">So erstellen Sie einen Schritt zum Archivieren der Datenbank-E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="a61d7-137">To create a step to archive the Database Mail attachments</span></span>  
  
1.  <span data-ttu-id="a61d7-138">Klicken Sie auf der Seite **Schritte** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-138">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="a61d7-139">Geben Sie im Feld **Schrittname** den Namen **Datenbank-E-Mail-Anlagen kopieren**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-139">In the **Step name** box, type **Copy Database Mail Attachments**.</span></span>  
  
3.  <span data-ttu-id="a61d7-140">Klicken Sie im Feld **Typ** auf **Transact-SQL-Skript (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="a61d7-140">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="a61d7-141">Klicken Sie im Feld **Datenbank** auf **msdb**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-141">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="a61d7-142">Geben Sie im Feld **Befehl** die folgende Anweisung zum Erstellen einer Tabelle mit Anlagen ein, die nach dem vorhergehenden Monat benannt wird und die Anlagen zu den im vorhergehenden Schritt übertragenen Nachrichten enthält:</span><span class="sxs-lookup"><span data-stu-id="a61d7-142">In the **Command** box, type the following statement to create an attachments table named after the previous month, containing the attachments that correspond to the messages transferred in the previous step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Attachments_' + @LastMonth + '] FROM sysmail_attachments   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="a61d7-143">Klicken Sie auf **OK** , um den Schritt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-143">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-log"></a><span data-ttu-id="a61d7-144">So erstellen Sie einen Schritt zum Archivieren des Datenbank-E-Mail-Protokolls</span><span class="sxs-lookup"><span data-stu-id="a61d7-144">To create a step to archive the Database Mail log</span></span>  
  
1.  <span data-ttu-id="a61d7-145">Klicken Sie auf der Seite **Schritte** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-145">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="a61d7-146">Geben Sie im Feld **Schrittname** den Namen **Datenbank-E-Mail-Protokoll kopieren**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-146">In the **Step name** box, type **Copy Database Mail Log**.</span></span>  
  
3.  <span data-ttu-id="a61d7-147">Klicken Sie im Feld **Typ** auf **Transact-SQL-Skript (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="a61d7-147">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="a61d7-148">Klicken Sie im Feld **Datenbank** auf **msdb**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-148">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="a61d7-149">Geben Sie im Feld **Befehl** die folgende Anweisung zum Erstellen einer Protokolltabelle ein, die nach dem vorhergehenden Monat benannt wird und die Protokolleinträge zu den in einem vorhergehenden Schritt übertragenen Nachrichten enthält:</span><span class="sxs-lookup"><span data-stu-id="a61d7-149">In the **Command** box, type the following statement to create a log table named after the previous month, containing the log entries that correspond to the messages transferred in the earlier step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Log_' + @LastMonth + '] FROM sysmail_Event_Log   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="a61d7-150">Klicken Sie auf **OK** , um den Schritt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-150">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-rows-from-database-mail"></a><span data-ttu-id="a61d7-151">So erstellen Sie einen Schritt zum Entfernen der archivierten Zeilen aus der Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="a61d7-151">To create a step to remove the archived rows from Database Mail</span></span>  
  
1.  <span data-ttu-id="a61d7-152">Klicken Sie auf der Seite **Schritte** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-152">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="a61d7-153">Geben Sie im Feld **Schrittname** den Namen **Zeilen aus Datenbank-E-Mail entfernen**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-153">In the **Step name** box, type **Remove rows from Database Mail**.</span></span>  
  
3.  <span data-ttu-id="a61d7-154">Klicken Sie im Feld **Typ** auf **Transact-SQL-Skript (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="a61d7-154">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="a61d7-155">Klicken Sie im Feld **Datenbank** auf **msdb**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-155">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="a61d7-156">Geben Sie im Feld **Befehl** die folgende Anweisung ein, um Zeilen aus den Datenbank-E-Mail-Tabellen zu entfernen, die älter als der aktuelle Monat sind:</span><span class="sxs-lookup"><span data-stu-id="a61d7-156">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail tables:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_mailitems_sp @sent_before = @CopyDate ;  
    ```  
  
6.  <span data-ttu-id="a61d7-157">Klicken Sie auf **OK** , um den Schritt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-157">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-items-from-database-mail-event-log"></a><span data-ttu-id="a61d7-158">So erstellen Sie einen Schritt zum Entfernen der archivierten Elemente aus dem Datenbank-E-Mail-Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="a61d7-158">To create a step to remove the archived items from Database Mail event log</span></span>  
  
1.  <span data-ttu-id="a61d7-159">Klicken Sie auf der Seite **Schritte** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-159">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="a61d7-160">Geben Sie im Feld **Schrittname** den Namen **Zeilen aus dem Datenbank-E-Mail-Protokoll entfernen**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-160">In the **Step Name** box type **Remove rows from Database Mail event log**.</span></span>  
  
3.  <span data-ttu-id="a61d7-161">Klicken Sie im Feld **Typ** auf **Transact-SQL-Skript (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="a61d7-161">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="a61d7-162">Geben Sie im Feld **Befehl** die folgende Anweisung ein, um Zeilen aus dem Datenbank-E-Mail-Ereignisprotokoll zu entfernen, die älter als der aktuelle Monat sind:</span><span class="sxs-lookup"><span data-stu-id="a61d7-162">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail event log:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_log_sp @logged_before = @CopyDate ;  
    ```  
  
5.  <span data-ttu-id="a61d7-163">Klicken Sie auf **OK** , um den Schritt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-163">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-schedule-the-job-to-run-periodically"></a><span data-ttu-id="a61d7-164">So planen Sie die regelmäßige Ausführung des Auftrags</span><span class="sxs-lookup"><span data-stu-id="a61d7-164">To schedule the job to run periodically</span></span>  
  
1.  <span data-ttu-id="a61d7-165">Klicken Sie im Dialogfeld **Neuer Auftrag** auf **Zeitpläne**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-165">In the **New Job** dialog box, click **Schedules**.</span></span>  
  
2.  <span data-ttu-id="a61d7-166">Klicken Sie auf der Seite **Zeitpläne** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-166">On the **Schedules** page, click **New**.</span></span>  
  
3.  <span data-ttu-id="a61d7-167">Geben Sie im Feld **Name** den Namen **Datenbank-E-Mail archivieren**ein.</span><span class="sxs-lookup"><span data-stu-id="a61d7-167">In the **Name** box, type **Archive Database Mail**.</span></span>  
  
4.  <span data-ttu-id="a61d7-168">Klicken Sie im Feld **Zeitplantyp** auf **Wiederholt**.</span><span class="sxs-lookup"><span data-stu-id="a61d7-168">In the **Schedule type** box, select **Recurring**.</span></span>  
  
5.  <span data-ttu-id="a61d7-169">Wählen Sie im Bereich **Häufigkeit** die Optionen zum regelmäßigen Ausführen des Auftrags, z. B. am ersten Tag eines jeden Monats, aus.</span><span class="sxs-lookup"><span data-stu-id="a61d7-169">In the **Frequency** area, select the options to run the job periodically, for example once every month.</span></span>  
  
6.  <span data-ttu-id="a61d7-170">Klicken Sie im Bereich **Häufigkeit pro Tag** auf **einmalig um \<time>** .</span><span class="sxs-lookup"><span data-stu-id="a61d7-170">In the **Daily frequency** area, select **Occurs once at \<time>**.</span></span>  
  
7.  <span data-ttu-id="a61d7-171">Überprüfen Sie, ob die anderen Optionen wie gewünscht konfiguriert sind, und klicken Sie dann auf **OK** , um den Zeitplan zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-171">Verify that the other options are configured as you wish, and then click **OK** to save the schedule.</span></span>  
  
8.  <span data-ttu-id="a61d7-172">Klicken Sie auf **OK** , um den Auftrag zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a61d7-172">Click **OK** to save the job.</span></span>  
  
  
  
  
