---
title: 'Tutorial: Hinzufügen eines Säulendiagramms zu einem Bericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ef3b3f2872c2f8181296bb05337ca18975ac2f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722470"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a><span data-ttu-id="4c0b4-102">Lernprogramm: Hinzufügen eines Säulendiagramms zu einem Bericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="4c0b4-102">Tutorial: Add a Column Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="4c0b4-103">Ein Säulendiagramm zeigt eine Reihe als Satz vertikaler Balken an, die nach Kategorie gruppiert sind.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-103">A column chart displays a series as a set of vertical bars that are grouped by category.</span></span> <span data-ttu-id="4c0b4-104">Ein Säulendiagramm kann für folgende Zwecke verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4c0b4-104">A column chart can be useful to:</span></span>  
  
-   <span data-ttu-id="4c0b4-105">Anzeigen von Datenänderungen über einen bestimmten Zeitraum</span><span class="sxs-lookup"><span data-stu-id="4c0b4-105">Show data changes over a period of time.</span></span>  
  
-   <span data-ttu-id="4c0b4-106">Vergleichen des relativen Werts mehrerer Reihen</span><span class="sxs-lookup"><span data-stu-id="4c0b4-106">Compare the relative value of multiple series.</span></span>  
  
-   <span data-ttu-id="4c0b4-107">Anzeigen eines gleitenden Durchschnitts, um Trends darzustellen</span><span class="sxs-lookup"><span data-stu-id="4c0b4-107">Display a moving average to show trends.</span></span>  
  
 <span data-ttu-id="4c0b4-108">In der folgenden Abbildung sehen Sie das zu erstellende Säulendiagramm mit einem gleitenden Durchschnitt:</span><span class="sxs-lookup"><span data-stu-id="4c0b4-108">The following illustration shows the column chart you will create, with a moving average.</span></span>  
  
 <span data-ttu-id="4c0b4-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span><span class="sxs-lookup"><span data-stu-id="4c0b4-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="4c0b4-110">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="4c0b4-110">What You Will Learn</span></span>  
 <span data-ttu-id="4c0b4-111">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4c0b4-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="4c0b4-112">Erstellen eines Diagramms mithilfe des Diagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4c0b4-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="4c0b4-113">Auswählen des Diagrammtyps</span><span class="sxs-lookup"><span data-stu-id="4c0b4-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="4c0b4-114">Formatieren und Beschriften der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="4c0b4-114">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
