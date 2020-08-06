---
title: Konvertieren eines vorhandenen SQL-Ablaufverfolgungsskripts in eine Sitzung für erweiterte Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, convert script to extended events
- extended events [SQL Server], convert SQL Trace script
ms.assetid: 4c8f29e6-0a37-490f-88b3-33493871b3f9
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e5b0d0e20fbf4fd55398c130abf6cfff128ebe8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620402"
---
# <a name="convert-an-existing-sql-trace-script-to-an-extended-events-session"></a><span data-ttu-id="95f98-102">Konvertieren eines vorhandenen SQL-Ablaufverfolgungsskripts in eine Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="95f98-102">Convert an Existing SQL Trace Script to an Extended Events Session</span></span>
  <span data-ttu-id="95f98-103">Wenn Sie ein vorhandenes SQL-Ablaufverfolgungsskript haben, das Sie in eine Sitzung für erweiterte Ereignisse konvertieren möchten, können Sie die Vorgehensweisen in diesem Thema verwenden, um eine entsprechende Sitzung für erweiterte Ereignisse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="95f98-103">If you have an existing SQL Trace script that you want to convert to an Extended Events session, you can use the procedures in this topic to create an equivalent Extended Events session.</span></span> <span data-ttu-id="95f98-104">Mit den Informationen in den Systemtabellen „trace_xe_action_map“ und „trace_xe_event_map“ können Sie die Informationen sammeln, die für die Konvertierung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="95f98-104">By using the information in the trace_xe_action_map and trace_xe_event_map system tables, you can collect the information that you must have to do the conversion.</span></span>  
  
 <span data-ttu-id="95f98-105">Die Schritte umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="95f98-105">The steps include the following:</span></span>  
  
1.  <span data-ttu-id="95f98-106">Führen Sie das vorhandene Skript aus, um eine SQL-Ablaufverfolgungssitzung zu erstellen, und rufen Sie dann die ID der Ablaufverfolgung ab.</span><span class="sxs-lookup"><span data-stu-id="95f98-106">Execute the existing script to create a SQL Trace session, and then obtain the ID of the trace.</span></span>  
  
2.  <span data-ttu-id="95f98-107">Führen Sie eine Abfrage aus, die die Funktion „fn_trace_geteventinfo“ verwendet, um die entsprechenden Ereignisse in „Erweiterte Ereignisse“ und die Aktionen für die einzelnen Ereignisklassen der SQL-Ablaufverfolgung sowie ihre zugeordneten Spalten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="95f98-107">Run a query that uses the fn_trace_geteventinfo function to find the equivalent Extended Events events and actions for each SQL Trace event class and its associated columns.</span></span>  
  
3.  <span data-ttu-id="95f98-108">Verwenden Sie die Funktion „fn_trace_getfilterinfo“, um die zu verwendenden Filter und die entsprechenden Aktionen für „Erweiterte Ereignisse“ aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="95f98-108">Use the fn_trace_getfilterinfo function to list the filters and the equivalent Extended Events actions to use.</span></span>  
  
4.  <span data-ttu-id="95f98-109">Erstellen Sie mithilfe der entsprechenden Ereignisse, Aktionen und Prädikate (Filter) für erweiterte Ereignisse manuell eine Sitzung für erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="95f98-109">Manually create an Extended Events session, using the equivalent Extended Events events, actions, and predicates (filters).</span></span>  
  
## <a name="to-obtain-the-trace-id"></a><span data-ttu-id="95f98-110">So rufen Sie die Ablaufverfolgungs-ID ab</span><span class="sxs-lookup"><span data-stu-id="95f98-110">To obtain the trace ID</span></span>  
  
1.  <span data-ttu-id="95f98-111">Öffnen Sie das SQL-Ablaufverfolgungsskript im Abfrage-Editor, und führen Sie dann das Skript aus, um die Ablaufverfolgungssitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="95f98-111">Open the SQL Trace script in Query Editor, and then execute the script to create the trace session.</span></span> <span data-ttu-id="95f98-112">Die Ablaufverfolgungssitzung muss nicht ausgeführt werden, um diese Vorgehensweise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="95f98-112">Note that the trace session does not need to be running to complete this procedure.</span></span>  
  
