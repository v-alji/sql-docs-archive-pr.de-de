---
title: Hinzufügen von Skalierungsunterbrechungen zu einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 84d66436-ed62-4967-bbbd-b457593ee787
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c081debd1e0a84158615edebdb6b84705c10e5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719573"
---
# <a name="add-scale-breaks-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="92a69-102">Hinzufügen von Skalierungsunterbrechungen zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="92a69-102">Add Scale Breaks to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="92a69-103">Eine Skalierungsunterbrechung ist ein Streifen, der über den Zeichnungsbereich eines Diagramms gezogen wird, um eine Unterbrechung in der Kontinuität zwischen den hohen und den niedrigen Werten auf einer Wertachse (normalerweise die vertikale oder y-Achse) zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="92a69-103">A scale break is a stripe drawn across the plotting area of a chart to denote a break in continuity between the high and low values on a value axis (usually the vertical, or y-axis).</span></span> <span data-ttu-id="92a69-104">Verwenden Sie eine Skalierungsunterbrechung, um zwei unterschiedliche Bereiche in der gleichen Diagrammfläche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="92a69-104">Use a scale break to display two distinct ranges in the same chart area.</span></span>  
  
 <span data-ttu-id="92a69-105">![Diagramm mit Skalierungsunterbrechung](../media/rs-multipledatarangeschart-scalebreak.gif "Diagramm mit Skalierungsunterbrechung")</span><span class="sxs-lookup"><span data-stu-id="92a69-105">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92a69-106">Sie können nicht angeben, an welcher Stelle im Diagramm eine Skalierungsunterbrechung platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="92a69-106">You cannot specify where to place a scale break on your chart.</span></span> <span data-ttu-id="92a69-107">Das Diagramm bestimmt anhand eigener, auf den Werten im Dataset basierenden Berechnungen, ob eine ausreichende Trennung zwischen den Datenbereichen vorhanden ist, um eine Skalierungsunterbrechung auf der Wertachse (Y-Achse) zur Laufzeit zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="92a69-107">The chart uses its own calculations based on the values in your dataset to determine whether there is sufficient separation between data ranges to draw a scale break on the value axis (y-axis) at run time.</span></span>  
  
 <span data-ttu-id="92a69-108">Ein Beispiel eines Diagramms mit Skalierungsunterbrechungen ist als Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="92a69-108">An example of a chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="92a69-109">Weitere Informationen zum Herunterladen des Beispielberichts und anderer Berichte finden Sie unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Beispielberichte zu Berichts-Generator und Berichts-Designer](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="92a69-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-scale-breaks-on-the-chart"></a><span data-ttu-id="92a69-110">So aktivieren Sie Skalierungsunterbrechungen für das Diagramm</span><span class="sxs-lookup"><span data-stu-id="92a69-110">To enable scale breaks on the chart</span></span>  
  
1.  <span data-ttu-id="92a69-111">Klicken Sie mit der rechten Maustaste auf die vertikale Achse, und klicken Sie dann auf **Achseneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="92a69-111">Right-click the vertical axis and then click **Axis Properties**.</span></span> <span data-ttu-id="92a69-112">Das Dialogfeld **Eigenschaften für vertikale Achsen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92a69-112">The **VerticalAxis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="92a69-113">Aktivieren Sie das Kontrollkästchen **Skalierungsunterbrechungen aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="92a69-113">Select the **Enable scale breaks** check box.</span></span>  
  
### <a name="to-change-the-style-of-the-scale-break"></a><span data-ttu-id="92a69-114">So ändern Sie den Stil der Skalierungsunterbrechung</span><span class="sxs-lookup"><span data-stu-id="92a69-114">To change the style of the scale break</span></span>  
  
1.  <span data-ttu-id="92a69-115">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="92a69-115">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="92a69-116">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Y-Achse des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="92a69-116">On the design surface, right-click on the y-axis of the chart.</span></span> <span data-ttu-id="92a69-117">Die Eigenschaften für das Y-Achsenobjekt (standardmäßig als Diagrammachse bezeichnet) werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92a69-117">The properties for the y-axis object (named Chart Axis by default) are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="92a69-118">Erweitern Sie im Abschnitt **Skala** die ScaleBreakStyle-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="92a69-118">In the **Scale** section, expand the ScaleBreakStyle property.</span></span>  
  
4.  <span data-ttu-id="92a69-119">Ändern Sie die Werte für ScaleBreakStyle-Eigenschaften, z.B. BreakLineType und Spacing.</span><span class="sxs-lookup"><span data-stu-id="92a69-119">Change the values for ScaleBreakStyle properties, such as BreakLineType and Spacing.</span></span> <span data-ttu-id="92a69-120">Weitere Informationen zu Skalierungsunterbrechungseigenschaften finden Sie unter [Anzeigen einer Reihe mit mehreren Datenbereichen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span><span class="sxs-lookup"><span data-stu-id="92a69-120">For more information about scale break properties, see [Displaying a Series with Multiple Data Ranges on a Chart &#40;Report Builder and SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a69-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92a69-121">See Also</span></span>  
 <span data-ttu-id="92a69-122">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92a69-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="92a69-123">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92a69-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="92a69-124">Achseneigenschaften (Dialogfeld), Achsenoptionen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="92a69-124">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
