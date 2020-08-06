---
title: Separates Speichern eines Showplan XML Statistics Profile-Ereignisses (SQL Server Profiler) | Microsoft-Dokumentation
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
ms.assetid: df393f13-d538-4d94-8155-9c2fdf5f755d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: be0c02f8396df81af803c365b9ede42610353ed3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701097"
---
# <a name="save-showplan-xml-statistics-profile-events-separately-sql-server-profiler"></a><span data-ttu-id="f2cbb-102">Separates Speichern eines Showplan XML Statistics Profile-Ereignisses (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f2cbb-102">Save Showplan XML Statistics Profile Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="f2cbb-103">In diesem Thema wird beschrieben, wie Sie in Ablaufverfolgungen aufgezeichnete **Showplan XML Statistics Profile** -Ereignisse mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]in separaten SQLPLAN-Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-103">This topic describes how to save **Showplan XML Statistics Profile** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f2cbb-104">Sie können die **Showplan XML Statistics Profile** -Ereignisdateien in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]öffnen, um den grafischen Ausführungsplan für jedes Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-104">You can open the **Showplan XML Statistics Profile** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-statistics-events-separately"></a><span data-ttu-id="f2cbb-105">So speichern Sie Showplan XML Statistics-Ereignisse separat</span><span class="sxs-lookup"><span data-stu-id="f2cbb-105">To save Showplan XML statistics events separately</span></span>  
  
1.  <span data-ttu-id="f2cbb-106">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-106">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="f2cbb-107">Das Dialogfeld **Ablaufverfolgungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-107">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2cbb-108">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box does not appear and the trace begins instead.</span></span> <span data-ttu-id="f2cbb-109">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="f2cbb-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="f2cbb-110">Geben Sie im Dialogfeld **Ablaufverfolgungseigenschaften** im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="f2cbb-111">Wählen Sie in der Liste **Vorlage verwenden** eine Ablaufverfolgungsvorlage für die Ablaufverfolgung aus, oder wählen Sie **Leer** aus, wenn Sie keine Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-111">In the **Use the template** list, select a trace template to base the trace on, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="f2cbb-112">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f2cbb-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="f2cbb-113">Klicken Sie auf**In Datei speichern**, um die Ablaufverfolgung in einer Datei zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-113">Click**Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="f2cbb-114">Geben Sie einen Wert für **Maximale Dateigröße festlegen**an.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="f2cbb-115">Aktivieren Sie optional die Option **dateirol Lover aktivieren** und Ablauf **Verfolgungs Daten von Server Prozessen**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-115">Optionally select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="f2cbb-116">Klicken Sie auf**In Tabelle speichern** , um die Ablaufverfolgung in einer Datenbanktabelle zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-116">Click**Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="f2cbb-117">Klicken Sie optional auf **Maximale Zeilen Anzahl festlegen**, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="f2cbb-118">Aktivieren Sie optional das Kontrollkästchen Ablauf **Verfolgungszeit aktivieren** , und geben Sie ein Enddatum und eine Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-118">Optionally select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="f2cbb-119">Klicken Sie auf die Registerkarte **Ereignisauswahl**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="f2cbb-120">Erweitern Sie in der **Events**-Datenspalte die **Performance**-Ereigniskategorie, und aktivieren Sie dann das Kontrollkästchen **Showplan XML Statistics Profile**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML Statistics Profile**check box.</span></span> <span data-ttu-id="f2cbb-121">Wenn die **Performance** -Ereigniskategorie nicht verfügbar ist, aktivieren Sie zum Anzeigen dieser Ereigniskategorie das Kontrollkästchen **Alle Ereignisse anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="f2cbb-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="f2cbb-122">Das Dialogfeld **Ereignisextraktionseinstellungen**wird dem Dialogfeld **Ablaufverfolgungseigenschaften**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog.</span></span>  
  
8.  <span data-ttu-id="f2cbb-123">Klicken Sie im Menü **Ereignisextraktionseinstellungen**auf **XML-Showplanereignisse separat speichern**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="f2cbb-124">Geben Sie im Dialogfeld **Speichern unter** den Dateinamen zum Speichern der **Showplan XML Statistics Profile** -Ereignisse ein.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-124">In the **Save As** dialog box, enter the file name to store the **Showplan XML Statistics Profile** events.</span></span>  
  
10. <span data-ttu-id="f2cbb-125">Klicken Sie auf **Alle XML-Showplanbatches in einer einzelnen Datei** , um alle **Showplan XML Statistics Profile** -Ereignisse in einer einzelnen XML-Datei zu speichern. Klicken Sie optional auf **Jeder XML-Showplanbatch in einer eigenen Datei**, um für jedes **Showplan XML Statistics Profile** -Ereignis eine neue XML-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-125">Click **All batches in a single file** to save all **Showplan XML Statistics Profile** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML Statistics Profile** event.</span></span>  
  
11. <span data-ttu-id="f2cbb-126">Zum Anzeigen der **Showplan XML Statistics Profile** -Ereignisdatei in SQL Server Management Studio zeigen Sie im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-126">To view the **Showplan XML Statistics Profile** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="f2cbb-127">Navigieren Sie zu dem Verzeichnis, in Sie die **Showplan XML Statistics Profile** -Ereignisdatei(en) gespeichert haben, um eine Ereignisdatei auszuwählen und zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-127">Navigate to the directory where you saved the **Showplan XML Statistics Profile** event file or files to select one and open it.</span></span> <span data-ttu-id="f2cbb-128">**Showplan XML Statistics Profile** -Ereignisdateien haben eine SQLPlan-Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-128">**Showplan XML Statistics Profile** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cbb-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2cbb-129">See Also</span></span>  
 [<span data-ttu-id="f2cbb-130">Analysieren von Abfragen mit SHOWPLAN-Ergebnissen in SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f2cbb-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
