---
title: Positionieren von Bezeichnungen in einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5db74e0b-8be8-4b47-b386-faab56dffa9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e90cbf04e0282454658e6324f0ba6600a99cb718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695289"
---
# <a name="position-labels-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="bceed-102">Positionieren von Bezeichnungen in einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="bceed-102">Position Labels in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bceed-103">Da jeder Diagrammtyp über eine andere Form verfügt, werden Datenpunktbezeichnungen so platziert, dass sie sich im Diagramm nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="bceed-103">Because each chart type has a different shape, data point labels are placed in an optimal location so as not to interfere on the chart.</span></span> <span data-ttu-id="bceed-104">Die Standardposition der Bezeichnungen ist vom Diagrammtyp abhängig:</span><span class="sxs-lookup"><span data-stu-id="bceed-104">The default position of the labels depends varies with the chart type:</span></span>  
  
-   <span data-ttu-id="bceed-105">Bei gestapelten Diagrammen können Bezeichnungen nur innerhalb der Reihe positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="bceed-105">On stacked charts, labels can only be positioned inside the series.</span></span>  
  
-   <span data-ttu-id="bceed-106">Bei Trichter- und Pyramidendiagrammen werden Bezeichnungen an der Außenseite in einer Spalte eingefügt.</span><span class="sxs-lookup"><span data-stu-id="bceed-106">On funnel or pyramid charts, labels are placed on the outside in a column.</span></span>  
  
-   <span data-ttu-id="bceed-107">Bei Kreisdiagrammen werden Bezeichnungen innerhalb der einzelnen Kreissegmente platziert.</span><span class="sxs-lookup"><span data-stu-id="bceed-107">On pie charts, labels are placed inside the individual slices on a pie chart.</span></span>  
  
-   <span data-ttu-id="bceed-108">Bei Balkendiagrammen werden Bezeichnungen außerhalb der Balken platziert, die Datenpunkte darstellen.</span><span class="sxs-lookup"><span data-stu-id="bceed-108">On bar charts, labels are placed outside of the bars that represent data points.</span></span>  
  
-   <span data-ttu-id="bceed-109">Bei Polardiagrammen werden Bezeichnungen außerhalb der Kreisbereiche platziert, die Datenpunkte darstellen.</span><span class="sxs-lookup"><span data-stu-id="bceed-109">On polar charts, labels are placed outside of the circular area that represents data points.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-position-of-point-labels-in-a-pie-chart"></a><span data-ttu-id="bceed-110">So ändern Sie die Position von Punktbezeichnungen in einem Kreisdiagramm</span><span class="sxs-lookup"><span data-stu-id="bceed-110">To change the position of point labels in a Pie chart</span></span>  
  
1.  <span data-ttu-id="bceed-111">Erstellen Sie ein Kreisdiagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-111">Create a pie chart.</span></span>  
  
2.  <span data-ttu-id="bceed-112">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Diagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-112">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="bceed-113">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bceed-113">Open the Properties pane.</span></span> <span data-ttu-id="bceed-114">Klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bceed-114">On the **View** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="bceed-115">Klicken Sie auf der Entwurfsoberfläche auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-115">On the design surface, click the chart.</span></span> <span data-ttu-id="bceed-116">Die Eigenschaften für das Diagramm werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-116">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="bceed-117">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="bceed-117">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="bceed-118">Eine Liste der Attribute für das Kreisdiagramm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-118">A list of attributes for the pie chart is displayed.</span></span>  
  
6.  <span data-ttu-id="bceed-119">Wählen Sie einen Wert für die Eigenschaft PieLabelStyle aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-119">Select a value for the PieLabelStyle property.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-funnel-or-pyramid-chart"></a><span data-ttu-id="bceed-120">So ändern Sie die Position von Punktbezeichnungen in einem Trichter- oder Pyramidendiagramm</span><span class="sxs-lookup"><span data-stu-id="bceed-120">To change the position of point labels in a Funnel or Pyramid chart</span></span>  
  
1.  <span data-ttu-id="bceed-121">Erstellen Sie ein Trichter- oder ein Pyramidendiagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-121">Create a funnel or pyramid chart.</span></span>  
  
2.  <span data-ttu-id="bceed-122">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Diagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-122">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="bceed-123">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bceed-123">Open the Properties pane.</span></span> <span data-ttu-id="bceed-124">Klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bceed-124">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="bceed-125">Klicken Sie auf der Entwurfsoberfläche auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-125">On the design surface, click the chart.</span></span> <span data-ttu-id="bceed-126">Die Eigenschaften für das Diagramm werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-126">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="bceed-127">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="bceed-127">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="bceed-128">Eine Liste der Attribute für das Trichterdiagramm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-128">A list of attributes for the funnel chart is displayed.</span></span>  
  