4.  [<span data-ttu-id="4c0b4-115">Verschieben der Legende</span><span class="sxs-lookup"><span data-stu-id="4c0b4-115">Move the Legend</span></span>](#Legend)  
  
5.  [<span data-ttu-id="4c0b4-116">Benennen des Diagramms</span><span class="sxs-lookup"><span data-stu-id="4c0b4-116">Title the Chart</span></span>](#ChartTitle)  
  
6.  [<span data-ttu-id="4c0b4-117">Formatieren und Beschriften der vertikalen Achse</span><span class="sxs-lookup"><span data-stu-id="4c0b4-117">Format and Label the Vertical Axis</span></span>](#Vertical)  
  
7.  [<span data-ttu-id="4c0b4-118">Hinzufügen eines gleitenden Durchschnitts</span><span class="sxs-lookup"><span data-stu-id="4c0b4-118">Add a Moving Average</span></span>](#Average)  
  
8.  [<span data-ttu-id="4c0b4-119">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="4c0b4-119">Add a Report Title</span></span>](#Title)  
  
9. [<span data-ttu-id="4c0b4-120">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="4c0b4-120">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="4c0b4-121">In diesem Lernprogramm werden die Schritte für den Assistenten in einem Verfahren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-121">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="4c0b4-122">Im ersten Tutorial dieser Reihe erhalten Sie detaillierte Anweisungen zum Navigieren zu einem Berichtsserver, zum Auswählen einer Datenquelle sowie zum Erstellen eines Datasets: [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4c0b4-122">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="4c0b4-123">Geschätzte Zeit zum Bearbeiten dieses Tutorials: 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-123">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c0b4-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4c0b4-124">Requirements</span></span>  
 <span data-ttu-id="4c0b4-125">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="4c0b4-125">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="4c0b4-126">1. Erstellen eines Diagramm Berichts mithilfe des Diagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4c0b4-126">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="4c0b4-127">Verwenden Sie im Dialogfeld " **Getting Started** " den Diagramm-Assistenten, um ein eingebettetes DataSet zu erstellen, eine freigegebene Datenquelle auszuwählen und ein Säulendiagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-127">From the **Getting Started** dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a column chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c0b4-128">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-128">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="4c0b4-129">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-129">This makes the query quite long.</span></span> <span data-ttu-id="4c0b4-130">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-130">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="4c0b4-131">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-131">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="4c0b4-132">So erstellen Sie einen neuen Diagrammbericht</span><span class="sxs-lookup"><span data-stu-id="4c0b4-132">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="4c0b4-133">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-133">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="4c0b4-134">Das Dialogfeld " **Getting Started** " wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-134">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c0b4-135">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche " **Berichts-Generator** " auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-135">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="4c0b4-136">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-136">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="4c0b4-137">Klicken Sie im rechten Bereich auf **Diagramm-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-137">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="4c0b4-138">Klicken Sie auf der **Seite Dataset auswählen**auf **DataSet erstellen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-138">On the **Choose a dataset page**, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="4c0b4-139">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichtsserver, und wählen Sie eine Datenquelle aus. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="4c0b4-140">Möglicherweise müssen Benutzername und Kennwort eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-140">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c0b4-141">Welche Datenquelle Sie auswählen, ist unwichtig, solange Sie über ausreichende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-141">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="4c0b4-142">Aus der Datenquelle werden keine Daten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-142">You will not be getting data from the data source.</span></span> <span data-ttu-id="4c0b4-143">Weitere Informationen finden Sie unter [Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4c0b4-143">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="4c0b4-144">Klicken Sie auf der Seite **Abfrage entwerfen** auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-144">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="4c0b4-145">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="4c0b4-145">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="4c0b4-146">(Optional) Klicken Sie auf die Schaltfläche Ausführen (**!**), um die Daten anzuzeigen, auf denen das Diagramm basiert.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="4c0b4-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-147">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="4c0b4-148">2. Wählen Sie den Diagrammtyp aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-148">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="4c0b4-149">Sie können aus einer Vielzahl vordefinierter Diagrammtypen auswählen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-149">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="4c0b4-150">So fügen Sie einem Bericht ein Säulendiagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="4c0b4-150">To add a column chart</span></span>  
  
1.  <span data-ttu-id="4c0b4-151">Das Säulendiagramm ist der Standarddiagrammtyp der Seite **Diagrammtyp auswählen** .</span><span class="sxs-lookup"><span data-stu-id="4c0b4-151">On the **Choose a chart type** page, the column chart is the default chart type.</span></span> <span data-ttu-id="4c0b4-152">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-152">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="4c0b4-153">Ziehen Sie auf der Seite **Diagrammfelder anordnen** das Feld „SalesDate“ in **Kategorien**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-153">On the **Arrange chart fields** page, drag the SalesDate field to **Categories**.</span></span> <span data-ttu-id="4c0b4-154">Kategorien werden auf der horizontalen Achse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-154">Categories display on the horizontal axis.</span></span>  
  
3.  <span data-ttu-id="4c0b4-155">Ziehen Sie das Feld „Sales“ in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-155">Drag the Sales field to **Values**.</span></span> <span data-ttu-id="4c0b4-156">Im Feld **Werte** wird „Sum(Sales)“ angezeigt, da die Summe des Gesamtumsatzwerts für jedes Datum aggregiert wird.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-156">The **Values** box displays Sum(Sales) because the sum of the sales total value is aggregated for each date.</span></span> <span data-ttu-id="4c0b4-157">Werte werden auf der vertikalen Achse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-157">Values display on the vertical axis.</span></span>  
  
4.  <span data-ttu-id="4c0b4-158">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-158">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="4c0b4-159">Wählen Sie auf der Seite Format **auswählen** im Feld Stile einen Stil aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-159">On the **Choose a Style** page, in the Styles box, select a style.</span></span>  
  
     <span data-ttu-id="4c0b4-160">Ein Format dient zum Angeben eines Schriftschnitts, einer Farbpalette und einer Rahmenart.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-160">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="4c0b4-161">Wenn Sie ein Format auswählen, wird im Vorschaubereich ein Beispiel für das Diagramm mit diesem Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-161">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
6.  <span data-ttu-id="4c0b4-162">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-162">Click **Finish**.</span></span>  
  
     <span data-ttu-id="4c0b4-163">Das Diagramm wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-163">The chart is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="4c0b4-164">Klicken Sie auf das Diagramm, um die Diagrammziehpunkte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-164">Click the chart to display the chart handles.</span></span> <span data-ttu-id="4c0b4-165">Ziehen Sie die rechte untere Ecke des Diagramms, um das Diagramm zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-165">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="4c0b4-166">Die Berichtsentwurfsoberfläche wird vergrößert, um genügend Platz für das Diagramm zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-166">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
8.  <span data-ttu-id="4c0b4-167">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-167">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="4c0b4-168">3. Formatieren und beschriften der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="4c0b4-168">3. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="4c0b4-169">Standardmäßig werden die Werte auf der horizontalen Achse in einem allgemeinen Format angezeigt, dessen Größe automatisch an die Diagrammgröße angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-169">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a><span data-ttu-id="4c0b4-170">So formatieren Sie ein Datum auf der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="4c0b4-170">To format a date on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="4c0b4-171">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-171">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-172">Klicken Sie mit der rechten Maustaste auf die horizontale Achse, und klicken Sie auf **Eigenschaften für horizontale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-172">Right-click the horizontal axis, and then click **Horizontal Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="4c0b4-173">Klicken Sie auf **Number**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-173">Click **Number**.</span></span>  
  
4.  <span data-ttu-id="4c0b4-174">Wählen Sie unter **Kategorie**die Option **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-174">In **Category**, select **Date**.</span></span>  
  
5.  <span data-ttu-id="4c0b4-175">Wählen Sie im Feld **Typ** die Option **31. Jan. 2000**aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-175">In the **Type** box, select **31 Jan 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="4c0b4-176">Klicken Sie auf der Registerkarte Stamm auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-176">On the Home tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4c0b4-177">Das Datum wird im ausgewählten Datumsformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-177">The date displays in the date format that you selected.</span></span> <span data-ttu-id="4c0b4-178">Beachten Sie, dass im Diagramm nicht jede Kategorie auf der horizontalen Achse beschriftet ist.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-178">Notice that the chart does not label every category on the horizontal axis.</span></span> <span data-ttu-id="4c0b4-179">Standardmäßig werden nur Bezeichnungen aufgenommen, die neben die Achse passen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-179">By default, only labels that fit next to the axis are included.</span></span>  
  
 <span data-ttu-id="4c0b4-180">Sie können die Bezeichnungsanzeige anpassen, indem Sie die Bezeichnungen drehen und das Intervall angeben.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-180">You can customize the label display by rotating the labels and specifying the interval.</span></span>  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a><span data-ttu-id="4c0b4-181">So drehen Sie die Achsenbezeichnungen und ändern das Anzeigeintervall auf der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="4c0b4-181">To rotate the axis labels and change the display interval along the horizontal axis</span></span>  
  
1.  <span data-ttu-id="4c0b4-182">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-182">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-183">Klicken Sie mit der rechten Maustaste auf den horizontalen Achsentitel, und klicken Sie dann auf **Achsentitel anzeigen** , um den Titel zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-183">Right-click the horizontal axis title, and then click **Show Axis Title** to remove the title.</span></span> <span data-ttu-id="4c0b4-184">Da auf der horizontalen Achse Datumsangaben angezeigt werden, wird der Titel nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-184">Because the horizontal axis displays dates, the title is not needed.</span></span>  
  
3.  <span data-ttu-id="4c0b4-185">Klicken Sie mit der rechten Maustaste auf die horizontale Achse und dann auf **Eigenschaften für horizontale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-185">Right-click the horizontal axis and then click **Horizontal Axis Properties**.</span></span>  
  
4.  <span data-ttu-id="4c0b4-186">Geben Sie auf der Seite **Achsen Optionen** unter **Achsen Bereich und-Intervall**den Namen **3** für **Intervall**ein.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-186">In the **Axis Options** page under **Axis range and interval**, type **3** for **Interval**.</span></span> <span data-ttu-id="4c0b4-187">Im Diagramm wird jedes dritte Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-187">The chart will display every third date.</span></span>  
  
5.  <span data-ttu-id="4c0b4-188">Klicken Sie auf **Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-188">Click **Labels**.</span></span>  
  
6.  <span data-ttu-id="4c0b4-189">Wählen Sie unter **Optionen für automatische Anpassung der Achsen Bezeichnung ändern die Option** **Automatische Anpassung deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-189">In **Change axis label auto-fit options**, select **Disable auto-fit**.</span></span>  
  
7.  <span data-ttu-id="4c0b4-190">Wählen Sie in **Drehwinkel für Bezeichnungen**den Wert **-90**aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-190">In **Label rotation angle**, select **-90**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="4c0b4-191">Der Beispieltext für die horizontale Achse wird um 90 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-191">The sample text for the horizontal axis rotates by 90 degrees.</span></span>  
  
9. <span data-ttu-id="4c0b4-192">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-192">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4c0b4-193">Im Diagramm werden die Bezeichnungen gedreht, und die Bezeichnung für jedes dritte Datum wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-193">On the chart, the labels are rotated and the label for every third date is shown.</span></span>  
  
##  <a name="4-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="4c0b4-194">4. Verschieben der Legende</span><span class="sxs-lookup"><span data-stu-id="4c0b4-194">4. Move the Legend</span></span>  
 <span data-ttu-id="4c0b4-195">Die Legende wird automatisch auf Basis der Kategorie- und Reihendaten erstellt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-195">The legend is automatically created from category and series data.</span></span>  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a><span data-ttu-id="4c0b4-196">So verschieben Sie die Legende unter den Diagrammbereich eines Säulendiagramms</span><span class="sxs-lookup"><span data-stu-id="4c0b4-196">To move the legend below the chart area of a column chart</span></span>  
  
1.  <span data-ttu-id="4c0b4-197">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-197">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-198">Klicken Sie mit der rechten Maustaste auf die Legende im Diagramm, und klicken Sie dann auf **Legenden Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-198">Right-click the legend on the chart, and then click **Legend Properties**.</span></span>  
  
3.  <span data-ttu-id="4c0b4-199">Wählen Sie unter **Layout und Position**eine andere Position aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-199">For **Layout and Position**, select a different position.</span></span> <span data-ttu-id="4c0b4-200">Legen Sie z. B. eine Position unten in der Mitte fest.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-200">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="4c0b4-201">Wenn Sie die Legende über oder unter einem Diagramm platzieren, ändert sich das Layout der Legende von vertikal zu horizontal.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-201">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="4c0b4-202">In der Dropdownliste **Layout** können Sie ein anderes Layout auswählen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-202">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="4c0b4-203">(Optional) Da es nur eine Kategorie in diesem Lernprogramm gibt, wird die Legende nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-203">(Optional) Because there is only one category in this tutorial, the legend is not needed.</span></span> <span data-ttu-id="4c0b4-204">Klicken Sie zum Entfernen der Legende mit der rechten Maustaste auf die Legende, und klicken Sie dann auf **Legende löschen**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-204">To remove the legend, right-click the legend and then click **Delete Legend**.</span></span>  
  
6.  <span data-ttu-id="4c0b4-205">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-205">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="4c0b4-206">5. Titel des Diagramms</span><span class="sxs-lookup"><span data-stu-id="4c0b4-206">5. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a><span data-ttu-id="4c0b4-207">So ändern Sie den Diagrammtitel über dem Diagrammbereich</span><span class="sxs-lookup"><span data-stu-id="4c0b4-207">To change the chart title above the chart area</span></span>  
  
1.  <span data-ttu-id="4c0b4-208">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-209">Markieren Sie am oberen Rand des Diagramms den Text **Diagramm Titel** , und geben Sie dann den folgenden Text ein: **Store Sales Order Total**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-209">Select the words **Chart Title** at the top of the chart, and then type the following text: **Store Sales Order Totals**.</span></span>  
  
3.  <span data-ttu-id="4c0b4-210">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-210">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-format-and-label-the-vertical-axis"></a><a name="Vertical"></a><span data-ttu-id="4c0b4-211">6. Formatieren und beschriften der vertikalen Achse</span><span class="sxs-lookup"><span data-stu-id="4c0b4-211">6. Format and Label the Vertical Axis</span></span>  
 <span data-ttu-id="4c0b4-212">Standardmäßig werden die Werte auf der vertikalen Achse in einem allgemeinen Format angezeigt, dessen Größe automatisch an die Diagrammgröße angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-212">By default, the vertical axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a><span data-ttu-id="4c0b4-213">So formatieren Sie die Zahlen auf der vertikalen Achse als Währung</span><span class="sxs-lookup"><span data-stu-id="4c0b4-213">To format as currency the numbers on the vertical axis</span></span>  
  
1.  <span data-ttu-id="4c0b4-214">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-214">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-215">Doppelklicken Sie neben dem Diagramm auf die Bezeichnungen der vertikalen Achse, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-215">Double-click the labels on the vertical axis along the side of the chart to select them.</span></span>  
  
3.  <span data-ttu-id="4c0b4-216">Klicken Sie im Menüband auf der Registerkarte **Startseite** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="4c0b4-216">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="4c0b4-217">Die Achsenbezeichnungen werden nun im Währungsformat dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-217">The axis labels change to show the currency format.</span></span>  
  
4.  <span data-ttu-id="4c0b4-218">Klicken Sie im Menüband auf der Registerkarte **Startseite** in der Gruppe **Zahl** zweimal auf die Schaltfläche **Dezimalstellen verringern** , um die auf den nächstgelegenen Dollar gerundete Zahl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-218">On the ribbon, on the **Home** tab, in the **Number** group, click the **Decrease Decimal** button two times, to show the number rounded to the nearest dollar.</span></span>  
  
5.  <span data-ttu-id="4c0b4-219">Klicken Sie mit der rechten Maustaste auf die vertikale Achse, und klicken Sie auf **Eigenschaften für vertikale**</span><span class="sxs-lookup"><span data-stu-id="4c0b4-219">Right-click the vertical axis and click **Vertical Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="4c0b4-220">Klicken Sie auf **Number**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-220">Click **Number**.</span></span> <span data-ttu-id="4c0b4-221">Beachten Sie, dass im Feld **Kategorie** bereits die Option **Währung** ausgewählt und **Dezimalstellen** bereits **0** (null) ist.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-221">Note that **Currency** is already selected in the **Category** box, and **Decimal places** is already **0** (zero).</span></span>  
  
7.  <span data-ttu-id="4c0b4-222">Klicken Sie im Feld **Werte anzeigen in** auf **tausende**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-222">In the **Show Values in** box, click **Thousands**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="4c0b4-223">Klicken Sie mit der rechten Maustaste auf den Titel der vertikalen Achse entlang der Seite des Diagramms, und klicken Sie auf **Achsentitel Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-223">Right-click the vertical axis title along the side of the chart and click **Axis Title Properties**.</span></span>  
  
10. <span data-ttu-id="4c0b4-224">Ersetzen Sie den Text im **Textfeld Titel** durch den folgenden Text: **Sales Total (in Tausender)**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-224">Replace the text in the **Title text** field with the following text: **Sales Total (in Thousands)**.</span></span> <span data-ttu-id="4c0b4-225">Darüber hinaus können Sie das gewünschte Format für den Titel festlegen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-225">You can also specify a variety of options related to how the title is formatted.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="4c0b4-226">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-add-a-moving-average"></a><a name="Average"></a><span data-ttu-id="4c0b4-227">7. Hinzufügen eines gleitenden Durchschnitts</span><span class="sxs-lookup"><span data-stu-id="4c0b4-227">7. Add a Moving Average</span></span>  
  
#### <a name="to-add-a-moving-average"></a><span data-ttu-id="4c0b4-228">So fügen Sie einen gleitenden Durchschnitt hinzu</span><span class="sxs-lookup"><span data-stu-id="4c0b4-228">To add a moving average</span></span>  
  
1.  <span data-ttu-id="4c0b4-229">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-229">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-230">Doppelklicken Sie auf das Diagramm, um den Bereich **Diagrammdaten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-230">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="4c0b4-231">Klicken Sie mit der rechten Maustaste auf das Feld **[Sum (Sales)]** , das sich im Bereich **Werte** befindet, und klicken Sie dann auf **berechnete Reihe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-231">Right-click the **[Sum(Sales)]** field that is in the **Values** area, and then click **Add Calculated Series**.</span></span>  
  
4.  <span data-ttu-id="4c0b4-232">Überprüfen Sie in **Formel**, ob **Gleitender Durchschnitt** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-232">In **Formula**, verify that **Moving average** is selected.</span></span>  
  
5.  <span data-ttu-id="4c0b4-233">Wählen Sie in **Formelparameter festlegen**für **Zeitraum**den Wert **4**aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-233">In **Set Formula Parameters**, for **Period**, select **4**.</span></span>  
  
6.  <span data-ttu-id="4c0b4-234">Klicken Sie auf **Border**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-234">Click **Border**.</span></span>  
  
7.  <span data-ttu-id="4c0b4-235">Wählen Sie unter **Linienbreite**den Eintrag **3 pt liegen**aus.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-235">In **Line width**, select **3pt**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="4c0b4-236">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-236">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="4c0b4-237">Im Diagramm wird eine Linie angezeigt, die den gleitenden Durchschnitt für den Gesamtumsatz nach Datum darstellt – gemittelt über jeweils vier Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-237">The chart displays a line that shows the moving average for total sales by date, averaged over every four dates.</span></span>  
  
##  <a name="8-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="4c0b4-238">8. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="4c0b4-238">8. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="4c0b4-239">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="4c0b4-239">To add a report title</span></span>  
  
1.  <span data-ttu-id="4c0b4-240">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-240">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-241">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-241">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="4c0b4-242">Geben Sie **Umsatz Diagramm**ein, drücken Sie die EINGABETASTE, und geben Sie dann **Januar bis Dezember 2009**ein, sodass Sie wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="4c0b4-242">Type **Sales Chart**, press ENTER, and then type **January to December 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="4c0b4-243">**Umsatzdiagramm**</span><span class="sxs-lookup"><span data-stu-id="4c0b4-243">**Sales Chart**</span></span>  
  
     <span data-ttu-id="4c0b4-244">**Januar bis Dezember 2009**</span><span class="sxs-lookup"><span data-stu-id="4c0b4-244">**January to December 2009**</span></span>  
  
4.  <span data-ttu-id="4c0b4-245">Wählen Sie **Umsatz Diagramm**aus, und klicken Sie im Abschnitt **Schriftart** auf der Registerkarte **Home** des Menübands auf die Schaltfläche **Fett** .</span><span class="sxs-lookup"><span data-stu-id="4c0b4-245">Select **Sales Chart**, and click the **Bold** button in the **Font** section on the **Home** tab of the ribbon.</span></span>  
  
5.  <span data-ttu-id="4c0b4-246">Wählen Sie **Januar bis Dezember 2009**aus, und legen Sie auf der Registerkarte **Home** im Abschnitt **Schriftart** den Schrift Grad auf **10**fest.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-246">Select **January to December 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
6.  <span data-ttu-id="4c0b4-247">Optionale Möglicherweise müssen Sie das Textfeld **Titel** vergrößern, um die zwei Textzeilen aufnehmen zu können, indem Sie die Pfeile mit zwei Spitzen nach unten ziehen, wenn Sie in die Mitte des unteren Rands klicken.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-247">(Optional) You may need to make the **Title** text box taller to accommodate the two lines of text by pulling down on the double-headed arrows when you click in the middle of the bottom edge.</span></span>  
  
     <span data-ttu-id="4c0b4-248">Dieser Titel wird am Anfang des Berichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-248">This title will appear at the top of the report.</span></span> <span data-ttu-id="4c0b4-249">Ist keine Kopfzeile definiert, erfüllen die Elemente über dem Berichtshauptteil die Funktion einer Berichtskopfzeile.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-249">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
7.  <span data-ttu-id="4c0b4-250">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-250">Click **Run** to preview the report.</span></span>  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="4c0b4-251">9. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="4c0b4-251">9. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="4c0b4-252">So speichern Sie den Bericht</span><span class="sxs-lookup"><span data-stu-id="4c0b4-252">To save the report</span></span>  
  
1.  <span data-ttu-id="4c0b4-253">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-253">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="4c0b4-254">Klicken Sie auf die Schaltfläche Berichts-Generator und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-254">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="4c0b4-255">Geben Sie im Feld **Name**den Text **Sales Order Column Chart**ein.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-255">In **Name**, type **Sales Order Column Chart**.</span></span>  
  
4.  <span data-ttu-id="4c0b4-256">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-256">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4c0b4-257">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4c0b4-257">Next Steps</span></span>  
 <span data-ttu-id="4c0b4-258">Sie haben das Lernprogramm "Hinzufügen eines Säulendiagramms zu einem Bericht" erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4c0b4-258">You have successfully completed the Adding a Column Chart to Your Report tutorial.</span></span> <span data-ttu-id="4c0b4-259">Weitere Informationen zu Diagrammen finden Sie unter [Diagramme (Berichts-Generator und SSRS)](report-design/charts-report-builder-and-ssrs.md) und [Sparklines und Datenbalken (Berichts-Generator und SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4c0b4-259">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c0b4-260">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c0b4-260">See Also</span></span>  
 <span data-ttu-id="4c0b4-261">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="4c0b4-261">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="4c0b4-262">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4c0b4-262">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
