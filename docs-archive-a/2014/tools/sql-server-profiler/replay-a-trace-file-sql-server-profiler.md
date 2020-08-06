---
title: Wiedergeben einer Ablauf Verfolgungs Datei (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 9e361275-c8fd-4499-8389-242cf8e27415
author: stevestein
ms.author: sstein
ms.openlocfilehash: d3a9f007b9b6d2b46be43abdb10db286a75c33fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722058"
---
# <a name="replay-a-trace-file-sql-server-profiler"></a><span data-ttu-id="f404f-102">Wiedergeben einer Ablaufverfolgungsdatei (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f404f-102">Replay a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="f404f-103">Die Wiedergabe bezeichnet die Möglichkeit, eine gespeicherte Ablaufverfolgung zu öffnen und erneut wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="f404f-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f404f-104">verfügt über eine Multithread-Wiedergabe-Engine, die Benutzerverbindungen und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung simulieren kann.</span><span class="sxs-lookup"><span data-stu-id="f404f-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f404f-105">Die Wiedergabe ist nützlich für die Behandlung von Anwendungs- oder Prozessproblemen.</span><span class="sxs-lookup"><span data-stu-id="f404f-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="f404f-106">Wenn Sie das Problem identifiziert und Korrekturen implementiert haben, sollten Sie die Ablaufverfolgung, in der das mögliche Problem aufgetreten ist, für die korrigierte Anwendung bzw. den korrigierten Prozess erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="f404f-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="f404f-107">Geben Sie anschließend die ursprüngliche Ablaufverfolgung wieder, und vergleichen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f404f-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="f404f-108">Neben anderen Ereignisklassen, die Sie überwachen möchten, müssen bestimmte Ereignisklassen erfasst werden, um die Wiedergabe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f404f-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="f404f-109">Diese Ereignisse werden standardmäßig erfasst, wenn Sie die **TSQL_Replay** -Ablaufverfolgungsvorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="f404f-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="f404f-110">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f404f-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-file"></a><span data-ttu-id="f404f-111">So geben Sie eine Ablaufverfolgungsdatei wieder</span><span class="sxs-lookup"><span data-stu-id="f404f-111">To replay a trace file</span></span>  
  
1.  <span data-ttu-id="f404f-112">Zeigen Sie im Menü **Datei** auf **Öffnen**, und klicken Sie dann auf **Ablaufverfolgungsdatei**.</span><span class="sxs-lookup"><span data-stu-id="f404f-112">On the **File** menu, point to **Open**, and then click **Trace File**.</span></span> <span data-ttu-id="f404f-113">Wählen Sie eine Ablaufverfolgungsdatei aus, die die für die Wiedergabe erforderlichen Ereignisklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="f404f-113">Select a trace file that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="f404f-114">Klicken Sie im Menü **Wiedergeben** auf **Start**, und stellen Sie eine Verbindung mit der Serverinstanz her, in der Sie die Ablaufverfolgung wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="f404f-114">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="f404f-115">Geben Sie im Dialogfeld **Wiedergabekonfiguration** auf der Registerkarte **Grundlegende Wiedergabeoptionen** den **Wiedergabeserver**an.</span><span class="sxs-lookup"><span data-stu-id="f404f-115">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify the **Replay server**.</span></span> <span data-ttu-id="f404f-116">Klicken Sie auf **Ändern** , um den im Feld **Wiedergabeserver** angezeigten Server zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f404f-116">Click **Change** to change the server displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="f404f-117">Wählen Sie optional eines der folgenden Ziele zum Speichern der Wiedergabe aus:</span><span class="sxs-lookup"><span data-stu-id="f404f-117">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="f404f-118">**In Datei speichern**gibt eine Datei an, in der die Wiedergabe gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f404f-118">**Save to file**, which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="f404f-119">**In Tabelle speichern**gibt eine Tabelle an, in der die Wiedergabe gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f404f-119">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="f404f-120">Wählen Sie entweder **Ereignisse in der Reihenfolge wiedergeben, in der ihr Ablauf verfolgt wurde**oder **Ereignisse mithilfe mehrerer Threads wiedergeben**.</span><span class="sxs-lookup"><span data-stu-id="f404f-120">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="f404f-121">In der folgenden Tabelle wird der Unterschied zwischen diesen Einstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f404f-121">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="f404f-122">Option</span><span class="sxs-lookup"><span data-stu-id="f404f-122">Option</span></span>|<span data-ttu-id="f404f-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f404f-123">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="f404f-124">**Ereignisse in der Reihenfolge wiedergeben, in der ihr Ablauf verfolgt wurde**</span><span class="sxs-lookup"><span data-stu-id="f404f-124">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="f404f-125">Gibt Ereignisse in der Reihenfolge wieder, in der sie aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="f404f-125">Replays events in the order they were recorded.</span></span> <span data-ttu-id="f404f-126">Diese Option aktiviert das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="f404f-126">This option enables debugging.</span></span>|  
    |<span data-ttu-id="f404f-127">**Ereignisse mithilfe mehrerer Threads wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="f404f-127">**Replay events using multiple threads**</span></span>|<span data-ttu-id="f404f-128">Diese Option verwendet mehrere Threads, um die einzelnen Ereignisse unabhängig von der Reihenfolge wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="f404f-128">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="f404f-129">Diese Option optimiert die Leistung.</span><span class="sxs-lookup"><span data-stu-id="f404f-129">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="f404f-130">Wählen Sie **Wiedergabeergebnisse anzeigen** aus, um die Wiedergabe während des Auftretens anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f404f-130">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="f404f-131">Klicken Sie optional auf die Registerkarte **Erweiterte Wiedergabeoptionen**, um folgende Optionen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f404f-131">Optionally click the **Advanced Replay Options**tab to configure the following options:</span></span>  
  
    -   <span data-ttu-id="f404f-132">Wählen Sie **System-SPIDs wiedergeben**aus, um alle Serverprozess-IDs (SPIDs) wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="f404f-132">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="f404f-133">Wählen Sie **Nur eine SPID wiedergeben**aus, um die Wiedergabe auf Prozesse zu beschränken, die zu einer bestimmten SPID gehören.</span><span class="sxs-lookup"><span data-stu-id="f404f-133">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="f404f-134">Geben Sie im Feld **SPID für Wiedergabe** die SPID ein.</span><span class="sxs-lookup"><span data-stu-id="f404f-134">In the **SPID to replay** box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="f404f-135">Wählen Sie **Wiedergabe nach Datum und Zeit beschränken**aus, um Ereignisse wiederzugeben, die in einem bestimmten Zeitraum aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="f404f-135">To replay events that occurred during a specific time period, select **Limit the replay by date and time**.</span></span> <span data-ttu-id="f404f-136">Wählen Sie ein Datum und eine Uhrzeit für **Startzeit**und **Beendigungszeit**aus, um den in der Wiedergabe enthaltenen Zeitraum anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f404f-136">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="f404f-137">Konfigurieren Sie **Systemüberwachungsoptionen**, um zu steuern, wie SQL Server die Prozesse während der Wiedergabe verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f404f-137">To control how SQL Server manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f404f-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f404f-138">See Also</span></span>  
 <span data-ttu-id="f404f-139">[Erforderliche Berechtigungen zum Ausführen von SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f404f-139">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f404f-140">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="f404f-140">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="f404f-141">[Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f404f-141">[Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="f404f-142">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f404f-142">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
