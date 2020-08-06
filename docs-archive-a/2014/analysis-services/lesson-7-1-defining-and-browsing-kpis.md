---
title: Definieren und Durchsuchen von KPIs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 648b9a02-1278-4f11-b940-6f0de6a4042d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44febe6c6c5d432f0cdee43e8eaaa3401c54a2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698750"
---
# <a name="defining-and-browsing-kpis"></a><span data-ttu-id="b47ad-102">Definieren und Durchsuchen von KPIs</span><span class="sxs-lookup"><span data-stu-id="b47ad-102">Defining and Browsing KPIs</span></span>
  <span data-ttu-id="b47ad-103">Zum Definieren von KPIs (Key Performance Indicators) müssen Sie zuerst einen KPI-Namen und die Measuregruppe definieren, der der KPI zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="b47ad-103">To define key performance indicators (KPIs), you first define a KPI name and the measure group to which the KPI is associated.</span></span> <span data-ttu-id="b47ad-104">Ein KPI kann entweder allen Measuregruppen oder einer einzelnen Measuregruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b47ad-104">A KPI can be associated with all measure groups or with a single measure group.</span></span> <span data-ttu-id="b47ad-105">Anschließend definieren Sie die folgenden Elemente des KPIs:</span><span class="sxs-lookup"><span data-stu-id="b47ad-105">You then define the following elements of the KPI:</span></span>

-   <span data-ttu-id="b47ad-106">Der Wertausdruck</span><span class="sxs-lookup"><span data-stu-id="b47ad-106">The value expression</span></span>

     <span data-ttu-id="b47ad-107">Ein Wertausdruck ist ein physisches Measure, wie z. B. Sales, ein berechnetes Measure, wie z. B. Profit, oder eine innerhalb des KPIs mithilfe eines MDX-Ausdrucks (Multidimensional Expressions) definierte Berechnung.</span><span class="sxs-lookup"><span data-stu-id="b47ad-107">A value expression is a physical measure such as Sales, a calculated measure such as Profit, or a calculation that is defined within the KPI by using a Multidimensional Expressions (MDX) expression.</span></span>

-   <span data-ttu-id="b47ad-108">Der Zielausdruck</span><span class="sxs-lookup"><span data-stu-id="b47ad-108">The goal expression</span></span>

     <span data-ttu-id="b47ad-109">Ein Zielausdruck ist ein Wert oder MDX-Ausdruck, der zu einem Wert aufgelöst wird, welcher das Ziel für das Measure definiert, das durch den Wertausdruck definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b47ad-109">A goal expression is a value, or an MDX expression that resolves to a value, that defines the target for the measure that the value expression defines.</span></span> <span data-ttu-id="b47ad-110">Ein Zielausdruck könnte beispielsweise der Betrag sein, um den die Geschäftsmanager eines Unternehmens die Verkaufszahlen oder Gewinne steigern möchten.</span><span class="sxs-lookup"><span data-stu-id="b47ad-110">For example, a goal expression could be the amount by which the business managers of a company want to increase sales or profit.</span></span>

-   <span data-ttu-id="b47ad-111">Der Statusausdruck</span><span class="sxs-lookup"><span data-stu-id="b47ad-111">The status expression</span></span>

     <span data-ttu-id="b47ad-112">Ein Statusausdruck ist ein MDX-Ausdruck, der von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] zum Auswerten des aktuellen Status des Wertausdrucks im Vergleich zum Zielausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b47ad-112">A status expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current status of the value expression compared to the goal expression.</span></span> <span data-ttu-id="b47ad-113">Ein Zielausdruck ist ein normalisierter Wert zwischen -1 und +1, wobei -1 für sehr schlecht und +1 für sehr gut steht.</span><span class="sxs-lookup"><span data-stu-id="b47ad-113">A goal expression is a normalized value in the range of -1 to +1, where -1 is very bad, and +1 is very good.</span></span> <span data-ttu-id="b47ad-114">Der Statusausdruck wird mithilfe einer Grafik dargestellt, damit Sie problemlos den Status des Wertausdrucks im Vergleich zum Zielausdruck bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="b47ad-114">The status expression displays a graphic to help you easily determine the status of the value expression compared to the goal expression.</span></span>

