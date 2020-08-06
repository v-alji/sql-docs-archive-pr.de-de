---
title: Konfiguration für "SQL Server Profiler-Replay" (grundlegende Wiedergabe Optionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: 85a1dec6-9bbc-477a-86c5-b463db9ebb31
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cbf433c3108294909d91f7860136c0755b39b46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721686"
---
# <a name="sql-server-profiler---replay-configuration-basic-replay-options"></a><span data-ttu-id="99b0c-102">SQL Server Profiler-Wiedergabekonfiguration (Grundlegende Wiedergabeoptionen)</span><span class="sxs-lookup"><span data-stu-id="99b0c-102">SQL Server Profiler - Replay Configuration (Basic Replay Options)</span></span>
  <span data-ttu-id="99b0c-103">Mithilfe der Seite **Grundlegende Wiedergabeoptionen** des Dialogfelds **Wiedergabekonfiguration** können Sie angeben, auf welche Weise eine Ablaufverfolgungsdatei oder -tabelle wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="99b0c-103">In the **Replay Configuration** dialog box, use the **Basic Replay Options** page to specify how to replay a trace file or table.</span></span>  
  
 <span data-ttu-id="99b0c-104">Zum Anzeigen dieses Fensters öffnen Sie mithilfe von [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] eine Ablaufverfolgungsdatei oder -tabelle, die die zur Wiedergabe vorgesehenen Ereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="99b0c-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="99b0c-105">Weitere Informationen finden Sie unter [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99b0c-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="99b0c-106">Wenn die Ablaufverfolgungsdatei oder -tabelle geöffnet ist, klicken Sie im Menü **Wiedergeben** auf **Start**, und stellen Sie dann eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] her, auf der die Ablaufverfolgung wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="99b0c-106">While the trace file or table is open, on the **Replay** menu, click **Start**, and then connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where you want to replay the trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="99b0c-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="99b0c-107">Options</span></span>  
 <span data-ttu-id="99b0c-108">**Wiedergabeserver**</span><span class="sxs-lookup"><span data-stu-id="99b0c-108">**Replay server**</span></span>  
 <span data-ttu-id="99b0c-109">Zeigt die Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] an, mit der eine Verbindung für die Wiedergabe hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="99b0c-109">Displays the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to for the replay.</span></span>  
  
 <span data-ttu-id="99b0c-110">**Ändern...**</span><span class="sxs-lookup"><span data-stu-id="99b0c-110">**Change...**</span></span>  
 <span data-ttu-id="99b0c-111">Öffnet das Dialogfeld **Verbindung mit Server herstellen** , um eine Verbindung mit einem anderen Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="99b0c-111">Launches the **Connect to Server** dialog box to connect to another server.</span></span>  
  
 <span data-ttu-id="99b0c-112">**In Datei speichern**</span><span class="sxs-lookup"><span data-stu-id="99b0c-112">**Save to file**</span></span>  
 <span data-ttu-id="99b0c-113">Speichert die Wiedergabeergebnisse in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="99b0c-113">Save the replay results to a file.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="99b0c-114">zeigt das Standarddialogfeld zum Speichern von Dateien an, in dem Sie einen Speicherort für die Datei angeben können.</span><span class="sxs-lookup"><span data-stu-id="99b0c-114">displays the standard file dialog, where you can specify the location to save the file.</span></span>  
  
 <span data-ttu-id="99b0c-115">**In Tabelle speichern**</span><span class="sxs-lookup"><span data-stu-id="99b0c-115">**Save to table**</span></span>  
 <span data-ttu-id="99b0c-116">Speichert die Wiedergabeergebnisse in einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="99b0c-116">Save the replay results to a table.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="99b0c-117">wird ein Dialogfeld zum Auswählen der Tabelle angezeigt, in dem Sie einen Speicherort für die Tabelle angeben können.</span><span class="sxs-lookup"><span data-stu-id="99b0c-117">displays the table selection dialog, where you can specify the location to save the table.</span></span>  
  
 <span data-ttu-id="99b0c-118">**Anzahl von Wiedergabethreads**</span><span class="sxs-lookup"><span data-stu-id="99b0c-118">**Number of replay threads**</span></span>  
 <span data-ttu-id="99b0c-119">Gibt die Anzahl der Threads an, die gleichzeitig verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="99b0c-119">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="99b0c-120">Bei einer höheren Anzahl werden zwar mehr Ressourcen beansprucht, dafür erfolgt die Wiedergabe schneller und in höherem Maße gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="99b0c-120">A higher number consumes more resources during replay, but replay is faster and more concurrent.</span></span>  
  
 <span data-ttu-id="99b0c-121">**Ereignisse in der Reihenfolge wiedergeben, in der ihr Ablauf verfolgt wurde**</span><span class="sxs-lookup"><span data-stu-id="99b0c-121">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="99b0c-122">Gibt Ereignisse sequenziell wieder.</span><span class="sxs-lookup"><span data-stu-id="99b0c-122">Replay events sequentially.</span></span> <span data-ttu-id="99b0c-123">Verwenden Sie diese Option, wenn Sie eine Ablaufverfolgung zum Debuggen wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="99b0c-123">Use this option if you are replaying a trace for debugging.</span></span>  
  
 <span data-ttu-id="99b0c-124">**Ereignisse mithilfe mehrerer Threads wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="99b0c-124">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="99b0c-125">Gibt die Ereignisse gleichzeitig wieder.</span><span class="sxs-lookup"><span data-stu-id="99b0c-125">Replay events concurrently.</span></span> <span data-ttu-id="99b0c-126">Diese Option ist zwar schneller als die sequenzielle Wiedergabe von Ereignissen, dafür ist kein Debugging verfügbar.</span><span class="sxs-lookup"><span data-stu-id="99b0c-126">This option is faster than replaying events sequentially, but disables debugging.</span></span> <span data-ttu-id="99b0c-127">Die Ereignisse werden je nach dazugehöriger Systemprozess-ID (SPID) geordnet.</span><span class="sxs-lookup"><span data-stu-id="99b0c-127">The events are ordered within their system process identifiers (SPID).</span></span>  
  
 <span data-ttu-id="99b0c-128">**Wiedergabeergebnisse anzeigen**</span><span class="sxs-lookup"><span data-stu-id="99b0c-128">**Display replay results**</span></span>  
 <span data-ttu-id="99b0c-129">Zeigt die Wiedergabeergebnisse in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]an.</span><span class="sxs-lookup"><span data-stu-id="99b0c-129">Display replay results in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b0c-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99b0c-130">See Also</span></span>  
 <span data-ttu-id="99b0c-131">[Wiedergeben einer Ablauf Verfolgungs Tabelle &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="99b0c-131">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="99b0c-132">[Wiedergeben einer Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="99b0c-132">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="99b0c-133">Wiedergeben von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="99b0c-133">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