6.  <span data-ttu-id="bceed-129">Wählen Sie bei Trichterdiagrammen einen Wert für die Eigenschaft FunnelLabelStyle aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-129">For a funnel chart, select a value for the FunnelLabelStyle property.</span></span> <span data-ttu-id="bceed-130">Wählen Sie bei Pyramidendiagrammen einen Wert für die Eigenschaft PyramidLabelStyle aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-130">For a pyramid chart, select a value for the PyramidLabelStyle property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bceed-131">Wird diese Eigenschaft auf den Wert `OutsideInColumn` festgelegt, werden die Bezeichnungen in einer vertikalen Spalte gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bceed-131">When this property is set to a value `OutsideInColumn`, the labels are drawn in a vertical column.</span></span> <span data-ttu-id="bceed-132">Die Position der Spalte kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bceed-132">There is no way to change the position of the column.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-bar-chart"></a><span data-ttu-id="bceed-133">So ändern Sie die Position von Punktbezeichnungen in einem Balkendiagramm</span><span class="sxs-lookup"><span data-stu-id="bceed-133">To change the position of point labels in a Bar chart</span></span>  
  
1.  <span data-ttu-id="bceed-134">Erstellen Sie ein Balkendiagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-134">Create a bar chart.</span></span>  
  
2.  <span data-ttu-id="bceed-135">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Diagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-135">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="bceed-136">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bceed-136">Open the Properties pane.</span></span> <span data-ttu-id="bceed-137">Klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bceed-137">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="bceed-138">Klicken Sie auf der Entwurfsoberfläche auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-138">On the design surface, click the chart.</span></span> <span data-ttu-id="bceed-139">Die Eigenschaften für das Diagramm werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-139">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="bceed-140">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="bceed-140">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="bceed-141">Eine Liste mit Attributen für das Balkendiagramm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-141">A list of attributes for the bar chart is displayed.</span></span>  
  
6.  <span data-ttu-id="bceed-142">Wählen Sie einen Wert für die Eigenschaft BarLabelStyle aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-142">Select a value for the BarLabelStyle property.</span></span>  
  
 <span data-ttu-id="bceed-143">Wenn Sie für die Balkenbezeichnungsart den Wert `Outside` festlegen, werden die Bezeichnungen außerhalb des Balkens platziert, sofern sie in den Diagrammbereich passen.</span><span class="sxs-lookup"><span data-stu-id="bceed-143">When the bar label style is set to `Outside`, the labels will be placed outside of the bar, as long as it fits in the chart area.</span></span> <span data-ttu-id="bceed-144">Falls die Bezeichnung nicht außerhalb des Balkens positioniert werden kann, sondern im Diagrammbereich platziert werden muss, wird sie im Balken an der dem Ende des Balkens am nächsten gelegenen Stelle eingefügt.</span><span class="sxs-lookup"><span data-stu-id="bceed-144">If the label cannot be placed outside of the bar but inside of the chart area, the label is placed inside the bar at the position closest to the end of the bar.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-an-area-column-line-or-scatter-chart"></a><span data-ttu-id="bceed-145">So ändern Sie die Position von Punktbezeichnungen in einem Flächen-, Säulen-, Linien- oder Punktdiagramm</span><span class="sxs-lookup"><span data-stu-id="bceed-145">To change the position of point labels in an Area, Column, Line or Scatter chart</span></span>  
  
1.  <span data-ttu-id="bceed-146">Erstellen Sie ein Flächen-, Säulen-, Linien- oder Punktdiagramm.</span><span class="sxs-lookup"><span data-stu-id="bceed-146">Create an Area, Column, Line or Scatter chart.</span></span>  
  
2.  <span data-ttu-id="bceed-147">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Diagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-147">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="bceed-148">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bceed-148">Open the Properties pane.</span></span> <span data-ttu-id="bceed-149">Klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bceed-149">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="bceed-150">Klicken Sie auf der Entwurfsoberfläche auf die Reihe.</span><span class="sxs-lookup"><span data-stu-id="bceed-150">On the design surface, click the series.</span></span> <span data-ttu-id="bceed-151">Die Eigenschaften für die Reihe werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bceed-151">The properties for the series are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="bceed-152">Erweitern Sie im Abschnitt **Daten** den Knoten **DataPoint** und dann den Knoten **Label**.</span><span class="sxs-lookup"><span data-stu-id="bceed-152">In the **Data** section, expand the **DataPoint** node, then expand the **Label**node.</span></span>  
  
6.  <span data-ttu-id="bceed-153">Wählen Sie einen Wert für die Eigenschaft „Position“ aus.</span><span class="sxs-lookup"><span data-stu-id="bceed-153">Select a value for the Position property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bceed-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bceed-154">See Also</span></span>  
 <span data-ttu-id="bceed-155">[Kreisdiagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bceed-155">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bceed-156">[Balkendiagramme &#40;Berichts-Generator und SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bceed-156">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bceed-157">[Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bceed-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bceed-158">[Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung (Berichts-Generator und SSRS)](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bceed-158">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bceed-159">[Anzeigen von Datenpunktbezeichnungen außerhalb eines Kreisdiagramms &#40;Berichts-Generator und SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bceed-159">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bceed-160">Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bceed-160">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
  
  