2.  <span data-ttu-id="95f98-113">Rufen Sie die ID der Ablaufverfolgung ab.</span><span class="sxs-lookup"><span data-stu-id="95f98-113">Obtain the ID of the trace.</span></span> <span data-ttu-id="95f98-114">Verwenden Sie hierzu die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="95f98-114">To do this, use the following query:</span></span>  
  
    ```sql
    SELECT * FROM sys.traces;  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="95f98-115">Die Ablaufverfolgungs-ID 1 gibt in der Regel die Standardablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="95f98-115">Trace ID 1 typically indicates the default trace.</span></span>  
  
## <a name="to-determine-the-extended-events-equivalents"></a><span data-ttu-id="95f98-116">So bestimmen Sie die Entsprechungen für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="95f98-116">To determine the Extended Events equivalents</span></span>  
  
1.  <span data-ttu-id="95f98-117">Führen Sie die folgende Abfrage aus, wobei *trace_id* auf den Wert der Ablaufverfolgungs-ID festgelegt wird, die Sie in der vorherigen Prozedur abgerufen haben, um die entsprechenden Ereignisse und Aktionen für „Erweiterte Ereignisse“ zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="95f98-117">To determine the equivalent Extended Events events and actions, run the following query, where *trace_id* is set to the value of the trace ID that you obtained in the previous procedure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95f98-118">In diesem Beispiel wird die Ablaufverfolgungs-ID für die Standardablaufverfolgung (1) verwendet.</span><span class="sxs-lookup"><span data-stu-id="95f98-118">In this example, the trace ID for the default trace (1) is used.</span></span>  
  
    ```sql
    USE MASTER;  
    GO  
    DECLARE @trace_id int;  
    SET @trace_id = 1;  
    SELECT DISTINCT el.eventid, em.package_name, em.xe_event_name AS 'event'  
       , el.columnid, ec.xe_action_name AS 'action'  
    FROM (sys.fn_trace_geteventinfo(@trace_id) AS el  
       LEFT OUTER JOIN sys.trace_xe_event_map AS em  
          ON el.eventid = em.trace_event_id)  
    LEFT OUTER JOIN sys.trace_xe_action_map AS ec  
       ON el.columnid = ec.trace_column_id  
    WHERE em.xe_event_name IS NOT NULL AND ec.xe_action_name IS NOT NULL;  
    ```  
  
     <span data-ttu-id="95f98-119">Die entsprechende Ereignis-ID für erweiterte Ereignisse, der Paketname, der Ereignisname, die Spalten-ID und der Aktionsname werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95f98-119">The equivalent Extended Events event ID, package name, event name, column ID and action name are returned.</span></span> <span data-ttu-id="95f98-120">Diese Ausgabe verwenden Sie in der Vorgehensweise "So erstellen Sie die Sitzung für erweiterte Ereignisse" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="95f98-120">You will use this output in the procedure "To create the Extended Events session" later in this topic.</span></span>  
  
     <span data-ttu-id="95f98-121">In einigen Fällen wird einem Ereignisdatenfeld, das standardmäßig im Ereignis für erweiterte Ereignisse enthalten ist, die gefilterte Spalte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="95f98-121">In some cases, the filtered column maps to an event data field that is included by default in the Extended Events event.</span></span> <span data-ttu-id="95f98-122">Daher ist die Spalte "Extended_Events_action_name" NULL.</span><span class="sxs-lookup"><span data-stu-id="95f98-122">Therefore, the "Extended_Events_action_name" column will be NULL.</span></span> <span data-ttu-id="95f98-123">Wenn dies auftritt, müssen Sie wie folgt vorgehen, zu bestimmen, welches Datenfeld der gefilterten Spalte entspricht:</span><span class="sxs-lookup"><span data-stu-id="95f98-123">If this occurs, you must do the following to determine which data field is equivalent to the filtered column:</span></span>  
  
    1.  <span data-ttu-id="95f98-124">Identifizieren Sie für die Aktionen, die NULL zurückgeben, welche SQL-Ablaufverfolgungs-Ereignisklassen in dem Skript die gefilterte Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="95f98-124">For the actions that return NULL, identify which SQL Trace event classes in the script contain the column that is being filtered.</span></span>  
  
         <span data-ttu-id="95f98-125">Möglicherweise haben Sie z.B. die Ereignisklasse „SP:StmtCompleted“ verwendet und einen Filter für den Namen der Ablaufverfolgungsspalte „Dauer“ (Ereignisklassen-ID 45 und Spalten-ID 13 der SQL-Ablaufverfolgung) angegeben.</span><span class="sxs-lookup"><span data-stu-id="95f98-125">For example, you may have used the SP:StmtCompleted event class, and specified a filter on the Duration trace column name (SQL Trace event class ID 45, and SQL Trace column ID 13).</span></span> <span data-ttu-id="95f98-126">In diesem Fall wird der Aktionsname in den Abfrageergebnissen als NULL angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95f98-126">In this case, the action name will appear as NULL in the query results.</span></span>  
  
    2.  <span data-ttu-id="95f98-127">Suchen Sie für jede SQL-Ablaufverfolgungs-Ereignisklasse, die Sie im vorherigen Schritt identifiziert haben, den entsprechenden Namen des Ereignisses für erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="95f98-127">For each SQL Trace event class that you identified in the previous step, find the equivalent Extended Events event name.</span></span> <span data-ttu-id="95f98-128">(Wenn Sie sich bzgl. des entsprechenden Ereignisnamens unsicher sind, verwenden Sie die Abfrage aus dem Thema [Anzeigen der Entsprechungen von erweiterten Ereignissen für SQL-Ablaufverfolgungsklassen](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span><span class="sxs-lookup"><span data-stu-id="95f98-128">(If you are not sure of the equivalent event name, use the query in the topic [View the Extended Events Equivalents to SQL Trace Event Classes](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span></span>  
  
    3.  <span data-ttu-id="95f98-129">Verwenden Sie die folgende Abfrage, um die richtigen Datenfelder zu identifizieren, die für die Ereignisse verwendet werden sollen, die Sie im vorherigen Schritt identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="95f98-129">Use the following query to identify the correct data fields to use for the events that you identified in the previous step.</span></span> <span data-ttu-id="95f98-130">Die Abfrage zeigt die Datenfelder für erweiterte Ereignisse in der "event_field"-Spalte an.</span><span class="sxs-lookup"><span data-stu-id="95f98-130">The query shows the Extended Events data fields in the "event_field" column.</span></span> <span data-ttu-id="95f98-131">Ersetzen Sie in der Abfrage *<Ereignisname>* durch den Namen eines Ereignisses, das Sie im vorherigen Schritt angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="95f98-131">In the query, replace *<event_name>* with the name of an event that you specified in the previous step.</span></span>  
  
        ```sql
        SELECT xp.name package_name, xe.name event_name  
           ,xc.name event_field, xc.description  
        FROM sys.trace_xe_event_map AS em  
        INNER JOIN sys.dm_xe_objects AS xe  
           ON em.xe_event_name = xe.name  
        INNER JOIN sys.dm_xe_packages AS xp  
           ON xe.package_guid = xp.guid AND em.package_name = xp.name  
        INNER JOIN sys.dm_xe_object_columns AS xc  
           ON xe.name = xc.object_name  
        WHERE xe.object_type = 'event' AND xc.column_type <> 'readonly'  
           AND em.xe_event_name = '<event_name>';  
        ```  
  
         <span data-ttu-id="95f98-132">Beispielsweise ist die Ereignisklasse „SP:StmtCompleted“ dem erweiterten Ereignis „sp_statement_completed“ zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="95f98-132">For example, the SP:StmtCompleted event class maps to the sp_statement_completed Extended Events event.</span></span> <span data-ttu-id="95f98-133">Wenn Sie „sp_statement_completed“ in der Abfrage als Ereignisnamen angeben, werden in der Spalte „event_field“ die Felder angezeigt, die standardmäßig in dem Ereignis enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="95f98-133">If you specify sp_statement_completed as the event name in the query, the "event_field" column shows the fields that are included by default with the event.</span></span> <span data-ttu-id="95f98-134">Wenn Sie sich die Felder ansehen, werden Sie sehen, dass es ein Feld "duration" gibt.</span><span class="sxs-lookup"><span data-stu-id="95f98-134">Looking at the fields, you can see that there is a "duration" field.</span></span> <span data-ttu-id="95f98-135">Um den Filter in der entsprechenden Sitzung für erweiterte Ereignisse zu erstellen, würden Sie ein Prädikat, z. B. "WHERE duration > 0" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95f98-135">To create the filter in the equivalent Extended Events session, you would add a predicate such as "WHERE duration > 0".</span></span> <span data-ttu-id="95f98-136">Ein Beispiel finden Sie in der Vorgehensweise "So erstellen Sie die Sitzung für erweiterte Ereignisse" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="95f98-136">For an example, see the "To create the Extended Events session" procedure in this topic.</span></span>  
  
## <a name="to-create-the-extended-events-session"></a><span data-ttu-id="95f98-137">So erstellen Sie die Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="95f98-137">To create the Extended Events session</span></span>  
 <span data-ttu-id="95f98-138">Verwenden Sie den Abfrage-Editor, um die Sitzung für erweiterte Ereignisse zu erstellen und die Ausgabe in eine Dateiziel zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="95f98-138">Use Query Editor to create the Extended Events session, and to write the output to a file target.</span></span> <span data-ttu-id="95f98-139">Die folgenden Schritte beschreiben eine einzelne Abfrage, mit Erklärungen, um Ihnen zu zeigen, wie die Abfrage erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="95f98-139">The following steps describe a single query, with explanations to show you how to build the query.</span></span> <span data-ttu-id="95f98-140">Die vollständige Beispielabfrage finden Sie im Abschnitt "Beispiel" dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="95f98-140">For the full query example, see the "Example" section of this topic.</span></span>  
  
1.  <span data-ttu-id="95f98-141">Fügen Sie Anweisungen hinzu, um die Ereignissitzung zu erstellen, und ersetzten Sie*Sitzungsname* durch den Namen, den Sie für die Sitzung für erweiterte Ereignisse verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="95f98-141">Add statements to create the event session, replacing s*ession_name* with the name that you want to use for the Extended Events session.</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [Session_Name] ON SERVER;  
    CREATE EVENT SESSION [Session_Name]  
    ON SERVER;  
    ```  
  
