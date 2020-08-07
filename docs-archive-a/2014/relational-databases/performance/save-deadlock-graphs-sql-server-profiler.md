---
title: Speichern von Deadlockdiagrammen (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], saving deadlock graphs
- graphs [SQL Server]
- saving deadlock graphs
ms.assetid: bf1fc906-abd6-4a89-842e-da0d66b2defe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cdd0bd808ba4b934e5b2d91c9079909acf6e3997
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619774"
---
# <a name="save-deadlock-graphs-sql-server-profiler"></a><span data-ttu-id="d6370-102">Speichern von Deadlockdiagrammen (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="d6370-102">Save Deadlock Graphs (SQL Server Profiler)</span></span>
  <span data-ttu-id="d6370-103">In diesem Thema wird beschrieben, wie ein Deadlock Graph mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d6370-103">This topic describes how to save a deadlock graph by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="d6370-104">Deadlock Graphs werden als XML-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6370-104">Deadlock graphs are saved as XML files.</span></span>  
  
### <a name="to-save-deadlock-graph-events-separately"></a><span data-ttu-id="d6370-105">So speichern Sie Deadlock Graph-Ereignisse separat</span><span class="sxs-lookup"><span data-stu-id="d6370-105">To save deadlock graph events separately</span></span>  
  
1.  <span data-ttu-id="d6370-106">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung zu einer Instanz von SQL Server her.</span><span class="sxs-lookup"><span data-stu-id="d6370-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="d6370-107">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6370-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6370-108">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="d6370-108">If **Start tracing immediately after making connection** is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="d6370-109">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="d6370-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="d6370-110">Geben Sie im Dialogfeld „Ablaufverfolgungseigenschaften“ im Feld**Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="d6370-110">In the Trace Properties dialog box, type a name for the trace in the**Trace name** box.</span></span>  
  
3.  <span data-ttu-id="d6370-111">Wählen Sie in der Liste **Vorlage verwenden** eine Ablaufverfolgungsvorlage als Basis für die Ablaufverfolgung aus, oder wählen Sie **Leer** aus, wenn Sie keine Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d6370-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="d6370-112">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="d6370-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="d6370-113">Aktivieren Sie das Kontrollkästchen**In Datei speichern** , um die Ablaufverfolgung in einer Datei aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d6370-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="d6370-114">Geben Sie einen Wert für **Maximale Dateigröße festlegen**an.</span><span class="sxs-lookup"><span data-stu-id="d6370-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="d6370-115">Aktivieren Sie optional die Kontrollkästchen **Dateirollover aktivieren** und **Ablaufverfolgungsdaten von Serverprozessen**.</span><span class="sxs-lookup"><span data-stu-id="d6370-115">Optionally, select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="d6370-116">Aktivieren Sie das Kontrollkästchen **In Tabelle speichern** , um die Ablaufverfolgung in einer Datenbanktabelle aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d6370-116">Select the **Save to table** check box to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="d6370-117">Klicken Sie optional auf **Maximale Zeilenzahl festlegen**, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="d6370-117">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="d6370-118">Aktivieren Sie optional das Kontrollkästchen **Beendigungszeit für Ablaufverfolgung aktivieren** , und geben Sie das Datum und die Uhrzeit zum Beenden der Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="d6370-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="d6370-119">Klicken Sie auf die Registerkarte **Ereignisauswahl**.</span><span class="sxs-lookup"><span data-stu-id="d6370-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="d6370-120">Erweitern Sie in der Datenspalte **Ereignisse**die Ereigniskategorie **Sperren**, und aktivieren Sie das Kontrollkästchen **Deadlock Graph**.</span><span class="sxs-lookup"><span data-stu-id="d6370-120">In the **Events**data column, expand the **Locks**event category, and then select the **Deadlock graph**check box.</span></span> <span data-ttu-id="d6370-121">Falls die Ereigniskategorie „Sperren“ nicht verfügbar ist, aktivieren Sie **Alle Ereignisse anzeigen** , damit sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d6370-121">If the Locks event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="d6370-122">Das Dialogfeld **Ereignisextraktionseinstellungen**wird dem Dialogfeld **Ablaufverfolgungseigenschaften**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d6370-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="d6370-123">Aktivieren Sie auf der Registerkarte **Ereignisextraktionseinstellungen**das Kontrollkästchen **Deadlock-XML-Ereignisse separat speichern**.</span><span class="sxs-lookup"><span data-stu-id="d6370-123">On the **Events Extraction Settings**tab, click **Save Deadlock XML Events Separately**.</span></span>  
  
9. <span data-ttu-id="d6370-124">Geben Sie im Dialogfeld **Speichern unter** den Namen der Datei ein, in der die Deadlock Graph-Ereignisse gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d6370-124">In the **Save As** dialog box, enter the name of the file in which to store the deadlock graph events.</span></span>  
  
10. <span data-ttu-id="d6370-125">Klicken Sie auf **Alle Deadlock-XML-Batches in einer einzelnen Datei** , um alle Deadlock Graph-Ereignisse in einer einzigen XML-Datei zu speichern, oder klicken Sie auf **Jeder Deadlock-XML-Batch in einer eigenen Datei**, um für jedes Deadlockdiagramm eine neue XML-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6370-125">Click **All Deadlock XML batches in a single file** to save all deadlock graph events in a single XML file, or click **Each Deadlock XML batch in a distinct file**to create a new XML file for each deadlock graph.</span></span>  
  
 <span data-ttu-id="d6370-126">Nach dem Speichern der Deadlockdatei können Sie sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]öffnen.</span><span class="sxs-lookup"><span data-stu-id="d6370-126">After you have saved the deadlock file, you can open the file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d6370-127">Weitere Informationen finden Sie unter [Öffnen, anzeigen und Drucken einer Deadlockdatei &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d6370-127">For more information, see [Open, View, and Print a Deadlock File &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6370-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6370-128">See Also</span></span>  
 [<span data-ttu-id="d6370-129">Analysieren von Deadlocks mit SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d6370-129">Analyze Deadlocks with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler.md)  
  
  
