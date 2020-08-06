---
title: Extrahieren eines Skripts aus einer Ablaufverfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6633fafb8a39b189093044ef39694afa601af7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694926"
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a><span data-ttu-id="95864-102">Extrahieren eines Skripts aus einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="95864-102">Extract a Script from a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="95864-103">In diesem Thema wird das Extrahieren von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ereignissen aus einer Ablaufverfolgungsdatei oder -tabelle sowie das Speichern in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95864-103">This topic describes how to extract [!INCLUDE[tsql](../../includes/tsql-md.md)] events from a trace file or table and save them as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a><span data-ttu-id="95864-104">So extrahieren Sie ein Transact-SQL-Skript aus einer Ablaufverfolgungsdatei oder -tabelle</span><span class="sxs-lookup"><span data-stu-id="95864-104">To extract a Transact-SQL script from a trace file or table</span></span>  
  
1.  <span data-ttu-id="95864-105">Öffnen Sie eine Ablaufverfolgungsdatei oder -tabelle, die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ereignisse enthält, die Sie in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="95864-105">Open a trace file or table that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] events that you want to save to a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="95864-106">Weitere Informationen finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) oder den Optimierungsratgeber von [Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md)die richtigen Ereignisse und Spalten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="95864-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="95864-107">Zeigen Sie im Menü **Datei** auf **Exportieren**, zeigen Sie auf **SQL Server-Ereignisse extrahieren**, und klicken Sie dann auf **Transact-SQL-Ereignisse extrahieren**.</span><span class="sxs-lookup"><span data-stu-id="95864-107">On the **File** menu, point to **Export**, point to **Extract SQL Server Events**, and then click **Extract Transact-SQL Events**.</span></span>  
  
3.  <span data-ttu-id="95864-108">Geben Sie im Dialogfeld **Speichern unter** einen Namen für die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Datei ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="95864-108">In the **Save As** dialog box, type a name for the [!INCLUDE[tsql](../../includes/tsql-md.md)] file, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95864-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95864-109">See Also</span></span>  
 [<span data-ttu-id="95864-110">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="95864-110">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
