---
title: Ziel der Ereignis Kopplung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- pairing target [SQL Server extended events]
- event pairing target
- targets [SQL Server extended events], pairing target
ms.assetid: 3c87dcfb-543a-4bd8-a73d-1390bdf4ffa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a1a6beb1c6996e6e12f16c4555fd9dfcab97617d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701601"
---
# <a name="event-pairing-target"></a><span data-ttu-id="6d1b1-102">Ziel 'Ereignispaarbildung'</span><span class="sxs-lookup"><span data-stu-id="6d1b1-102">Event Pairing Target</span></span>
  <span data-ttu-id="6d1b1-103">Das Ziel Ereignispaarbildung ordnet zwei Ereignisse mithilfe mindestens einer Datenspalte in jedem Ereignis einander zu.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-103">The event pairing target matches two events using one or more columns of data that are present in each event.</span></span> <span data-ttu-id="6d1b1-104">Viele Ereignisse sind einander paarweise zugeordnet, z. B. die Anforderungen zur Einrichtung und Aufhebung einer Sperre.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-104">Many events come in pairs, for example, lock acquires and lock releases.</span></span> <span data-ttu-id="6d1b1-105">Nachdem eine Ereignissequenz paarweise zugeordnet wurde, werden beide Ereignisse verworfen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-105">After an event sequence is paired, both events are discarded.</span></span> <span data-ttu-id="6d1b1-106">Das Verwerfen übereinstimmender Sätze ermöglicht ein problemloses Erkennen von eingerichteten Sperren, die noch nicht aufgehoben wurden.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-106">Discarding matched sets allows for easy detection of lock acquisitions that have not been released.</span></span>  
  
 <span data-ttu-id="6d1b1-107">Beim Verwenden von Filtern auf Ereignisebene können mithilfe des Ziels Ereignispaarbildung nur die Ereignisse aufgezeichnet werden, die nicht den voreingestellten Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-107">By using event-level filters, the pairing target can be used to only capture events that do not match pre-set criteria.</span></span>  
  
 <span data-ttu-id="6d1b1-108">Bei Verwendung des Ziels Ereignispaarbildung können Sie zwei Ereignisse auswählen, die einander zugeordnet werden, sowie eine Sequenz von Spalten, für die die Zuordnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-108">When you use the event pairing target, you can choose two events that will be matched, together with a sequence of columns to perform the matching on.</span></span> <span data-ttu-id="6d1b1-109">Alle Spalten in dieser Sequenz müssen den gleichen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-109">All the columns in this sequence must be of the same type.</span></span>  
  
 <span data-ttu-id="6d1b1-110">In der folgenden Tabelle werden die verfügbaren Optionen für das Konfigurieren der Ereignispaarbildung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-110">The following table describes the available options for configuring event pairing.</span></span>  
  