-   <span data-ttu-id="b47ad-115">Der Trendausdruck</span><span class="sxs-lookup"><span data-stu-id="b47ad-115">The trend expression</span></span>

     <span data-ttu-id="b47ad-116">Ein Trendausdruck ist ein MDX-Ausdruck, der von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] zum Auswerten des aktuellen Trends des Wertausdrucks im Vergleich zum Zielausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b47ad-116">A trend expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current trend of the value expression compared to the goal expression.</span></span> <span data-ttu-id="b47ad-117">Mithilfe des Trendausdrucks kann der Anwender des Produkts im geschäftlichen Bereich rasch erkennen, ob sich der Wertausdruck im Hinblick auf den Zielausdruck verbessert oder verschlechtert.</span><span class="sxs-lookup"><span data-stu-id="b47ad-117">The trend expression helps the business user to quickly determine whether the value expression is becoming better or worse relative to the goal expression.</span></span> <span data-ttu-id="b47ad-118">Sie können dem Trendausdruck eine von mehreren Grafiken zuordnen, damit Anwender des Produkts im geschäftlichen Bereich den Trend schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="b47ad-118">You can associate one of several graphics with the trend expression to help business users be able to quickly understand the trend.</span></span>

 <span data-ttu-id="b47ad-119">Zusätzlich zu diesen Elementen, die für ein KPI definiert werden, können auch verschiedene Eigenschaften eines KPIs definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b47ad-119">In addition to these elements that you define for a KPI, you also define several properties of a KPI.</span></span> <span data-ttu-id="b47ad-120">Zu diesen Eigenschaften gehören ein Anzeigeordner, ein übergeordneter KPI, falls der KPI aus anderen KPIs berechnet wird, ggf. das aktuelle Zeitelement, ggf. die Gewichtung des KPIs sowie eine Beschreibung des KPIs.</span><span class="sxs-lookup"><span data-stu-id="b47ad-120">These properties include a display folder, a parent KPI if the KPI is computed from other KPIs, the current time member if there is one, the weight of the KPI if it has one, and a description of the KPI.</span></span>

> [!NOTE]
>  <span data-ttu-id="b47ad-121">Weitere Beispiele für KPIs finden Sie auf der Registerkarte Vorlagen im Bereich Berechnungstools oder im Data Warehouse-Beispiel **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-121">For more examples of KPIs, see the KPI examples on the Templates tab in the Calculation Tools pane or in the examples in the **Adventure Works DW 2012** sample data warehouse.</span></span> <span data-ttu-id="b47ad-122">Weitere Informationen zum Installieren dieser Datenbank finden Sie unter [Installieren von Beispieldaten und -projekten für das Analysis Services-Tutorial zur mehrdimensionalen Modellierung](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="b47ad-122">For more information about how to install this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

 <span data-ttu-id="b47ad-123">In den Aufgaben in dieser Lektion definieren Sie KPIs im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Projekt und durchsuchen dann den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube mithilfe dieser KPIs.</span><span class="sxs-lookup"><span data-stu-id="b47ad-123">In the task in this lesson, you define  KPIs in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, and you then browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube by using these KPIs.</span></span> <span data-ttu-id="b47ad-124">Sie definieren folgende KPIs:</span><span class="sxs-lookup"><span data-stu-id="b47ad-124">You will define the following KPIs:</span></span>

-   <span data-ttu-id="b47ad-125">Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="b47ad-125">Reseller Revenue</span></span>

     <span data-ttu-id="b47ad-126">Mit diesem KPI wird gemessen, wie sich die tatsächlichen Verkäufe durch Wiederverkäufer im Vergleich zu den Sollvorgaben für den Verkauf verhalten, wie nahe die Verkaufszahlen an das gesetzte Ziel heranreichen und welcher Trend sich hinsichtlich des Zieles abzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b47ad-126">This KPI is used to measure how actual reseller sales compare to sales quotas for reseller sales, how close the sales are to the goal, and what the trend is toward reaching the goal.</span></span>

-   <span data-ttu-id="b47ad-127">Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="b47ad-127">Product Gross Profit Margin</span></span>

     <span data-ttu-id="b47ad-128">Mit diesem KPI wird bestimmt, wie stark sich die Bruttorendite für jede Produktkategorie an das angegebene Ziel für jede Produktkategorie annähert und welcher Trend sich im Hinblick auf die Umsetzung dieses Zieles abzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b47ad-128">This KPI is used to determine how close the gross profit margin is for each product category to a specified goal for each product category, and also to determine the trend toward reaching this goal.</span></span>

