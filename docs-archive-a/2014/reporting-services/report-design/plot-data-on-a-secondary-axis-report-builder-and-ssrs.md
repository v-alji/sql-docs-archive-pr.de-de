---
title: Zeichnen von Daten auf einer sekundären Achse (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 094f39bf-3634-4852-9fc3-3adec4b266e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cec58820e0373bb1e9ef2d50d022e5b4ef7e962b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695293"
---
# <a name="plot-data-on-a-secondary-axis-report-builder-and-ssrs"></a><span data-ttu-id="6ab47-102">Zeichnen von Daten auf einer sekundären Achse (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6ab47-102">Plot Data on a Secondary Axis (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6ab47-103">Das Diagramm verfügt über zwei Achsentypen: primär und sekundär.</span><span class="sxs-lookup"><span data-stu-id="6ab47-103">The chart has two axis types: primary and secondary.</span></span> <span data-ttu-id="6ab47-104">Die sekundäre Achse ist nützlich beim Vergleichen von zwei Wertsätzen mit zwei unterschiedlichen Datenbereichen, die eine gemeinsame Kategorie verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ab47-104">The secondary axis is useful when comparing two value sets with two distinct data ranges that share a common category.</span></span>  
  
 <span data-ttu-id="6ab47-105">Angenommen, Sie haben ein Diagramm, das Einnahmen und Steuern für das Jahr 2008 berechnet.</span><span class="sxs-lookup"><span data-stu-id="6ab47-105">For example, suppose you have a chart that calculates Revenue vs. Tax for the year 2008.</span></span> <span data-ttu-id="6ab47-106">In diesem Fall verwenden beide Wertsätze den Zeitraum 2008 gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="6ab47-106">In this case, the 2008 time period is common to both value sets.</span></span> <span data-ttu-id="6ab47-107">Wenn beide Reihen jedoch auf derselben Y-Achse gezeichnet werden, kann kein sinnvoller Vergleich durchgeführt werden, da die Skala der Y-Achse für die größten Werte im Dataset optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="6ab47-107">However, when both series are plotted on the same y-axis, we cannot make a useful comparison because the scale of the y-axis is optimized for the largest values in the dataset.</span></span> <span data-ttu-id="6ab47-108">Wenn die Einnahmen auf der primären Achse und die Steuern auf der sekundären Achse angezeigt werden, kann jede Reihe auf einer eigenen Y-Achse mit einer eigenen Werteskala dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6ab47-108">If we show Revenue on the primary axis, and Tax on the secondary axis, we can display each series on its own y-axis with its own scale of values.</span></span> <span data-ttu-id="6ab47-109">Die Reihen verwenden nach wie vor eine gemeinsame X-Achse.</span><span class="sxs-lookup"><span data-stu-id="6ab47-109">The series still share a common x-axis.</span></span>  
  
 <span data-ttu-id="6ab47-110">In Fällen, in denen mehr als zwei Reihen verglichen werden, sollten Sie einen anderen Ansatz für den Vergleich und die Anzeige mehrerer Reihen in einem Diagramm in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="6ab47-110">In situations where there are more than two series to be compared, consider a different approach for comparing and displaying multiple series in a chart.</span></span> <span data-ttu-id="6ab47-111">Weitere Informationen hierzu finden Sie unter [Mehrere Reihen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md):</span><span class="sxs-lookup"><span data-stu-id="6ab47-111">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="6ab47-112">Ein Beispiel für dieses Diagramm ist als Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6ab47-112">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="6ab47-113">Weitere Informationen zum Herunterladen des Beispielberichts und anderer Berichte finden Sie unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Beispielberichte zu Berichts-Generator und Berichts-Designer](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="6ab47-113">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-plot-a-series-on-the-secondary-axis"></a><span data-ttu-id="6ab47-114">So zeichnen Sie eine Reihe auf der sekundären Achse</span><span class="sxs-lookup"><span data-stu-id="6ab47-114">To plot a series on the secondary axis</span></span>  
  
1.  <span data-ttu-id="6ab47-115">Klicken Sie mit der rechten Maustaste auf die Reihe im Diagramm oder auf ein Feld im Bereich **Werte** , das Sie auf der sekundären Achse anzeigen möchten. Klicken Sie anschließend auf **Reiheneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6ab47-115">Right-click the series in the chart or right-click on a field in the **Values** area that you want to display on the secondary axis and click **Series Properties**.</span></span> <span data-ttu-id="6ab47-116">Das Dialogfeld **Reiheneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ab47-116">The **Series Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="6ab47-117">Klicken Sie auf **Achsen und Diagrammfläche**, und wählen Sie die sekundäre Achse aus, die Sie aktivieren möchten, d. h. die Wertachse oder die Kategorieachse.</span><span class="sxs-lookup"><span data-stu-id="6ab47-117">Click **Axes and Chart Area**, and select which of the secondary axes you want to enable, the value axis or the category axis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab47-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ab47-118">See Also</span></span>  
 <span data-ttu-id="6ab47-119">[Formatieren von Achsen Bezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6ab47-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6ab47-120">Angeben eines Achsenintervalls (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="6ab47-120">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
