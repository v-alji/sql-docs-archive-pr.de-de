---
title: Erstellen eines Transact-SQL-Skripts zum Ausführen einer Ablaufverfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], running
- scripts [SQL Server], traces
ms.assetid: 6b0e2519-998d-40d5-b8ba-5e6a773f91a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3d4b4bebb2a3e05e3de12e59c53ccca9c980afd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694937"
---
# <a name="create-a-transact-sql-script-for-running-a-trace-sql-server-profiler"></a><span data-ttu-id="00744-102">Erstellen eines Transact-SQL-Skripts zum Ausführen einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="00744-102">Create a Transact-SQL Script for Running a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="00744-103">In diesem Thema wird beschrieben, wie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]ein Transact-SQL-Skript anhand einer vorhandenen Ablaufverfolgungsdatei oder -tabelle erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="00744-103">This topic describes how to create a Transact-SQL script from an existing trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-transact-sql-script-to-run-a-trace"></a><span data-ttu-id="00744-104">So erstellen Sie ein Transact-SQL-Skript für die Ausführung einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="00744-104">To create a Transact-SQL script to run a trace</span></span>  
  
1.  <span data-ttu-id="00744-105">Öffnen Sie eine Ablaufverfolgungsdatei oder -tabelle.</span><span class="sxs-lookup"><span data-stu-id="00744-105">Open a trace file or table.</span></span> <span data-ttu-id="00744-106">Weitere Informationen finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) oder den Optimierungsratgeber von [Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md)die richtigen Ereignisse und Spalten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="00744-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="00744-107">Zeigen Sie im Menü**Datei**auf **Exportieren**und auf **Skript für Ablaufverfolgungsdefinition erstellen**, und klicken Sie dann auf die Version, die dem für die Ablaufverfolgung vorgesehenen Server entspricht.</span><span class="sxs-lookup"><span data-stu-id="00744-107">On the**File**menu, point to **Export**, point to **Script Trace Definition**, and then click the version that corresponds to the server you want to trace.</span></span>  
  
3.  <span data-ttu-id="00744-108">Geben Sie im Dialogfeld **Speichern unter** einen Namen für die Skriptdatei ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="00744-108">In the **Save As** dialog box, enter a name for the script file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00744-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00744-109">See Also</span></span>  
 <span data-ttu-id="00744-110">[Vorlagen und Berechtigungen in SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="00744-110">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="00744-111">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="00744-111">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
