---
title: Anzeigen der Entsprechungen von erweiterten Ereignissen für SQL-Ablaufverfolgungsklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, extended events equivalents
- extended events [SQL Server], SQL Trace equivalents
- extended events [SQL Server], user configurable events
ms.assetid: 7f24104c-201d-4361-9759-f78a27936011
author: rothja
ms.author: jroth
ms.openlocfilehash: 37459359f9f6cb7e3951b705c4007477ec43e36a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695602"
---
# <a name="view-the-extended-events-equivalents-to-sql-trace-event-classes"></a><span data-ttu-id="3ab75-102">Anzeigen der Entsprechungen von erweiterten Ereignissen für SQL-Ablaufverfolgungsklassen</span><span class="sxs-lookup"><span data-stu-id="3ab75-102">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>
  <span data-ttu-id="3ab75-103">Wenn Sie Erweiterte Ereignisse verwenden möchten, um Ereignisdaten zu erfassen, die SQL-Ablaufverfolgungs-Ereignisklassen und Spalten entsprechen, müssen Sie verstehen, wie die SQL-Ablaufverfolgungsereignisse Ereignissen und Aktionen für erweiterte Ereignisse zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3ab75-103">If you want to use Extended Events to collect event data that is equivalent to SQL Trace event classes and columns, it is useful to understand how the SQL Trace events map to Extended Events events and actions.</span></span>  
  
 <span data-ttu-id="3ab75-104">Gehen Sie folgendermaßen vor, um die Ereignisse und Aktionen für erweiterte Ereignisse anzuzeigen, die den einzelnen SQL-Ablaufverfolgungsereignissen und deren zugeordneten Spalten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3ab75-104">You can use the following procedure to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>  
  
## <a name="to-view-the-extended-events-equivalents-to-sql-trace-events-using-query-editor"></a><span data-ttu-id="3ab75-105">So zeigen Sie die Entsprechungen der erweiterten Ereignisse für SQL-Ablaufverfolgungsereignisse mit dem Abfrage-Editor an</span><span class="sxs-lookup"><span data-stu-id="3ab75-105">To view the Extended Events equivalents to SQL Trace events using Query Editor</span></span>  
  
