---
title: Ring Puffer Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events], ring buffer target
- ring buffer target [SQL Server extended events]
ms.assetid: 54494e11-b56b-43b7-aa5e-c8724e56b251
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 186e847bb9f9b621543119c25510dc5d6107e274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621155"
---
# <a name="ring-buffer-target"></a><span data-ttu-id="8e1a8-102">Ringpufferziel</span><span class="sxs-lookup"><span data-stu-id="8e1a8-102">Ring Buffer Target</span></span>
  <span data-ttu-id="8e1a8-103">Das Ringpufferziel speichert kurzzeitig Ereignisdaten im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-103">The ring buffer target briefly holds event data in memory.</span></span> <span data-ttu-id="8e1a8-104">Dieses Ziel kann Ereignisse in einem von zwei Modi verwalten.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-104">This target can manage events in one of two modes.</span></span>  
  
-   <span data-ttu-id="8e1a8-105">Bei dem ersten Modus handelt es sich um eine strikte FIFO-Reihenfolge (First-In-First-Out), bei der das älteste Ereignis verworfen wird, wenn der gesamte dem Ziel zugeordnete Arbeitsspeicher verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-105">The first mode is strict first-in first-out (FIFO), where the oldest event is discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="8e1a8-106">In diesem Modus (dem Standardmodus) wird die Option "occurrence_number" auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-106">In this mode (the default), the occurrence_number option is set to 0.</span></span>  
  
-   <span data-ttu-id="8e1a8-107">Der zweite Modus ist eine FIFO-Reihenfolge pro Ereignis, bei der eine festgelegte Anzahl von Ereignissen jedes Typs aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-107">The second mode is per-event FIFO, where a specified number of events of each type is kept.</span></span> <span data-ttu-id="8e1a8-108">In diesem Modus werden die ältesten Ereignisse des jeweiligen Typs verworfen, wenn der gesamte dem Ziel zugeordnete Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-108">In this mode, the oldest events of each type are discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="8e1a8-109">Sie können die Option "occurrence_number" so konfigurieren, dass die Anzahl der für jeden Typ beizubehaltenden Ereignisse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-109">You can configure the occurrence_number option to specify the number of events of each type to keep.</span></span>  
  
 <span data-ttu-id="8e1a8-110">In der folgenden Tabelle werden die verfügbaren Optionen für das Konfigurieren des Ringpufferziels beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-110">The following table describes the available options for configuring the ring buffer target.</span></span>  
  