|<span data-ttu-id="6d1b1-111">Option</span><span class="sxs-lookup"><span data-stu-id="6d1b1-111">Option</span></span>|<span data-ttu-id="6d1b1-112">Zulässige Werte</span><span class="sxs-lookup"><span data-stu-id="6d1b1-112">Allowed values</span></span>|<span data-ttu-id="6d1b1-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d1b1-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="6d1b1-114">begin_event</span><span class="sxs-lookup"><span data-stu-id="6d1b1-114">begin_event</span></span>|<span data-ttu-id="6d1b1-115">Ein beliebiger Ereignisname, der in der aktuellen Sitzung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-115">Any event name that is present in the current session.</span></span>|<span data-ttu-id="6d1b1-116">Der Ereignisname, der das Startereignis in einer paarweise zugeordneten Sequenz angibt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-116">The event name specifying the beginning event in a paired sequence.</span></span>|  
|<span data-ttu-id="6d1b1-117">end_event</span><span class="sxs-lookup"><span data-stu-id="6d1b1-117">end_event</span></span>|<span data-ttu-id="6d1b1-118">Ein beliebiger Ereignisname, der in der aktuellen Sitzung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-118">Any event name that is present in the current session.</span></span>|<span data-ttu-id="6d1b1-119">Der Ereignisname, der das Endereignis in einer paarweise zugeordneten Sequenz angibt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-119">The event name specifying the ending event in a paired sequence.</span></span>|  
|<span data-ttu-id="6d1b1-120">begin_matching_columns</span><span class="sxs-lookup"><span data-stu-id="6d1b1-120">begin_matching_columns</span></span>|<span data-ttu-id="6d1b1-121">Eine durch Trennzeichen getrennte geordnete Liste mit Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-121">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="6d1b1-122">Die Spalten, für die die Zuordnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-122">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="6d1b1-123">end_matching_columns</span><span class="sxs-lookup"><span data-stu-id="6d1b1-123">end_matching_columns</span></span>|<span data-ttu-id="6d1b1-124">Eine durch Trennzeichen getrennte geordnete Liste mit Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-124">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="6d1b1-125">Die Spalten, für die die Zuordnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-125">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="6d1b1-126">begin_matching_actions</span><span class="sxs-lookup"><span data-stu-id="6d1b1-126">begin_matching_actions</span></span>|<span data-ttu-id="6d1b1-127">Eine durch Trennzeichen getrennte, geordnete Liste von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-127">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="6d1b1-128">Die Aktionen, für die die Zuordnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-128">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="6d1b1-129">end_matching_actions</span><span class="sxs-lookup"><span data-stu-id="6d1b1-129">end_matching_actions</span></span>|<span data-ttu-id="6d1b1-130">Eine durch Trennzeichen getrennte, geordnete Liste von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-130">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="6d1b1-131">Die Aktionen, für die die Zuordnung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-131">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="6d1b1-132">respond_to_memory_pressure</span><span class="sxs-lookup"><span data-stu-id="6d1b1-132">respond_to_memory_pressure</span></span>|<span data-ttu-id="6d1b1-133">Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="6d1b1-133">One of the following values:</span></span><br /><br /> <span data-ttu-id="6d1b1-134">0 = Es erfolgt keine Antwort.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-134">0 = Do not respond.</span></span><br /><br /> <span data-ttu-id="6d1b1-135">1 = Der Liste werden keine neuen verwaisten Objekte hinzugefügt, wenn nicht mehr genügend Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-135">1 = Stop adding new orphans to the list when there is memory pressure.</span></span>|<span data-ttu-id="6d1b1-136">Die Antwort des Ziels auf Speicherereignisse.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-136">The target response to memory events.</span></span> <span data-ttu-id="6d1b1-137">Wenn auf 1 festgelegt, ist auf den Server wenig Arbeitsspeicher verfügbar, und nicht paarweise zugeordnete Informationen, die beibehalten wurden, werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-137">If set to 1 and the server is low on memory, unpaired information that is being maintained is removed.</span></span>|  
|<span data-ttu-id="6d1b1-138">max_orphans</span><span class="sxs-lookup"><span data-stu-id="6d1b1-138">max_orphans</span></span>||<span data-ttu-id="6d1b1-139">Gibt die Gesamtzahl von nicht paarweise zugeordneten Ereignissen an, die im Ziel gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-139">Specifies the total number of unpaired events that will be collected in the target.</span></span> <span data-ttu-id="6d1b1-140">Sobald die Grenze erreicht wird, werden nicht paarweise zugeordnete Ereignisse auf einer FIFO-Basis (First In, First Out) entfernt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-140">Once the limit is reached, unpaired events are removed on a first-in, first-out (FIFO) basis.</span></span> <span data-ttu-id="6d1b1-141">Standardeinstellung = 10,000.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-141">Default = 10,000.</span></span>|  
  
 <span data-ttu-id="6d1b1-142">Alle einem Ereignis zugeordneten Daten werden aufgezeichnet und für zukünftige paarweise Zuordnungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-142">All the data associated with an event is captured and stored for future pairing.</span></span> <span data-ttu-id="6d1b1-143">Außerdem werden von Aktionen hinzugefügte Daten gesammelt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-143">In addition, data added by actions is also collected.</span></span> <span data-ttu-id="6d1b1-144">Die aufgezeichneten Ereignisdaten werden im Arbeitsspeicher gespeichert und verfügen daher über eine feste Begrenzung.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-144">The collected event data is stored in memory, and therefore has a finite limit.</span></span> <span data-ttu-id="6d1b1-145">Diese Begrenzung basiert auf Systemkapazität und -aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-145">This limit is based on system capacity and activity.</span></span> <span data-ttu-id="6d1b1-146">Statt die maximale Arbeitsspeichermenge als Parameter zu verwenden, wird der verwendete Arbeitsspeicher auf Grundlage der verfügbaren Systemressourcen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-146">Instead of taking the maximum amount of memory to be used as a parameter, the amount of memory used will be based on available system resources.</span></span> <span data-ttu-id="6d1b1-147">Wenn keine verfügbar sind, werden nicht paarweise zugeordnete Ereignisse, die behalten wurden, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-147">When these are not available, unpaired events that have been retained will be dropped.</span></span> <span data-ttu-id="6d1b1-148">Wenn ein Ereignis nicht paarweise zugeordnet wurde und gelöscht wird, wird das übereinstimmende Ereignis als nicht paarweise zugeordnetes Ereignis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-148">If an event has not been paired and is dropped, the matching event will appear as an unpaired event.</span></span>  
  
 <span data-ttu-id="6d1b1-149">Das Ziel Ereignispaarbildung serialisiert nicht paarweise zugeordnete Ereignisse in einem XML-Format.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-149">The pairing target serializes unpaired events to an XML format.</span></span> <span data-ttu-id="6d1b1-150">Dieses Format entspricht keinem Schema.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-150">This format does not conform to any schema.</span></span> <span data-ttu-id="6d1b1-151">Das Format enthält nur zwei Elementtypen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-151">The format only contains two element types.</span></span> <span data-ttu-id="6d1b1-152">Das- **\<unpaired>** Element ist der Stamm, gefolgt von einem.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-152">The **\<unpaired>** element is the root, followed by one.</span></span> <span data-ttu-id="6d1b1-153">**\<event>**-Element für jedes nicht zugeordnete Ereignis, das derzeit nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-153">**\<event>** element for each unpaired event that is currently being tracked.</span></span> <span data-ttu-id="6d1b1-154">Das- **\<event>** Element enthält ein Attribut, das den Namen des nicht paarweise zugeordneten Ereignisses enthält.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-154">The **\<event>** element contains one attribute that contains the name of the unpaired event.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="6d1b1-155">Hinzufügen des Ziels zu einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="6d1b1-155">Adding the Target to a Session</span></span>  
 <span data-ttu-id="6d1b1-156">Wenn Sie das Paarvergleichsziel einer Sitzung für erweiterte Ereignisse hinzufügen möchten, müssen Sie beim Erstellen oder Ändern einer Ereignissitzung die folgende Anweisung einschließen:</span><span class="sxs-lookup"><span data-stu-id="6d1b1-156">To add the pair matching target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.pair_matching   
