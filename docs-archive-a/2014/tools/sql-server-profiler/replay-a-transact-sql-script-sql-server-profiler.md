---
title: Wiedergeben eines Transact-SQL-Skripts (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- scripts [SQL Server], traces
- replaying traces
ms.assetid: 9c0eb222-e6e3-4bc1-a25f-a41e962d361b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5abf22a1201ac927f12ef9e4cfdd1f6d3026d00a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722061"
---
# <a name="replay-a-transact-sql-script-sql-server-profiler"></a><span data-ttu-id="89f5c-102">Wiedergeben eines Transact-SQL-Skripts (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="89f5c-102">Replay a Transact-SQL Script (SQL Server Profiler)</span></span>
  <span data-ttu-id="89f5c-103">Verwenden Sie beim Testen von möglichen Lösungen für ein Leistungsproblem [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , um [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts wiederzugeben, und vergleichen Sie die Leistung vor und nach dem Ändern.</span><span class="sxs-lookup"><span data-stu-id="89f5c-103">When you test possible solutions to a performance problem, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, and compare performance before and after your changes.</span></span>  
  
### <a name="to-replay-a-transact-sql-script"></a><span data-ttu-id="89f5c-104">So geben Sie ein Transact-SQL-Skript wieder</span><span class="sxs-lookup"><span data-stu-id="89f5c-104">To replay a Transact-SQL script</span></span>  
  
1.  <span data-ttu-id="89f5c-105">Zeigen Sie im Menü **Datei** auf **Öffnen**, und klicken Sie dann auf **Skriptdatei**.</span><span class="sxs-lookup"><span data-stu-id="89f5c-105">On the **File** menu, point to **Open**, and then click **Script File**.</span></span>  
  
2.  <span data-ttu-id="89f5c-106">Wählen Sie die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei aus, die Sie öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="89f5c-106">Select the [!INCLUDE[tsql](../../includes/tsql-md.md)] script file you want to open.</span></span> <span data-ttu-id="89f5c-107">Stellen Sie sicher, dass das [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript die zum Wiedergeben erforderlichen Ereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="89f5c-107">Make sure that the [!INCLUDE[tsql](../../includes/tsql-md.md)] script contains events necessary for replay.</span></span> <span data-ttu-id="89f5c-108">Weitere Informationen finden Sie unter [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f5c-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
3.  <span data-ttu-id="89f5c-109">Klicken Sie im Menü **Wiedergeben** auf **Start**, und stellen Sie eine Verbindung mit dem Server her, auf dem das Skript wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="89f5c-109">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the script.</span></span>  
  
4.  <span data-ttu-id="89f5c-110">Überprüfen Sie im Dialogfeld **Wiedergabekonfiguration** die Einstellungen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="89f5c-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f5c-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89f5c-111">See Also</span></span>  
 <span data-ttu-id="89f5c-112">[Wiedergeben von Ablaufverfolgungen](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="89f5c-112">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="89f5c-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="89f5c-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