|<span data-ttu-id="8e1a8-111">Option</span><span class="sxs-lookup"><span data-stu-id="8e1a8-111">Option</span></span>|<span data-ttu-id="8e1a8-112">Zulässige Werte</span><span class="sxs-lookup"><span data-stu-id="8e1a8-112">Allowed values</span></span>|<span data-ttu-id="8e1a8-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e1a8-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="8e1a8-114">max_memory</span><span class="sxs-lookup"><span data-stu-id="8e1a8-114">max_memory</span></span>|<span data-ttu-id="8e1a8-115">Eine beliebige 32-Bit-Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-115">Any 32-bit integer.</span></span> <span data-ttu-id="8e1a8-116">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-116">This value is optional.</span></span>|<span data-ttu-id="8e1a8-117">Die Höchstmenge des verfügbaren Arbeitsspeichers in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="8e1a8-117">The maximum amount of memory in kilobytes (KB) to use.</span></span> <span data-ttu-id="8e1a8-118">Vorhandene Ereignisse werden auf Grundlage der Grenze gelöscht, die zuerst erreicht wird: max_event_limit oder max_memory.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-118">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="8e1a8-119">Der Höchstwert beträgt 4194303 KB.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-119">The maximum value is 4194303 KB.</span></span> <span data-ttu-id="8e1a8-120">Es muss sorgfältig vorgegangen werden, bevor die Ringpuffer Größe auf Limits im GB-Bereich festgelegt wird, da dies Auswirkungen auf andere Arbeitsspeicherconsumer in SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e1a8-120">A careful consideration should be made before setting the ring buffer size to limits in the GB range as it may impact other memory consumers in SQL Server</span></span>|  
|<span data-ttu-id="8e1a8-121">max_event_limit</span><span class="sxs-lookup"><span data-stu-id="8e1a8-121">max_event_limit</span></span>|<span data-ttu-id="8e1a8-122">Eine beliebige 32-Bit-Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-122">Any 32-bit integer.</span></span> <span data-ttu-id="8e1a8-123">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-123">This value is optional.</span></span>|<span data-ttu-id="8e1a8-124">Die maximale Anzahl von Ereignissen, die in ring_buffer behalten wurden.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-124">The maximum number of events kept in the ring_buffer.</span></span> <span data-ttu-id="8e1a8-125">Vorhandene Ereignisse werden auf Grundlage der Grenze gelöscht, die zuerst erreicht wird: max_event_limit oder max_memory.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-125">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="8e1a8-126">Standardeinstellung = 1000.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-126">Default = 1000.</span></span>|  
|<span data-ttu-id="8e1a8-127">occurrence_number</span><span class="sxs-lookup"><span data-stu-id="8e1a8-127">occurrence_number</span></span>|<span data-ttu-id="8e1a8-128">Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="8e1a8-128">One of the following values:</span></span><br /><br /> <span data-ttu-id="8e1a8-129">0 (Standard) = Das älteste Ereignis wird verworfen, wenn der gesamte dem Ziel zugeordnete Arbeitsspeicher verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-129">0 (the default) = Oldest event is discarded when all the memory allocated to the target is used.</span></span><br /><br /> <span data-ttu-id="8e1a8-130">Eine beliebige 32-Bit-Ganzzahl = die Anzahl der Ereignisse jedes Typs, die aufbewahrt werden, bevor Sie auf einer FIFO-Basis pro Ereignis verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-130">Any 32-bit integer = The number of events of each type to keep before being discarded on a per-event FIFO basis.</span></span><br /><br /> <br /><br /> <span data-ttu-id="8e1a8-131">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-131">This value is optional.</span></span>|<span data-ttu-id="8e1a8-132">Der zu verwendende FIFO-Modus. Wenn dieser auf einen Wert größer als 0 festgelegt ist, die gewünschte Anzahl von Ereignissen, die für jeden Typ im Puffer gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-132">The FIFO mode to use, and, if set to a value greater than 0, the preferred number of events of each type to keep in the buffer.</span></span>|
| &nbsp; | &nbsp; | &nbsp; |
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="8e1a8-133">Hinzufügen des Ziels zu einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="8e1a8-133">Adding the Target to a Session</span></span>  
 <span data-ttu-id="8e1a8-134">Wenn Sie das Ringpufferziel einer Sitzung für erweiterte Ereignisse hinzufügen möchten, müssen Sie beim Erstellen oder Ändern einer Ereignissitzung die folgende Anweisung einschließen:</span><span class="sxs-lookup"><span data-stu-id="8e1a8-134">To add the ring buffer target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```sql
ADD TARGET package0.ring_buffer  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="8e1a8-135">Überprüfen der Zielausgabe</span><span class="sxs-lookup"><span data-stu-id="8e1a8-135">Reviewing the Target Output</span></span>  
 <span data-ttu-id="8e1a8-136">Sie können die Ausgabe des Ringpufferziels mithilfe der folgenden Abfrage überprüfen und dabei *session_name* durch den Namen der Ereignissitzung ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-136">To review the output from the ring buffer target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```sql
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="8e1a8-137">Im folgenden Beispiel wird das Ausgabeformat des Ringpufferziels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e1a8-137">The following example shows the ring buffer target output format.</span></span>  
  
```  
<RingBufferTarget eventsPerSec="" processingTime="" totalEventsProcessed="" eventCount="" droppedCount="" memoryUsed="">  
 <event name="" package="" id="" version="" timestamp="">  
    <data name="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </data>  
    <action name="" package="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </action>  
  </event>  
</RingBufferTarget>  
```


## <a name="see-also"></a><span data-ttu-id="8e1a8-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e1a8-138">See Also</span></span>

- [<span data-ttu-id="8e1a8-139">Ziele für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e1a8-139">SQL Server Extended Events Targets</span></span>](../../2014/database-engine/sql-server-extended-events-targets.md)
- [<span data-ttu-id="8e1a8-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8e1a8-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="8e1a8-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8e1a8-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-session-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="8e1a8-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8e1a8-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](https://docs.microsoft.com/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2016)

