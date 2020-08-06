---
title: Zusammenfassen von kleinen Slices in einem Kreisdiagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618500"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="1619b-102">Zusammenfassen von kleinen Slices in einem Kreisdiagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="1619b-102">Collect Small Slices on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1619b-103">Wenn Kreisdiagramme zu viele Datenpunkte enthalten, werden sie unübersichtlich.</span><span class="sxs-lookup"><span data-stu-id="1619b-103">When pie charts display too many points of data, they begin to look cluttered.</span></span> <span data-ttu-id="1619b-104">Zur Vermeidung dieses Problems können Sie alle Daten, die unter einen bestimmten Wert fallen, im Kreisdiagramm als einen gemeinsamen Slice anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1619b-104">To resolve this issue, you can show all data that falls beneath a certain value as one slice on the pie chart.</span></span>  
  
 <span data-ttu-id="1619b-105">Wenn Sie kleinere Slices zu einem einzelnen Slice zusammenfassen möchten, müssen Sie zuerst entscheiden, ob der Schwellenwert für das Zusammenfassen kleiner Slices als Prozentanteil des Kreisdiagramms oder als fester Wert gemessen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1619b-105">To collect small slices into one slice, first decide whether your threshold for collecting small slices is measured as a percentage of the pie chart or as a fixed value.</span></span> <span data-ttu-id="1619b-106">Legen Sie dann die Eigenschaften CollectedThreshold und CollectedThresholdUsePercent fest. Legen Sie die Eigenschaft CollectedThreshold entweder auf den Prozentanteil des Diagramms, unter den die Werte fallen müssen, damit sie zusammengefasst werden, oder auf den tatsächlichen Schwellendatenwert für die Zusammenfassung fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-106">Then set the CollectedThreshold and CollectedThresholdUsePercent properties.Set the CollectedThreshold property to either the percentage of the chart that a value must fall below to be collected, or the actual threshold data value for collection.</span></span> <span data-ttu-id="1619b-107">Legen Sie die Eigenschaft collectedationsolduse% auf fest, `True` um einen Prozentsatz oder einen `False` tatsächlichen Wert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1619b-107">Set the CollectedThresholdUsePercent property to `True` to use a percentage or `False` to use an actual value.</span></span>  
  
 <span data-ttu-id="1619b-108">Sie können kleinere Slices auch zu einem zweiten Kreisdiagramm zusammenfassen, das aus einem zusammengefassten Slice des ersten Kreisdiagramms gebildet wird.</span><span class="sxs-lookup"><span data-stu-id="1619b-108">You can also collect small slices into a second pie chart that is called out from a collected slice of the first pie chart.</span></span> <span data-ttu-id="1619b-109">Das zweite Kreisdiagramm wird rechts vom ursprünglichen Kreisdiagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1619b-109">The second pie chart is drawn to the right of the original pie chart.</span></span>  
  
 <span data-ttu-id="1619b-110">Slices von Trichter- oder Pyramidendiagrammen können nicht zu einem Slice zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="1619b-110">You cannot combine slices of funnel or pyramid charts into one slice.</span></span>  
  
 <span data-ttu-id="1619b-111">Ein Beispiel für dieses Diagramm ist als Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1619b-111">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="1619b-112">Weitere Informationen zum Herunterladen des Beispielberichts und anderer Berichte finden Sie unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Beispielberichte zu Berichts-Generator und Berichts-Designer](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="1619b-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a><span data-ttu-id="1619b-113">So fassen Sie kleinere Slices zu einem einzelnen Slice in einem Kreisdiagramm zusammen</span><span class="sxs-lookup"><span data-stu-id="1619b-113">To collect small slices into a single slice on a pie chart</span></span>  
  
1.  <span data-ttu-id="1619b-114">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1619b-114">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="1619b-115">Klicken Sie auf der Entwurfsoberfläche auf ein Segment des Kreisdiagramms.</span><span class="sxs-lookup"><span data-stu-id="1619b-115">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="1619b-116">Die Eigenschaften für die Reihe werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1619b-116">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="1619b-117">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="1619b-117">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="1619b-118">Legen Sie die Eigenschaft CollectedStyle auf **SingleSlice**fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-118">Set the CollectedStyle property to **SingleSlice**.</span></span>  
  
