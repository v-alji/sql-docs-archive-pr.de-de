---
title: Separates Speichern von Showplan XML-Ereignissen (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML events
- saving Showplan XML events
- events [SQL Server], Showplan XML
ms.assetid: 33320a7a-36e8-401c-876d-5b82c49abd85
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 240fb408bb3ed8585ecc915ba4829ac21285d241
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622037"
---
# <a name="save-showplan-xml-events-separately-sql-server-profiler"></a><span data-ttu-id="91ac0-102">Separates Speichern von Showplan XML-Ereignissen (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="91ac0-102">Save Showplan XML Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="91ac0-103">In diesem Thema wird beschrieben, wie **Showplan XML** -Ereignisse, die in Ablaufverfolgungen erfasst sind, mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]in separaten .SQLPlan-Dateien gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="91ac0-103">This topic describes how to save **Showplan XML** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="91ac0-104">Sie können die **Showplan XML** -Ereignisdateien in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]öffnen, sodass Sie den grafischen Ausführungsplan für die einzelnen Ereignisse betrachten können.</span><span class="sxs-lookup"><span data-stu-id="91ac0-104">You can open the **Showplan XML** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-events-separately"></a><span data-ttu-id="91ac0-105">So speichern Sie Showplan XML-Ereignisse separat</span><span class="sxs-lookup"><span data-stu-id="91ac0-105">To save Showplan XML events separately</span></span>  
  
1.  <span data-ttu-id="91ac0-106">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung zu einer Instanz von SQL Server her.</span><span class="sxs-lookup"><span data-stu-id="91ac0-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="91ac0-107">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91ac0-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91ac0-108">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="91ac0-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="91ac0-109">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="91ac0-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="91ac0-110">Geben Sie im Dialogfeld **Ablaufverfolgungseigenschaften** im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="91ac0-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="91ac0-111">Wählen Sie in der Liste **Vorlage verwenden** eine Ablaufverfolgungsvorlage als Basis für die Ablaufverfolgung aus, oder wählen Sie **Leer** aus, wenn Sie keine Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="91ac0-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="91ac0-112">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="91ac0-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="91ac0-113">Aktivieren Sie das Kontrollkästchen**In Datei speichern** , um die Ablaufverfolgung in einer Datei aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="91ac0-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="91ac0-114">Geben Sie einen Wert für **Maximale Dateigröße festlegen**an.</span><span class="sxs-lookup"><span data-stu-id="91ac0-114">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="91ac0-115">Optional aktivieren Sie die Kontrollkästchen **Dateirollover aktivieren** und **Ablaufverfolgungsdaten von Serverprozessen** .</span><span class="sxs-lookup"><span data-stu-id="91ac0-115">Optionally, select the **Enable file rollover** and **Server processes trace data** check boxes.</span></span>  
  
    -   <span data-ttu-id="91ac0-116">Aktivieren Sie das Kontrollkästchen**In Tabelle speichern** , um die Ablaufverfolgung in einer Datenbanktabelle aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="91ac0-116">Select the**Save to table** check box to capture the trace to a database table.</span></span> <span data-ttu-id="91ac0-117">Klicken Sie optional auf **Maximale Zeilen Anzahl festlegen**, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="91ac0-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="91ac0-118">Aktivieren Sie optional das Kontrollkästchen **Beendigungszeit für Ablaufverfolgung aktivieren** , und geben Sie das Datum und die Uhrzeit zum Beenden der Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="91ac0-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="91ac0-119">Klicken Sie auf die Registerkarte **Ereignisauswahl**.</span><span class="sxs-lookup"><span data-stu-id="91ac0-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="91ac0-120">Geben Sie im Dialogfeld **Ereignisse**die Ereigniskategorie **Leistung**, und aktivieren Sie dann das Kontrollkästchen **Showplan XML**.</span><span class="sxs-lookup"><span data-stu-id="91ac0-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML**check box.</span></span> <span data-ttu-id="91ac0-121">Wenn die **Performance** -Ereigniskategorie nicht verfügbar ist, aktivieren Sie zum Anzeigen dieser Ereigniskategorie das Kontrollkästchen **Alle Ereignisse anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="91ac0-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="91ac0-122">Das Dialogfeld **Ereignisextraktionseinstellungen**wird dem Dialogfeld **Ablaufverfolgungseigenschaften**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="91ac0-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="91ac0-123">Klicken Sie im Menü **Ereignisextraktionseinstellungen**auf **XML-Showplanereignisse separat speichern**.</span><span class="sxs-lookup"><span data-stu-id="91ac0-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="91ac0-124">Geben Sie in das Dialogfeld **Speichern unter** den Namen der Datei ein, in die die **Showplan XML** -Ereignisse gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="91ac0-124">In the **Save As** dialog box, enter the name of the file in which to store the **Showplan XML** events.</span></span>  
  
10. <span data-ttu-id="91ac0-125">Klicken Sie auf **Alle XML-Showplanbatches in einer einzelnen Datei** , wenn alle **Showplan XML** -Ereignisse in einer einzigen XML-Datei gespeichert werden sollen, bzw. auf **Jeder XML-Showplanbatch in einer eigenen Datei**, um so je eine neue XML-Datei für die einzelnen **Showplan XML** -Ereignisse anlegen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="91ac0-125">Click **All XML Showplan batches in a single file** to save all **Showplan XML** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML** event.</span></span>  
  
11. <span data-ttu-id="91ac0-126">Um die **Showplan XML** -Ereignisdatei in SQL Server Management Studio anzeigen zu lassen, zeigen Sie im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="91ac0-126">To view the **Showplan XML** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="91ac0-127">Navigieren Sie zu dem Verzeichnis, in dem Sie die **Showplan XML** -Ereignisdatei(en) gespeichert hatten, wählen Sie eine Datei aus, und öffnen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="91ac0-127">Navigate to the directory where you saved the **Showplan XML** event file or files to select one and open it.</span></span> <span data-ttu-id="91ac0-128">**Showplan XML** -Ereignisdateien besitzen die Dateierweiterung .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="91ac0-128">**Showplan XML** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ac0-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91ac0-129">See Also</span></span>  
 [<span data-ttu-id="91ac0-130">Analysieren von Abfragen mit SHOWPLAN-Ergebnissen in SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="91ac0-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
