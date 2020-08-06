---
title: Verwenden der system_health-Sitzung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
ms.openlocfilehash: 86c3221fb4c0ea0690b369888ac8f2f9f82d6ef9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608654"
---
# <a name="use-the-system_health-session"></a><span data-ttu-id="aadc1-102">Verwenden der system_health-Sitzung</span><span class="sxs-lookup"><span data-stu-id="aadc1-102">Use the system_health Session</span></span>
  <span data-ttu-id="aadc1-103">Bei der system_health-Sitzung handelt es sich um eine standardmäßig in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]enthaltene Sitzung für erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="aadc1-103">The system_health session is an Extended Events session that is included by default with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aadc1-104">Diese Sitzung wird automatisch beim Start von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] gestartet und ohne merkliche Auswirkungen auf die Leistung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aadc1-104">This session starts automatically when the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] starts, and runs without any noticeable performance effects.</span></span> <span data-ttu-id="aadc1-105">In der Sitzung werden Systemdaten erfasst, mit deren Hilfe Sie Leistungsprobleme in [!INCLUDE[ssDE](../../includes/ssde-md.md)]beheben können.</span><span class="sxs-lookup"><span data-stu-id="aadc1-105">The session collects system data that you can use to help troubleshoot performance issues in the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="aadc1-106">Daher empfiehlt es sich, die Sitzung nicht zu beenden oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="aadc1-106">Therefore, we recommend that you do not stop or delete the session.</span></span>  
  
 <span data-ttu-id="aadc1-107">In der Sitzung werden u. a. folgende Informationen erfasst:</span><span class="sxs-lookup"><span data-stu-id="aadc1-107">The session collects information that includes the following:</span></span>  
  
-   <span data-ttu-id="aadc1-108">„sql_text“ und „session_id“ aller Sitzungen, in denen ein Fehler mit einem Schweregrad >= 20 aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="aadc1-108">The sql_text and session_id for any sessions that encounter an error that has a severity >=20.</span></span>  
  
-   <span data-ttu-id="aadc1-109">„sql_text“ und „session_id“ aller Sitzungen, in denen ein arbeitsspeicherbezogener Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="aadc1-109">The sql_text and session_id for any sessions that encounter a memory-related error.</span></span> <span data-ttu-id="aadc1-110">Zu diesen Fehlern zählen 17803, 701, 802, 8645, 8651, 8657 und 8902.</span><span class="sxs-lookup"><span data-stu-id="aadc1-110">The errors include 17803, 701, 802, 8645, 8651, 8657 and 8902.</span></span>  
  
-   <span data-ttu-id="aadc1-111">Aufzeichnungen zu allen nicht gelösten Zeitplanungsproblemen.</span><span class="sxs-lookup"><span data-stu-id="aadc1-111">A record of any non-yielding scheduler problems.</span></span> <span data-ttu-id="aadc1-112">(Diese werden im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll als Fehler 17883 angezeigt.)</span><span class="sxs-lookup"><span data-stu-id="aadc1-112">(These appear in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log as error 17883.)</span></span>  
  
-   <span data-ttu-id="aadc1-113">Alle erkannten Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="aadc1-113">Any deadlocks that are detected.</span></span>  
  
-   <span data-ttu-id="aadc1-114">„callstack“, „sql_text“ und „session_id“ aller Sitzungen, die > 15 Sekunden lang auf Latches (oder andere relevante Ressourcen) gewartet haben.</span><span class="sxs-lookup"><span data-stu-id="aadc1-114">The callstack, sql_text, and session_id for any sessions that have waited on latches (or other interesting resources) for > 15 seconds.</span></span>  
  
-   <span data-ttu-id="aadc1-115">„callstack“, „sql_text“ und „session_id“ aller Sitzungen, die > 30 Sekunden lang auf Sperren gewartet haben.</span><span class="sxs-lookup"><span data-stu-id="aadc1-115">The callstack, sql_text, and session_id for any sessions that have waited on locks for > 30 seconds.</span></span>  
  
-   <span data-ttu-id="aadc1-116">„callstack“, „sql_text“ und „session_id“ aller Sitzungen, die lange auf präemptive Wartevorgänge gewartet haben.</span><span class="sxs-lookup"><span data-stu-id="aadc1-116">The callstack, sql_text, and session_id for any sessions that have waited for a long time for preemptive waits.</span></span> <span data-ttu-id="aadc1-117">Die Dauer schwankt je nach Wartetyp.</span><span class="sxs-lookup"><span data-stu-id="aadc1-117">The duration varies by wait type.</span></span> <span data-ttu-id="aadc1-118">Bei einem präemptiven Wartevorgang wartet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf externe API-Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="aadc1-118">A preemptive wait is where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for external API calls.</span></span>  
  
-   <span data-ttu-id="aadc1-119">Die Aufrufliste und session_id für Fehler bei der CLR-Belegung und virtuellen Belegung.</span><span class="sxs-lookup"><span data-stu-id="aadc1-119">The callstack and session_id for CLR allocation and virtual allocation failures.</span></span>  
  
