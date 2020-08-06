---
title: 'Tutorial: Hinzufügen eines Balkendiagramms zu einem Bericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6956ebd6-0217-4087-a4fa-5cc1c3804691
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01708ca548c40118daa03fac34d8a323d628b012
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616361"
---
# <a name="tutorial-add-a-bar-chart-to-your-report-report-builder"></a><span data-ttu-id="273a0-102">Tutorial: Hinzufügen eines Balkendiagramms zu einem Bericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="273a0-102">Tutorial: Add a Bar Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="273a0-103">In einem Balkendiagramm werden Kategoriedaten horizontal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-103">A bar chart displays category data horizontally.</span></span> <span data-ttu-id="273a0-104">Diese Darstellung bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="273a0-104">This can help to:</span></span>  
  
-   <span data-ttu-id="273a0-105">Bessere Lesbarkeit langer Kategorienamen</span><span class="sxs-lookup"><span data-stu-id="273a0-105">Improve readability of long category names.</span></span>  
  
-   <span data-ttu-id="273a0-106">Bessere Verständlichkeit von Zeiten, die als Werte ausgegeben werden</span><span class="sxs-lookup"><span data-stu-id="273a0-106">Improve understandability of times plotted as values.</span></span>  
  
-   <span data-ttu-id="273a0-107">Vergleichen des relativen Werts mehrerer Reihen</span><span class="sxs-lookup"><span data-stu-id="273a0-107">Compare the relative value of multiple series.</span></span>  
  
 <span data-ttu-id="273a0-108">Die folgende Abbildung zeigt das zu erstellende Balkendiagramm mit den Umsätzen der fünf besten Vertriebsmitarbeiter für die Jahre 2008 und 2009 in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="273a0-108">The following illustration shows the bar chart that you will create, with sales for 2008 and 2009 for the top five salespeople, in alphabetical order.</span></span>  
  
 <span data-ttu-id="273a0-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span><span class="sxs-lookup"><span data-stu-id="273a0-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="273a0-110">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="273a0-110">What You Will Learn</span></span>  
 <span data-ttu-id="273a0-111">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="273a0-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="273a0-112">Erstellen eines Diagramms mithilfe des Diagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="273a0-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="273a0-113">Auswählen des Diagrammtyps</span><span class="sxs-lookup"><span data-stu-id="273a0-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="273a0-114">Anzeigen aller Kategoriewerte auf der vertikalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-114">Display all Category Values on the Vertical Axis</span></span>](#AllValues)  
  
4.  [<span data-ttu-id="273a0-115">Ändern der Darstellung von Namen auf der vertikalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-115">Modify the Display of Names on the Vertical Axis</span></span>](#Sort)  
  
5.  [<span data-ttu-id="273a0-116">Verschieben der Legende</span><span class="sxs-lookup"><span data-stu-id="273a0-116">Move the Legend</span></span>](#Legend)  
  
6.  [<span data-ttu-id="273a0-117">Verschieben des Diagrammtitels</span><span class="sxs-lookup"><span data-stu-id="273a0-117">Move the Chart Title</span></span>](#ChartTitle)  
  
7.  [<span data-ttu-id="273a0-118">Formatieren und Beschriften der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-118">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
8.  [<span data-ttu-id="273a0-119">Hinzufügen eines Filters zum Anzeigen der fünf besten Werte</span><span class="sxs-lookup"><span data-stu-id="273a0-119">Add a Filter to Display the Top Five Values</span></span>](#Filter)  
  
9. [<span data-ttu-id="273a0-120">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="273a0-120">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="273a0-121">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="273a0-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="273a0-122">In diesem Lernprogramm werden die Schritte für den Assistenten in einem Verfahren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="273a0-122">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="273a0-123">Detaillierte Anweisungen zum Navigieren zu einem Berichtsserver, zum Erstellen eines Datasets und zum Auswählen einer Datenquelle finden Sie im ersten Tutorial dieser Reihe unter [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="273a0-123">For step-by-step instructions about how to browse to a report server, create a dataset, and choose a data source, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="273a0-124">Geschätzte Zeit zum Bearbeiten dieses Tutorials: 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="273a0-124">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="273a0-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="273a0-125">Requirements</span></span>  
 <span data-ttu-id="273a0-126">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="273a0-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="273a0-127">1. Erstellen eines Diagramm Berichts mithilfe des Diagramm-Assistenten</span><span class="sxs-lookup"><span data-stu-id="273a0-127">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="273a0-128">Erstellen Sie im Dialogfeld " **Getting Started** " ein eingebettetes DataSet, wählen Sie eine freigegebene Datenquelle aus, und erstellen Sie mithilfe des Diagramm-Assistenten ein Balkendiagramm.</span><span class="sxs-lookup"><span data-stu-id="273a0-128">From the **Getting Started** dialog box, create an embedded dataset, choose a shared data source, and create a bar chart by using the Chart Wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="273a0-129">In diesem Tutorial sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="273a0-129">In this tutorial, the query contains the data values so that it does not need an external data source.</span></span> <span data-ttu-id="273a0-130">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="273a0-130">This makes the query quite long.</span></span> <span data-ttu-id="273a0-131">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="273a0-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="273a0-132">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="273a0-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="273a0-133">So erstellen Sie einen neuen Diagrammbericht</span><span class="sxs-lookup"><span data-stu-id="273a0-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="273a0-134">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="273a0-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="273a0-135">Das Dialogfeld " **Getting Started** " wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-135">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="273a0-136">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf die Schaltfläche Berichts-Generator, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="273a0-136">If the **Getting Started** dialog box does not appear, click the Report Builder button, and then click **New**.</span></span>  
  
2.  <span data-ttu-id="273a0-137">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="273a0-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="273a0-138">Klicken Sie im rechten Bereich auf **Diagramm-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="273a0-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="273a0-139">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="273a0-140">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichtsserver, und wählen Sie eine Datenquelle aus. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="273a0-141">Möglicherweise müssen Benutzername und Kennwort eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="273a0-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="273a0-142">Welche Datenquelle Sie auswählen, ist unwichtig, solange Sie über ausreichende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="273a0-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="273a0-143">Aus der Datenquelle werden keine Daten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="273a0-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="273a0-144">Weitere Informationen finden Sie unter [Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="273a0-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="273a0-145">Klicken Sie auf der Seite **Abfrage entwerfen** auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="273a0-145">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="273a0-146">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="273a0-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Luis' as FirstName, 'Alverca' as LastName, CAST(170000.00 AS money) AS SalesYear2009, CAST(150000. AS money) AS SalesYear2008  
    UNION SELECT 'Jeffrey' as FirstName, 'Zeng' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(190000. AS money) AS SalesYear2008  
    UNION SELECT 'Houman' as FirstName, 'Pournasseh' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Robin' as FirstName, 'Wood' as LastName, CAST(75000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'Daniela' as FirstName, 'Guaita' as LastName,  CAST(170000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'John' as FirstName, 'Yokim' as LastName, CAST(160000. AS money) AS SalesYear2009, CAST(195000. AS money) AS SalesYear2008  
    UNION SELECT 'Delphine' as FirstName, 'Ribaute' as LastName, CAST(180000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Robert' as FirstName, 'Hernady' as LastName, CAST(140000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Tanja' as FirstName, 'Plate' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(160000. AS money) AS SalesYear2008  
    UNION SELECT 'David' as FirstName, 'Bradley' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Michal' as FirstName, 'Jaworski' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(220000. AS money) AS SalesYear2008  
    UNION SELECT 'Chris' as FirstName, 'Ashton' as LastName, CAST(195000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Pongsiri' as FirstName, 'Hirunyanitiwatna' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(215000. AS money) AS SalesYear2008  
    UNION SELECT 'Brian' as FirstName, 'Burke' as LastName, CAST(187000. AS money) AS SalesYear2009, CAST(207000. AS money) AS SalesYear2008  
    ```  
  
8.  <span data-ttu-id="273a0-147">(Optional) Klicken Sie auf die Schaltfläche Ausführen (**!**), um die Daten anzuzeigen, auf denen das Diagramm basiert.</span><span class="sxs-lookup"><span data-stu-id="273a0-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="273a0-148">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="273a0-149">2. Wählen Sie den Diagrammtyp aus.</span><span class="sxs-lookup"><span data-stu-id="273a0-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="273a0-150">Sie können aus einer Vielzahl vordefinierter Diagrammtypen auswählen.</span><span class="sxs-lookup"><span data-stu-id="273a0-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="273a0-151">So fügen Sie einem Bericht ein Säulendiagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="273a0-151">To add a column chart</span></span>  
  
1.  <span data-ttu-id="273a0-152">Das Säulendiagramm ist der Standarddiagrammtyp der Seite **Diagrammtyp auswählen** .</span><span class="sxs-lookup"><span data-stu-id="273a0-152">On the **Choose a chart type** page, the column chart is the default chart type.</span></span>  
  
2.  <span data-ttu-id="273a0-153">Klicken Sie auf **Balken**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-153">Click **Bar**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="273a0-154">Auf der Seite **Diagramm Felder anordnen** befinden sich vier Felder im **Bereich Verfügbare Felder** : FirstName, LastName, "salesyear2009" und "salesyear2008".</span><span class="sxs-lookup"><span data-stu-id="273a0-154">On the **Arrange chart fields** page, there are four fields in the **Available fields** pane: FirstName, LastName, SalesYear2009, and SalesYear2008.</span></span>  
  
3.  <span data-ttu-id="273a0-155">Ziehen Sie "LastName" in den Bereich "Kategorien".</span><span class="sxs-lookup"><span data-stu-id="273a0-155">Drag LastName to the Categories pane.</span></span>  
  
4.  <span data-ttu-id="273a0-156">Ziehen Sie "SalesYear2009" in den Bereich "Werte".</span><span class="sxs-lookup"><span data-stu-id="273a0-156">Drag SalesYear2009 to the Values pane.</span></span> <span data-ttu-id="273a0-157">"SalesYear2009" steht für den Umsatz der einzelnen Vertriebsmitarbeiter im Jahr 2009.</span><span class="sxs-lookup"><span data-stu-id="273a0-157">SalesYear2009 represents the sales amount for each salesperson for the year 2009.</span></span> <span data-ttu-id="273a0-158">Im Bereich Werte wird `[Sum(SalesYear2009)]` angezeigt, da im Diagramm der aggregierte Wert für die einzelnen Produkte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="273a0-158">The Values pane displays `[Sum(SalesYear2009)]` because the chart displays the aggregate for each product.</span></span>  
  
5.  <span data-ttu-id="273a0-159">Ziehen Sie "SalesYear2008" im Bereich "Werte" unter "SalesYear2009".</span><span class="sxs-lookup"><span data-stu-id="273a0-159">Drag SalesYear2008 to the Values pane under SalesYear2009.</span></span> <span data-ttu-id="273a0-160">"SalesYear2008" steht für den Umsatz der einzelnen Vertriebsmitarbeiter im Jahr 2008.</span><span class="sxs-lookup"><span data-stu-id="273a0-160">SalesYear2008 represents the sales amount for each salesperson for the year 2008.</span></span>  
  
6.  <span data-ttu-id="273a0-161">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-161">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="273a0-162">Wählen Sie auf der Seite Format **auswählen** im Bereich Stile einen Stil aus.</span><span class="sxs-lookup"><span data-stu-id="273a0-162">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="273a0-163">Ein Format dient zum Angeben eines Schriftschnitts, einer Farbpalette und einer Rahmenart.</span><span class="sxs-lookup"><span data-stu-id="273a0-163">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="273a0-164">Wenn Sie ein Format auswählen, wird im Vorschaubereich ein Beispiel für das Diagramm mit diesem Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-164">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
8.  <span data-ttu-id="273a0-165">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="273a0-165">Click **Finish**.</span></span>  
  
     <span data-ttu-id="273a0-166">Das Diagramm wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="273a0-166">The chart is added to the design surface.</span></span>  
  
9. <span data-ttu-id="273a0-167">Klicken Sie auf das Diagramm, um die Diagrammziehpunkte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-167">Click the chart to display the chart handles.</span></span> <span data-ttu-id="273a0-168">Ziehen Sie die rechte untere Ecke des Diagramms, um das Diagramm zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="273a0-168">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span>  
  
10. <span data-ttu-id="273a0-169">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="273a0-170">Im Bericht wird das Balkendiagramm für die Umsätze der einzelnen Vertriebsmitarbeiter in den Jahren 2008 und 2009 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-170">The report displays the bar chart for sales for each sales person for the years 2008 and 2009.</span></span> <span data-ttu-id="273a0-171">Die Balkenlänge entspricht dem jeweiligen Gesamtumsatz.</span><span class="sxs-lookup"><span data-stu-id="273a0-171">The length of the bar corresponds to the sales total.</span></span>  
  
##  <a name="3-modify-the-display-of-names-on-the-vertical-axis"></a><a name="AllValues"></a><span data-ttu-id="273a0-172">3. Ändern der Anzeige von Namen auf der vertikalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-172">3. Modify the Display of Names on the Vertical Axis</span></span>  
 <span data-ttu-id="273a0-173">Standardmäßig werden auf der vertikalen Achse nur einige der Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-173">By default, only some of the values on the vertical axis appear.</span></span> <span data-ttu-id="273a0-174">Sie können das Diagramm so ändern, dass alle Kategorien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="273a0-174">You can change the chart to display all categories.</span></span>  
  
#### <a name="to-display-all-sales-persons-along-the-category-axis-of-a-bar-chart"></a><span data-ttu-id="273a0-175">So zeigen Sie auf der Kategorieachse eines Balkendiagramms alle Vertriebsmitarbeiter an</span><span class="sxs-lookup"><span data-stu-id="273a0-175">To display all sales persons along the category axis of a bar chart</span></span>  
  
1.  <span data-ttu-id="273a0-176">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-177">Klicken Sie mit der rechten Maustaste auf die vertikale Achse, und klicken Sie auf **Eigenschaften für vertikale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="273a0-177">Right-click the vertical axis, and then click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="273a0-178">Geben Sie unter **Achsenbereich und -intervall**im Feld **Intervall** den Wert **1**ein.</span><span class="sxs-lookup"><span data-stu-id="273a0-178">Under **Axis range and interval**, in the **Interval** box, type **1**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="273a0-179">Klicken Sie mit der rechten Maustaste auf den Titel der vertikalen **Achse** , und deaktivieren Sie das Kontrollkästchen **Achsentitel anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="273a0-179">Right-click the vertical **Axis Title** and clear the **Show Axis Title** check box.</span></span>  
  
6.  <span data-ttu-id="273a0-180">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-180">Click **Run** to preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="273a0-181">Wenn Sie die Namen der Vertriebsmitarbeiter auf der vertikalen Achse nicht lesen können, können Sie das Diagramm vergrößern oder die Formatierungsoptionen für die Achsenbezeichnungen ändern.</span><span class="sxs-lookup"><span data-stu-id="273a0-181">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
###  <a name="display-last-name-and-first-name-on-vertical-axis"></a><a name="CategoryExpression"></a><span data-ttu-id="273a0-182">Nachname und Vorname auf vertikaler Achse anzeigen</span><span class="sxs-lookup"><span data-stu-id="273a0-182">Display Last Name and First Name on Vertical Axis</span></span>  
 <span data-ttu-id="273a0-183">Sie können den Kategorieausdruck so ändern, dass die Nach- und Vornamen der einzelnen Vertriebsmitarbeiter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="273a0-183">You can change the category expression to include last name followed by first name of each sales person.</span></span>  
  
##### <a name="to-change-the-category-expression"></a><span data-ttu-id="273a0-184">So ändern Sie den Kategorieausdruck</span><span class="sxs-lookup"><span data-stu-id="273a0-184">To change the category expression</span></span>  
  
1.  <span data-ttu-id="273a0-185">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-185">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-186">Doppelklicken Sie auf das Diagramm, um den Bereich **Diagrammdaten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-186">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="273a0-187">Klicken Sie mit der rechten Maustaste im Bereich **Kategoriegruppen** auf „[LastName]“, und klicken Sie anschließend auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="273a0-187">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="273a0-188">Klicken Sie unter "Bezeichnung" auf die Ausdrucksschaltfläche ("Fx").</span><span class="sxs-lookup"><span data-stu-id="273a0-188">In Label, click the expression (Fx) button.</span></span>  
  
5.  <span data-ttu-id="273a0-189">Geben Sie den folgenden Ausdruck ein: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="273a0-189">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
     <span data-ttu-id="273a0-190">Durch diesen Ausdruck wird eine Verkettung aus dem Nachnamen, einem Komma und dem Vornamen erstellt.</span><span class="sxs-lookup"><span data-stu-id="273a0-190">This expression concatenates the last name, a comma, and the first name.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="273a0-191">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-191">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="273a0-192">Sollten beim Ausführen des Berichts keine Vornamen angezeigt werden, können Sie die Daten manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="273a0-192">If the first names do not appear when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="273a0-193">Klicken Sie im Vorschaumodus auf der Registerkarte **Ausführen** in der Gruppe **Navigation** auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="273a0-193">While still in preview mode, on the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="273a0-194">Wenn Sie die Namen der Vertriebsmitarbeiter auf der vertikalen Achse nicht lesen können, können Sie das Diagramm vergrößern oder die Formatierungsoptionen für die Achsenbezeichnungen ändern.</span><span class="sxs-lookup"><span data-stu-id="273a0-194">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
##  <a name="4-change-the-sort-order-for-names-on-the-vertical-axis"></a><a name="Sort"></a><span data-ttu-id="273a0-195">4. Ändern der Sortierreihenfolge für Namen auf der vertikalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-195">4. Change the Sort Order for Names on the Vertical Axis</span></span>  
 <span data-ttu-id="273a0-196">Beim Sortieren der Daten eines Diagramms wird die Reihenfolge der Werte auf der Kategorieachse geändert.</span><span class="sxs-lookup"><span data-stu-id="273a0-196">When you sort the data on a chart, you are changing the order of values on the category axis.</span></span>  
  
#### <a name="to-sort-the-names-in-alphabetical-order-on-the-bar-chart"></a><span data-ttu-id="273a0-197">So sortieren Sie die Namen im Balkendiagramm in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="273a0-197">To sort the names in alphabetical order on the bar chart</span></span>  
  
1.  <span data-ttu-id="273a0-198">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-198">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-199">Doppelklicken Sie auf das Diagramm, um den Bereich **Diagrammdaten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-199">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="273a0-200">Klicken Sie mit der rechten Maustaste im Bereich **Kategoriegruppen** auf „[LastName]“, und klicken Sie anschließend auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="273a0-200">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="273a0-201">Klicken Sie auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="273a0-201">Click **Sorting**.</span></span> <span data-ttu-id="273a0-202">Auf der Seite **Ändern Sie die Sortieroptionen** wird eine Liste mit Sortierausdrücken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-202">The **Change sorting options** page displays a list of sort expressions.</span></span> <span data-ttu-id="273a0-203">Standardmäßig enthält diese Liste einen einzelnen Sortierungsausdruck, der dem ursprünglichen Kategoriegruppenausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="273a0-203">By default, this list has one sort expression that is the same as the original category group expression.</span></span>  
  
5.  <span data-ttu-id="273a0-204">Klicken Sie unter Sortieren nach auf die Ausdrucks Schaltfläche (**FX**).</span><span class="sxs-lookup"><span data-stu-id="273a0-204">In Sort by, click the expression (**Fx**) button.</span></span>  
  
6.  <span data-ttu-id="273a0-205">Geben Sie den folgenden Ausdruck ein: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="273a0-205">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
7.  <span data-ttu-id="273a0-206">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="273a0-206">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="273a0-207">Wählen Sie auf der Seite **Kategoriegruppeneigenschaften** in der Dropdown Liste **Reihenfolge** die Option **Z bis A**aus. Dadurch wird die umgekehrte alphabetische Reihenfolge ausgewählt, sodass die Namen in der Reihenfolge von oben nach unten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="273a0-207">Back on the **Category Group Properties** page, in the **Order** drop-down list, select **Z to A**. This selects reverse alphabetical order so that the names appear in order from top to bottom.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="273a0-208">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-208">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="273a0-209">Die Namen auf der horizontalen Achse werden in umgekehrter Reihenfolge sortiert, wobei **alerca** oben und **Zeng** unten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="273a0-209">The names on the horizontal axis are sorted in reverse order, with **Alerca** at the top and **Zeng** at the bottom.</span></span>  
  
##  <a name="5-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="273a0-210">5. Verschieben der Legende</span><span class="sxs-lookup"><span data-stu-id="273a0-210">5. Move the Legend</span></span>  
 <span data-ttu-id="273a0-211">Um die Lesbarkeit der Diagrammwerte zu verbessern, können Sie gegebenenfalls die Diagrammlegende verschieben.</span><span class="sxs-lookup"><span data-stu-id="273a0-211">To improve the readability of the chart values, you might want to move the chart legend.</span></span> <span data-ttu-id="273a0-212">So können Sie zum Beispiel in einem Balkendiagramm mit einer horizontalen Anordnung der Balken die Legende oberhalb oder unterhalb des Diagrammbereichs platzieren.</span><span class="sxs-lookup"><span data-stu-id="273a0-212">For example, in a bar chart where bars are shown horizontally, you can change the position of the legend so that it is above or below the chart area.</span></span> <span data-ttu-id="273a0-213">Dann bleibt horizontal mehr Platz für die Balken.</span><span class="sxs-lookup"><span data-stu-id="273a0-213">This gives more horizontal space to the bars.</span></span>  
  
#### <a name="to-display-the-legend-below-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="273a0-214">So zeigen Sie die Legende unterhalb des Diagrammbereichs eines Balkendiagramms an</span><span class="sxs-lookup"><span data-stu-id="273a0-214">To display the legend below the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="273a0-215">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-215">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-216">Klicken Sie mit der rechten Maustaste auf die Legende des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="273a0-216">Right-click the legend on the chart.</span></span>  
  
3.  <span data-ttu-id="273a0-217">Wählen Sie **Legendeneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="273a0-217">Select **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="273a0-218">Wählen Sie unter **Legendenposition**eine andere Position aus.</span><span class="sxs-lookup"><span data-stu-id="273a0-218">For **Legend position**, select a different position.</span></span> <span data-ttu-id="273a0-219">Legen Sie z. B. eine Position unten in der Mitte fest.</span><span class="sxs-lookup"><span data-stu-id="273a0-219">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="273a0-220">Wenn Sie die Legende über oder unter einem Diagramm platzieren, ändert sich das Layout der Legende von vertikal zu horizontal.</span><span class="sxs-lookup"><span data-stu-id="273a0-220">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="273a0-221">In der Dropdownliste **Layout** können Sie ein anderes Layout auswählen.</span><span class="sxs-lookup"><span data-stu-id="273a0-221">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="273a0-222">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-222">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="273a0-223">6. Titel des Diagramms</span><span class="sxs-lookup"><span data-stu-id="273a0-223">6. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="273a0-224">So ändern Sie den Diagrammtitel über dem Diagrammbereich eines Balkendiagramms</span><span class="sxs-lookup"><span data-stu-id="273a0-224">To change the chart title above the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="273a0-225">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-225">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-226">Markieren Sie am oberen Rand des Diagramms den Text **Diagramm Titel** , und geben Sie dann den folgenden Text ein: **Sales für 2008 und 2009**.</span><span class="sxs-lookup"><span data-stu-id="273a0-226">Select the words **Chart Title** at the top of the chart, and then type the following text: **Sales for 2008 and 2009**.</span></span>  
  
3.  <span data-ttu-id="273a0-227">Klicken Sie auf eine Stelle außerhalb des Texts.</span><span class="sxs-lookup"><span data-stu-id="273a0-227">Click anywhere outside the text.</span></span>  
  
4.  <span data-ttu-id="273a0-228">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-228">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="273a0-229">7. Formatieren und beschriften der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-229">7. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="273a0-230">Standardmäßig werden die Werte auf der horizontalen Achse in einem allgemeinen Format angezeigt, dessen Größe automatisch an die Diagrammgröße angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="273a0-230">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-the-numbers-on-the-horizontal-axis"></a><span data-ttu-id="273a0-231">So formatieren Sie die Zahlen auf der horizontalen Achse</span><span class="sxs-lookup"><span data-stu-id="273a0-231">To format the numbers on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="273a0-232">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-232">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-233">Klicken Sie unten im Diagramm auf die horizontale Achse, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="273a0-233">Click the horizontal axis along the bottom of the chart to select it.</span></span>  
  
     <span data-ttu-id="273a0-234">Klicken Sie im Menüband auf der Registerkarte **Startseite** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="273a0-234">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="273a0-235">Die horizontalen Achsenbezeichnungen werden zu Währungsbezeichnungen geändert.</span><span class="sxs-lookup"><span data-stu-id="273a0-235">The horizontal axis labels change to currency.</span></span>  
  
3.  <span data-ttu-id="273a0-236">(Optional) Entfernen Sie die Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="273a0-236">(Optional) Remove the decimal digits.</span></span> <span data-ttu-id="273a0-237">Klicken Sie in der Nähe der Schaltfläche **Währung** zweimal auf die Schaltfläche **Dezimalstelle löschen** .</span><span class="sxs-lookup"><span data-stu-id="273a0-237">Near the **Currency** button, click the **Decrease Decimal** button twice.</span></span>  
  
4.  <span data-ttu-id="273a0-238">Klicken Sie mit der rechten Maustaste auf die horizontale Achse, und klicken Sie anschließend auf **Eigenschaften für horizontale Achsen**.</span><span class="sxs-lookup"><span data-stu-id="273a0-238">Right-click the horizontal axis, and click **Horizontal Axis Properties**.</span></span>  
  
5.  <span data-ttu-id="273a0-239">Wählen Sie auf der Registerkarte **Zahl** die Option **Werte in Tausenden anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="273a0-239">On the **Number** tab, select **Show values in Thousands.**</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="273a0-240">Klicken Sie mit der rechten Maustaste auf **Achsentitel** und dann auf **Achsentitel Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="273a0-240">Right-click **Axis Title** and click **Axis Title Properties**.</span></span>  
  
8.  <span data-ttu-id="273a0-241">Geben Sie im **Textfeld Titel** **Sales in Tausende** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="273a0-241">In the **Title text** box, type **Sales in thousands** and click **OK**.</span></span>  
  
9. <span data-ttu-id="273a0-242">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-242">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="273a0-243">Auf der horizontalen Achse des Berichts werden die Umsätze als Währung in Tausendern ohne Dezimalstellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-243">The report displays the sales amount on the horizontal axis as currency in thousands, and has no decimal digits.</span></span>  
  
##  <a name="8-add-a-filter-to-display-the-top-five-values"></a><a name="Filter"></a><span data-ttu-id="273a0-244">8. Hinzufügen eines Filters zum Anzeigen der fünf besten Werte</span><span class="sxs-lookup"><span data-stu-id="273a0-244">8. Add a Filter to Display the Top Five Values</span></span>  
 <span data-ttu-id="273a0-245">Sie können dem Diagramm einen Filter hinzufügen, um anzugeben, welche Daten des Datasets ein- oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="273a0-245">You can add a filter to the chart to specify which data from the dataset to include or exclude in the chart.</span></span>  
  
#### <a name="to-add-a-filter-and-display-the-top-five-values"></a><span data-ttu-id="273a0-246">So können Sie einen Filtern hinzufügen und die fünf besten Werte anzeigen</span><span class="sxs-lookup"><span data-stu-id="273a0-246">To add a filter and display the top five values</span></span>  
  
1.  <span data-ttu-id="273a0-247">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-247">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-248">Doppelklicken Sie auf das Diagramm, um den Bereich **Diagrammdaten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-248">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="273a0-249">Klicken Sie im Bereich **Kategoriegruppen** mit der rechten Maustaste auf das Feld [LastName]. Klicken Sie danach auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="273a0-249">In the **Category Groups** area, right-click the [LastName] field, and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="273a0-250">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-250">Click **Filters**.</span></span> <span data-ttu-id="273a0-251">Die Seite **Filter ändern** zeigt eine Liste von Filterausdrücken an.</span><span class="sxs-lookup"><span data-stu-id="273a0-251">The **Change filters** page can display a list of filter expressions.</span></span> <span data-ttu-id="273a0-252">Standardmäßig ist diese Liste leer.</span><span class="sxs-lookup"><span data-stu-id="273a0-252">By default, this list is empty.</span></span>  
  
5.  <span data-ttu-id="273a0-253">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="273a0-253">Click **Add**.</span></span> <span data-ttu-id="273a0-254">Ein neuer leerer Filter wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-254">A new blank filter appears.</span></span>  
  
6.  <span data-ttu-id="273a0-255">Geben **Expression**Sie in Ausdruck **[Sum ("salesyear2009")]** ein.</span><span class="sxs-lookup"><span data-stu-id="273a0-255">In **Expression**, type **[Sum(SalesYear2009)]**.</span></span> <span data-ttu-id="273a0-256">Dadurch wird der zugrunde liegende Ausdruck `=Sum(Fields!SalesYear2009.Value)`erstellt, der durch Klicken auf die Schaltfläche **fx** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="273a0-256">This creates the underlying expression `=Sum(Fields!SalesYear2009.Value)`, which you can see if you click the **fx** button.</span></span>  
  
7.  <span data-ttu-id="273a0-257">Überprüfen Sie, ob der Datentyp gleich **Text**ist.</span><span class="sxs-lookup"><span data-stu-id="273a0-257">Verify that the data type is **Text**.</span></span>  
  
8.  <span data-ttu-id="273a0-258">Wählen Sie in **Operator**in der Dropdownliste den Eintrag **Erste N** aus.</span><span class="sxs-lookup"><span data-stu-id="273a0-258">In **Operator**, select **Top N** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="273a0-259">Geben Sie unter **Wert**den folgenden Ausdruck ein: **=5**</span><span class="sxs-lookup"><span data-stu-id="273a0-259">In **Value**, type the following expression: **=5**</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="273a0-260">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-260">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="273a0-261">Sollten die Ergebnisse nicht gefiltert werden, wenn Sie den Bericht ausführen, können Sie die Daten manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="273a0-261">If the results are not filtered when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="273a0-262">Klicken Sie auf der Registerkarte **Ausführen** in der Gruppe **Navigation** auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="273a0-262">On the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
 <span data-ttu-id="273a0-263">Im Diagramm werden die Namen der fünf besten Vertriebsmitarbeiter gemäß den Umsatzdaten des Jahres 2009 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-263">The chart shows the top five salesperson names from the 2009 sales data.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="273a0-264">9. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="273a0-264">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="273a0-265">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="273a0-265">To add a report title</span></span>  
  
1.  <span data-ttu-id="273a0-266">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="273a0-266">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="273a0-267">Geben Sie **Umsatz-Balkendiagramm**ein, drücken Sie die EINGABETASTE, und geben Sie dann **Top Five-Verkäufer für 2009**ein, sodass es wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="273a0-267">Type **Sales Bar Chart**, press ENTER, and then type **Top Five Sellers for 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="273a0-268">**Umsatz-Balkendiagramm**</span><span class="sxs-lookup"><span data-stu-id="273a0-268">**Sales Bar Chart**</span></span>  
  
     <span data-ttu-id="273a0-269">**Top Five-Verkaufsschlager 2009**</span><span class="sxs-lookup"><span data-stu-id="273a0-269">**Top Five Sellers for 2009**</span></span>  
  
3.  <span data-ttu-id="273a0-270">Markieren Sie **Umsatz-Balkendiagramm**, und klicken Sie auf die Schaltfläche **Fett** .</span><span class="sxs-lookup"><span data-stu-id="273a0-270">Select **Sales Bar Chart**, and click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="273a0-271">Wählen Sie **Top Five Verkäufers for 2009 aus**, und legen Sie auf der Registerkarte **Home** im Abschnitt **Schriftart** den Schrift Grad auf **10**fest.</span><span class="sxs-lookup"><span data-stu-id="273a0-271">Select **Top Five Sellers for 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="273a0-272">(Optional) Das Textfeld "Titel" muss ggf. vergrößert werden, damit die beiden Textzeilen hineinpassen.</span><span class="sxs-lookup"><span data-stu-id="273a0-272">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="273a0-273">Dieser Titel wird am Anfang des Berichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273a0-273">This title will appear at the top of the report.</span></span> <span data-ttu-id="273a0-274">Ist keine Kopfzeile definiert, erfüllen die Elemente über dem Berichtshauptteil die Funktion einer Berichtskopfzeile.</span><span class="sxs-lookup"><span data-stu-id="273a0-274">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="273a0-275">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="273a0-275">Click **Run** to preview the report.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="273a0-276">10. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="273a0-276">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="273a0-277">So speichern Sie den Bericht</span><span class="sxs-lookup"><span data-stu-id="273a0-277">To save the report</span></span>  
  
1.  <span data-ttu-id="273a0-278">Wechseln Sie zur Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="273a0-278">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="273a0-279">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="273a0-279">From the **Report Builder** button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="273a0-280">Geben Sie im Feld **Name**die Zeichenfolge **Umsatz-Balkendiagramm**ein.</span><span class="sxs-lookup"><span data-stu-id="273a0-280">In **Name**, type **Sales Bar Chart**.</span></span>  
  
4.  <span data-ttu-id="273a0-281">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="273a0-281">Click **Save**.</span></span>  
  
 <span data-ttu-id="273a0-282">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="273a0-282">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="273a0-283">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="273a0-283">Next Steps</span></span>  
 <span data-ttu-id="273a0-284">Sie haben das Lernprogramm "Hinzufügen eines Balkendiagramms zu einem Bericht" erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="273a0-284">You have successfully completed the Adding a Bar Chart to Your Report tutorial.</span></span> <span data-ttu-id="273a0-285">Weitere Informationen zu Diagrammen finden Sie unter [Diagramme (Berichts-Generator und SSRS)](report-design/charts-report-builder-and-ssrs.md) und [Sparklines und Datenbalken (Berichts-Generator und SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="273a0-285">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="273a0-286">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="273a0-286">See Also</span></span>  
 <span data-ttu-id="273a0-287">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="273a0-287">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="273a0-288">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="273a0-288">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
