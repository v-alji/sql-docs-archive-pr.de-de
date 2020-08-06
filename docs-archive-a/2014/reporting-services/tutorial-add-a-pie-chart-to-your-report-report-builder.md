---
title: 'Tutorial: Hinzufügen eines Kreisdiagramms zu einem Bericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720962"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a><span data-ttu-id="4be9e-102">Tutorial: Hinzufügen eines Kreisdiagramms zu einem Bericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="4be9e-102">Tutorial: Add a Pie Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="4be9e-103">Kreis- und Ringdiagramme zeigen Daten als Teile des Ganzen an.</span><span class="sxs-lookup"><span data-stu-id="4be9e-103">Pie charts and doughnut charts display data as a proportion of the whole.</span></span> <span data-ttu-id="4be9e-104">Kreisdiagramme werden häufig verwendet, um Vergleiche zwischen Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-104">Pie charts are most commonly used to make comparisons between groups.</span></span> <span data-ttu-id="4be9e-105">Kreis-und Ring Diagramme bilden zusammen mit Pyramiden-und Trichter Diagrammen eine Gruppe von Diagrammen, die als Form Diagramme bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4be9e-105">Pie and doughnut charts, along with pyramid and funnel charts, constitute a group of charts known as shape charts.</span></span> <span data-ttu-id="4be9e-106">Formdiagramme haben keine Achsen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-106">Shape charts have no axes.</span></span> <span data-ttu-id="4be9e-107">Wenn ein numerisches Feld auf einem Formdiagramm abgelegt wird, berechnet das Diagramm den prozentualen Anteil jedes einzelnen Werts der Gesamtsumme.</span><span class="sxs-lookup"><span data-stu-id="4be9e-107">When a numeric field is dropped on a shape chart, the chart calculates the percentage of each value to the total.</span></span>  
  
 <span data-ttu-id="4be9e-108">Wenn in einem Kreisdiagramm zu viele Datenpunkte vorhanden sind, können die Datenpunktbezeichnungen zu überfüllt sein, um sie zu lesen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-108">If there are too many data points on a pie chart, your data point labels might be too crowded to read.</span></span> <span data-ttu-id="4be9e-109">In diesem Fall sollten Sie die Verwendung eines Liniendiagramms erwägen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-109">In that case, consider using a line chart.</span></span> <span data-ttu-id="4be9e-110">Verwenden Sie Kreisdiagramme möglichst nur, nachdem Sie die Daten bereits zu einer kleineren Anzahl von Datenpunkten aggregiert haben.</span><span class="sxs-lookup"><span data-stu-id="4be9e-110">Consider using pie charts only after you have aggregated your data into a few data points.</span></span>  
  
 <span data-ttu-id="4be9e-111">Die folgende Abbildung zeigt das Kreisdiagramm, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-111">The following illustration shows the pie chart you will create.</span></span>  
  
 <span data-ttu-id="4be9e-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span><span class="sxs-lookup"><span data-stu-id="4be9e-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="4be9e-113">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="4be9e-113">What You Will Learn</span></span>  
 <span data-ttu-id="4be9e-114">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4be9e-114">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="4be9e-115">Erstellen eines Kreisdiagramms im Diagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4be9e-115">Create a Pie Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="4be9e-116">Auswählen des Diagrammtyps</span><span class="sxs-lookup"><span data-stu-id="4be9e-116">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="4be9e-117">Anzeigen von Prozentsätzen in jedem Slice</span><span class="sxs-lookup"><span data-stu-id="4be9e-117">Display Percentages in Each Slice</span></span>](#Percentages)  
  
4.  [<span data-ttu-id="4be9e-118">Kombinieren von kleinen Slices zu einem Slice</span><span class="sxs-lookup"><span data-stu-id="4be9e-118">Combine Small Slices into One Slice</span></span>](#CombineSlices)  
  
5.  [<span data-ttu-id="4be9e-119">Anpassen des Zeichnungseffekts</span><span class="sxs-lookup"><span data-stu-id="4be9e-119">Customize the Drawing Effect</span></span>](#DrawingEffect)  
  
6.  [<span data-ttu-id="4be9e-120">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="4be9e-120">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="4be9e-121">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="4be9e-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="4be9e-122">In diesem Lernprogramm werden die Schritte für den Assistenten in zwei Verfahren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4be9e-122">In this tutorial, the steps for the wizard are consolidated into two procedures.</span></span> <span data-ttu-id="4be9e-123">Im ersten Tutorial dieser Reihe erhalten Sie detaillierte Anweisungen zum Navigieren zu einem Berichtsserver, Hinzufügen einer Datenquelle und Hinzufügen eines Datasets: [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4be9e-123">For step-by-step instructions about how to browse to a report server, add a data source, and add a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="4be9e-124">Ungefähre Dauer dieses Lernprogramms: 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="4be9e-124">Estimated time to complete this tutorial: 10 minutes</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4be9e-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4be9e-125">Requirements</span></span>  
 <span data-ttu-id="4be9e-126">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="4be9e-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="4be9e-127">1. Erstellen eines Kreis Diagramms im Diagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4be9e-127">1. Create a Pie Chart from the Chart Wizard</span></span>  
 <span data-ttu-id="4be9e-128">Erstellen Sie im Dialogfeld Erste Schritte mithilfe des Diagramm-Assistenten ein eingebettetes Dataset, wählen Sie eine freigegebene Datenquelle aus, und erstellen Sie ein Kreisdiagramm.</span><span class="sxs-lookup"><span data-stu-id="4be9e-128">From the Getting Started dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a pie chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4be9e-129">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="4be9e-129">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="4be9e-130">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="4be9e-130">This makes the query quite long.</span></span> <span data-ttu-id="4be9e-131">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="4be9e-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="4be9e-132">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="4be9e-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="4be9e-133">So erstellen Sie einen neuen Diagrammbericht</span><span class="sxs-lookup"><span data-stu-id="4be9e-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="4be9e-134">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="4be9e-135">Das Dialogfeld Erste Schritte wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-135">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4be9e-136">Wenn das Dialogfeld "Getting Started" nicht angezeigt wird, klicken Sie auf der Schaltfläche "Berichts-Generator" auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-136">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="4be9e-137">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4be9e-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="4be9e-138">Klicken Sie im rechten Bereich auf **Diagramm-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="4be9e-139">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="4be9e-140">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichtsserver, und wählen Sie eine Datenquelle aus. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="4be9e-141">Möglicherweise müssen Benutzername und Kennwort eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4be9e-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4be9e-142">Welche Datenquelle Sie auswählen, ist unwichtig, solange Sie über ausreichende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="4be9e-143">Aus der Datenquelle werden keine Daten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="4be9e-144">Weitere Informationen finden Sie unter [Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4be9e-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="4be9e-145">Klicken Sie auf der Seite **Abfrage entwerfen** auf **als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-145">On the **Design a Query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="4be9e-146">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="4be9e-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="4be9e-147">(Optional) Klicken Sie auf die Schaltfläche Ausführen (**!**), um die Daten anzuzeigen, auf denen das Diagramm basiert.</span><span class="sxs-lookup"><span data-stu-id="4be9e-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="4be9e-148">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="4be9e-149">2. Wählen Sie den Diagrammtyp aus.</span><span class="sxs-lookup"><span data-stu-id="4be9e-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="4be9e-150">Sie können aus einer Vielzahl vordefinierter Diagrammtypen auswählen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="4be9e-151">So fügen Sie ein Kreisdiagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="4be9e-151">To add a pie chart</span></span>  
  
1.  <span data-ttu-id="4be9e-152">Klicken Sie auf der Seite **Diagrammtyp auswählen** **auf Kreis, und**klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-152">On the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span> <span data-ttu-id="4be9e-153">Die Seite **Diagrammfelder anordnen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4be9e-153">The **Arrange chart fields** page opens.</span></span>  
  
     <span data-ttu-id="4be9e-154">Ziehen Sie auf der Seite **Diagrammfelder anordnen** das Feld „Product“ in den Bereich **Kategorien** .</span><span class="sxs-lookup"><span data-stu-id="4be9e-154">On the **Arrange chart fields** page, drag the Product field to the **Categories** pane.</span></span> <span data-ttu-id="4be9e-155">Kategorien definieren die Anzahl von Slices im Kreisdiagramm.</span><span class="sxs-lookup"><span data-stu-id="4be9e-155">Categories define the number of slices in the pie chart.</span></span> <span data-ttu-id="4be9e-156">In diesem Beispiel werden acht Slices verwendet, eines für jedes Produkt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-156">In this example, there will be eight slices, one for each product.</span></span>  
  
2.  <span data-ttu-id="4be9e-157">Ziehen Sie das Feld „Sales“ in den Bereich **Werte** .</span><span class="sxs-lookup"><span data-stu-id="4be9e-157">Drag the Sales field to the **Values** pane.</span></span> <span data-ttu-id="4be9e-158">Das Feld "Sales" stellt den Umsatz für die Unterkategorie dar.</span><span class="sxs-lookup"><span data-stu-id="4be9e-158">Sales represents the sales amount for the subcategory.</span></span> <span data-ttu-id="4be9e-159">Im Bereich **Werte** wird `[Sum(Sales)]` angezeigt, da im Diagramm der aggregierte Wert für die einzelnen Produkte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4be9e-159">The **Values** pane displays `[Sum(Sales)]` because the chart displays the aggregate for each product.</span></span>  
  
3.  <span data-ttu-id="4be9e-160">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-160">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="4be9e-161">Wählen Sie auf der Seite Format **auswählen** im Bereich Stile einen Stil aus.</span><span class="sxs-lookup"><span data-stu-id="4be9e-161">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="4be9e-162">Ein Format dient zum Angeben eines Schriftschnitts, einer Farbpalette und einer Rahmenart.</span><span class="sxs-lookup"><span data-stu-id="4be9e-162">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="4be9e-163">Wenn Sie ein Format auswählen, wird im Vorschaubereich ein Beispiel für das Diagramm mit diesem Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-163">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
5.  <span data-ttu-id="4be9e-164">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-164">Click **Finish**.</span></span>  
  
     <span data-ttu-id="4be9e-165">Das Diagramm wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-165">The chart is added to the design surface.</span></span>  
  
6.  <span data-ttu-id="4be9e-166">Klicken Sie auf das Diagramm, um die Diagrammziehpunkte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-166">Click the chart to display the chart handles.</span></span> <span data-ttu-id="4be9e-167">Ziehen Sie die rechte untere Ecke des Diagramms, um das Diagramm zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="4be9e-167">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="4be9e-168">Die Berichtsentwurfsoberfläche wird vergrößert, um genügend Platz für das Diagramm zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4be9e-168">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
7.  <span data-ttu-id="4be9e-169">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4be9e-170">Im Bericht wird das Kreisdiagramm mit acht Slices angezeigt, eines für jedes Produkt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-170">The report displays the pie chart with eight slices, one for each product.</span></span> <span data-ttu-id="4be9e-171">Die Größe der Slices stellt den Umsatz für das jeweilige Produkt dar.</span><span class="sxs-lookup"><span data-stu-id="4be9e-171">The size of each slice represents the sales for that product.</span></span> <span data-ttu-id="4be9e-172">Drei der Slices sind relativ dünn.</span><span class="sxs-lookup"><span data-stu-id="4be9e-172">Three of the slices are quite thin.</span></span>  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a><span data-ttu-id="4be9e-173">3. Anzeigen von Prozentsätzen in jedem Slice</span><span class="sxs-lookup"><span data-stu-id="4be9e-173">3. Display Percentages in Each Slice</span></span>  
 <span data-ttu-id="4be9e-174">Sie können für jeden Slice des Kreisdiagramms den Prozentsatz des Slices im Vergleich zum gesamten Kreis anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-174">On each slice of the pie, you can display a percentage for this slice compared to the whole pie.</span></span>  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a><span data-ttu-id="4be9e-175">So zeigen Sie Prozentwerte in den einzelnen Segmenten eines Kreisdiagramms an</span><span class="sxs-lookup"><span data-stu-id="4be9e-175">To display percentages in each slice of the pie chart</span></span>  
  
1.  <span data-ttu-id="4be9e-176">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4be9e-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4be9e-177">Klicken Sie mit der rechten Maustaste auf das Kreisdiagramm, und klicken Sie anschließend auf **Datenbezeichnungen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-177">Right-click the pie chart and click **Show Data Labels**.</span></span> <span data-ttu-id="4be9e-178">Die Datenbezeichnungen werden im Diagramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-178">The data labels appear on the chart.</span></span>  
  
3.  <span data-ttu-id="4be9e-179">Klicken Sie mit der rechten Maustaste auf eine Bezeichnung, und klicken Sie dann auf **Reihen Bezeichnung Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-179">Right-click a label, and then click **Series Label Properties**.</span></span>  
  
4.  <span data-ttu-id="4be9e-180">Wählen Sie unter Bezeichnungs Daten im Dropdown Feld die Option **#percent**aus.</span><span class="sxs-lookup"><span data-stu-id="4be9e-180">In Label data, from the drop-down box, select **#PERCENT**.</span></span>  
  
     <span data-ttu-id="4be9e-181">Die UseValueAsLabel-Eigenschaft muss zum Anzeigen von Werten als Prozentsätze auf "False" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4be9e-181">To display values as percentages, the UseValueAsLabel property must be false.</span></span> <span data-ttu-id="4be9e-182">Klicken Sie auf **Ja** , wenn Sie im Dialogfeld **Aktion bestätigen**zum Festlegen dieses Werts aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4be9e-182">If you are prompted to set this value in the **Confirm Action** dialog, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="4be9e-183">Optionale Um anzugeben, wie viele Dezimalstellen in der Bezeichnung angezeigt werden, geben Sie ein, `#PERCENT{Pn}` wobei *n* die Anzahl der anzuzeigenden Dezimalstellen ist.</span><span class="sxs-lookup"><span data-stu-id="4be9e-183">(Optional) To specify how many decimal places the label shows, type `#PERCENT{Pn}` where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="4be9e-184">Wenn Sie z. b. keine Dezimalstellen anzeigen möchten, geben Sie ein `#PERCENT{P0}` .</span><span class="sxs-lookup"><span data-stu-id="4be9e-184">For example, to display no decimal places, type `#PERCENT{P0}`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4be9e-185">Die Option**Zahlenformat** im Dialogfeld **Reihenbezeichnungseigenschaften** hat beim Formatieren von Prozentwerten keinen Einfluss auf das Format.</span><span class="sxs-lookup"><span data-stu-id="4be9e-185">**Number Format** in the **Series Label Properties** dialog box has no effect when you format percentages.</span></span> <span data-ttu-id="4be9e-186">Hierdurch werden die Bezeichnungen als Prozentwerte formatiert, die eigentlichen Prozentwerte der einzelnen Slices eines Kreisdiagramms werden jedoch nicht berechnet.</span><span class="sxs-lookup"><span data-stu-id="4be9e-186">This formats the labels as percentages, but does not calculate the percentage of the pie that each slice represents.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="4be9e-187">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-187">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4be9e-188">Im Bericht wird der Prozentsatz am gesamten Kreis für jeden Kreisslice angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-188">The report displays the percentage of the whole for each pie slice.</span></span>  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a><span data-ttu-id="4be9e-189">4. Kombinieren von kleinen Slices zu einem Slice</span><span class="sxs-lookup"><span data-stu-id="4be9e-189">4. Combine Small Slices into One Slice</span></span>  
 <span data-ttu-id="4be9e-190">Drei der Slices im Kreis sind relativ klein.</span><span class="sxs-lookup"><span data-stu-id="4be9e-190">Three of the slices in the pie are quite small.</span></span> <span data-ttu-id="4be9e-191">Sie können mehrere kleine Slices zu einem größeren Slice kombinieren, durch das alle Slices dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4be9e-191">You can combine multiple small slices into one larger slice that represents all of them.</span></span>  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a><span data-ttu-id="4be9e-192">So kombinieren Sie alle Slices des Kreisdiagramms unter fünf Prozent zu einem Slice</span><span class="sxs-lookup"><span data-stu-id="4be9e-192">To combine any slices on the pie chart smaller than 5 percent into one slice</span></span>  
  
1.  <span data-ttu-id="4be9e-193">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4be9e-193">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4be9e-194">Wählen Sie auf der Registerkarte **Ansicht** in der Gruppe **anzeigen/ausblenden** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="4be9e-194">On the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="4be9e-195">Klicken Sie auf der Entwurfsoberfläche auf ein Segment des Kreisdiagramms.</span><span class="sxs-lookup"><span data-stu-id="4be9e-195">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="4be9e-196">Die Eigenschaften für die Reihe werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-196">The properties for the series are displayed in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="4be9e-197">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="4be9e-197">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="4be9e-198">Legen Sie die Eigenschaft **CollectedStyle** auf **SingleSlice**fest.</span><span class="sxs-lookup"><span data-stu-id="4be9e-198">Set the **CollectedStyle** property to **SingleSlice**.</span></span>  
  
6.  <span data-ttu-id="4be9e-199">Vergewissern Sie sich, dass die **CollectedThreshold** -Eigenschaft auf 5 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4be9e-199">Verify that the **CollectedThreshold** property is set to 5.</span></span>  
  
7.  <span data-ttu-id="4be9e-200">Vergewissern Sie sich, dass die **CollectedThresholdUsePercent** -Eigenschaft auf **TRUE**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4be9e-200">Verify that the **CollectedThresholdUsePercent** property is set to **True**.</span></span>  
  
8.  <span data-ttu-id="4be9e-201">Klicken Sie im Menüband auf der Registerkarte **Start** auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-201">On the Ribbon, on the **Home** tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4be9e-202">In der Legende ist die Kategorie "Other" jetzt vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4be9e-202">In the legend, the category "Other" now exists.</span></span> <span data-ttu-id="4be9e-203">Im neuen Kreisslice werden alle Slices, die kleiner als 5 % waren, zu einem Slice kombiniert, das 6 % des gesamten Kreises darstellt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-203">The new pie slice combines all the slices that were under 5% into one slice that is 6% of the whole pie.</span></span>  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a><span data-ttu-id="4be9e-204">5. Anpassen des Zeichnungs Effekts</span><span class="sxs-lookup"><span data-stu-id="4be9e-204">5. Customize the Drawing Effect</span></span>  
 <span data-ttu-id="4be9e-205">Das Standardformat für Kreisdiagramme im Diagramm-Assistenten ist "Ozean", ein Format mit einem konkaven Zeichnungseffekt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-205">In the Chart Wizard, the default style for a pie chart is Ocean, which features a Concave drawing effect.</span></span> <span data-ttu-id="4be9e-206">Sie können das Format nach dem Ausführen des Assistenten ändern.</span><span class="sxs-lookup"><span data-stu-id="4be9e-206">You can change that after you run the wizard.</span></span>  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a><span data-ttu-id="4be9e-207">So fügen Sie dem Kreisdiagramm einen Zeichnungseffekt hinzu</span><span class="sxs-lookup"><span data-stu-id="4be9e-207">To add a drawing effect to the pie chart</span></span>  
  
1.  <span data-ttu-id="4be9e-208">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4be9e-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4be9e-209">Wenn der Bereich Eigenschaften nicht bereits geöffnet ist, wählen Sie auf der Registerkarte **Ansicht** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="4be9e-209">If the Properties pane is not already opened, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="4be9e-210">Doppelklicken Sie auf das Kreis Diagramm.</span><span class="sxs-lookup"><span data-stu-id="4be9e-210">Double-click the pie chart itself.</span></span> <span data-ttu-id="4be9e-211">Die Reiheneigenschaften für das Kreisdiagramm werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-211">The series properties for the pie chart are shown in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="4be9e-212">Erweitern Sie im Bereich Eigenschaften den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="4be9e-212">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="4be9e-213">Legen Sie " **PieDrawingStyle** " auf " **SoftEdge**" fest.</span><span class="sxs-lookup"><span data-stu-id="4be9e-213">Set the **PieDrawingStyle** to **SoftEdge**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4be9e-214">Zeichnungs Effekte und dreidimensionale Effekte sind exklusive Optionen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-214">Drawing effects and three-dimensional effects are exclusive options.</span></span> <span data-ttu-id="4be9e-215">Wenn für ein Diagramm dreidimensionale Effekte angewendet werden, ist **PieDrawingStyle** nicht im Bereich Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4be9e-215">If a chart has three-dimensional effects applied, **PieDrawingStyle** is not available on the Properties pane.</span></span>  
  
6.  <span data-ttu-id="4be9e-216">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-216">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4be9e-217">Die folgende Abbildung zeigt das Kreisdiagramm mit weichen Kanten.</span><span class="sxs-lookup"><span data-stu-id="4be9e-217">The following illustration shows the pie chart with the soft edge effect.</span></span>  
  
 <span data-ttu-id="4be9e-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span><span class="sxs-lookup"><span data-stu-id="4be9e-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="4be9e-219">6. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="4be9e-219">6. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="4be9e-220">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="4be9e-220">To add a report title</span></span>  
  
1.  <span data-ttu-id="4be9e-221">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-221">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="4be9e-222">Geben Sie wie folgt **Kamera- und Camcorderumsatz**ein, drücken Sie die EINGABETASTE, und geben Sie anschließend **Als Prozentsatz des Gesamtumsatzes**ein:</span><span class="sxs-lookup"><span data-stu-id="4be9e-222">Type **Camera and Camcorder Sales**, press ENTER, and then type **As a Percentage of Total Sales**, so it looks like this:</span></span>  
  
     <span data-ttu-id="4be9e-223">**Kamera- und Camcorderumsatz**</span><span class="sxs-lookup"><span data-stu-id="4be9e-223">**Camera and Camcorder Sales**</span></span>  
  
     <span data-ttu-id="4be9e-224">**Als Prozentsatz des Gesamtumsatzes**</span><span class="sxs-lookup"><span data-stu-id="4be9e-224">**As a Percentage of Total Sales**</span></span>  
  
3.  <span data-ttu-id="4be9e-225">Wählen Sie **Kamera-und camcorderumsatz**aus, und klicken Sie im Abschnitt **Schriftart** der Registerkarte **Home** des Menübands auf die Schaltfläche **Fett** .</span><span class="sxs-lookup"><span data-stu-id="4be9e-225">Select **Camera and Camcorder Sales**, and click the **Bold** button from the **Font** section of the **Home** tab of the ribbon.</span></span>  
  
4.  <span data-ttu-id="4be9e-226">Wählen Sie **als Prozentsatz des Gesamtumsatzes aus**, und legen Sie auf der Registerkarte **Home** im Abschnitt **Schriftart** den Schrift Grad auf **10**fest.</span><span class="sxs-lookup"><span data-stu-id="4be9e-226">Select **As a Percentage of Total Sales**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="4be9e-227">(Optional) Das Textfeld "Titel" muss ggf. vergrößert werden, damit die beiden Textzeilen hineinpassen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-227">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="4be9e-228">Dieser Titel wird am Anfang des Berichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4be9e-228">This title will appear at the top of the report.</span></span> <span data-ttu-id="4be9e-229">Ist keine Kopfzeile definiert, erfüllen die Elemente über dem Berichtshauptteil die Funktion einer Berichtskopfzeile.</span><span class="sxs-lookup"><span data-stu-id="4be9e-229">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="4be9e-230">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-230">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="4be9e-231">7. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="4be9e-231">7. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="4be9e-232">So speichern Sie den Bericht</span><span class="sxs-lookup"><span data-stu-id="4be9e-232">To save the report</span></span>  
  
1.  <span data-ttu-id="4be9e-233">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4be9e-233">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4be9e-234">Klicken Sie auf die Schaltfläche Berichts-Generator und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-234">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="4be9e-235">Geben Sie im Feld **Name**den Namen **Umsatz-Kreisdiagramm**ein.</span><span class="sxs-lookup"><span data-stu-id="4be9e-235">In **Name**, type **Sales Pie Chart**.</span></span>  
  
4.  <span data-ttu-id="4be9e-236">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4be9e-236">Click **Save**.</span></span>  
  
 <span data-ttu-id="4be9e-237">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4be9e-237">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4be9e-238">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4be9e-238">Next Steps</span></span>  
 <span data-ttu-id="4be9e-239">Sie haben das Lernprogramm "Hinzufügen eines Kreisdiagramms zu einem Bericht" erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4be9e-239">You have successfully completed the Adding a Pie Chart to Your Report tutorial.</span></span> <span data-ttu-id="4be9e-240">Weitere Informationen zu Diagrammen finden Sie unter [Diagramme (Berichts-Generator und SSRS)](report-design/charts-report-builder-and-ssrs.md) und [Sparklines und Datenbalken (Berichts-Generator und SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4be9e-240">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be9e-241">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4be9e-241">See Also</span></span>  
 <span data-ttu-id="4be9e-242">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="4be9e-242">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="4be9e-243">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4be9e-243">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
