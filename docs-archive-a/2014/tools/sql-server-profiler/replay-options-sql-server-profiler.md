---
title: Wiedergabe Optionen (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
- health monitor [SQL Server]
- Replay Configuration dialog box
ms.assetid: 58761a25-a84f-4a90-9c61-97700bc5ad9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 695a1431145813f0a7829626a380e510d0e602e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722057"
---
# <a name="replay-options-sql-server-profiler"></a><span data-ttu-id="9a42e-102">Wiedergabeoptionen (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="9a42e-102">Replay Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="9a42e-103">Vor der Wiedergabe einer aufgezeichneten Ablaufverfolgung mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]können Sie im Dialogfeld **Wiedergabekonfiguration** Wiedergabeoptionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="9a42e-103">Before replaying a captured trace with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], specify replay options in the **Replay Configuration** dialog box.</span></span> <span data-ttu-id="9a42e-104">Um dieses Dialogfeld zu starten, öffnen Sie die Datei oder Tabelle für die Ablaufverfolgungswiedergabe in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], und klicken Sie im Menü **Wiedergeben** auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="9a42e-104">To launch this dialog box, open the replay trace file or table in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and on the **Replay** menu, click **Start**.</span></span> <span data-ttu-id="9a42e-105">Informationen zu den Berechtigungen, die zum Wiedergeben einer Ablaufverfolgung erforderlich sind, finden Sie unter [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="9a42e-105">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="9a42e-106">In diesem Thema werden die im Dialogfeld **Wiedergabekonfiguration** angegebenen Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a42e-106">This topic describes the options specified with the **Replay Configuration** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a42e-107">Es empfiehlt sich, zum Wiedergeben einer intensiven OLTP-Anwendung das Distributed Replay Utility (mit zahlreichen aktiven gleichzeitigen Verbindungen oder hohem Durchsatz) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a42e-107">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="9a42e-108">Mit dem Distributed Replay Utility können Sie Ablaufverfolgungsdaten von mehreren Computern wiedergeben, um unternehmenswichtige Arbeitsauslastungen besser zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="9a42e-108">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="9a42e-109">Weitere Informationen finden Sie unter [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="9a42e-109">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="basic-replay-options"></a><span data-ttu-id="9a42e-110">Grundlegende Wiedergabeoptionen</span><span class="sxs-lookup"><span data-stu-id="9a42e-110">Basic Replay Options</span></span>  
 <span data-ttu-id="9a42e-111">**Wiedergabeserver**</span><span class="sxs-lookup"><span data-stu-id="9a42e-111">**Replay server**</span></span>  
 <span data-ttu-id="9a42e-112">Der Server ist der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , für die Sie die Ablaufverfolgung wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="9a42e-112">The server is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] against which you want to replay the trace.</span></span> <span data-ttu-id="9a42e-113">Der Server muss die unter [Replay Requirements](replay-requirements.md)beschriebenen Anforderungen für die Wiedergabe erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9a42e-113">The server must adhere to the replay requirements described in [Replay Requirements](replay-requirements.md)."</span></span>  
  
 <span data-ttu-id="9a42e-114">**In Datei speichern**</span><span class="sxs-lookup"><span data-stu-id="9a42e-114">**Save to file**</span></span>  
 <span data-ttu-id="9a42e-115">Die Ausgabedatei, in die das Ergebnis aus der Wiedergabe der Ablaufverfolgung geschrieben wird, das zu einem späteren Zeitpunkt angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a42e-115">The output file where the result of replaying the trace is written for later viewing.</span></span> <span data-ttu-id="9a42e-116">Standardmäßig zeigt [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] die Ergebnisse der Wiedergabe der Ablaufverfolgung nur auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="9a42e-116">By default, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays only the results of replaying the trace on the screen.</span></span>  
  
 <span data-ttu-id="9a42e-117">**In Tabelle speichern**</span><span class="sxs-lookup"><span data-stu-id="9a42e-117">**Save to table**</span></span>  
 <span data-ttu-id="9a42e-118">Die Datenbanktabelle, in die das Ergebnis aus der Wiedergabe der Ablaufverfolgung geschrieben wird, das zu einem späteren Zeitpunkt angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a42e-118">The database table where the result of replaying the trace is written for later viewing.</span></span>  
  
 <span data-ttu-id="9a42e-119">**Anzahl von Wiedergabethreads**</span><span class="sxs-lookup"><span data-stu-id="9a42e-119">**Number of replay threads**</span></span>  
 <span data-ttu-id="9a42e-120">Gibt die Anzahl der Threads an, die gleichzeitig verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9a42e-120">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="9a42e-121">Bei einem höheren Wert werden während der Wiedergabe mehr Ressourcen verbraucht, aber die Wiedergabe ist schneller.</span><span class="sxs-lookup"><span data-stu-id="9a42e-121">A higher number consumes more resources during replay, but replay is faster.</span></span> <span data-ttu-id="9a42e-122">Die Ereignisreihenfolge wird nicht vollständig beibehalten, wenn mehrere Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a42e-122">Event ordering is not fully maintained when multiple threads are used.</span></span>  
  
 <span data-ttu-id="9a42e-123">**Ereignisse in der Reihenfolge wiedergeben, in der ihr Ablauf verfolgt wurde**</span><span class="sxs-lookup"><span data-stu-id="9a42e-123">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="9a42e-124">Hiermit können Sie Debugmethoden, wie das Durchlaufen der einzelnen Ablaufverfolgungen, verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a42e-124">Allows you to use debugging methods such as stepping through each trace.</span></span> <span data-ttu-id="9a42e-125">Wenn diese Option nicht ausgewählt ist, wird bei der Wiedergabe nicht sichergestellt, dass die Ereignisse in der Reihenfolge, in der sie ursprünglich aufgezeichnet wurden, wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9a42e-125">If this option is not selected, replay does not guarantee that events are replayed in an order that is consistent with the order in which events were originally captured.</span></span>  
  
 <span data-ttu-id="9a42e-126">**Ereignisse mithilfe mehrerer Threads wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="9a42e-126">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="9a42e-127">Optimiert die Leistung und deaktiviert das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="9a42e-127">Optimizes performance and disables debugging.</span></span> <span data-ttu-id="9a42e-128">Die Ereignisse werden in der Reihenfolge wiedergegeben, in der sie für eine bestimmte Serverprozess-ID (SPID) aufgezeichnet wurden, aber die Reihenfolge der SPIDs ist nicht sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="9a42e-128">Events are replayed in the order they were recorded for a particular server process ID (SPID), but ordering of SPIDs is not guaranteed.</span></span>  
  
 <span data-ttu-id="9a42e-129">**Wiedergabeergebnisse anzeigen**</span><span class="sxs-lookup"><span data-stu-id="9a42e-129">**Display replay results**</span></span>  
 <span data-ttu-id="9a42e-130">Hiermit wird das Ergebnis der Wiedergabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a42e-130">Display the results of the replay.</span></span> <span data-ttu-id="9a42e-131">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="9a42e-131">This is the default option.</span></span> <span data-ttu-id="9a42e-132">Wenn die wiedergegebene Ablaufverfolgung sehr groß ist, sollten Sie diese Option eventuell deaktivieren, um Datenträgerspeicher zu sparen.</span><span class="sxs-lookup"><span data-stu-id="9a42e-132">If the trace you are replaying is very large, you may want to disable this to save disk space.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a42e-133">Für eine optimale Wiedergabeleistung wird empfohlen, Ereignisse mithilfe mehrerer Threads wiederzugeben und die Wiedergabeergebnisse nicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a42e-133">For best replay performance, we recommend that you select to replay events using multiple threads, and do not select to display the replay results.</span></span>  
  
