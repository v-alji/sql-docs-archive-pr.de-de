---
title: Polardiagramme (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c9402d8f-202a-4cdf-949e-50f5b1d2b885
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b8c4dd9394fab3e076c4a714375954a616e081f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695294"
---
# <a name="polar-charts-report-builder-and-ssrs"></a><span data-ttu-id="3cdf3-102">Polardiagramme (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="3cdf3-102">Polar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3cdf3-103">Ein Polardiagramm zeigt eine Reihe als Satz von Punkten an, die nach der Kategorie in einem 360-Grad-Kreis angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-103">A polar chart displays a series as a set of points that are grouped by category on a 360-degree circle.</span></span> <span data-ttu-id="3cdf3-104">Werte werden durch den Abstand der Punkte von der Mitte des Kreises dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-104">Values are represented by the length of the point as measured from the center of the circle.</span></span> <span data-ttu-id="3cdf3-105">Je weiter der Punkt von der Mitte entfernt liegt, desto größer ist sein Wert.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-105">The farther the point is from the center, the greater its value.</span></span> <span data-ttu-id="3cdf3-106">Kategoriebezeichnungen werden auf dem Umkreis des Diagramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-106">Category labels are displayed on the perimeter of the chart.</span></span> <span data-ttu-id="3cdf3-107">Weitere Informationen zu Hinzufügen von Daten zu einem Polardiagramm finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3cdf3-107">For more information on how to add data to a polar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="3cdf3-108">Abweichungen</span><span class="sxs-lookup"><span data-stu-id="3cdf3-108">Variations</span></span>  
  
-   <span data-ttu-id="3cdf3-109">**Netzdiagramm**.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-109">**Radar chart**.</span></span> <span data-ttu-id="3cdf3-110">Ein Netzdiagramm zeigt eine Serie als zirkuläre Linie oder Bereich an.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-110">A radar chart displays a series as a circular line or area.</span></span> <span data-ttu-id="3cdf3-111">Im Gegensatz zum Polardiagramm zeigt das Netzdiagramm die Daten nicht im Hinblick auf polare Koordinaten an.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-111">Unlike the polar chart, the radar chart does not display data in terms of polar coordinates.</span></span>  
  
## <a name="data-considerations-for-polar-charts"></a><span data-ttu-id="3cdf3-112">Überlegungen zu Daten für ein Polardiagramm</span><span class="sxs-lookup"><span data-stu-id="3cdf3-112">Data Considerations for Polar Charts</span></span>  
  
-   <span data-ttu-id="3cdf3-113">Das Netzdiagramm ist für Vergleiche zwischen mehreren Serien von Kategoriedaten nützlich.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-113">The radar chart is useful for comparisons between multiple series of category data.</span></span>  
  
-   <span data-ttu-id="3cdf3-114">Polardiagramme werden am häufigsten zur Aufzeichnung von polaren Daten verwendet, bei denen jeder Datenpunkt durch einen Winkel und einen Abstand festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-114">Polar charts are most commonly used to graph polar data, where each data point is determined by an angle and a distance.</span></span>  
  
-   <span data-ttu-id="3cdf3-115">Polardiagramme können nicht mit anderen Diagrammtypen im gleichen Diagrammbereich kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-115">Polar charts cannot be combined with any other chart type in the same chart area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cdf3-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cdf3-116">Example</span></span>  
 <span data-ttu-id="3cdf3-117">Im folgenden Beispiel wird gezeigt, wie ein Netzdiagramm verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-117">The following example shows how a radar chart can be used.</span></span> <span data-ttu-id="3cdf3-118">In der unten stehenden Tabelle werden Beispieldaten für das Diagramm bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-118">The table below provides sample data for the chart.</span></span>  
  
|<span data-ttu-id="3cdf3-119">Name</span><span class="sxs-lookup"><span data-stu-id="3cdf3-119">Name</span></span>|<span data-ttu-id="3cdf3-120">Sales</span><span class="sxs-lookup"><span data-stu-id="3cdf3-120">Sales</span></span>|  
|----------|-----------|  
|<span data-ttu-id="3cdf3-121">Sträucher</span><span class="sxs-lookup"><span data-stu-id="3cdf3-121">Shrubs</span></span>|<span data-ttu-id="3cdf3-122">61</span><span class="sxs-lookup"><span data-stu-id="3cdf3-122">61</span></span>|  
|<span data-ttu-id="3cdf3-123">Samen</span><span class="sxs-lookup"><span data-stu-id="3cdf3-123">Seeds</span></span>|<span data-ttu-id="3cdf3-124">78</span><span class="sxs-lookup"><span data-stu-id="3cdf3-124">78</span></span>|  
|<span data-ttu-id="3cdf3-125">Zwiebeln</span><span class="sxs-lookup"><span data-stu-id="3cdf3-125">Bulbs</span></span>|<span data-ttu-id="3cdf3-126">60</span><span class="sxs-lookup"><span data-stu-id="3cdf3-126">60</span></span>|  
|<span data-ttu-id="3cdf3-127">Strukturen</span><span class="sxs-lookup"><span data-stu-id="3cdf3-127">Trees</span></span>|<span data-ttu-id="3cdf3-128">38</span><span class="sxs-lookup"><span data-stu-id="3cdf3-128">38</span></span>|  
|<span data-ttu-id="3cdf3-129">Blumen</span><span class="sxs-lookup"><span data-stu-id="3cdf3-129">Flowers</span></span>|<span data-ttu-id="3cdf3-130">81</span><span class="sxs-lookup"><span data-stu-id="3cdf3-130">81</span></span>|  
  
 <span data-ttu-id="3cdf3-131">In diesem Beispiel wird das Feld Name in den Bereich Kategoriegruppen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-131">In this example, the Name field is placed in the Category Groups area.</span></span> <span data-ttu-id="3cdf3-132">Das Feld Verkauf wird in den Bereich Werte eingefügt.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-132">The Sales field is placed in the Values area.</span></span> <span data-ttu-id="3cdf3-133">Das Feld Verkauf wird automatisch für das Diagramm aggregiert, wenn Sie es ablegen.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-133">The Sales field is automatically aggregated for the chart when you drop it.</span></span> <span data-ttu-id="3cdf3-134">Im Netzdiagramm wird basierend auf der Anzahl der Werte im Feld "Verkauf" berechnet, wo die Bezeichnungen platziert werden. Das Feld enthält fünf Werte, und es werden fünf Bezeichnungen an Punkten mit gleichem Abstand auf einem Kreis platziert.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-134">The radar chart calculates where to place the labels based on the number of values in the Sales field, which contains five values and places labels at five equidistant points on a circle.</span></span> <span data-ttu-id="3cdf3-135">Wenn das Feld "Verkauf" drei Werte enthielte, würden die Bezeichnungen an drei Punkten mit gleichem Abstand auf einem Kreis platziert.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-135">If the Sales field contained three values, the labels would be placed at three equidistant points on a circle.</span></span>  
  
 <span data-ttu-id="3cdf3-136">Die folgende Abbildung zeigt ein Beispiel für ein Netzdiagramm auf Grundlage der dargestellten Daten.</span><span class="sxs-lookup"><span data-stu-id="3cdf3-136">The following illustration shows an example of a radar chart based on the data presented.</span></span>  
  
 <span data-ttu-id="3cdf3-137">![Netzdiagramm](../media/rs-radarchart.gif "Netzdiagramm")</span><span class="sxs-lookup"><span data-stu-id="3cdf3-137">![Radar chart](../media/rs-radarchart.gif "Radar chart")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdf3-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cdf3-138">See Also</span></span>  
 <span data-ttu-id="3cdf3-139">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3cdf3-139">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3cdf3-140">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3cdf3-140">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3cdf3-141">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3cdf3-141">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3cdf3-142">[Liniendiagramme (Berichts-Generator und SSRS)](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3cdf3-142">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3cdf3-143">Leere und NULL-Datenpunkte in Diagrammen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3cdf3-143">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