2.  <span data-ttu-id="95f98-142">Fügen Sie die Ereignisse und Aktionen für erweiterte Ereignisse hinzu, die in der Vorgehensweise "So bestimmen Sie die Entsprechungen für erweiterte Ereignisse" als Ausgabe zurückgegeben wurden, und fügen Sie die Prädikate (Filter) hinzu, die Sie in der Vorgehensweise "So bestimmen Sie die Filter, die im Skript verwendet werden" identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="95f98-142">Add the Extended Events events and actions that were returned as output in the procedure "Determine the Extended Events equivalents", and add the predicates (filters) that you identified in the procedure "To determine the filters that were used in the script".</span></span>  
  
     <span data-ttu-id="95f98-143">Im folgenden Beispiel wird ein SQL-Ablaufverfolgungsskript, das die Ereignisklassen „SQL:StmtStarting“ und „SP:StmtCompleted“ einschließt, mit Filtern für die Sitzungs-ID und die Dauer verwendet.</span><span class="sxs-lookup"><span data-stu-id="95f98-143">The following example uses a SQL Trace script that includes the SQL:StmtStarting and SP:StmtCompleted event classes, with filters for session ID and duration.</span></span> <span data-ttu-id="95f98-144">Die Beispielausgabe für die Abfrage in der Vorgehensweise "So bestimmen Sie die Entsprechungen für erweiterte Ereignisse" gab das folgende Resultset zurück:</span><span class="sxs-lookup"><span data-stu-id="95f98-144">Sample output for the query in the "Determine the Extended Events equivalents" procedure returned the following result set:</span></span>  
  
    ```  
    Eventid  package_name  event                   columnid  action  
    44       sqlserver     sp_statement_starting   6         nt_username  
    44       sqlserver     sp_statement_starting   9         client_pid  
    44       sqlserver     sp_statement_starting   10        client_app_name  
    44       sqlserver     sp_statement_starting   11        server_principal_name  
    44       sqlserver     sp_statement_starting   12        session_id  
    45       sqlserver     sp_statement_completed  6         nt_username  
    45       sqlserver     sp_statement_completed  9         client_pid  
    45       sqlserver     sp_statement_completed  10        client_app_name  
    45       sqlserver     sp_statement_completed  11        server_principal_name  
    45       sqlserver     sp_statement_completed  12        session_id  
    ```  
  
     <span data-ttu-id="95f98-145">Die Ereignisse „sqlserver.sp_statement_starting“ und „sqlserver.sp_statement_completed“ werden mit einer Liste von Aktionen hinzugefügt, um dies in die Entsprechung für erweiterte Ereignisse konvertieren.</span><span class="sxs-lookup"><span data-stu-id="95f98-145">To convert this to the Extended Events equivalent, the sqlserver.sp_statement_starting and the sqlserver.sp_statement_completed events are added, with a list of actions.</span></span> <span data-ttu-id="95f98-146">Prädikatanweisungen sind als WHERE-Klauseln eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="95f98-146">Predicate statements are included as WHERE clauses.</span></span>  
  
    ```sql
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       )  
    ```  
  