```  
  
 <span data-ttu-id="6d1b1-157">Nach dieser fügen Sie eine SET-Anweisung ein, um die Anfangs- und Endereignisse sowie die zu vergleichenden Aktionen oder Spalten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-157">You would follow this with a SET statement, to define the beginning and ending events, and which actions or columns to match.</span></span> <span data-ttu-id="6d1b1-158">Das folgende Beispiel zeigt Beispielsyntax für den Paarvergleich der Ereignisse sqlserver.lock_acquired und sqlserver.lock_released.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-158">The following example shows sample syntax for pair matching the sqlserver.lock_acquired and sqlserver.lock_released events.</span></span>  
  
```  
   ( SET begin_event = 'sqlserver.lock_acquired',  
      begin_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
      end_event = 'sqlserver.lock_released',  
      end_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
   respond_to_memory_pressure = 1)  
```  
  
 <span data-ttu-id="6d1b1-159">Weitere Informationen finden Sie unter [Feststellen, welche Abfragen Sperren enthalten](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span><span class="sxs-lookup"><span data-stu-id="6d1b1-159">For more information, see [Determine Which Queries Are Holding Locks](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span></span>  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="6d1b1-160">Überprüfen der Zielausgabe</span><span class="sxs-lookup"><span data-stu-id="6d1b1-160">Reviewing the Target Output</span></span>  
 <span data-ttu-id="6d1b1-161">Sie können die Ausgabe des Paarvergleichsziels mithilfe der folgenden Abfrage überprüfen und dabei *session_name* durch den Namen der Ereignissitzung ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-161">To review the output for the pair matching target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="6d1b1-162">Im folgenden Beispiel wird das Ausgabeformat des Ziels Ereignispaarbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6d1b1-162">The following example shows the pairing target output format.</span></span>  
  
```  
<unpaired truncated = "0" matchedCount = "[matched count]" memoryPressureDroppedCount = " [lost count]">  
    <event name  = "[event name]" package = "[package]" id= "[event ID value]" version = "[event version]">  
    <data name = "[column name]">   
    <type name = "[column type]" package = "[type package]" />   
    <value>[column value]</value>  
    <text value>[text value]</text>>  
        </data>  
    </event>  
</unpaired>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d1b1-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d1b1-163">See Also</span></span>  
 <span data-ttu-id="6d1b1-164">[Ziele für erweiterte Ereignisse von SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="6d1b1-164">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="6d1b1-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d1b1-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="6d1b1-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d1b1-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="6d1b1-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6d1b1-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
