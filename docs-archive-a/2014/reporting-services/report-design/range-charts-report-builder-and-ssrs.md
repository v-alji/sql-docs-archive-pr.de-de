---
title: Bereichsdiagramme (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48e351d3-ac5b-4eda-a4bd-32a0de206a30
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 76a9723bc55030da59d22c945a40ce4418b84ab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717464"
---
# <a name="range-charts-report-builder-and-ssrs"></a><span data-ttu-id="7eff0-102">Bereichsdiagramme (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="7eff0-102">Range Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7eff0-103">Ein Bereichsdiagramm zeigt eine Menge von Datenpunkten an, die jeweils durch mehrere Werte für dieselbe Kategorie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7eff0-103">A range chart type displays a set of data points that are each defined by multiple values for the same category.</span></span> <span data-ttu-id="7eff0-104">Die Werte werden durch die Höhe der Markierung, gemessen an der Wertachse, dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7eff0-104">Values are represented by the height of the marker as measured by the value axis.</span></span> <span data-ttu-id="7eff0-105">Kategoriebezeichnungen werden an der Kategorieachse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7eff0-105">Category labels are displayed on the category axis.</span></span> <span data-ttu-id="7eff0-106">Das einfache Bereichsdiagramm füllt den Bereich zwischen dem oberen und dem unteren Wert für jeden Datenpunkt aus.</span><span class="sxs-lookup"><span data-stu-id="7eff0-106">The plain range chart fills in the area between the top and bottom value for each data point.</span></span>  
  
 <span data-ttu-id="7eff0-107">Die folgende Illustration zeigt ein einfaches Bereichsdiagramm mit drei Reihen.</span><span class="sxs-lookup"><span data-stu-id="7eff0-107">The following illustration shows a plain range chart with three series.</span></span>  
  
 <span data-ttu-id="7eff0-108">![Bereichsdiagramm](../media/rs-rangechart.gif "Bereichsdiagramm")</span><span class="sxs-lookup"><span data-stu-id="7eff0-108">![Range chart](../media/rs-rangechart.gif "Range chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="7eff0-109">Abweichungen</span><span class="sxs-lookup"><span data-stu-id="7eff0-109">Variations</span></span>  
  
-   <span data-ttu-id="7eff0-110">**Glatter Bereich**.</span><span class="sxs-lookup"><span data-stu-id="7eff0-110">**Smooth range**.</span></span> <span data-ttu-id="7eff0-111">Ein glattes Bereichsdiagramm zeigt gekrümmte statt gerade Linien an.</span><span class="sxs-lookup"><span data-stu-id="7eff0-111">A smooth range chart displays curved lines rather than straight.</span></span>  
  
-   <span data-ttu-id="7eff0-112">**Spaltenbereich**.</span><span class="sxs-lookup"><span data-stu-id="7eff0-112">**Column range**.</span></span> <span data-ttu-id="7eff0-113">Ein Spaltenbereichsdiagramm verwendet Spalten statt Flächen, um die Bereiche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7eff0-113">A column range chart uses columns instead of areas to display the ranges.</span></span>  
  
-   <span data-ttu-id="7eff0-114">**Balkenbereich**.</span><span class="sxs-lookup"><span data-stu-id="7eff0-114">**Bar range**.</span></span> <span data-ttu-id="7eff0-115">Ein Balkenbereichsdiagramm verwendet Balken statt Flächen, um die Bereiche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7eff0-115">A bar range chart uses bars instead of areas to display the ranges.</span></span>  
  
## <a name="data-considerations-for-range-charts"></a><span data-ttu-id="7eff0-116">Überlegungen zu Daten für ein Bereichsdiagramm</span><span class="sxs-lookup"><span data-stu-id="7eff0-116">Data Considerations for Range Charts</span></span>  
  
-   <span data-ttu-id="7eff0-117">Bereichsdiagrammtypen erfordern zwei Werte pro Datenpunkt.</span><span class="sxs-lookup"><span data-stu-id="7eff0-117">Range chart types require two values per data point.</span></span> <span data-ttu-id="7eff0-118">Diese Werte entsprechen einem hohen und einem niedrigen Wert, die den Bereich für jeden Datenpunkt definieren.</span><span class="sxs-lookup"><span data-stu-id="7eff0-118">These values correspond with a high value and a low value that defines the range for each data point.</span></span>  
  
-   <span data-ttu-id="7eff0-119">Bereichsdiagramme sind nur für Analysezwecke nützlich, wenn die oberen Werte stets höher sind als die unteren Werte.</span><span class="sxs-lookup"><span data-stu-id="7eff0-119">Range charts are useful for analysis only if the top values are always higher than the bottom values.</span></span> <span data-ttu-id="7eff0-120">Wenn dies nicht der Fall ist, sollten Sie ein Liniendiagramm verwenden.</span><span class="sxs-lookup"><span data-stu-id="7eff0-120">If this is not the case, consider using a line chart.</span></span> <span data-ttu-id="7eff0-121">Wenn der obere Wert niedriger ist als der untere Wert, zeigt das Bereichsdiagramm die absolute Differenz zwischen diesen Werten an.</span><span class="sxs-lookup"><span data-stu-id="7eff0-121">If the high value is lower the low value, the range chart will display the absolute value of the difference between these values.</span></span>  
  
-   <span data-ttu-id="7eff0-122">Ist nur ein Wert angegeben, wird das Bereichsdiagramm wie ein normales Bereichsdiagramm mit einem Wert pro Datenpunkt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7eff0-122">If only one value is specified, the range chart will display as if it were a regular area chart, with one value per data point.</span></span>  
  
-   <span data-ttu-id="7eff0-123">Bereichsdiagramme werden häufig zur Darstellung von Daten verwendet, die Mindest- und Höchstwerte für jede Kategoriegruppe im Dataset enthalten.</span><span class="sxs-lookup"><span data-stu-id="7eff0-123">Range charts are often used to graph data that contains minimum and maximum values for each category group in the dataset.</span></span>  
  
-   <span data-ttu-id="7eff0-124">Die Anzeige von Markern auf jedem Datenpunkt wird im Bereichsdiagramm nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7eff0-124">Displaying markers on each data point is not supported on the range chart.</span></span>  
  
-   <span data-ttu-id="7eff0-125">Wie im Bereichsdiagramm überlappen die Reihen in einem einfachen Bereichsdiagramm, wenn die Werte in mehreren Reihen ähnlich sind.</span><span class="sxs-lookup"><span data-stu-id="7eff0-125">Like the area chart, in a plain range chart, if the values in multiple series are similar, the series will overlap.</span></span> <span data-ttu-id="7eff0-126">In diesem Szenario bietet es sich an, statt eines einfachen Bereichsdiagramms ein Spaltenbereichs- oder Balkenbereichsdiagramm zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7eff0-126">In this scenario, you may want to use a column range or bar range chart instead of a plain range chart.</span></span>  
  
-   <span data-ttu-id="7eff0-127">Gantt-Diagramme können mit einem Bereichsbalkendiagramm erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7eff0-127">Gantt charts can be created using a range bar chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eff0-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eff0-128">See Also</span></span>  
 <span data-ttu-id="7eff0-129">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7eff0-129">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7eff0-130">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7eff0-130">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7eff0-131">Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7eff0-131">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
