---
title: Erstellen einer Ablauf Verfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], creating
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7d73333bbf0ba985ed4952e03584b4e4c130ab6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694957"
---
# <a name="create-a-trace-sql-server-profiler"></a><span data-ttu-id="f1229-102">Erstellen einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f1229-102">Create a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="f1229-103">In diesem Thema wird beschrieben, wie Sie mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] eine Ablaufverfolgung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f1229-103">This topic describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="f1229-104">So erstellen Sie eine Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f1229-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="f1229-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="f1229-105">On the **File** menu, click **New Trace**, and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="f1229-106">Das Dialogfeld **Ablaufverfolgungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1229-106">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1229-107">Wenn die Option **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** ausgewählt wurde, wird die Ablaufverfolgung sofort gestartet, ohne dass das Dialogfeld **Ablaufverfolgungseigenschaften** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1229-107">The **Trace Properties** dialog box fails to appear, and the trace begins instead, if **Start tracing immediately after making connection** is selected.</span></span> <span data-ttu-id="f1229-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="f1229-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="f1229-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="f1229-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="f1229-110">Wählen Sie in der Liste **Vorlage verwenden** eine Ablaufverfolgungsvorlage als Basis für die Ablaufverfolgung aus, oder wählen Sie **Leer** aus, wenn Sie keine Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f1229-110">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="f1229-111">Führen Sie eine der folgenden Aktionen aus, um die Ergebnisse der Ablaufverfolgung zu speichern:</span><span class="sxs-lookup"><span data-stu-id="f1229-111">To save the trace results, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f1229-112">Klicken Sie auf **In Datei speichern**, um die Ablaufverfolgung in einer Datei aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="f1229-112">Click **Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="f1229-113">Geben Sie einen Wert für **Maximale Dateigröße festlegen**an.</span><span class="sxs-lookup"><span data-stu-id="f1229-113">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="f1229-114">Der Standardwert ist 5 MB.</span><span class="sxs-lookup"><span data-stu-id="f1229-114">The default value is 5 megabytes (MB).</span></span>  
  
         <span data-ttu-id="f1229-115">Sie können auch die Option **Dateirollover aktivieren** auswählen, um automatisch neue Dateien zu erstellen, sobald die maximale Dateigröße erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="f1229-115">Optionally, select **Enable file rollover** to automatically create new files when the maximum file size is reached.</span></span> <span data-ttu-id="f1229-116">Darüber hinaus können Sie die Option **Ablaufverfolgungsdaten von Serverprozessen**auswählen. Dadurch werden die Ablaufverfolgungsdaten nicht durch die Clientanwendung, sondern durch den Dienst verarbeitet, der die Ablaufverfolgung ausführt.</span><span class="sxs-lookup"><span data-stu-id="f1229-116">You can also optionally select **Server processes trace data**, which causes the service that is running the trace to process trace data instead of the client application.</span></span> <span data-ttu-id="f1229-117">Wenn der Server die Ablaufverfolgungsdaten verarbeitet, werden auch bei hoher Belastung keine Ereignisse ausgelassen, wodurch die Serverleistung natürlich beeinträchtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1229-117">When the server processes trace data, no events are skipped even under stress conditions, but server performance may be affected.</span></span>  
  
    -   <span data-ttu-id="f1229-118">Klicken Sie auf **In Tabelle speichern** , um die Ablaufverfolgung in einer Datenbanktabelle zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="f1229-118">Click **Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="f1229-119">Klicken Sie optional auf **Maximale Zeilenzahl festlegen**, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="f1229-119">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="f1229-120">Wenn Sie die Ergebnisse der Ablaufverfolgung nicht in einer Datei oder Tabelle speichern, können Sie die Ablaufverfolgung nur anzeigen, solange [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="f1229-120">When you do not save the trace results to a file or table, you can view the trace while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is open.</span></span> <span data-ttu-id="f1229-121">Sobald die Ablaufverfolgung beendet und [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]geschlossen wird, gehen die Ergebnisse der Ablaufverfolgung verloren.</span><span class="sxs-lookup"><span data-stu-id="f1229-121">However, you lose the trace results after you stop the trace and close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f1229-122">Damit das nicht geschieht, klicken Sie im Menü **Datei** auf **Speichern** . Auf diese Weise werden die Ergebnisse gespeichert, bevor Sie [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]schließen.</span><span class="sxs-lookup"><span data-stu-id="f1229-122">To avoid losing the trace results in this way, click **Save** on the **File** menu to save the results before you close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
5.  <span data-ttu-id="f1229-123">Aktivieren Sie optional das Kontrollkästchen **Beendigungszeit für Ablaufverfolgung aktivieren** , und geben Sie das Datum und die Uhrzeit zum Beenden der Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="f1229-123">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="f1229-124">Klicken Sie auf die Registerkarte **Ereignisauswahl**, um Ereignisse, Datenspalten oder Filter hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f1229-124">To add or remove events, data columns or filters, click the **Events Selection**tab.</span></span> <span data-ttu-id="f1229-125">Weitere Informationen finden Sie unter [Angeben von Ereignissen und Datenspalten für eine Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f1229-125">For more information, see: [Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span></span>  
  
7.  <span data-ttu-id="f1229-126">Klicken Sie auf **Ausführen** , um die Ablaufverfolgung zu starten.</span><span class="sxs-lookup"><span data-stu-id="f1229-126">Click **Run** to start the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1229-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1229-127">See Also</span></span>  
 <span data-ttu-id="f1229-128">[Erforderliche Berechtigungen zum Ausführen von SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f1229-128">[Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f1229-129">[Vorlagen und Berechtigungen in SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="f1229-129">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="f1229-130">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f1229-130">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="f1229-131">Korrelieren einer Ablaufverfolgung mit Windows-Leistungsprotokolldaten &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f1229-131">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