## <a name="advanced-replay-options"></a><span data-ttu-id="9a42e-134">Erweiterte Wiedergabeoptionen</span><span class="sxs-lookup"><span data-stu-id="9a42e-134">Advanced Replay Options</span></span>  
 <span data-ttu-id="9a42e-135">**System-SPIDs wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="9a42e-135">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="9a42e-136">Alle System-SPIDs wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="9a42e-136">Replay all SPIDs.</span></span> <span data-ttu-id="9a42e-137">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="9a42e-137">This is the default option.</span></span>  
  
 <span data-ttu-id="9a42e-138">**Nur eine SPID wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="9a42e-138">**Replay one SPID only**</span></span>  
 <span data-ttu-id="9a42e-139">Gibt die SPID-Nummer wieder, die Sie aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="9a42e-139">Replays the SPID number you choose from the list.</span></span>  
  
 <span data-ttu-id="9a42e-140">**Wiedergabe nach Datum und Zeit beschränken**</span><span class="sxs-lookup"><span data-stu-id="9a42e-140">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="9a42e-141">Gibt die Ablaufverfolgung für die angegebene **Startzeit** und **Beendigungszeit**wieder.</span><span class="sxs-lookup"><span data-stu-id="9a42e-141">Replays the trace for the specified **Start time** and **End time**.</span></span>  
  
 <span data-ttu-id="9a42e-142">**Wartezeit für Systemüberwachung**</span><span class="sxs-lookup"><span data-stu-id="9a42e-142">**Health monitor wait interval**</span></span>  
 <span data-ttu-id="9a42e-143">Legt fest, wie lange ein Prozess ausgeführt werden kann, bevor die Systemüberwachung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a42e-143">Sets the amount of time a process is allowed to run before the health monitor terminates it.</span></span>  
  
 <span data-ttu-id="9a42e-144">**Abrufintervall für Systemüberwachung**</span><span class="sxs-lookup"><span data-stu-id="9a42e-144">**Health monitor poll interval**</span></span>  
 <span data-ttu-id="9a42e-145">Legt fest, wie oft die Systemüberwachung die Kandidaten wegen der Beendigung abruft.</span><span class="sxs-lookup"><span data-stu-id="9a42e-145">Sets how often the health monitor polls candidates for termination.</span></span>  
  
 <span data-ttu-id="9a42e-146">**Überwachung blockierter SQL Server-Prozesse aktivieren**</span><span class="sxs-lookup"><span data-stu-id="9a42e-146">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="9a42e-147">Legt fest, wie oft die Überwachung blockierter Prozesse nach blockierten oder blockierenden Prozessen sucht.</span><span class="sxs-lookup"><span data-stu-id="9a42e-147">Sets how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="about-the-health-monitor"></a><span data-ttu-id="9a42e-148">Informationen zur Systemüberwachung</span><span class="sxs-lookup"><span data-stu-id="9a42e-148">About the Health Monitor</span></span>  
 <span data-ttu-id="9a42e-149">Die Systemüberwachung ist ein Anwendungsthread, der die simulierten Prozesse bei der Wiedergabe einer Ablaufverfolgung überwacht und jene Prozesse beendet, die bei der Wiedergabe blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="9a42e-149">The health monitor is an application thread that monitors the simulated processes involved in replaying a trace, and ends those processes that are blocked within the replay.</span></span> <span data-ttu-id="9a42e-150">Auf der Registerkarte **Erweiterte Wiedergabeoptionen** des Dialogfelds **Wiedergabekonfiguration** können Sie angeben, nach wie vielen Sekunden die Systemüberwachung einen blockierten Prozess beenden soll (**Wartezeit für Systemüberwachung**).</span><span class="sxs-lookup"><span data-stu-id="9a42e-150">In the **Advanced Replay Options** tab of the **Replay Configuration** dialog box, you can specify how long the health monitor should wait in seconds before ending a blocked process (**Health monitor wait interval**).</span></span> <span data-ttu-id="9a42e-151">Wenn Sie dieses Intervall auf 0 festlegen, werden simulierte blockierende Prozesse bei der Wiedergabe der Ablaufverfolgung niemals durch die Systemüberwachung beendet.</span><span class="sxs-lookup"><span data-stu-id="9a42e-151">If you set this interval to 0, the health monitor never ends simulated blocking processes in the replaying trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a42e-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a42e-152">See Also</span></span>  
 <span data-ttu-id="9a42e-153">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="9a42e-153">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="9a42e-154">[Anforderungen für die Wiedergabe](replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="9a42e-154">[Replay Requirements](replay-requirements.md) </span></span>  
 [<span data-ttu-id="9a42e-155">Überlegungen zum Wiedergeben von Ablaufverfolgungen &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="9a42e-155">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)  
  
  
