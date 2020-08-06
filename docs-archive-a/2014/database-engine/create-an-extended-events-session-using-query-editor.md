---
title: Erstellen einer Sitzung für erweiterte Ereignisse mit dem Abfrage-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- create extended events session
- extended events [SQL Server], create session
ms.assetid: cba0e02b-b201-4863-bf1b-9164e68e5fa8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 648370ecdd2938b6fb425955dc02da8960f884c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618259"
---
# <a name="create-an-extended-events-session-using-query-editor"></a><span data-ttu-id="dbada-102">Erstellen einer Sitzung für erweiterte Ereignisse mit dem Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="dbada-102">Create an Extended Events Session Using Query Editor</span></span>
  <span data-ttu-id="dbada-103">Eine Sitzung für erweiterte Ereignisse können Sie mit dem Abfrage-Editor erstellen, können aber auch im Objekt-Explorer eine Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="dbada-103">You can create an Extended Events session by using the Query Editor, or you can create a session in Object Explorer.</span></span> <span data-ttu-id="dbada-104">In Objekt-Explorer bieten erweiterte Ereignisse zwei Benutzeroberflächen, die Sie zum Erstellen, ändern und Anzeigen von Ereignis Sitzungsdaten verwenden können: einen Assistenten, der Sie durch den Prozess der Ereignis Sitzungs Erstellung führt, und eine neue Benutzeroberfläche für Sitzungen, die Erweiterte Konfigurationsoptionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dbada-104">In Object Explorer, Extended Events provides two user interfaces you can use to create, modify, and view event session data - a wizard that guides you through the event session creation process, and a New Session UI that provides more advanced configuration options.</span></span> <span data-ttu-id="dbada-105">Sie können Sitzungen für erweiterte Ereignisse erstellen, um die SQL Server-Ablaufverfolgung zu diagnostizieren, sodass Sie z. B. folgende Aufgaben ausführen können:</span><span class="sxs-lookup"><span data-stu-id="dbada-105">You can create Extended Events sessions to diagnose SQL Server tracing, which enables you to resolve issues such as the following:</span></span>  
  
-   <span data-ttu-id="dbada-106">Suchen der aufwendigsten Abfragen</span><span class="sxs-lookup"><span data-stu-id="dbada-106">Find your most expensive queries</span></span>  
  
-   <span data-ttu-id="dbada-107">Suchen der Ursachen von Latchkonflikten</span><span class="sxs-lookup"><span data-stu-id="dbada-107">Find root causes of latch contention</span></span>  
  
-   <span data-ttu-id="dbada-108">Suchen von Abfragen, die andere Abfragen blockieren</span><span class="sxs-lookup"><span data-stu-id="dbada-108">Find a query that is blocking other queries</span></span>  
  
-   <span data-ttu-id="dbada-109">Behandeln des Problems übermäßiger, durch Abfrageneukompilierung verursachter CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="dbada-109">Troubleshoot excessive CPU usage caused by query recompilation</span></span>  
  