-   <span data-ttu-id="3ab75-106">Führen Sie im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="3ab75-106">From Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], run the following query:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    SELECT DISTINCT  
       tb.trace_event_id,  
       te.name AS 'Event Class',  
       em.package_name AS 'Package',  
       em.xe_event_name AS 'XEvent Name',  
       tb.trace_column_id,  
       tc.name AS 'SQL Trace Column',  
       am.xe_action_name as 'Extended Events action'  
    FROM (sys.trace_events te LEFT OUTER JOIN sys.trace_xe_event_map em  
       ON te.trace_event_id = em.trace_event_id) LEFT OUTER JOIN sys.trace_event_bindings tb  
       ON em.trace_event_id = tb.trace_event_id LEFT OUTER JOIN sys.trace_columns tc  
       ON tb.trace_column_id = tc.trace_column_id LEFT OUTER JOIN sys.trace_xe_action_map am  
       ON tc.trace_column_id = am.trace_column_id  
    ORDER BY te.name, tc.name  
    ```  
  
 <span data-ttu-id="3ab75-107">Beachten Sie beim Anzeigen der Ergebnisse Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3ab75-107">When you view the results, note the following:</span></span>  
  
-   <span data-ttu-id="3ab75-108">Wenn alle Spalten außer der Spalte zu Ereignisklassen NULL zurückgeben, deutet dies darauf hin, dass die Ereignisklasse nicht von der SQL-Ablaufverfolgung migriert wurde.</span><span class="sxs-lookup"><span data-stu-id="3ab75-108">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="3ab75-109">Wenn nur der Wert in der Aktionsspalte zu erweiterten Ereignissen NULL ist, deutet dies darauf hin, dass eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="3ab75-109">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="3ab75-110">Die SQL-Ablaufverfolgungsspalte ist einem der Datenfelder zugeordnet, das dem Ereignis für erweiterte Ereignisse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3ab75-110">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3ab75-111">Jedes Ereignis für erweiterte Ereignisse verfügt über ein Standardsatz von Datenfeldern, die automatisch im Resultset enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3ab75-111">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="3ab75-112">Die Aktionsspalte hat keine sinnvolle Entsprechung in den erweiterten Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="3ab75-112">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="3ab75-113">Ein Beispiel dafür ist die Spalte zu Ereignisklassen in der SQL-Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="3ab75-113">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="3ab75-114">Diese Spalte wird nicht in den erweiterten Ereignissen benötigt, da der Ereignisname demselben Zweck dient.</span><span class="sxs-lookup"><span data-stu-id="3ab75-114">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="3ab75-115">Für vom Benutzer konfigurierbare SQL-Ablaufverfolgungs-Ereignisklassen (UserConfigurable:1 bis UserConfigurable:9) verwenden die erweiterten Ereignisse ein einzelnes Ereignis, um diese zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3ab75-115">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="3ab75-116">Das Ereignis trägt den Namen „user_event“.</span><span class="sxs-lookup"><span data-stu-id="3ab75-116">The event is named user_event.</span></span> <span data-ttu-id="3ab75-117">Dieses Ereignis wird mit „sp_trace_generateevent“ ausgelöst, die gleiche gespeicherte Prozedur, die von der SQL-Ablaufverfolgung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ab75-117">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="3ab75-118">Das Ereignis „user_event“ wird unabhängig davon zurückgegeben, welche Ereignis-ID an die gespeicherte Prozedur übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3ab75-118">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="3ab75-119">Ein „event_id“-Feld wird jedoch als Teil der Ereignisdaten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ab75-119">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="3ab75-120">Sie können auf diese Weise ein Prädikat erstellen, das auf der Ereignis-ID basiert.</span><span class="sxs-lookup"><span data-stu-id="3ab75-120">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="3ab75-121">Wenn Sie z. B. „UserConfigurable:0“ (Ereignis-ID = 82) im Code verwenden, können Sie der Sitzung das „user_event“-Ereignis hinzufügen, und das Prädikat „event_id = 82“ angeben.</span><span class="sxs-lookup"><span data-stu-id="3ab75-121">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="3ab75-122">Daher müssen Sie den Code nicht ändern, da die gespeicherte Prozedur „sp_trace_generateevent“ das „user_event“-Ereignis für erweiterte Ereignisse und die entsprechende SQL-Ablaufverfolgungs-Ereignisklasse generiert.</span><span class="sxs-lookup"><span data-stu-id="3ab75-122">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
-   <span data-ttu-id="3ab75-123">Wenn alle Spalten außer der Spalte zu Ereignisklassen NULL zurückgeben, deutet dies darauf hin, dass die Ereignisklasse nicht von der SQL-Ablaufverfolgung migriert wurde.</span><span class="sxs-lookup"><span data-stu-id="3ab75-123">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="3ab75-124">Wenn nur der Wert in der Aktionsspalte zu erweiterten Ereignissen NULL ist, deutet dies darauf hin, dass eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="3ab75-124">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="3ab75-125">Die SQL-Ablaufverfolgungsspalte ist einem der Datenfelder zugeordnet, das dem Ereignis für erweiterte Ereignisse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3ab75-125">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3ab75-126">Jedes Ereignis für erweiterte Ereignisse verfügt über ein Standardsatz von Datenfeldern, die automatisch im Resultset enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3ab75-126">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="3ab75-127">Die Aktionsspalte hat keine sinnvolle Entsprechung in den erweiterten Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="3ab75-127">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="3ab75-128">Ein Beispiel dafür ist die Spalte zu Ereignisklassen in der SQL-Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="3ab75-128">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="3ab75-129">Diese Spalte wird nicht in den erweiterten Ereignissen benötigt, da der Ereignisname demselben Zweck dient.</span><span class="sxs-lookup"><span data-stu-id="3ab75-129">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="3ab75-130">Für vom Benutzer konfigurierbare SQL-Ablaufverfolgungs-Ereignisklassen (UserConfigurable:1 bis UserConfigurable:9) verwenden die erweiterten Ereignisse ein einzelnes Ereignis, um diese zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3ab75-130">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="3ab75-131">Das Ereignis trägt den Namen „user_event“.</span><span class="sxs-lookup"><span data-stu-id="3ab75-131">The event is named user_event.</span></span> <span data-ttu-id="3ab75-132">Dieses Ereignis wird mit „sp_trace_generateevent“ ausgelöst, die gleiche gespeicherte Prozedur, die von der SQL-Ablaufverfolgung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ab75-132">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="3ab75-133">Das Ereignis „user_event“ wird unabhängig davon zurückgegeben, welche Ereignis-ID an die gespeicherte Prozedur übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3ab75-133">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="3ab75-134">Ein „event_id“-Feld wird jedoch als Teil der Ereignisdaten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ab75-134">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="3ab75-135">Sie können auf diese Weise ein Prädikat erstellen, das auf der Ereignis-ID basiert.</span><span class="sxs-lookup"><span data-stu-id="3ab75-135">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="3ab75-136">Wenn Sie z. B. „UserConfigurable:0“ (Ereignis-ID = 82) im Code verwenden, können Sie der Sitzung das „user_event“-Ereignis hinzufügen, und das Prädikat „event_id = 82“ angeben.</span><span class="sxs-lookup"><span data-stu-id="3ab75-136">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="3ab75-137">Daher müssen Sie den Code nicht ändern, da die gespeicherte Prozedur „sp_trace_generateevent“ das „user_event“-Ereignis für erweiterte Ereignisse und die entsprechende SQL-Ablaufverfolgungs-Ereignisklasse generiert.</span><span class="sxs-lookup"><span data-stu-id="3ab75-137">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab75-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ab75-138">See Also</span></span>  
 [<span data-ttu-id="3ab75-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ab75-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)  
  
  
