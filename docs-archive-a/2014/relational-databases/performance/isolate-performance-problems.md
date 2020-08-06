---
title: Isolieren von Leistungsproblemen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- isolating performance problems [SQL Server]
- monitoring performance [SQL Server], isolating problems
- database monitoring [SQL Server], isolating problems
- tuning databases [SQL Server], isolating problems
- monitoring server performance [SQL Server], isolating problems
- database performance [SQL Server], isolating problems
- server performance [SQL Server], isolating problems
ms.assetid: 2eb425cb-9166-4027-ae08-c8fc2d236f44
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b42d780a8174ab57d00de72e8b00ef7af0abc17e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701102"
---
# <a name="isolate-performance-problems"></a><span data-ttu-id="a7445-102">Isolieren von Leistungsproblemen</span><span class="sxs-lookup"><span data-stu-id="a7445-102">Isolate Performance Problems</span></span>
  <span data-ttu-id="a7445-103">In den meisten Fällen ist es effektiver, mehrere [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]- oder Microsoft Windows-Tools gleichzeitig zu verwenden, um Leistungsprobleme mit der Datenbank zu isolieren, anstatt immer nur ein Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7445-103">It is often more effective to use several [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Microsoft Windows tools together to isolate database performance problems than to use one tool at a time.</span></span> <span data-ttu-id="a7445-104">So können Sie beispielsweise mithilfe der Funktion für den grafischen Ausführungsplan (auch Showplan genannt) Deadlocks in einer einzigen Abfrage erkennen.</span><span class="sxs-lookup"><span data-stu-id="a7445-104">For example, the graphical Execution Plan feature, also called Showplan, helps you quickly recognize deadlocks in a single query.</span></span> <span data-ttu-id="a7445-105">Einige andere Leistungsprobleme lassen sich wiederum einfacher ermitteln, indem Sie die Überwachungsfunktionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und Windows zusammen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7445-105">However, you can recognize some other performance problems more easily if you use the monitoring features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows together.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="a7445-106">kann für die Überwachung und Problembehandlung von Transact-SQL-Anweisungen und anwendungsbasierten Problemen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7445-106">can be used to monitor and troubleshoot Transact-SQL and application-related problems.</span></span> <span data-ttu-id="a7445-107">Mit dem Systemmonitor können Sie Hardwareprobleme und andere systembedingte Probleme überwachen.</span><span class="sxs-lookup"><span data-stu-id="a7445-107">System Monitor can be used to monitor hardware and other system-related problems.</span></span>  
  
 <span data-ttu-id="a7445-108">Sie können die folgenden Bereiche zur Problembehandlung überwachen:</span><span class="sxs-lookup"><span data-stu-id="a7445-108">You can monitor the following areas to troubleshoot problems:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a7445-109">oder [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungsbatches, die von Benutzeranwendungen übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="a7445-109">stored procedures or batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements submitted by user applications.</span></span>  
  
-   <span data-ttu-id="a7445-110">Benutzeraktivität, z. B. Sperren oder Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="a7445-110">User activity, such as blocking locks or deadlocks.</span></span>  
  
-   <span data-ttu-id="a7445-111">Hardwareaktivität, z. B. die Datenträgernutzung.</span><span class="sxs-lookup"><span data-stu-id="a7445-111">Hardware activity, such as disk usage.</span></span>  
  
 <span data-ttu-id="a7445-112">Mögliche Probleme sind:</span><span class="sxs-lookup"><span data-stu-id="a7445-112">Problems can include:</span></span>  
  
-   <span data-ttu-id="a7445-113">Fehler bei der Anwendungsentwicklung im Zusammenhang mit fehlerhaft geschriebenen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a7445-113">Application development errors involving incorrectly written [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="a7445-114">Hardwarefehler, z. B. Fehler im Zusammenhang mit den Datenträgern oder dem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="a7445-114">Hardware errors, such as disk- or network-related errors.</span></span>  
  
-   <span data-ttu-id="a7445-115">Zu häufiges Blockieren aufgrund einer fehlerhaft entworfenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a7445-115">Excessive blocking due to an incorrectly designed database.</span></span>  
  
## <a name="tools-for-common-performance-problems"></a><span data-ttu-id="a7445-116">Tools für häufig auftretende Leistungsprobleme</span><span class="sxs-lookup"><span data-stu-id="a7445-116">Tools for Common Performance Problems</span></span>  
 <span data-ttu-id="a7445-117">Genau so wichtig ist die sorgfältige Auswahl der Leistungsprobleme, die durch die einzelnen Tools überwacht oder optimiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a7445-117">Equally important is careful selection of the performance problem that you want each tool to monitor or tune.</span></span> <span data-ttu-id="a7445-118">Welches Tool und welcher Dienst geeignet sind, hängt von der Art des zu lösenden Leistungsproblems ab.</span><span class="sxs-lookup"><span data-stu-id="a7445-118">The tool and the utility depend on the type of performance problem you want to resolve.</span></span>  
  
 <span data-ttu-id="a7445-119">Die folgenden Themen enthalten Beschreibungen einer Vielzahl von Tools zur Überwachung und Optimierung sowie der durch sie feststellbaren Probleme.</span><span class="sxs-lookup"><span data-stu-id="a7445-119">The following topics describe a variety of monitoring and tuning tools and the problems they uncover.</span></span>  
  
 [<span data-ttu-id="a7445-120">Identifizieren von Engpässen</span><span class="sxs-lookup"><span data-stu-id="a7445-120">Identify Bottlenecks</span></span>](identify-bottlenecks.md)  
  
 [<span data-ttu-id="a7445-121">Überwachen der Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="a7445-121">Monitor Memory Usage</span></span>](../performance-monitor/monitor-memory-usage.md)  
  
  
