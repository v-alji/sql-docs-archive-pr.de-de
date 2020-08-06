---
title: Angeben einer Diagrammfläche für eine Reihe (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10157"
- sql12.rtp.rptdesigner.chartareaproperties.alignment.f1
ms.assetid: dc3c365b-c263-402a-bf6f-c2a7081db073
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483bc6d2fa4aa079c95e9dbd03e18c71d7b13abf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608273"
---
# <a name="specify-a-chart-area-for-a-series-report-builder-and-ssrs"></a><span data-ttu-id="e2c3e-102">Angeben einer Diagrammfläche für eine Reihe (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e2c3e-102">Specify a Chart Area for a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e2c3e-103">Das Diagramm stellt den Container der obersten Ebene dar, der den äußeren Rahmen, den Diagrammtitel und die Legende enthält.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-103">The chart is the top-level container that includes the outer border, the chart title, and the legend.</span></span> <span data-ttu-id="e2c3e-104">Standardmäßig wird im Diagramm eine Diagrammfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-104">By default, the chart contains one default chart area.</span></span> <span data-ttu-id="e2c3e-105">Die Diagrammfläche ist auf der Diagrammoberfläche nicht sichtbar. Sie können sich diese jedoch als Container vorstellen, der lediglich die Achsenbezeichnungen, den Achsentitel und den Zeichnungsbereich einer oder mehrerer Reihen umfasst.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-105">The chart area is not visible on the chart surface, but you can think of the chart area as a container that encompasses only the axis labels, the axis title and the plotting area of one or more series.</span></span> <span data-ttu-id="e2c3e-106">In der folgenden Abbildung wird das Konzept der Diagrammflächen in einem einzelnen Diagramm veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-106">The following illustration shows the concept of chart areas within a single chart.</span></span>  
  
 <span data-ttu-id="e2c3e-107">![Diagramm eines Diagrammbereichs](../media/chartareasdiagram.gif "Diagramm eines Diagrammbereichs")</span><span class="sxs-lookup"><span data-stu-id="e2c3e-107">![Shows a diagram of a chart area](../media/chartareasdiagram.gif "Shows a diagram of a chart area")</span></span>  
  
 <span data-ttu-id="e2c3e-108">Standardmäßig werden alle Reihen der Standarddiagrammfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-108">By default, all series are added to the default chart area.</span></span> <span data-ttu-id="e2c3e-109">In Flächen-, Säulen-, Linien- und Punktdiagrammen kann in einer Diagrammfläche eine beliebige Kombination dieser Reihen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-109">When using area, column, line, and scatter charts, any combination of these series can be displayed on the same chart area.</span></span> <span data-ttu-id="e2c3e-110">Bei mehreren Reihen in einer einzelnen Diagrammfläche verschlechtert sich die Lesbarkeit des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-110">If you have several series in the same chart area, the readability of the chart is reduced.</span></span> <span data-ttu-id="e2c3e-111">Sie können die Diagrammtypen in mehrere Diagrammflächen aufteilen.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-111">You may want to separate the chart types into multiple chart areas.</span></span> <span data-ttu-id="e2c3e-112">Bei mehreren Diagrammflächen verbessert sich Lesbarkeit, sodass Vergleiche erleichtert werden.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-112">Using multiple chart areas will increase readability for easier comparisons.</span></span> <span data-ttu-id="e2c3e-113">Zum Beispiel weisen Preis-Volumen-Kursdiagramme häufig unterschiedliche Wertebereiche auf, dennoch können Vergleiche zwischen Preis- und Volumendaten in demselben Zeitraum vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-113">For example, price-volume stock charts often have different ranges of values, but comparisons can be made between the price and volume data over the same period of time.</span></span>  
  
 <span data-ttu-id="e2c3e-114">Die Balken-, Polar- oder Formreihen können nur mit Reihen derselben Diagrammtypen in derselben Diagrammfläche kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-114">The bar, polar, or shape series can only be combined with series of the same chart types in the same chart area.</span></span> <span data-ttu-id="e2c3e-115">Wenn Sie ein Polar- oder Formdiagramm verwenden, erwägen Sie, für jedes anzuzeigende Feld einen eigenen Diagrammdatenbereich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-115">If you are using a Polar or Shape chart, consider using a separate chart data region for each field that you wish to show.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-series-with-a-new-chart-area"></a><span data-ttu-id="e2c3e-116">So ordnen Sie eine Reihe einer neuen Diagrammfläche zu</span><span class="sxs-lookup"><span data-stu-id="e2c3e-116">To associate a series with a new chart area</span></span>  
  
1.  <span data-ttu-id="e2c3e-117">Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Diagramm, und wählen Sie **Neue Diagrammfläche hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-117">Right-click anywhere on the chart and select **Add New Chart Area**.</span></span> <span data-ttu-id="e2c3e-118">Im Diagramm wird eine neue, leere Diagrammfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-118">A new, blank chart area appears on the chart.</span></span>  
  
2.  <span data-ttu-id="e2c3e-119">Klicken Sie mit der rechten Maustaste auf die Reihe im Diagramm oder auf eine Reihe oder ein Datenfeld in der entsprechenden Fläche im Bereich „Diagrammdaten“, und klicken Sie dann auf **Reiheneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-119">Right-click the series on the chart or right-click a series or data field in the appropriate area in the Chart Data pane, and then click **Series Properties**.</span></span>  
  
3.  <span data-ttu-id="e2c3e-120">Wählen Sie unter **Achsen und Diagrammfläche**die Diagrammfläche aus, in der die Reihe angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-120">In **Axes and Chart Areas**, select the chart area that you want the series to be shown in.</span></span>  
  
4.  <span data-ttu-id="e2c3e-121">(Optional) Richten Sie die Diagrammflächen vertikal aus.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-121">(Optional) Align the chart areas vertically.</span></span> <span data-ttu-id="e2c3e-122">Klicken Sie dazu mit der rechten Maustaste auf das Diagramm, und wählen Sie **Diagrammflächeneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-122">To do this, right-click the chart and select **Chart Area Properties**.</span></span> <span data-ttu-id="e2c3e-123">Wählen Sie unter **Ausrichtung**eine andere Diagrammfläche aus, an der Sie die ausgewählte Diagrammfläche ausrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="e2c3e-123">In **Alignment**, select another chart area that you want to align the selected chart area with.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c3e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2c3e-124">See Also</span></span>  
 <span data-ttu-id="e2c3e-125">[Mehrere Reihen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2c3e-125">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e2c3e-126">[Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2c3e-126">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e2c3e-127">[Definieren von Farben in einem Diagramm mit einer Palette (Berichts-Generator und SSRS)](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2c3e-127">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e2c3e-128">[Netzdiagramme (Berichts-Generator und SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2c3e-128">[Polar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e2c3e-129">[Formdiagramme (Berichts-Generator und SSRS)](shape-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2c3e-129">[Shape Charts &#40;Report Builder and SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e2c3e-130">Kreisdiagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e2c3e-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)  
  
  