-   <span data-ttu-id="aadc1-120">Die ring_buffer-Ereignisse für den Speicherbroker, die Zeitplanungsmodul-Überwachung, Speicherknoten-OOMs sowie Sicherheit und Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="aadc1-120">The ring_buffer events for the memory broker, scheduler monitor, memory node OOM, security, and connectivity.</span></span>  
  
-   <span data-ttu-id="aadc1-121">Die Systemkomponente ergibt sich aus sp_server_diagnostics.</span><span class="sxs-lookup"><span data-stu-id="aadc1-121">System component results from sp_server_diagnostics.</span></span>  
  
-   <span data-ttu-id="aadc1-122">Mit scheduler_monitor_system_health_ring_buffer_recorded erfasster Zustand der Instanz.</span><span class="sxs-lookup"><span data-stu-id="aadc1-122">Instance health collected by scheduler_monitor_system_health_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="aadc1-123">CLR-Belegungsfehler.</span><span class="sxs-lookup"><span data-stu-id="aadc1-123">CLR Allocation failures.</span></span>  
  
-   <span data-ttu-id="aadc1-124">Konnektivitätsfehler mit connectivity_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="aadc1-124">Connectivity errors using connectivity_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="aadc1-125">Sicherheitsfehler mit security_error_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="aadc1-125">Security errors using security_error_ring_buffer_recorded.</span></span>  
  
## <a name="viewing-the-session-data"></a><span data-ttu-id="aadc1-126">Anzeigen der Sitzungsdaten</span><span class="sxs-lookup"><span data-stu-id="aadc1-126">Viewing the Session Data</span></span>  
 <span data-ttu-id="aadc1-127">In der Sitzung werden die Daten im Ringpufferziel gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aadc1-127">The session uses the ring buffer target to store the data.</span></span> <span data-ttu-id="aadc1-128">Zum Anzeigen der Sitzungsdaten verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="aadc1-128">To view the session data, use the following query:</span></span>  
  
```  
SELECT CAST(xet.target_data as xml) FROM sys.dm_xe_session_targets xet  
JOIN sys.dm_xe_sessions xe  
ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'system_health'  
```  
  
 <span data-ttu-id="aadc1-129">Um die Sitzungsdaten aus der Ereignisdatei anzuzeigen, verwenden Sie die in Management Studio verfügbare Benutzeroberfläche für erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="aadc1-129">To view the session data from the event file, use the Extended Events user interface available in Management Studio.</span></span> <span data-ttu-id="aadc1-130">Weitere Informationen finden Sie unter [View Event Session Data](../../database-engine/view-event-session-data.md) .</span><span class="sxs-lookup"><span data-stu-id="aadc1-130">See [View Event Session Data](../../database-engine/view-event-session-data.md) for more information.</span></span>  
  
## <a name="restoring-the-system_health-session"></a><span data-ttu-id="aadc1-131">Wiederherstellen der system_health-Sitzung</span><span class="sxs-lookup"><span data-stu-id="aadc1-131">Restoring the system_health Session</span></span>  
 <span data-ttu-id="aadc1-132">Wenn Sie die system_health-Sitzung gelöscht haben, können Sie diese wiederherstellen, indem Sie die Datei **u_tables.sql** im Abfrage-Editor ausführen.</span><span class="sxs-lookup"><span data-stu-id="aadc1-132">If you delete the system_health session, you can restore it by executing the **u_tables.sql** file in Query Editor.</span></span> <span data-ttu-id="aadc1-133">Diese Datei befindet sich im folgenden Ordner, wobei C: dem Laufwerk entspricht, auf dem Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Programmdateien installiert haben:</span><span class="sxs-lookup"><span data-stu-id="aadc1-133">This file is located in the following folder, where C: represents the drive where you installed the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program files:</span></span>  
  
 <span data-ttu-id="aadc1-134">C:\Programme\Microsoft SQL server\mssql12. \<*instanceid*> \Mssql\install</span><span class="sxs-lookup"><span data-stu-id="aadc1-134">C:\Program Files\Microsoft SQL Server\MSSQL12.\<*instanceid*>\MSSQL\Install</span></span>  
  
 <span data-ttu-id="aadc1-135">Wenn Sie die Sitzung wiederhergestellt haben, müssen Sie die Sitzung mit der ALTER EVENT SESSION-Anweisung oder über den Knoten **Erweiterte Ereignisse** im Objekt-Explorer starten.</span><span class="sxs-lookup"><span data-stu-id="aadc1-135">Be aware that after you restore the session, you must start the session by using the ALTER EVENT SESSION statement or by using the **Extended Events** node in Object Explorer.</span></span> <span data-ttu-id="aadc1-136">Andernfalls wird die Sitzung beim nächsten Neustart des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Diensts automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="aadc1-136">Otherwise, the session starts automatically the next time that you restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadc1-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aadc1-137">See Also</span></span>  
 [<span data-ttu-id="aadc1-138">Tools für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="aadc1-138">Extended Events Tools</span></span>](extended-events-tools.md)  
  
  
