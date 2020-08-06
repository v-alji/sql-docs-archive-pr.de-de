---
title: Konfiguration für "SQL Server Profiler-Replay" (Erweiterte Wiedergabe Optionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.advanced.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: b4eb34f7-3af6-4a44-ba7e-2b8430ec3cd7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95070d8defb5b7778859ce470aaa8cfc85955ba6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721690"
---
# <a name="sql-server-profiler---replay-configuration-advanced-replay-options"></a><span data-ttu-id="50d43-102">SQL Server Profiler - Wiedergabekonfiguration (Erweiterte Wiedergabeoptionen)</span><span class="sxs-lookup"><span data-stu-id="50d43-102">SQL Server Profiler - Replay Configuration (Advanced Replay Options)</span></span>
  <span data-ttu-id="50d43-103">Mithilfe der Registerkarte **Erweiterte Wiedergabeoptionen** des Dialogfelds **Wiedergabekonfiguration** können Sie angeben, auf welche Weise eine Ablaufverfolgungsdatei wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="50d43-103">In the **Replay Configuration** dialog box, use the **Advanced Replay Options** tab to specify how to replay a trace file.</span></span>  
  
 <span data-ttu-id="50d43-104">Zum Anzeigen dieses Fensters öffnen Sie mithilfe von [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] eine Ablaufverfolgungsdatei oder -tabelle, die die zur Wiedergabe vorgesehenen Ereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="50d43-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="50d43-105">Weitere Informationen finden Sie unter [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50d43-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="50d43-106">Wenn die Ablaufverfolgungsdatei oder -tabelle geöffnet ist, klicken Sie im Menü **Wiedergeben** auf **Start**, und stellen Sie dann eine Verbindung mit der Instanz von SQL Server her, auf der die Ablaufverfolgung wiedergegeben werden soll. Klicken Sie anschließend auf die Registerkarte **Erweiterte Wiedergabeoptionen** .</span><span class="sxs-lookup"><span data-stu-id="50d43-106">While the trace file or table is open, on the **Replay** menu, click **Start**, connect to the instance of SQL Server where you want to replay the trace, and then click the **Advanced Replay Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="50d43-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="50d43-107">Options</span></span>  
 <span data-ttu-id="50d43-108">**System-SPIDs wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="50d43-108">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="50d43-109">Gibt an, ob [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] die Systemprozess-IDs (SPIDs) wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="50d43-109">Specifies whether [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] replays system process identifiers (SPIDs).</span></span>  
  
 <span data-ttu-id="50d43-110">**Nur eine SPID wiedergeben**</span><span class="sxs-lookup"><span data-stu-id="50d43-110">**Replay one SPID only**</span></span>  
 <span data-ttu-id="50d43-111">Gibt nur die Aktivität in der Ablaufverfolgungs-Quelldatei wieder, die mit der ausgewählten SPID in Beziehung steht.</span><span class="sxs-lookup"><span data-stu-id="50d43-111">Replays only the activity in the source trace file that is related to the selected SPID.</span></span>  
  
 <span data-ttu-id="50d43-112">**SPID für Wiedergabe**</span><span class="sxs-lookup"><span data-stu-id="50d43-112">**SPID to replay**</span></span>  
 <span data-ttu-id="50d43-113">Gibt an, welche SPID wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="50d43-113">Specify which SPID to replay.</span></span>  
  
 <span data-ttu-id="50d43-114">**Wiedergabe nach Datum und Zeit beschränken**</span><span class="sxs-lookup"><span data-stu-id="50d43-114">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="50d43-115">Durch Aktivieren dieses Kontrollkästchens kann festgelegt werden, dass nur ein Teil der Ablaufverfolgungs-Quelldatei wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50d43-115">Check to replay only a portion of the source trace file.</span></span>  
  
 <span data-ttu-id="50d43-116">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="50d43-116">**Start time**</span></span>  
 <span data-ttu-id="50d43-117">Datum und Uhrzeit in der Ablaufverfolgungs-Quelldatei, zu der die Wiedergabe beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="50d43-117">Date and time in the source trace file where the replay should start.</span></span>  
  
 <span data-ttu-id="50d43-118">**Endzeit**</span><span class="sxs-lookup"><span data-stu-id="50d43-118">**End time**</span></span>  
 <span data-ttu-id="50d43-119">Datum und Uhrzeit in der Ablaufverfolgungs-Quelldatei, zu der die Wiedergabe enden soll.</span><span class="sxs-lookup"><span data-stu-id="50d43-119">Date and time in the source trace file where the replay should stop.</span></span>  
  
 <span data-ttu-id="50d43-120">**Wartezeit für Systemüberwachung (Sek.)**</span><span class="sxs-lookup"><span data-stu-id="50d43-120">**Health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="50d43-121">Gibt die Wartezeit für die Wiedergabe in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="50d43-121">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="50d43-122">Der Standardwert ist 3600 Sekunden (1 Stunde).</span><span class="sxs-lookup"><span data-stu-id="50d43-122">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="50d43-123">Die Einstellung bestimmt den Zeitraum, in dem ein Prozess ausgeführt werden kann, bevor er von der Systemüberwachung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="50d43-123">This setting affects the amount of time a process is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="50d43-124">**Abrufintervall für Systemüberwachung (Sek.)**</span><span class="sxs-lookup"><span data-stu-id="50d43-124">**Health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="50d43-125">Gibt das Abrufinterval für die Systemüberwachung während der Wiedergabe in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="50d43-125">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="50d43-126">Der Standardwert ist 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="50d43-126">Default is 60 seconds.</span></span> <span data-ttu-id="50d43-127">Mit diesem Wert kann der Benutzer konfigurieren, wie oft die Systemüberwachung Informationen zu potenziell zu beendenden Vorgängen abruft.</span><span class="sxs-lookup"><span data-stu-id="50d43-127">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
 <span data-ttu-id="50d43-128">**Überwachung blockierter SQL Server-Prozesse aktivieren**</span><span class="sxs-lookup"><span data-stu-id="50d43-128">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="50d43-129">Aktiviert einen Prozess, mit dem nach blockierten oder blockierenden Prozessen gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="50d43-129">Enables a process that searches for blocked or blocking processes.</span></span>  
  
 <span data-ttu-id="50d43-130">**Wartezeit für die Überwachung blockierter Prozesse (Sek.)**</span><span class="sxs-lookup"><span data-stu-id="50d43-130">**Blocked processes monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="50d43-131">Konfiguriert die Häufigkeit, mit der mithilfe der Überwachung für blockierte Prozesse nach blockierten oder blockierenden Prozessen gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="50d43-131">Configures how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d43-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50d43-132">See Also</span></span>  
 <span data-ttu-id="50d43-133">[Wiedergeben einer Ablauf Verfolgungs Tabelle &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="50d43-133">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="50d43-134">[Wiedergeben einer Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="50d43-134">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="50d43-135">Wiedergeben von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="50d43-135">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
