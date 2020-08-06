---
title: Punktdiagramme (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2520ae24-0609-4890-807d-3267018aba8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 93f9b31089eb8399c7fdfd201d3c799608f2e91e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717467"
---
# <a name="scatter-charts-report-builder-and-ssrs"></a><span data-ttu-id="b91a3-102">Punktdiagramme (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b91a3-102">Scatter Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b91a3-103">Ein Punktdiagramm zeigt eine Reihe als Menge von Punkten an.</span><span class="sxs-lookup"><span data-stu-id="b91a3-103">A scatter chart displays a series as a set of points.</span></span> <span data-ttu-id="b91a3-104">Die Werte werden durch die Position der Punkte im Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b91a3-104">Values are represented by the position of the points on the chart.</span></span> <span data-ttu-id="b91a3-105">Kategorien werden durch verschiedene Marker im Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b91a3-105">Categories are represented by different markers on the chart.</span></span> <span data-ttu-id="b91a3-106">Punktdiagramme dienen im Allgemeinen zum Vergleich aggregierter Daten über Kategorien hinweg.</span><span class="sxs-lookup"><span data-stu-id="b91a3-106">Scatter charts are typically used to compare aggregated data across categories.</span></span> <span data-ttu-id="b91a3-107">Weitere Informationen zum Hinzufügen von Daten zu einem Punktdiagramm finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="b91a3-107">For more information on how to add data to a scatter chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="b91a3-108">Die folgende Abbildung zeigt ein Beispiel für ein Punktdiagramm.</span><span class="sxs-lookup"><span data-stu-id="b91a3-108">The following illustration shows an example of a scatter chart.</span></span>  
  
 <span data-ttu-id="b91a3-109">![Punktdiagramm](../media/rs-scatterchart.gif "Punktdiagramm")</span><span class="sxs-lookup"><span data-stu-id="b91a3-109">![Scatter chart](../media/rs-scatterchart.gif "Scatter chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="b91a3-110">Abweichungen</span><span class="sxs-lookup"><span data-stu-id="b91a3-110">Variations</span></span>  
  
-   <span data-ttu-id="b91a3-111">**Blase.**</span><span class="sxs-lookup"><span data-stu-id="b91a3-111">**Bubble.**</span></span> <span data-ttu-id="b91a3-112">Blasendiagramme zeigen den Unterschied zwischen zwei Werten eines Datenpunkts basierend auf der Größe der Blase an.</span><span class="sxs-lookup"><span data-stu-id="b91a3-112">Bubble charts display the difference between two values of a data point based on the size of the bubble.</span></span> <span data-ttu-id="b91a3-113">Je größer die Blase, desto größer der Unterschied zwischen den beiden Werten.</span><span class="sxs-lookup"><span data-stu-id="b91a3-113">The larger the bubble, the larger the difference between the two values.</span></span>  
  
-   <span data-ttu-id="b91a3-114">**3D-Blase**.</span><span class="sxs-lookup"><span data-stu-id="b91a3-114">**3-D Bubble**.</span></span> <span data-ttu-id="b91a3-115">Ein dreidimensionales Blasendiagramm.</span><span class="sxs-lookup"><span data-stu-id="b91a3-115">A bubble chart displayed in 3-D.</span></span>  
  
## <a name="data-considerations-for-a-scatter-chart"></a><span data-ttu-id="b91a3-116">Überlegungen zu Daten für ein Punktdiagramm</span><span class="sxs-lookup"><span data-stu-id="b91a3-116">Data Considerations for a Scatter Chart</span></span>  
  
-   <span data-ttu-id="b91a3-117">Punktdiagramme werden im Allgemeinen zum Anzeigen und Vergleichen numerischer Werte, wie wissenschaftliche, statistische und technische Daten, verwendet.</span><span class="sxs-lookup"><span data-stu-id="b91a3-117">Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical, and engineering data.</span></span>  
  
-   <span data-ttu-id="b91a3-118">Verwenden Sie das Punktdiagramm, wenn Sie große Mengen von Datenpunkten ohne Berücksichtigung des Zeitfaktors vergleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="b91a3-118">Use the scatter chart when you want to compare large numbers of data points without regard to time.</span></span> <span data-ttu-id="b91a3-119">Je mehr Daten Sie in ein Punktdiagramm integrieren, desto besser ist die Qualität der Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="b91a3-119">The more data that you include in a scatter chart, the better the comparisons that you can make.</span></span>  
  
-   <span data-ttu-id="b91a3-120">Das Blasendiagramm erfordert zwei Werte (oben und unten) pro Datenpunkt.</span><span class="sxs-lookup"><span data-stu-id="b91a3-120">The bubble chart requires two values (top and bottom) per data point.</span></span>  
  
-   <span data-ttu-id="b91a3-121">Punktdiagramme eignen sich ideal für die Verteilung von Werten und Clustern von Datenpunkten.</span><span class="sxs-lookup"><span data-stu-id="b91a3-121">Scatter charts are ideal for handling the distribution of values and clusters of data points.</span></span> <span data-ttu-id="b91a3-122">Dies ist der am besten geeignete Diagrammtyp, wenn das Dataset viele Punkte (z. B. mehrere tausend Punkte) enthält.</span><span class="sxs-lookup"><span data-stu-id="b91a3-122">This is the best chart type if your dataset contains many points (for example, several thousand points).</span></span> <span data-ttu-id="b91a3-123">Die Anzeige mehrerer Reihen in einem Punktdiagramm lenkt visuell ab und sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="b91a3-123">Displaying multiple series on a point chart is visually distracting and should be avoided.</span></span> <span data-ttu-id="b91a3-124">Erwägen Sie in einem solchen Fall, ein Liniendiagramm zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b91a3-124">In this scenario, consider using a line chart.</span></span>  
  
-   <span data-ttu-id="b91a3-125">Standardmäßig zeigen Punktdiagramme Datenpunkte als Kreise an.</span><span class="sxs-lookup"><span data-stu-id="b91a3-125">By default, scatter charts display data points as circles.</span></span> <span data-ttu-id="b91a3-126">Wenn mehrere Reihen in einem Punktdiagramm vorhanden sind, ändern Sie die Form des Markers für jeden Punkt gegebenenfalls in quadratisch, dreieckig, rautenförmig oder eine andere Form.</span><span class="sxs-lookup"><span data-stu-id="b91a3-126">If you have multiple series on a scatter chart, consider changing the marker shape of each point to be square, triangle, diamond, or another shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91a3-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b91a3-127">See Also</span></span>  
 <span data-ttu-id="b91a3-128">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b91a3-128">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b91a3-129">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b91a3-129">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b91a3-130">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b91a3-130">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b91a3-131">Liniendiagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b91a3-131">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)  
  
  
