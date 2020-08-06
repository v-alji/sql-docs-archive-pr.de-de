---
title: Analysieren von Deadlocks mit SQL Server Profiler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- process nodes [SQL Server Profiler]
- Profiler [SQL Server Profiler], deadlocks
- deadlocks [SQL Server], identifying cause
- resource nodes [SQL Server Profiler]
- graphs [SQL Server Profiler]
- SQL Server Profiler, deadlocks
- events [SQL Server], deadlocks
- edges [SQL Server Profiler]
ms.assetid: 72d6718f-501b-4ea6-b344-c0e653f19561
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3414cda74d75dbacf10ed98b6fc6d50da2feaa18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694974"
---
# <a name="analyze-deadlocks-with-sql-server-profiler"></a><span data-ttu-id="1ea38-102">Analysieren von Deadlocks mit SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1ea38-102">Analyze Deadlocks with SQL Server Profiler</span></span>
  <span data-ttu-id="1ea38-103">Verwenden Sie [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , um die Ursache für einen Deadlock zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1ea38-103">Use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to identify the cause of a deadlock.</span></span> <span data-ttu-id="1ea38-104">Ein Deadlock tritt dann auf, wenn eine zyklische Abhängigkeit zwischen mindestens zwei Threads oder Prozessen für eine beliebige Gruppe von Ressourcen in SQL Server besteht.</span><span class="sxs-lookup"><span data-stu-id="1ea38-104">A deadlock occurs when there is a cyclic dependency between two or more threads, or processes, for some set of resources within SQL Server.</span></span> <span data-ttu-id="1ea38-105">Mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]können Sie eine Ablaufverfolgung erstellen, die Deadlockereignisse zu Analysezwecken aufzeichnet, wiedergibt und anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1ea38-105">Using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a trace that records, replays, and displays deadlock events for analysis.</span></span>  
  
 <span data-ttu-id="1ea38-106">Um eine Ablaufverfolgung für Deadlockereignisse auszuführen, fügen Sie die **Deadlock graph** -Ereignisklasse zu einer Ablaufverfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ea38-106">To trace deadlock events, add the **Deadlock graph** event class to a trace.</span></span> <span data-ttu-id="1ea38-107">Diese Ereignisklasse füllt die **TextData** -Datenspalte in der Ablaufverfolgung mit XML-Daten zum Prozess sowie zu vom Deadlock betroffenen Objekten auf.</span><span class="sxs-lookup"><span data-stu-id="1ea38-107">This event class populates the **TextData** data column in the trace with XML data about the process and objects that are involved in the deadlock.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="1ea38-108">kann das XML-Dokument in eine Deadlock-XML-Datei (.xdl) extrahieren, die Sie später in SQL Server Management Studio anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="1ea38-108">can extract the XML document to a deadlock XML (.xdl) file which you can view later in SQL Server Management Studio.</span></span> <span data-ttu-id="1ea38-109">Sie können [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] so konfigurieren, dass **Deadlock graph** -Ereignisse entweder in eine einzelne Datei mit allen **Deadlock graph** -Ereignissen oder in separate Dateien extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ea38-109">You can configure [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to extract **Deadlock graph** events to a single file that contains all **Deadlock graph** events, or to separate files.</span></span> <span data-ttu-id="1ea38-110">Das Extrahieren kann auf eine der folgenden Arten ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1ea38-110">This extraction can be done in any of the following ways:</span></span>  
  
-   <span data-ttu-id="1ea38-111">Beim Konfigurieren der Ablaufverfolgung über die Registerkarte **Ereignisextraktionseinstellungen** . Beachten Sie, dass diese Registerkarte erst angezeigt wird, wenn Sie das **Deadlock graph** -Ereignis auf der Registerkarte **Ereignisauswahl** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="1ea38-111">At trace configuration time, using the **Events Extraction Settings** tab. Note that this tab does not appear until you select the **Deadlock graph** event on the **Events Selection** tab.</span></span>  
  
-   <span data-ttu-id="1ea38-112">Mithilfe der Option **SQL Server-Ereignisse extrahieren** im Menü **Datei**</span><span class="sxs-lookup"><span data-stu-id="1ea38-112">Using the **Extract SQL Server Events** option on the **File** menu.</span></span>  
  
-   <span data-ttu-id="1ea38-113">Einzelne Ereignisse können auch extrahiert und gespeichert werden, indem Sie mit der rechten Maustaste auf ein bestimmtes Ereignis klicken und **Ereignisdaten extrahieren**auswählen.</span><span class="sxs-lookup"><span data-stu-id="1ea38-113">Individual events can also be extracted and saved by right-clicking a specific event and choosing **Extract Event Data**.</span></span>  
  
## <a name="deadlock-graphs"></a><span data-ttu-id="1ea38-114">Deadlockdiagramme</span><span class="sxs-lookup"><span data-stu-id="1ea38-114">Deadlock Graphs</span></span>  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="1ea38-115">und [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verwenden Deadlock-Wartediagramme zum Beschreiben von Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="1ea38-115">and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use a deadlock wait-for graph to describe a deadlock.</span></span> <span data-ttu-id="1ea38-116">Das Deadlock-Wartediagramm enthält Prozessknoten, Ressourcenknoten und Rahmen, die die Beziehungen zwischen den Prozessen und Ressourcen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1ea38-116">The deadlock wait-for graph contains process nodes, resource nodes, and edges representing the relationships between the processes and the resources.</span></span> <span data-ttu-id="1ea38-117">Die folgende Tabelle enthält die Definitionen der Komponenten in Wartediagrammen:</span><span class="sxs-lookup"><span data-stu-id="1ea38-117">The components of wait-for graphs are defined in the following table:</span></span>  
  
 <span data-ttu-id="1ea38-118">Prozessknoten</span><span class="sxs-lookup"><span data-stu-id="1ea38-118">Process node</span></span>  
 <span data-ttu-id="1ea38-119">Ein Thread, der eine Aufgabe ausführt, beispielsweise INSERT, UPDATE oder DELETE</span><span class="sxs-lookup"><span data-stu-id="1ea38-119">A thread that performs a task; for example, INSERT, UPDATE, or DELETE.</span></span>  
  
 <span data-ttu-id="1ea38-120">Ressourcenknoten</span><span class="sxs-lookup"><span data-stu-id="1ea38-120">Resource node</span></span>  
 <span data-ttu-id="1ea38-121">Ein Datenbankobjekt, beispielsweise eine Tabelle, ein Index oder eine Zeile</span><span class="sxs-lookup"><span data-stu-id="1ea38-121">A database object; for example, a table, index, or row.</span></span>  
  
 <span data-ttu-id="1ea38-122">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1ea38-122">Edge</span></span>  
 <span data-ttu-id="1ea38-123">Die Beziehung zwischen einen Prozess und einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="1ea38-123">A relationship between a process and a resource.</span></span> <span data-ttu-id="1ea38-124">Ein `request`-Rahmen tritt auf, wenn ein Prozess auf eine Ressource wartet.</span><span class="sxs-lookup"><span data-stu-id="1ea38-124">A `request` edge occurs when a process waits for a resource.</span></span> <span data-ttu-id="1ea38-125">Ein `owner`-Rahmen tritt auf, wenn eine Ressource auf einen Prozess wartet.</span><span class="sxs-lookup"><span data-stu-id="1ea38-125">An `owner` edge occurs when a resource waits for a process.</span></span> <span data-ttu-id="1ea38-126">Die Rahmenbeschreibung enthält den Sperrmodus.</span><span class="sxs-lookup"><span data-stu-id="1ea38-126">The lock mode is included in the edge description.</span></span> <span data-ttu-id="1ea38-127">Beispiel: **Modus: X**.</span><span class="sxs-lookup"><span data-stu-id="1ea38-127">For example, **Mode: X**.</span></span>  
  
## <a name="deadlock-process-node"></a><span data-ttu-id="1ea38-128">Deadlock-Prozessknoten</span><span class="sxs-lookup"><span data-stu-id="1ea38-128">Deadlock Process Node</span></span>  
 <span data-ttu-id="1ea38-129">In einem Wartediagramm enthält der Prozessknoten Informationen zum Prozess.</span><span class="sxs-lookup"><span data-stu-id="1ea38-129">In a wait-for graph, the process node contains information about the process.</span></span> <span data-ttu-id="1ea38-130">In der folgenden Tabelle werden die Komponenten eines Prozesses erläutert.</span><span class="sxs-lookup"><span data-stu-id="1ea38-130">The following table explains the components of a process.</span></span>  
  
|<span data-ttu-id="1ea38-131">Komponente</span><span class="sxs-lookup"><span data-stu-id="1ea38-131">Component</span></span>|<span data-ttu-id="1ea38-132">Definition</span><span class="sxs-lookup"><span data-stu-id="1ea38-132">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="1ea38-133">Serverprozess-ID</span><span class="sxs-lookup"><span data-stu-id="1ea38-133">Server process Id</span></span>|<span data-ttu-id="1ea38-134">Serverprozessbezeichner (Server Process Identifier, SPID). Ein vom Server zugewiesener Bezeichner für den Prozess, der im Besitz der Sperre ist.</span><span class="sxs-lookup"><span data-stu-id="1ea38-134">Server process identifier (SPID), a server assigned identifier for the process owning the lock.</span></span>|  
|<span data-ttu-id="1ea38-135">Serverbatch-ID</span><span class="sxs-lookup"><span data-stu-id="1ea38-135">Server batch Id</span></span>|<span data-ttu-id="1ea38-136">Serverbatch-Bezeichner (Server Batch Identifier, SBID)</span><span class="sxs-lookup"><span data-stu-id="1ea38-136">Server batch identifier (SBID).</span></span>|  
|<span data-ttu-id="1ea38-137">Ausführungskontext-ID</span><span class="sxs-lookup"><span data-stu-id="1ea38-137">Execution context Id</span></span>|<span data-ttu-id="1ea38-138">Ausführungskontext-Bezeichner (Execution Context ID, ECID).</span><span class="sxs-lookup"><span data-stu-id="1ea38-138">Execution context identifier (ECID).</span></span> <span data-ttu-id="1ea38-139">Die Ausführungskontext-ID für einen bestimmten Thread, der einer bestimmten SPID zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ea38-139">The execution context ID of a given thread associated with a specific SPID.</span></span><br /><br /> <span data-ttu-id="1ea38-140">ECID = {0,1,2,3, *...n*}, wobei 0 immer den übergeordneten Thread oder Hauptthread darstellt und {1,2,3, *...n*} die Subthreads.</span><span class="sxs-lookup"><span data-stu-id="1ea38-140">ECID = {0,1,2,3, *...n*}, where 0 always represents the main or parent thread, and {1,2,3, *...n*} represent the subthreads.</span></span>|  
|<span data-ttu-id="1ea38-141">Deadlockpriorität</span><span class="sxs-lookup"><span data-stu-id="1ea38-141">Deadlock priority</span></span>|<span data-ttu-id="1ea38-142">Deadlockpriorität für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="1ea38-142">Deadlock priority for the process.</span></span> <span data-ttu-id="1ea38-143">Weitere Informationen zu den möglichen Werten finden Sie unter [SET DEADLOCK_PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-deadlock-priority-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ea38-143">For more information about possible values, see [SET DEADLOCK_PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-deadlock-priority-transact-sql).</span></span>|  
|<span data-ttu-id="1ea38-144">Verwendetes Protokoll</span><span class="sxs-lookup"><span data-stu-id="1ea38-144">Log Used</span></span>|<span data-ttu-id="1ea38-145">Protokollspeicherplatz, der vom Prozess belegt wird</span><span class="sxs-lookup"><span data-stu-id="1ea38-145">Amount of log space used by the process.</span></span>|  
|<span data-ttu-id="1ea38-146">Besitzer-ID</span><span class="sxs-lookup"><span data-stu-id="1ea38-146">Owner Id</span></span>|<span data-ttu-id="1ea38-147">Transaktions-ID für die Prozesse, die Transaktionen verwenden und sich aufgrund einer Sperre gegenwärtig im Wartezustand befinden</span><span class="sxs-lookup"><span data-stu-id="1ea38-147">Transaction ID for the processes which are using transactions and currently waiting on a lock.</span></span>|  
|<span data-ttu-id="1ea38-148">Transaktionsdeskriptor</span><span class="sxs-lookup"><span data-stu-id="1ea38-148">Transaction descriptor</span></span>|<span data-ttu-id="1ea38-149">Zeiger auf den Transaktionsdeskriptor, der den Transaktionszustand beschreibt</span><span class="sxs-lookup"><span data-stu-id="1ea38-149">Pointer to the transaction descriptor that describes the state of the transaction.</span></span>|  
|<span data-ttu-id="1ea38-150">Eingabepuffer</span><span class="sxs-lookup"><span data-stu-id="1ea38-150">Input buffer</span></span>|<span data-ttu-id="1ea38-151">Eingabepuffer des aktuellen Prozesses. Er definiert den Ereignistyp und die ausgeführte Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1ea38-151">Input buffer of the current process, defines the type of event and the statement being executed.</span></span> <span data-ttu-id="1ea38-152">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="1ea38-152">Possible values include:</span></span><br /><br /> <span data-ttu-id="1ea38-153">**Sprache**</span><span class="sxs-lookup"><span data-stu-id="1ea38-153">**Language**</span></span><br /><br /> <span data-ttu-id="1ea38-154">**RPC**</span><span class="sxs-lookup"><span data-stu-id="1ea38-154">**RPC**</span></span><br /><br /> <span data-ttu-id="1ea38-155">**None**</span><span class="sxs-lookup"><span data-stu-id="1ea38-155">**None**</span></span>|  
|<span data-ttu-id="1ea38-156">-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1ea38-156">Statement</span></span>|<span data-ttu-id="1ea38-157">Der Anweisungstyp.</span><span class="sxs-lookup"><span data-stu-id="1ea38-157">Type of statement.</span></span> <span data-ttu-id="1ea38-158">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="1ea38-158">Possible values are:</span></span><br /><br /> <span data-ttu-id="1ea38-159">**NOP**</span><span class="sxs-lookup"><span data-stu-id="1ea38-159">**NOP**</span></span><br /><br /> <span data-ttu-id="1ea38-160">**SELECT**</span><span class="sxs-lookup"><span data-stu-id="1ea38-160">**SELECT**</span></span><br /><br /> <span data-ttu-id="1ea38-161">**UPDATE**</span><span class="sxs-lookup"><span data-stu-id="1ea38-161">**UPDATE**</span></span><br /><br /> <span data-ttu-id="1ea38-162">**INSERT**</span><span class="sxs-lookup"><span data-stu-id="1ea38-162">**INSERT**</span></span><br /><br /> <span data-ttu-id="1ea38-163">**DELETE**</span><span class="sxs-lookup"><span data-stu-id="1ea38-163">**DELETE**</span></span><br /><br /> <span data-ttu-id="1ea38-164">**Unbekannt**</span><span class="sxs-lookup"><span data-stu-id="1ea38-164">**Unknown**</span></span>|  
  
## <a name="deadlock-resource-node"></a><span data-ttu-id="1ea38-165">Deadlock-Ressourcenknoten</span><span class="sxs-lookup"><span data-stu-id="1ea38-165">Deadlock Resource Node</span></span>  
 <span data-ttu-id="1ea38-166">Bei einem Deadlock warten zwei Prozesse auf eine Ressource, die vom jeweils anderen Prozess beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="1ea38-166">In a deadlock, two processes are each waiting for a resource held by the other process.</span></span> <span data-ttu-id="1ea38-167">In einem Deadlockdiagramm werden die Ressourcen als Ressourcenknoten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ea38-167">In a deadlock graph, the resources are displayed as resource nodes.</span></span>  
  
  