-   <span data-ttu-id="dbada-110">Problembehandlung für Deadlocks</span><span class="sxs-lookup"><span data-stu-id="dbada-110">Troubleshoot deadlocks</span></span>  
  
 <span data-ttu-id="dbada-111">Informationen dazu, wie Sie eine Extended Events-Sitzung mit dem Assistenten für neue Sitzung erstellen, finden Sie unter [Erstellen einer Sitzung für erweiterte Ereignisse mithilfe des Assistenten &#40;Objekt-Explorer&#41;](../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="dbada-111">For information about how to create an Extended Events session using the New Session Wizard, see [Create an Extended Events Session Using the Wizard &#40;Object Explorer&#41;](../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="dbada-112">Informationen dazu, wie Sie eine Extended Events-Sitzung mit dem Assistenten für neue Sitzung erstellen, finden Sie unter [Quick Start: Extended events in SQL Server](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) (Schnellstart: Erweiterte Ereignisse in SQL Server).</span><span class="sxs-lookup"><span data-stu-id="dbada-112">For information about how to create an Extended Events session using the New Session UI, see [Create an Extended Events Session Using the New Session Dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dbada-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dbada-113">Permissions</span></span>  
 <span data-ttu-id="dbada-114">Zum Erstellen einer Sitzung für erweiterte Ereignisse müssen Sie über die ALTER ANY EVENT SESSION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="dbada-114">To create an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="creating-an-extended-events-session-using-query-editor"></a><span data-ttu-id="dbada-115">Erstellen einer Sitzung für erweiterte Ereignisse mit dem Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="dbada-115">Creating an Extended Events session using Query Editor</span></span>  
  
#### <a name="to-create-an-extended-events-session"></a><span data-ttu-id="dbada-116">So erstellen Sie eine Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="dbada-116">To create an Extended Events session</span></span>  
  
1.  <span data-ttu-id="dbada-117">In der folgenden Vorgehensweise wird gezeigt, wie eine Sitzung für erweiterte Ereignisse mit dem Abfrage-Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dbada-117">The following procedure shows how to create an Extended Events session by using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="dbada-118">Bestimmen Sie, welche Ereignisse Sie in der Sitzung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dbada-118">Determine which events that you want to use in the session.</span></span> <span data-ttu-id="dbada-119">Um alle verfügbaren Ereignisse zusammen mit dem Schlüsselwort und dem Kanal anzuzeigen, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="dbada-119">To see all the events that are available, together with the keyword and channel, use the following query:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbada-120">Informationen zu Schlüsselwörtern und Kanälen finden Sie unter [Pakete für erweiterte Ereignisse von SQL Server](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="dbada-120">For information about keywords and channels, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
    ```  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
       (  
       SELECT event_package = o.package_guid, o.description,   
       event=c.object_name, channel = v.map_value  
       FROM sys.dm_xe_objects o  
       LEFT JOIN sys.dm_xe_object_columns c ON o.name = c.object_name  
       INNER JOIN sys.dm_xe_map_values v ON c.type_name = v.name   
       AND c.column_value = cast(v.map_key AS nvarchar)  
       WHERE object_type = 'event' AND (c.name = 'CHANNEL' or c.name IS NULL)  
       ) c LEFT JOIN   
       (  
       SELECT event_package = c.object_package_guid, event = c.object_name,   
       keyword = v.map_value  
       FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
       ON c.type_name = v.name AND c.column_value = v.map_key   
       AND c.type_package_guid = v.object_package_guid  
       INNER JOIN sys.dm_xe_objects o ON o.name = c.object_name   
       AND o.package_guid = c.object_package_guid  
       WHERE object_type = 'event' AND c.name = 'KEYWORD'   
       ) k  
       ON  
       k.event_package = c.event_package AND (k.event=c.event or k.event IS NULL)  
       INNER JOIN sys.dm_xe_packages p ON p.guid = c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
2.  <span data-ttu-id="dbada-121">Fügen Sie in einem neuen Abfragefenster die folgenden Anweisungen hinzu, um eine Ereignissitzung zu erstellen, und ersetzen Sie dabei *session_name* durch den Sitzungsnamen, den Sie verwenden möchten:</span><span class="sxs-lookup"><span data-stu-id="dbada-121">In a new query window, add the following statements to create an event session, replacing *session_name* with the session name that you want to use:</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dbada-122">In den Schritten 2 bis 6 dieser Vorgehensweise werden die einzelnen Abschnitte der Ereignissitzungsdefinition beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dbada-122">Steps 2 through 6 of this procedure describe each section of the event session definition.</span></span> <span data-ttu-id="dbada-123">Sie würden alle Anweisungen vor dem Ausführen einem einzelnen Abfragefenster hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dbada-123">You would add all the statements to a single query window before executing.</span></span> <span data-ttu-id="dbada-124">Ein vollständiges Beispiel finden Sie in den Beispielen dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="dbada-124">For a full example, see the Example section of this topic.</span></span>  
  
    ```  
    CREATE EVENT SESSION session_name   
    ON SERVER  
    ```  
  
3.  <span data-ttu-id="dbada-125">Fügen Sie die Ereignisse, die Sie überwachen möchten, im Format *Paketname*.*Ereignisname*hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbada-125">Add the events that you want to monitor, in the format *package_name*.*event_name*.</span></span> <span data-ttu-id="dbada-126">Fügen Sie für jedes Ereignis eine Zeile wie die folgende hinzu:</span><span class="sxs-lookup"><span data-stu-id="dbada-126">For each event, add a line similar to the following:</span></span>  
  
    ```  
    ADD EVENT package_name.event_name  
    ```  
  
     <span data-ttu-id="dbada-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dbada-127">For example:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed,  
    ADD EVENT sqlserver.file_write_completed  
    ```  
  
4.  <span data-ttu-id="dbada-128">(Optional) Nachdem Sie ein Ereignis hinzugefügt haben, können Sie zu verwendende Aktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dbada-128">(Optional) After you add an event, you can add actions to take.</span></span> <span data-ttu-id="dbada-129">Sie können auch Prädikate hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dbada-129">You can also add predicates.</span></span> <span data-ttu-id="dbada-130">Prädikate werden verwendet, um Kriterien dafür festzulegen, wann die Ereignisinformationen vom Ziel verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dbada-130">Predicates are used to establish criteria for when the event information should be consumed by the target.</span></span> <span data-ttu-id="dbada-131">Aktionen werden mit einer ACTION-Klausel hinzugefügt, Prädikate werden mit einer WHERE-Klausel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dbada-131">Actions are added by using an ACTION clause, and predicates are added by using a WHERE clause.</span></span> <span data-ttu-id="dbada-132">Um beispielsweise eine Aktion und ein Prädikat hinzuzufügen, bei der bzw. dem der [!INCLUDE[tsql](../includes/tsql-md.md)] -Text für das -Ereignis aufgezeichnet wird und die Datei-ID gleich 1 ist, würden Sie die folgende Anweisung einschließen:</span><span class="sxs-lookup"><span data-stu-id="dbada-132">For example, to add an action and predicate where the [!INCLUDE[tsql](../includes/tsql-md.md)] text is captured for the sqlserver.file_read_completed event, where the file ID equals 1, you would include the following statement:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed  
       (ACTION (sqlserver.sql_text)  
       WHERE file_id = 1),  
    ```  
  
    -   <span data-ttu-id="dbada-133">Um anzuzeigen, welche Aktionen verfügbar sind, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="dbada-133">To view which actions are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS 'package_name', xo.name AS 'action_name', xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'action'  
        AND (xo.capabilities & 1 = 0   
        OR xo.capabilities IS NULL)  
        ORDER BY p.name, xo.name  
        ```  
  
    -   <span data-ttu-id="dbada-134">Um anzuzeigen, welche Prädikate für ein Ereignis verfügbar sind, verwenden Sie die folgende Abfrage, und ersetzen Sie *event_name* durch den Namen des Ereignisses, für das Sie ein Prädikat hinzufügen möchten:</span><span class="sxs-lookup"><span data-stu-id="dbada-134">To view which predicates are available for an event, use the following query, replacing *event_name* with the name of the event for which you want to add a predicate:</span></span>  
  
        ```  
        SELECT *  
        FROM sys.dm_xe_object_columns  
        WHERE object_name = 'event_name'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="dbada-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dbada-135">For example:</span></span>  
  
        ```  
        SELECT *   
        FROM sys.dm_xe_object_columns   
        WHERE object_name = 'file_read_completed'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="dbada-136">Beachten Sie, dass Sie auch globale Prädikatquellen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="dbada-136">Be aware that you can also add global predicate sources.</span></span> <span data-ttu-id="dbada-137">Eine globale Prädikatquelle kann in einen beliebigen Prädikatausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbada-137">A global predicate source can be used in any predicate expression.</span></span> <span data-ttu-id="dbada-138">Um anzuzeigen, welche globalen Prädikatquellen verfügbar sind, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="dbada-138">To view which global predicate sources are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS package_name, xo.name AS predicate_name  
           , xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'pred_source'  
        ORDER BY p.name, xo.name  
        ```  
  
         <span data-ttu-id="dbada-139">Sie könnten z. B. den folgenden Prädikatausdruck verwenden, um anzugeben, dass Daten für ein Ereignis nur die ersten fünf Male, die ein Ereignis auftritt, erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dbada-139">For example, you could use the following predicate expression to specify that data should only be collected for an event the first five times that an event occurs.</span></span>  
  
        ```  
        WHERE package0.counter <= 5  
        ```  
  
5.  <span data-ttu-id="dbada-140">Fügen Sie das gewünschte Ziel hinzu, an dem die Ereignisdaten verarbeitet und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dbada-140">Add the desired target, where the event data will be processed and consumed.</span></span> <span data-ttu-id="dbada-141">Verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="dbada-141">Use the following format:</span></span>  
  
    ```  
    ADD TARGET package_name.target_name  
    ```  
  
     <span data-ttu-id="dbada-142">Im folgenden Beispiel wird das asynchrone Dateiziel hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="dbada-142">The following example adds the asynchronous file target:</span></span>  
  
    ```  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
    ```  
  
     <span data-ttu-id="dbada-143">Um die Liste der verfügbaren Ziele anzuzeigen, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="dbada-143">To view the list of available targets, use the following query:</span></span>  
  
    ```  
    SELECT p.name AS 'package_name', xo.name AS 'target_name'  
       , xo.description, xo.object_type   
    FROM sys.dm_xe_objects AS xo  
    JOIN sys.dm_xe_packages AS p  
       ON xo.package_guid = p.guid  
    WHERE xo.object_type = 'target'  
    AND (xo.capabilities & 1 = 0  
    OR xo.capabilities IS NULL)  
    ORDER BY p.name, xo.name  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbada-144">Informationen zu den unterschiedlichen Zieltypen finden Sie unter [Ziele für erweiterte Ereignisse von SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="dbada-144">For information about the different target types, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
6.  <span data-ttu-id="dbada-145">Überprüfen Sie alle zusätzlichen Konfigurationsoptionen, und fügen Sie sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbada-145">Review and add any additional configuration options.</span></span> <span data-ttu-id="dbada-146">Sie können Optionen konfigurieren, beispielsweise den Ereignisbeibehaltungsmodus, wie lange Ereignisse im Arbeitsspeicher gepuffert werden, oder ob die Ereignissitzung automatisch gestartet werden soll, wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="dbada-146">For example, you can configure options such as the event retention mode, how long events are buffered in memory, or whether the event session should start automatically when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="dbada-147">In diesem Thema werden die Optionen beschrieben: [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dbada-147">The options are described in the topic [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span></span> <span data-ttu-id="dbada-148">Beachten Sie, dass Standardwerte zugewiesen werden, wenn diese Optionen nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dbada-148">Be aware that default values are assigned if these options are not specified.</span></span>  
  
7.  <span data-ttu-id="dbada-149">Starten Sie die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="dbada-149">Start the session.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbada-150">Weitere Informationen zum Anzeigen der Sitzungsergebnisse finden Sie im entsprechenden Thema für den verwendeten Zieltyp im Knoten [Ziele für erweiterte Ereignisse von SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) der Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="dbada-150">For more information about how to view the session results, see the corresponding topic for the target type that you used in the [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) node of Books Online.</span></span>  
  
 <span data-ttu-id="dbada-151">Im folgenden Beispiel wird eine Sitzung für erweiterte Ereignisse mit dem Namen "IOActivity" erstellt, die die folgenden Informationen aufzeichnet:</span><span class="sxs-lookup"><span data-stu-id="dbada-151">The following example creates an Extended Events session named IOActivity that captures the following information:</span></span>  
  
-   <span data-ttu-id="dbada-152">Ereignisdaten für abgeschlossene Dateilesevorgänge, einschließlich des zugewiesenen [!INCLUDE[tsql](../includes/tsql-md.md)] -Texts für Dateilesevorgänge, bei denen die Datei-ID gleich 1 ist.</span><span class="sxs-lookup"><span data-stu-id="dbada-152">Event data for completed file reads, including the associated [!INCLUDE[tsql](../includes/tsql-md.md)] text for file reads where the file ID is equal to 1.</span></span>  
  
-   <span data-ttu-id="dbada-153">Ereignisdaten für abgeschlossene Dateischreibvorgänge.</span><span class="sxs-lookup"><span data-stu-id="dbada-153">Event data for completed file writes.</span></span>  
  
-   <span data-ttu-id="dbada-154">Ereignisdaten für Situationen, in denen Daten aus dem Protokollcache in die physische Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="dbada-154">Event data for when data is written from the log cache to the physical log file.</span></span>  
  
 <span data-ttu-id="dbada-155">Die Sitzung sendet die Ausgabe an ein Dateiziel.</span><span class="sxs-lookup"><span data-stu-id="dbada-155">The session sends the output to a file target.</span></span>  
  
```  
CREATE EVENT SESSION IOActivity  
ON SERVER  
  
ADD EVENT sqlserver.file_read_completed  
   (  
   ACTION (sqlserver.sql_text)  
   WHERE file_id = 1),  
ADD EVENT sqlserver.file_write_completed,  
ADD EVENT sqlserver.databases_log_flush  
  
ADD TARGET package0.asynchronous_file_target   
   (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbada-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbada-156">See Also</span></span>  
 <span data-ttu-id="dbada-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dbada-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="dbada-158">[Ziele für erweiterte Ereignisse von SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="dbada-158">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 [<span data-ttu-id="dbada-159">Pakete für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="dbada-159">SQL Server Extended Events Packages</span></span>](../relational-databases/extended-events/sql-server-extended-events-packages.md)  
  
  
