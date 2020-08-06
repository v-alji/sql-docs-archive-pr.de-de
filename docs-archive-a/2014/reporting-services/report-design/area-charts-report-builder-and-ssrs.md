---
title: Flächendiagramme (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 245b236d-1d55-4744-b752-80bd133502aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f401efa0abd5eac8ab39e511bc6b16a4f381ebdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717500"
---
# <a name="area-charts-report-builder-and-ssrs"></a><span data-ttu-id="313ed-102">Flächendiagramme (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="313ed-102">Area Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="313ed-103">Ein Flächendiagramm zeigt eine Reihe als verschiedene Punkte an, die durch eine Linie miteinander verbunden sind, wobei die Fläche unterhalb der Linie ausgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="313ed-103">An area chart displays a series as a set of points connected by a line, with all the area filled in below the line.</span></span> <span data-ttu-id="313ed-104">Weitere Informationen zu Hinzufügen von Daten zu einem Flächendiagramm finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="313ed-104">For more information on how to add data to an area chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="313ed-105">Die folgende Abbildung zeigt ein Beispiel für ein gestapeltes Flächendiagramm.</span><span class="sxs-lookup"><span data-stu-id="313ed-105">The following illustration shows an example of a stacked area chart.</span></span> <span data-ttu-id="313ed-106">Die Daten sind für die Anzeige in einem gestapelten Flächendiagramm geeignet, da das Diagramm Summen für alle Reihen sowie den Anteil der einzelnen Reihen an der Gesamtsumme anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="313ed-106">The data is well suited for display on a stacked area chart because the chart can display totals for all series as well as the proportion that each series contributes to the total.</span></span>  
  
 <span data-ttu-id="313ed-107">![Flächendiagramm](../media/areachart.gif "Flächendiagramm")</span><span class="sxs-lookup"><span data-stu-id="313ed-107">![Area chart](../media/areachart.gif "Area chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="313ed-108">Abweichungen</span><span class="sxs-lookup"><span data-stu-id="313ed-108">Variations</span></span>  
  
-   <span data-ttu-id="313ed-109">**Gestapelte Fläche**.</span><span class="sxs-lookup"><span data-stu-id="313ed-109">**Stacked area**.</span></span> <span data-ttu-id="313ed-110">Ein Flächendiagramm, in dem mehrere Reihen vertikal gestapelt werden.</span><span class="sxs-lookup"><span data-stu-id="313ed-110">An area chart where multiple series are stacked vertically.</span></span> <span data-ttu-id="313ed-111">Wenn nur eine Reihe im Diagramm vorhanden ist, wird das gestapelte Flächendiagramm angezeigt wie ein Flächendiagramm.</span><span class="sxs-lookup"><span data-stu-id="313ed-111">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="313ed-112">**Prozentual gestapelte Fläche**.</span><span class="sxs-lookup"><span data-stu-id="313ed-112">**Percent stacked area**.</span></span> <span data-ttu-id="313ed-113">Ein Flächendiagramm, in dem mehrere Reihen vertikal gestapelt sind, um auf die gesamte Diagrammfläche zu passen.</span><span class="sxs-lookup"><span data-stu-id="313ed-113">An area chart where multiple series are stacked vertically to fit the entire chart area.</span></span> <span data-ttu-id="313ed-114">Wenn nur eine Reihe im Diagramm vorhanden ist, wird das gestapelte Flächendiagramm angezeigt wie ein Flächendiagramm.</span><span class="sxs-lookup"><span data-stu-id="313ed-114">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="313ed-115">**Glatter Bereich**.</span><span class="sxs-lookup"><span data-stu-id="313ed-115">**Smooth area**.</span></span> <span data-ttu-id="313ed-116">Ein Flächendiagramm, in dem Datenpunkte durch eine geglättete Linie statt einer regulären Linie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="313ed-116">An area chart where the data points are connected by a smooth line instead of a regular line.</span></span> <span data-ttu-id="313ed-117">Verwenden Sie ein geglättetes Flächendiagramm statt eines Flächendiagramms, wenn Ihnen an der Anzeige von Trends mehr liegt als an der Anzeige von Werten einzelner Datenpunkte.</span><span class="sxs-lookup"><span data-stu-id="313ed-117">Use a smooth area chart instead of an area chart when you are more concerned with displaying trends than with displaying the values of individual data points.</span></span>  
  
## <a name="data-considerations-for-area-charts"></a><span data-ttu-id="313ed-118">Überlegungen zu Daten für ein Flächendiagramm</span><span class="sxs-lookup"><span data-stu-id="313ed-118">Data Considerations for Area Charts</span></span>  
  
-   <span data-ttu-id="313ed-119">Neben dem Liniendiagramm ist das Flächendiagramm der einzige Diagrammtyp, der Daten zusammenhängend anzeigt.</span><span class="sxs-lookup"><span data-stu-id="313ed-119">Along with the line chart, the area chart is the only chart type that displays data contiguously.</span></span> <span data-ttu-id="313ed-120">Aus diesem Grund wird ein Flächendiagramm häufig zur Darstellung von Daten verwendet, die über einen kontinuierlichen Zeitraum hinweg auftreten.</span><span class="sxs-lookup"><span data-stu-id="313ed-120">For this reason, an area chart is commonly used to represent data that occurs over a continuous period of time.</span></span>  
  
-   <span data-ttu-id="313ed-121">Ein prozentual gestapeltes Flächendiagramm ist nützlich, um proportionale Daten anzuzeigen, die im Laufe der Zeit auftreten.</span><span class="sxs-lookup"><span data-stu-id="313ed-121">A percent stacked area chart is useful for showing proportional data that occurs over time.</span></span>  
  
-   <span data-ttu-id="313ed-122">Wenn nur eine Reihe im Diagramm vorhanden ist, wird das gestapelte Flächendiagramm wie ein Flächendiagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="313ed-122">If there is only one series, a stacked area chart will be drawn as an area chart.</span></span>  
  
-   <span data-ttu-id="313ed-123">Wenn die Werte in mehreren Reihen ähnlich sind, überlappen die Flächen in einem einfachen Flächendiagramm. Dadurch werden wichtige Datenpunktwerte verdeckt.</span><span class="sxs-lookup"><span data-stu-id="313ed-123">In a plain area chart, if the values in multiple series are similar, the areas may overlap, obscuring important data point values.</span></span> <span data-ttu-id="313ed-124">Sie können dieses Problem beheben, indem Sie den Diagrammtyp zu einem gestapelten Flächendiagramm ändern, das für die Anzeige mehrerer Reihen in einem Flächendiagramm entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="313ed-124">You can resolve this issue by changing the chart type to a stacked area chart, which is designed to show multiple series on an area chart.</span></span>  
  
-   <span data-ttu-id="313ed-125">Wenn Ihr gestapeltes Flächendiagramm Lücken enthält, schließt Ihr Dataset möglicherweise leere Werte ein, die als Leerbereich in einem gestapelten Flächendiagramm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="313ed-125">If your stacked area chart contains gaps, it is possible that your dataset includes empty values, which will be shown as a vacant section on a stacked area chart.</span></span> <span data-ttu-id="313ed-126">Wenn das Dataset leere Werte enthält, erwägen Sie, leere Punkte auf dem Diagramm einzufügen.</span><span class="sxs-lookup"><span data-stu-id="313ed-126">If your dataset includes empty values, consider inserting empty points on the chart.</span></span> <span data-ttu-id="313ed-127">Durch Hinzufügen von leeren Punkten werden die leeren Bereiche des Diagramms mit einer anderen Farbe ausgefüllt, um Nullwerte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="313ed-127">Adding empty points will fill in the empty areas on the chart with a different color to indicate null or zero values.</span></span> <span data-ttu-id="313ed-128">Weitere Informationen finden Sie unter [Hinzufügen von leeren Punkten zum Diagramm &#40;Berichts-Generator und SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="313ed-128">For more information, see [Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="313ed-129">Flächendiagrammtypen verhalten sich ähnlich wie Säulen- und Liniendiagramme.</span><span class="sxs-lookup"><span data-stu-id="313ed-129">Area chart types are very similar to column and line charts in behavior.</span></span> <span data-ttu-id="313ed-130">Wenn Sie einen Vergleich zwischen mehreren Reihen durchführen, erwägen Sie, stattdessen ein Säulendiagramm zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="313ed-130">If you are making a comparison between multiple series, consider using a column chart instead.</span></span> <span data-ttu-id="313ed-131">Für die Analyse von Trends über einen bestimmten Zeitraum ist ein Liniendiagramm unter Umständen besser geeignet.</span><span class="sxs-lookup"><span data-stu-id="313ed-131">If you are analyzing trends over a period of time, consider using a line chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313ed-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="313ed-132">See Also</span></span>  
 <span data-ttu-id="313ed-133">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="313ed-133">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="313ed-134">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="313ed-134">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="313ed-135">[Liniendiagramme (Berichts-Generator und SSRS)](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="313ed-135">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="313ed-136">[Ändern eines Diagrammtyps (Berichts-Generator und SSRS)](change-a-chart-type-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="313ed-136">[Change a Chart Type &#40;Report Builder and SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="313ed-137">Leere und NULL-Datenpunkte in Diagrammen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="313ed-137">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
