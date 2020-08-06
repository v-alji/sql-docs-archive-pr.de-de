---
title: Ablauf Verfolgung und Wiedergabe von Ereignissen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7f0d570c70ef1cba080217e6c3a0f9b6055a4d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700934"
---
# <a name="tracing-and-replaying-events"></a><span data-ttu-id="27d1f-102">Verfolgen und Wiedergeben von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="27d1f-102">Tracing and Replaying Events</span></span>
  <span data-ttu-id="27d1f-103">In SMO bieten die Objekte `Trace` und `Replay` im <xref:Microsoft.SqlServer.Management.Trace>-Namespace programmgesteuerten Zugriff auf die [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)]-Funktionalität, mit der eine Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="27d1f-103">In SMO, the `Trace` and `Replay` objects in the <xref:Microsoft.SqlServer.Management.Trace> namespace provide programmatic access to the [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] functionality, which is used for monitoring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="27d1f-104">Daten über die einzelnen Ereignisse können aufgezeichnet und in einer Datei oder Tabelle zur späteren Analyse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="27d1f-104">You can capture and save data about each event to a file or table to analyze later.</span></span> <span data-ttu-id="27d1f-105">Beispielsweise können Sie eine Produktionsumgebung überwachen und feststellen, welche Prozeduren langsam ablaufen und dadurch die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="27d1f-105">For example, you can monitor a production environment to see which procedures are impeding performance by executing too slowly.</span></span>  
  
 <span data-ttu-id="27d1f-106">Die Objekte `Trace` und `Replay` bieten einen Objektsatz, mit dem Ablaufverfolgungen auf einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="27d1f-106">The `Trace` and `Replay` objects provide a set of objects that can be used to create traces on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27d1f-107">Diese Objekte können in Ihren eigenen Anwendungen verwendet werden, um manuell Ablaufverfolgungen für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27d1f-107">These objects can be used from within your own applications to create traces manually for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="27d1f-108">Darüber hinaus können SMO `Trace`-Objekte zum Lesen von SQL-Ablaufverfolgungsdateien und -tabellen verwendet werden, die durch die Überwachung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] oder DTS-Protokollierung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="27d1f-108">Additionally, SMO `Trace` objects can be used to read SQL Trace files and tables that were created by monitoring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], or DTS logging.</span></span>  
  
 <span data-ttu-id="27d1f-109">SMO `Trace`-Objekte ermöglichen die Durchführung der folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="27d1f-109">SMO `Trace` objects let you perform the following functions:</span></span>  
  
-   <span data-ttu-id="27d1f-110">Erstellen einer Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="27d1f-110">Create a trace.</span></span>  
  
-   <span data-ttu-id="27d1f-111">Festlegen von Filtern für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="27d1f-111">Set filters on the trace.</span></span>  
  
-   <span data-ttu-id="27d1f-112">Festlegen der zu verfolgenden Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="27d1f-112">Set the events that are being traced.</span></span>  
  
-   <span data-ttu-id="27d1f-113">Stoppen und Starten einer Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="27d1f-113">Stop or start a trace.</span></span>  
  
-   <span data-ttu-id="27d1f-114">Lesen von Ablaufverfolgungsdateien und Ablaufverfolgungstabellen.</span><span class="sxs-lookup"><span data-stu-id="27d1f-114">Read trace files, and trace tables.</span></span>  
  
-   <span data-ttu-id="27d1f-115">Abrufen von Informationen zu Ereignissen in einer Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="27d1f-115">Get information about events on a trace.</span></span>  
  
-   <span data-ttu-id="27d1f-116">Abrufen von Informationen zu Filtern in einer Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="27d1f-116">Get information about filters on a trace.</span></span>  
  
-   <span data-ttu-id="27d1f-117">Programmgesteuertes Bearbeiten von Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="27d1f-117">Manipulate trace data programmatically.</span></span>  
  
-   <span data-ttu-id="27d1f-118">Schreiben von Ablaufverfolgungstabellen und Ablaufverfolgungsdateien.</span><span class="sxs-lookup"><span data-stu-id="27d1f-118">Write trace tables and trace files.</span></span>  
  
-   <span data-ttu-id="27d1f-119">Wiedergeben von Ablaufverfolgungsdateien oder Ablaufverfolgungstabellen.</span><span class="sxs-lookup"><span data-stu-id="27d1f-119">Replay trace files or trace tables.</span></span>  
  
 <span data-ttu-id="27d1f-120">Die Ablauf Verfolgungs Daten aus dem `Trace` -Objekt und dem- `Replay` Objekt können von der SMO-Anwendung verwendet werden, oder Sie können mithilfe [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md)manuell untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="27d1f-120">The trace data from the `Trace` and `Replay` objects can be used by the SMO application, or it can be examined manually by using [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span></span> <span data-ttu-id="27d1f-121">Die Ablauf Verfolgungs Daten sind auch mit den gespeicherten Prozeduren der [SQL](../../sql-trace/sql-trace.md) -Ablauf Verfolgung kompatibel, die ebenfalls Ablauf Verfolgungs Funktionen bieten</span><span class="sxs-lookup"><span data-stu-id="27d1f-121">The trace data is also compatible with the [SQL Trace](../../sql-trace/sql-trace.md) stored procedures that also provide tracing capabilities.</span></span>  
  
 <span data-ttu-id="27d1f-122">Die SMO-Ablaufverfolgungsobjekte befinden sich im <xref:Microsoft.SqlServer.Management.Trace>-Namespace, für den ein Verweis auf die Datei Microsoft.SQLServer.ConnectionInfo.dll erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="27d1f-122">The SMO trace objects reside in the <xref:Microsoft.SqlServer.Management.Trace> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
 <span data-ttu-id="27d1f-123">Für die Objekte `Trace` und `Replay` ist ein <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A>-Objekt erforderlich, um eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="27d1f-123">The `Trace` and `Replay` objects require a <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> object to establish a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27d1f-124">Das <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt befindet sich im <xref:Microsoft.SqlServer.Management.Common>-Namespace, für den ein Verweis auf die Datei Microsoft.SQLServer.ConnectionInfo.dll erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="27d1f-124">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object resides in the <xref:Microsoft.SqlServer.Management.Common> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27d1f-125">Die Objekte `Trace` und `Replay` werden nicht auf 64-Bit-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27d1f-125">The `Trace` and `Replay` objects are not supported on a 64-bit platform.</span></span>  
  
  