## <a name="defining-the-reseller-revenue-kpi"></a><span data-ttu-id="b47ad-129">Definieren des Reseller Revenue-KPI</span><span class="sxs-lookup"><span data-stu-id="b47ad-129">Defining the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="b47ad-130">Öffnen Sie den Cube-Designer für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube, und klicken Sie anschließend auf die Registerkarte **KPIs** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-130">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **KPIs** tab.</span></span>

     <span data-ttu-id="b47ad-131">Die Registerkarte **KPIs** umfasst mehrere Bereiche.</span><span class="sxs-lookup"><span data-stu-id="b47ad-131">The **KPIs** tab includes several panes.</span></span> <span data-ttu-id="b47ad-132">Auf der linken Seite der Registerkarte werden die Bereiche **KPI-Planer** und **Berechnungstools** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b47ad-132">On the left side of the tab are the **KPI Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="b47ad-133">Der Anzeigebereich in der Mitte der Registerkarte enthält die Details des KPIs, der im Bereich **KPI-Planer** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b47ad-133">The display pane in the middle of the tab contains the details of the KPI that is selected in the **KPI Organizer** pane.</span></span>

     <span data-ttu-id="b47ad-134">In der folgenden Abbildung ist die Registerkarte **KPIs** des Cube-Designers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b47ad-134">The following image shows the **KPIs** tab of Cube Designer.</span></span>

     <span data-ttu-id="b47ad-135">![KPIs (Registerkarte des Cube-Designers)](../../2014/tutorials/media/l7-kpi-1.gif "KPIs (Registerkarte des Cube-Designers)")</span><span class="sxs-lookup"><span data-stu-id="b47ad-135">![KPIs tab of Cube Designer](../../2014/tutorials/media/l7-kpi-1.gif "KPIs tab of Cube Designer")</span></span>

2.  <span data-ttu-id="b47ad-136">Klicken Sie auf der Symbolleiste der Registerkarte **KPIs** auf **Neuer KPI** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-136">On the toolbar of the **KPIs** tab, click the **New KPI** button.</span></span>

     <span data-ttu-id="b47ad-137">Im Anzeigebereich wird eine leere KPI-Vorlage angezeigt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b47ad-137">A blank KPI template appears in the display pane, as shown in the following image.</span></span>

     <span data-ttu-id="b47ad-138">![Leere KPI-Vorlage im Anzeigebereich](../../2014/tutorials/media/l7-kpi-2.gif "Leere KPI-Vorlage im Anzeigebereich")</span><span class="sxs-lookup"><span data-stu-id="b47ad-138">![Blank KPI template in display pane](../../2014/tutorials/media/l7-kpi-2.gif "Blank KPI template in display pane")</span></span>

3.  <span data-ttu-id="b47ad-139">Geben Sie im Feld **Name** ein `Reseller Revenue` , und wählen Sie dann **Reseller Sales** in der Liste zugeordnete **Measure-Gruppe** aus.</span><span class="sxs-lookup"><span data-stu-id="b47ad-139">In the **Name** box, type `Reseller Revenue`, and then select **Reseller Sales** in the **Associated measure group** list.</span></span>

4.  <span data-ttu-id="b47ad-140">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungstools** die Optionen **Measures**und **Reseller Sales**, und ziehen Sie anschließend das Measure **Reseller Sales-Sales Amount** in das Feld **Wertausdruck** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Reseller Sales**, and then drag the **Reseller Sales-Sales Amount** measure to the **Value Expression** box.</span></span>

5.  <span data-ttu-id="b47ad-141">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungstools** die Optionen **Measures**und **Sales Quotas**, und ziehen Sie anschließend das Measure **Sales Amount Quota** in das Feld **Zielausdruck** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-141">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Sales Quotas**, and then drag the **Sales Amount Quota** measure to the **Goal Expression** box.</span></span>

