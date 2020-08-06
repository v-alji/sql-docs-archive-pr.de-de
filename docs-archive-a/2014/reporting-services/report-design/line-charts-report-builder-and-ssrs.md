---
title: Liniendiagramme (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 44e7a011186e66e6b8bdc8b5dd31939c883e320b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723409"
---
# <a name="line-charts-report-builder-and-ssrs"></a><span data-ttu-id="0ac59-102">Liniendiagramme (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0ac59-102">Line Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0ac59-103">Ein Liniendiagramm zeigt Reihen als einen Satz von Punkten an, die durch eine einzelne Linie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="0ac59-103">A line chart displays a series as a set of points connected by a single line.</span></span> <span data-ttu-id="0ac59-104">Liniendiagramme werden verwendet, um große Datenmengen darzustellen, die über einen kontinuierlichen Zeitraum hinweg auftreten.</span><span class="sxs-lookup"><span data-stu-id="0ac59-104">Line charts are used to representing large amounts of data that occur over a continuous period of time.</span></span> <span data-ttu-id="0ac59-105">Weitere Informationen zu Hinzufügen von Daten zu einem Liniendiagramm finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0ac59-105">For more information about how to add data to a line chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="0ac59-106">Die folgende Illustration zeigt ein Liniendiagramm mit drei Reihen an.</span><span class="sxs-lookup"><span data-stu-id="0ac59-106">The following illustration shows a line chart that contains three series.</span></span>  
  
 <span data-ttu-id="0ac59-107">![Liniendiagramm](../media/rs-linechart.gif "Liniendiagramm")</span><span class="sxs-lookup"><span data-stu-id="0ac59-107">![Line chart](../media/rs-linechart.gif "Line chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="0ac59-108">Abweichungen</span><span class="sxs-lookup"><span data-stu-id="0ac59-108">Variations</span></span>  
  
-   <span data-ttu-id="0ac59-109">**Geglättete Linie**.</span><span class="sxs-lookup"><span data-stu-id="0ac59-109">**Smooth line**.</span></span> <span data-ttu-id="0ac59-110">Ein Liniendiagramm, in dem eine gekrümmte statt einer regulären Linie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ac59-110">A line chart that uses a curved line instead of a regular line.</span></span>  
  
-   <span data-ttu-id="0ac59-111">**Linie, abgestuft**.</span><span class="sxs-lookup"><span data-stu-id="0ac59-111">**Stepped line**.</span></span> <span data-ttu-id="0ac59-112">Ein Liniendiagramm, in dem eine abgestufte statt einer regulären Linie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ac59-112">A line chart that uses a stepped line instead of a regular line.</span></span> <span data-ttu-id="0ac59-113">Die abgestufte Linie verbindet Punkte miteinander, indem eine Linie verwendet wird, die sie wie die Stufen einer Treppe aussehen lässt.</span><span class="sxs-lookup"><span data-stu-id="0ac59-113">The stepped line connects points by using a line that makes it look like steps on a ladder or staircase.</span></span>  
  
-   <span data-ttu-id="0ac59-114">**Sparklinediagramme**.</span><span class="sxs-lookup"><span data-stu-id="0ac59-114">**Sparkline charts**.</span></span> <span data-ttu-id="0ac59-115">Variationen des Liniendiagramms, die nur die Zeilenreihe in der Zelle einer Tabelle oder einer Matrix anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0ac59-115">Variations of the line chart that show only the line series in the cell of a table or matrix.</span></span> <span data-ttu-id="0ac59-116">Weitere Informationen finden Sie unter [Sparklines und Datenbalken &#40;Berichts-Generator und SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0ac59-116">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="data-considerations-for-line-charts"></a><span data-ttu-id="0ac59-117">Überlegungen zu Daten für ein Liniendiagramm</span><span class="sxs-lookup"><span data-stu-id="0ac59-117">Data Considerations for Line Charts</span></span>  
  
-   <span data-ttu-id="0ac59-118">Um das Standardliniendiagramm einprägsamer darzustellen, sollten Sie in Betracht ziehen, die Breite des Reihenrahmens auf 3 einzustellen und einen Schattenoffset mit dem Wert 1 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ac59-118">To improve the visual impact of the default line chart, consider changing the width of the series border to 3, and adding a shadow offset of 1.</span></span> <span data-ttu-id="0ac59-119">Hierdurch wird ein weit fetteres Liniendiagramm erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac59-119">This will create a much bolder line chart.</span></span> <span data-ttu-id="0ac59-120">Diese Eigenschaften müssen auf die ursprünglichen Werte zurückgesetzt werden, wenn Sie den Diagrammtyp von Linie in einen anderen Typ ändern.</span><span class="sxs-lookup"><span data-stu-id="0ac59-120">You will need to revert these properties to their original values if you change the chart type from Line to another type.</span></span>  
  
-   <span data-ttu-id="0ac59-121">Falls das Dataset leere Werte enthält, werden vom Liniendiagramm leere Punkte in Form von Platzhalterlinien hinzugefügt, um die Kontinuität im Diagramm zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="0ac59-121">If your dataset includes empty values, the line chart will add empty points, in the form of placeholder lines, in order to maintain continuity on the chart.</span></span> <span data-ttu-id="0ac59-122">Falls Sie nicht möchten, dass diese Linien angezeigt werden, können Sie das Dataset mit einem nicht zusammenhängenden Diagrammtyp anzeigen, beispielsweise einem Balken- oder Säulendiagramm.</span><span class="sxs-lookup"><span data-stu-id="0ac59-122">If you would rather not see these lines, consider displaying your dataset using a non-contiguous chart type such as a bar or column chart.</span></span>  
  
-   <span data-ttu-id="0ac59-123">Ein Liniendiagramm erfordert mindestens zwei Punkte, um eine Linie zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="0ac59-123">A line chart requires at least two points to draw a line.</span></span>  <span data-ttu-id="0ac59-124">Falls das Dataset nur einen Datenpunkt aufweist, wird das Liniendiagramm als einzelner Datenpunktmarker angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ac59-124">If your dataset has only one data point, the line chart will display as a single data point marker.</span></span>  
  
-   <span data-ttu-id="0ac59-125">Eine als Linie gezeichnete Reihe nimmt in einem Diagrammbereich nur wenig Raum ein.</span><span class="sxs-lookup"><span data-stu-id="0ac59-125">A series that is drawn as a line will not take up much space within a chart area.</span></span>  <span data-ttu-id="0ac59-126">Aus diesem Grund werden Liniendiagramme häufig mit anderen Diagrammtypen, z. B. Säulendiagrammen, kombiniert.</span><span class="sxs-lookup"><span data-stu-id="0ac59-126">For this reason, line charts are frequently combined with other chart types such as column charts.</span></span> <span data-ttu-id="0ac59-127">Liniendiagramme können jedoch nicht mit Balken-, Polar-, Kreis- oder Formdiagrammtypen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="0ac59-127">However, you cannot combine a line chart with bar, polar, pie or shape chart types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac59-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ac59-128">See Also</span></span>  
 <span data-ttu-id="0ac59-129">[Balkendiagramme &#40;Berichts-Generator und SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0ac59-129">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0ac59-130">[Säulendiagramme (Berichts-Generator und SSRS)](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0ac59-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0ac59-131">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0ac59-131">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0ac59-132">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0ac59-132">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0ac59-133">[Flächendiagramme (Berichts-Generator und SSRS)](area-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0ac59-133">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0ac59-134">[Leere und NULL-Datenpunkte in Diagrammen (Berichts-Generator und SSRS)](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0ac59-134">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0ac59-135">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0ac59-135">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
