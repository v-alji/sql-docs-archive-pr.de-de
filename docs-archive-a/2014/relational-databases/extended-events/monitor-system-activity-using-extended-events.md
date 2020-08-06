---
title: Überwachen der Systemaktivität mit erweiterten Ereignissen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- xe
- extended events [SQL Server], monitoring system activity
ms.assetid: d83ad88f-818c-49fe-a9a9-299f704fca53
author: rothja
ms.author: jroth
ms.openlocfilehash: d847d156d8244ede533e684c9e6b753d7d7b5047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608666"
---
# <a name="monitor-system-activity-using-extended-events"></a><span data-ttu-id="a447f-102">Überwachen der Systemaktivität mit erweiterten Ereignisses</span><span class="sxs-lookup"><span data-stu-id="a447f-102">Monitor System Activity Using Extended Events</span></span>
  <span data-ttu-id="a447f-103">Das folgende Verfahren veranschaulicht, wie Extended Events mit der Ereignisablaufverfolgung für Windows (ETW) zum Überwachen der Systemaktivität verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a447f-103">This procedure illustrates how Extended Events can be used with Event Tracing for Windows (ETW) to monitor system activity.</span></span> <span data-ttu-id="a447f-104">Außerdem wird gezeigt, wie die Anweisungen CREATE EVENT SESSION, ALTER EVENT SESSION und DROP EVENT SESSION verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a447f-104">The procedure also shows how the CREATE EVENT SESSION, ALTER EVENT SESSION, and DROP EVENT SESSION statements are used.</span></span>  
  
 <span data-ttu-id="a447f-105">Das Ausführen dieser Tasks umfasst die Verwendung des Abfrage-Editors in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , um den folgenden Vorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a447f-105">Accomplishing these tasks involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span> <span data-ttu-id="a447f-106">Das Verfahren erfordert außerdem, mithilfe der Eingabeaufforderung ETW-Befehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a447f-106">The procedure also requires using the command prompt to run ETW commands.</span></span>  
  
### <a name="to-monitor-system-activity-using-extended-events"></a><span data-ttu-id="a447f-107">So überwachen Sie die Systemaktivität mit erweiterten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="a447f-107">To monitor system activity using Extended Events</span></span>  
  
1.  <span data-ttu-id="a447f-108">Geben Sie im Abfrage-Editor die folgenden Anweisungen aus, um eine Ereignissitzung zu erstellen und zwei Ereignisse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a447f-108">In Query Editor, issue the following statements to create an event session and add two events.</span></span> <span data-ttu-id="a447f-109">Diese Ereignisse, checkpoint_begin und checkpoint_end, werden am Anfang und am Ende eines Datenbankprüfpunkts ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a447f-109">These events, checkpoint_begin and checkpoint_end, fire at the beginning and end of a database checkpoint.</span></span>  
  
    ```  
    CREATE EVENT SESSION test0  
    ON SERVER  
    ADD EVENT sqlserver.checkpoint_begin,  
    ADD EVENT sqlserver.checkpoint_end  
    WITH (MAX_DISPATCH_LATENCY = 1 SECONDS)  
    go  
    ```  
  
2.  <span data-ttu-id="a447f-110">Fügen Sie das Ziel mit 32 Buckets hinzu, um die Anzahl der Prüfpunkte basierend auf der Datenbank-ID zu zählen.</span><span class="sxs-lookup"><span data-stu-id="a447f-110">Add the bucketing target with 32 buckets to count the number of checkpoints based on the database ID.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.histogram  
    (  
          SET slots = 32, filtering_event_name = 'sqlserver.checkpoint_end', source_type = 0, source = 'database_id'  
    )  
    go  
    ```  
  
3.  <span data-ttu-id="a447f-111">Geben Sie die folgenden Anweisungen aus, um das ETW-Ziel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a447f-111">Issue the following statements to add the ETW target.</span></span> <span data-ttu-id="a447f-112">So können Sie die Anfangs- und Endereignisse anzeigen, mit denen die Dauer des Prüfpunkts bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="a447f-112">This will enable you to see the begin and end events, which is used to determine how long the checkpoint takes.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.etw_classic_sync_target  
    go  
    ```  
  
4.  <span data-ttu-id="a447f-113">Geben Sie die folgenden Anweisungen aus, um die Sitzung und die Ereignisauflistung zu starten.</span><span class="sxs-lookup"><span data-stu-id="a447f-113">Issue the following statements to start the session and begin event collection.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = start  
    go  
    ```  
  
5.  <span data-ttu-id="a447f-114">Geben Sie die folgenden Anweisungen aus, um drei Ereignisse auszulösen.</span><span class="sxs-lookup"><span data-stu-id="a447f-114">Issue the following statements to cause three events to fire.</span></span>  
  
    ```  
    USE tempdb  
          checkpoint  
    go  
    USE master  
          checkpoint  
          checkpoint  
    go  
    ```  
  
6.  <span data-ttu-id="a447f-115">Geben Sie die folgenden Anweisungen aus, um die Ereigniszähler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a447f-115">Issue the following statements to view the event counts.</span></span>  
  
    ```  
    SELECT CAST(xest.target_data AS xml) Bucketizer_Target_Data_in_XML  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'test0'  
    go  
    ```  
  
7.  <span data-ttu-id="a447f-116">Geben Sie die folgenden Befehle an der Eingabeaufforderung aus, um die ETW-Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a447f-116">At the command prompt, issue the following commands to view the ETW data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a447f-117"> Um Hilfe für den **tracerpt** -Befehl aufzurufen, geben Sie `tracerpt /?`an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="a447f-117">To get help for the **tracerpt** command, at the command prompt, enter `tracerpt /?`.</span></span>  
  
    ```  
    logman query -ets --- List the ETW sessions. This is optional.  
    logman update XE_DEFAULT_ETW_SESSION -fd -ets --- Flush the ETW log.  
    tracerpt %temp%\xeetw.etl -o xeetw.txt --- Dump the events so they can be seen.  
    ```  
  
8.  <span data-ttu-id="a447f-118">Geben Sie die folgenden Anweisungen aus, um die Ereignissitzung zu beenden und vom Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a447f-118">Issue the following statements to stop the event session and remove it from the server.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = STOP  
    go  
  
    DROP EVENT SESSION test0  
    ON SERVER  
    go  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a447f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a447f-119">See Also</span></span>  
 <span data-ttu-id="a447f-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a447f-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="a447f-121">[Alter Event Session &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a447f-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="a447f-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a447f-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="a447f-123">Katalogsichten für erweiterte Ereignisse &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a447f-123">Extended Events Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql)  
 <span data-ttu-id="a447f-124">[Dynamische Verwaltungs Sichten für erweiterte Ereignisse](../views/views.md) </span><span class="sxs-lookup"><span data-stu-id="a447f-124">[Extended Events Dynamic Management Views](../views/views.md) </span></span>  
 [<span data-ttu-id="a447f-125">Ziele für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="a447f-125">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
