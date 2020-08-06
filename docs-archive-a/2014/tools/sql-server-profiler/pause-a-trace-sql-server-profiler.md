---
title: Anhalten einer Ablauf Verfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694929"
---
# <a name="pause-a-trace-sql-server-profiler"></a><span data-ttu-id="56dba-102">Anhalten einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="56dba-102">Pause a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="56dba-103">Durch Anhalten einer Ablaufverfolgung wird verhindert, dass weitere Ereignisdaten vor dem Neustarten der Ablaufverfolgung aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="56dba-103">Pausing a trace prevents further event data from being captured until the trace is restarted.</span></span>  
  
 <span data-ttu-id="56dba-104">Durch Anhalten einer Ablaufverfolgung wird verhindert, dass Ereignisdaten vor dem Neustarten der Ablaufverfolgung aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="56dba-104">When you pause a trace, you prevent event data from being captured until the trace is restarted.</span></span> <span data-ttu-id="56dba-105">Durch das Neustarten einer Ablaufverfolgung werden die Ablaufverfolgungsvorgänge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="56dba-105">Restarting a trace lets trace operations resume.</span></span> <span data-ttu-id="56dba-106">Zuvor aufgezeichnete Daten gehen nach einem Neustart nicht verloren.</span><span class="sxs-lookup"><span data-stu-id="56dba-106">No previously captured data is lost after a restart.</span></span> <span data-ttu-id="56dba-107">Wird die Ablaufverfolgung neu gestartet, wird die Aufzeichnung der Daten von diesem Punkt an fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="56dba-107">When the trace is restarted, data capturing resumes from that point onward.</span></span> <span data-ttu-id="56dba-108">Während eine Ablaufverfolgung angehalten wird, können Sie den Namen, Ereignisse, Spalten und Filter ändern.</span><span class="sxs-lookup"><span data-stu-id="56dba-108">While a trace is paused, you can change the name, events, columns, and filters.</span></span> <span data-ttu-id="56dba-109">Es ist allerdings nicht möglich, die Ziele, an die Sie die Ablaufverfolgungsdaten senden, oder die Serververbindung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="56dba-109">However, you cannot change the destinations to which you are sending the trace data, nor change the server connection.</span></span>  
  
### <a name="to-pause-a-trace"></a><span data-ttu-id="56dba-110">So halten Sie eine Ablaufverfolgung an</span><span class="sxs-lookup"><span data-stu-id="56dba-110">To pause a trace</span></span>  
  
1.  <span data-ttu-id="56dba-111">Wählen Sie ein Fenster aus, das eine derzeit ausgeführte Ablaufverfolgung enthält.</span><span class="sxs-lookup"><span data-stu-id="56dba-111">Select a window that contains a running trace.</span></span>  
  
2.  <span data-ttu-id="56dba-112">Klicken Sie im Menü **Datei** auf **Ablaufverfolgung anhalten**.</span><span class="sxs-lookup"><span data-stu-id="56dba-112">On the **File** menu, click **Pause Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dba-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56dba-113">See Also</span></span>  
 [<span data-ttu-id="56dba-114">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="56dba-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
