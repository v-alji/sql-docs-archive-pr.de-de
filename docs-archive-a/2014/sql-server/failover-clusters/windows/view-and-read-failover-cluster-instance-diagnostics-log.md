---
title: Anzeigen und Lesen des Failoverclusterinstanz-Diagnoseprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 68074bd5-be9d-4487-a320-5b51ef8e2b2d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 774dc4ec4a02c72420d004909cb7e6ee1b31f3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617557"
---
# <a name="view-and-read-failover-cluster-instance-diagnostics-log"></a><span data-ttu-id="3cbdd-102">Anzeigen und Lesen des Failoverclusterinstanz-Diagnoseprotokolls</span><span class="sxs-lookup"><span data-stu-id="3cbdd-102">View and Read Failover Cluster Instance Diagnostics Log</span></span>
  <span data-ttu-id="3cbdd-103">Alle kritischen Fehler und Warnungsereignisse für die Ressourcen-DLL von SQL Server werden in das Windows-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-103">All critical errors and warning events for the SQL Server Resource DLL are written to the Windows event log.</span></span> <span data-ttu-id="3cbdd-104">Ein Ausführungsprotokoll mit für SQL Server spezifischen Diagnoseinformationen wird von der gespeicherten Systemprozedur [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) erfasst und in die Protokolldateien der SQL Server-Failoverclusterdiagnose (auch als *SQLDIAG*-Protokolle bezeichnet) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-104">A running log of the diagnostic information specific to SQL Server is captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) system stored procedure and is written to the SQL Server failover cluster diagnostics (also known as the *SQLDIAG* logs) log files.</span></span>  
  
