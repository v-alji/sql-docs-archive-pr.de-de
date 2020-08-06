---
title: Wiedergeben einer Ablauf Verfolgungs Tabelle (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 6a0ad817-3d8d-4495-889d-c66a7ef9e8bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: f3c26858fa852686bc3d9ccf4a26d47e04852647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717116"
---
# <a name="replay-a-trace-table-sql-server-profiler"></a><span data-ttu-id="e28e8-102">Wiedergeben einer Ablaufverfolgungstabelle (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e28e8-102">Replay a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="e28e8-103">Die Wiedergabe bezeichnet die Möglichkeit, eine gespeicherte Ablaufverfolgung zu öffnen und erneut wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="e28e8-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="e28e8-104">verfügt über eine Multithread-Wiedergabe-Engine, die Benutzerverbindungen und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung simulieren kann.</span><span class="sxs-lookup"><span data-stu-id="e28e8-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e28e8-105">Die Wiedergabe ist nützlich für die Behandlung von Anwendungs- oder Prozessproblemen.</span><span class="sxs-lookup"><span data-stu-id="e28e8-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="e28e8-106">Wenn Sie das Problem identifiziert und Korrekturen implementiert haben, sollten Sie die Ablaufverfolgung, in der das mögliche Problem aufgetreten ist, für die korrigierte Anwendung bzw. den korrigierten Prozess erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="e28e8-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="e28e8-107">Geben Sie anschließend die ursprüngliche Ablaufverfolgung wieder, und vergleichen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e28e8-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="e28e8-108">Neben anderen Ereignisklassen, die Sie überwachen möchten, müssen bestimmte Ereignisklassen erfasst werden, um die Wiedergabe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e28e8-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="e28e8-109">Diese Ereignisse werden standardmäßig erfasst, wenn Sie die **TSQL_Replay** -Ablaufverfolgungsvorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="e28e8-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="e28e8-110">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e28e8-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-table"></a><span data-ttu-id="e28e8-111">So geben Sie eine Ablaufverfolgungstabelle wieder</span><span class="sxs-lookup"><span data-stu-id="e28e8-111">To replay a trace table</span></span>  
  
1.  <span data-ttu-id="e28e8-112">Öffnen Sie eine Ablaufverfolgungstabelle, die die für die Wiedergabe erforderlichen Ereignisklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="e28e8-112">Open a trace table that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="e28e8-113">Klicken Sie im Menü **Wiedergeben** auf **Start**, und stellen Sie eine Verbindung mit der Serverinstanz her, in der Sie die Ablaufverfolgung wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="e28e8-113">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="e28e8-114">Geben Sie im Dialogfeld **Wiedergabekonfiguration** auf der Registerkarte **Grundlegende Wiedergabeoptionen** einen Wert für **Wiedergabeserver**an.</span><span class="sxs-lookup"><span data-stu-id="e28e8-114">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify **Replay server**.</span></span> <span data-ttu-id="e28e8-115">Klicken Sie auf **Ändern** , um den im Feld **Wiedergabeserver** angezeigten Server zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e28e8-115">Click **Change** to change the server that is displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="e28e8-116">Wählen Sie optional eines der folgenden Ziele zum Speichern der Wiedergabe aus:</span><span class="sxs-lookup"><span data-stu-id="e28e8-116">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="e28e8-117">**In Datei speichern** gibt eine Datei an, in der die Wiedergabe gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="e28e8-117">**Save to file,** which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="e28e8-118">**In Tabelle speichern**gibt eine Tabelle an, in der die Wiedergabe gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="e28e8-118">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="e28e8-119">Wählen Sie entweder **Ereignisse in der Reihenfolge wiedergeben, in der ihr Ablauf verfolgt wurde**oder **Ereignisse mithilfe mehrerer Threads wiedergeben**.</span><span class="sxs-lookup"><span data-stu-id="e28e8-119">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="e28e8-120">In der folgenden Tabelle wird der Unterschied zwischen diesen Einstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e28e8-120">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="e28e8-121">Option</span><span class="sxs-lookup"><span data-stu-id="e28e8-121">Option</span></span>|<span data-ttu-id="e28e8-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e28e8-122">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="e28e8-123">**Ereignisse in der Reihenfolge wiedergeben, in der ihr Ablauf verfolgt wurde**</span><span class="sxs-lookup"><span data-stu-id="e28e8-123">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="e28e8-124">Gibt Ereignisse in der Reihenfolge wieder, in der sie aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="e28e8-124">Replays events in the order they were recorded.</span></span> <span data-ttu-id="e28e8-125">Diese Option aktiviert das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="e28e8-125">This option enables debugging.</span></span>|  
    |<span data-ttu-id="e28e8-126">**Ereignisse mithilfe mehrerer Threads wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="e28e8-126">**Replay events using multiple threads**</span></span>|<span data-ttu-id="e28e8-127">Diese Option verwendet mehrere Threads, um die einzelnen Ereignisse unabhängig von der Reihenfolge wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="e28e8-127">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="e28e8-128">Diese Option optimiert die Leistung.</span><span class="sxs-lookup"><span data-stu-id="e28e8-128">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="e28e8-129">Wählen Sie **Wiedergabeergebnisse anzeigen** aus, um die Wiedergabe während des Auftretens anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e28e8-129">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="e28e8-130">Optional können Sie auf **Erweiterte Wiedergabeoptionen**klicken, um die folgenden Optionen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="e28e8-130">Optionally, click the **Advanced Replay Options**tab to specify the following options:</span></span>  
  
    -   <span data-ttu-id="e28e8-131">Wählen Sie **System-SPIDs wiedergeben**aus, um alle Serverprozess-IDs (SPIDs) wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="e28e8-131">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="e28e8-132">Wählen Sie **Nur eine SPID wiedergeben**aus, um die Wiedergabe auf Prozesse zu beschränken, die zu einer bestimmten SPID gehören.</span><span class="sxs-lookup"><span data-stu-id="e28e8-132">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="e28e8-133">Geben Sie im Dialogfeld **SPID für Wiedergabe**die SPID ein.</span><span class="sxs-lookup"><span data-stu-id="e28e8-133">In the **SPID to replay**box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="e28e8-134">Wählen Sie **Wiedergabe nach Datum und Zeit beschränken**aus, um Ereignisse wiederzugeben, die während eines bestimmten Zeitraums aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e28e8-134">To replay events that occurred during a specific time period, select **Limit replay by date and time**.</span></span> <span data-ttu-id="e28e8-135">Wählen Sie ein Datum und eine Uhrzeit für **Startzeit**und **Beendigungszeit**aus, um den in der Wiedergabe enthaltenen Zeitraum anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e28e8-135">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="e28e8-136">Konfigurieren Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Systemüberwachungsoptionen, um zu steuern, wie**Prozesse während der Wiedergabe verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e28e8-136">To control how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28e8-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e28e8-137">See Also</span></span>  
 <span data-ttu-id="e28e8-138">[Erforderliche Berechtigungen zum Ausführen von SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e28e8-138">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e28e8-139">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="e28e8-139">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="e28e8-140">[Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e28e8-140">[Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="e28e8-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e28e8-141">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
