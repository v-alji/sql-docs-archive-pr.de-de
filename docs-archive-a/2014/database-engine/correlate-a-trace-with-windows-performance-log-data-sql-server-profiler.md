---
title: Korrelieren einer Ablauf Verfolgung mit Windows-Leistungs Protokolldaten (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], logs
ms.assetid: e1b3072c-8daf-49a7-9895-c8cccd2adb95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 34575cf4270d817ecfbb5b2d1824831cc99454fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618262"
---
# <a name="correlate-a-trace-with-windows-performance-log-data-sql-server-profiler"></a><span data-ttu-id="cb313-102">Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="cb313-102">Correlate a Trace with Windows Performance Log Data (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]<span data-ttu-id="cb313-103">kann die Microsoft Windows System Monitor-Leistungsindikatoren mit-oder-Ereignissen korrelieren [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb313-103">can correlate Microsoft Windows System Monitor counters with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] events.</span></span> <span data-ttu-id="cb313-104">Der Windows-Systemmonitor protokolliert die Systemaktivität für angegebene Leistungsindikatoren in Leistungsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="cb313-104">Windows System Monitor logs system activity for specified counters in performance logs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb313-105">Informationen zur gemeinsamen Nutzung von Protokollen in verschiedenen Windows-Versionen finden Sie am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="cb313-105">For information about sharing logs among different versions of Windows, see the procedure at the end of this topic.</span></span>  
  
### <a name="to-correlate-a-trace-with-performance-log-data"></a><span data-ttu-id="cb313-106">So korrelieren Sie eine Ablaufverfolgung mit Leistungsprotokolldaten</span><span class="sxs-lookup"><span data-stu-id="cb313-106">To correlate a trace with performance log data</span></span>  
  
1.  <span data-ttu-id="cb313-107">Öffnen Sie eine Ablaufverfolgungsdatei oder -tabelle in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb313-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], open a saved trace file or trace table.</span></span> <span data-ttu-id="cb313-108">Ablaufverfolgungen, die noch ausgeführt werden und Ereignisdaten sammeln, können nicht korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="cb313-108">You cannot correlate a running trace that is still collecting event data.</span></span> <span data-ttu-id="cb313-109">Um die Genauigkeit der Korrelation mit den Systemmonitordaten sicherzustellen, muss die Ablaufverfolgung die beiden Datenspalten **StartTime** und **EndTime** enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb313-109">For accurate correlation with System Monitor data, the trace must contain both **StartTime** and **EndTime** data columns.</span></span>  
  
2.  <span data-ttu-id="cb313-110">Klicken Sie im  im Menü [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **Datei** auf **Leistungsdaten importieren**.</span><span class="sxs-lookup"><span data-stu-id="cb313-110">On the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu, click **Import Performance Data**.</span></span>  
  
3.  <span data-ttu-id="cb313-111">Wählen Sie im Dialogfeld **Öffnen** eine Datei aus, die ein Leistungsprotokoll enthält.</span><span class="sxs-lookup"><span data-stu-id="cb313-111">In the **Open** dialog box, select a file that contains a performance log.</span></span> <span data-ttu-id="cb313-112">Die Leistungsprotokolldaten und die Ablaufverfolgungsdaten müssen im selben Zeitraum aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="cb313-112">The performance log data must have been captured during the same time period in which the trace data is captured.</span></span>  
  
4.  <span data-ttu-id="cb313-113">Aktivieren Sie im Dialogfeld zum Beschränken der **Leistungsindikatoren** die Kontrollkästchen, die den Systemmonitorobjekten und den Leistungsindikatoren entsprechen, die Sie neben der Ablaufverfolgung anzeigen möchten. </span><span class="sxs-lookup"><span data-stu-id="cb313-113">In the **Performance Counters Limit** dialog box, select the check boxes that correspond to the System Monitor objects and counters that you want to display alongside the trace.</span></span> <span data-ttu-id="cb313-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb313-114">Click **OK.**</span></span>  
  
5.  <span data-ttu-id="cb313-115">Wählen Sie im Ablaufverfolgungs-Ereignisfenster ein Ereignis aus, oder navigieren Sie in diesem Fenster mithilfe der Pfeiltasten durch mehrere benachbarte Zeilen.</span><span class="sxs-lookup"><span data-stu-id="cb313-115">Select an event in the trace events window, or navigate through several adjacent rows in the trace events window by using the arrow keys.</span></span> <span data-ttu-id="cb313-116">Der senkrechte rote Strich im Datenfenster unter **Systemmonitor** weist auf die mit dem ausgewählten Ablaufverfolgungsereignis korrelierten Leistungsprotokolldaten hin.</span><span class="sxs-lookup"><span data-stu-id="cb313-116">The vertical red bar in the **System Monitor data** window indicates the performance log data that is correlated with the selected trace event.</span></span>  
  
6.  <span data-ttu-id="cb313-117">Klicken Sie im Systemmonitordiagramm auf einen Sie interessierenden Punkt.</span><span class="sxs-lookup"><span data-stu-id="cb313-117">Click a point of interest in the System Monitor graph.</span></span> <span data-ttu-id="cb313-118">Die entsprechende Ablaufverfolgungszeile, die zeitlich am nächsten ist, wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="cb313-118">The corresponding trace row that is nearest in time is selected.</span></span> <span data-ttu-id="cb313-119">Halten Sie die linke Maustaste gedrückt, und ziehen Sie den Mauszeiger innerhalb des Systemmonitordiagramms, um einen Zeitbereich zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="cb313-119">To zoom in on a time range, press and drag the mouse pointer in the System Monitor graph.</span></span>  
  
### <a name="to-create-performance-logs-that-can-be-shared-among-different-versions-of-windows"></a><span data-ttu-id="cb313-120">So erstellen Sie Leistungsprotokolle, die in verschiedenen Windows-Versionen verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="cb313-120">To create performance logs that can be shared among different versions of Windows</span></span>  
  
1.  <span data-ttu-id="cb313-121">Öffnen Sie **Verwaltung**in der Systemsteuerung, und doppelklicken Sie dann auf **Leistung**.</span><span class="sxs-lookup"><span data-stu-id="cb313-121">In Control Panel, open **Administrative Tools**, and then double click **Performance**.</span></span>  
  
2.  <span data-ttu-id="cb313-122">Erweitern Sie im Dialogfeld **Leistung** die Option **Leistungsdatenprotokolle und Warnungen**, klicken Sie mit der rechten Maustaste auf **Leistungsindikatorenprotokolle**, und klicken Sie dann auf **Neue Protokolleinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="cb313-122">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span>  
  
3.  <span data-ttu-id="cb313-123">Geben Sie einen Namen für das Leistungsindikatorenprotokoll ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb313-123">Type a name for the counter log, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="cb313-124">Klicken Sie auf der Registerkarte **Allgemein** auf **Indikatoren hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cb313-124">On the **General** tab, click **Add Counters**.</span></span>  
  
5.  <span data-ttu-id="cb313-125">Wählen Sie in der Liste **Leistungsobjekt** das Leistungsobjekt aus, das Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="cb313-125">In the **Performance object** list, select a performance object you want to monitor.</span></span> <span data-ttu-id="cb313-126">Die Namen der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Leistungsobjekte für Standardinstanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] beginnen mit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , benannte Instanzen beginnen mit MSSQL$*instanceName*.</span><span class="sxs-lookup"><span data-stu-id="cb313-126">The names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] performance objects for default instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] start with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and named instances start with MSSQL$*instanceName*.</span></span>  
  
