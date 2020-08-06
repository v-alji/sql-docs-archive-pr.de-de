---
title: Abbrechen einer Ablauf Verfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], stopping
- stopping traces
ms.assetid: 47c4f33d-63e0-4444-bec8-4c1c91f8e25c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 501ea4a4838f8e2ea42fc475c486466d48020a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719147"
---
# <a name="stop-a-trace-sql-server-profiler"></a><span data-ttu-id="4fa24-102">Beenden einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="4fa24-102">Stop a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="4fa24-103">In diesem Thema wird das Beenden einer derzeit ausgeführten Ablaufverfolgung mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4fa24-103">This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="4fa24-104">Durch Beenden einer Ablaufverfolgung wird die Aufzeichnung der Daten abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4fa24-104">Stopping a trace stops data from being captured.</span></span> <span data-ttu-id="4fa24-105">Wenn eine Ablaufverfolgung beendet wurde, kann sie nur dann ohne den Verlust zuvor aufgezeichneter Daten erneut gestartet werden, wenn die Daten in einer Ablaufverfolgungsdatei oder -tabelle aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="4fa24-105">After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table.</span></span> <span data-ttu-id="4fa24-106">Außerdem können Sie die gesammelten Daten in einer Tabelle oder Datei speichern, nachdem eine Ablaufverfolgung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4fa24-106">You can also save the collected data to a table or file after stopping a trace.</span></span> <span data-ttu-id="4fa24-107">Alle zuvor ausgewählten Ablaufverfolgungseigenschaften bleiben beim Beenden einer Ablaufverfolgung erhalten.</span><span class="sxs-lookup"><span data-stu-id="4fa24-107">All trace properties that were previously selected are preserved when a trace is stopped.</span></span> <span data-ttu-id="4fa24-108">Wenn eine Ablaufverfolgung beendet wird, können Sie den Namen, Ereignisse, Spalten und Filter ändern.</span><span class="sxs-lookup"><span data-stu-id="4fa24-108">When a trace is stopped, you can change the name, events, columns, and filters.</span></span>  
  
### <a name="to-stop-a-trace"></a><span data-ttu-id="4fa24-109">So beenden Sie eine Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4fa24-109">To stop a trace</span></span>  
  
1.  <span data-ttu-id="4fa24-110">Wählen Sie eine derzeit ausgeführte Ablaufverfolgung aus.</span><span class="sxs-lookup"><span data-stu-id="4fa24-110">Select a trace that is running.</span></span>  
  
2.  <span data-ttu-id="4fa24-111">Klicken Sie im Menü **Datei** auf **Ablaufverfolgung beenden**.</span><span class="sxs-lookup"><span data-stu-id="4fa24-111">On the **File** menu, click **Stop Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa24-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fa24-112">See Also</span></span>  
 [<span data-ttu-id="4fa24-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4fa24-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