5.  <span data-ttu-id="1619b-119">Legen Sie den Schwellenwert für die Zusammenfassung und den Typ des Schwellenwerts fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-119">Set the collected threshold value and type of threshold.</span></span> <span data-ttu-id="1619b-120">Die folgenden Beispiele zeigen häufig verwendete Methoden zum Festlegen der Schwellenwerte für die Zusammenfassung.</span><span class="sxs-lookup"><span data-stu-id="1619b-120">The following examples are common ways of setting collected thresholds.</span></span>  
  
    -   <span data-ttu-id="1619b-121">**Nach Prozentanteil.**</span><span class="sxs-lookup"><span data-stu-id="1619b-121">**By percentage.**</span></span> <span data-ttu-id="1619b-122">So fassen Sie beispielsweise in einem Kreisdiagramm Slices zusammen, die weniger als 10 % darstellen:</span><span class="sxs-lookup"><span data-stu-id="1619b-122">For example, to collect any slice on your pie chart that is less than 10% into a single slice:</span></span>  
  
         <span data-ttu-id="1619b-123">Legen Sie die Eigenschaft collectedfür olduse% auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="1619b-123">Set the CollectedThresholdUsePercent property to `True`.</span></span>  
  
         <span data-ttu-id="1619b-124">Legen Sie die Eigenschaft CollectedThreshold auf **10**fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-124">Set the CollectedThreshold property to **10**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1619b-125">Wenn Sie CollectedStyle auf **SingleSlice**, CollectedThreshold auf einen Wert größer als **100**und collectedagraolduseprozent auf festlegen `True` , löst das Diagramm eine Ausnahme aus, da es keinen Prozentsatz berechnen kann.</span><span class="sxs-lookup"><span data-stu-id="1619b-125">If you set CollectedStyle to **SingleSlice**, CollectedThreshold to a value greater than **100**, and CollectedThresholdUsePercent is `True`, the chart will throw an exception because it cannot calculate a percentage.</span></span> <span data-ttu-id="1619b-126">Zur Behebung dieses Problems legen Sie CollectedThreshold auf einen Wert kleiner als **100** fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-126">To resolve this issue, set the CollectedThreshold to a value less than **100**.</span></span>  
  
    -   <span data-ttu-id="1619b-127">**Nach Datenwert.**</span><span class="sxs-lookup"><span data-stu-id="1619b-127">**By data value.**</span></span> <span data-ttu-id="1619b-128">So fassen Sie beispielsweise in einem Kreisdiagramm Slices zusammen, die weniger als 5000 darstellen:</span><span class="sxs-lookup"><span data-stu-id="1619b-128">For example, to collect any slice on your pie chart that is less than 5000 into a single slice:</span></span>  
  
         <span data-ttu-id="1619b-129">Legen Sie die Eigenschaft collectedfür olduse% auf fest `False` .</span><span class="sxs-lookup"><span data-stu-id="1619b-129">Set the CollectedThresholdUsePercent property to `False`.</span></span>  
  
         <span data-ttu-id="1619b-130">Legen Sie die Eigenschaft CollectedThreshold auf **5000**fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-130">Set the CollectedThreshold property to **5000**.</span></span>  
  
6.  <span data-ttu-id="1619b-131">Legen Sie die Eigenschaft CollectedLabel auf eine Zeichenfolge fest, die als Beschriftung für das zusammengefasste Segment angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1619b-131">Set the CollectedLabel property to a string that represents the text label that will be shown on the collected slice.</span></span>  
  