3.  <span data-ttu-id="95f98-147">Fügen Sie das asynchrone Dateiziel hinzu, und ersetzen Sie dabei die Dateipfade durch den Speicherort, an dem Sie die Ausgabe speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="95f98-147">Add the asynchronous file target, replacing the file paths with the location where you want to save the output.</span></span> <span data-ttu-id="95f98-148">Wenn Sie das Dateiziel angeben, müssen Sie einen Dateipfad für die Protokolldatei sowie die Metadatendatei angeben.</span><span class="sxs-lookup"><span data-stu-id="95f98-148">When specifying the file target, you must include a log file and metadata file path file.</span></span>  
  
    ```sql
    ADD TARGET package0.asynchronous_file_target(  
       SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="to-view-the-results"></a><span data-ttu-id="95f98-149">So zeigen Sie die Ergebnisse an</span><span class="sxs-lookup"><span data-stu-id="95f98-149">To view the results</span></span>  
  
1.  <span data-ttu-id="95f98-150">Sie können die Funktion „sys.fn_xe_file_target_read_file“ verwenden, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="95f98-150">You can use the sys.fn_xe_file_target_read_file function to view the output.</span></span> <span data-ttu-id="95f98-151">Führen Sie hierzu die folgende Abfrage aus, und ersetzen Sie dabei die Dateipfade durch die angegebenen Pfade:</span><span class="sxs-lookup"><span data-stu-id="95f98-151">To do this, run the following query, replacing the file paths with the paths that you specified:</span></span>  
  
    ```sql
    SELECT *, CAST(event_data as XML) AS 'event_data_XML'  
    FROM sys.fn_xe_file_target_read_file('c:\temp\ExtendedEventsStoredProcs*.xel', 'c:\temp\ExtendedEventsStoredProcs*.xem', NULL, NULL);  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="95f98-152">Die Umwandlung der Ereignisdaten in XML ist optional.</span><span class="sxs-lookup"><span data-stu-id="95f98-152">Casting the event data as XML is optional.</span></span>  
  
     <span data-ttu-id="95f98-153">Weitere Informationen über die Funktion „sys.fn_xe_file_target_read_file“ finden Sie unter [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95f98-153">For more information about the sys.fn_xe_file_target_read_file function, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [session_name] ON SERVER;  
    CREATE EVENT SESSION [session_name]  
    ON SERVER  
  
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       );  
  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="example"></a><span data-ttu-id="95f98-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95f98-154">Example</span></span>  
  
```sql
IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
   DROP EVENT SESSION [session_name] ON SERVER;  
CREATE EVENT SESSION [session_name]  
ON SERVER  
  
ADD EVENT sqlserver.sp_statement_starting  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59   
   ),  
  
ADD EVENT sqlserver.sp_statement_completed  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59 AND duration > 0  
   )  
  
ADD TARGET package0.asynchronous_file_target  
   (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
```  
  
## <a name="see-also"></a><span data-ttu-id="95f98-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95f98-155">See Also</span></span>  
 [<span data-ttu-id="95f98-156">Anzeigen der Entsprechungen von erweiterten Ereignissen für SQL-Ablaufverfolgungsklassen</span><span class="sxs-lookup"><span data-stu-id="95f98-156">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)  
  
  