6.  <span data-ttu-id="b47ad-142">Überprüfen Sie, ob in der Liste **Statusindikator\*\*\*\*Maßstab** ausgewählt ist, und geben Sie anschließend den folgenden MDX-Ausdruck in das Feld **Statusausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="b47ad-142">Verify that **Gauge** is selected in the **Status indicator** list, and then type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
     When 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.95
       Then 1
     When
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")<.95
       And 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.85
       Then 0
      Else-1
    End
    ```

     <span data-ttu-id="b47ad-143">Dieser MDX-Ausdruck bildet die Grundlage für das Auswerten der Entwicklung im Hinblick auf das Ziel.</span><span class="sxs-lookup"><span data-stu-id="b47ad-143">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span> <span data-ttu-id="b47ad-144">In diesem MDX-Ausdruck wird der Wert 0 zum Auffüllen der ausgewählten Grafik verwendet, wenn die tatsächlichen Verkäufe durch Wiederverkäufer 85 % des gesetzten Zieles überschreiten.</span><span class="sxs-lookup"><span data-stu-id="b47ad-144">In this MDX expression, if actual reseller sales are more than 85 percent of the goal, a value of 0 is used to populate the chosen graphic.</span></span> <span data-ttu-id="b47ad-145">Da ein Maßstab als Grafik gewählt wurde, steht der Zeiger des Maßstabs auf halber Höhe zwischen leer und voll.</span><span class="sxs-lookup"><span data-stu-id="b47ad-145">Because a gauge is the chosen graphic, the pointer in the gauge will be half-way between empty and full.</span></span> <span data-ttu-id="b47ad-146">Überschreiten die tatsächlichen Verkäufe durch Wiederverkäufer 90 Prozent, steht der Zeiger des Maßstabs bei drei Viertel zwischen leer und voll.</span><span class="sxs-lookup"><span data-stu-id="b47ad-146">If actual reseller sales are more the 90 percent, the pointer on the gauge will be three-fourths of the way between empty and full.</span></span>

7.  <span data-ttu-id="b47ad-147">Überprüfen Sie, ob in der Liste **Trendindikator** die Option **Standardpfeil** ausgewählt ist, und geben Sie anschließend den folgenden Ausdruck in das Feld **Trendausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="b47ad-147">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following expression in the **Trend expression** box:</span></span>

    ```
    Case
     When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
     When  (
      KpiValue("Reseller Revenue") - 
       (KpiValue("Reseller Revenue"), 
        ParallelPeriod
         ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
          /
          (KpiValue ("Reseller Revenue"),
           ParallelPeriod
            ([Date].[Calendar Date].[Calendar Year],1,
             [Date].[Calendar Date].CurrentMember)))
           >=.02
      Then 1
       When(
        KpiValue("Reseller Revenue") - 
         (KpiValue ( "Reseller Revenue" ),
          ParallelPeriod
           ([Date].[Calendar Date].[Calendar Year],1,
            [Date].[Calendar Date].CurrentMember))
           /
            (KpiValue("Reseller Revenue"),
             ParallelPeriod
              ([Date].[Calendar Date].[Calendar Year],1,
                [Date].[Calendar Date].CurrentMember)))
            <=.02
      Then -1
       Else 0
    End
    ```

     <span data-ttu-id="b47ad-148">Dieser MDX-Ausdruck bildet die Grundlage für das Auswerten des Trends im Hinblick auf die Umsetzung des festgelegten Zieles.</span><span class="sxs-lookup"><span data-stu-id="b47ad-148">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-reseller-revenue-kpi"></a><span data-ttu-id="b47ad-149">Durchsuchen des Cubes mithilfe des Reseller Revenue-KPI</span><span class="sxs-lookup"><span data-stu-id="b47ad-149">Browsing the Cube by Using the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="b47ad-150">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-150">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="b47ad-151">Klicken Sie nach der erfolgreichen Bereitstellung auf der Symbolleiste der Registerkarte **KPIs** auf **Browseransicht** und anschließend auf **Verbindung wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-151">When deployment has successfully completed, on the toolbar of the **KPIs** tab, click the **Browser View** button, and then click **Reconnect**.</span></span>

     <span data-ttu-id="b47ad-152">Die Status- und Trendmaßstäbe werden im Bereich **KPI-Browser** für die Verkäufe durch Wiederverkäufer auf der Grundlage der Werte für das Standardelement der einzelnen Dimensionen zusammen mit dem Wert für den Wert- und den Zielausdruck angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b47ad-152">The status and trend gauges are displayed in the **KPI Browser** pane for reseller sales based on the values for the default member of each dimension, together with the value for the value and the goal.</span></span> <span data-ttu-id="b47ad-153">Das Standardelement aller Dimensionen ist das All-Element auf der All-Ebene, da Sie kein anderes Element einer Dimension als Standardelement definiert haben.</span><span class="sxs-lookup"><span data-stu-id="b47ad-153">The default member of each dimension is the All member of the All level, because you have not defined any other member of any dimension as the default member.</span></span>

3.  <span data-ttu-id="b47ad-154">Wählen Sie im Bereich Filter in der Liste **Dimension** die Option **Sales Territory** , in der Liste **Hierarchie** die Option **Sales Territories** , in der Liste **Operator** die Option **Gleich** aus, und aktivieren Sie in der Liste **Filterausdruck** das Kontrollkästchen **North America** . Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-154">In the filter pane, select **Sales Territory** in the **Dimension** list, select **Sales Territories** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **North America** check box in the **Filter Expression** list, and then click **OK**.</span></span>

4.  <span data-ttu-id="b47ad-155">Wählen Sie in der nächsten Zeile im Bereich **Filter** in der Liste **Dimension** die Option **Date** , in der Liste **Hierarchie** die Option **Calendar Date** , in der Liste **Operator** die Option **Gleich** aus, und aktivieren Sie in der Liste **Filterausdruck** das Kontrollkästchen **Q3 CY 2007** . Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-155">In the next row in the **Filter** pane, select **Date** in the **Dimension** list, select **Calendar Date** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **Q3 CY 2007** check box in the **Filter Expression** list, and then click **OK**.</span></span>

5.  <span data-ttu-id="b47ad-156">Klicken Sie auf eine beliebige Stelle im Bereich **KPI-Browser** , um die Werte für den **Reseller Revenue**-KPI zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b47ad-156">Click anywhere in the **KPI Browser** pane to update the values for the **Reseller Revenue KPI**.</span></span>

     <span data-ttu-id="b47ad-157">Die Abschnitte **Wert**, **Ziel**und **Status** des KPIs spiegeln die Werte für den neuen Zeitraum wider</span><span class="sxs-lookup"><span data-stu-id="b47ad-157">Notice that the **Value**, **Goal**, and **Status** sections of the KPI reflect the values for the new time period</span></span>

## <a name="defining-the-product-gross-profit-margin-kpi"></a><span data-ttu-id="b47ad-158">Definieren des Product Gross Profit Margin-KPIs</span><span class="sxs-lookup"><span data-stu-id="b47ad-158">Defining the Product Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="b47ad-159">Klicken Sie auf der Symbolleiste der Registerkarte **KPIs** auf **Formularansicht** und anschließend auf die Schaltfläche **Neuer KPI** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-159">Click the **Form View** button on the toolbar of the **KPIs** tab, and then click the **New KPI** button.</span></span>

2.  <span data-ttu-id="b47ad-160">Geben Sie im Feld **Name** ein `Product Gross Profit Margin` , und überprüfen Sie dann, ob **\<All>** in der Liste zugeordnete **Measure-Gruppe** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b47ad-160">In the **Name** box, type `Product Gross Profit Margin`, and then verify that **\<All>** appears in the **Associated measure group** list.</span></span>

3.  <span data-ttu-id="b47ad-161">Ziehen Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungstools** das **Total GPM** -Measure in das Feld **Wertausdruck** .</span><span class="sxs-lookup"><span data-stu-id="b47ad-161">In the **Metadata** tab in the **Calculation Tools** pane, drag the **Total GPM** measure to the **Value Expression** box.</span></span>

4.  <span data-ttu-id="b47ad-162">Geben Sie im Feld **Zielausdruck** den folgenden Ausdruck ein:</span><span class="sxs-lookup"><span data-stu-id="b47ad-162">In the **Goal Expression** box, type the following expression:</span></span>

    ```
    Case
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Accessories]
        Then .40                 
        When [Product].[Category].CurrentMember 
          Is [Product].[Category].[Bikes]
        Then .12                
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Clothing]
        Then .20
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Components]
        Then .10
        Else .12            
    End
    ```

5.  <span data-ttu-id="b47ad-163">Wählen Sie in der Liste **Statusindikator** die Option **Zylinder**aus.</span><span class="sxs-lookup"><span data-stu-id="b47ad-163">In the **Status indicator** list, select **Cylinder**.</span></span>

6.  <span data-ttu-id="b47ad-164">Geben Sie den folgenden MDX-Ausdruck in das Feld **Statusausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="b47ad-164">Type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .90
        Then 1
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) <  .90
             And 
             KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .80
        Then 0
        Else -1
    End
    ```

     <span data-ttu-id="b47ad-165">Dieser MDX-Ausdruck bildet die Grundlage für das Auswerten der Entwicklung im Hinblick auf das Ziel.</span><span class="sxs-lookup"><span data-stu-id="b47ad-165">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span>