7.  <span data-ttu-id="1619b-132">(Optional) Legen Sie die Eigenschaften CollectedSliceExploded, CollectedColor, CollectedLegendText und CollectedToolTip fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-132">(Optional) Set the CollectedSliceExploded, CollectedColor, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="1619b-133">Diese Eigenschaften ändern die Darstellung, die Farbe, den Bezeichnungstext, den Legendentext und die QuickInfo des zusammengefassten Slice.</span><span class="sxs-lookup"><span data-stu-id="1619b-133">These properties change the appearance, color, label text, legend text and tooltip aspects of the single slice.</span></span>  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a><span data-ttu-id="1619b-134">So fassen Sie kleinere Slices zu einem sekundären Legendenkreisdiagramm zusammen</span><span class="sxs-lookup"><span data-stu-id="1619b-134">To collect small slices into a secondary, callout pie chart</span></span>  
  
1.  <span data-ttu-id="1619b-135">Führen Sie die Schritte 1-3 von oben aus.</span><span class="sxs-lookup"><span data-stu-id="1619b-135">Follow Steps 1-3 from above.</span></span>  
  
2.  <span data-ttu-id="1619b-136">Legen Sie die Eigenschaft CollectedStyle auf **CollectedPie**fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-136">Set the CollectedStyle property to **CollectedPie**.</span></span>  
  
3.  <span data-ttu-id="1619b-137">Legen Sie die Eigenschaft CollectedThresholdproperty auf den Wert fest, der als Schwellenwert für die Zusammenfassung kleinerer Segmente zu einem einzelnen Segment verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1619b-137">Set the CollectedThresholdproperty to a value that represents the threshold at which small slices will be collected into one slice.</span></span> <span data-ttu-id="1619b-138">Wenn die Eigenschaft CollectedStyle auf **CollectedPie**festgelegt ist, wird die Eigenschaft CollectedThreshold olduse%immer auf festgelegt `True` , und der erfasste Schwellenwert wird immer in Prozent gemessen.</span><span class="sxs-lookup"><span data-stu-id="1619b-138">When the CollectedStyle property is set to **CollectedPie**, the CollectedThresholdUsePercentproperty is always set to `True`, and the collected threshold is always measured in percent.</span></span>  
  
4.  <span data-ttu-id="1619b-139">(Optional) Legen Sie die Eigenschaften CollectedColor, CollectedLabel, CollectedLegendText und CollectedToolTip fest.</span><span class="sxs-lookup"><span data-stu-id="1619b-139">(Optional) Set the CollectedColor, CollectedLabel, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="1619b-140">Alle anderen Eigenschaften mit der Bezeichnung "Collected" gelten nicht für den zusammengefassten Slice in einem Kreisdiagramm.</span><span class="sxs-lookup"><span data-stu-id="1619b-140">All other properties named "Collected" do not apply to the collected pie.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1619b-141">Das sekundäre Kreisdiagramm wird auf der Grundlage der kleinen Slices in Ihren Daten berechnet, sodass es nur in der Vorschau angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1619b-141">The secondary pie chart is calculated based on the small slices in your data so it will only appear in Preview.</span></span> <span data-ttu-id="1619b-142">Es wird nicht auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1619b-142">It does not appear on the design surface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1619b-143">Sie können das sekundäre Kreisdiagramm nicht formatieren.</span><span class="sxs-lookup"><span data-stu-id="1619b-143">You cannot format the secondary pie chart.</span></span> <span data-ttu-id="1619b-144">Aus diesem Grund wird dringend empfohlen, beim Zusammenfassen von Slices in einem Kreisdiagramm die erste Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1619b-144">For this reason, it is strongly recommended to use the first approach when collecting pie slices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1619b-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1619b-145">See Also</span></span>  
 <span data-ttu-id="1619b-146">[Kreis Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1619b-146">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1619b-147">[Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1619b-147">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1619b-148">[Anzeigen von Datenpunkt Bezeichnungen außerhalb eines Kreis Diagramms &#40;Berichts-Generator und SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1619b-148">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1619b-149">[Anzeigen von Prozentwerten in einem Kreis Diagramm &#40;Berichts-Generator und SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1619b-149">[Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1619b-150">Hinzufügen von 3D-Effekten zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="1619b-150">Add 3D Effects to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-3d-effects-report-builder.md)  
  
  