-   <span data-ttu-id="3cbdd-105">**Vorbereitungen:**  [Empfehlungen](#Recommendations), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="3cbdd-105">**Before you begin:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3cbdd-106">**Anzeigen des Diagnoseprotokolls mit:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="3cbdd-106">**To View the Diagnostic Log, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="3cbdd-107">**Konfigurieren der Diagnoseprotokolleinstellungen mit:** [Transact-SQL](#TsqlConfigure)</span><span class="sxs-lookup"><span data-stu-id="3cbdd-107">**To Configure Diagnostic Log settings, using:** [Transact-SQL](#TsqlConfigure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3cbdd-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3cbdd-108">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3cbdd-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="3cbdd-109">Recommendations</span></span>  
 <span data-ttu-id="3cbdd-110">Standardmäßig werden die SQLdiag in einem lokalen Protokoll Ordner des SQL Server Instanzverzeichnisses gespeichert, z. b. "c\programme\microsoft SQL server\mssql12. \<InstanceName> ". \MSSQL\LOG "des besitzenden Knotens der AlwaysOn-Failoverclusterinstanz (FCI).</span><span class="sxs-lookup"><span data-stu-id="3cbdd-110">By default, the SQLDIAG are stored under a local LOG folder of the SQL Server instance directory, for example, 'C\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\LOG' of the owning node of the AlwaysOn Failover Cluster Instance (FCI).</span></span> <span data-ttu-id="3cbdd-111">Die Größe jeder SQLDIAG-Protokolldatei wird auf 100 MB begrenzt.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-111">The size of each SQLDIAG log file is fixed at 100 MB.</span></span> <span data-ttu-id="3cbdd-112">Zehn dieser Protokolldateien werden auf dem Computer gespeichert, bevor sie für neue Protokolle wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-112">Ten such log files are stored on the computer before they are recycled for new logs.</span></span>  
  
 <span data-ttu-id="3cbdd-113">Die Protokolle verwenden das Dateiformat für erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-113">The logs use the extended events file format.</span></span> <span data-ttu-id="3cbdd-114">Mit der Systemfunktion **sys.fn_xe_file_target_read_file** können Sie die Dateien lesen, die durch erweiterte Ereignisse erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-114">The **sys.fn_xe_file_target_read_file** system function can be used to read the files that are created by Extended Events.</span></span> <span data-ttu-id="3cbdd-115">Pro Zeile wird ein Ereignis im XML-Format zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-115">One event, in XML format, is returned per row.</span></span> <span data-ttu-id="3cbdd-116">Fragen Sie die Systemsicht ab, um die XML-Daten als Resultset zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-116">Query the system view to parse the XML data as a result-set.</span></span> <span data-ttu-id="3cbdd-117">Weitere Informationen finden Sie unter [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cbdd-117">For more information, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3cbdd-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3cbdd-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3cbdd-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3cbdd-119">Permissions</span></span>  
 <span data-ttu-id="3cbdd-120">Die VIEW SERVER STATE-Berechtigung ist erforderlich, um **fn_xe_file_target_read_file**auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-120">VIEW SERVER STATE permission is needed to run **fn_xe_file_target_read_file**.</span></span>  
  
 <span data-ttu-id="3cbdd-121">Öffnen von SQL Server Management Studio als Administrator</span><span class="sxs-lookup"><span data-stu-id="3cbdd-121">Open SQL Server Management Studio as Administrator</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3cbdd-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cbdd-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3cbdd-123">**So zeigen Sie die Diagnoseprotokolldateien an:**</span><span class="sxs-lookup"><span data-stu-id="3cbdd-123">**To view the Diagnostic log files:**</span></span>  
  
1.  <span data-ttu-id="3cbdd-124">Wählen Sie im Menü **Datei** die Option **Öffnen**, **Datei**, und wählen Sie die anzuzeigende Diagnoseprotokolldatei an.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-124">From the **File** menu, select **Open**, **File**, and choose the diagnostic log file you want to view.</span></span>  
  
2.  <span data-ttu-id="3cbdd-125">Die Ereignisse werden als Zeilen im rechten Bereich angezeigt. Standardmäßig werden nur die Spalten **name**und **timestamp** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-125">The events are displayed as rows in the right pane, and by default **name**, and **timestamp** are the only two columns displayed.</span></span>  
  
     <span data-ttu-id="3cbdd-126">Dadurch wird außerdem das Menü **ExtendedEvents** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-126">This also activates the **ExtendedEvents** menu.</span></span>  
  
3.  <span data-ttu-id="3cbdd-127">Rufen Sie zum Anzeigen weiterer Spalten das Menü **ExtendedEvents** auf, und wählen Sie **Spalten auswählen**.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-127">To see more columns, go the **ExtendedEvents** menu, and select **Choose Columns**.</span></span>  
  
     <span data-ttu-id="3cbdd-128">Ein Dialogfeld mit den verfügbaren Spalten wird angezeigt, in dem Sie die anzuzeigenden Spalten auswählen können.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-128">A dialog box opens with the available columns allowing you to select the columns for display.</span></span>  
  
4.  <span data-ttu-id="3cbdd-129">Sie können die Ereignisdaten mithilfe des Menüs **ExtendedEvents** und der Option **Filter** filtern und sortieren.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-129">You can filter, and sort the event data using the **ExtendedEvents** menu and selecting the **Filter** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3cbdd-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cbdd-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="3cbdd-131">**So zeigen Sie die Diagnoseprotokolldateien an:**</span><span class="sxs-lookup"><span data-stu-id="3cbdd-131">**To view the Diagnostic log files:**</span></span>  
  
 <span data-ttu-id="3cbdd-132">Um alle Protokollelemente in der SQLDIAG-Protokolldatei anzuzeigen, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="3cbdd-132">To view all the log items in the SQLDIAG log file, use the following query:</span></span>  
  
```  
SELECT  
xml_data.value('(event/@name)[1]','varchar(max)') AS 'Name'  
,xml_data.value('(event/@package)[1]','varchar(max)') AS 'Package'  
,xml_data.value('(event/@timestamp)[1]','datetime') AS 'Time'  
,xml_data.value('(event/data[@name=''state'']/value)[1]','int') AS 'State'  
,xml_data.value('(event/data[@name=''state_desc'']/text)[1]','varchar(max)') AS 'State Description'  
,xml_data.value('(event/data[@name=''failure_condition_level'']/value)[1]','int') AS 'Failure Conditions'  
,xml_data.value('(event/data[@name=''node_name'']/value)[1]','varchar(max)') AS 'Node_Name'  
,xml_data.value('(event/data[@name=''instancename'']/value)[1]','varchar(max)') AS 'Instance Name'  
,xml_data.value('(event/data[@name=''creation time'']/value)[1]','datetime') AS 'Creation Time'  
,xml_data.value('(event/data[@name=''component'']/value)[1]','varchar(max)') AS 'Component'  
,xml_data.value('(event/data[@name=''data'']/value)[1]','varchar(max)') AS 'Data'  
,xml_data.value('(event/data[@name=''info'']/value)[1]','varchar(max)') AS 'Info'  
FROM  
 ( SELECT object_name AS 'event'  
  ,CONVERT(xml,event_data) AS 'xml_data'  
  FROM sys.fn_xe_file_target_read_file('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log\SQLNODE1_MSSQLSERVER_SQLDIAG_0_129936003752530000.xel',NULL,NULL,NULL)   
)   
AS XEventData  
ORDER BY Time;  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3cbdd-133">Sie können die Ergebnisse nach bestimmten Komponenten oder Status filtern, indem Sie die WHERE-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-133">You can filter the results for specific components or state using the WHERE clause.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlConfigure"></a> <span data-ttu-id="3cbdd-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cbdd-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="3cbdd-135">**So konfigurieren Sie die Diagnoseprotokolleigenschaften**</span><span class="sxs-lookup"><span data-stu-id="3cbdd-135">**To configure the Diagnostic Log Properties**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3cbdd-136">Ein Beispiel für diese Prozedur finden Sie weiter unten in diesem Abschnitt unter [Beispiel (Transact-SQL)](#TsqlExample).</span><span class="sxs-lookup"><span data-stu-id="3cbdd-136">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
 <span data-ttu-id="3cbdd-137">Mithilfe der DDL-Anweisung (Data Definition Language, Datendefinitionssprache) `ALTER SERVER CONFIGURATION` können Sie die Protokollierung von Diagnosedaten starten oder Abbrechen, die von der [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) -Prozedur erfasst wurden, und SQLdiag-Protokoll Konfigurationsparameter festlegen, wie z. b. die Anzahl der Protokolldatei-Rollover, die Protokolldatei Größe</span><span class="sxs-lookup"><span data-stu-id="3cbdd-137">Using the Data Definition Language (DDL) statement, `ALTER SERVER CONFIGURATION`, you can start or stop logging diagnostic data captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) procedure, and set SQLDIAG log configuration parameters such as the log file rollover count, log file size, and file location.</span></span> <span data-ttu-id="3cbdd-138">Einzelheiten zur Syntax finden Sie unter [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span><span class="sxs-lookup"><span data-stu-id="3cbdd-138">For syntax details, see [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="ConfigTsqlExample"></a> <span data-ttu-id="3cbdd-139">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3cbdd-139">Examples (Transact-SQL)</span></span>  
  
####  <a name="setting-diagnostic-log-options"></a><a name="TsqlExample"></a> <span data-ttu-id="3cbdd-140">Setting diagnostic log options</span><span class="sxs-lookup"><span data-stu-id="3cbdd-140">Setting diagnostic log options</span></span>  
 <span data-ttu-id="3cbdd-141">Die Beispiele in diesem Abschnitt veranschaulichen, wie die Werte für die Diagnoseprotokolloption festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-141">The examples in this section show how to set the values for the diagnostic log option.</span></span>  
  
##### <a name="a-starting-diagnostic-logging"></a><span data-ttu-id="3cbdd-142">A.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-142">A.</span></span> <span data-ttu-id="3cbdd-143">Starten der Diagnoseprotokollierung</span><span class="sxs-lookup"><span data-stu-id="3cbdd-143">Starting diagnostic logging</span></span>  
 <span data-ttu-id="3cbdd-144">Im folgenden Beispiel wird die Protokollierung von Diagnosedaten gestartet.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-144">The following example starts the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
##### <a name="b-stopping-diagnostic-logging"></a><span data-ttu-id="3cbdd-145">B.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-145">B.</span></span> <span data-ttu-id="3cbdd-146">Beenden der Diagnoseprotokollierung</span><span class="sxs-lookup"><span data-stu-id="3cbdd-146">Stopping diagnostic logging</span></span>  
 <span data-ttu-id="3cbdd-147">Im folgenden Beispiel wird die Protokollierung von Diagnosedaten beendet.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-147">The following example stops the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
##### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a><span data-ttu-id="3cbdd-148">C.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-148">C.</span></span> <span data-ttu-id="3cbdd-149">Angeben des Speicherorts für die Diagnoseprotokolle</span><span class="sxs-lookup"><span data-stu-id="3cbdd-149">Specifying the location of the diagnostic logs</span></span>  
 <span data-ttu-id="3cbdd-150">Im folgenden Beispiel wird der Speicherort für die Diagnoseprotokolle auf den angegebenen Dateipfad festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-150">The following example sets the location of the diagnostic logs to the specified file path.</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
##### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a><span data-ttu-id="3cbdd-151">D:</span><span class="sxs-lookup"><span data-stu-id="3cbdd-151">D.</span></span> <span data-ttu-id="3cbdd-152">Angeben der maximalen Größe jedes Diagnoseprotokolls</span><span class="sxs-lookup"><span data-stu-id="3cbdd-152">Specifying the maximum size of each diagnostic log</span></span>  
 <span data-ttu-id="3cbdd-153">Im folgenden Beispiel wird die maximale Größe jedes Diagnoseprotokolls auf 10 Megabytes festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3cbdd-153">The following example set the maximum size of each diagnostic log to 10 megabytes.</span></span>  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cbdd-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cbdd-154">See Also</span></span>  
 [<span data-ttu-id="3cbdd-155">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="3cbdd-155">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
  
  