7.  <span data-ttu-id="b47ad-166">Überprüfen Sie, dass in der Liste **Trendindikator** die Option **Standardpfeil** ausgewählt ist, und geben Sie anschließend den folgenden MDX-Ausdruck in das Feld **Trendausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="b47ad-166">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following MDX expression in the **Trend expression** box:</span></span>

    ```
    Case
    When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
       When VBA!Abs
        (
          KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            ) /
            (
              KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            )  
          ) <=.02
      Then 0
      When KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[ Calendar Date].[ Calendar Year],
               1,
               [Date].[ Calendar Date].CurrentMember
             )
           ) /
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[Calendar Date].[Calendar Year],
               1,
               [Date].[Calendar Date].CurrentMember
             )
           )  >.02
      Then 1
      Else -1
    End
    ```

     <span data-ttu-id="b47ad-167">Dieser MDX-Ausdruck bildet die Grundlage für das Auswerten des Trends im Hinblick auf die Umsetzung des festgelegten Zieles.</span><span class="sxs-lookup"><span data-stu-id="b47ad-167">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-total-gross-profit-margin-kpi"></a><span data-ttu-id="b47ad-168">Durchsuchen des Cubes mithilfe des Total Gross Profit Margin-KPI</span><span class="sxs-lookup"><span data-stu-id="b47ad-168">Browsing the Cube by Using the Total Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="b47ad-169">Klicken Sie im Menü **Erstellen** auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-169">On the **Build** menu, click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="b47ad-170">Klicken Sie nach der erfolgreichen Bereitstellung auf der Symbolleiste der Registerkarte **KPIs** auf **Verbindung wiederherstellen** und anschließend auf **Browseransicht**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-170">When deployment has successfully completed, click **Reconnect** on the toolbar of the **KPIs** tab, and then click **Browser View**.</span></span>

     <span data-ttu-id="b47ad-171">Der `Product Gross Profit Margin` KPI wird angezeigt und zeigt den KPI-Wert für **Q3 CY 2007** und den **Nordamerika** Sales Territory an.</span><span class="sxs-lookup"><span data-stu-id="b47ad-171">The `Product Gross Profit Margin` KPI appears and displays the KPI value for **Q3 CY 2007** and the **North America** sales territory.</span></span>

3.  <span data-ttu-id="b47ad-172">Wählen Sie im Bereich **Filter** in der Liste **Dimension** die Option **Product** , in der Liste **Hierarchy** die Option **Category** , in der Liste **Operator** die Option **Gleich** und in der Liste **Filterausdruck** die Option **Bikes** aus. Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47ad-172">In the **Filter** pane, select **Product** in the **Dimension** list, select **Category** in the **Hierarchy** list, select **Equal** in the **Operator** list, and then select **Bikes** in the **Filter Expression** list, and then click **OK**.</span></span>

     <span data-ttu-id="b47ad-173">Die Bruttorendite für die von Wiederverkäufern verkauften Fahrräder in Nordamerika wird für das dritte Quartal des Kalenderjahres 2007 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b47ad-173">The gross profit margin for the sale of Bikes by resellers in North America in Q3 CY 2007 appears.</span></span>

## <a name="next-lesson"></a><span data-ttu-id="b47ad-174">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="b47ad-174">Next Lesson</span></span>
 [<span data-ttu-id="b47ad-175">Lektion 8: Definieren von Aktionen</span><span class="sxs-lookup"><span data-stu-id="b47ad-175">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)