6.  <span data-ttu-id="cb313-127">Fügen Sie Ihrer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz die benötigte Anzahl an Leistungsindikatoren und andere wichtige Werte, wie z. B. die Prozessorzeit und die Datenträgerzeit, hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb313-127">Add as many counters as necessary for your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and other important values, such as processor time and disk time.</span></span>  
  
7.  <span data-ttu-id="cb313-128">Wenn Sie alle gewünschten Leistungsindikatoren hinzugefügt haben, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="cb313-128">When you have finished adding counters, click **Close**.</span></span>  
  
8.  <span data-ttu-id="cb313-129">Legen Sie Werte für das Intervall **Daten erfassen alle** fest.</span><span class="sxs-lookup"><span data-stu-id="cb313-129">Set values for the **Sample data every** interval.</span></span> <span data-ttu-id="cb313-130">Beginnen Sie mit einem mittleren Stichprobenintervall, beispielsweise 5 Minuten, und passen Sie es dann bei Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="cb313-130">Start with a modest sampling interval, such as 5 minutes, and then adjust the interval if necessary.</span></span>  
  
9. <span data-ttu-id="cb313-131">Wählen Sie auf der Registerkarte **Protokolldateien** in der Liste **Protokolldateityp** die Option **Textdatei (durch Trennzeichen getrennt)** aus.</span><span class="sxs-lookup"><span data-stu-id="cb313-131">On the **Log Files** tab, choose **TextFile (Comma delimited)** from the **Log file type** list.</span></span> <span data-ttu-id="cb313-132">Durch Trennzeichen getrennte Textprotokolldateien können in verschiedenen Windows-Versionen freigegeben und später in Berichtstools, wie z. B. Microsoft Excel, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cb313-132">Comma-delimited text log files can be shared among different versions of Windows and can be viewed later in reporting tools such as Microsoft Excel.</span></span>  
  
10. <span data-ttu-id="cb313-133">Geben Sie auf der Registerkarte **Zeitplan** einen Zeitplan für die Überwachung an.</span><span class="sxs-lookup"><span data-stu-id="cb313-133">On the **Schedule** tab, specify a monitoring schedule.</span></span>  
  
11. <span data-ttu-id="cb313-134">Klicken Sie auf **OK** , um das Leistungsprotokoll zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb313-134">Click **OK** to create the performance log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb313-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb313-135">See Also</span></span>  
 <span data-ttu-id="cb313-136">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="cb313-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="cb313-137">Starten des SQL Server Profilers</span><span class="sxs-lookup"><span data-stu-id="cb313-137">Start SQL Server Profiler</span></span>](../tools/sql-server-profiler/start-sql-server-profiler.md)  
  
  
